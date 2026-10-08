# Mantovani Barbearia — Landing Page

Landing page profissional para barbearia, feita com HTML, CSS e JavaScript puro (sem frameworks e sem etapa de build). Todo o conteúdo é editável em um único bloco de configuração.

## Funcionalidades

- Vídeo de fundo na primeira tela (com fundo animado como alternativa)
- Botões com animações (brilho, elevação e pulso no botão flutuante do WhatsApp)
- Botão de WhatsApp com mensagem pronta
- Seção de serviços com cartões e efeito 3D ao passar o mouse
- Galeria de fotos dos trabalhos, com ampliação ao clicar
- Horários de atendimento, endereço e link do Google Maps
- Link do Instagram (opcional)
- Layout responsivo (celular, tablet e computador)
- Respeita a opção "reduzir movimento" do sistema

## Estrutura

```
barbearia-mantovani/
├── index.html
├── logo-mantovani-transparente.png
├── hero.mp4              # vídeo da primeira tela
└── fotos/                # fotos da galeria (1.jpg, 2.jpg, ...)
```

## Como editar o conteúdo

Abra o `index.html` e procure o bloco `CONFIG` no início do `<script>`:

```js
const CONFIG = {
  nome: "Mantovani Barbearia",
  slogan: "...",
  logo: "logo-mantovani-transparente.png",
  video: { mp4: "hero.mp4", webm: "", poster: "" },
  whatsapp: "5515999999999",   // DDI + DDD + número, só dígitos
  mensagem: "Olá! Quero agendar um horário.",
  endereco: "...",
  mapsUrl: "https://www.google.com/maps/...",
  instagram: "",               // https://instagram.com/perfil
  servicos: [ ... ],
  horarios: [ ... ],
  galeria: ["fotos/1.jpg", "fotos/2.jpg", ...]
};
```

| Campo | O que muda |
|---|---|
| `whatsapp` e `mensagem` | Número e texto inicial da conversa |
| `endereco` e `mapsUrl` | Endereço exibido e link "Como chegar" |
| `servicos` | Nome, descrição e preço de cada serviço |
| `horarios` | Dias e horários de atendimento |
| `galeria` | Lista de fotos (sem arquivo, aparece um espaço reservado) |
| `instagram` | Link do perfil (vazio = não exibe) |

### Vídeo

Salve o vídeo como `hero.mp4` na mesma pasta do `index.html`. Recomendações: 5 a 15 segundos, sem áudio e até 5 MB. Para comprimir:

```bash
ffmpeg -i original.mp4 -vf "scale=1280:-2" -an -c:v libx264 -crf 28 -preset slow hero.mp4
```

### Cores

Edite as variáveis no início do CSS:

```css
:root { --bg:#000; --gold:#f0b82d; /* ... */ }
```

## Como rodar localmente

Abra o `index.html` no navegador, ou use a extensão **Live Server** do VS Code (clique direito no arquivo > *Open with Live Server*).

## Publicação (Vercel)

1. Suba o projeto para o GitHub.
2. Na [Vercel](https://vercel.com), clique em **Add New > Project** e importe o repositório.
3. Deixe as configurações padrão (é um site estático) e clique em **Deploy**.
4. Para domínio próprio, use **Settings > Domains** no projeto.

## Tecnologias

HTML5, CSS3 e JavaScript (ES6). Fontes: Playfair Display e Inter (Google Fonts).

## Autor

Willian — [github.com/willianjsilva-dev](https://github.com/willianjsilva-dev)

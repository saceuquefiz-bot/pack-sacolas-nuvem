# Pack Premium de Sacolas Nuvem — Landing Page

Landing page estática, pronta para produção. Este guia assume que você **nunca usou a Vercel** — vamos do zero até o site no ar, com seu domínio próprio.

## Estrutura do projeto
```
public/
  index.html          → a página inteira (HTML + CSS + JS já minificados)
  images/              → 12 imagens reais do produto, em WebP
vercel.json             → configuração de cache e pasta de publicação
README.md               → este guia
```
Você não precisa entender ou mexer em nenhum desses arquivos técnicos — só precisa subir a pasta inteira.

---

## Antes de começar: escolha seu caminho

Existem dois jeitos de publicar. Recomendo o **Caminho A** porque permite atualizar o site facilmente no futuro, sem repetir todo o processo.

| | Caminho A — GitHub (recomendado) | Caminho B — Vercel Drop (mais rápido) |
|---|---|---|
| Ideal para | Quem vai atualizar o site depois | Quem só quer ver o site no ar agora, rapidinho |
| Atualizações futuras | Automáticas, a cada alteração salva | Manuais, repetindo o processo cada vez |
| Tempo do primeiro deploy | ~10 minutos | ~2 minutos |

Vou explicar os dois. Se estiver em dúvida, siga o **Caminho A**.

---

## Caminho A — Publicando com GitHub (recomendado)

### Passo 1 — Crie sua conta no GitHub
1. Acesse **github.com** e clique em **Sign up**.
2. Preencha e-mail, senha e um nome de usuário.
3. Confirme seu e-mail quando o GitHub pedir.

> O GitHub é apenas o "armário" onde os arquivos do seu site vão ficar guardados. É gratuito.

### Passo 2 — Crie um repositório (uma pasta do projeto no GitHub)
1. Já logada, clique no **+** no canto superior direito → **New repository**.
2. Dê um nome, por exemplo `pack-sacolas-nuvem`.
3. Deixe como **Public** (ou Private, se preferir — ambos funcionam com a Vercel).
4. **Não marque** nenhuma opção de criar README ou .gitignore — deixe o repositório vazio.
5. Clique em **Create repository**.

### Passo 3 — Suba os arquivos do projeto (sem usar comandos)
1. Na página do repositório recém-criado, clique no link **uploading an existing file**.
2. Arraste **a pasta inteira `public`**, o arquivo `vercel.json` e o `README.md` para dentro da área de upload do navegador.
3. Role até o fim da página e clique em **Commit changes**.

> Isso é literalmente arrastar e soltar — nenhum comando de terminal é necessário.

### Passo 4 — Crie sua conta na Vercel
1. Acesse **vercel.com** e clique em **Sign Up**.
2. Escolha **Continue with GitHub** — isso já conecta as duas contas automaticamente.
3. Autorize o acesso quando o GitHub pedir.

### Passo 5 — Importe o projeto na Vercel
1. No painel da Vercel, clique em **Add New… → Project**.
2. Na lista de repositórios, encontre `pack-sacolas-nuvem` e clique em **Import**.
3. A Vercel vai detectar sozinha que é um site estático (graças ao `vercel.json` que já está no projeto, apontando para a pasta `public`). Você não precisa mudar nenhuma configuração.
4. Clique em **Deploy**.

### Passo 6 — Pronto, seu site está no ar
1. Em cerca de 30 segundos a Vercel mostra **"Congratulations!"** com uma imagem do seu site.
2. Você já recebe um endereço gratuito, algo como `pack-sacolas-nuvem.vercel.app`.
3. Clique nele para conferir a Landing publicada de verdade.

---

## Caminho B — Publicando em 2 minutos com Vercel Drop (sem GitHub)

Use esse caminho se quiser ver o site no ar agora mesmo, sem criar conta no GitHub.

1. Crie sua conta na Vercel em **vercel.com** (pode ser com e-mail ou Google).
2. Acesse **vercel.com/drop**.
3. Arraste o arquivo `.zip` do projeto (ou a pasta `public` inteira) para dentro da página.
4. Escolha um nome para o projeto e clique em **Deploy**.
5. Em segundos, a Vercel te entrega um link com o site já publicado.

**Atenção:** nesse caminho, cada vez que você quiser atualizar o site, vai precisar repetir esse mesmo processo (arrastar de novo), e isso cria um projeto/link novo a cada vez. Para atualizações contínuas e automáticas, o Caminho A (GitHub) é o correto.

---

## Conectando seu domínio próprio (ex: packsacolasnuvem.com.br)

Isso funciona igual nos dois caminhos, depois que o site já está publicado.

1. No painel da Vercel, abra o projeto e vá em **Settings → Domains**.
2. Digite o domínio que você comprou (ex: `packsacolasnuvem.com.br`) e clique em **Add**.
3. A Vercel vai te mostrar um ou dois registros para configurar — geralmente um registro **A** e/ou **CNAME**.
4. Abra o painel do lugar onde você **comprou o domínio** (Registro.br, GoDaddy, Hostinger, etc.) e procure por **"Gerenciar DNS"** ou **"Zona DNS"**.
5. Copie exatamente os valores que a Vercel mostrou e cole nos campos correspondentes do seu provedor de domínio.
6. Volte para a Vercel — o status ao lado do domínio muda de "Pendente" para **"Válido"** quando a configuração é reconhecida (pode levar de alguns minutos até algumas horas, dependendo do provedor).

> Dica: se tiver dúvida em qual campo colar cada valor no seu provedor de domínio, a própria tela da Vercel mostra instruções específicas assim que você adiciona o domínio — ela reconhece os provedores mais comuns e te orienta.

---

## Como atualizar a Landing no futuro

**Se você seguiu o Caminho A (GitHub):**
1. Acesse o repositório no site do GitHub.
2. Abra o arquivo que quer alterar (por exemplo `public/index.html`) e clique no ícone de lápis (**Edit**) no canto superior direito.
3. Faça a alteração diretamente na caixa de texto do navegador.
4. Role até o fim e clique em **Commit changes**.
5. Pronto — a Vercel detecta a alteração automaticamente e publica a nova versão em menos de um minuto, **sem você precisar fazer mais nada**.

**Se você seguiu o Caminho B (Vercel Drop):**
1. Faça a alteração no arquivo localmente (ou peça para eu gerar a nova versão).
2. Vá de novo em **vercel.com/drop** e arraste o projeto atualizado.
3. Publique novamente.

---

## Duas coisas para ajustar antes de publicar de verdade

Essas duas informações eu não tinha como preencher por você:

1. **Domínio nas tags de SEO** — dentro do `public/index.html`, existem 3 menções a `SEU-DOMINIO-AQUI.com.br` (usadas nas tags `canonical`, `og:url` e `og:image`, que ajudam o Google e as redes sociais a entenderem seu site). Troque pelo domínio real assim que ele estiver ativo.
2. **Link do botão de compra** — o botão principal de preço aponta para `#oferta` (uma âncora dentro da própria página). Assim que você tiver o link real do seu checkout/pagamento, substitua esse `href="#oferta"` pelo link de verdade.

Qualquer dúvida durante o processo, é só chamar.

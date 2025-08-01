# Simple Notepad 📝

> Um aplicativo minimalista de bloco de notas para macOS, inspirado no clássico Notepad do Windows.

![Simple Notepad](notepad.png)

## 📥 Download Rápido

**Quer usar agora? Baixe o executável pronto:**

[![Download Simple Notepad](https://img.shields.io/badge/Download-Simple%20Notepad%20v1.0.0-blue?style=for-the-badge&logo=apple)](https://github.com/ricardoreis/simple-notepad/releases/download/v1.0.0/Simple.Notepad_1.0.0_aarch64.dmg)

> 💿 **Arquivo DMG** - Compatível com macOS (Apple Silicon M1/M2/M3)  
> 📁 **Instalação**: Baixe → Abra o DMG → Arraste para Applications → Pronto!

---

## ✨ Características

- 🎯 **Interface Ultra-Minimalista**: Apenas uma área de texto limpa, sem distrações
- 🔤 **Fonte Monospace**: Courier New 16px bold para melhor legibilidade
- 📏 **Janela Redimensionável**: Inicia com 640x480px, mas pode ser ajustada conforme necessário
- 💾 **Persistência Automática**: Seu texto é salvo automaticamente e permanece quando você fecha o app
- ⌨️ **Atalhos Nativos**: Cmd+C, Cmd+V, Cmd+A funcionam perfeitamente
- ⚡ **Rápido e Leve**: Aplicação nativa construída com Tauri
- 🎨 **Ícone Personalizado**: Ícone de bloco de notas para fácil identificação

## 🚀 Instalação para Desenvolvedores

### Pré-requisitos
- **Node.js** (versão 14 ou superior)
- **Rust** (será instalado automaticamente se não estiver presente)
- **Xcode Command Line Tools** (macOS)

### Instalação do Rust (se necessário)
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### Clone e Execute
```bash
# Clone o repositório
git clone https://github.com/seu-usuario/simple-notepad.git
cd simple-notepad

# Instale as dependências
npm install

# Execute em modo desenvolvimento
npm run tauri dev
```

## 🛠️ Comandos Disponíveis

| Comando | Descrição |
|---------|-----------|
| `npm run tauri dev` | Executa em modo desenvolvimento |
| `npm run tauri build` | Gera o executável final |
| `npm run dev` | Apenas o servidor web (sem Tauri) |

## 📦 Gerando o Aplicativo Final

Para criar o arquivo `.app` que pode ser instalado:

```bash
npm run tauri build
```

O aplicativo final estará localizado em:
```
src-tauri/target/release/bundle/macos/Simple Notepad.app
```

Você pode:
- Arrastar para a pasta `Applications`
- Executar diretamente do local
- Distribuir para outros usuários

## 🎯 Casos de Uso

- ✅ **Anotações Rápidas**: Para textos temporários e lembretes
- ✅ **Rascunhos**: Área limpa para começar a escrever
- ✅ **Clipboard Manager**: Para armazenar temporariamente textos copiados
- ✅ **Notas de Reunião**: Interface simples sem distrações
- ✅ **Desenvolvimento**: Para snippets de código ou logs temporários

## 🏗️ Arquitetura Técnica

### Stack Tecnológico
- **Frontend**: HTML5, CSS3, JavaScript Vanilla
- **Backend**: Rust com Tauri
- **Persistência**: LocalStorage (navegador)
- **Build**: Vite + Tauri CLI

### Estrutura do Projeto
```
simple-notepad/
├── index.html              # Interface principal
├── vite.config.js          # Configuração do Vite
├── package.json            # Dependências Node.js
├── notepad.png             # Ícone do aplicativo
└── src-tauri/
    ├── src/main.rs         # Código Rust principal
    ├── tauri.conf.json     # Configuração do Tauri
    ├── Cargo.toml          # Dependências Rust
    └── icons/              # Ícones em vários tamanhos
```

## 🔧 Personalização

### Alterando o Tamanho da Fonte
Edite o arquivo `index.html`, linha 29:
```css
font-size: 16px; /* Altere para o tamanho desejado */
```

### Mudando as Dimensões Iniciais
Edite `src-tauri/tauri.conf.json`:
```json
"width": 640,  // Largura inicial
"height": 480  // Altura inicial
```

### Customizando o Ícone
Substitua os arquivos em `src-tauri/icons/` pelos seus próprios ícones.

## 🐛 Resolução de Problemas

### Erro: "cargo not found"
```bash
# Instale o Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### Erro: "failed to get cargo metadata"
```bash
# Adicione o Rust ao PATH
export PATH="$HOME/.cargo/bin:$PATH"
```

### App não abre
1. Verifique se as dependências foram instaladas: `npm install`
2. Tente limpar o cache: `rm -rf node_modules && npm install`
3. Verifique se o Rust está instalado: `cargo --version`

## 🤝 Contribuição

Contribuições são bem-vindas! Por favor:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 🙏 Agradecimentos

- [Tauri](https://tauri.app/) - Framework para aplicações desktop
- [Vite](https://vitejs.dev/) - Build tool rápido
- Inspirado no clássico Notepad do Windows

---

**Feito com ❤️ para quem valoriza a simplicidade**
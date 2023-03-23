# 在Cloudflare Worker上一键部署OpenAI代理
本项目使用Cloudflare Worker提供的无服务器函数功能，创建了一个简单的代理服务器，可以将OpenAI API请求转发到OpenAI服务器，并返回响应。这个代理服务器可以用于保护您的OpenAI API密钥和限制访问。

## 部署步骤
1. 注册并登录Cloudflare
访问 Cloudflare网站(https://www.cloudflare-cn.com/) 并注册一个新账户（如果您还没有账户的话），然后登录到Cloudflare控制台。

2. 安装pnpm
在您的终端或命令提示符窗口中，运行以下命令来安装pnpm：

```
npm install -g pnpm
```
如果您没有足够的权限来运行此命令，则可以使用以下命令：

```
sudo npm install -g pnpm
```
3. 部署代理服务器
在您的终端或命令提示符窗口中，进入到该项目的根目录，并运行以下命令：

```
pnpm i
pnpm run deploy
```
这将使用pnpm安装所需的依赖项，并将代理服务器部署到您的Cloudflare Worker上，中间会提示用户完成Cloudflare API AUTH 授权，按照提示进行操作即可，然后等待部署完成。

4. 使用代理服务器

现在您已经成功部署了代理服务器，要使用代理服务器，只需将OpenAI API请求的URL更改为您的代理服务器的URL即可。如果您的代理服务器URL为“https://my-worker.example.com”，则可以将OpenAI API请求的URL更改为“https://my-worker.example.com/completions”。

## 参考
* [Cloudflare Workers文档](https://developers.cloudflare.com/workers)
* [OpenAI API文档](https://platform.openai.com/docs/api-reference)


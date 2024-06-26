---
titleTemplate: LittleSkin FAQ
description: 任何事物都不可能尽善尽美，LittleSkin 也是如此。如果你在使用 LittleSkin 的过程中遇到了任何问题，看看这个也许会帮到你。
head:
  - - meta
    - name: keywords
      content: mc skin cape 我的世界 faq littleskin 万用皮肤补丁 csl 外置登录 皮肤站 披风 报错 打不开 加载 不显示 无效的会话 看不见 邮件 邮箱
---

# 游戏内加载相关

[[toc]]

## <Badge type="info">皮肤 Mod</Badge> 这不是我自己设置的皮肤 {#not-my-skin}

这个问题通常出现在使用皮肤 Mod（如 _CustomSkinLoader_）加载皮肤的用户当中。

以 CustomSkinLoader 为例，它的默认加载顺序为 _Mojang_ > _LittleSkin_。  
所以，如果你的角色名与某位正版用户相同，那么 CustomSkinLoader 会优先加载那位正版用户的皮肤。

要解决此问题，可以参照 [新手指引 > 配置 Mod > 手动修改配置文件](/newbee/mod.md#edit-csl-config) 章节手动调整加载顺序。

## <Badge type="info">皮肤 Mod</Badge> 别人看不到我的材质 {#no-skin-by-other-players}

只有 **正确安装并配置** 皮肤 Mod 后才能加载来自 LittleSkin 的材质。

如果你想让别人也看见你的材质，请让他们也正确安装并配置皮肤 Mod。

## <Badge type="info">皮肤 Mod</Badge> 为什么我在网站上设置好了材质，但是在游戏中不显示 / 没更新？ {#no-skin}

对于使用皮肤 Mod 加载材质的用户，这是个很常见的问题。大多数情况下，这个问题是以下四个原因引起的：

::: details 1. 你没有正确地安装和配置皮肤 Mod

解决方案：正确安装并配置皮肤 Mod。

你可以在 [新手指引 > 配置 Mod](/newbee/mod.md) 中学习如何正确配置皮肤 Mod；
:::

::: details 2. 你安装的其它 Mod（如 _NonUpdate_）干扰了皮肤 Mod 与 LittleSkin 之间的连接

解决方案：删除这些 Mod，或让它们绕过皮肤 Mod 与 LittleSkin 之间的连接。
:::

::: details 3. 你的材质被皮肤 Mod 缓存了
解决方案：等待几分钟后再试。

如果还是没有更新，尝试清除皮肤 Mod 的缓存，即**直接删除**对应的文件夹：

- CustomSkinLoader 的缓存文件夹为 `.minecraft/CustomSkinLoader/caches`
- SkinPort 的缓存文件夹为 `.minecraft/cachedImages`
:::

::: details 4. 你使用了 Alex 模型的皮肤，并且你的 Minecraft 版本低于 1.8
解决方案：

- 对于 1.7.10，请使用 SkinPort 加载材质。SkinPort 在 1.7.10 上提供了对 Alex 模型的支持。  
  参考 [新手指引 > 配置 Mod > SkinPort](/newbee/mod.md#skinport) 进行配置。
- 对于更低版本，目前无解，你只能更换为 Steve 模型的皮肤。
:::

::: info 使用的是外置登录，但在多人游戏中不显示皮肤？
如果你使用外置登录的方式加载材质，并遇到了如标题所说的问题，请阅读 [下一条👇](#no-skin-in-server)。
:::

如果你确定你的问题不是以上原因引起的，或者你按照以上的解决方案做了之后你的角色的材质依然没有显示或更新，请在详细阅读 [👉 遇到问题怎么办](/problems.md) 以后，带上你的皮肤 Mod 的日志，加入 [官方用户交流群](/user-group.md) 或 [发送邮件工单](/email.md) 询问，或直接购买一对一远程技术支持服务。

## <Badge type="info">外置登录</Badge> 单人游戏中可以正常显示皮肤，但在多人游戏中就不行 {#no-skin-in-server}

这种情况往往在使用 Yggdrasil 外置登录进行服务器联机时出现。

由于 Minecraft 的材质加载机制，在多人游戏中，只有正确配置了外置登录（即**同时满足以下全部条件**），才能正常地在多人游戏中显示你在 LittleSkin 上设置的材质：

- 服务端启用了在线模式（`server.properties` 中 `online-mode=true`）
- [在服务端配置了 Yggdrasil 外置登录](/yggdrasil/server.md)

否则，就会出现如同标题中描述的问题。

如果你有在服务器联机中加载材质的需求，并且你是服主，请在服务端也加载并正确配置 authlib-injector；否则请使用皮肤 Mod 加载材质。

## <Badge type="info">皮肤 Mod</Badge> 为什么我无法使用 Universal Skin Mod 加载材质了？ {#universal-skin-mod}

由于一些技术上的原因，LittleSkin 自 2020 年 1 月起不再支持 UniSkinAPI。你仍然可以通过传统加载方式加载材质，但我们建议使用 Universal Skin Mod 加载材质的用户尽快更换到 CustomSkinLoader。

## <Badge type="info">外置登录</Badge> 启动器下载 authlib-injector 失败  {#authlib-injector-failed-to-download}

虽然可能有多种报错，但一般都是网络原因引起的，请在启动器中更换下载源后再试。

如果你使用 HMCL 3，如果更换下载源后仍然报错，请手动下载 authlib-injector，将其放入 `%appdata%\.hmcl\`（Windows）或 `$HOME/.hmcl/`（Linux 和 macOS）中并重命名为 `authlib-injector.jar`。使用其他启动器的用户请咨询启动器作者。

## <Badge type="info">外置登录</Badge> 外置登录进入服务器时提示「无效的会话」/ accessToken 无效  {#invalid-session}

请先尝试退出游戏并在启动器中删除账号，然后重新登录。

如果重新登录无法解决问题，请检查你在 LittleSkin 绑定的邮箱中是否存在大写英文字母，如果有，请将其更改为全小写字母，然后再次在启动器中重新登录。

如果以上操作均无法解决问题，请在完整阅读并理解 [遇到问题怎么办](/problems.md) 后，加入 [官方用户交流群](/user-group.md#主用户群) 询问。

## LittleSkin 支持 Minecraft 中国版（国服）吗？ {#about-netease}

取决于你使用的皮肤 Mod 是否支持 Minecraft 中国版。

我们没有进行过测试，但从我们目前了解的信息来看，在对 Minecraft 中国版客户端进行一些特殊处理后，CustomSkinLoader 可以在 Minecraft 中国版中很好地运行。

我们不建议用户在 Minecraft 中国版中使用 LittleSkin，这可能给你带来被网易封禁的风险。我们不会对想要在 Minecraft 中国版中使用 LittleSkin 的用户提供技术支持，就算你是捐助者也一样。用户在 Minecraft 中国版中使用 LittleSkin 是用户的个人行为，与我们无关。

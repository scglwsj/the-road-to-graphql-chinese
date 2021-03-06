# Apollo

​在给定问题上找到正确的解决方案并不总是那么简单，使用 GrahpQL 构建 Web 应用程序就是一个很好的例子来说明在不断变化的时代中如何应对源源不断的挑战。此外，不断变化的挑战也造成了必须不断进化的解决方案，因此即使作出选择也成为了一项任务。这篇文章将会解读用于 GraphQL 的 Apollo 的解决方案的优缺点，以及你决定使用它时的替代解决方案。

​GraphQL 作为一个查询语言，不仅在 JavaScript 中有一个可供参考的实现，Apollo 在其之上构建了它自己的生态系统，以使 GraphQL 可供更广泛的用户使用。它包括客户端和服务端，他们为两端都提供了一个庞大的库生态系统。这些库也提供了一个中间层 — Apollo Engine，它是一个 GraphQL 网关。本质上讲，Apollo 能成为在 JavaScript 应用中使用 GraphQL 的最流行选择之一也是有原因的。

## Apollo 优势

​为了更全面的对比，接下来我们来看看使用 Apollo 的一些优势。如果你认为这些列表里有任何遗漏，请随时联系我。

### Apollo 的生态圈

​虽然 GraphQL 还处在早期阶段，但 Apollo 生态圈为其他许多挑战提供了解决方案。除此之外，我们可以看到生态圈的增长，因为在每一次技术会议上，相关公司都会宣布 Apollo 和使用了 Apollo 技术栈的库的一些更新。然而，Apollo 不只是涵盖了 GraphQL；他们还花费精力投入 REST 接口，以便向后兼容 RESTful 架构。这甚至使 GraphQL 超越了网络层和远程数据，也为本地数据提供了状态管理解决方案。

### Apollo 背后的公司和社区

​Apollo 背后的公司正在为其成功倾注大量资源。他们也积极参与开源，提供了很多深入讲解他们产品的文章，并得到了技术会议的支持。总的来说，GraphQL 生态系统[似乎在未来处于良好的状况](https://techcrunch.com/2018/05/15/prisma)。随着越来越多的开发人员接受将 Apollo 用于客户端和 JavaScript 服务端应用程序，GraphQL 背后的社区正在成长。

### 谁在使用 Apollo ？

有很多拥有成熟技术的公司已经在投入 Apollo 的使用了，他们以前熟悉的或许是像 Meteor 那样的流行框架，但像 Airbnb 和 Twitch 这样的新兴并极受欢迎的公司已经在使用它了。以下为部分案例：

* Airbnb [[1]](https://medium.com/airbnb-engineering/reconciling-graphql-and-thrift-at-airbnb-a97e8d290712) [[2]](https://youtu.be/oBOSJFkrNqc)
* [Twitch](https://about.sourcegraph.com/graphql/twitch-our-graphql-transformation)
* [The New York Times](https://open.nytimes.com/the-new-york-times-now-on-apollo-b9a78a5038c)
* [KLM](https://youtu.be/T2njjXHdKqw)
* [Medium](https://www.infoq.com/news/2018/05/medium-reactjs-graphql-migration)

### Apollo 的文档

​虽然 Apollo 持续在发展，但它背后的团队和社区仍然使文档保持最新，他们有许多关于如何构建应用程序的洞见。事实上，他们已经覆盖了初学者所能接触到的绝大多数领域

### Apollo 库

​Apollo 提供了大量的库，用于为 JavaScript 应用程序实现更高效的 GraphQL 技术栈，并且他们的库都是开源的，以便更易于管理。例如：[Apollo Link](https://www.apollographql.com/docs/link/) 提供了一个 API 用于将不同功能链接到 GraphQL 的控制流中。这使得自动的网络重试或 RESTful API 端点替代 GraphQL 端点成为可能（这些端点也可以一起使用）。

​	Apollo 还提供了可替换的库，可以在 Apollo 客户端缓存中看到。Apollo 客户端本身是不会偏向其存储数据的缓存的，就像 Apollo 或者其社区宣传的任何缓存一样。已有可用缓存可以用于设置 Apollo 客户端实例。

### Apollo 的功能

​Apollo 内置了许多特性将复杂性从应用间抽离出来，并且处理客户端和服务端应用程序之间的交集。例如： Apollo 客户端缓存请求，从而使当缓存中已经存在结果时，请求不会被发送两次。该功能可为应用程序提供性能提升，节省宝贵的网络流量。并且, Apollo 客户端会规范化数据，从而使 GraphQL 查询中嵌套的数据被存储在 Apollo 客户端缓存中的规范化数据结构中。数据可以通过标识符从 Apollo 客户端缓存中被读取，而不需要在 "author" 实体中查找 "article" 实体。除了缓存和规范化， Apollo 客户端还有很多新功能，比如：错误管理，支持分页和乐观 UI ，预获取数据，将数据层（Apollo 客户端）连接到视图层（如：React）。

### 与其他框架协作

​Apollo 中有一个库可以使 Apollo 客户端连接 React。 就像 Redux 和 MobX 这样的库一样。React-Apollo 有高阶组件和 render prop 组件来连接彼此。但是，还有其他的库不仅可以连接 Apollo 客户端和 React，还可以连接 Apollo 到 Angular 或者 Vue。这就是使 Apollo 客户端视图层没有限制的原因，这对 JavaScript 生态圈的增长非常有用。

​Apollo 在服务端也与库无关，它提供了几种与 Node.js 库连接的解决方案。基于 Express.js 的 Apollo 服务端是最受开发人员和公司欢迎的选择之一，而且还有其他针对 Apollo 服务端的解决方案，如使用 Node.js 的 Koa 和 Hapi。

### 使用 Apollo 处理现代数据

​还记得我们必须在组件的生命周期方法中强制触发数据获取么？Apollo 客户端解决了这个问题，因为它的数据查询是声明式的。React 经常使用高阶组件或者 render prop 的方式在组件渲染时去自动触发查询。GraphQL 变更是强制触发的，但是那只是因为高阶组件或者 render prop 授予了执行变更的函数权限（比如：在点击按钮时）。从本质上讲，Apollo 信奉声明式编程多过命令式编程。

### 使用 GraphQL 和 Apollo 管理现代状态

​随着 GraphQL 在 JavaScript 应用程序中的兴起， 状态管理进入了另一种混乱状态。即使使用像 Apollo 客户端一样的 GraphQL 库消除了很多痛点，因为它负责远程数据的状态管理，一些开发者会对在哪里放置像 Redux 或者 MobX 这样的库而感到困惑。但是，只需要将这些库用于本地数据管理并将远端数据留给 Apollo 即可。不再需要在 Redux 中通过异步 actions 获取数据了，因此它成了一个可预测所有剩余应用状态（如：本地数据／视图数据／UI 数据）的容器。事实上，剩余应用状态可能足够简单到只需要去使用 React 本身的状态管理而不是 Redux。

​与此同时，Apollo 已经发布了它自己的解决方案，即通过 GraphQL 来处理所有事情来管理原本应该由 React，Redux 或者 MobX 来管理的本地状态。Apollo Link State 库使我们可以通过 GraphQL 的操作来管理本地数据，但 Apollo 的客户端除外。Apollo 说："你不在需要其他的状态管理库，我们会处理你的数据"。这些是开发 JavaScript 应用程序的激动人心的时刻。

### 便捷的开发体验

​使用 Apollo 来写 JavaScript 应用程序变得越来越容易。社区正在推出实现工具。有很多开发工具可以用作浏览器插件，第三方工具来进行 GraphQL 的操作，比如： GraphiQL，以及用于简化开发 Apollo 应用程序的库。例如：Apollo Boost 库提供了一个几乎零配置的 Apollo 客户端设置，以便客户端应用程序开始使用 GraphQL。Apollo 删除了 JavaScript 中 GraphQL 参考实现附带的所有样板实现。

## Apollo 劣势

​为了更全面的对比，接下来我们来看看使用 Apollo 的一些缺点。如果您认为任何一个列表里缺少了任何内容，请随时与我联系。

### 风险

​GraphQL 仍处在早期阶段。Apollo 的用户和所有早期 GraphQL 的采用者都在使用全新的技术。Apollo 团队正在围绕 GraphQL 开发一个丰富的生态系统，提供基础功能和像缓存以及监控一样的高级功能。这伴随着未知的困难，主要因为一切都不是一成不变的。当你更新 GraphQL 相关库时，有些零星的改动可能会带来挑战。相比之下，GraphQL 中的库可能比 Apollo 团队更加保守，但是提供的这些功能也通常没那么强大。

​	快速发展也阻碍了开发者继续学习的能力。GraphQL 和 Apollo 的教程有时已经过时，找到答案可能需要外部资源。不过，大多数的新技术都是这样。

### 在建设中

​Apollo 团队和社区快速实现了很多新功能，但是速度如此之快也需要付出代价。搜索解决方案经常会导向 GitHub， 因为关于该主题的其他信息很少。尽管你确实可以找到关于你的问题的 GitHub issue，但是通常没有解决方案。

​快速开发还伴随着忽视过早期版本的代价。据我的经验，[人们对于 Apollo 放弃 Redux 作为内部状态管理的解决方案感到困惑](https://github.com/apollographql/apollo-client/issues/2593)。Apollo 并没有对 Redux 应该如何与它一起使用发表意见，但是因为它的内部已经决定放弃 Redux 作为内部状态管理的解决方案，当 Apollo 2.0 发布时，许多人并不知道如何继续。我认为 Apollo 背后的团队可能正在努力跟上快节奏的 GraphQL 生态系统，但是能够注意到开源开发中的所有声音并不是那么容易。

### 它大胆且时尚

​Apollo 很大胆，因为它不仅是 JavaScript 中 GraphQL 的客户端和服务端间的网络层生态系统，还将自己定位为未来的数据管理解决方案。它使用 GraphQL，用于 RESTful API 的 apollo-link-rest ，以及用于本地状态管理的 apollo-link-state 来连接客户端和后端应用程序。一些专家对于 "GraphQL 一切"持怀疑态度，但是时间会证明它是否影响市场。

​Apollo 很时尚，因为它能跟得上最新趋势。在 React 中，最新趋势是 render prop 组件。正应如此，可以说 render prop 组件的好处是多于高阶组件的，React Apollo 库紧挨着高阶组件介绍了 [render prop 组件](https://www.robinwieruch.de/react-render-props-pattern/)。提供多种解决方案是个非常明智之举，因为高阶和 render prop 组件都有各自的优缺点。但是，Apollo 确实提倡 render props 多于高阶组件，不清楚这是否是炒作驱动开发或营销或是他们真的相信这是未来之路。Render props 在 React 中相对较新，所以会开发人员需要花时间才能意识到他们自己带来的缺陷（参见：高阶组件）。我已经看见 React 应用程序因为在一个 React 组件中使用多个 render prop 组件而变得越来越冗长，尽管一个 render prop 不会依赖另一个 render prop，而不是通过使用高阶组件来协同 React 组件。毕竟，Apollo 提供了两种解决方案， rende props 和高阶组件，所以开发者可以根据具体情况做决定。对于用户来说，这是一个好兆头，Apollo 团队正在跟上其他库的最新趋势，而不是把自己局限在泡沫里。

### 缺少竞争

​这些问题大都与 GraphQL 的新特性有关，这些问题可以应用于同一领域的几乎任何其他开源解决方案。但是，其中主要的一个问题是 GraphQL 在 JavaScript 领域中缺少竞争。下一节将会罗列几种 Apollo 的替代方案，但是与 Apollo 的生态系统相比，它们是很有限的。虽然可以为 GraphQL 写你自己的库（比如： React 客户端中一个简单的 GraphQL），但是并没有很多开发者尝试过。Apollo 解决的问题并非微不足道，但是我认为竞争对于 JavaScript 生态圈中的 GraphQL 来说是一个健康的推动。现在 GraphQL 有巨大的潜力，开源开发者使用它非常的明智。

## 针对 JavaScript, React 和 Node.js 的 Apollo 替代选择

​有一些缺点源于使用 GraphQL 作为 RESTful 驱动架构的替代方案。在 JavaScript 中也有一些替代 Apollo 客户端和 Apollo 服务端去消费 GraphQL APIs 的方案。以下列表应该会提供有关 JavaScript 生态系统中解决方案的洞见，用于 React 在客户端和 Node.js 在服务端的场景。

###  针对 React 的 Apollo Client 替代选择

​对于 React，Angular，Vue 或者类似应用程序的 [Apollo 客户端](https://github.com/apollographql/apollo-client)，有一些替代选择。像 Apollo 一样，他们都有各自的优缺点。

* 普通的 HTTP 请求：尽管可以使用复杂的 GraphQL 库来操作 GraphQL，GraphQL 并不关注它自身的网络层。因此你可以将 GraphQL 和普通的 HTTP 方法结合使用，只使用一个端点 ，其中包括固定的针对 GraphQL 查询和变更的负载结构。

* [Relay]((https://github.com/facebook/relay)): Relay 是 Facebook 的一个在 React 应用程序客户端中使用 GraphQL 的库。它是出现在 Apollo 之前的第一批 GraphQL 客户端库。

* [urql]((https://github.com/FormidableLabs/urql)): urql 是来自 Formidable Labs 的 GraphQL 客户端库，用于在 React 应用程序中使用 GraphQL。它是开源的，是日益壮大的 Apollo 的简化替代品。

* [graphql.js](https://github.com/f/graphql.js/): graphql.js 不应该被误解为 GraphQL 的参考实现。它就是个简单的，服务于没有 Vue，React 或 Angular 这样的强大的库的应用程序的 GraphQL 客户端。

* [AWS Amplify - GraphQL 客户端](https://github.com/aws/aws-amplify): AWS Amplify 系列为支持云的应用提供库。其中一个模块是被用于常规 GraphQL 服务或 AWS AppSync APIs 的 GraphQL 客户端。

### 针对 Node.js 的 Apollo Server 替代选择

​对于 Express，Koa，Hapi 或者其他 Node.js 库的  [Apollo 服务端](https://github.com/apollographql/apollo-server)，还有一些替代方案可以查看。显然它们都有自己的优劣势，然而并没有在这里讨论。

* [express-graphql](https://github.com/graphql/express-graphql): 这个库提供了一个低级 API 去连接 GraphQL 层到 Express 的中间件。它使用纯 GraphQL.js 参考实现来定义 GraphQL 的概要，而 Apollo 服务端却为开发者简单化了它。

* [graphql-yoga](https://github.com/prisma/graphql-yoga): 一个专注于简单启动，性能和出色的开发者体验的功能完整的 GraphQL 服务。它建立在其他的GraphQL 库之上，可以为我们减少样板代码。

| |

当你想用 GraphQL 接口多于 RESTful 接口时，有很多原因去使用 Apollo 及其为 JavaScript 应用程序开发的生态系统。它们的库与框架无关，因此它们可以和各种客户端框架，如：React， Angular， Vue 和服务端应用程序，如：Express，Koa，Hapi 一起使用。
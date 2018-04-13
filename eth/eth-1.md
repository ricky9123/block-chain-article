![97BB4625FC0F77D101B26D42954C2874.jpg][1]

# 以太坊概述

## 为什么介绍以太坊

尽管很多人对区块链不甚了解，但是一定听说过比特币。比特币作为开山劈地的区块链元老，首先介绍一定不会引起争议。

以太坊是什么？
为什么以太坊够资格作为第二个介绍的区块链技术？
​其实就是作者的喜好而已 = =

当然也不仅仅如此，在之前我有提到，比特币的技术架构属于区块链1.0技术架构，而以太坊属于区块链2.0技术架构，从1.0走向2.0最主要的不同是2.0技术架构拥有了智能合约层，区块链系统拥有了更加完备的开发能力。

我用这样一个比喻方便理解：

区块链1.0技术架构就像是**计算器**，基本只能用于加减乘除等数值计算，有些高级计算器也可以提供一定的开发功能（如函数的定义）。

![euro-870757_1280.jpg][2]

区块链2.0技术架构就像是**计算机**，你可以在计算机上开发各种软件，既可以是计算器，也可以是扫雷游戏。

![office-583839_1280.jpg][3]

以太坊就是当前区块链2.0技术架构的代表。下图为加密货币资本市值排名：

![EA872AAA-11D6-4E19-B630-6D9E698E1923.png][4]

从排名中，我们也可以看到资本市场对以太坊的热衷程度。一些人认为，区块链2.0的代表以太坊足以取代比特币，不过我认为这种思想过于激进，可能性很小。

## 以太坊与以太币

通常，**以太坊（Ethereum）**表示的是**有智能合约功能的区块链开发平台**，而**以太币（Ether）**指的是**以太坊上用于交易的货币**。

类似于比特币，以太币也是一种区块链货币，只能在以太坊平台上使用。

![7692CB35-4CB2-47AE-AB93-0DDE3476D36F.png][5]

上图是以太坊测试网络下的账户以太币余额截图（假装自己真的拥有35.218 ETH）。

## 以太坊简史

比特币的发明者中本聪至今仍是个谜，网上流传的各种关于中本聪本人的照片与新闻实际上都未经过证实。但是以太坊不同，以太坊的创始人“V神”从以太坊创立之初到现在都一直都出现在公众视野里。

![1280px-VitalikButerinProfile.jpg][6]

关于“V神”Vitalik Buterin的履历，你可以在搜索引擎简单获取到，我就不多余赘述，这里简单介绍几个时间点：

- 2011年，17岁的V神接触了比特币，从刚开始的嗤之以鼻到一心投身区块链技术中。
- 2013年，V神从加拿大滑铁卢大学辍学，开始了自己的游学经历，和全世界的区块链爱好者交流学习。
- 2013年末，游学结束的V神撰写了以太坊白皮书，获得广泛认可。
- 2014年，以太坊进行ICO，募集了31000个比特币，募集价格为1比特币=2000以太币。
- 2015年，以太坊正式上线。

我们可以看到，以太坊相比于比特币而言，是一个更加年轻的区块链技术。从比特币诞生到以太坊正式上线，这中间区块链技术也曾爆发式增长，其中许多虚拟货币早已无人问津。相比这些虚拟货币，以太坊最大的特点就是拥有**智能合约**。

之前的文章我们已经提到，**智能合约**意味着区块链平台拥有更加强大的开发能力，这种开发能力相比于比特币本身的交易脚本而言，无论是开发难度和开发能力上都是质的飞跃。对于程序员，编写智能合约就如同你开发一个服务端App一样简单。

![D2C09D4C-7330-4E61-9052-5582BEEFA966.png][7]

## 以太坊与ERC20代币

如果你想发行一个自己的区块链虚拟货币，怎么办？

其实非常简单，你完全可以把比特币的源码拿过来改个名字部署一份，然而并没有人使用这个货币交易，也并没有人为你挖矿，或许整个区块链网络只有你一个矿机。

啥？你说想用更方便的方式发行一个虚拟货币？

当然也可以，如果我们使用刚才所说的方式发行虚拟货币，实际上是“创造”了一个全新的区块链网络。我们吹了这么久智能合约，当然也可以通过编写智能合约，在以太坊之上发行具有特定功能的代币。

以太坊的智能合约有ERC20(Ethereum token standard)协议，我们可以编写符合ERC20的智能合约来发行属于我们的代币，这样的代币区别于区块链上的原生币（以太坊上的原生币就是以太币）。

ERC20协议的标准接口如下：

```solidity
contract ERC20Interface {
function totalSupply() public constant returns (uint);
function balanceOf(address tokenOwner) public constant returns (uint balance);
function allowance(address tokenOwner, address spender) public constant returns (uint remaining);
function transfer(address to, uint tokens) public returns (bool success);
function approve(address spender, uint tokens) public returns (bool success);
function transferFrom(address from, address to, uint tokens) public returns (bool success);

event Transfer(address indexed from, address indexed to, uint tokens);
event Approval(address indexed tokenOwner, address indexed spender, uint tokens);
}
```
你可能不太懂编程，上述接口主要定义了一个货币该有的基本功能：查询货币总量、查询余额、转账等。通过实现上述接口，你可以用不到100行代码定义一个具备基础功能的代币。

现有的很多虚拟货币其实都是[以太坊上的ERC20代币](https://etherscan.io/tokens)，目前以太坊上总共有68229种ERC20代币，当然其中不乏有很多骗钱的空气币。

![6BF40093626C63AEF678F006769BF21A.jpg][8]

其中排名第一的EOS，我将会在下一个大篇目里讲到。当今EOS是一个大热门，一些人认为，当EOS脱离以太坊回归自己的主链后，将会取代以太坊。让我们拭目以待。




  [1]: http://blockchain8.tech/usr/uploads/2018/04/3101884876.jpg
  [2]: http://blockchain8.tech/usr/uploads/2018/04/2187210467.jpg
  [3]: http://blockchain8.tech/usr/uploads/2018/04/2476749269.jpg
  [4]: http://blockchain8.tech/usr/uploads/2018/04/675072174.png
  [5]: http://blockchain8.tech/usr/uploads/2018/04/1164759014.png
  [6]: http://blockchain8.tech/usr/uploads/2018/04/2466234790.jpg
  [7]: http://blockchain8.tech/usr/uploads/2018/04/3077308426.png
  [8]: http://blockchain8.tech/usr/uploads/2018/04/1436681647.jpg
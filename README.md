# learningpython
A project to help me learn Python

# Things to learn in Python

- [ ] basics 
	- [The Python Tutorial](https://docs.python.org/2/tutorial/index.html)
- [ ] decorator 装饰器在框架中运用的很多，比如flask_login，要精通至少很随意的写出满足需求的装饰器，用装饰器肯定需要functools模块的支持
- [ ] generator 说道生成器就自然地联系到各种推导式（列表，元祖，字段，集合），那肯定也要提到itertools模块，contextlib标准库中是个典范，说到contextlib就需要提到with协议，迭代器协议，以及标准库中的哪些实现了它们，如文件描述符，线程锁，继续延伸的话需要了解greenlet提供的协程，那就不得不提gevent,eventlet
- [ ] 描述符 这你就得知道所有的函数其实都是描述符，property,classmethod,staticmethod都是通过描述符实现的，那就得提到werkzeug和bottle都提供的cached_property，都是访问属性的就得提到
__getattr__和__getattribute__，知道在合适的时候定义合适的方法简化流程
- [ ] Pythonic 所谓 Pythonic，就是相比其它语言，Python 可以通过更加优雅的实现方式（不管是语法糖还是什么），比如（包括但不限于） with、for-else、try-else、yield 等。
另外你还需要掌握这些所谓魔法的实现原理，了解 Python 在语法层面的一些协议，可以自己实现语法糖。如 with 的实现方式（上下文管理器）等。
	- [The Python Language Reference](https://docs.python.org/2/reference/index.html)
	- [Python HOWTOs](https://docs.python.org/2/howto/index.html)
- [ ] meta-class 其实这玩意用处很大，如sqlalchemy，django的orm中field的定义都用到了它，那你得知道当python解析py时，发现__metaclass__的时候就会调用元类的__new__和__init__,如果你理解元类的__new__和__init__的第一个参数都是类(而不是self)那元类就差不多了
- [ ] multithread 虽说python由于gil的限制不能利用多核，但在处理io密集型的任务还是有很大好处的,
那得知道threading.RLock是线程可重入锁，daemon thread的用处(python执行环境会等待所有非daemon thread的结束)，Queue是线程安全的锁，logging是线程安全的日志模块，还有线程池也要熟悉
- [ ] others 如python2,6/7包含了不少新特性，如abc模块的抽象方法机制，collections提供的有用容器，python中的编码问题，super为啥需要两个参数，而3不需要参数，经典的闭包问题，NotImplemented和NotImplementedError的区别，多继承的mro问题，相对导入原理(__name__,如果看最新开源代码，基本都是相对导入)
- [ ] 掌握 Python 的内存机制、GIL 限制等，知道如何改变 Python 的行为，可以轻松写出高效的优质的 Python 代码，能够轻松分辨不同 Python 代码的效率并知道如何优化。
- [ ] 阅读 Python 的 C 实现，掌握 Python 中各种对象的本质，掌握是如何通过 C 实现面向对象的行为，对于常见的数据结构，掌握其实现细节。到这一步，需要将 Python 源码学习至少一遍，并对关键部分有较深层次的理解。
- [ ] 熟知 CPython 的具体实现，如若可能至少通读源码三遍以上
- [ ] 熟知每条 Python bytecode 如何被解释执行
- [ ] 熟知每条 Python 语句如何 compile 成 bytecode
- [ ] 熟知 Python 主要数据结构所采用的优化手段
- [ ] 熟知 JIT 以及哪些场合下 PyPy 会比 CPython 有较大性能提高、以及有什么代价

# Suggestions
- 如若可能，尽量避免 map/reduce/fitler，而用 list/generator/set comprehension，代码要清晰得多，GvR 如此说。xrange 和 range 的区别在 Python 3 中马上就要滚蛋了，所以如非必要，不要大量使用 xrange。
- 敢于在 CPython 中大量使用递归是对 CPython 实现的公然侮辱。Python 的多个稳定实现都没有 TCO，递归会让性能迅速下降。记住一点：Python 中函数调用非常昂贵，可读性、可维护性影响不大的情况下，能展开函数调用的时候尽量展开、递归能转化成循环的尽量转化。递归也不是人类自然的思考方式。
- 看书是对的，但不要把 Python 当作一门经典函数式语言对待，因为它不是。你当它是，它会很痛苦（“为毛要这样滥用我！？”），你也会很痛苦（“为毛你不这样实现 blah blah！？”）。SICP 是本好书，但不要因此而教条。要清楚的知道什么时候用函数式，什么时候用面向对象，什么时候用面向过程，什么时候用面向任务，什么时候用面向结果。在一棵树上吊死是大多数非理性死忠的表现。

# References
- [怎么样才算是精通 Python？xlzd, 罗伊, Rio的回答](https://www.zhihu.com/question/19794855)


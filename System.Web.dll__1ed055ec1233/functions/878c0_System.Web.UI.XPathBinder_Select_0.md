# System.Web.UI.XPathBinder::Select_0

- ea: `0x878c0`
- end: `0x87960`
- name: `System.Web.UI.XPathBinder::Select_0`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x80370`
- `0x878b0`

## callees

- `0x34f20`
- `0x34fa0`
- `0x878c0`

## string_xrefs

- `0x878d6`: `xPath`
- `0x878f1`: `XPathBinder_MustBeIXPathNavigable`
- `0x87938`: `XPathBinder_MustHaveXmlNodes`

## pseudocode

```c

```

## disassembly

```asm
0x878c0  ldarg.0
0x878c1  brtrue.s loc_878CE
0x878c3  ldstr    aContainer// "container"
0x878c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x878cd  throw
0x878ce  ldarg.1
0x878cf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x878d4  brfalse.s loc_878E1
0x878d6  ldstr    aXpath// "xPath"
0x878db  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x878e0  throw
0x878e1  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x878e6  stloc.0
0x878e7  ldarg.0
0x878e8  isinst   [System.Xml]System.Xml.XPath.IXPathNavigable
0x878ed  stloc.1
0x878ee  ldloc.1
0x878ef  brtrue.s loc_87915
0x878f1  ldstr    aXpathbinderMus// "XPathBinder_MustBeIXPathNavigable"
0x878f6  ldc.i4.1
0x878f7  newarr   [mscorlib]System.Object
0x878fc  dup
0x878fd  ldc.i4.0
0x878fe  ldarg.0
0x878ff  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x87904  callvirt instance string [mscorlib]System.Type::get_FullName()
0x87909  stelem.ref
0x8790a  call     string System.Web.SR::GetString(string name, object[] args)
0x8790f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x87914  throw
0x87915  ldloc.1
0x87916  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.IXPathNavigable::CreateNavigator()
0x8791b  stloc.2
0x8791c  ldloc.2
0x8791d  ldarg.1
0x8791e  ldarg.2
0x8791f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string, class [System.Xml]System.Xml.IXmlNamespaceResolver)
0x87924  stloc.3
0x87925  br.s     loc_87956
0x87927  ldloc.3
0x87928  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x8792d  isinst   [System.Xml]System.Xml.IHasXmlNode
0x87932  stloc.s  4
0x87934  ldloc.s  4
0x87936  brtrue.s loc_87948
0x87938  ldstr    aXpathbinderMus_0// "XPathBinder_MustHaveXmlNodes"
0x8793d  call     string System.Web.SR::GetString(string name)
0x87942  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x87947  throw
0x87948  ldloc.0
0x87949  ldloc.s  4
0x8794b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.IHasXmlNode::GetNode()
0x87950  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x87955  pop
0x87956  ldloc.3
0x87957  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x8795c  brtrue.s loc_87927
0x8795e  ldloc.0
0x8795f  ret
```

# System.Web.XmlSiteMapProvider::AddNodeInternal

- ea: `0x32ea0`
- end: `0x32fcb`
- name: `System.Web.XmlSiteMapProvider::AddNodeInternal`
- size: `299`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x32df0`
- `0x32fd0`
- `0x33300`

## callees

- `0x2c3c0`
- `0x2c670`
- `0x2cb00`
- `0x2cc80`
- `0x2e010`
- `0x2e050`
- `0x2e090`
- `0x2e0d0`
- `0x32ea0`
- `0x34f20`

## string_xrefs

- `0x32edb`: `XmlSiteMapProvider_Multiple_Nodes_With_Identical_Url`
- `0x32ef6`: `XmlSiteMapProvider_Multiple_Nodes_With_Identical_Url`
- `0x32f24`: `XmlSiteMapProvider_Multiple_Nodes_With_Identical_Key`
- `0x32f3f`: `XmlSiteMapProvider_Multiple_Nodes_With_Identical_Key`

## pseudocode

```c

```

## disassembly

```asm
0x32ea0  ldarg.0
0x32ea1  ldfld    object System.Web.SiteMapProvider::_lock
0x32ea6  stloc.0
0x32ea7  ldc.i4.0
0x32ea8  stloc.1
0x32ea9  ldloc.0
0x32eaa  ldloca.s 1
0x32eac  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x32eb1  ldarg.1
0x32eb2  callvirt instance string System.Web.SiteMapNode::get_Url()
0x32eb7  stloc.2
0x32eb8  ldarg.1
0x32eb9  callvirt instance string System.Web.SiteMapNode::get_Key()
0x32ebe  stloc.3
0x32ebf  ldc.i4.0
0x32ec0  stloc.s  4
0x32ec2  ldloc.2
0x32ec3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32ec8  brtrue.s loc_32F13
0x32eca  ldarg.0
0x32ecb  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_UrlTable()
0x32ed0  ldloc.2
0x32ed1  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x32ed6  brfalse.s loc_32F10
0x32ed8  ldarg.3
0x32ed9  brfalse.s loc_32EF6
0x32edb  ldstr    aXmlsitemapprov// "XmlSiteMapProvider_Multiple_Nodes_With_"...
0x32ee0  ldc.i4.1
0x32ee1  newarr   [mscorlib]System.Object
0x32ee6  dup
0x32ee7  ldc.i4.0
0x32ee8  ldloc.2
0x32ee9  stelem.ref
0x32eea  call     string System.Web.SR::GetString(string name, object[] args)
0x32eef  ldarg.3
0x32ef0  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x32ef5  throw
0x32ef6  ldstr    aXmlsitemapprov// "XmlSiteMapProvider_Multiple_Nodes_With_"...
0x32efb  ldc.i4.1
0x32efc  newarr   [mscorlib]System.Object
0x32f01  dup
0x32f02  ldc.i4.0
0x32f03  ldloc.2
0x32f04  stelem.ref
0x32f05  call     string System.Web.SR::GetString(string name, object[] args)
0x32f0a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x32f0f  throw
0x32f10  ldc.i4.1
0x32f11  stloc.s  4
0x32f13  ldarg.0
0x32f14  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_KeyTable()
0x32f19  ldloc.3
0x32f1a  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x32f1f  brfalse.s loc_32F59
0x32f21  ldarg.3
0x32f22  brfalse.s loc_32F3F
0x32f24  ldstr    aXmlsitemapprov_0// "XmlSiteMapProvider_Multiple_Nodes_With_"...
0x32f29  ldc.i4.1
0x32f2a  newarr   [mscorlib]System.Object
0x32f2f  dup
0x32f30  ldc.i4.0
0x32f31  ldloc.3
0x32f32  stelem.ref
0x32f33  call     string System.Web.SR::GetString(string name, object[] args)
0x32f38  ldarg.3
0x32f39  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x32f3e  throw
0x32f3f  ldstr    aXmlsitemapprov_0// "XmlSiteMapProvider_Multiple_Nodes_With_"...
0x32f44  ldc.i4.1
0x32f45  newarr   [mscorlib]System.Object
0x32f4a  dup
0x32f4b  ldc.i4.0
0x32f4c  ldloc.3
0x32f4d  stelem.ref
0x32f4e  call     string System.Web.SR::GetString(string name, object[] args)
0x32f53  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x32f58  throw
0x32f59  ldloc.s  4
0x32f5b  brfalse.s loc_32F6A
0x32f5d  ldarg.0
0x32f5e  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_UrlTable()
0x32f63  ldloc.2
0x32f64  ldarg.1
0x32f65  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x32f6a  ldarg.0
0x32f6b  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_KeyTable()
0x32f70  ldloc.3
0x32f71  ldarg.1
0x32f72  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x32f77  ldarg.2
0x32f78  brfalse.s loc_32FBE
0x32f7a  ldarg.0
0x32f7b  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ParentNodeTable()
0x32f80  ldarg.1
0x32f81  ldarg.2
0x32f82  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x32f87  ldarg.0
0x32f88  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ChildNodeCollectionTable()
0x32f8d  ldarg.2
0x32f8e  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x32f93  brtrue.s loc_32FA6
0x32f95  ldarg.0
0x32f96  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ChildNodeCollectionTable()
0x32f9b  ldarg.2
0x32f9c  newobj   instance void System.Web.SiteMapNodeCollection::.ctor()
0x32fa1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x32fa6  ldarg.0
0x32fa7  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ChildNodeCollectionTable()
0x32fac  ldarg.2
0x32fad  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x32fb2  castclass System.Web.SiteMapNodeCollection
0x32fb7  ldarg.1
0x32fb8  callvirt instance int32 System.Web.SiteMapNodeCollection::Add(class System.Web.SiteMapNode value)
0x32fbd  pop
0x32fbe  leave.s  loc_32FCA
0x32fc0  ldloc.1
0x32fc1  brfalse.s loc_32FC9
0x32fc3  ldloc.0
0x32fc4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x32fc9  endfinally
0x32fca  ret
```

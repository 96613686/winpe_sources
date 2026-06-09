# System.Web.XmlSiteMapProvider::RemoveNode

- ea: `0x33f30`
- end: `0x33fc2`
- name: `System.Web.XmlSiteMapProvider::RemoveNode`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x2c4d0`
- `0x2d010`
- `0x2d370`
- `0x2d500`
- `0x2e4a0`
- `0x33f30`
- `0x34f20`
- `0x34fa0`

## string_xrefs

- `0x33f55`: `XmlSiteMapProvider_cannot_remove_node`
- `0x33f9f`: `SiteMapProvider_cannot_remove_root_node`

## pseudocode

```c

```

## disassembly

```asm
0x33f30  ldarg.1
0x33f31  brtrue.s loc_33F3E
0x33f33  ldstr    aNode// "node"
0x33f38  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x33f3d  throw
0x33f3e  ldarg.1
0x33f3f  callvirt instance class System.Web.SiteMapProvider System.Web.SiteMapNode::get_Provider()
0x33f44  stloc.0
0x33f45  ldloc.0
0x33f46  ldarg.0
0x33f47  beq.s    loc_33F91
0x33f49  ldloc.0
0x33f4a  callvirt instance class System.Web.SiteMapProvider System.Web.SiteMapProvider::get_ParentProvider()
0x33f4f  stloc.1
0x33f50  br.s     loc_33F8D
0x33f52  ldloc.1
0x33f53  brtrue.s loc_33F86
0x33f55  ldstr    aXmlsitemapprov_18// "XmlSiteMapProvider_cannot_remove_node"
0x33f5a  ldc.i4.3
0x33f5b  newarr   [mscorlib]System.Object
0x33f60  dup
0x33f61  ldc.i4.0
0x33f62  ldarg.1
0x33f63  callvirt instance string [mscorlib]System.Object::ToString()
0x33f68  stelem.ref
0x33f69  dup
0x33f6a  ldc.i4.1
0x33f6b  ldarg.0
0x33f6c  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0x33f71  stelem.ref
0x33f72  dup
0x33f73  ldc.i4.2
0x33f74  ldloc.0
0x33f75  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0x33f7a  stelem.ref
0x33f7b  call     string System.Web.SR::GetString(string name, object[] args)
0x33f80  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x33f85  throw
0x33f86  ldloc.1
0x33f87  callvirt instance class System.Web.SiteMapProvider System.Web.SiteMapProvider::get_ParentProvider()
0x33f8c  stloc.1
0x33f8d  ldloc.1
0x33f8e  ldarg.0
0x33f8f  bne.un.s loc_33F52
0x33f91  ldarg.1
0x33f92  ldloc.0
0x33f93  callvirt instance class System.Web.SiteMapNode System.Web.SiteMapProvider::GetRootNodeCore()
0x33f98  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x33f9d  brfalse.s loc_33FAF
0x33f9f  ldstr    aSitemapprovide_2// "SiteMapProvider_cannot_remove_root_node"
0x33fa4  call     string System.Web.SR::GetString(string name)
0x33fa9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x33fae  throw
0x33faf  ldloc.0
0x33fb0  ldarg.0
0x33fb1  beq.s    loc_33FBA
0x33fb3  ldloc.0
0x33fb4  ldarg.1
0x33fb5  callvirt instance void System.Web.SiteMapProvider::RemoveNode(class System.Web.SiteMapNode node)
0x33fba  ldarg.0
0x33fbb  ldarg.1
0x33fbc  call     instance void System.Web.StaticSiteMapProvider::RemoveNode(class System.Web.SiteMapNode node)
0x33fc1  ret
```

# System.Web.XmlSiteMapProvider::GetNodeFromProvider

- ea: `0x33880`
- end: `0x33983`
- name: `System.Web.XmlSiteMapProvider::GetNodeFromProvider`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x32fd0`
- `0x33300`

## callees

- `0x2d020`
- `0x2d370`
- `0x2e240`
- `0x30f70`
- `0x31550`
- `0x32cf0`
- `0x33880`
- `0x33e00`
- `0x34f20`

## string_xrefs

- `0x33917`: `XmlSiteMapProvider_FileName_already_in_use`
- `0x33947`: `XmlSiteMapProvider_invalid_GetRootNodeCore`

## pseudocode

```c

```

## disassembly

```asm
0x33880  ldarg.0
0x33881  ldarg.1
0x33882  call     instance class System.Web.SiteMapProvider System.Web.XmlSiteMapProvider::GetProviderFromName(string providerName)
0x33887  stloc.0
0x33888  ldnull
0x33889  stloc.1
0x3388a  ldloc.0
0x3388b  isinst   System.Web.XmlSiteMapProvider
0x33890  brfalse  loc_3393D
0x33895  ldloc.0
0x33896  castclass System.Web.XmlSiteMapProvider
0x3389b  stloc.2
0x3389c  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x338a1  stloc.3
0x338a2  ldarg.0
0x338a3  ldfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x338a8  brfalse.s loc_338EB
0x338aa  ldarg.0
0x338ab  ldfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x338b0  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x338b5  stloc.s  4
0x338b7  br.s     loc_338CB
0x338b9  ldloc.s  4
0x338bb  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x338c0  stloc.s  5
0x338c2  ldloc.3
0x338c3  ldloc.s  5
0x338c5  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x338ca  pop
0x338cb  ldloc.s  4
0x338cd  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x338d2  brtrue.s loc_338B9
0x338d4  leave.s  loc_338EB
0x338d6  ldloc.s  4
0x338d8  isinst   [mscorlib]System.IDisposable
0x338dd  stloc.s  6
0x338df  ldloc.s  6
0x338e1  brfalse.s loc_338EA
0x338e3  ldloc.s  6
0x338e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x338ea  endfinally
0x338eb  ldloc.2
0x338ec  callvirt instance class System.Web.SiteMapNode System.Web.StaticSiteMapProvider::BuildSiteMap()
0x338f1  pop
0x338f2  ldloc.3
0x338f3  ldarg.0
0x338f4  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x338f9  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x338fe  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x33903  pop
0x33904  ldloc.3
0x33905  ldloc.2
0x33906  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x3390b  call     string System.Web.VirtualPath::GetVirtualPathString(class System.Web.VirtualPath virtualPath)
0x33910  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0x33915  brfalse.s loc_33936
0x33917  ldstr    aXmlsitemapprov_11// "XmlSiteMapProvider_FileName_already_in_"...
0x3391c  ldc.i4.1
0x3391d  newarr   [mscorlib]System.Object
0x33922  dup
0x33923  ldc.i4.0
0x33924  ldloc.2
0x33925  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x3392a  stelem.ref
0x3392b  call     string System.Web.SR::GetString(string name, object[] args)
0x33930  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x33935  throw
0x33936  ldloc.2
0x33937  ldloc.3
0x33938  stfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x3393d  ldloc.0
0x3393e  callvirt instance class System.Web.SiteMapNode System.Web.SiteMapProvider::GetRootNodeCore()
0x33943  stloc.1
0x33944  ldloc.1
0x33945  brtrue.s loc_33966
0x33947  ldstr    aXmlsitemapprov_12// "XmlSiteMapProvider_invalid_GetRootNodeC"...
0x3394c  ldc.i4.1
0x3394d  newarr   [mscorlib]System.Object
0x33952  dup
0x33953  ldc.i4.0
0x33954  ldloc.0
0x33955  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0x3395a  stelem.ref
0x3395b  call     string System.Web.SR::GetString(string name, object[] args)
0x33960  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x33965  throw
0x33966  ldarg.0
0x33967  call     instance class [mscorlib]System.Collections.Hashtable System.Web.XmlSiteMapProvider::get_ChildProviderTable()
0x3396c  ldloc.0
0x3396d  ldloc.1
0x3396e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x33973  ldarg.0
0x33974  ldnull
0x33975  stfld    class [mscorlib]System.Collections.ArrayList System.Web.XmlSiteMapProvider::_childProviderList
0x3397a  ldloc.0
0x3397b  ldarg.0
0x3397c  callvirt instance void System.Web.SiteMapProvider::set_ParentProvider(class System.Web.SiteMapProvider value)
0x33981  ldloc.1
0x33982  ret
```

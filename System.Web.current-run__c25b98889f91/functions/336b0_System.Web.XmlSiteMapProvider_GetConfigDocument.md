# System.Web.XmlSiteMapProvider::GetConfigDocument

- ea: `0x336b0`
- end: `0x33878`
- name: `System.Web.XmlSiteMapProvider::GetConfigDocument`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x33020`

## callees

- `0xc060`
- `0xd640`
- `0x243c0`
- `0x2d010`
- `0x2d040`
- `0x30f70`
- `0x310e0`
- `0x31100`
- `0x31330`
- `0x31460`
- `0x33290`
- `0x336b0`
- `0x34f20`
- `0x34fa0`
- `0x162260`

## string_xrefs

- `0x336c7`: `XmlSiteMapProvider_Not_Initialized`
- `0x336e5`: `XmlSiteMapProvider_missing_siteMapFile`
- `0x3371b`: `XmlSiteMapProvider_Invalid_Extension`
- `0x33796`: `XmlSiteMapProvider_FileName_already_in_use`

## pseudocode

```c

```

## disassembly

```asm
0x336b0  ldarg.0
0x336b1  ldfld    class [System.Xml]System.Xml.XmlDocument System.Web.XmlSiteMapProvider::_document
0x336b6  brfalse.s loc_336BF
0x336b8  ldarg.0
0x336b9  ldfld    class [System.Xml]System.Xml.XmlDocument System.Web.XmlSiteMapProvider::_document
0x336be  ret
0x336bf  ldarg.0
0x336c0  ldfld    bool System.Web.XmlSiteMapProvider::_initialized
0x336c5  brtrue.s loc_336D7
0x336c7  ldstr    aXmlsitemapprov_8// "XmlSiteMapProvider_Not_Initialized"
0x336cc  call     string System.Web.SR::GetString(string name)
0x336d1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x336d6  throw
0x336d7  ldarg.0
0x336d8  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x336dd  ldnull
0x336de  call     bool System.Web.VirtualPath::op_Equality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x336e3  brfalse.s loc_33703
0x336e5  ldstr    aXmlsitemapprov_9// "XmlSiteMapProvider_missing_siteMapFile"
0x336ea  ldc.i4.1
0x336eb  newarr   [mscorlib]System.Object
0x336f0  dup
0x336f1  ldc.i4.0
0x336f2  ldstr    aSitemapfile// "siteMapFile"
0x336f7  stelem.ref
0x336f8  call     string System.Web.SR::GetString(string name, object[] args)
0x336fd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x33702  throw
0x33703  ldarg.0
0x33704  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x33709  callvirt instance string System.Web.VirtualPath::get_Extension()
0x3370e  ldstr    aSitemap_0// ".sitemap"
0x33713  ldc.i4.5
0x33714  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33719  brtrue.s loc_3373A
0x3371b  ldstr    aXmlsitemapprov_10// "XmlSiteMapProvider_Invalid_Extension"
0x33720  ldc.i4.1
0x33721  newarr   [mscorlib]System.Object
0x33726  dup
0x33727  ldc.i4.0
0x33728  ldarg.0
0x33729  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x3372e  stelem.ref
0x3372f  call     string System.Web.SR::GetString(string name, object[] args)
0x33734  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x33739  throw
0x3373a  ldarg.0
0x3373b  ldarg.0
0x3373c  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x33741  callvirt instance class System.Web.VirtualPath System.Web.VirtualPath::CombineWithAppRoot()
0x33746  stfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x3374b  ldarg.0
0x3374c  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x33751  callvirt instance void System.Web.VirtualPath::FailIfNotWithinAppRoot()
0x33756  ldarg.0
0x33757  call     instance void System.Web.XmlSiteMapProvider::CheckSiteMapFileExists()
0x3375c  ldarg.0
0x3375d  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x33762  stfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x33767  ldarg.0
0x33768  callvirt instance class System.Web.SiteMapProvider System.Web.SiteMapProvider::get_ParentProvider()
0x3376d  isinst   System.Web.XmlSiteMapProvider
0x33772  stloc.0
0x33773  ldloc.0
0x33774  brfalse.s loc_337F2
0x33776  ldloc.0
0x33777  ldfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x3377c  brfalse.s loc_337F2
0x3377e  ldloc.0
0x3377f  ldfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x33784  ldarg.0
0x33785  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x3378a  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x3378f  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0x33794  brfalse.s loc_337B5
0x33796  ldstr    aXmlsitemapprov_11// "XmlSiteMapProvider_FileName_already_in_"...
0x3379b  ldc.i4.1
0x3379c  newarr   [mscorlib]System.Object
0x337a1  dup
0x337a2  ldc.i4.0
0x337a3  ldarg.0
0x337a4  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x337a9  stelem.ref
0x337aa  call     string System.Web.SR::GetString(string name, object[] args)
0x337af  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x337b4  throw
0x337b5  ldloc.0
0x337b6  ldfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x337bb  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x337c0  stloc.1
0x337c1  br.s     loc_337D7
0x337c3  ldloc.1
0x337c4  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x337c9  stloc.2
0x337ca  ldarg.0
0x337cb  ldfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x337d0  ldloc.2
0x337d1  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x337d6  pop
0x337d7  ldloc.1
0x337d8  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x337dd  brtrue.s loc_337C3
0x337df  leave.s  loc_337F2
0x337e1  ldloc.1
0x337e2  isinst   [mscorlib]System.IDisposable
0x337e7  stloc.3
0x337e8  ldloc.3
0x337e9  brfalse.s loc_337F1
0x337eb  ldloc.3
0x337ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x337f1  endfinally
0x337f2  ldarg.0
0x337f3  ldfld    class [System]System.Collections.Specialized.StringCollection System.Web.XmlSiteMapProvider::_parentSiteMapFileCollection
0x337f8  ldarg.0
0x337f9  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x337fe  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x33803  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x33808  pop
0x33809  ldarg.0
0x3380a  ldarg.0
0x3380b  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x33810  call     string System.Web.Hosting.HostingEnvironment::MapPathInternal(class System.Web.VirtualPath virtualPath)
0x33815  stfld    string System.Web.XmlSiteMapProvider::_filename
0x3381a  ldarg.0
0x3381b  ldfld    string System.Web.XmlSiteMapProvider::_filename
0x33820  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33825  brtrue.s loc_33866
0x33827  ldarg.0
0x33828  ldarg.0
0x33829  ldftn    instance void System.Web.XmlSiteMapProvider::OnConfigFileChange(object sender, class System.Web.FileChangeEvent e)
0x3382f  newobj   instance void System.Web.FileChangeEventHandler::.ctor(object object, native int method)
0x33834  stfld    class System.Web.FileChangeEventHandler System.Web.XmlSiteMapProvider::_handler
0x33839  call     class System.Web.FileChangesMonitor System.Web.HttpRuntime::get_FileChangesMonitor()
0x3383e  ldarg.0
0x3383f  ldfld    string System.Web.XmlSiteMapProvider::_filename
0x33844  ldarg.0
0x33845  ldfld    class System.Web.FileChangeEventHandler System.Web.XmlSiteMapProvider::_handler
0x3384a  callvirt instance valuetype [mscorlib]System.DateTime System.Web.FileChangesMonitor::StartMonitoringFile(string alias, class System.Web.FileChangeEventHandler callback)
0x3384f  pop
0x33850  ldarg.0
0x33851  ldarg.0
0x33852  ldfld    string System.Web.XmlSiteMapProvider::_filename
0x33857  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x3385c  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x33861  call     instance void System.Web.SiteMapProvider::set_ResourceKey(string value)
0x33866  ldarg.0
0x33867  newobj   instance void [System]System.Configuration.ConfigXmlDocument::.ctor()
0x3386c  stfld    class [System.Xml]System.Xml.XmlDocument System.Web.XmlSiteMapProvider::_document
0x33871  ldarg.0
0x33872  ldfld    class [System.Xml]System.Xml.XmlDocument System.Web.XmlSiteMapProvider::_document
0x33877  ret
```

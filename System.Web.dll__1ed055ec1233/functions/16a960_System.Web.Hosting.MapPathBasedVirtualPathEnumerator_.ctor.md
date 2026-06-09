# System.Web.Hosting.MapPathBasedVirtualPathEnumerator::.ctor

- ea: `0x16a960`
- end: `0x16aacd`
- name: `System.Web.Hosting.MapPathBasedVirtualPathEnumerator::.ctor`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x16a930`

## callees

- `0x30f70`
- `0x31160`
- `0x311e0`
- `0x31390`
- `0x34fa0`
- `0x546c0`
- `0x54b80`
- `0x14b750`
- `0x14b780`
- `0x156fe0`
- `0x157080`
- `0x16a870`
- `0x16a960`

## string_xrefs

- `0x16a978`: `virtualPath`
- `0x16a96e`: `Invalid_app_VirtualPath`

## pseudocode

```c

```

## disassembly

```asm
0x16a960  ldarg.0
0x16a961  call     instance void [mscorlib]System.MarshalByRefObject::.ctor()
0x16a966  ldarg.1
0x16a967  callvirt instance bool System.Web.VirtualPath::get_IsRelative()
0x16a96c  brfalse.s loc_16A983
0x16a96e  ldstr    aInvalidAppVirt// "Invalid_app_VirtualPath"
0x16a973  call     string System.Web.SR::GetString(string name)
0x16a978  ldstr    aVirtualpath_0// "virtualPath"
0x16a97d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x16a982  throw
0x16a983  ldarg.0
0x16a984  ldarg.1
0x16a985  stfld    class System.Web.VirtualPath System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPath
0x16a98a  ldarg.0
0x16a98b  ldarg.2
0x16a98c  stfld    valuetype System.Web.Hosting.RequestedEntryType System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_requestedEntryType
0x16a991  call     bool System.Web.Configuration.ServerConfig::get_UseServerConfig()
0x16a996  brtrue.s loc_16A9A9
0x16a998  ldarg.0
0x16a999  ldfld    class System.Web.VirtualPath System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPath
0x16a99e  callvirt instance string System.Web.VirtualPath::MapPathInternal()
0x16a9a3  stloc.0
0x16a9a4  br       loc_16AAB9
0x16a9a9  call     class System.Web.Configuration.IServerConfig System.Web.Configuration.ServerConfig::GetInstance()
0x16a9ae  stloc.1
0x16a9af  ldarg.0
0x16a9b0  ldloc.1
0x16a9b1  isinst   System.Web.Configuration.IServerConfig2
0x16a9b6  stfld    class System.Web.Configuration.IServerConfig2 System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_serverConfig2
0x16a9bb  ldloc.1
0x16a9bc  ldnull
0x16a9bd  ldarg.0
0x16a9be  ldfld    class System.Web.VirtualPath System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPath
0x16a9c3  callvirt instance string System.Web.Configuration.IServerConfig::MapPath(class System.Web.Hosting.IApplicationHost appHost, class System.Web.VirtualPath path)
0x16a9c8  stloc.0
0x16a9c9  ldarg.0
0x16a9ca  ldfld    valuetype System.Web.Hosting.RequestedEntryType System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_requestedEntryType
0x16a9cf  brfalse  loc_16AAB9
0x16a9d4  ldarg.0
0x16a9d5  ldfld    class System.Web.Configuration.IServerConfig2 System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_serverConfig2
0x16a9da  brtrue.s loc_16AA29
0x16a9dc  ldloc.1
0x16a9dd  ldarg.0
0x16a9de  ldfld    class System.Web.VirtualPath System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPath
0x16a9e3  ldc.i4.0
0x16a9e4  callvirt instance string[] System.Web.Configuration.IServerConfig::GetVirtualSubdirs(class System.Web.VirtualPath path, bool inApp)
0x16a9e9  stloc.3
0x16a9ea  ldloc.3
0x16a9eb  brfalse.s loc_16AA29
0x16a9ed  ldarg.0
0x16a9ee  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x16a9f3  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x16a9f8  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_exclude
0x16a9fd  ldloc.3
0x16a9fe  stloc.s  4
0x16aa00  ldc.i4.0
0x16aa01  stloc.s  5
0x16aa03  br.s     loc_16AA21
0x16aa05  ldloc.s  4
0x16aa07  ldloc.s  5
0x16aa09  ldelem.ref
0x16aa0a  stloc.s  6
0x16aa0c  ldarg.0
0x16aa0d  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_exclude
0x16aa12  ldloc.s  6
0x16aa14  ldloc.s  6
0x16aa16  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x16aa1b  ldloc.s  5
0x16aa1d  ldc.i4.1
0x16aa1e  add
0x16aa1f  stloc.s  5
0x16aa21  ldloc.s  5
0x16aa23  ldloc.s  4
0x16aa25  ldlen
0x16aa26  conv.i4
0x16aa27  blt.s    loc_16AA05
0x16aa29  ldloc.1
0x16aa2a  ldarg.0
0x16aa2b  ldfld    class System.Web.VirtualPath System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPath
0x16aa30  ldc.i4.1
0x16aa31  callvirt instance string[] System.Web.Configuration.IServerConfig::GetVirtualSubdirs(class System.Web.VirtualPath path, bool inApp)
0x16aa36  stloc.2
0x16aa37  ldloc.2
0x16aa38  brfalse.s loc_16AAB9
0x16aa3a  ldarg.0
0x16aa3b  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x16aa40  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x16aa45  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPaths
0x16aa4a  ldloc.2
0x16aa4b  stloc.s  7
0x16aa4d  ldc.i4.0
0x16aa4e  stloc.s  8
0x16aa50  br.s     loc_16AA9B
0x16aa52  ldloc.s  7
0x16aa54  ldloc.s  8
0x16aa56  ldelem.ref
0x16aa57  stloc.s  9
0x16aa59  ldarg.0
0x16aa5a  ldfld    class System.Web.VirtualPath System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPath
0x16aa5f  ldloc.s  9
0x16aa61  callvirt instance class System.Web.VirtualPath System.Web.VirtualPath::SimpleCombineWithDir(string directoryName)
0x16aa66  stloc.s  0xA
0x16aa68  ldloc.1
0x16aa69  ldnull
0x16aa6a  ldloc.s  0xA
0x16aa6c  callvirt instance string System.Web.Configuration.IServerConfig::MapPath(class System.Web.Hosting.IApplicationHost appHost, class System.Web.VirtualPath path)
0x16aa71  stloc.s  0xB
0x16aa73  ldloc.s  0xB
0x16aa75  call     bool System.Web.Util.FileUtil::DirectoryExists(string dirname)
0x16aa7a  brfalse.s loc_16AA95
0x16aa7c  ldarg.0
0x16aa7d  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPaths
0x16aa82  ldloc.s  9
0x16aa84  ldloc.s  0xA
0x16aa86  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x16aa8b  newobj   instance void System.Web.Hosting.MapPathBasedVirtualDirectory::.ctor(string virtualPath)
0x16aa90  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x16aa95  ldloc.s  8
0x16aa97  ldc.i4.1
0x16aa98  add
0x16aa99  stloc.s  8
0x16aa9b  ldloc.s  8
0x16aa9d  ldloc.s  7
0x16aa9f  ldlen
0x16aaa0  conv.i4
0x16aaa1  blt.s    loc_16AA52
0x16aaa3  ldarg.0
0x16aaa4  ldarg.0
0x16aaa5  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualPaths
0x16aaaa  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x16aaaf  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x16aab4  stfld    class [mscorlib]System.Collections.IEnumerator System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_virtualEnumerator
0x16aab9  ldarg.0
0x16aaba  ldloc.0
0x16aabb  call     class System.Web.Util.FileEnumerator System.Web.Util.FileEnumerator::Create(string path)
0x16aac0  stfld    class [mscorlib]System.Collections.IEnumerator System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_fileEnumerator
0x16aac5  ldarg.0
0x16aac6  ldc.i4.0
0x16aac7  stfld    bool System.Web.Hosting.MapPathBasedVirtualPathEnumerator::_useFileEnumerator
0x16aacc  ret
```

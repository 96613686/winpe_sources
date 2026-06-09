# System.Web.UI.WebControls.AccessDataSource::GetPhysicalDataFilePath

- ea: `0x8e3b0`
- end: `0x8e442`
- name: `System.Web.UI.WebControls.AccessDataSource::GetPhysicalDataFilePath`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x8e260`

## callees

- `0x16330`
- `0x18990`
- `0x1d5a0`
- `0x24040`
- `0x24170`
- `0x241d0`
- `0x34f20`
- `0x596b0`
- `0x5ef80`
- `0x5f060`
- `0x5f1b0`
- `0x5fa30`
- `0x8e200`
- `0x8e3b0`

## string_xrefs

- `0x8e3d1`: `AccessDataSource_DesignTimeRelativePathsNotSupported`
- `0x8e418`: `AccessDataSource_NoPathDiscoveryPermission`

## pseudocode

```c

```

## disassembly

```asm
0x8e3b0  ldarg.0
0x8e3b1  call     instance string System.Web.UI.WebControls.AccessDataSource::get_DataFile()
0x8e3b6  stloc.0
0x8e3b7  ldloc.0
0x8e3b8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8e3bd  brtrue.s loc_8E3C1
0x8e3bf  ldnull
0x8e3c0  ret
0x8e3c1  ldloc.0
0x8e3c2  call     bool System.Web.Util.UrlPath::IsAbsolutePhysicalPath(string path)
0x8e3c7  brtrue.s loc_8E409
0x8e3c9  ldarg.0
0x8e3ca  call     instance bool System.Web.UI.Control::get_DesignMode()
0x8e3cf  brfalse.s loc_8E3F0
0x8e3d1  ldstr    aAccessdatasour_2// "AccessDataSource_DesignTimeRelativePath"...
0x8e3d6  ldc.i4.1
0x8e3d7  newarr   [mscorlib]System.Object
0x8e3dc  dup
0x8e3dd  ldc.i4.0
0x8e3de  ldarg.0
0x8e3df  callvirt instance string System.Web.UI.Control::get_ID()
0x8e3e4  stelem.ref
0x8e3e5  call     string System.Web.SR::GetString(string name, object[] args)
0x8e3ea  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x8e3ef  throw
0x8e3f0  ldarg.0
0x8e3f1  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x8e3f6  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x8e3fb  ldloc.0
0x8e3fc  ldarg.0
0x8e3fd  call     instance string System.Web.UI.Control::get_AppRelativeTemplateSourceDirectory()
0x8e402  ldc.i4.1
0x8e403  callvirt instance string System.Web.HttpRequest::MapPath(string virtualPath, string baseVirtualDir, bool allowCrossAppMapping)
0x8e408  stloc.0
0x8e409  ldloc.0
0x8e40a  ldc.i4.1
0x8e40b  call     void System.Web.HttpRuntime::CheckFilePermission(string path, bool writePermissions)
0x8e410  ldloc.0
0x8e411  call     bool System.Web.HttpRuntime::HasPathDiscoveryPermission(string path)
0x8e416  brtrue.s loc_8E440
0x8e418  ldstr    aAccessdatasour_3// "AccessDataSource_NoPathDiscoveryPermiss"...
0x8e41d  ldc.i4.2
0x8e41e  newarr   [mscorlib]System.Object
0x8e423  dup
0x8e424  ldc.i4.0
0x8e425  ldloc.0
0x8e426  call     string System.Web.HttpRuntime::GetSafePath(string path)
0x8e42b  stelem.ref
0x8e42c  dup
0x8e42d  ldc.i4.1
0x8e42e  ldarg.0
0x8e42f  callvirt instance string System.Web.UI.Control::get_ID()
0x8e434  stelem.ref
0x8e435  call     string System.Web.SR::GetString(string name, object[] args)
0x8e43a  newobj   instance void System.Web.HttpException::.ctor(string message)
0x8e43f  throw
0x8e440  ldloc.0
0x8e441  ret
```

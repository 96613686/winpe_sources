# System.Web.UI.WebControls.XmlDataSource::GetReader

- ea: `0xee9a0`
- end: `0xeea73`
- name: `System.Web.UI.WebControls.XmlDataSource::GetReader`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0xeeba0`

## callees

- `0x240e0`
- `0x31470`
- `0x34f20`
- `0x56bd0`
- `0x56c00`
- `0x56c30`
- `0x5f060`
- `0x5f1b0`
- `0x60850`
- `0x60930`
- `0xee9a0`

## string_xrefs

- `0xee9d2`: `XmlDataSource_NoWebPermission`
- `0xeea20`: `XmlDataSource_DesignTimeRelativePathsNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0xee9a0  ldarg.1
0xee9a1  callvirt instance int32 [mscorlib]System.String::get_Length()
0xee9a6  brfalse  loc_EEA52
0xee9ab  ldarg.1
0xee9ac  ldc.i4.1
0xee9ad  ldloca.s 0
0xee9af  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0xee9b4  stloc.1
0xee9b5  ldloc.1
0xee9b6  brfalse.s loc_EEA04
0xee9b8  ldloc.0
0xee9b9  callvirt instance string [System]System.Uri::get_Scheme()
0xee9be  ldsfld   string [System]System.Uri::UriSchemeHttp
0xee9c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xee9c8  brfalse.s loc_EEA04
0xee9ca  ldloc.0
0xee9cb  call     bool System.Web.HttpRuntime::HasWebPermission(class [System]System.Uri uri)
0xee9d0  brtrue.s loc_EE9FA
0xee9d2  ldstr    aXmldatasourceN_0// "XmlDataSource_NoWebPermission"
0xee9d7  ldc.i4.2
0xee9d8  newarr   [mscorlib]System.Object
0xee9dd  dup
0xee9de  ldc.i4.0
0xee9df  ldloc.0
0xee9e0  callvirt instance string [System]System.Uri::get_PathAndQuery()
0xee9e5  stelem.ref
0xee9e6  dup
0xee9e7  ldc.i4.1
0xee9e8  ldarg.0
0xee9e9  callvirt instance string System.Web.UI.Control::get_ID()
0xee9ee  stelem.ref
0xee9ef  call     string System.Web.SR::GetString(string name, object[] args)
0xee9f4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xee9f9  throw
0xee9fa  ldarg.3
0xee9fb  ldnull
0xee9fc  stind.ref
0xee9fd  ldarg.1
0xee9fe  call     class [System.Xml]System.Xml.XmlReader System.Web.Util.XmlUtils::CreateXmlReader(string filepath)
0xeea03  ret
0xeea04  ldarg.0
0xeea05  ldarg.1
0xeea06  ldloca.s 2
0xeea08  ldloca.s 3
0xeea0a  call     instance void System.Web.UI.Control::ResolvePhysicalOrVirtualPath(string path, [out] class System.Web.VirtualPath& virtualPath, [out] string& physicalPath)
0xeea0f  ldloc.2
0xeea10  ldnull
0xeea11  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0xeea16  brfalse.s loc_EEA3F
0xeea18  ldarg.0
0xeea19  call     instance bool System.Web.UI.Control::get_DesignMode()
0xeea1e  brfalse.s loc_EEA3F
0xeea20  ldstr    aXmldatasourceD// "XmlDataSource_DesignTimeRelativePathsNo"...
0xeea25  ldc.i4.1
0xeea26  newarr   [mscorlib]System.Object
0xeea2b  dup
0xeea2c  ldc.i4.0
0xeea2d  ldarg.0
0xeea2e  callvirt instance string System.Web.UI.Control::get_ID()
0xeea33  stelem.ref
0xeea34  call     string System.Web.SR::GetString(string name, object[] args)
0xeea39  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xeea3e  throw
0xeea3f  ldarg.0
0xeea40  ldloc.2
0xeea41  ldloc.3
0xeea42  ldarg.3
0xeea43  call     instance class [mscorlib]System.IO.Stream System.Web.UI.Control::OpenFileAndGetDependency(class System.Web.VirtualPath virtualPath, string physicalPath, [out] class System.Web.Caching.CacheDependency& dependency)
0xeea48  stloc.s  4
0xeea4a  ldloc.s  4
0xeea4c  call     class [System.Xml]System.Xml.XmlReader System.Web.Util.XmlUtils::CreateXmlReader(class [mscorlib]System.IO.Stream datastream)
0xeea51  ret
0xeea52  ldarg.3
0xeea53  ldnull
0xeea54  stind.ref
0xeea55  ldarg.2
0xeea56  callvirt instance string [mscorlib]System.String::Trim()
0xeea5b  starg.s  2
0xeea5d  ldarg.2
0xeea5e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xeea63  brtrue.s loc_EEA67
0xeea65  ldnull
0xeea66  ret
0xeea67  ldarg.2
0xeea68  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xeea6d  call     class [System.Xml]System.Xml.XmlReader System.Web.Util.XmlUtils::CreateXmlReader(class [mscorlib]System.IO.TextReader reader)
0xeea72  ret
```

# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeExportHelper::GetNextManifestName

- ea: `0xa590`
- end: `0xa604`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeExportHelper::GetNextManifestName`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9f50`

## callees

- `0xa590`

## string_xrefs

- `0xa5c5`: `manifest*.xml`
- `0xa5d0`: `manifest.xml`
- `0xa5e3`: `manifest{0}.xml`

## pseudocode

```c

```

## disassembly

```asm
0xa590  ldc.i4   0x38797077
0xa595  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xa59a  ldarg.0
0xa59b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa5a0  ldc.i4.0
0xa5a1  ceq
0xa5a3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::ShipAssertTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, bool)
0xa5a8  ldarg.0
0xa5a9  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0xa5ae  stloc.0
0xa5af  ldc.i4   0x38797078
0xa5b4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xa5b9  ldloc.0
0xa5ba  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0xa5bf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::ShipAssertTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, bool)
0xa5c4  ldloc.0
0xa5c5  ldstr    aManifestXml// "manifest*.xml"
0xa5ca  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0xa5cf  stloc.1
0xa5d0  ldstr    aManifestXml_0// "manifest.xml"
0xa5d5  stloc.2
0xa5d6  ldloc.1
0xa5d7  ldlen
0xa5d8  conv.i4
0xa5d9  stloc.3
0xa5da  ldloc.3
0xa5db  ldc.i4.0
0xa5dc  ble.s    loc_A602
0xa5de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa5e3  ldstr    aManifest0Xml// "manifest{0}.xml"
0xa5e8  ldc.i4.1
0xa5e9  newarr   [mscorlib]System.Object
0xa5ee  stloc.s  4
0xa5f0  ldloc.s  4
0xa5f2  ldc.i4.0
0xa5f3  ldloc.3
0xa5f4  box      [mscorlib]System.Int32
0xa5f9  stelem.ref
0xa5fa  ldloc.s  4
0xa5fc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa601  stloc.2
0xa602  ldloc.2
0xa603  ret
```

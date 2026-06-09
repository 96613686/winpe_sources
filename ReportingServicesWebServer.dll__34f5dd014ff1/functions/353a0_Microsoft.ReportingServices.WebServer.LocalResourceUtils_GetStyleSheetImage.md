# Microsoft.ReportingServices.WebServer.LocalResourceUtils::GetStyleSheetImage

- ea: `0x353a0`
- end: `0x3542a`
- name: `Microsoft.ReportingServices.WebServer.LocalResourceUtils::GetStyleSheetImage`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x24480`
- `0x32190`

## callees

- `0x2de80`
- `0x353a0`

## string_xrefs

- `0x353df`: `Microsoft.ReportingServices.WebServer.`

## pseudocode

```c

```

## disassembly

```asm
0x353a0  ldarg.0
0x353a1  call     string Microsoft.ReportingServices.WebServer.Global::get_StylesFolder()
0x353a6  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x353ab  call     unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ResourceLoader::GetStyleSheetImage(string, string, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace)
0x353b0  stloc.0
0x353b1  ldloc.0
0x353b2  brfalse.s loc_353B6
0x353b4  ldloc.0
0x353b5  ret
0x353b6  ldarg.0
0x353b7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x353bc  brtrue.s loc_35417
0x353be  ldarg.0
0x353bf  ldstr    aToolbarJpg// "toolbar.jpg"
0x353c4  ldc.i4.4
0x353c5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x353ca  brtrue.s loc_353DA
0x353cc  ldarg.0
0x353cd  ldstr    aDocmapHeaderJp// "docmap_header.jpg"
0x353d2  ldc.i4.4
0x353d3  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x353d8  brfalse.s loc_35417
0x353da  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x353df  ldstr    aMicrosoftRepor_129// "Microsoft.ReportingServices.WebServer."
0x353e4  ldarg.0
0x353e5  call     string [mscorlib]System.String::Concat(string, string)
0x353ea  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x353ef  stloc.1
0x353f0  ldloc.1
0x353f1  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x353f6  conv.ovf.i
0x353f7  newarr   [mscorlib]System.Byte
0x353fc  stloc.0
0x353fd  ldloc.1
0x353fe  ldloc.0
0x353ff  ldc.i4.0
0x35400  ldloc.0
0x35401  ldlen
0x35402  conv.i4
0x35403  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x35408  pop
0x35409  ldloc.0
0x3540a  stloc.2
0x3540b  leave.s  loc_35428
0x3540d  ldloc.1
0x3540e  brfalse.s loc_35416
0x35410  ldloc.1
0x35411  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35416  endfinally
0x35417  ldarg.0
0x35418  brfalse.s loc_3541D
0x3541a  ldarg.0
0x3541b  br.s     loc_35422
0x3541d  ldstr    aNull_1// "null"
0x35422  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalResourceNotFoundException::.ctor(string)
0x35427  throw
0x35428  ldloc.2
0x35429  ret
```

# Microsoft.ReportingServices.WebServer.LocalResourceUtils::GetStyleSheet

- ea: `0x35350`
- end: `0x3539b`
- name: `Microsoft.ReportingServices.WebServer.LocalResourceUtils::GetStyleSheet`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x24480`
- `0x32170`

## callees

- `0x2de80`
- `0x35350`

## string_xrefs

- `0x35369`: `Microsoft.ReportingServices.WebServer.HtmlViewer.css`

## pseudocode

```c

```

## disassembly

```asm
0x35350  ldarg.0
0x35351  call     string Microsoft.ReportingServices.WebServer.Global::get_StylesFolder()
0x35356  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x3535b  call     unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ResourceLoader::GetStyleSheet(string, string, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace)
0x35360  stloc.0
0x35361  ldloc.0
0x35362  brtrue.s loc_35399
0x35364  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x35369  ldstr    aMicrosoftRepor_139// "Microsoft.ReportingServices.WebServer.H"...
0x3536e  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x35373  stloc.1
0x35374  ldloc.1
0x35375  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x3537a  conv.ovf.i
0x3537b  newarr   [mscorlib]System.Byte
0x35380  stloc.0
0x35381  ldloc.1
0x35382  ldloc.0
0x35383  ldc.i4.0
0x35384  ldloc.0
0x35385  ldlen
0x35386  conv.i4
0x35387  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x3538c  pop
0x3538d  leave.s  loc_35399
0x3538f  ldloc.1
0x35390  brfalse.s loc_35398
0x35392  ldloc.1
0x35393  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35398  endfinally
0x35399  ldloc.0
0x3539a  ret
```

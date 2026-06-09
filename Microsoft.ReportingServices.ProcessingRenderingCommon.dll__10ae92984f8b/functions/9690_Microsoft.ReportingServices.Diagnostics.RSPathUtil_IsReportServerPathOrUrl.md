# Microsoft.ReportingServices.Diagnostics.RSPathUtil::IsReportServerPathOrUrl

- ea: `0x9690`
- end: `0x96ff`
- name: `Microsoft.ReportingServices.Diagnostics.RSPathUtil::IsReportServerPathOrUrl`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x95b0`

## callees

- `0x6270`
- `0x7900`
- `0x9680`
- `0x9690`
- `0x10150`

## pseudocode

```c

```

## disassembly

```asm
0x9690  call     class Microsoft.ReportingServices.Diagnostics.IPathManager Microsoft.ReportingServices.Diagnostics.RSPathUtil::GetPathManager()
0x9695  ldarg.0
0x9696  ldarg.1
0x9697  ldarg.2
0x9698  callvirt instance bool Microsoft.ReportingServices.Diagnostics.IPathManager::IsSupportedUrl(string path, bool checkProtocol, [out] bool& isInternal)
0x969d  brfalse.s loc_96FD
0x969f  ldarg.2
0x96a0  ldind.u1
0x96a1  brtrue.s loc_96FB
0x96a3  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x96a8  callvirt instance string Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_ReportServerVirtualDirectory()
0x96ad  stloc.0
0x96ae  ldloc.0
0x96af  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x96b4  brfalse.s loc_96B8
0x96b6  ldc.i4.0
0x96b7  ret
0x96b8  ldarg.0
0x96b9  newobj   instance void [System]System.Uri::.ctor(string)
0x96be  stloc.1
0x96bf  ldloc.0
0x96c0  newobj   instance void [System]System.Uri::.ctor(string)
0x96c5  stloc.2
0x96c6  ldloc.1
0x96c7  ldc.i4.s 0xD
0x96c9  ldc.i4.3
0x96ca  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x96cf  ldloc.2
0x96d0  ldc.i4.s 0xD
0x96d2  ldc.i4.3
0x96d3  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x96d8  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x96dd  brtrue.s loc_96F9
0x96df  ldloc.1
0x96e0  ldc.i4.s 0x10
0x96e2  ldc.i4.3
0x96e3  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x96e8  ldloc.2
0x96e9  ldc.i4.s 0x10
0x96eb  ldc.i4.3
0x96ec  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x96f1  ldc.i4.5
0x96f2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x96f7  brfalse.s loc_96FB
0x96f9  ldc.i4.0
0x96fa  ret
0x96fb  ldc.i4.1
0x96fc  ret
0x96fd  ldc.i4.0
0x96fe  ret
```

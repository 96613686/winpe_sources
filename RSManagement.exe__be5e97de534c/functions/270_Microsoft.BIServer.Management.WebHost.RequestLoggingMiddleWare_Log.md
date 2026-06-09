# Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::Log

- ea: `0x270`
- end: `0x2be`
- name: `Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::Log`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x470`

## callees

- `0x270`

## pseudocode

```c

```

## disassembly

```asm
0x270  ldarg.1
0x271  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x276  stloc.0
0x277  ldloca.s 0
0x279  call     instance bool [Microsoft.Owin]Microsoft.Owin.PathString::get_HasValue()
0x27e  brfalse.s loc_2B6
0x280  ldsfld   string[] Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::LogRoutesAsTrace
0x285  stloc.1
0x286  ldc.i4.0
0x287  stloc.2
0x288  br.s     loc_2B0
0x28a  ldloc.1
0x28b  ldloc.2
0x28c  ldelem.ref
0x28d  stloc.3
0x28e  ldarg.1
0x28f  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x294  stloc.0
0x295  ldloca.s 0
0x297  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x29c  ldloc.3
0x29d  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x2a2  brfalse.s loc_2AC
0x2a4  ldarg.2
0x2a5  ldarg.3
0x2a6  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x2ab  ret
0x2ac  ldloc.2
0x2ad  ldc.i4.1
0x2ae  add
0x2af  stloc.2
0x2b0  ldloc.2
0x2b1  ldloc.1
0x2b2  ldlen
0x2b3  conv.i4
0x2b4  blt.s    loc_28A
0x2b6  ldarg.2
0x2b7  ldarg.3
0x2b8  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2bd  ret
```

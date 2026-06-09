# Microsoft.ManagementConsole.Internal.ClassLibraryServices::Microsoft.ManagementConsole.Internal.IClassLibraryServices.CreateMessagePumpProxy

- ea: `0x7e20`
- end: `0x7e42`
- name: `Microsoft.ManagementConsole.Internal.ClassLibraryServices::Microsoft.ManagementConsole.Internal.IClassLibraryServices.CreateMessagePumpProxy`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x7e20`
- `0x8210`

## pseudocode

```c

```

## disassembly

```asm
0x7e20  newobj   instance void Microsoft.ManagementConsole.Internal.SnapInMessagePumpProxy::.ctor()
0x7e25  stloc.0
0x7e26  ldloc.0
0x7e27  stloc.2
0x7e28  leave.s  loc_7E40
0x7e2a  stloc.1
0x7e2b  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x7e30  ldc.i4.2
0x7e31  ldc.i4.s 0xC
0x7e33  ldloc.1
0x7e34  ldstr    aTracingExcepti// "Tracing exception from snap-in AppDomai"...
0x7e39  call     void [MMCFxCommon]Microsoft.ManagementConsole.Internal.TraceUtility::TraceException(class [System]System.Diagnostics.TraceSource, valuetype [System]System.Diagnostics.TraceEventType, int32, class [mscorlib]System.Exception, string)
0x7e3e  rethrow
0x7e40  ldloc.2
0x7e41  ret
```

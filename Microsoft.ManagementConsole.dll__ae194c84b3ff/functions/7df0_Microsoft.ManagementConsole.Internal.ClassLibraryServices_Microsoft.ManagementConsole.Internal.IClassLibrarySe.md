# Microsoft.ManagementConsole.Internal.ClassLibraryServices::Microsoft.ManagementConsole.Internal.IClassLibraryServices.CreateSnapIn

- ea: `0x7df0`
- end: `0x7e1a`
- name: `Microsoft.ManagementConsole.Internal.ClassLibraryServices::Microsoft.ManagementConsole.Internal.IClassLibraryServices.CreateSnapIn`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7df0`
- `0x7f10`
- `0x8020`

## pseudocode

```c

```

## disassembly

```asm
0x7df0  newobj   instance void Microsoft.ManagementConsole.Internal.SnapInClient::.ctor()
0x7df5  stloc.0
0x7df6  ldloc.0
0x7df7  ldarg.1
0x7df8  ldarg.2
0x7df9  callvirt instance void Microsoft.ManagementConsole.Internal.SnapInClient::CreateSnapIn(string assemblyName, string typeName)
0x7dfe  ldloc.0
0x7dff  stloc.2
0x7e00  leave.s  loc_7E18
0x7e02  stloc.1
0x7e03  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x7e08  ldc.i4.2
0x7e09  ldc.i4.s 0xC
0x7e0b  ldloc.1
0x7e0c  ldstr    aTracingExcepti// "Tracing exception from snap-in AppDomai"...
0x7e11  call     void [MMCFxCommon]Microsoft.ManagementConsole.Internal.TraceUtility::TraceException(class [System]System.Diagnostics.TraceSource, valuetype [System]System.Diagnostics.TraceEventType, int32, class [mscorlib]System.Exception, string)
0x7e16  rethrow
0x7e18  ldloc.2
0x7e19  ret
```

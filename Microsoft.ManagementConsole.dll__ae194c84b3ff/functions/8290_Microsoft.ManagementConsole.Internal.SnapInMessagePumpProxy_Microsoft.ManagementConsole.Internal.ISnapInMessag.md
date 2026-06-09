# Microsoft.ManagementConsole.Internal.SnapInMessagePumpProxy::Microsoft.ManagementConsole.Internal.ISnapInMessagePumpProxy.ExitThread

- ea: `0x8290`
- end: `0x82b4`
- name: `Microsoft.ManagementConsole.Internal.SnapInMessagePumpProxy::Microsoft.ManagementConsole.Internal.ISnapInMessagePumpProxy.ExitThread`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8290`

## pseudocode

```c

```

## disassembly

```asm
0x8290  ldarg.0
0x8291  call     void [System.Windows.Forms]System.Windows.Forms.Application::RemoveMessageFilter(class [System.Windows.Forms]System.Windows.Forms.IMessageFilter)
0x8296  call     void [System.Windows.Forms]System.Windows.Forms.Application::ExitThread()
0x829b  leave.s  loc_82B3
0x829d  stloc.0
0x829e  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x82a3  ldc.i4.2
0x82a4  ldc.i4.s 0xC
0x82a6  ldloc.0
0x82a7  ldstr    aTracingExcepti// "Tracing exception from snap-in AppDomai"...
0x82ac  call     void [MMCFxCommon]Microsoft.ManagementConsole.Internal.TraceUtility::TraceException(class [System]System.Diagnostics.TraceSource, valuetype [System]System.Diagnostics.TraceEventType, int32, class [mscorlib]System.Exception, string)
0x82b1  rethrow
0x82b3  ret
```

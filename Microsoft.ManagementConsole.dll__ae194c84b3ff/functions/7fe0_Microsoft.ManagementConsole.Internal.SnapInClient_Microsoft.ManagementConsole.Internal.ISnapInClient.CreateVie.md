# Microsoft.ManagementConsole.Internal.SnapInClient::Microsoft.ManagementConsole.Internal.ISnapInClient.CreateView

- ea: `0x7fe0`
- end: `0x801c`
- name: `Microsoft.ManagementConsole.Internal.SnapInClient::Microsoft.ManagementConsole.Internal.ISnapInClient.CreateView`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7fe0`
- `0x8090`
- `0x81e0`

## pseudocode

```c

```

## disassembly

```asm
0x7fe0  call     void Microsoft.ManagementConsole.Internal.SynchronizationContextCache::RestoreOriginalContext()
0x7fe5  ldarg.0
0x7fe6  ldfld    class CreateViewHandler Microsoft.ManagementConsole.Internal.SnapInClient::_onCreateView
0x7feb  brfalse.s loc_8000
0x7fed  ldarg.0
0x7fee  ldfld    class CreateViewHandler Microsoft.ManagementConsole.Internal.SnapInClient::_onCreateView
0x7ff3  ldarg.1
0x7ff4  ldarg.2
0x7ff5  ldarg.3
0x7ff6  ldarg.s  4
0x7ff8  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IMessageClient CreateViewHandler::Invoke(int32 nodeId, int32 componentId, int32 viewDescriptionId, int32 viewInstanceId)
0x7ffd  stloc.1
0x7ffe  leave.s  loc_801A
0x8000  ldnull
0x8001  stloc.1
0x8002  leave.s  loc_801A
0x8004  stloc.0
0x8005  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x800a  ldc.i4.2
0x800b  ldc.i4.s 0xC
0x800d  ldloc.0
0x800e  ldstr    aTracingExcepti// "Tracing exception from snap-in AppDomai"...
0x8013  call     void [MMCFxCommon]Microsoft.ManagementConsole.Internal.TraceUtility::TraceException(class [System]System.Diagnostics.TraceSource, valuetype [System]System.Diagnostics.TraceEventType, int32, class [mscorlib]System.Exception, string)
0x8018  rethrow
0x801a  ldloc.1
0x801b  ret
```

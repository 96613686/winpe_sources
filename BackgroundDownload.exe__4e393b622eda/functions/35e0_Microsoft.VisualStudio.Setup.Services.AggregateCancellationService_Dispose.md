# Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::Dispose

- ea: `0x35e0`
- end: `0x361b`
- name: `Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::Dispose`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3620`

## callees

- `0x35e0`

## pseudocode

```c

```

## disassembly

```asm
0x35e0  ldarg.0
0x35e1  ldfld    bool Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::isDisposed
0x35e6  brtrue.s loc_361A
0x35e8  ldarg.1
0x35e9  brfalse.s loc_3613
0x35eb  ldarg.0
0x35ec  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::cancellationTokenSource
0x35f1  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Dispose()
0x35f6  ldarg.0
0x35f7  ldfld    class Microsoft.VisualStudio.Setup.Services.ICancellationService[] Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::<cancellationServices>P
0x35fc  stloc.0
0x35fd  ldc.i4.0
0x35fe  stloc.1
0x35ff  br.s     loc_360D
0x3601  ldloc.0
0x3602  ldloc.1
0x3603  ldelem.ref
0x3604  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3609  ldloc.1
0x360a  ldc.i4.1
0x360b  add
0x360c  stloc.1
0x360d  ldloc.1
0x360e  ldloc.0
0x360f  ldlen
0x3610  conv.i4
0x3611  blt.s    loc_3601
0x3613  ldarg.0
0x3614  ldc.i4.1
0x3615  stfld    bool Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::isDisposed
0x361a  ret
```

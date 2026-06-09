# Microsoft.VisualStudio.Setup.ElevationServiceManager::Dispose_0

- ea: `0xf30`
- end: `0xf65`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::Dispose_0`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xf20`

## callees

- `0xe90`
- `0xf30`

## pseudocode

```c

```

## disassembly

```asm
0xf30  ldarg.0
0xf31  ldfld    bool Microsoft.VisualStudio.Setup.ElevationServiceManager::isDisposed
0xf36  brtrue.s loc_F64
0xf38  ldarg.1
0xf39  brfalse.s loc_F5D
0xf3b  ldarg.0
0xf3c  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.ElevationServiceManager::cancellationToken
0xf41  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0xf46  ldarg.0
0xf47  call     instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::TryClearPipeName()
0xf4c  ldarg.0
0xf4d  ldfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0xf52  dup
0xf53  brtrue.s loc_F58
0xf55  pop
0xf56  br.s     loc_F5D
0xf58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf5d  ldarg.0
0xf5e  ldc.i4.1
0xf5f  stfld    bool Microsoft.VisualStudio.Setup.ElevationServiceManager::isDisposed
0xf64  ret
```

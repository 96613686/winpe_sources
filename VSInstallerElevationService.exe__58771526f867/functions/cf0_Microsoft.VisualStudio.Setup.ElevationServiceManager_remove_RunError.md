# Microsoft.VisualStudio.Setup.ElevationServiceManager::remove_RunError

- ea: `0xcf0`
- end: `0xd19`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::remove_RunError`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1370`

## callees

- `0xcf0`

## pseudocode

```c

```

## disassembly

```asm
0xcf0  ldarg.0
0xcf1  ldfld    class [mscorlib]System.Action`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.ElevationServiceManager::RunError
0xcf6  stloc.0
0xcf7  ldloc.0
0xcf8  stloc.1
0xcf9  ldloc.1
0xcfa  ldarg.1
0xcfb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xd00  castclass class [mscorlib]System.Action`1<class [mscorlib]System.Exception>
0xd05  stloc.2
0xd06  ldarg.0
0xd07  ldflda   class [mscorlib]System.Action`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.ElevationServiceManager::RunError
0xd0c  ldloc.2
0xd0d  ldloc.1
0xd0e  call     T0x2B000001
0xd13  stloc.0
0xd14  ldloc.0
0xd15  ldloc.1
0xd16  bne.un.s loc_CF7
0xd18  ret
```

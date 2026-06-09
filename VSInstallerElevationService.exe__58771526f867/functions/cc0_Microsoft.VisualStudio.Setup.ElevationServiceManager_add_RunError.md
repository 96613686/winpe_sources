# Microsoft.VisualStudio.Setup.ElevationServiceManager::add_RunError

- ea: `0xcc0`
- end: `0xce9`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::add_RunError`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1200`

## callees

- `0xcc0`

## pseudocode

```c

```

## disassembly

```asm
0xcc0  ldarg.0
0xcc1  ldfld    class [mscorlib]System.Action`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.ElevationServiceManager::RunError
0xcc6  stloc.0
0xcc7  ldloc.0
0xcc8  stloc.1
0xcc9  ldloc.1
0xcca  ldarg.1
0xccb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xcd0  castclass class [mscorlib]System.Action`1<class [mscorlib]System.Exception>
0xcd5  stloc.2
0xcd6  ldarg.0
0xcd7  ldflda   class [mscorlib]System.Action`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.ElevationServiceManager::RunError
0xcdc  ldloc.2
0xcdd  ldloc.1
0xcde  call     T0x2B000001
0xce3  stloc.0
0xce4  ldloc.0
0xce5  ldloc.1
0xce6  bne.un.s loc_CC7
0xce8  ret
```

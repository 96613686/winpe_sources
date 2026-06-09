# System.Windows.Input.TextComposition::.ctor_0

- ea: `0x4d320`
- end: `0x4d356`
- name: `System.Windows.Input.TextComposition::.ctor_0`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x37d50`
- `0x4d310`

## callees

- `0x398f0`
- `0x39bc0`
- `0x4d320`
- `0x4d360`

## string_xrefs

- `0x4d33e`: `autoComplete`

## pseudocode

```c

```

## disassembly

```asm
0x4d320  ldarg.0
0x4d321  ldarg.1
0x4d322  ldarg.2
0x4d323  ldarg.3
0x4d324  ldarg.s  4
0x4d326  call     class System.Windows.Input.InputManager System.Windows.Input.InputManager::get_Current()
0x4d32b  callvirt instance class System.Windows.Input.KeyboardDevice System.Windows.Input.InputManager::get_PrimaryKeyboardDevice()
0x4d330  call     instance void System.Windows.Input.TextComposition::.ctor(class System.Windows.Input.InputManager inputManager, class System.Windows.IInputElement source, string resultText, valuetype System.Windows.Input.TextCompositionAutoComplete autoComplete, class System.Windows.Input.InputDevice inputDevice)
0x4d335  ldarg.s  4
0x4d337  brfalse.s loc_4D355
0x4d339  ldarg.s  4
0x4d33b  ldc.i4.1
0x4d33c  beq.s    loc_4D355
0x4d33e  ldstr    aAutocomplete// "autoComplete"
0x4d343  ldarg.s  4
0x4d345  ldtoken  System.Windows.Input.TextCompositionAutoComplete
0x4d34a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4d34f  newobj   instance void [System]System.ComponentModel.InvalidEnumArgumentException::.ctor(string, int32, class [mscorlib]System.Type)
0x4d354  throw
0x4d355  ret
```

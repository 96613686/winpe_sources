# System.Windows.Input.TextCompositionEventArgs::.ctor

- ea: `0x4d5e0`
- end: `0x4d602`
- name: `System.Windows.Input.TextCompositionEventArgs::.ctor`
- size: `34`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4d8d0`
- `0x4d970`
- `0x4da30`
- `0x4dcb0`

## callees

- `0x38f90`
- `0x4d5e0`

## string_xrefs

- `0x4d5ef`: `composition`

## pseudocode

```c

```

## disassembly

```asm
0x4d5e0  ldarg.0
0x4d5e1  ldarg.1
0x4d5e2  call     int32 [mscorlib]System.Environment::get_TickCount()
0x4d5e7  call     instance void System.Windows.Input.InputEventArgs::.ctor(class System.Windows.Input.InputDevice inputDevice, int32 timestamp)
0x4d5ec  ldarg.2
0x4d5ed  brtrue.s loc_4D5FA
0x4d5ef  ldstr    aComposition// "composition"
0x4d5f4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d5f9  throw
0x4d5fa  ldarg.0
0x4d5fb  ldarg.2
0x4d5fc  stfld    class System.Windows.Input.TextComposition System.Windows.Input.TextCompositionEventArgs::_composition
0x4d601  ret
```

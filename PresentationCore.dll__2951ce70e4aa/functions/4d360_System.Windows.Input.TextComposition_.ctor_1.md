# System.Windows.Input.TextComposition::.ctor_1

- ea: `0x4d360`
- end: `0x4d3d2`
- name: `System.Windows.Input.TextComposition::.ctor_1`
- size: `114`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x37a30`
- `0x4d320`
- `0x4db60`
- `0x4dcb0`

## callees

- `0x4d360`
- `0x146e40`

## string_xrefs

- `0x4d378`: `TextComposition_NullResultText`

## pseudocode

```c

```

## disassembly

```asm
0x4d360  ldarg.0
0x4d361  call     instance void [WindowsBase]System.Windows.Threading.DispatcherObject::.ctor()
0x4d366  ldarg.0
0x4d367  ldarg.1
0x4d368  stfld    class System.Windows.Input.InputManager System.Windows.Input.TextComposition::_inputManager
0x4d36d  ldarg.0
0x4d36e  ldarg.s  5
0x4d370  stfld    class System.Windows.Input.InputDevice System.Windows.Input.TextComposition::_inputDevice
0x4d375  ldarg.3
0x4d376  brtrue.s loc_4D388
0x4d378  ldstr    aTextcompositio// "TextComposition_NullResultText"
0x4d37d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x4d382  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d387  throw
0x4d388  ldarg.0
0x4d389  ldarg.3
0x4d38a  stfld    string System.Windows.Input.TextComposition::_resultText
0x4d38f  ldarg.0
0x4d390  ldstr    asc_15E4E4// ""
0x4d395  stfld    string System.Windows.Input.TextComposition::_compositionText
0x4d39a  ldarg.0
0x4d39b  ldstr    asc_15E4E4// ""
0x4d3a0  stfld    string System.Windows.Input.TextComposition::_systemText
0x4d3a5  ldarg.0
0x4d3a6  ldstr    asc_15E4E4// ""
0x4d3ab  stfld    string System.Windows.Input.TextComposition::_systemCompositionText
0x4d3b0  ldarg.0
0x4d3b1  ldstr    asc_15E4E4// ""
0x4d3b6  stfld    string System.Windows.Input.TextComposition::_controlText
0x4d3bb  ldarg.0
0x4d3bc  ldarg.s  4
0x4d3be  stfld    valuetype System.Windows.Input.TextCompositionAutoComplete System.Windows.Input.TextComposition::_autoComplete
0x4d3c3  ldarg.0
0x4d3c4  ldc.i4.0
0x4d3c5  stfld    valuetype System.Windows.Input.TextCompositionStage System.Windows.Input.TextComposition::_stage
0x4d3ca  ldarg.0
0x4d3cb  ldarg.2
0x4d3cc  stfld    class System.Windows.IInputElement System.Windows.Input.TextComposition::_source
0x4d3d1  ret
```

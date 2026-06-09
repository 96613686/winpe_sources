# System.Windows.Input.TextCompositionManager::UnsafeCompleteComposition

- ea: `0x4da30`
- end: `0x4dae9`
- name: `System.Windows.Input.TextCompositionManager::UnsafeCompleteComposition`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x4d8c0`
- `0x4dcb0`

## callees

- `0x2cbe0`
- `0x2ccb0`
- `0x39f10`
- `0x4d580`
- `0x4d590`
- `0x4d5a0`
- `0x4d5b0`
- `0x4d5c0`
- `0x4d5e0`
- `0x4da30`
- `0x146e70`

## string_xrefs

- `0x4da33`: `composition`
- `0x4da53`: `composition`
- `0x4da79`: `composition`
- `0x4daa0`: `composition`
- `0x4da46`: `TextCompositionManager_NoInputManager`
- `0x4da6c`: `TextCompositionManager_TextCompositionNotStarted`
- `0x4da93`: `TextCompositionManager_TextCompositionHasDone`

## pseudocode

```c

```

## disassembly

```asm
0x4da30  ldarg.0
0x4da31  brtrue.s loc_4DA3E
0x4da33  ldstr    aComposition// "composition"
0x4da38  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4da3d  throw
0x4da3e  ldarg.0
0x4da3f  callvirt instance class System.Windows.Input.InputManager System.Windows.Input.TextComposition::get__InputManager()
0x4da44  brtrue.s loc_4DA64
0x4da46  ldstr    aTextcompositio_0// "TextCompositionManager_NoInputManager"
0x4da4b  ldc.i4.1
0x4da4c  newarr   [mscorlib]System.Object
0x4da51  dup
0x4da52  ldc.i4.0
0x4da53  ldstr    aComposition// "composition"
0x4da58  stelem.ref
0x4da59  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4da5e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4da63  throw
0x4da64  ldarg.0
0x4da65  callvirt instance valuetype System.Windows.Input.TextCompositionStage System.Windows.Input.TextComposition::get_Stage()
0x4da6a  brtrue.s loc_4DA8A
0x4da6c  ldstr    aTextcompositio_2// "TextCompositionManager_TextCompositionN"...
0x4da71  ldc.i4.1
0x4da72  newarr   [mscorlib]System.Object
0x4da77  dup
0x4da78  ldc.i4.0
0x4da79  ldstr    aComposition// "composition"
0x4da7e  stelem.ref
0x4da7f  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4da84  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4da89  throw
0x4da8a  ldarg.0
0x4da8b  callvirt instance valuetype System.Windows.Input.TextCompositionStage System.Windows.Input.TextComposition::get_Stage()
0x4da90  ldc.i4.2
0x4da91  bne.un.s loc_4DAB1
0x4da93  ldstr    aTextcompositio_3// "TextCompositionManager_TextCompositionH"...
0x4da98  ldc.i4.1
0x4da99  newarr   [mscorlib]System.Object
0x4da9e  dup
0x4da9f  ldc.i4.0
0x4daa0  ldstr    aComposition// "composition"
0x4daa5  stelem.ref
0x4daa6  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4daab  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4dab0  throw
0x4dab1  ldarg.0
0x4dab2  ldc.i4.2
0x4dab3  callvirt instance void System.Windows.Input.TextComposition::set_Stage(valuetype System.Windows.Input.TextCompositionStage value)
0x4dab8  ldarg.0
0x4dab9  callvirt instance class System.Windows.Input.InputDevice System.Windows.Input.TextComposition::get__InputDevice()
0x4dabe  ldarg.0
0x4dabf  newobj   instance void System.Windows.Input.TextCompositionEventArgs::.ctor(class System.Windows.Input.InputDevice inputDevice, class System.Windows.Input.TextComposition composition)
0x4dac4  stloc.0
0x4dac5  ldloc.0
0x4dac6  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::PreviewTextInputEvent
0x4dacb  callvirt instance void System.Windows.RoutedEventArgs::set_RoutedEvent(class System.Windows.RoutedEvent value)
0x4dad0  ldloc.0
0x4dad1  ldarg.0
0x4dad2  callvirt instance class System.Windows.IInputElement System.Windows.Input.TextComposition::get_Source()
0x4dad7  callvirt instance void System.Windows.RoutedEventArgs::set_Source(object value)
0x4dadc  ldarg.0
0x4dadd  callvirt instance class System.Windows.Input.InputManager System.Windows.Input.TextComposition::get__InputManager()
0x4dae2  ldloc.0
0x4dae3  callvirt instance bool System.Windows.Input.InputManager::ProcessInput(class System.Windows.Input.InputEventArgs input)
0x4dae8  ret
```

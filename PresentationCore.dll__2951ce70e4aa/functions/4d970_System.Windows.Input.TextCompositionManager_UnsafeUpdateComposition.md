# System.Windows.Input.TextCompositionManager::UnsafeUpdateComposition

- ea: `0x4d970`
- end: `0x4da22`
- name: `System.Windows.Input.TextCompositionManager::UnsafeUpdateComposition`
- size: `178`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4d8b0`
- `0x4db60`
- `0x4e1c0`

## callees

- `0x2cbe0`
- `0x2ccb0`
- `0x39f10`
- `0x4d580`
- `0x4d590`
- `0x4d5a0`
- `0x4d5b0`
- `0x4d5e0`
- `0x4d970`
- `0x146e70`

## string_xrefs

- `0x4d973`: `composition`
- `0x4d993`: `composition`
- `0x4d9b9`: `composition`
- `0x4d9e0`: `composition`
- `0x4d986`: `TextCompositionManager_NoInputManager`
- `0x4d9ac`: `TextCompositionManager_TextCompositionNotStarted`
- `0x4d9d3`: `TextCompositionManager_TextCompositionHasDone`

## pseudocode

```c

```

## disassembly

```asm
0x4d970  ldarg.0
0x4d971  brtrue.s loc_4D97E
0x4d973  ldstr    aComposition// "composition"
0x4d978  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d97d  throw
0x4d97e  ldarg.0
0x4d97f  callvirt instance class System.Windows.Input.InputManager System.Windows.Input.TextComposition::get__InputManager()
0x4d984  brtrue.s loc_4D9A4
0x4d986  ldstr    aTextcompositio_0// "TextCompositionManager_NoInputManager"
0x4d98b  ldc.i4.1
0x4d98c  newarr   [mscorlib]System.Object
0x4d991  dup
0x4d992  ldc.i4.0
0x4d993  ldstr    aComposition// "composition"
0x4d998  stelem.ref
0x4d999  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4d99e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d9a3  throw
0x4d9a4  ldarg.0
0x4d9a5  callvirt instance valuetype System.Windows.Input.TextCompositionStage System.Windows.Input.TextComposition::get_Stage()
0x4d9aa  brtrue.s loc_4D9CA
0x4d9ac  ldstr    aTextcompositio_2// "TextCompositionManager_TextCompositionN"...
0x4d9b1  ldc.i4.1
0x4d9b2  newarr   [mscorlib]System.Object
0x4d9b7  dup
0x4d9b8  ldc.i4.0
0x4d9b9  ldstr    aComposition// "composition"
0x4d9be  stelem.ref
0x4d9bf  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4d9c4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d9c9  throw
0x4d9ca  ldarg.0
0x4d9cb  callvirt instance valuetype System.Windows.Input.TextCompositionStage System.Windows.Input.TextComposition::get_Stage()
0x4d9d0  ldc.i4.2
0x4d9d1  bne.un.s loc_4D9F1
0x4d9d3  ldstr    aTextcompositio_3// "TextCompositionManager_TextCompositionH"...
0x4d9d8  ldc.i4.1
0x4d9d9  newarr   [mscorlib]System.Object
0x4d9de  dup
0x4d9df  ldc.i4.0
0x4d9e0  ldstr    aComposition// "composition"
0x4d9e5  stelem.ref
0x4d9e6  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4d9eb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d9f0  throw
0x4d9f1  ldarg.0
0x4d9f2  callvirt instance class System.Windows.Input.InputDevice System.Windows.Input.TextComposition::get__InputDevice()
0x4d9f7  ldarg.0
0x4d9f8  newobj   instance void System.Windows.Input.TextCompositionEventArgs::.ctor(class System.Windows.Input.InputDevice inputDevice, class System.Windows.Input.TextComposition composition)
0x4d9fd  stloc.0
0x4d9fe  ldloc.0
0x4d9ff  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::PreviewTextInputUpdateEvent
0x4da04  callvirt instance void System.Windows.RoutedEventArgs::set_RoutedEvent(class System.Windows.RoutedEvent value)
0x4da09  ldloc.0
0x4da0a  ldarg.0
0x4da0b  callvirt instance class System.Windows.IInputElement System.Windows.Input.TextComposition::get_Source()
0x4da10  callvirt instance void System.Windows.RoutedEventArgs::set_Source(object value)
0x4da15  ldarg.0
0x4da16  callvirt instance class System.Windows.Input.InputManager System.Windows.Input.TextComposition::get__InputManager()
0x4da1b  ldloc.0
0x4da1c  callvirt instance bool System.Windows.Input.InputManager::ProcessInput(class System.Windows.Input.InputEventArgs input)
0x4da21  ret
```

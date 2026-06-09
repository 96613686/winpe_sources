# System.Windows.Input.TextCompositionManager::UnsafeStartComposition

- ea: `0x4d8d0`
- end: `0x4d962`
- name: `System.Windows.Input.TextCompositionManager::UnsafeStartComposition`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x4d8a0`
- `0x4db60`
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
- `0x4d8d0`
- `0x146e70`

## string_xrefs

- `0x4d8d3`: `composition`
- `0x4d8f3`: `composition`
- `0x4d919`: `composition`
- `0x4d8e6`: `TextCompositionManager_NoInputManager`
- `0x4d90c`: `TextCompositionManager_TextCompositionHasStarted`

## pseudocode

```c

```

## disassembly

```asm
0x4d8d0  ldarg.0
0x4d8d1  brtrue.s loc_4D8DE
0x4d8d3  ldstr    aComposition// "composition"
0x4d8d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d8dd  throw
0x4d8de  ldarg.0
0x4d8df  callvirt instance class System.Windows.Input.InputManager System.Windows.Input.TextComposition::get__InputManager()
0x4d8e4  brtrue.s loc_4D904
0x4d8e6  ldstr    aTextcompositio_0// "TextCompositionManager_NoInputManager"
0x4d8eb  ldc.i4.1
0x4d8ec  newarr   [mscorlib]System.Object
0x4d8f1  dup
0x4d8f2  ldc.i4.0
0x4d8f3  ldstr    aComposition// "composition"
0x4d8f8  stelem.ref
0x4d8f9  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4d8fe  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d903  throw
0x4d904  ldarg.0
0x4d905  callvirt instance valuetype System.Windows.Input.TextCompositionStage System.Windows.Input.TextComposition::get_Stage()
0x4d90a  brfalse.s loc_4D92A
0x4d90c  ldstr    aTextcompositio_1// "TextCompositionManager_TextCompositionH"...
0x4d911  ldc.i4.1
0x4d912  newarr   [mscorlib]System.Object
0x4d917  dup
0x4d918  ldc.i4.0
0x4d919  ldstr    aComposition// "composition"
0x4d91e  stelem.ref
0x4d91f  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x4d924  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d929  throw
0x4d92a  ldarg.0
0x4d92b  ldc.i4.1
0x4d92c  callvirt instance void System.Windows.Input.TextComposition::set_Stage(valuetype System.Windows.Input.TextCompositionStage value)
0x4d931  ldarg.0
0x4d932  callvirt instance class System.Windows.Input.InputDevice System.Windows.Input.TextComposition::get__InputDevice()
0x4d937  ldarg.0
0x4d938  newobj   instance void System.Windows.Input.TextCompositionEventArgs::.ctor(class System.Windows.Input.InputDevice inputDevice, class System.Windows.Input.TextComposition composition)
0x4d93d  stloc.0
0x4d93e  ldloc.0
0x4d93f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::PreviewTextInputStartEvent
0x4d944  callvirt instance void System.Windows.RoutedEventArgs::set_RoutedEvent(class System.Windows.RoutedEvent value)
0x4d949  ldloc.0
0x4d94a  ldarg.0
0x4d94b  callvirt instance class System.Windows.IInputElement System.Windows.Input.TextComposition::get_Source()
0x4d950  callvirt instance void System.Windows.RoutedEventArgs::set_Source(object value)
0x4d955  ldarg.0
0x4d956  callvirt instance class System.Windows.Input.InputManager System.Windows.Input.TextComposition::get__InputManager()
0x4d95b  ldloc.0
0x4d95c  callvirt instance bool System.Windows.Input.InputManager::ProcessInput(class System.Windows.Input.InputEventArgs input)
0x4d961  ret
```

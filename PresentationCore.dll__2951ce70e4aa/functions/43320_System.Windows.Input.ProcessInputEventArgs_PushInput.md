# System.Windows.Input.ProcessInputEventArgs::PushInput

- ea: `0x43320`
- end: `0x43346`
- name: `System.Windows.Input.ProcessInputEventArgs::PushInput`
- size: `38`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x30490`
- `0x3d770`
- `0x41bf0`
- `0x41fe0`
- `0x42740`
- `0x44ad0`
- `0x4dcb0`
- `0x50670`
- `0x50730`
- `0x56f10`
- `0x56fc0`

## callees

- `0x39f50`
- `0x431f0`
- `0x43320`
- `0x146e40`

## string_xrefs

- `0x43328`: `NotAllowedToAccessStagingArea`

## pseudocode

```c

```

## disassembly

```asm
0x43320  ldarg.0
0x43321  ldfld    bool System.Windows.Input.ProcessInputEventArgs::_allowAccessToStagingArea
0x43326  brtrue.s loc_43338
0x43328  ldstr    aNotallowedtoac// "NotAllowedToAccessStagingArea"
0x4332d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x43332  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x43337  throw
0x43338  ldarg.0
0x43339  call     instance class System.Windows.Input.InputManager System.Windows.Input.NotifyInputEventArgs::get_UnsecureInputManager()
0x4333e  ldarg.1
0x4333f  ldarg.2
0x43340  callvirt instance class System.Windows.Input.StagingAreaInputItem System.Windows.Input.InputManager::PushInput(class System.Windows.Input.InputEventArgs input, class System.Windows.Input.StagingAreaInputItem promote)
0x43345  ret
```

# System.Windows.Input.CommandDeviceEventArgs::.ctor

- ea: `0x308a0`
- end: `0x308be`
- name: `System.Windows.Input.CommandDeviceEventArgs::.ctor`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x30490`

## callees

- `0x308a0`
- `0x38f90`

## string_xrefs

- `0x308ab`: `command`

## pseudocode

```c

```

## disassembly

```asm
0x308a0  ldarg.0
0x308a1  ldarg.1
0x308a2  ldarg.2
0x308a3  call     instance void System.Windows.Input.InputEventArgs::.ctor(class System.Windows.Input.InputDevice inputDevice, int32 timestamp)
0x308a8  ldarg.3
0x308a9  brtrue.s loc_308B6
0x308ab  ldstr    aCommand// "command"
0x308b0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x308b5  throw
0x308b6  ldarg.0
0x308b7  ldarg.3
0x308b8  stfld    class [System]System.Windows.Input.ICommand System.Windows.Input.CommandDeviceEventArgs::_command
0x308bd  ret
```

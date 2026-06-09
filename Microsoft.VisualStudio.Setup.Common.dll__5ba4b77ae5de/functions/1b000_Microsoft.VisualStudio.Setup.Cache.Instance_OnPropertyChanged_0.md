# Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged_0

- ea: `0x1b000`
- end: `0x1b01b`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged_0`
- size: `27`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1aa70`
- `0x1afd0`
- `0x1aff0`
- `0x1b150`
- `0x1b1d0`
- `0x1b1f0`
- `0x1b210`
- `0x1b230`

## callees

- `0x1b000`

## pseudocode

```c

```

## disassembly

```asm
0x1b000  ldarg.1
0x1b001  ldc.i4.1
0x1b002  stind.i1
0x1b003  ldarg.0
0x1b004  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.VisualStudio.Setup.Cache.Instance::PropertyChanged
0x1b009  dup
0x1b00a  brtrue.s loc_1B00E
0x1b00c  pop
0x1b00d  ret
0x1b00e  ldarg.0
0x1b00f  ldarg.2
0x1b010  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1b015  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1b01a  ret
```

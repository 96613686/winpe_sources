# System.Windows.Input.CommandBinding::.ctor_2

- ea: `0x30970`
- end: `0x309a0`
- name: `System.Windows.Input.CommandBinding::.ctor_2`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x30950`
- `0x30960`

## callees

- `0x30970`
- `0x30a30`
- `0x30af0`

## string_xrefs

- `0x30979`: `command`

## pseudocode

```c

```

## disassembly

```asm
0x30970  ldarg.0
0x30971  call     instance void [mscorlib]System.Object::.ctor()
0x30976  ldarg.1
0x30977  brtrue.s loc_30984
0x30979  ldstr    aCommand// "command"
0x3097e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x30983  throw
0x30984  ldarg.0
0x30985  ldarg.1
0x30986  stfld    class [System]System.Windows.Input.ICommand System.Windows.Input.CommandBinding::_command
0x3098b  ldarg.2
0x3098c  brfalse.s loc_30995
0x3098e  ldarg.0
0x3098f  ldarg.2
0x30990  call     instance void System.Windows.Input.CommandBinding::add_Executed(class System.Windows.Input.ExecutedRoutedEventHandler value)
0x30995  ldarg.3
0x30996  brfalse.s loc_3099F
0x30998  ldarg.0
0x30999  ldarg.3
0x3099a  call     instance void System.Windows.Input.CommandBinding::add_CanExecute(class System.Windows.Input.CanExecuteRoutedEventHandler value)
0x3099f  ret
```

# System.Windows.Window::VerifyNotClosing

- ea: `0x35300`
- end: `0x35339`
- name: `System.Windows.Window::VerifyNotClosing`
- size: `57`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x32e40`
- `0x32f50`
- `0x34190`
- `0x343c0`
- `0x36870`

## callees

- `0x34230`
- `0x34250`
- `0x35300`
- `0x38c40`

## string_xrefs

- `0x35308`: `InvalidOperationDuringClosing`
- `0x35328`: `InvalidCompositionTarget`

## pseudocode

```c

```

## disassembly

```asm
0x35300  ldarg.0
0x35301  ldfld    bool System.Windows.Window::_isClosing
0x35306  brfalse.s loc_35318
0x35308  ldstr    aInvalidoperati// "InvalidOperationDuringClosing"
0x3530d  call     string System.Windows.SR::Get(string id)
0x35312  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x35317  throw
0x35318  ldarg.0
0x35319  call     instance bool System.Windows.Window::get_IsSourceWindowNull()
0x3531e  brtrue.s loc_35338
0x35320  ldarg.0
0x35321  call     instance bool System.Windows.Window::get_IsCompositionTargetInvalid()
0x35326  brfalse.s loc_35338
0x35328  ldstr    aInvalidcomposi// "InvalidCompositionTarget"
0x3532d  call     string System.Windows.SR::Get(string id)
0x35332  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x35337  throw
0x35338  ret
```

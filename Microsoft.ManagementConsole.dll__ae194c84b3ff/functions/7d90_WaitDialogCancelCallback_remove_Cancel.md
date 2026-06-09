# WaitDialogCancelCallback::remove_Cancel

- ea: `0x7d90`
- end: `0x7dbe`
- name: `WaitDialogCancelCallback::remove_Cancel`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x7be0`

## callees

- `0x7d90`

## pseudocode

```c

```

## disassembly

```asm
0x7d90  ldarg.0
0x7d91  ldfld    object WaitDialogCancelCallback::_syncRoot
0x7d96  dup
0x7d97  stloc.0
0x7d98  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x7d9d  ldarg.0
0x7d9e  dup
0x7d9f  ldfld    class [mscorlib]System.EventHandler WaitDialogCancelCallback::_cancel
0x7da4  ldarg.1
0x7da5  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x7daa  castclass [mscorlib]System.EventHandler
0x7daf  stfld    class [mscorlib]System.EventHandler WaitDialogCancelCallback::_cancel
0x7db4  leave.s  loc_7DBD
0x7db6  ldloc.0
0x7db7  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7dbc  endfinally
0x7dbd  ret
```

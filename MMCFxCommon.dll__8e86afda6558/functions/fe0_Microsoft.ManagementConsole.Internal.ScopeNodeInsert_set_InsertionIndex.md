# Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_InsertionIndex

- ea: `0xfe0`
- end: `0xffd`
- name: `Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_InsertionIndex`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x58d0`

## callees

- `0xfe0`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldarg.1
0xfe1  ldc.i4   0x7FFFFFFF
0xfe6  bne.un.s loc_FF3
0xfe8  ldstr    aValue// "value"
0xfed  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xff2  throw
0xff3  ldarg.0
0xff4  ldarg.1
0xff5  ldc.i4.1
0xff6  add
0xff7  stfld    int32 Microsoft.ManagementConsole.Internal.ScopeNodeInsert::_insertionIndex
0xffc  ret
```

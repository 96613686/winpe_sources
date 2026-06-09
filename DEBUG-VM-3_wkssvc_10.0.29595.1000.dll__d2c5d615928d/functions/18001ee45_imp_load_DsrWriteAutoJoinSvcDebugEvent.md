# __imp_load_DsrWriteAutoJoinSvcDebugEvent

- ea: `0x18001ee45`
- end: `0x18001ee51`
- name: `__imp_load_DsrWriteAutoJoinSvcDebugEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001eda2`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ee45`

## pseudocode

```c
__int64 load_DsrWriteAutoJoinSvcDebugEvent()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x18001ee45  lea     rax, __imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ee4c  jmp     __tailMerge_dsreg_dll
```

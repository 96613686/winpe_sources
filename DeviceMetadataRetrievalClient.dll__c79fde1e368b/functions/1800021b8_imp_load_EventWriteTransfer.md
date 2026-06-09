# __imp_load_EventWriteTransfer

- ea: `0x1800021b8`
- end: `0x1800021c4`
- name: `__imp_load_EventWriteTransfer`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800021b8`

## pseudocode

```c
__int64 load_EventWriteTransfer()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021b8  lea     rax, __imp_EventWriteTransfer
0x1800021bf  jmp     __tailMerge_advapi32_dll
```

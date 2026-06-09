# __imp_load_CoCreateInstance

- ea: `0x140002640`
- end: `0x14000264c`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002056`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140002640`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x140002640  lea     rax, __imp_CoCreateInstance
0x140002647  jmp     __tailMerge_ole32_dll
```

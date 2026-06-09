# __imp_load_CoCreateInstance

- ea: `0x1800026af`
- end: `0x1800026bb`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002558`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800026af`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800026af  lea     rax, __imp_CoCreateInstance
0x1800026b6  jmp     __tailMerge_ole32_dll
```

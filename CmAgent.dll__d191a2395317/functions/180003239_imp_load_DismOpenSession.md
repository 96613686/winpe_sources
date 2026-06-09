# __imp_load_DismOpenSession

- ea: `0x180003239`
- end: `0x180003245`
- name: `__imp_load_DismOpenSession`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003160`

## import_xrefs

- `DismApi!DismOpenSession` at `0x180003239`

## pseudocode

```c
__int64 load_DismOpenSession()
{
  return _tailMerge_dismapi_dll();
}

```

## disassembly

```asm
0x180003239  lea     rax, __imp_DismOpenSession
0x180003240  jmp     __tailMerge_dismapi_dll
```

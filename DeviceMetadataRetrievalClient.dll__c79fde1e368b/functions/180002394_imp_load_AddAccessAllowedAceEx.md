# __imp_load_AddAccessAllowedAceEx

- ea: `0x180002394`
- end: `0x1800023a0`
- name: `__imp_load_AddAccessAllowedAceEx`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAceEx` at `0x180002394`

## pseudocode

```c
__int64 load_AddAccessAllowedAceEx()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002394  lea     rax, __imp_AddAccessAllowedAceEx
0x18000239b  jmp     __tailMerge_advapi32_dll
```

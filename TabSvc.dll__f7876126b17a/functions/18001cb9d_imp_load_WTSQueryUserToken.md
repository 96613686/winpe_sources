# __imp_load_WTSQueryUserToken

- ea: `0x18001cb9d`
- end: `0x18001cba9`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001cb0c`

## import_xrefs

- `WTSAPI32!WTSQueryUserToken` at `0x18001cb9d`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_wtsapi32_dll();
}

```

## disassembly

```asm
0x18001cb9d  lea     rax, __imp_WTSQueryUserToken
0x18001cba4  jmp     __tailMerge_wtsapi32_dll
```

# __imp_load_RmAccessCheck

- ea: `0x18001db50`
- end: `0x18001db5c`
- name: `__imp_load_RmAccessCheck`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001dad1`

## import_xrefs

- `RMCLIENT!RmAccessCheck` at `0x18001db50`

## pseudocode

```c
__int64 load_RmAccessCheck()
{
  return _tailMerge_rmclient_dll();
}

```

## disassembly

```asm
0x18001db50  lea     rax, __imp_RmAccessCheck
0x18001db57  jmp     __tailMerge_rmclient_dll
```

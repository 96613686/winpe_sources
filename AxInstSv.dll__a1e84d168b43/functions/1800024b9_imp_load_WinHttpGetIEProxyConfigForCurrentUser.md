# __imp_load_WinHttpGetIEProxyConfigForCurrentUser

- ea: `0x1800024b9`
- end: `0x1800024c5`
- name: `__imp_load_WinHttpGetIEProxyConfigForCurrentUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800022a1`

## import_xrefs

- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800024b9`

## pseudocode

```c
__int64 load_WinHttpGetIEProxyConfigForCurrentUser()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800024b9  lea     rax, __imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800024c0  jmp     __tailMerge_winhttp_dll
```

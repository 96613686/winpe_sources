# __imp_load_WinHttpGetDefaultProxyConfiguration

- ea: `0x1800024a7`
- end: `0x1800024b3`
- name: `__imp_load_WinHttpGetDefaultProxyConfiguration`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800022a1`

## import_xrefs

- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800024a7`

## pseudocode

```c
__int64 load_WinHttpGetDefaultProxyConfiguration()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800024a7  lea     rax, __imp_WinHttpGetDefaultProxyConfiguration
0x1800024ae  jmp     __tailMerge_winhttp_dll
```

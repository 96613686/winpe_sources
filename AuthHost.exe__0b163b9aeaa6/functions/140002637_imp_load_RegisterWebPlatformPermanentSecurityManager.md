# __imp_load_RegisterWebPlatformPermanentSecurityManager

- ea: `0x140002637`
- end: `0x140002643`
- name: `__imp_load_RegisterWebPlatformPermanentSecurityManager`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025b8`

## import_xrefs

- `urlmon!RegisterWebPlatformPermanentSecurityManager` at `0x140002637`

## pseudocode

```c
__int64 load_RegisterWebPlatformPermanentSecurityManager()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x140002637  lea     rax, __imp_RegisterWebPlatformPermanentSecurityManager
0x14000263e  jmp     __tailMerge_urlmon_dll
```

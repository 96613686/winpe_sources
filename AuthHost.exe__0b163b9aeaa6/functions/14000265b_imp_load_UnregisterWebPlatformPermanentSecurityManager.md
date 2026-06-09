# __imp_load_UnregisterWebPlatformPermanentSecurityManager

- ea: `0x14000265b`
- end: `0x140002667`
- name: `__imp_load_UnregisterWebPlatformPermanentSecurityManager`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025b8`

## import_xrefs

- `urlmon!UnregisterWebPlatformPermanentSecurityManager` at `0x14000265b`

## pseudocode

```c
__int64 load_UnregisterWebPlatformPermanentSecurityManager()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x14000265b  lea     rax, __imp_UnregisterWebPlatformPermanentSecurityManager
0x140002662  jmp     __tailMerge_urlmon_dll
```

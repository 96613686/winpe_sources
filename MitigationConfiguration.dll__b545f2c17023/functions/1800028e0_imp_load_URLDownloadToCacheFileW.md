# __imp_load_URLDownloadToCacheFileW

- ea: `0x1800028e0`
- end: `0x1800028ec`
- name: `__imp_load_URLDownloadToCacheFileW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002861`

## import_xrefs

- `urlmon!URLDownloadToCacheFileW` at `0x1800028e0`

## pseudocode

```c
__int64 load_URLDownloadToCacheFileW()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x1800028e0  lea     rax, __imp_URLDownloadToCacheFileW
0x1800028e7  jmp     __tailMerge_urlmon_dll
```

# __imp_load_?GetUSDeviceStoreFolderPath@@YAJPEAG_K@Z

- ea: `0x180002399`
- end: `0x1800023a5`
- name: `__imp_load_?GetUSDeviceStoreFolderPath@@YAJPEAG_K@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002308`

## import_xrefs

- `unistore!GetUSDeviceStoreFolderPath` at `0x180002399`

## pseudocode

```c
__int64 load__GetUSDeviceStoreFolderPath__YAJPEAG_K_Z()
{
  return _tailMerge_unistore_dll();
}

```

## disassembly

```asm
0x180002399  lea     rax, __imp_?GetUSDeviceStoreFolderPath@@YAJPEAG_K@Z; GetUSDeviceStoreFolderPath(ushort *,unsigned __int64)
0x1800023a0  jmp     __tailMerge_unistore_dll
```

# __imp_load_MFCreateDXGIDeviceManager

- ea: `0x180018341`
- end: `0x18001834d`
- name: `__imp_load_MFCreateDXGIDeviceManager`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateDXGIDeviceManager` at `0x180018341`

## pseudocode

```c
__int64 load_MFCreateDXGIDeviceManager()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180018341  lea     rax, __imp_MFCreateDXGIDeviceManager
0x180018348  jmp     __tailMerge_mfplat_dll
```

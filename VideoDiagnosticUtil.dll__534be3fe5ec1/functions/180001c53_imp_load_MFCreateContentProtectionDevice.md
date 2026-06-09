# __imp_load_MFCreateContentProtectionDevice

- ea: `0x180001c53`
- end: `0x180001c5f`
- name: `__imp_load_MFCreateContentProtectionDevice`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001bb0`

## import_xrefs

- `MFPlat!MFCreateContentProtectionDevice` at `0x180001c53`

## pseudocode

```c
__int64 load_MFCreateContentProtectionDevice()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180001c53  lea     rax, __imp_MFCreateContentProtectionDevice
0x180001c5a  jmp     __tailMerge_mfplat_dll
```

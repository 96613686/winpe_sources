# __imp_load_DXGIDeclareAdapterRemovalSupport

- ea: `0x1400040c8`
- end: `0x1400040d4`
- name: `__imp_load_DXGIDeclareAdapterRemovalSupport`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004049`

## import_xrefs

- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x1400040c8`

## pseudocode

```c
__int64 load_DXGIDeclareAdapterRemovalSupport()
{
  return _tailMerge_dxgi_dll();
}

```

## disassembly

```asm
0x1400040c8  lea     rax, __imp_DXGIDeclareAdapterRemovalSupport
0x1400040cf  jmp     __tailMerge_dxgi_dll
```

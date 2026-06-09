# __imp_load_D3D11CreateDevice

- ea: `0x18000a105`
- end: `0x18000a111`
- name: `__imp_load_D3D11CreateDevice`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a086`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x18000a105`

## pseudocode

```c
__int64 load_D3D11CreateDevice()
{
  return _tailMerge_d3d11_dll();
}

```

## disassembly

```asm
0x18000a105  lea     rax, __imp_D3D11CreateDevice
0x18000a10c  jmp     __tailMerge_d3d11_dll
```

# __imp_load_CreateDXGIFactory1

- ea: `0x180002028`
- end: `0x180002034`
- name: `__imp_load_CreateDXGIFactory1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001fa9`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x180002028`

## pseudocode

```c
__int64 load_CreateDXGIFactory1()
{
  return _tailMerge_dxgi_dll();
}

```

## disassembly

```asm
0x180002028  lea     rax, __imp_CreateDXGIFactory1
0x18000202f  jmp     __tailMerge_dxgi_dll
```

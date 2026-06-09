# _byteswap_ulong

- ea: `0x180078c32`
- end: `0x180078c38`
- name: `_byteswap_ulong`
- size: `6`
- prototype: `unsigned int __cdecl(unsigned int Number)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x18002dc50`
- `0x18002de20`
- `0x18002df90`
- `0x180030510`
- `0x180030624`
- `0x180030b7c`
- `0x180034110`
- `0x1800368a0`
- `0x180036b40`
- `0x180036c70`
- `0x180036f40`
- `0x18003c8a0`
- `0x18003ce10`
- `0x18004c910`
- `0x18004cbe0`
- `0x18004d3d8`
- `0x18004fc60`
- `0x18004fe60`
- `0x18004ff80`
- `0x180050130`
- `0x1800518e0`
- `0x180051940`
- `0x180078790`
- `0x180078940`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!_byteswap_ulong` at `0x180078c32`

## pseudocode

```c
// attributes: thunk
unsigned int __cdecl byteswap_ulong(unsigned int Number)
{
  return _byteswap_ulong(Number);
}

```

## disassembly

```asm
0x180078c32  jmp     cs:__imp__byteswap_ulong
```

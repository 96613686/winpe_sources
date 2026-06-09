# _byteswap_uint64

- ea: `0x180078be0`
- end: `0x180078be6`
- name: `_byteswap_uint64`
- size: `6`
- prototype: `unsigned __int64 __cdecl(unsigned __int64 Number)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18002a460`
- `0x18002a5d0`
- `0x18002f710`
- `0x18002f8f8`
- `0x18002fcc8`
- `0x1800357b8`
- `0x180035960`
- `0x18003ce10`
- `0x18003d990`
- `0x18003ea80`
- `0x18004fc60`
- `0x180050130`
- `0x1800504f8`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!_byteswap_uint64` at `0x180078be0`

## pseudocode

```c
// attributes: thunk
unsigned __int64 __cdecl byteswap_uint64(unsigned __int64 Number)
{
  return _byteswap_uint64(Number);
}

```

## disassembly

```asm
0x180078be0  jmp     cs:__imp__byteswap_uint64
```

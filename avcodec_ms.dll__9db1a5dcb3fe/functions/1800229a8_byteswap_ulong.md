# _byteswap_ulong

- ea: `0x1800229a8`
- end: `0x1800229ae`
- name: `_byteswap_ulong`
- size: `6`
- prototype: `unsigned int __cdecl(unsigned int Number)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x1800090a4`
- `0x18000ab54`
- `0x18000afb0`
- `0x18000c0fc`
- `0x180012b60`
- `0x180015020`
- `0x18001bd00`
- `0x18001c530`
- `0x18001cda8`
- `0x18001d3b8`
- `0x18001de28`
- `0x18001e3b0`
- `0x18001e9b4`
- `0x18001ec0c`
- `0x18001efc8`
- `0x18001f470`
- `0x18001fc38`
- `0x1800205d4`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!_byteswap_ulong` at `0x1800229a8`

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
0x1800229a8  jmp     cs:__imp__byteswap_ulong
```

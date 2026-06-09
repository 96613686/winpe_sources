# _byteswap_ulong

- ea: `0x18001bdf0`
- end: `0x18001bdf6`
- name: `_byteswap_ulong`
- size: `6`
- prototype: `unsigned int __cdecl(unsigned int Number)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005440`
- `0x18000f4c4`
- `0x180010818`
- `0x1800164c0`
- `0x180016590`
- `0x1800179a0`
- `0x180018c60`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!_byteswap_ulong` at `0x18001bdf0`

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
0x18001bdf0  jmp     cs:__imp__byteswap_ulong
```

# _invalid_parameter_noinfo

- ea: `0x1800020d0`
- end: `0x1800020d6`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006cbc`
- `0x18000824c`
- `0x1800083f0`
- `0x180008a38`
- `0x18000a150`
- `0x18000aa0c`
- `0x18000b080`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800020d0`

## pseudocode

```c
// attributes: thunk
void __cdecl invalid_parameter_noinfo()
{
  _invalid_parameter_noinfo();
}

```

## disassembly

```asm
0x1800020d0  jmp     cs:__imp__invalid_parameter_noinfo
```

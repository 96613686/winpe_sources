# _invalid_parameter_noinfo

- ea: `0x1800034fe`
- end: `0x180003504`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800073b8`
- `0x18000952c`
- `0x18000a708`
- `0x18000a8ac`
- `0x18000ae90`
- `0x18000c404`
- `0x18000c9e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800034fe`

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
0x1800034fe  jmp     cs:__imp__invalid_parameter_noinfo
```

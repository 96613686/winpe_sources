# _invalid_parameter_noinfo

- ea: `0x180002472`
- end: `0x180002478`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800042ec`
- `0x18000587c`
- `0x180005a1c`
- `0x180006060`
- `0x1800071a8`
- `0x180007a3c`
- `0x180007ed4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002472`

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
0x180002472  jmp     cs:__imp__invalid_parameter_noinfo
```

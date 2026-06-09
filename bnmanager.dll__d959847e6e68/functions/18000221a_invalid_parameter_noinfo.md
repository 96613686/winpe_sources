# _invalid_parameter_noinfo

- ea: `0x18000221a`
- end: `0x180002220`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000787c`
- `0x18000903c`
- `0x1800091e0`
- `0x180009828`
- `0x18000b1c8`
- `0x18000ba8c`
- `0x18000c398`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000221a`

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
0x18000221a  jmp     cs:__imp__invalid_parameter_noinfo
```

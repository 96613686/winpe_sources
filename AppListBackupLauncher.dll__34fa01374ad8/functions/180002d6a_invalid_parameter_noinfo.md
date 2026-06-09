# _invalid_parameter_noinfo

- ea: `0x180002d6a`
- end: `0x180002d70`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180007a1c`
- `0x18000a018`
- `0x18000a1bc`
- `0x18000a37c`
- `0x18000ac08`
- `0x18000d31c`
- `0x18000d524`
- `0x18000e714`
- `0x18000fbf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002d6a`

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
0x180002d6a  jmp     cs:__imp__invalid_parameter_noinfo
```

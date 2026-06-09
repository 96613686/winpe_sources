# _invalid_parameter_noinfo

- ea: `0x14000216a`
- end: `0x140002170`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140004730`
- `0x140005e58`
- `0x140005ffc`
- `0x140006848`
- `0x140007e64`
- `0x14000806c`
- `0x1400089fc`
- `0x140009088`
- `0x14000aa8c`
- `0x14000b2d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x14000216a`

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
0x14000216a  jmp     cs:__imp__invalid_parameter_noinfo
```

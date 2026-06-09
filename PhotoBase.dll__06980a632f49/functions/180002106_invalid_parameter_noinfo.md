# _invalid_parameter_noinfo

- ea: `0x180002106`
- end: `0x18000210c`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e70`
- `0x180003f30`
- `0x1800043dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002106`

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
0x180002106  jmp     cs:__imp__invalid_parameter_noinfo
```

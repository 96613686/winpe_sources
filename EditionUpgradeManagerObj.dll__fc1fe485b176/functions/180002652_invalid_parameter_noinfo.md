# _invalid_parameter_noinfo

- ea: `0x180002652`
- end: `0x180002658`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800048f0`
- `0x180005fe8`
- `0x180006188`
- `0x1800069b4`
- `0x180007a78`
- `0x180007c80`
- `0x1800085fc`
- `0x180008a94`
- `0x18000958c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002652`

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
0x180002652  jmp     cs:__imp__invalid_parameter_noinfo
```

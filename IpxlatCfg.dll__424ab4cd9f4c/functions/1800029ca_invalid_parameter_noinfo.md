# _invalid_parameter_noinfo

- ea: `0x1800029ca`
- end: `0x1800029d0`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18000565c`
- `0x180006d78`
- `0x180006f1c`
- `0x1800077a8`
- `0x180008f34`
- `0x18000913c`
- `0x180009acc`
- `0x18000a168`
- `0x18000aabc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800029ca`

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
0x1800029ca  jmp     cs:__imp__invalid_parameter_noinfo
```

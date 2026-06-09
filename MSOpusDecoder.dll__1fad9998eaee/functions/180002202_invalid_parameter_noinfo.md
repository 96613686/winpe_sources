# _invalid_parameter_noinfo

- ea: `0x180002202`
- end: `0x180002208`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ce80`
- `0x180021f9c`
- `0x1800222c4`
- `0x180022644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002202`

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
0x180002202  jmp     cs:__imp__invalid_parameter_noinfo
```

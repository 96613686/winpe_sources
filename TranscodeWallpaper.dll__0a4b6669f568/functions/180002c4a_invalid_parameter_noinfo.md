# _invalid_parameter_noinfo

- ea: `0x180002c4a`
- end: `0x180002c50`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006fa4`
- `0x18000870c`
- `0x180008c40`
- `0x180008de4`
- `0x1800093bc`
- `0x18000a454`
- `0x18000a924`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002c4a`

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
0x180002c4a  jmp     cs:__imp__invalid_parameter_noinfo
```

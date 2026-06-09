# _invalid_parameter_noinfo

- ea: `0x180001f8a`
- end: `0x180001f90`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180005918`
- `0x18000614c`
- `0x180006590`
- `0x180007270`
- `0x180007300`
- `0x18000a9d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180001f8a`

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
0x180001f8a  jmp     cs:__imp__invalid_parameter_noinfo
```

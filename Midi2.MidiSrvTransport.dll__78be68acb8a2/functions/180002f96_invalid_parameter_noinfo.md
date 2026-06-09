# _invalid_parameter_noinfo

- ea: `0x180002f96`
- end: `0x180002f9c`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008bf4`
- `0x180009228`
- `0x18001162c`
- `0x1800116f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002f96`

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
0x180002f96  jmp     cs:__imp__invalid_parameter_noinfo
```

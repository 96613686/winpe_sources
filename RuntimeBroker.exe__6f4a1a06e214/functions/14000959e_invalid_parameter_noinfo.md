# _invalid_parameter_noinfo

- ea: `0x14000959e`
- end: `0x1400095a4`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140003950`
- `0x140003bb8`
- `0x140003d20`
- `0x140003e30`
- `0x14000417c`
- `0x1400044e8`
- `0x140006030`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x14000959e`

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
0x14000959e  jmp     cs:__imp__invalid_parameter_noinfo
```

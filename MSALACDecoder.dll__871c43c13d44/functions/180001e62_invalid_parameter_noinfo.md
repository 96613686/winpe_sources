# _invalid_parameter_noinfo

- ea: `0x180001e62`
- end: `0x180001e68`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023b0`
- `0x180006bcc`
- `0x180006ef4`
- `0x180007274`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180001e62`

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
0x180001e62  jmp     cs:__imp__invalid_parameter_noinfo
```

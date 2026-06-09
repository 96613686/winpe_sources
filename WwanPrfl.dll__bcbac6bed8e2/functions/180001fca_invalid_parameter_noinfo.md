# _invalid_parameter_noinfo

- ea: `0x180001fca`
- end: `0x180001fd0`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800047c0`
- `0x1800060a8`
- `0x18000624c`
- `0x180006408`
- `0x180006c48`
- `0x1800084e4`
- `0x1800086ec`
- `0x18000907c`
- `0x18000e674`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180001fca`

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
0x180001fca  jmp     cs:__imp__invalid_parameter_noinfo
```

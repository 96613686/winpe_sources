# _invalid_parameter_noinfo

- ea: `0x1800040f6`
- end: `0x1800040fc`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180009cf4`
- `0x18000a328`
- `0x1800104c0`
- `0x180010588`
- `0x180011d2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800040f6`

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
0x1800040f6  jmp     cs:__imp__invalid_parameter_noinfo
```

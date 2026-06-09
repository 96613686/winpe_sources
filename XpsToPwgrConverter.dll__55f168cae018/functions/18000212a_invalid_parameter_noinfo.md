# _invalid_parameter_noinfo

- ea: `0x18000212a`
- end: `0x180002130`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000440c`
- `0x18000599c`
- `0x180005b40`
- `0x1800061c8`
- `0x180007a30`
- `0x18000830c`
- `0x180008998`
- `0x18000a88c`
- `0x18000cddc`
- `0x18000d0e4`
- `0x18000e7a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000212a`

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
0x18000212a  jmp     cs:__imp__invalid_parameter_noinfo
```

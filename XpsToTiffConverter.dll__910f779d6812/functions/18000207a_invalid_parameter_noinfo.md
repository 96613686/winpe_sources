# _invalid_parameter_noinfo

- ea: `0x18000207a`
- end: `0x180002080`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800046ac`
- `0x180005c3c`
- `0x180005de0`
- `0x180006468`
- `0x180007d40`
- `0x18000861c`
- `0x180008f08`
- `0x18000c690`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000207a`

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
0x18000207a  jmp     cs:__imp__invalid_parameter_noinfo
```

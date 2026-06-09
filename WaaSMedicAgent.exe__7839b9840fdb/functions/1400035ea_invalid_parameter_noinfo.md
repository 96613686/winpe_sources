# _invalid_parameter_noinfo

- ea: `0x1400035ea`
- end: `0x1400035f0`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140007618`
- `0x14000a7d4`
- `0x14000cbdc`
- `0x14000d158`
- `0x14000d308`
- `0x14000d8f0`
- `0x14000e3d0`
- `0x14000e8a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1400035ea`

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
0x1400035ea  jmp     cs:__imp__invalid_parameter_noinfo
```

# _invalid_parameter_noinfo

- ea: `0x14000903a`
- end: `0x140009040`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14000d608`
- `0x1400141bc`
- `0x1400146e0`
- `0x140014884`
- `0x140014e5c`
- `0x140015c8c`
- `0x140016154`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x14000903a`

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
0x14000903a  jmp     cs:__imp__invalid_parameter_noinfo
```

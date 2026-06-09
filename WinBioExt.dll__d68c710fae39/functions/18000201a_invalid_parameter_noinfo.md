# _invalid_parameter_noinfo

- ea: `0x18000201a`
- end: `0x180002020`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005d78`
- `0x180007d90`
- `0x180008184`
- `0x180008328`
- `0x18000890c`
- `0x180009478`
- `0x180009944`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000201a`

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
0x18000201a  jmp     cs:__imp__invalid_parameter_noinfo
```

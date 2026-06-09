# _invalid_parameter_noinfo

- ea: `0x1400020b2`
- end: `0x1400020b8`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140004ba8`
- `0x140007ed0`
- `0x140008074`
- `0x140008234`
- `0x140008a78`
- `0x14000a88c`
- `0x14000aa94`
- `0x14000b42c`
- `0x14000c1a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1400020b2`

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
0x1400020b2  jmp     cs:__imp__invalid_parameter_noinfo
```

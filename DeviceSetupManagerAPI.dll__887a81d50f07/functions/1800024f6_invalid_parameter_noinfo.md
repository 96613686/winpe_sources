# _invalid_parameter_noinfo

- ea: `0x1800024f6`
- end: `0x1800024fc`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800047ec`
- `0x180005d7c`
- `0x180005f20`
- `0x180006568`
- `0x180007c80`
- `0x18000853c`
- `0x180008bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800024f6`

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
0x1800024f6  jmp     cs:__imp__invalid_parameter_noinfo
```

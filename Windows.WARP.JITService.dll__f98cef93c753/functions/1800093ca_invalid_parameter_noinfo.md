# _invalid_parameter_noinfo

- ea: `0x1800093ca`
- end: `0x1800093d0`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001224`
- `0x1800042fc`
- `0x1800043ec`
- `0x180004888`
- `0x1800054f0`
- `0x180006050`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800093ca`

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
0x1800093ca  jmp     cs:__imp__invalid_parameter_noinfo
```

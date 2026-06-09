# _o__invalid_parameter_noinfo

- ea: `0x1800030d2`
- end: `0x1800030d8`
- name: `_o__invalid_parameter_noinfo`
- size: `6`
- prototype: `__int64()`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x18000be4c`
- `0x18001e870`
- `0x180028790`
- `0x180029a80`
- `0x18002c540`
- `0x180031e64`
- `0x1800323e8`
- `0x180032658`
- `0x180034aa4`
- `0x18003a024`
- `0x1800400a8`
- `0x180040760`
- `0x1800434b8`
- `0x180058ed0`
- `0x180059f40`
- `0x18005a26c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800030d2`

## pseudocode

```c
// attributes: thunk
__int64 o__invalid_parameter_noinfo()
{
  return _o__invalid_parameter_noinfo();
}

```

## disassembly

```asm
0x1800030d2  jmp     cs:__imp__o__invalid_parameter_noinfo
```

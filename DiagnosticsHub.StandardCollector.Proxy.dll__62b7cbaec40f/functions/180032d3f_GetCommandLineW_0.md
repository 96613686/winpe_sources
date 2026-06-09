# GetCommandLineW_0

- ea: `0x180032d3f`
- end: `0x180032d45`
- name: `GetCommandLineW_0`
- size: `6`
- prototype: `LPWSTR __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x180032d3f`

## pseudocode

```c
// attributes: thunk
LPWSTR __stdcall GetCommandLineW_0()
{
  return GetCommandLineW();
}

```

## disassembly

```asm
0x180032d3f  jmp     cs:__imp_GetCommandLineW
```

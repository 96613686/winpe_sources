# GetCommandLineA_0

- ea: `0x180032d39`
- end: `0x180032d3f`
- name: `GetCommandLineA_0`
- size: `6`
- prototype: `LPSTR __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x180032d39`

## pseudocode

```c
// attributes: thunk
LPSTR __stdcall GetCommandLineA_0()
{
  return GetCommandLineA();
}

```

## disassembly

```asm
0x180032d39  jmp     cs:__imp_GetCommandLineA
```

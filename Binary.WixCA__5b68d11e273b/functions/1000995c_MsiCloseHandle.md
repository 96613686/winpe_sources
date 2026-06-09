# MsiCloseHandle

- ea: `0x1000995c`
- end: `0x10009962`
- name: `MsiCloseHandle`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hAny)`
- caller_count: `22`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x100012eb`
- `0x100015c4`
- `0x100020f7`
- `0x100034ad`
- `0x10003b7b`
- `0x10003e9c`
- `0x100044d9`
- `0x10004da5`
- `0x10005139`
- `0x10006208`
- `0x1000660f`
- `0x1000722e`
- `0x100086c2`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000dba2`
- `0x1000e13e`
- `0x1000e439`
- `0x1000e78c`
- `0x1000ee5c`
- `0x1000f18d`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x1000995c`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiCloseHandle(MSIHANDLE hAny)
{
  return __imp_MsiCloseHandle(hAny);
}

```

## disassembly

```asm
0x1000995c  jmp     ds:__imp_MsiCloseHandle
```

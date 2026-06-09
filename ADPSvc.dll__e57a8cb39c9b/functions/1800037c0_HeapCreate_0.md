# HeapCreate_0

- ea: `0x1800037c0`
- end: `0x1800037c6`
- name: `HeapCreate_0`
- size: `6`
- prototype: `HANDLE __stdcall(DWORD flOptions, SIZE_T dwInitialSize, SIZE_T dwMaximumSize)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800037c0`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall HeapCreate_0(DWORD flOptions, SIZE_T dwInitialSize, SIZE_T dwMaximumSize)
{
  return HeapCreate(flOptions, dwInitialSize, dwMaximumSize);
}

```

## disassembly

```asm
0x1800037c0  jmp     cs:__imp_HeapCreate
```

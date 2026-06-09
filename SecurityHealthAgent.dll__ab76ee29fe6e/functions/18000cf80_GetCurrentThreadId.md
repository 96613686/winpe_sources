# GetCurrentThreadId

- ea: `0x18000cf80`
- end: `0x18000cf87`
- name: `GetCurrentThreadId`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18002c860`
- `0x18002da60`
- `0x180096b08`
- `0x1800977a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000cf80`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetCurrentThreadId()
{
  return __imp_GetCurrentThreadId();
}

```

## disassembly

```asm
0x18000cf80  jmp     cs:__imp_GetCurrentThreadId
```

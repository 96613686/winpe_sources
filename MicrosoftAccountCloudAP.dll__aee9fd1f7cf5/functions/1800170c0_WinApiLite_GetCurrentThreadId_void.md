# WinApiLite::GetCurrentThreadId(void)

- ea: `0x1800170c0`
- end: `0x1800170c7`
- name: `?GetCurrentThreadId@WinApiLite@@UEAAKXZ`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170c0`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall WinApiLite::GetCurrentThreadId()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x1800170c0  jmp     cs:__imp_GetCurrentThreadId
```

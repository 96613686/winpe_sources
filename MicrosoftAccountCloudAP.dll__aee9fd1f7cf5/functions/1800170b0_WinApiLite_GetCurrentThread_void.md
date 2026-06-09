# WinApiLite::GetCurrentThread(void)

- ea: `0x1800170b0`
- end: `0x1800170b7`
- name: `?GetCurrentThread@WinApiLite@@UEAAPEAXXZ`
- size: `7`
- prototype: `HANDLE __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800170b0`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WinApiLite::GetCurrentThread()
{
  return GetCurrentThread();
}

```

## disassembly

```asm
0x1800170b0  jmp     cs:__imp_GetCurrentThread
```

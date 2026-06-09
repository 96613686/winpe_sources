# CSmallSpinLock::_CurrentThreadId(void)

- ea: `0x180005070`
- end: `0x180005077`
- name: `?_CurrentThreadId@CSmallSpinLock@@CAJXZ`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005070`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall CSmallSpinLock::_CurrentThreadId()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x180005070  jmp     cs:__imp_GetCurrentThreadId
```

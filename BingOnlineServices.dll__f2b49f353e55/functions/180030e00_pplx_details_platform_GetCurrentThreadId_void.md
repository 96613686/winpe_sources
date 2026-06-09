# pplx::details::platform::GetCurrentThreadId(void)

- ea: `0x180030e00`
- end: `0x180030e07`
- name: `?GetCurrentThreadId@platform@details@pplx@@YAJXZ`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030e00`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall pplx::details::platform::GetCurrentThreadId()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x180030e00  jmp     cs:__imp_GetCurrentThreadId
```

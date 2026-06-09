# Concurrency::details::platform::GetCurrentThreadId(void)

- ea: `0x18030a200`
- end: `0x18030a207`
- name: `?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800dd910`
- `0x18031c44c`
- `0x18031c7fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18030a200`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall Concurrency::details::platform::GetCurrentThreadId()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x18030a200  jmp     cs:__imp_GetCurrentThreadId
```

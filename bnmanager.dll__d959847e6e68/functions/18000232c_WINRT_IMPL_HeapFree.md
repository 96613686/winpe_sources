# WINRT_IMPL_HeapFree

- ea: `0x18000232c`
- end: `0x180002332`
- name: `WINRT_IMPL_HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ae8`
- `0x1800057fc`
- `0x180007250`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000232c`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WINRT_IMPL_HeapFree(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)
{
  return HeapFree(hHeap, dwFlags, lpMem);
}

```

## disassembly

```asm
0x18000232c  jmp     cs:__imp_HeapFree
```

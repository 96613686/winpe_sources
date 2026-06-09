# WINRT_IMPL_HeapFree

- ea: `0x180002150`
- end: `0x180002156`
- name: `WINRT_IMPL_HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008934`
- `0x1800096f0`
- `0x18000d05c`
- `0x18000d32c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002150`

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
0x180002150  jmp     cs:__imp_HeapFree
```

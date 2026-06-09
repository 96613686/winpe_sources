# WINRT_IMPL_HeapFree

- ea: `0x18000204c`
- end: `0x180002052`
- name: `WINRT_IMPL_HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000614c`
- `0x180007438`
- `0x180008124`
- `0x180008190`
- `0x18000bb6e`
- `0x18000bc67`
- `0x18000bd60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000204c`

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
0x18000204c  jmp     cs:__imp_HeapFree
```

# WINRT_IMPL_HeapFree

- ea: `0x180003ab0`
- end: `0x180003ab6`
- name: `WINRT_IMPL_HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c974`
- `0x18000d038`
- `0x18000d450`
- `0x18000d4d4`
- `0x18000e220`
- `0x18000e950`
- `0x18000f9dc`
- `0x180010e7c`
- `0x180012791`
- `0x180012895`
- `0x180012999`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ab0`

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
0x180003ab0  jmp     cs:__imp_HeapFree
```

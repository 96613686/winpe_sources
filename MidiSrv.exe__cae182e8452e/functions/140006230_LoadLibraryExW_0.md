# LoadLibraryExW_0

- ea: `0x140006230`
- end: `0x140006236`
- name: `LoadLibraryExW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140013170`
- `0x1400226e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006230`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryExW_0(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)
{
  return LoadLibraryExW(lpLibFileName, hFile, dwFlags);
}

```

## disassembly

```asm
0x140006230  jmp     cs:__imp_LoadLibraryExW
```

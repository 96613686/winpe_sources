# LoadLibraryExW

- ea: `0x18001d0c5`
- end: `0x18001d0cb`
- name: `LoadLibraryExW`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000e9b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d0c5`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryExW(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)
{
  return __imp_LoadLibraryExW(lpLibFileName, hFile, dwFlags);
}

```

## disassembly

```asm
0x18001d0c5  jmp     cs:__imp_LoadLibraryExW
```

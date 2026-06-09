# LoadLibraryExW_0

- ea: `0x180005398`
- end: `0x18000539e`
- name: `LoadLibraryExW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000fb5c`
- `0x1800219cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005398`

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
0x180005398  jmp     cs:__imp_LoadLibraryExW
```

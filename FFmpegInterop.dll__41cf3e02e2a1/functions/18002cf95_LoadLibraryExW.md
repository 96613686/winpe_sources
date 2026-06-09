# LoadLibraryExW

- ea: `0x18002cf95`
- end: `0x18002cf9b`
- name: `LoadLibraryExW`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006950`
- `0x18000c400`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002cf95`

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
0x18002cf95  jmp     cs:__imp_LoadLibraryExW
```

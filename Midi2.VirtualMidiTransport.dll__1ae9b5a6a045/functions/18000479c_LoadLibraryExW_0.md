# LoadLibraryExW_0

- ea: `0x18000479c`
- end: `0x1800047a2`
- name: `LoadLibraryExW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800130d0`
- `0x18001c494`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000479c`

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
0x18000479c  jmp     cs:__imp_LoadLibraryExW
```

# LoadLibraryExW_0

- ea: `0x180030acd`
- end: `0x180030ad3`
- name: `LoadLibraryExW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180013ed0`
- `0x180014870`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180030acd`

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
0x180030acd  jmp     cs:__imp_LoadLibraryExW
```

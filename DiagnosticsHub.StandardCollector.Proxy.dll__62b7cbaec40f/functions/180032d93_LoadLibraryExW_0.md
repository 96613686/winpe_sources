# LoadLibraryExW_0

- ea: `0x180032d93`
- end: `0x180032d99`
- name: `LoadLibraryExW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180032d93`

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
0x180032d93  jmp     cs:__imp_LoadLibraryExW
```

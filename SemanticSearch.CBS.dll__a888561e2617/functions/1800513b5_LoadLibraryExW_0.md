# LoadLibraryExW_0

- ea: `0x1800513b5`
- end: `0x1800513bb`
- name: `LoadLibraryExW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007a00`
- `0x180008ac0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800513b5`

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
0x1800513b5  jmp     cs:__imp_LoadLibraryExW
```

# LoadLibraryW_0

- ea: `0x180069390`
- end: `0x180069396`
- name: `LoadLibraryW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180069390`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryW_0(LPCWSTR lpLibFileName)
{
  return LoadLibraryW(lpLibFileName);
}

```

## disassembly

```asm
0x180069390  jmp     cs:__imp_LoadLibraryW
```

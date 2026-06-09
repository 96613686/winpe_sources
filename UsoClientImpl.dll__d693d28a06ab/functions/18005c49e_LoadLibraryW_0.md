# LoadLibraryW_0

- ea: `0x18005c49e`
- end: `0x18005c4a4`
- name: `LoadLibraryW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001a39c`
- `0x18002d6a4`
- `0x1800356d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005c49e`

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
0x18005c49e  jmp     cs:__imp_LoadLibraryW
```

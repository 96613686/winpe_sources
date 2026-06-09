# LoadLibraryA_0

- ea: `0x180003940`
- end: `0x180003946`
- name: `LoadLibraryA_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCSTR lpLibFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180003940`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryA_0(LPCSTR lpLibFileName)
{
  return LoadLibraryA(lpLibFileName);
}

```

## disassembly

```asm
0x180003940  jmp     cs:__imp_LoadLibraryA
```

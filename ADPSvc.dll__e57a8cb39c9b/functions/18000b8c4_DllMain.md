# DllMain

- ea: `0x18000b8c4`
- end: `0x18000b8dd`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800020c4`

## callees

- `0x18000b8c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b8cd`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b8cd`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
    DisableThreadLibraryCalls(hinstDLL);
  return 1;
}

```

## disassembly

```asm
0x18000b8c4  sub     rsp, 28h
0x18000b8c8  cmp     edx, 1
0x18000b8cb  jnz     short loc_18000B8D3
0x18000b8cd  call    cs:__imp_DisableThreadLibraryCalls
0x18000b8d3  mov     eax, 1
0x18000b8d8  add     rsp, 28h
0x18000b8dc  retn
```

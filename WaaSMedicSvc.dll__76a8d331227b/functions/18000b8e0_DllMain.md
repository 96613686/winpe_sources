# DllMain

- ea: `0x18000b8e0`
- end: `0x18000b8f9`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002074`

## callees

- `0x18000b8e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b8e9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b8e9`

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
0x18000b8e0  sub     rsp, 28h
0x18000b8e4  cmp     edx, 1
0x18000b8e7  jnz     short loc_18000B8EF
0x18000b8e9  call    cs:__imp_DisableThreadLibraryCalls
0x18000b8ef  mov     eax, 1
0x18000b8f4  add     rsp, 28h
0x18000b8f8  retn
```

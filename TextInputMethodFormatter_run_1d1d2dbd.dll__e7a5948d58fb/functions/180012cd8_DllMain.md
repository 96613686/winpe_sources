# DllMain

- ea: `0x180012cd8`
- end: `0x180012cf1`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800020b4`

## callees

- `0x180012cd8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012ce1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012ce1`

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
0x180012cd8  sub     rsp, 28h
0x180012cdc  cmp     edx, 1
0x180012cdf  jnz     short loc_180012CE7
0x180012ce1  call    cs:__imp_DisableThreadLibraryCalls
0x180012ce7  mov     eax, 1
0x180012cec  add     rsp, 28h
0x180012cf0  retn
```

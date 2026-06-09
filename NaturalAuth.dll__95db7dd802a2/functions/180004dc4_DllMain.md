# DllMain

- ea: `0x180004dc4`
- end: `0x180004de7`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003fe4`

## callees

- `0x180004dc4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004dd7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004dd7`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 && !pRawDllMain )
    DisableThreadLibraryCalls(hinstDLL);
  return 1;
}

```

## disassembly

```asm
0x180004dc4  sub     rsp, 28h
0x180004dc8  cmp     edx, 1
0x180004dcb  jnz     short loc_180004DDD
0x180004dcd  cmp     cs:_pRawDllMain, 0
0x180004dd5  jnz     short loc_180004DDD
0x180004dd7  call    cs:__imp_DisableThreadLibraryCalls
0x180004ddd  mov     eax, 1
0x180004de2  add     rsp, 28h
0x180004de6  retn
```

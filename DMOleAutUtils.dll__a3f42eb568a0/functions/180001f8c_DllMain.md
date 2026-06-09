# DllMain

- ea: `0x180001f8c`
- end: `0x180001fa5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001f8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001f95`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001f95`

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
0x180001f8c  sub     rsp, 28h
0x180001f90  cmp     edx, 1
0x180001f93  jnz     short loc_180001F9B
0x180001f95  call    cs:__imp_DisableThreadLibraryCalls
0x180001f9b  mov     eax, 1
0x180001fa0  add     rsp, 28h
0x180001fa4  retn
```

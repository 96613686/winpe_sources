# DllMain

- ea: `0x180007fac`
- end: `0x180007fc5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002fc4`

## callees

- `0x180007fac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007fb5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007fb5`

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
0x180007fac  sub     rsp, 28h
0x180007fb0  cmp     edx, 1
0x180007fb3  jnz     short loc_180007FBB
0x180007fb5  call    cs:__imp_DisableThreadLibraryCalls
0x180007fbb  mov     eax, 1
0x180007fc0  add     rsp, 28h
0x180007fc4  retn
```

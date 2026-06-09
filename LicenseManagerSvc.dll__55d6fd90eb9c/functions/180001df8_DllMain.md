# DllMain

- ea: `0x180001df8`
- end: `0x180001e11`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003244`

## callees

- `0x180001df8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001e01`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001e01`

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
0x180001df8  sub     rsp, 28h
0x180001dfc  cmp     edx, 1
0x180001dff  jnz     short loc_180001E07
0x180001e01  call    cs:__imp_DisableThreadLibraryCalls
0x180001e07  mov     eax, 1
0x180001e0c  add     rsp, 28h
0x180001e10  retn
```

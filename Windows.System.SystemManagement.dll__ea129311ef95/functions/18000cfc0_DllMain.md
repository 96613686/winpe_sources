# DllMain

- ea: `0x18000cfc0`
- end: `0x18000cfd9`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002c34`

## callees

- `0x18000cfc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000cfc9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000cfc9`

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
0x18000cfc0  sub     rsp, 28h
0x18000cfc4  cmp     edx, 1
0x18000cfc7  jnz     short loc_18000CFCF
0x18000cfc9  call    cs:__imp_DisableThreadLibraryCalls
0x18000cfcf  mov     eax, 1
0x18000cfd4  add     rsp, 28h
0x18000cfd8  retn
```

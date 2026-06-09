# DllMain

- ea: `0x18000fa1c`
- end: `0x18000fa35`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002174`

## callees

- `0x18000fa1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000fa25`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000fa25`

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
0x18000fa1c  sub     rsp, 28h
0x18000fa20  cmp     edx, 1
0x18000fa23  jnz     short loc_18000FA2B
0x18000fa25  call    cs:__imp_DisableThreadLibraryCalls
0x18000fa2b  mov     eax, 1
0x18000fa30  add     rsp, 28h
0x18000fa34  retn
```

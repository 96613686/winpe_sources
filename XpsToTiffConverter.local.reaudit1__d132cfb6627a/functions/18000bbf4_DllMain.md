# DllMain

- ea: `0x18000bbf4`
- end: `0x18000bc0d`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001514`

## callees

- `0x18000bbf4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bbfd`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bbfd`

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
0x18000bbf4  sub     rsp, 28h
0x18000bbf8  cmp     edx, 1
0x18000bbfb  jnz     short loc_18000BC03
0x18000bbfd  call    cs:__imp_DisableThreadLibraryCalls
0x18000bc03  mov     eax, 1
0x18000bc08  add     rsp, 28h
0x18000bc0c  retn
```

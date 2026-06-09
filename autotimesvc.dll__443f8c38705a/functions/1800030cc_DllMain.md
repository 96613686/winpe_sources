# DllMain

- ea: `0x1800030cc`
- end: `0x1800030ef`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800028e4`

## callees

- `0x1800030cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800030df`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800030df`

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
0x1800030cc  sub     rsp, 28h
0x1800030d0  cmp     edx, 1
0x1800030d3  jnz     short loc_1800030E5
0x1800030d5  cmp     cs:_pRawDllMain, 0
0x1800030dd  jnz     short loc_1800030E5
0x1800030df  call    cs:__imp_DisableThreadLibraryCalls
0x1800030e5  mov     eax, 1
0x1800030ea  add     rsp, 28h
0x1800030ee  retn
```

# DllMain

- ea: `0x1800024dc`
- end: `0x1800024ff`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001bb4`

## callees

- `0x1800024dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800024ef`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800024ef`

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
0x1800024dc  sub     rsp, 28h
0x1800024e0  cmp     edx, 1
0x1800024e3  jnz     short loc_1800024F5
0x1800024e5  cmp     cs:_pRawDllMain, 0
0x1800024ed  jnz     short loc_1800024F5
0x1800024ef  call    cs:__imp_DisableThreadLibraryCalls
0x1800024f5  mov     eax, 1
0x1800024fa  add     rsp, 28h
0x1800024fe  retn
```

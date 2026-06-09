# DllMain

- ea: `0x180002eb0`
- end: `0x180002ed3`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002764`

## callees

- `0x180002eb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ec3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ec3`

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
0x180002eb0  sub     rsp, 28h
0x180002eb4  cmp     edx, 1
0x180002eb7  jnz     short loc_180002EC9
0x180002eb9  cmp     cs:_pRawDllMain, 0
0x180002ec1  jnz     short loc_180002EC9
0x180002ec3  call    cs:__imp_DisableThreadLibraryCalls
0x180002ec9  mov     eax, 1
0x180002ece  add     rsp, 28h
0x180002ed2  retn
```

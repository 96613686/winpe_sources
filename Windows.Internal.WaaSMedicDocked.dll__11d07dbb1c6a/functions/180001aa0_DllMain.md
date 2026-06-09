# DllMain

- ea: `0x180001aa0`
- end: `0x180001ac3`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800013e4`

## callees

- `0x180001aa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001ab3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001ab3`

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
0x180001aa0  sub     rsp, 28h
0x180001aa4  cmp     edx, 1
0x180001aa7  jnz     short loc_180001AB9
0x180001aa9  cmp     cs:_pRawDllMain, 0
0x180001ab1  jnz     short loc_180001AB9
0x180001ab3  call    cs:__imp_DisableThreadLibraryCalls
0x180001ab9  mov     eax, 1
0x180001abe  add     rsp, 28h
0x180001ac2  retn
```

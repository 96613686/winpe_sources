# DllMain

- ea: `0x180001b4c`
- end: `0x180001b6f`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800014d4`

## callees

- `0x180001b4c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001b5f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001b5f`

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
0x180001b4c  sub     rsp, 28h
0x180001b50  cmp     edx, 1
0x180001b53  jnz     short loc_180001B65
0x180001b55  cmp     cs:_pRawDllMain, 0
0x180001b5d  jnz     short loc_180001B65
0x180001b5f  call    cs:__imp_DisableThreadLibraryCalls
0x180001b65  mov     eax, 1
0x180001b6a  add     rsp, 28h
0x180001b6e  retn
```

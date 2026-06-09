# DllMain

- ea: `0x18001e51c`
- end: `0x18001e53f`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001e294`

## callees

- `0x18001e51c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001e52f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001e52f`

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
0x18001e51c  sub     rsp, 28h
0x18001e520  cmp     edx, 1
0x18001e523  jnz     short loc_18001E535
0x18001e525  cmp     cs:_pRawDllMain, 0
0x18001e52d  jnz     short loc_18001E535
0x18001e52f  call    cs:__imp_DisableThreadLibraryCalls
0x18001e535  mov     eax, 1
0x18001e53a  add     rsp, 28h
0x18001e53e  retn
```

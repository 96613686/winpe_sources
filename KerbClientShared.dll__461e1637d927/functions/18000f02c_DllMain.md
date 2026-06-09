# DllMain

- ea: `0x18000f02c`
- end: `0x18000f04f`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e9e4`

## callees

- `0x18000f02c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f03f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f03f`

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
0x18000f02c  sub     rsp, 28h
0x18000f030  cmp     edx, 1
0x18000f033  jnz     short loc_18000F045
0x18000f035  cmp     cs:_pRawDllMain, 0
0x18000f03d  jnz     short loc_18000F045
0x18000f03f  call    cs:__imp_DisableThreadLibraryCalls
0x18000f045  mov     eax, 1
0x18000f04a  add     rsp, 28h
0x18000f04e  retn
```

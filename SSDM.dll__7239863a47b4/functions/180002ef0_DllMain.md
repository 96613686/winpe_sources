# DllMain

- ea: `0x180002ef0`
- end: `0x180002f09`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800022b4`

## callees

- `0x180002ef0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ef9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ef9`

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
0x180002ef0  sub     rsp, 28h
0x180002ef4  cmp     edx, 1
0x180002ef7  jnz     short loc_180002EFF
0x180002ef9  call    cs:__imp_DisableThreadLibraryCalls
0x180002eff  mov     eax, 1
0x180002f04  add     rsp, 28h
0x180002f08  retn
```

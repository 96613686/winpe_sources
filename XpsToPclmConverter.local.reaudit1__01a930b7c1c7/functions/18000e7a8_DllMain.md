# DllMain

- ea: `0x18000e7a8`
- end: `0x18000e7c1`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001464`

## callees

- `0x18000e7a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000e7b1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000e7b1`

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
0x18000e7a8  sub     rsp, 28h
0x18000e7ac  cmp     edx, 1
0x18000e7af  jnz     short loc_18000E7B7
0x18000e7b1  call    cs:__imp_DisableThreadLibraryCalls
0x18000e7b7  mov     eax, 1
0x18000e7bc  add     rsp, 28h
0x18000e7c0  retn
```

# DllMain

- ea: `0x18000b0ac`
- end: `0x18000b0c5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001f34`

## callees

- `0x18000b0ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b0b5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b0b5`

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
0x18000b0ac  sub     rsp, 28h
0x18000b0b0  cmp     edx, 1
0x18000b0b3  jnz     short loc_18000B0BB
0x18000b0b5  call    cs:__imp_DisableThreadLibraryCalls
0x18000b0bb  mov     eax, 1
0x18000b0c0  add     rsp, 28h
0x18000b0c4  retn
```

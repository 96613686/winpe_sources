# DllMain

- ea: `0x18000c56c`
- end: `0x18000c585`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x18000c56c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c575`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c575`

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
0x18000c56c  sub     rsp, 28h
0x18000c570  cmp     edx, 1
0x18000c573  jnz     short loc_18000C57B
0x18000c575  call    cs:__imp_DisableThreadLibraryCalls
0x18000c57b  mov     eax, 1
0x18000c580  add     rsp, 28h
0x18000c584  retn
```

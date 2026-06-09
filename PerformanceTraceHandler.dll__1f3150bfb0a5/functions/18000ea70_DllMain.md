# DllMain

- ea: `0x18000ea70`
- end: `0x18000ea89`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002a74`

## callees

- `0x18000ea70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ea79`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ea79`

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
0x18000ea70  sub     rsp, 28h
0x18000ea74  cmp     edx, 1
0x18000ea77  jnz     short loc_18000EA7F
0x18000ea79  call    cs:__imp_DisableThreadLibraryCalls
0x18000ea7f  mov     eax, 1
0x18000ea84  add     rsp, 28h
0x18000ea88  retn
```

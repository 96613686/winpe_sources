# DllMain

- ea: `0x1800032fc`
- end: `0x180003315`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004ae4`

## callees

- `0x1800032fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180003305`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180003305`

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
0x1800032fc  sub     rsp, 28h
0x180003300  cmp     edx, 1
0x180003303  jnz     short loc_18000330B
0x180003305  call    cs:__imp_DisableThreadLibraryCalls
0x18000330b  mov     eax, 1
0x180003310  add     rsp, 28h
0x180003314  retn
```

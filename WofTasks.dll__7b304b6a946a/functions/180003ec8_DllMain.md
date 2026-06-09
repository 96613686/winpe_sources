# DllMain

- ea: `0x180003ec8`
- end: `0x180003ee1`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001314`

## callees

- `0x180003ec8`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180003ed1`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180003ed1`

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
0x180003ec8  sub     rsp, 28h
0x180003ecc  cmp     edx, 1
0x180003ecf  jnz     short loc_180003ED7
0x180003ed1  call    cs:__imp_DisableThreadLibraryCalls
0x180003ed7  mov     eax, 1
0x180003edc  add     rsp, 28h
0x180003ee0  retn
```

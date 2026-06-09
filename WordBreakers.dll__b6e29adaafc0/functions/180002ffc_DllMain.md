# DllMain

- ea: `0x180002ffc`
- end: `0x180003022`
- name: `DllMain`
- size: `38`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800023d4`

## callees

- `0x180002ffc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000300a`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000300a`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    g_hInstDll = hinstDLL;
  }
  return 1;
}

```

## disassembly

```asm
0x180002ffc  push    rbx
0x180002ffe  sub     rsp, 20h
0x180003002  mov     rbx, rcx
0x180003005  cmp     edx, 1
0x180003008  jnz     short loc_180003017
0x18000300a  call    cs:__imp_DisableThreadLibraryCalls
0x180003010  mov     cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstDll
0x180003017  mov     eax, 1
0x18000301c  add     rsp, 20h
0x180003020  pop     rbx
0x180003021  retn
```

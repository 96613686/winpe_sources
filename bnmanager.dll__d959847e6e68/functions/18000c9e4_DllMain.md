# DllMain

- ea: `0x18000c9e4`
- end: `0x18000ca04`
- name: `DllMain`
- size: `32`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001634`

## callees

- `0x18000c9e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c9f4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c9f4`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    g_hInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18000c9e4  sub     rsp, 28h
0x18000c9e8  cmp     edx, 1
0x18000c9eb  jnz     short loc_18000C9FA
0x18000c9ed  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x18000c9f4  call    cs:__imp_DisableThreadLibraryCalls
0x18000c9fa  mov     eax, 1
0x18000c9ff  add     rsp, 28h
0x18000ca03  retn
```

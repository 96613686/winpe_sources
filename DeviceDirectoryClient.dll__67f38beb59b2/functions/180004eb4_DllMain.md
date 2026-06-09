# DllMain

- ea: `0x180004eb4`
- end: `0x180004edd`
- name: `DllMain`
- size: `41`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002324`

## callees

- `0x180001008`
- `0x1800010b8`
- `0x180004eb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004ec1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004ec1`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x180004eb4  sub     rsp, 28h
0x180004eb8  test    edx, edx
0x180004eba  jz      short loc_180004ECE
0x180004ebc  cmp     edx, 1
0x180004ebf  jnz     short loc_180004ED3
0x180004ec1  call    cs:__imp_DisableThreadLibraryCalls
0x180004ec7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180004ecc  jmp     short loc_180004ED3
0x180004ece  call    TraceLoggingUnregister_EventUnregister
0x180004ed3  mov     eax, 1
0x180004ed8  add     rsp, 28h
0x180004edc  retn
```

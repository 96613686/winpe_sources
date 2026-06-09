# DllMain

- ea: `0x18000b34c`
- end: `0x18000b38a`
- name: `DllMain`
- size: `62`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002614`

## callees

- `0x180001a30`
- `0x180001af4`
- `0x18000b34c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b359`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b359`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18003E038);
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(&dword_18003E038, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x18000b34c  sub     rsp, 28h
0x18000b350  test    edx, edx
0x18000b352  jz      short loc_18000B373
0x18000b354  cmp     edx, 1
0x18000b357  jnz     short loc_18000B37F
0x18000b359  call    cs:__imp_DisableThreadLibraryCalls
0x18000b360  nop     dword ptr [rax+rax+00h]
0x18000b365  lea     rcx, dword_18003E038; CallbackContext
0x18000b36c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000b371  jmp     short loc_18000B37F
0x18000b373  lea     rcx, dword_18003E038
0x18000b37a  call    TraceLoggingUnregister_EventUnregister
0x18000b37f  mov     eax, 1
0x18000b384  add     rsp, 28h
0x18000b388  retn
```

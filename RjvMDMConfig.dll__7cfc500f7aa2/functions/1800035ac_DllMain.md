# DllMain

- ea: `0x1800035ac`
- end: `0x180003602`
- name: `DllMain`
- size: `86`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001ad4`

## callees

- `0x180001010`
- `0x1800010d0`
- `0x1800035ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800035b9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800035b9`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  __int64 v4; // r8

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180029000);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180029038);
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(&dword_180029038, fdwReason, lpvReserved);
    TraceLoggingUnregister_EventUnregister(&dword_180029000, v3, v4);
  }
  return 1;
}

```

## disassembly

```asm
0x1800035ac  sub     rsp, 28h
0x1800035b0  test    edx, edx
0x1800035b2  jz      short loc_1800035DF
0x1800035b4  cmp     edx, 1
0x1800035b7  jnz     short loc_1800035F7
0x1800035b9  call    cs:__imp_DisableThreadLibraryCalls
0x1800035c0  nop     dword ptr [rax+rax+00h]
0x1800035c5  lea     rcx, dword_180029000; CallbackContext
0x1800035cc  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800035d1  lea     rcx, dword_180029038; CallbackContext
0x1800035d8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800035dd  jmp     short loc_1800035F7
0x1800035df  lea     rcx, dword_180029038
0x1800035e6  call    TraceLoggingUnregister_EventUnregister
0x1800035eb  lea     rcx, dword_180029000
0x1800035f2  call    TraceLoggingUnregister_EventUnregister
0x1800035f7  mov     eax, 1
0x1800035fc  add     rsp, 28h
0x180003600  retn
```

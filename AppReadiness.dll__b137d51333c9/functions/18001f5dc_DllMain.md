# DllMain

- ea: `0x18001f5dc`
- end: `0x18001f6ba`
- name: `DllMain`
- size: `222`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003e084`

## callees

- `0x180001ad0`
- `0x18001f5dc`
- `0x18001f6c0`
- `0x18001f778`
- `0x18001f800`
- `0x18001f830`
- `0x1800368c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001f5f1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001f5f1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001f667`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001f667`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      qword_1800A4540 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_AppReadiness;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_1800A4548 = 1;
      WppInitUm();
      McGenEventRegister_EventRegister(v4, v3, &Windows_AppReadiness_Context, &Windows_AppReadiness_Context);
      EventSetInformation(
        Windows_AppReadiness_Context,
        2,
        &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
        (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800A2278);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800A2208);
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(&dword_1800A2278, fdwReason, lpvReserved);
    TraceLoggingUnregister_EventUnregister(&dword_1800A2208, v5, v6);
    McGenEventUnregister_EventUnregister(&Windows_AppReadiness_Context);
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x18001f5dc  sub     rsp, 28h
0x18001f5e0  test    edx, edx
0x18001f5e2  jz      loc_18001F687
0x18001f5e8  cmp     edx, 1
0x18001f5eb  jnz     loc_18001F6B0
0x18001f5f1  call    cs:__imp_DisableThreadLibraryCalls
0x18001f5f7  lea     rax, WPP_ThisDir_CTLGUID_AppReadiness
0x18001f5fe  mov     cs:qword_1800A4540, 0
0x18001f609  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001f610  lea     rax, WPP_MAIN_CB
0x18001f617  mov     cs:WPP_GLOBAL_Control, rax
0x18001f61e  mov     cs:WPP_MAIN_CB, 0
0x18001f629  mov     cs:qword_1800A4548, 1
0x18001f634  call    WppInitUm
0x18001f639  lea     r9, Windows_AppReadiness_Context
0x18001f640  lea     r8, Windows_AppReadiness_Context
0x18001f647  call    McGenEventRegister_EventRegister
0x18001f64c  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18001f654  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18001f65b  mov     rcx, cs:Windows_AppReadiness_Context
0x18001f662  mov     edx, 2
0x18001f667  call    cs:__imp_EventSetInformation
0x18001f66d  lea     rcx, dword_1800A2278; CallbackContext
0x18001f674  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001f679  lea     rcx, dword_1800A2208; CallbackContext
0x18001f680  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001f685  jmp     short loc_18001F6B0
0x18001f687  lea     rcx, dword_1800A2278
0x18001f68e  call    TraceLoggingUnregister_EventUnregister
0x18001f693  lea     rcx, dword_1800A2208
0x18001f69a  call    TraceLoggingUnregister_EventUnregister
0x18001f69f  lea     rcx, Windows_AppReadiness_Context
0x18001f6a6  call    McGenEventUnregister_EventUnregister
0x18001f6ab  call    WppCleanupUm
0x18001f6b0  mov     eax, 1
0x18001f6b5  add     rsp, 28h
0x18001f6b9  retn
```

# DllMain

- ea: `0x18000ec6c`
- end: `0x18000edf0`
- name: `DllMain`
- size: `388`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001add4`

## callees

- `0x1800011b4`
- `0x180009fb0`
- `0x18000e1d8`
- `0x18000ec6c`
- `0x1800199fc`
- `0x18001af70`
- `0x1800215cc`
- `0x180021728`
- `0x180021760`
- `0x180021790`
- `0x1800218b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ed20`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ed20`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // r8
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-28h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800590A0);
      qword_180059D90 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_DSM;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_180059D98 = 1;
      WppInitUm();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_41e6758d2a6231c8dfd64340188f545a_Traceguids);
      wil::SetResultLoggingCallback(lambda_3971ce3fd6d5a484e0170019b9ddd9dd_::_lambda_invoker_cdecl_);
      DisableThreadLibraryCalls(hinstDLL);
      McGenEventRegister_EventRegister();
      if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
          (const EVENT_DESCRIPTOR *)DsmServiceDllLoad,
          v4,
          1u,
          &v6);
    }
  }
  else
  {
    if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
        (const EVENT_DESCRIPTOR *)DsmServiceDllUnload,
        (__int64)lpvReserved,
        1u,
        &v6);
    McGenEventUnregister_EventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_41e6758d2a6231c8dfd64340188f545a_Traceguids);
    wil::details::g_pfnLoggingCallback = 0;
    WppCleanupUm();
    TraceLoggingUnregister_EventUnregister(&dword_1800590A0);
  }
  return 1;
}

```

## disassembly

```asm
0x18000ec6c  push    rbx
0x18000ec6e  sub     rsp, 50h
0x18000ec72  mov     rax, cs:__security_cookie
0x18000ec79  xor     rax, rsp
0x18000ec7c  mov     [rsp+58h+var_18], rax
0x18000ec81  mov     rbx, rcx
0x18000ec84  test    edx, edx
0x18000ec86  jz      loc_18000ED5D
0x18000ec8c  cmp     edx, 1
0x18000ec8f  jnz     loc_18000EDD8
0x18000ec95  lea     rcx, dword_1800590A0; CallbackContext
0x18000ec9c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000eca1  lea     rax, WPP_ThisDir_CTLGUID_DSM
0x18000eca8  mov     cs:qword_180059D90, 0
0x18000ecb3  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000ecba  lea     rax, WPP_MAIN_CB
0x18000ecc1  mov     cs:WPP_GLOBAL_Control, rax
0x18000ecc8  mov     cs:WPP_MAIN_CB, 0
0x18000ecd3  mov     cs:qword_180059D98, 1
0x18000ecde  call    WppInitUm
0x18000ece3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecea  lea     rax, WPP_GLOBAL_Control
0x18000ecf1  cmp     rcx, rax
0x18000ecf4  jz      short loc_18000ED11
0x18000ecf6  test    byte ptr [rcx+1Ch], 1
0x18000ecfa  jz      short loc_18000ED11
0x18000ecfc  mov     rcx, [rcx+10h]
0x18000ed00  lea     r8, WPP_41e6758d2a6231c8dfd64340188f545a_Traceguids
0x18000ed07  mov     edx, 0Ah
0x18000ed0c  call    WPP_SF_
0x18000ed11  lea     rcx, _lambda_3971ce3fd6d5a484e0170019b9ddd9dd____lambda_invoker_cdecl_
0x18000ed18  call    ?SetResultLoggingCallback@wil@@YAXP6AXAEBUFailureInfo@1@@_E@Z; wil::SetResultLoggingCallback(void (*)(wil::FailureInfo const &),...)
0x18000ed1d  mov     rcx, rbx; hLibModule
0x18000ed20  call    cs:__imp_DisableThreadLibraryCalls
0x18000ed26  call    McGenEventRegister_EventRegister
0x18000ed2b  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 4
0x18000ed32  jz      loc_18000EDD8
0x18000ed38  lea     rax, [rsp+58h+var_28]
0x18000ed3d  mov     r9d, 1
0x18000ed43  lea     rdx, DsmServiceDllLoad
0x18000ed4a  mov     [rsp+58h+var_38], rax
0x18000ed4f  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x18000ed56  call    McGenEventWrite_EventWriteTransfer
0x18000ed5b  jmp     short loc_18000EDD8
0x18000ed5d  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 4
0x18000ed64  jz      short loc_18000ED89
0x18000ed66  lea     rax, [rsp+58h+var_28]
0x18000ed6b  mov     r9d, 1
0x18000ed71  lea     rdx, DsmServiceDllUnload
0x18000ed78  mov     [rsp+58h+var_38], rax
0x18000ed7d  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x18000ed84  call    McGenEventWrite_EventWriteTransfer
0x18000ed89  call    McGenEventUnregister_EventUnregister
0x18000ed8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed95  lea     rax, WPP_GLOBAL_Control
0x18000ed9c  cmp     rcx, rax
0x18000ed9f  jz      short loc_18000EDBC
0x18000eda1  test    byte ptr [rcx+1Ch], 1
0x18000eda5  jz      short loc_18000EDBC
0x18000eda7  mov     rcx, [rcx+10h]
0x18000edab  lea     r8, WPP_41e6758d2a6231c8dfd64340188f545a_Traceguids
0x18000edb2  mov     edx, 0Ch
0x18000edb7  call    WPP_SF_
0x18000edbc  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x18000edc7  call    WppCleanupUm
0x18000edcc  lea     rcx, dword_1800590A0
0x18000edd3  call    TraceLoggingUnregister_EventUnregister
0x18000edd8  mov     eax, 1
0x18000eddd  mov     rcx, [rsp+58h+var_18]
0x18000ede2  xor     rcx, rsp; StackCookie
0x18000ede5  call    __security_check_cookie
0x18000edea  add     rsp, 50h
0x18000edee  pop     rbx
0x18000edef  retn
```

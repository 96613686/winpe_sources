# DllMain

- ea: `0x18001ac20`
- end: `0x18001ae05`
- name: `DllMain`
- size: `485`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180024864`

## callees

- `0x180007aa0`
- `0x18001ac20`
- `0x18001ae0c`
- `0x18001b070`
- `0x18001b09c`
- `0x18001b0c8`
- `0x18001b0f8`
- `0x18001b150`
- `0x18001b1d8`
- `0x18001b210`
- `0x180023548`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adc6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001ac65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001ac65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001ac72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001ac72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001ad95`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001ad95`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  EventRendering *v10; // rcx
  DWORD LastError; // eax

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      McGenEventRegister_EventRegister(hinstDLL, fdwReason, lpvReserved);
      qword_18004B378 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_CtlGuid;
      WPP_GLOBAL_Control = (LastErrInfo *)&WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_18004B380 = 1;
      WppInitUm();
      TraceLoggingRegisterEx_EventRegister_EventSetInformation();
      g_wevtapiModuleCallbackEnvironment.Version = 3;
      g_wevtapiModuleCallbackEnvironment.Pool = 0;
      g_wevtapiModuleCallbackEnvironment.CleanupGroup = 0;
      g_wevtapiModuleCallbackEnvironment.CleanupGroupCancelCallback = 0;
      g_wevtapiModuleCallbackEnvironment.ActivationContext = 0;
      g_wevtapiModuleCallbackEnvironment.FinalizationCallback = 0;
      g_wevtapiModuleCallbackEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
      g_wevtapiModuleCallbackEnvironment.Size = 72;
      g_wevtapiModuleCallbackEnvironment.u.Flags = 1;
      g_wevtapiModuleCallbackEnvironment.RaceDll = hinstDLL;
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      ptpcg = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        g_wevtapiModuleCallbackEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
        g_wevtapiModuleCallbackEnvironment.CleanupGroupCancelCallback = 0;
      }
      else
      {
        LastError = GetLastError();
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids,
              LastError);
        }
      }
      EventRendering::InitializeGlobals(v10);
    }
    return 1;
  }
  if ( !lpvReserved )
  {
    if ( ptpcg )
    {
      CloseThreadpoolCleanupGroupMembers(ptpcg, 1, 0);
      CloseThreadpoolCleanupGroup(ptpcg);
    }
    wmi::AutoRef<Object>::Release(&g_defaultSession);
    v5 = g_systemValuesRenderContext;
    g_defaultSession = 0;
    g_systemValuesRenderContext = 0;
    if ( v5 )
      utl::default_delete<ValuesRenderContext>::operator()();
    v6 = g_userDataValuesRenderContext;
    g_userDataValuesRenderContext = 0;
    if ( v6 )
      utl::default_delete<ValuesRenderContext>::operator()();
    v7 = g_eventDataValuesRenderContext;
    g_eventDataValuesRenderContext = 0;
    if ( v7 )
      utl::default_delete<ValuesRenderContext>::operator()();
    v8 = g_forwardedEventsValuesRenderContext;
    g_forwardedEventsValuesRenderContext = 0;
    if ( v8 )
      utl::default_delete<ValuesRenderContext>::operator()();
    TraceLoggingUnregister_EventUnregister();
    WppCleanupUm();
    McGenEventUnregister_EventUnregister();
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ac20  mov     [rsp+arg_0], rsi
0x18001ac25  push    rdi
0x18001ac26  sub     rsp, 20h
0x18001ac2a  xor     esi, esi
0x18001ac2c  mov     rdi, rcx
0x18001ac2f  test    edx, edx
0x18001ac31  jz      short loc_18001AC4C
0x18001ac33  cmp     edx, 1
0x18001ac36  jz      loc_18001ACFF
0x18001ac3c  mov     eax, 1
0x18001ac41  mov     rsi, [rsp+28h+arg_0]
0x18001ac46  add     rsp, 20h
0x18001ac4a  pop     rdi
0x18001ac4b  retn
0x18001ac4c  test    r8, r8
0x18001ac4f  jnz     loc_18001ADBF
0x18001ac55  mov     rcx, cs:ptpcg; ptpcg
0x18001ac5c  test    rcx, rcx
0x18001ac5f  jz      short loc_18001AC78
0x18001ac61  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18001ac65  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001ac6b  mov     rcx, cs:ptpcg; ptpcg
0x18001ac72  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001ac78  lea     rcx, ?g_defaultSession@@3V?$AutoRef@VSession@@@wmi@@A; void *
0x18001ac7f  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x18001ac84  mov     rdx, cs:?g_systemValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_systemValuesRenderContext
0x18001ac8b  mov     cs:?g_defaultSession@@3V?$AutoRef@VSession@@@wmi@@A, rsi; wmi::AutoRef<Session> g_defaultSession
0x18001ac92  mov     cs:?g_systemValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A, rsi; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_systemValuesRenderContext
0x18001ac99  test    rdx, rdx
0x18001ac9c  jz      short loc_18001ACA3
0x18001ac9e  call    ??R?$default_delete@VValuesRenderContext@@@utl@@QEBAXPEAVValuesRenderContext@@@Z; utl::default_delete<ValuesRenderContext>::operator()(ValuesRenderContext *)
0x18001aca3  mov     rdx, cs:?g_userDataValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_userDataValuesRenderContext
0x18001acaa  mov     cs:?g_userDataValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A, rsi; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_userDataValuesRenderContext
0x18001acb1  test    rdx, rdx
0x18001acb4  jz      short loc_18001ACBB
0x18001acb6  call    ??R?$default_delete@VValuesRenderContext@@@utl@@QEBAXPEAVValuesRenderContext@@@Z; utl::default_delete<ValuesRenderContext>::operator()(ValuesRenderContext *)
0x18001acbb  mov     rdx, cs:?g_eventDataValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_eventDataValuesRenderContext
0x18001acc2  mov     cs:?g_eventDataValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A, rsi; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_eventDataValuesRenderContext
0x18001acc9  test    rdx, rdx
0x18001accc  jz      short loc_18001ACD3
0x18001acce  call    ??R?$default_delete@VValuesRenderContext@@@utl@@QEBAXPEAVValuesRenderContext@@@Z; utl::default_delete<ValuesRenderContext>::operator()(ValuesRenderContext *)
0x18001acd3  mov     rdx, cs:?g_forwardedEventsValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_forwardedEventsValuesRenderContext
0x18001acda  mov     cs:?g_forwardedEventsValuesRenderContext@@3V?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@A, rsi; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> g_forwardedEventsValuesRenderContext
0x18001ace1  test    rdx, rdx
0x18001ace4  jz      short loc_18001ACEB
0x18001ace6  call    ??R?$default_delete@VValuesRenderContext@@@utl@@QEBAXPEAVValuesRenderContext@@@Z; utl::default_delete<ValuesRenderContext>::operator()(ValuesRenderContext *)
0x18001aceb  call    TraceLoggingUnregister_EventUnregister
0x18001acf0  call    WppCleanupUm
0x18001acf5  call    McGenEventUnregister_EventUnregister
0x18001acfa  jmp     loc_18001AC3C
0x18001acff  call    McGenEventRegister_EventRegister
0x18001ad04  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x18001ad0b  mov     cs:qword_18004B378, rsi
0x18001ad12  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001ad19  lea     rax, WPP_MAIN_CB
0x18001ad20  mov     cs:WPP_GLOBAL_Control, rax
0x18001ad27  mov     cs:WPP_MAIN_CB, rsi
0x18001ad2e  mov     cs:qword_18004B380, 1
0x18001ad39  call    WppInitUm
0x18001ad3e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001ad43  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad4d  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rsi; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad54  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rsi; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad5b  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad62  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.ActivationContext, rsi; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad69  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad70  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad7a  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad84  mov     dword ptr cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 1; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad8e  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, rdi; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001ad95  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001ad9b  mov     cs:ptpcg, rax
0x18001ada2  test    rax, rax
0x18001ada5  jz      short loc_18001ADC6
0x18001ada7  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001adae  mov     cs:?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_wevtapiModuleCallbackEnvironment ...
0x18001adb5  call    ?InitializeGlobals@EventRendering@@YAKXZ; EventRendering::InitializeGlobals(void)
0x18001adba  jmp     loc_18001AC3C
0x18001adbf  xor     eax, eax
0x18001adc1  jmp     loc_18001AC41
0x18001adc6  call    cs:__imp_GetLastError
0x18001adcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001add3  lea     rdx, WPP_GLOBAL_Control
0x18001adda  cmp     rcx, rdx
0x18001addd  jz      short loc_18001ADB5
0x18001addf  test    byte ptr [rcx+1Ch], 8
0x18001ade3  jz      short loc_18001ADB5
0x18001ade5  cmp     byte ptr [rcx+19h], 1
0x18001ade9  jb      short loc_18001ADB5
0x18001adeb  mov     rcx, [rcx+10h]
0x18001adef  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001adf6  mov     edx, 11h
0x18001adfb  mov     r9d, eax
0x18001adfe  call    WPP_SF_D
0x18001ae03  jmp     short loc_18001ADB5
```

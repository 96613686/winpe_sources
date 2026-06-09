# DllMain

- ea: `0x1800667ec`
- end: `0x180066a54`
- name: `DllMain`
- size: `616`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b9864`

## callees

- `0x18002ee38`
- `0x180050a90`
- `0x1800667ec`
- `0x180066a5c`
- `0x180066ac4`
- `0x180080524`
- `0x1800894e0`
- `0x1800896dc`
- `0x1800a483c`
- `0x1800a5b54`
- `0x1800af0a4`
- `0x1800ba574`
- `0x1800be730`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180066824`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180066824`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066831`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066831`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800669f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800669f0`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180066865`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180066865`

## string_xrefs

- `0x18006690b`: `onecoreuap\base\diagnosis\platform\notifications\platform\dll\dllmain.cpp`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  const struct wil::FailureInfo *v8; // rdx
  int v9[42]; // [rsp+20h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( hinstDLL )
  {
    v3 = 0;
    if ( fdwReason )
    {
      if ( fdwReason == 1 )
      {
        g_Module = hinstDLL;
        DisableThreadLibraryCalls(hinstDLL);
        InitializeCriticalSection(&g_CritSec);
        McGenEventRegister_EventRegister(v6, v5, &WPNCORE_PROVIDER_GUID_Context, &WPNCORE_PROVIDER_GUID_Context);
        EventSetInformation(
          WPNCORE_PROVIDER_GUID_Context,
          2,
          &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
          (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
        qword_18015D338 = 0;
        WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_Wpn;
        WPP_GLOBAL_Control = &WPP_MAIN_CB;
        WPP_MAIN_CB = 0;
        qword_18015D340 = 1;
        WppInitUm();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ae8a1fd9e8e934e7938f20e678f1d79f_Traceguids);
        }
        g_resetEnclosedObject = 1;
        v7 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18015C038);
        v3 = v7;
        if ( v7 < 0 )
        {
          if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x10) != 0 )
            McTemplateU0d_EventWriteTransfer(
              &WPNCORE_PROVIDER_GUID_Context,
              WPNPLAT_TRACELOGGING_REGISTRATION,
              (unsigned int)v7);
          v3 = 0;
        }
        else
        {
          byte_18015DC88 = 1;
        }
        if ( wil::details::g_pfnLoggingCallback
          && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != FailureLoggingCallback )
        {
          memset_0(v9, 0, 0x98u);
          wil::details::WilFailFast((wil::details *)v9, v8);
        }
        wil::details::g_pfnLoggingCallback = (__int64)FailureLoggingCallback;
      }
    }
    else
    {
      g_resetEnclosedObject = lpvReserved == 0;
      DeleteCriticalSection(&g_CritSec);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ae8a1fd9e8e934e7938f20e678f1d79f_Traceguids);
      }
      WppCleanupUm();
      if ( byte_18015DC88 )
        TraceLoggingUnregister_EventUnregister(&dword_18015C038);
      McGenEventUnregister_EventUnregister(&WPNCORE_PROVIDER_GUID_Context);
    }
  }
  else
  {
    v3 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\dll\\dllmain.cpp",
      (const char *)0x80070057LL,
      v9[0]);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ae8a1fd9e8e934e7938f20e678f1d79f_Traceguids, 2147942487LL);
  }
  return v3 >= 0;
}

```

## disassembly

```asm
0x1800667ec  push    rbx
0x1800667ee  sub     rsp, 0C0h
0x1800667f5  test    rcx, rcx
0x1800667f8  jz      loc_180066903
0x1800667fe  xor     ebx, ebx
0x180066800  test    edx, edx
0x180066802  jz      loc_1800669DF
0x180066808  cmp     edx, 1
0x18006680b  jz      short loc_18006681D
0x18006680d  not     ebx
0x18006680f  shr     ebx, 1Fh
0x180066812  mov     eax, ebx
0x180066814  add     rsp, 0C0h
0x18006681b  pop     rbx
0x18006681c  retn
0x18006681d  mov     cs:?g_Module@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_Module
0x180066824  call    cs:__imp_DisableThreadLibraryCalls
0x18006682a  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180066831  call    cs:__imp_InitializeCriticalSection
0x180066837  lea     r9, WPNCORE_PROVIDER_GUID_Context
0x18006683e  lea     r8, WPNCORE_PROVIDER_GUID_Context
0x180066845  call    McGenEventRegister_EventRegister
0x18006684a  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x180066852  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x180066859  mov     rcx, cs:WPNCORE_PROVIDER_GUID_Context
0x180066860  mov     edx, 2
0x180066865  call    cs:__imp_EventSetInformation
0x18006686b  lea     rax, WPP_ThisDir_CTLGUID_Wpn
0x180066872  mov     cs:qword_18015D338, rbx
0x180066879  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180066880  lea     rax, WPP_MAIN_CB
0x180066887  mov     cs:WPP_GLOBAL_Control, rax
0x18006688e  mov     cs:WPP_MAIN_CB, rbx
0x180066895  mov     cs:qword_18015D340, 1
0x1800668a0  call    WppInitUm
0x1800668a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800668ac  lea     rax, WPP_GLOBAL_Control
0x1800668b3  cmp     rcx, rax
0x1800668b6  jnz     loc_180066965
0x1800668bc  lea     rcx, dword_18015C038; CallbackContext
0x1800668c3  mov     cs:?g_resetEnclosedObject@@3_NA, 1; bool g_resetEnclosedObject
0x1800668ca  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800668cf  mov     ebx, eax
0x1800668d1  test    eax, eax
0x1800668d3  js      loc_180066993
0x1800668d9  mov     cs:byte_18015DC88, 1
0x1800668e0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800668e7  lea     rcx, ?FailureLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z; FailureLoggingCallback(wil::FailureInfo const &)
0x1800668ee  test    rax, rax
0x1800668f1  jnz     loc_1800669B9
0x1800668f7  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x1800668fe  jmp     loc_18006680D
0x180066903  mov     rcx, [rsp+0C8h]; this
0x18006690b  lea     r8, aOnecoreuapBase_114; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180066912  mov     ebx, 80070057h
0x180066917  mov     edx, 4Fh ; 'O'; void *
0x18006691c  mov     r9d, ebx; char *
0x18006691f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180066924  mov     rcx, cs:WPP_GLOBAL_Control
0x18006692b  lea     rax, WPP_GLOBAL_Control
0x180066932  cmp     rcx, rax
0x180066935  jz      loc_18006680D
0x18006693b  test    byte ptr [rcx+1Ch], 80h
0x18006693f  jz      loc_18006680D
0x180066945  mov     rcx, [rcx+10h]
0x180066949  lea     r8, WPP_ae8a1fd9e8e934e7938f20e678f1d79f_Traceguids
0x180066950  mov     edx, 0Ah
0x180066955  mov     r9d, 80070057h
0x18006695b  call    WPP_SF_d
0x180066960  jmp     loc_18006680D
0x180066965  test    byte ptr [rcx+1Ch], 40h
0x180066969  jz      loc_1800668BC
0x18006696f  cmp     byte ptr [rcx+19h], 5
0x180066973  jb      loc_1800668BC
0x180066979  mov     rcx, [rcx+10h]
0x18006697d  lea     r8, WPP_ae8a1fd9e8e934e7938f20e678f1d79f_Traceguids
0x180066984  mov     edx, 0Bh
0x180066989  call    WPP_SF_
0x18006698e  jmp     loc_1800668BC
0x180066993  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 10h
0x18006699a  jz      short loc_1800669B2
0x18006699c  mov     r8d, eax
0x18006699f  lea     rdx, WPNPLAT_TRACELOGGING_REGISTRATION
0x1800669a6  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x1800669ad  call    McTemplateU0d_EventWriteTransfer
0x1800669b2  xor     ebx, ebx
0x1800669b4  jmp     loc_1800668E0
0x1800669b9  cmp     rax, rcx
0x1800669bc  jz      loc_1800668F7
0x1800669c2  xor     edx, edx; Val
0x1800669c4  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800669c9  mov     r8d, 98h; Size
0x1800669cf  call    memset_0
0x1800669d4  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800669d9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800669df  test    r8, r8
0x1800669e2  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800669e9  setz    cs:?g_resetEnclosedObject@@3_NA; bool g_resetEnclosedObject
0x1800669f0  call    cs:__imp_DeleteCriticalSection
0x1800669f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800669fd  lea     rax, WPP_GLOBAL_Control
0x180066a04  cmp     rcx, rax
0x180066a07  jz      short loc_180066A2A
0x180066a09  test    byte ptr [rcx+1Ch], 40h
0x180066a0d  jz      short loc_180066A2A
0x180066a0f  cmp     byte ptr [rcx+19h], 5
0x180066a13  jb      short loc_180066A2A
0x180066a15  mov     rcx, [rcx+10h]
0x180066a19  lea     r8, WPP_ae8a1fd9e8e934e7938f20e678f1d79f_Traceguids
0x180066a20  mov     edx, 0Ch
0x180066a25  call    WPP_SF_
0x180066a2a  call    WppCleanupUm
0x180066a2f  cmp     cs:byte_18015DC88, bl
0x180066a35  jz      short loc_180066A43
0x180066a37  lea     rcx, dword_18015C038
0x180066a3e  call    TraceLoggingUnregister_EventUnregister
0x180066a43  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x180066a4a  call    McGenEventUnregister_EventUnregister
0x180066a4f  jmp     loc_18006680D
```

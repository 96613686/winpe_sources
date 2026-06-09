# DllMain

- ea: `0x18002ce60`
- end: `0x18002d04a`
- name: `DllMain`
- size: `490`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800aeb84`

## callees

- `0x180012fc8`
- `0x18001adb4`
- `0x180021374`
- `0x18002cd24`
- `0x18002ce60`
- `0x18002d050`
- `0x18002d2e0`
- `0x18002db7c`
- `0x18005877c`
- `0x18007ea98`
- `0x180087ec0`
- `0x1800af1bc`
- `0x1800af918`
- `0x18018ca90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18002cf25`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18002cf25`
- `ntdll!RtlDeleteCriticalSection` at `0x18002cf81`
- `ntdll!RtlDeleteCriticalSection` at `0x18002d030`
- `ntdll!RtlDeleteCriticalSection` at `0x18002cf81`
- `ntdll!RtlDeleteCriticalSection` at `0x18002d030`
- `KERNEL32!TlsGetValue` at `0x18002ce98`
- `KERNEL32!TlsGetValue` at `0x18002ce98`
- `KERNEL32!TlsSetValue` at `0x18002cec4`
- `KERNEL32!TlsSetValue` at `0x18002cec4`

## string_xrefs

- `0x18002cfee`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x18002cf58`: `onecore\admin\appmodel\osim\src\extensiondll\desktop\dllmain.cpp`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rdx
  LPVOID Value; // rax
  __int64 v7; // rcx
  void *v8; // rbx
  const struct std::nothrow_t *v9; // rdx
  int v10; // eax
  Common::Deployment::Platform *v11; // rcx
  __int64 v12; // rdx
  PRTL_CRITICAL_SECTION i; // rbx
  const struct wil::FailureInfo *v14; // rdx
  int v15; // eax
  int v16[42]; // [rsp+20h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( !fdwReason )
  {
    v15 = StateRepository::Shutdown(hinstDLL);
    if ( v15 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v15,
        v16[0]);
    Common::Deployment::VolumeManager::Cleanup();
    McGenEventUnregister_EventUnregister(&APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context);
    Common::StateSeparation::ClearCache();
    if ( !lpvReserved )
    {
      RtlDeleteCriticalSection(&Common::mainLock);
      for ( i = Common::StaticLock::head; i; i = *(PRTL_CRITICAL_SECTION *)&i[1].LockCount )
      {
        if ( LODWORD(i[1].DebugInfo) )
          RtlDeleteCriticalSection(i);
      }
      Common::StaticLock::head = 0;
    }
    return 1;
  }
  v4 = fdwReason - 1;
  if ( (_DWORD)v4 )
  {
    if ( (_DWORD)v4 == 2 && dwTlsIndex != -1 )
    {
      Value = TlsGetValue(dwTlsIndex);
      v8 = Value;
      if ( Value )
      {
        Common::Deployment::List<APPX_ERROR_INFO>::RemoveElement(v7, Value);
        operator delete(v8, v9);
        TlsSetValue(dwTlsIndex, 0);
      }
    }
    return 1;
  }
  if ( wil::details::g_pfnLoggingCallback
    && (__int64 (__fastcall *)())wil::details::g_pfnLoggingCallback != TraceFailureFromProvider<AppXDEHTelemetry> )
  {
    memset_0(v16, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v16, v14);
  }
  wil::details::g_pfnLoggingCallback = (__int64)TraceFailureFromProvider<AppXDEHTelemetry>;
  McGenEventRegister_EventRegister(
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
    v4,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context);
  EventSetInformation(
    APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
    2,
    &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
    (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  v10 = StateRepository::Initialize();
  if ( v10 < 0 )
  {
    v12 = 26;
  }
  else
  {
    v10 = Common::Deployment::Platform::Initialize(v11);
    if ( v10 >= 0 )
      return 1;
    v12 = 32;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\extensiondll\\desktop\\dllmain.cpp",
    (const char *)(unsigned int)v10,
    v16[0]);
  McGenEventUnregister_EventUnregister(&APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context);
  return 0;
}

```

## disassembly

```asm
0x18002ce60  push    rbx
0x18002ce62  sub     rsp, 0C0h
0x18002ce69  mov     rbx, r8
0x18002ce6c  test    edx, edx
0x18002ce6e  jz      loc_18002CFDD
0x18002ce74  sub     edx, 1
0x18002ce77  jz      short loc_18002CED2
0x18002ce79  cmp     edx, 2
0x18002ce7c  jz      short loc_18002CE8D
0x18002ce7e  mov     eax, 1
0x18002ce83  add     rsp, 0C0h
0x18002ce8a  pop     rbx
0x18002ce8b  retn
0x18002ce8d  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002ce93  cmp     ecx, 0FFFFFFFFh
0x18002ce96  jz      short loc_18002CE7E
0x18002ce98  call    cs:__imp_TlsGetValue
0x18002ce9f  nop     dword ptr [rax+rax+00h]
0x18002cea4  mov     rbx, rax
0x18002cea7  test    rax, rax
0x18002ceaa  jz      short loc_18002CE7E
0x18002ceac  mov     rdx, rax
0x18002ceaf  call    ?RemoveElement@?$List@UAPPX_ERROR_INFO@@@Deployment@Common@@QEAAXPEAUAPPX_ERROR_INFO@@@Z; Common::Deployment::List<APPX_ERROR_INFO>::RemoveElement(APPX_ERROR_INFO *)
0x18002ceb4  mov     rcx, rbx; void *
0x18002ceb7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cebc  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002cec2  xor     edx, edx; lpTlsValue
0x18002cec4  call    cs:__imp_TlsSetValue
0x18002cecb  nop     dword ptr [rax+rax+00h]
0x18002ced0  jmp     short loc_18002CE7E
0x18002ced2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002ced9  lea     rcx, ??$TraceFailureFromProvider@VAppXDEHTelemetry@@@@YAXAEBUFailureInfo@wil@@@Z; TraceFailureFromProvider<AppXDEHTelemetry>(wil::FailureInfo const &)
0x18002cee0  test    rax, rax
0x18002cee3  jnz     loc_18002CFAD
0x18002cee9  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18002cef0  lea     r9, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18002cef7  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID
0x18002cefe  lea     r8, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18002cf05  call    McGenEventRegister_EventRegister
0x18002cf0a  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18002cf12  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18002cf19  mov     rcx, cs:APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18002cf20  mov     edx, 2
0x18002cf25  call    cs:__imp_EventSetInformation
0x18002cf2c  nop     dword ptr [rax+rax+00h]
0x18002cf31  call    ?Initialize@StateRepository@@YAJW4InitializeFlags@1@@Z; StateRepository::Initialize(StateRepository::InitializeFlags)
0x18002cf36  test    eax, eax
0x18002cf38  js      loc_18002CFD3
0x18002cf3e  call    ?Initialize@Platform@Deployment@Common@@YAJXZ; Common::Deployment::Platform::Initialize(void)
0x18002cf43  test    eax, eax
0x18002cf45  jns     loc_18002CE7E
0x18002cf4b  mov     edx, 20h ; ' '; void *
0x18002cf50  mov     rcx, [rsp+0C8h]; this
0x18002cf58  lea     r8, aOnecoreAdminAp_104; "onecore\\admin\\appmodel\\osim\\src\\ex"...
0x18002cf5f  mov     r9d, eax; char *
0x18002cf62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cf67  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18002cf6e  call    McGenEventUnregister_EventUnregister
0x18002cf73  xor     eax, eax
0x18002cf75  jmp     loc_18002CE83
0x18002cf7a  lea     rcx, ?mainLock@Common@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002cf81  call    cs:__imp_RtlDeleteCriticalSection
0x18002cf88  nop     dword ptr [rax+rax+00h]
0x18002cf8d  mov     rbx, cs:?head@StaticLock@Common@@0PEAV12@EA; Common::StaticLock * Common::StaticLock::head
0x18002cf94  test    rbx, rbx
0x18002cf97  jnz     loc_18002D026
0x18002cf9d  mov     cs:?head@StaticLock@Common@@0PEAV12@EA, 0; Common::StaticLock * Common::StaticLock::head
0x18002cfa8  jmp     loc_18002CE7E
0x18002cfad  cmp     rax, rcx
0x18002cfb0  jz      loc_18002CEE9
0x18002cfb6  xor     edx, edx; Val
0x18002cfb8  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18002cfbd  mov     r8d, 98h; Size
0x18002cfc3  call    memset_0
0x18002cfc8  lea     rcx, [rsp+0C8h+var_A8]; this
0x18002cfcd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002cfd3  mov     edx, 1Ah
0x18002cfd8  jmp     loc_18002CF50
0x18002cfdd  call    ?Shutdown@StateRepository@@YAJP6AXXZW4InitializeFlags@1@@Z; StateRepository::Shutdown(void (*)(void),StateRepository::InitializeFlags)
0x18002cfe2  test    eax, eax
0x18002cfe4  jns     short loc_18002D002
0x18002cfe6  mov     rcx, [rsp+0C8h]; this
0x18002cfee  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x18002cff5  mov     r9d, eax; char *
0x18002cff8  mov     edx, 11Fh; void *
0x18002cffd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d002  call    ?Cleanup@VolumeManager@Deployment@Common@@SAXXZ; Common::Deployment::VolumeManager::Cleanup(void)
0x18002d007  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18002d00e  call    McGenEventUnregister_EventUnregister
0x18002d013  call    ?ClearCache@StateSeparation@Common@@SAXXZ; Common::StateSeparation::ClearCache(void)
0x18002d018  test    rbx, rbx
0x18002d01b  jnz     loc_18002CE7E
0x18002d021  jmp     loc_18002CF7A
0x18002d026  mov     eax, [rbx+28h]
0x18002d029  test    eax, eax
0x18002d02b  jz      short loc_18002D03C
0x18002d02d  mov     rcx, rbx; CriticalSection
0x18002d030  call    cs:__imp_RtlDeleteCriticalSection
0x18002d037  nop     dword ptr [rax+rax+00h]
0x18002d03c  mov     rbx, [rbx+30h]
0x18002d040  test    rbx, rbx
0x18002d043  jnz     short loc_18002D026
0x18002d045  jmp     loc_18002CF9D
```

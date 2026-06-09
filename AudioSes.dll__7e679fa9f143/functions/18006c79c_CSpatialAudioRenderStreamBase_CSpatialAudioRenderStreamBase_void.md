# CSpatialAudioRenderStreamBase::~CSpatialAudioRenderStreamBase(void)

- ea: `0x18006c79c`
- end: `0x18006ca57`
- name: `??1CSpatialAudioRenderStreamBase@@QEAA@XZ`
- size: `699`
- prototype: `void __fastcall(CSpatialAudioRenderStreamBase *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006c258`

## callees

- `0x180007f00`
- `0x18000d11c`
- `0x1800154e0`
- `0x180031574`
- `0x18006c338`
- `0x18006c708`
- `0x18006c79c`
- `0x18006ca60`
- `0x18006ca90`
- `0x18006cadc`
- `0x18006cafc`
- `0x18006cb18`
- `0x18006cd8c`
- `0x18006cdc0`
- `0x180087e80`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c9f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c9fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c9f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c9fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c91b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c91b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006c85a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006c94b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006c85a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006c94b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c8c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c8de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c8c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c8de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSpatialAudioRenderStreamBase::~CSpatialAudioRenderStreamBase(CSpatialAudioRenderStreamBase *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  char *v5; // rcx
  void *v6; // rdx
  wil::details *v7; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-50h] BYREF
  char v9; // [rsp+28h] [rbp-48h]
  _BYTE v10[16]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+40h] [rbp-30h]
  GUID ActivityId; // [rsp+50h] [rbp-20h] BYREF

  *(_QWORD *)this = &CSpatialAudioRenderStreamBase::`vftable'{for `IMFTrustedOutput'};
  *((_QWORD *)this + 1) = &CSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTrustedOutputPriv,IAudioStreamVolume,ISpatialAudioObjectRenderStreamBase,ISpatialAudioStreamInternal,IAudioClientTest,ICrossVmMediaNotificationProducer,IInspectable,IAudioClientTest,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &CSpatialAudioRenderStreamBase::`vftable'{for `IAudioStreamVolume'};
  *((_QWORD *)this + 3) = &CSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISpatialAudioObjectRenderStreamBase,ISpatialAudioStreamInternal,IAudioClientTest,ICrossVmMediaNotificationProducer,IInspectable,IAudioClientTest,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &CSpatialAudioRenderStreamBase::`vftable'{for `ISpatialAudioStreamInternal'};
  *((_QWORD *)this + 5) = &CSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTest,ICrossVmMediaNotificationProducer,IInspectable,IAudioClientTest,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 6) = &CSpatialAudioRenderStreamBase::`vftable'{for `ICrossVmMediaNotificationProducer'};
  *((_QWORD *)this + 7) = &CGuestSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
  *((_QWORD *)this + 8) = &CSpatialAudioRenderStreamBase::`vftable'{for `IAudioClientTest'};
  *((_QWORD *)this + 9) = &CSpatialAudioObjectBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v11 = *(_OWORD *)((char *)this + 1896);
  ActivityId = *(GUID *)((char *)this + 1896);
  EventActivityIdControl(4u, &ActivityId);
  AudSesTraceLoggingFuncEntryExit::AudSesTraceLoggingFuncEntryExit(
    (AudSesTraceLoggingFuncEntryExit *)v10,
    "CSpatialAudioRenderStreamBase::~CSpatialAudioRenderStreamBase",
    0x79Bu);
  CSpatialAudioRenderStreamBase::ReleaseStreamResources(this, 0);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 296);
  v9 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  v2 = *((_QWORD *)this + 222);
  *((_QWORD *)this + 222) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 15);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 15) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (char *)*((_QWORD *)this + 51);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 51) = 0;
  }
  if ( v9 )
    LeaveCriticalSection(lpCriticalSection);
  if ( *((_DWORD *)this + 47) )
    CSpatialAudioRenderStreamBase::UnregisterSuspensionHandler(this);
  else
    CSpatialAudioRenderStreamBase::UnregisterSuspensionHandlerForClassicApp(this);
  AudSesTraceLoggingFuncEntryExit::~AudSesTraceLoggingFuncEntryExit((AudSesTraceLoggingFuncEntryExit *)v10);
  EventActivityIdControl(4u, &ActivityId);
  v7 = (wil::details *)*((_QWORD *)this + 274);
  if ( v7 )
    wil::details::CloseHandle(v7, v6);
  CSpatialAudioClientTraceLogger::~CSpatialAudioClientTraceLogger((CSpatialAudioRenderStreamBase *)((char *)this + 1848));
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 1832);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 1824);
  ATL::CAtlArray<ISpatialAudioObjectInternal *,ATL::CElementTraits<ISpatialAudioObjectInternal *>>::~CAtlArray<ISpatialAudioObjectInternal *,ATL::CElementTraits<ISpatialAudioObjectInternal *>>((char *)this + 1792);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 1784);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 1776);
  CCoTaskMemPtr<tWAVEFORMATEX>::~CCoTaskMemPtr<tWAVEFORMATEX>((char *)this + 1768);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 1728);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 1720);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 1712);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 1704);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 432);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 32) - 24LL));
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 240);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 224);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 96);
}

```

## disassembly

```asm
0x18006c79c  mov     [rsp-18h+arg_8], rbx
0x18006c7a1  mov     [rsp-18h+arg_10], rsi
0x18006c7a6  push    rbp
0x18006c7a7  push    rdi
0x18006c7a8  push    r14
0x18006c7aa  mov     rbp, rsp
0x18006c7ad  sub     rsp, 70h
0x18006c7b1  mov     rax, cs:__security_cookie
0x18006c7b8  xor     rax, rsp
0x18006c7bb  mov     [rbp+var_10], rax
0x18006c7bf  mov     rbx, rcx
0x18006c7c2  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6BIMFTrustedOutput@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `IMFTrustedOutput'}
0x18006c7c9  mov     [rcx], rax
0x18006c7cc  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioClientTrustedOutputPriv@@UIAudioStreamVolume@@UISpatialAudioObjectRenderStreamBase@@UISpatialAudioStreamInternal@@UIAudioClientTest@@UICrossVmMediaNotificationProducer@@UIInspectable@@U8@VFtmBase@23@@Details@WRL@Microsoft@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTrustedOutputPriv,IAudioStreamVolume,ISpatialAudioObjectRenderStreamBase,ISpatialAudioStreamInternal,IAudioClientTest,ICrossVmMediaNotificationProducer,IInspectable,IAudioClientTest,Microsoft::WRL::FtmBase>'}
0x18006c7d3  mov     [rcx+8], rax
0x18006c7d7  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6BIAudioStreamVolume@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `IAudioStreamVolume'}
0x18006c7de  mov     [rcx+10h], rax
0x18006c7e2  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISpatialAudioObjectRenderStreamBase@@UISpatialAudioStreamInternal@@UIAudioClientTest@@UICrossVmMediaNotificationProducer@@UIInspectable@@U6@VFtmBase@23@@Details@WRL@Microsoft@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISpatialAudioObjectRenderStreamBase,ISpatialAudioStreamInternal,IAudioClientTest,ICrossVmMediaNotificationProducer,IInspectable,IAudioClientTest,Microsoft::WRL::FtmBase>'}
0x18006c7e9  mov     [rcx+18h], rax
0x18006c7ed  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6BISpatialAudioStreamInternal@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `ISpatialAudioStreamInternal'}
0x18006c7f4  mov     [rcx+20h], rax
0x18006c7f8  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioClientTest@@UICrossVmMediaNotificationProducer@@UIInspectable@@U4@VFtmBase@23@@Details@WRL@Microsoft@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTest,ICrossVmMediaNotificationProducer,IInspectable,IAudioClientTest,Microsoft::WRL::FtmBase>'}
0x18006c7ff  mov     [rcx+28h], rax
0x18006c803  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6BICrossVmMediaNotificationProducer@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `ICrossVmMediaNotificationProducer'}
0x18006c80a  mov     [rcx+30h], rax
0x18006c80e  lea     rax, ??_7CGuestSpatialAudioRenderStreamBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@WRL@Microsoft@@@; const CGuestSpatialAudioRenderStreamBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x18006c815  mov     [rcx+38h], rax
0x18006c819  lea     rax, ??_7CSpatialAudioRenderStreamBase@@6BIAudioClientTest@@@; const CSpatialAudioRenderStreamBase::`vftable'{for `IAudioClientTest'}
0x18006c820  mov     [rcx+40h], rax
0x18006c824  lea     rax, ??_7CSpatialAudioObjectBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CSpatialAudioObjectBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006c82b  mov     [rcx+48h], rax
0x18006c82f  movups  xmm0, xmmword ptr [rcx+768h]
0x18006c836  movdqu  [rbp+var_30], xmm0
0x18006c83b  mov     rax, [rcx+768h]
0x18006c842  mov     qword ptr [rbp+ActivityId.Data1], rax
0x18006c846  mov     rax, [rcx+770h]
0x18006c84d  mov     qword ptr [rbp+ActivityId.Data4], rax
0x18006c851  lea     rdx, [rbp+ActivityId]; ActivityId
0x18006c855  mov     ecx, 4; ControlCode
0x18006c85a  call    cs:__imp_EventActivityIdControl
0x18006c860  mov     r8d, 79Bh; unsigned int
0x18006c866  lea     rdx, aCspatialaudior_23; "CSpatialAudioRenderStreamBase::~CSpatia"...
0x18006c86d  lea     rcx, [rbp+var_40]; this
0x18006c871  call    ??0AudSesTraceLoggingFuncEntryExit@@QEAA@PEBDI@Z; AudSesTraceLoggingFuncEntryExit::AudSesTraceLoggingFuncEntryExit(char const *,uint)
0x18006c876  xor     edx, edx; int
0x18006c878  mov     rcx, rbx; this
0x18006c87b  call    ?ReleaseStreamResources@CSpatialAudioRenderStreamBase@@IEAAXH@Z; CSpatialAudioRenderStreamBase::ReleaseStreamResources(int)
0x18006c880  lea     rsi, [rbx+128h]
0x18006c887  mov     [rbp+lpCriticalSection], rsi
0x18006c88b  mov     [rbp+var_48], 0
0x18006c88f  lea     rcx, [rbp+lpCriticalSection]; this
0x18006c893  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18006c898  lea     rdi, [rbx+6F0h]
0x18006c89f  mov     rcx, [rdi]
0x18006c8a2  mov     qword ptr [rdi], 0
0x18006c8a9  test    rcx, rcx
0x18006c8ac  jz      short loc_18006C8BB
0x18006c8ae  mov     rax, [rcx]
0x18006c8b1  mov     rax, [rax+10h]
0x18006c8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8ba  nop
0x18006c8bb  mov     rcx, [rbx+78h]; pv
0x18006c8bf  test    rcx, rcx
0x18006c8c2  jz      short loc_18006C8D2
0x18006c8c4  call    cs:__imp_CoTaskMemFree
0x18006c8ca  mov     qword ptr [rbx+78h], 0
0x18006c8d2  mov     rcx, [rbx+80h]; pv
0x18006c8d9  test    rcx, rcx
0x18006c8dc  jz      short loc_18006C8EF
0x18006c8de  call    cs:__imp_CoTaskMemFree
0x18006c8e4  mov     qword ptr [rbx+80h], 0
0x18006c8ef  mov     rcx, [rbx+198h]; hObject
0x18006c8f6  lea     rax, [rcx-1]
0x18006c8fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c8fe  ja      short loc_18006C911
0x18006c900  call    cs:__imp_CloseHandle
0x18006c906  mov     qword ptr [rbx+198h], 0
0x18006c911  cmp     [rbp+var_48], 0
0x18006c915  jz      short loc_18006C921
0x18006c917  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18006c91b  call    cs:__imp_LeaveCriticalSection
0x18006c921  mov     rcx, rbx; this
0x18006c924  cmp     dword ptr [rbx+0BCh], 0
0x18006c92b  jz      short loc_18006C934
0x18006c92d  call    ?UnregisterSuspensionHandler@CSpatialAudioRenderStreamBase@@IEAAXXZ; CSpatialAudioRenderStreamBase::UnregisterSuspensionHandler(void)
0x18006c932  jmp     short loc_18006C939
0x18006c934  call    ?UnregisterSuspensionHandlerForClassicApp@CSpatialAudioRenderStreamBase@@IEAAXXZ; CSpatialAudioRenderStreamBase::UnregisterSuspensionHandlerForClassicApp(void)
0x18006c939  lea     rcx, [rbp+var_40]; this
0x18006c93d  call    ??1AudSesTraceLoggingFuncEntryExit@@QEAA@XZ; AudSesTraceLoggingFuncEntryExit::~AudSesTraceLoggingFuncEntryExit(void)
0x18006c942  lea     rdx, [rbp+ActivityId]; ActivityId
0x18006c946  mov     ecx, 4; ControlCode
0x18006c94b  call    cs:__imp_EventActivityIdControl
0x18006c951  mov     rcx, [rbx+890h]; this
0x18006c958  test    rcx, rcx
0x18006c95b  jz      short loc_18006C962
0x18006c95d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18006c962  lea     rcx, [rbx+738h]; this
0x18006c969  call    ??1CSpatialAudioClientTraceLogger@@QEAA@XZ; CSpatialAudioClientTraceLogger::~CSpatialAudioClientTraceLogger(void)
0x18006c96e  lea     rcx, [rbx+728h]; void *
0x18006c975  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006c97a  lea     rcx, [rbx+720h]; void *
0x18006c981  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006c986  lea     rcx, [rbx+700h]
0x18006c98d  call    ??1?$CAtlArray@PEAUISpatialAudioObjectInternal@@V?$CElementTraits@PEAUISpatialAudioObjectInternal@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ISpatialAudioObjectInternal *,ATL::CElementTraits<ISpatialAudioObjectInternal *>>::~CAtlArray<ISpatialAudioObjectInternal *,ATL::CElementTraits<ISpatialAudioObjectInternal *>>(void)
0x18006c992  lea     rcx, [rbx+6F8h]
0x18006c999  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006c99e  mov     rcx, rdi
0x18006c9a1  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006c9a6  lea     rcx, [rbx+6E8h]
0x18006c9ad  call    ??1?$CCoTaskMemPtr@UtWAVEFORMATEX@@@@QEAA@XZ; CCoTaskMemPtr<tWAVEFORMATEX>::~CCoTaskMemPtr<tWAVEFORMATEX>(void)
0x18006c9b2  lea     rcx, [rbx+6C0h]; void *
0x18006c9b9  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006c9be  lea     rcx, [rbx+6B8h]; void *
0x18006c9c5  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006c9ca  lea     rcx, [rbx+6B0h]; void *
0x18006c9d1  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006c9d6  lea     rcx, [rbx+6A8h]; void *
0x18006c9dd  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006c9e2  lea     rcx, [rbx+1B0h]; void *
0x18006c9e9  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006c9ee  lea     rcx, [rbx+150h]; lpCriticalSection
0x18006c9f5  call    cs:__imp_DeleteCriticalSection
0x18006c9fb  mov     rcx, rsi; lpCriticalSection
0x18006c9fe  call    cs:__imp_DeleteCriticalSection
0x18006ca04  mov     rcx, [rbx+100h]
0x18006ca0b  sub     rcx, 18h; this
0x18006ca0f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006ca14  lea     rcx, [rbx+0F0h]; void *
0x18006ca1b  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006ca20  lea     rcx, [rbx+0E0h]; void *
0x18006ca27  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006ca2c  lea     rcx, [rbx+60h]
0x18006ca30  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006ca35  nop
0x18006ca36  mov     rcx, [rbp+var_10]
0x18006ca3a  xor     rcx, rsp; StackCookie
0x18006ca3d  call    __security_check_cookie
0x18006ca42  lea     r11, [rsp+70h+var_s0]
0x18006ca47  mov     rbx, [r11+28h]
0x18006ca4b  mov     rsi, [r11+30h]
0x18006ca4f  mov     rsp, r11
0x18006ca52  pop     r14
0x18006ca54  pop     rdi
0x18006ca55  pop     rbp
0x18006ca56  retn
```

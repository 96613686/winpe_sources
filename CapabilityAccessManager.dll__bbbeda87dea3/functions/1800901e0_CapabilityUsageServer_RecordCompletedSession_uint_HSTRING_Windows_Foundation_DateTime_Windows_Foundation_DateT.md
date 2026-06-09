# CapabilityUsageServer::RecordCompletedSession(uint,HSTRING__ *,Windows::Foundation::DateTime,Windows::Foundation::DateTime)

- ea: `0x1800901e0`
- end: `0x180090967`
- name: `?RecordCompletedSession@CapabilityUsageServer@@UEAAJIPEAUHSTRING__@@UDateTime@Foundation@Windows@@1@Z`
- size: `1927`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800094c0`
- `0x1800094e4`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001e118`
- `0x18001e42c`
- `0x180020fcc`
- `0x18002392c`
- `0x180029304`
- `0x18002f93c`
- `0x18002f978`
- `0x180036f0c`
- `0x1800380a0`
- `0x1800382b8`
- `0x180038894`
- `0x180039a1c`
- `0x18003f4a0`
- `0x1800401f0`
- `0x1800428a8`
- `0x180042c4c`
- `0x180043224`
- `0x180045e74`
- `0x1800505c4`
- `0x1800581a8`
- `0x180060950`
- `0x1800619dc`
- `0x180064304`
- `0x180064fe4`
- `0x18008346c`
- `0x18008eb64`
- `0x1800901e0`
- `0x180090bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800904eb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800904eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090327`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CapabilityUsageServer::RecordCompletedSession(
        CapabilityUsageServer *a1,
        DWORD a2,
        HSTRING a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  Windows::Internal::CapabilityAccess::Private *v9; // rcx
  unsigned __int64 SystemTimeAsUInt64; // rax
  __int64 v11; // r15
  PCWSTR StringRawBuffer; // r14
  std::_Ref_count_base *v13; // r13
  __int64 v14; // r8
  __int64 v15; // rdx
  HANDLE *ProcessTokenFromProcessId; // rax
  __int64 PackageFullNameFromToken; // rax
  __int64 AdjustedUserSidString; // rax
  Windows::Internal::CapabilityAccess::Private::SQL *v19; // rcx
  HRESULT v20; // eax
  __int64 AppFriendlyName; // r12
  __int64 v22; // r15
  int v23; // esi
  char v24; // r14
  char v25; // bl
  int Capability; // eax
  __int128 *v27; // rcx
  unsigned __int64 v28; // r12
  unsigned __int16 *v29; // r15
  int v30; // r14d
  __int64 v31; // rax
  unsigned __int64 v32; // r12
  unsigned __int16 *v33; // r15
  int v34; // r14d
  __int64 v35; // rax
  __int64 v36; // rdx
  Windows::Internal::CapabilityAccess::Private::SQL *v37; // rcx
  __int64 v38; // r15
  int v39; // esi
  __int64 v40; // r14
  __int64 v41; // rbx
  int v42; // eax
  const char *v43; // r9
  __int64 result; // rax
  const struct wil::FailureInfo *Failure; // rax
  const char *v46; // rbx
  unsigned int v47; // edi
  int v48; // r14d
  const unsigned __int16 *v49; // rsi
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdx
  const unsigned __int16 *v53; // rax
  int v54; // [rsp+20h] [rbp-298h]
  unsigned __int16 *v55; // [rsp+28h] [rbp-290h]
  unsigned __int16 *v56; // [rsp+28h] [rbp-290h]
  void *phNewToken; // [rsp+78h] [rbp-240h] BYREF
  CapabilityUsageServer *v59; // [rsp+80h] [rbp-238h]
  std::_Ref_count_base *v60; // [rsp+88h] [rbp-230h]
  CapabilityUsageServer *v61; // [rsp+90h] [rbp-228h]
  int *v62; // [rsp+98h] [rbp-220h]
  _DWORD *v63; // [rsp+A0h] [rbp-218h]
  std::_Ref_count_base *v64; // [rsp+A8h] [rbp-210h]
  _BYTE v65[8]; // [rsp+B0h] [rbp-208h] BYREF
  std::_Ref_count_base *v66; // [rsp+B8h] [rbp-200h]
  int v67[8]; // [rsp+C0h] [rbp-1F8h] BYREF
  _BYTE v68[224]; // [rsp+E0h] [rbp-1D8h] BYREF
  __int128 v69; // [rsp+1C0h] [rbp-F8h] BYREF
  __int64 v70; // [rsp+1D0h] [rbp-E8h]
  __int64 v71; // [rsp+1D8h] [rbp-E0h]
  __int128 v72; // [rsp+1E0h] [rbp-D8h] BYREF
  __int64 v73; // [rsp+1F0h] [rbp-C8h]
  __int64 v74; // [rsp+1F8h] [rbp-C0h]
  __int128 v75; // [rsp+200h] [rbp-B8h] BYREF
  __int64 v76; // [rsp+210h] [rbp-A8h]
  __int64 v77; // [rsp+218h] [rbp-A0h]
  _BYTE v78[32]; // [rsp+220h] [rbp-98h] BYREF
  __int128 v79; // [rsp+240h] [rbp-78h] BYREF
  __int64 v80; // [rsp+250h] [rbp-68h]
  __int64 v81; // [rsp+258h] [rbp-60h]
  GUID pguid; // [rsp+260h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v59 = a1;
  v61 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_0fdf3ed1e82d3e0be5d42f30398a8154_Traceguids);
  }
  try
  {
    CapabilityUsageServer::EnsureCallerIsShellExperience(a1);
    wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v68);
    SystemTimeAsUInt64 = Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(v9);
    try
    {
      if ( !a2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
          (const char *)0x80070057LL,
          v54);
      if ( a4 > SystemTimeAsUInt64 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A8,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
          (const char *)0x80070057LL,
          v54);
      if ( a5 > SystemTimeAsUInt64 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A9,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
          (const char *)0x80070057LL,
          v54);
      if ( (__int64)a4 > (__int64)a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1AC,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
          (const char *)0x80070057LL,
          v54);
      if ( !a4 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
          (const char *)0x80070057LL,
          v54);
      if ( !a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
          (const char *)0x80070057LL,
          v54);
      Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(v65);
      v79 = 0;
      v80 = 0;
      v81 = 7;
      LOWORD(v79) = 0;
      v11 = *((_QWORD *)a1 + 5);
      StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
      v13 = (std::_Ref_count_base *)operator new(0x110u);
      v60 = v13;
      *((_DWORD *)v13 + 2) = 1;
      *((_DWORD *)v13 + 3) = 1;
      *(_QWORD *)v13 = &std::_Ref_count_obj2<Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo>::`vftable';
      std::wstring::wstring(&v69, StringRawBuffer);
      Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::AdjustedAppDisplayInfo(
        (__int64)v13 + 16,
        a2,
        (__int64)&v69,
        (_QWORD *)(v11 + 24));
      std::wstring::_Tidy_deallocate(&v69);
      v63 = (_DWORD *)((char *)v13 + 16);
      v64 = v13;
      LOBYTE(v14) = 3;
      LOBYTE(v15) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
        v15,
        v14);
      ProcessTokenFromProcessId = Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(
                                    &phNewToken,
                                    a2);
      PackageFullNameFromToken = Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromToken(
                                   (__int64)&v69,
                                   ProcessTokenFromProcessId);
      std::wstring::operator=(&v79, PackageFullNameFromToken);
      std::wstring::_Tidy_deallocate(&v69);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      if ( v80 )
        phNewToken = (void *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::GetAppCategoryForPackage(&v79);
      else
        phNewToken = 0;
      v72 = 0;
      v73 = 0;
      v74 = 7;
      LOWORD(v72) = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl) )
      {
        std::wstring::operator=(&v72, (char *)v13 + 224);
      }
      else
      {
        AdjustedUserSidString = Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AdjustedUserSidString((char *)v13 + 16);
        std::wstring::operator=(&v72, AdjustedUserSidString);
      }
      v60 = (std::_Ref_count_base *)((char *)v13 + 72);
      if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilitySessionManager::IsCapabilityInUseByClient(
                              (char *)v13 + 72,
                              *((_QWORD *)a1 + 5) + 40LL,
                              &v72,
                              *((unsigned int *)v13 + 9)) )
      {
        if ( Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(v19) )
        {
          pguid = 0;
          v20 = CoCreateGuid(&pguid);
          if ( v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1F8,
              (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
              (const char *)(unsigned int)v20,
              v54);
          v69 = 0;
          v70 = 0;
          v71 = 7;
          LOWORD(v69) = 0;
          v75 = 0;
          v76 = 0;
          v77 = 7;
          LOWORD(v75) = 0;
          AppFriendlyName = Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName((char *)v13 + 16);
          v62 = v67;
          v22 = Windows::Internal::CapabilityAccess::Private::GUIDToString((int)v67, &pguid);
          v23 = *((_DWORD *)v13 + 9);
          v24 = Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(a5);
          v25 = Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(a4);
          Capability = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(
                         *((_QWORD *)v59 + 5),
                         v78);
          Windows::Internal::CapabilityAccess::Private::SQL::RecordUsage(
            (unsigned int)&v72,
            Capability,
            a2,
            (_DWORD)v60,
            v25,
            v24,
            v23,
            v22,
            2,
            AppFriendlyName,
            (__int64)phNewToken,
            (unsigned int)&v75,
            (unsigned int)&v69,
            4);
          std::wstring::_Tidy_deallocate(v78);
          std::wstring::_Tidy_deallocate(&v75);
          v27 = &v69;
          goto LABEL_23;
        }
      }
      else
      {
        v28 = Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName((char *)v13 + 16);
        v29 = (unsigned __int16 *)Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(a4);
        v30 = *((_DWORD *)v13 + 9);
        v31 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(
                *((_QWORD *)v59 + 5),
                v78);
        LODWORD(v55) = 0;
        Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetLastUsedTime(
          a2,
          (std::_Ref_count_base *)&v72,
          v31,
          (__int64)v13 + 72,
          v30,
          v55,
          v29,
          a2,
          v28);
        std::wstring::_Tidy_deallocate(v78);
        v32 = Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName((char *)v13 + 16);
        v33 = (unsigned __int16 *)Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(a5);
        v34 = *((_DWORD *)v13 + 9);
        v35 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(
                *((_QWORD *)v59 + 5),
                v78);
        LODWORD(v56) = 1;
        Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetLastUsedTime(
          a2,
          (std::_Ref_count_base *)&v72,
          v35,
          (__int64)v13 + 72,
          v34,
          v56,
          v33,
          a2,
          v32);
        std::wstring::_Tidy_deallocate(v78);
        LOBYTE(v36) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl'::`2'::impl,
          v36);
        if ( Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(v37) )
        {
          v75 = 0;
          v76 = 0;
          v77 = 7;
          LOWORD(v75) = 0;
          v69 = 0;
          v70 = 0;
          v71 = 7;
          LOWORD(v69) = 0;
          v38 = Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName((char *)v13 + 16);
          v39 = *((_DWORD *)v13 + 9);
          v40 = Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(a5);
          v41 = Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(a4);
          v42 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(
                  *((_QWORD *)v59 + 5),
                  v78);
          Windows::Internal::CapabilityAccess::Private::SQL::RecordUsage(
            (unsigned int)&v72,
            v42,
            a2,
            (_DWORD)v13 + 72,
            v41,
            v40,
            v39,
            v38,
            (__int64)phNewToken,
            (__int64)&v69,
            (__int64)&v75);
          std::wstring::_Tidy_deallocate(v78);
          std::wstring::_Tidy_deallocate(&v69);
          v27 = &v75;
LABEL_23:
          std::wstring::_Tidy_deallocate(v27);
        }
      }
      std::wstring::_Tidy_deallocate(&v72);
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
      std::wstring::_Tidy_deallocate(&v79);
      if ( v66 )
        std::_Ref_count_base::_Decref(v66);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v68);
      result = 0;
    }
    catch ( wil::ResultException )
    {
      if ( !Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::GetIsTestCode() )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        Failure = wil::ThreadFailureCache::GetFailure((wil::ThreadFailureCache *)v68);
        if ( Failure )
          v46 = (const char *)*((_QWORD *)Failure + 7);
        else
          v46 = qword_1800D35C0;
        if ( Failure )
          v47 = *((_DWORD *)Failure + 16);
        else
          v47 = 0;
        if ( Failure )
          v48 = *((_DWORD *)Failure + 2);
        else
          v48 = 0;
        if ( Failure )
          v49 = (const unsigned __int16 *)*((_QWORD *)Failure + 3);
        else
          v49 = (const unsigned __int16 *)&Format;
        v50 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>::operator-><Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager,0>((char *)v61 + 40);
        v51 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(v50, v78);
        v53 = (const unsigned __int16 *)std::wstring::c_str(v51, v52);
        LogCriticalUxDependencyFailure(v53, "CapabilityUsageServer::RecordCompletedSession", v46, v47, v49, v48);
        std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(v78);
      }
      throw;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x25B,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
                           v43);
  }
  return result;
}

```

## disassembly

```asm
0x1800901e0  push    rbx
0x1800901e2  push    rsi
0x1800901e3  push    rdi
0x1800901e4  push    r12
0x1800901e6  push    r13
0x1800901e8  push    r14
0x1800901ea  push    r15
0x1800901ec  sub     rsp, 280h
0x1800901f3  mov     rax, cs:__security_cookie
0x1800901fa  xor     rax, rsp
0x1800901fd  mov     [rsp+2B8h+var_48], rax
0x180090205  mov     rdi, r9
0x180090208  mov     rsi, r8
0x18009020b  mov     r14d, edx
0x18009020e  mov     [rsp+2B8h+dwProcessId], edx
0x180090212  mov     r12, rcx
0x180090215  mov     [rsp+2B8h+var_238], rcx
0x18009021d  mov     rbx, [rsp+2B8h+arg_20]
0x180090225  mov     [rsp+2B8h+var_228], rcx
0x18009022d  lea     rax, WPP_GLOBAL_Control
0x180090234  mov     rcx, cs:WPP_GLOBAL_Control
0x18009023b  cmp     rcx, rax
0x18009023e  jz      short loc_180090261
0x180090240  test    byte ptr [rcx+1Ch], 1
0x180090244  jz      short loc_180090261
0x180090246  cmp     byte ptr [rcx+19h], 5
0x18009024a  jb      short loc_180090261
0x18009024c  mov     edx, 18h
0x180090251  lea     r8, WPP_0fdf3ed1e82d3e0be5d42f30398a8154_Traceguids
0x180090258  mov     rcx, [rcx+10h]
0x18009025c  call    WPP_SF_
0x180090261  mov     rcx, r12; this
0x180090264  call    ?EnsureCallerIsShellExperience@CapabilityUsageServer@@AEBAXXZ; CapabilityUsageServer::EnsureCallerIsShellExperience(void)
0x180090269  lea     rcx, [rsp+2B8h+var_1D8]; this
0x180090271  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x180090276  nop
0x180090277  call    ?GetSystemTimeAsUInt64@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(void)
0x18009027c  mov     rcx, [rsp+2B8h]; this
0x180090284  test    r14d, r14d
0x180090287  jz      loc_1800908C6
0x18009028d  mov     rcx, [rsp+2B8h]; this
0x180090295  cmp     rdi, rax
0x180090298  ja      loc_1800908DD
0x18009029e  mov     rcx, [rsp+2B8h]; this
0x1800902a6  cmp     rbx, rax
0x1800902a9  ja      loc_1800908F4
0x1800902af  mov     rcx, [rsp+2B8h]; this
0x1800902b7  cmp     rdi, rbx
0x1800902ba  jg      loc_18009090B
0x1800902c0  mov     rcx, [rsp+2B8h]; this
0x1800902c8  test    rdi, rdi
0x1800902cb  jz      loc_180090922
0x1800902d1  mov     rcx, [rsp+2B8h]; this
0x1800902d9  test    rbx, rbx
0x1800902dc  jz      loc_180090939
0x1800902e2  lea     rcx, [rsp+2B8h+var_208]
0x1800902ea  call    ?Instance@?$SingletonWithFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(void)
0x1800902ef  nop
0x1800902f0  xorps   xmm0, xmm0
0x1800902f3  movups  [rsp+2B8h+var_78], xmm0
0x1800902fb  mov     [rsp+2B8h+var_68], 0
0x180090307  mov     [rsp+2B8h+var_60], 7
0x180090313  xor     eax, eax
0x180090315  mov     word ptr [rsp+2B8h+var_78], ax
0x18009031d  mov     r15, [r12+28h]
0x180090322  xor     edx, edx; length
0x180090324  mov     rcx, rsi; string
0x180090327  call    cs:__imp_WindowsGetStringRawBuffer
0x18009032d  mov     r14, rax
0x180090330  mov     ecx, 110h; Size
0x180090335  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009033a  mov     r13, rax
0x18009033d  mov     [rsp+2B8h+var_230], rax
0x180090345  mov     dword ptr [rax+8], 1
0x18009034c  mov     dword ptr [rax+0Ch], 1
0x180090353  lea     rax, ??_7?$_Ref_count_obj2@VAdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo>::`vftable'
0x18009035a  mov     [r13+0], rax
0x18009035e  lea     rsi, [r13+10h]
0x180090362  mov     rdx, r14
0x180090365  lea     rcx, [rsp+2B8h+var_F8]
0x18009036d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180090372  nop
0x180090373  lea     r9, [r15+18h]
0x180090377  lea     r8, [rsp+2B8h+var_F8]
0x18009037f  mov     r14d, [rsp+2B8h+dwProcessId]
0x180090384  mov     edx, r14d
0x180090387  mov     rcx, rsi
0x18009038a  call    ??0AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEAA@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@6@@Z; Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::AdjustedAppDisplayInfo(ulong,std::wstring const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> const &)
0x18009038f  nop
0x180090390  lea     rcx, [rsp+2B8h+var_F8]
0x180090398  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009039d  nop
0x18009039e  mov     [rsp+2B8h+var_218], rsi
0x1800903a6  mov     [rsp+2B8h+var_210], r13
0x1800903ae  mov     r8b, 3
0x1800903b1  mov     dl, 1
0x1800903b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_CUASupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport> `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl(void)'::`2'::impl
0x1800903ba  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800903bf  mov     edx, r14d; dwProcessId
0x1800903c2  lea     rcx, [rsp+2B8h+phNewToken]; phNewToken
0x1800903c7  call    ?GetProcessTokenFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(ulong)
0x1800903cc  nop
0x1800903cd  mov     rdx, rax
0x1800903d0  lea     rcx, [rsp+2B8h+var_F8]
0x1800903d8  call    ?GetPackageFullNameFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1800903dd  mov     rdx, rax
0x1800903e0  lea     rcx, [rsp+2B8h+var_78]
0x1800903e8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800903ed  lea     rcx, [rsp+2B8h+var_F8]
0x1800903f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800903fa  nop
0x1800903fb  lea     rcx, [rsp+2B8h+phNewToken]
0x180090400  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180090405  cmp     [rsp+2B8h+var_68], 0
0x18009040e  jnz     short loc_18009041B
0x180090410  mov     [rsp+2B8h+phNewToken], 0
0x180090419  jmp     short loc_18009042D
0x18009041b  lea     rcx, [rsp+2B8h+var_78]
0x180090423  call    ?GetAppCategoryForPackage@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::GetAppCategoryForPackage(std::wstring const &)
0x180090428  mov     [rsp+2B8h+phNewToken], rax
0x18009042d  xorps   xmm0, xmm0
0x180090430  movups  [rsp+2B8h+var_D8], xmm0
0x180090438  mov     [rsp+2B8h+var_C8], 0
0x180090444  mov     r14d, 7
0x18009044a  mov     [rsp+2B8h+var_C0], r14
0x180090452  xor     ecx, ecx
0x180090454  mov     word ptr [rsp+2B8h+var_D8], cx
0x18009045c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline> `wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl(void)'::`2'::impl
0x180090463  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(void)
0x180090468  test    al, al
0x18009046a  jz      short loc_180090482
0x18009046c  lea     rdx, [rsi+0D0h]
0x180090473  lea     rcx, [rsp+2B8h+var_D8]
0x18009047b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180090480  jmp     short loc_18009049A
0x180090482  mov     rcx, rsi
0x180090485  call    ?get_AdjustedUserSidString@AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AdjustedUserSidString(void)
0x18009048a  mov     rdx, rax
0x18009048d  lea     rcx, [rsp+2B8h+var_D8]
0x180090495  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009049a  lea     rax, [rsi+38h]
0x18009049e  mov     [rsp+2B8h+var_230], rax
0x1800904a6  mov     rdx, [r12+28h]
0x1800904ab  add     rdx, 28h ; '('
0x1800904af  mov     r9d, [rsi+14h]
0x1800904b3  lea     r8, [rsp+2B8h+var_D8]
0x1800904bb  mov     rcx, rax
0x1800904be  call    ?IsCapabilityInUseByClient@CapabilitySessionManager@Private@CapabilityAccess@Internal@Windows@@KA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4AppIdType@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilitySessionManager::IsCapabilityInUseByClient(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType)
0x1800904c3  test    al, al
0x1800904c5  jz      loc_180090643
0x1800904cb  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x1800904d0  test    al, al
0x1800904d2  jz      loc_180090851
0x1800904d8  xorps   xmm0, xmm0
0x1800904db  movups  xmmword ptr [rsp+2B8h+pguid.Data1], xmm0
0x1800904e3  lea     rcx, [rsp+2B8h+pguid]; pguid
0x1800904eb  call    cs:__imp_CoCreateGuid
0x1800904f1  mov     rcx, [rsp+2B8h]; this
0x1800904f9  test    eax, eax
0x1800904fb  js      loc_180090951
0x180090501  xorps   xmm0, xmm0
0x180090504  movups  [rsp+2B8h+var_F8], xmm0
0x18009050c  mov     [rsp+2B8h+var_E8], 0
0x180090518  mov     [rsp+2B8h+var_E0], r14
0x180090520  xor     eax, eax
0x180090522  mov     word ptr [rsp+2B8h+var_F8], ax
0x18009052a  movups  [rsp+2B8h+var_B8], xmm0
0x180090532  mov     [rsp+2B8h+var_A8], rax
0x18009053a  mov     [rsp+2B8h+var_A0], r14
0x180090542  mov     word ptr [rsp+2B8h+var_B8], ax
0x18009054a  mov     rcx, rsi
0x18009054d  call    ?get_AppFriendlyName@AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName(void)
0x180090552  mov     r12, rax
0x180090555  lea     rax, [rsp+2B8h+var_1F8]
0x18009055d  mov     [rsp+2B8h+var_220], rax
0x180090565  lea     rdx, [rsp+2B8h+pguid]; rguid
0x18009056d  lea     rcx, [rsp+2B8h+var_1F8]; int
0x180090575  call    ?GUIDToString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; Windows::Internal::CapabilityAccess::Private::GUIDToString(_GUID const &)
0x18009057a  mov     r15, rax
0x18009057d  mov     esi, [rsi+14h]
0x180090580  mov     rcx, rbx
0x180090583  call    ?UTCFromDateTime@Private@CapabilityAccess@Internal@Windows@@YA_KUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(Windows::Foundation::DateTime)
0x180090588  mov     r14, rax
0x18009058b  mov     rcx, rdi
0x18009058e  call    ?UTCFromDateTime@Private@CapabilityAccess@Internal@Windows@@YA_KUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(Windows::Foundation::DateTime)
0x180090593  mov     rbx, rax
0x180090596  lea     rdx, [rsp+2B8h+var_98]
0x18009059e  mov     rcx, [rsp+2B8h+var_238]
0x1800905a6  mov     rcx, [rcx+28h]
0x1800905aa  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
0x1800905af  nop
0x1800905b0  mov     [rsp+2B8h+var_250], 4
0x1800905b8  lea     rcx, [rsp+2B8h+var_F8]
0x1800905c0  mov     [rsp+2B8h+var_258], rcx
0x1800905c5  lea     rcx, [rsp+2B8h+var_B8]
0x1800905cd  mov     [rsp+2B8h+var_260], rcx
0x1800905d2  mov     rcx, [rsp+2B8h+phNewToken]
0x1800905d7  mov     [rsp+2B8h+var_268], rcx
0x1800905dc  mov     [rsp+2B8h+var_270], r12
0x1800905e1  mov     dword ptr [rsp+2B8h+var_278], 2
0x1800905e9  mov     [rsp+2B8h+var_280], r15
0x1800905ee  mov     dword ptr [rsp+2B8h+var_288], esi
0x1800905f2  mov     [rsp+2B8h+var_290], r14
0x1800905f7  mov     [rsp+2B8h+var_298], rbx
0x1800905fc  mov     r9, [rsp+2B8h+var_230]
0x180090604  mov     r8d, [rsp+2B8h+dwProcessId]
0x180090609  mov     rdx, rax
0x18009060c  lea     rcx, [rsp+2B8h+var_D8]
0x180090614  call    ?RecordUsage@SQL@Private@CapabilityAccess@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K0_K1W4AppIdType@2345@V67@I0100I@Z; Windows::Internal::CapabilityAccess::Private::SQL::RecordUsage(std::wstring const &,std::wstring const &,ulong,std::wstring const &,unsigned __int64,unsigned __int64,Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring,uint,std::wstring const &,unsigned __int64,std::wstring const &,std::wstring const &,uint)
0x180090619  nop
0x18009061a  lea     rcx, [rsp+2B8h+var_98]
0x180090622  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090627  nop
0x180090628  lea     rcx, [rsp+2B8h+var_B8]
0x180090630  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090635  nop
0x180090636  lea     rcx, [rsp+2B8h+var_F8]
0x18009063e  jmp     loc_18009084B
0x180090643  mov     rcx, rsi
0x180090646  call    ?get_AppFriendlyName@AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName(void)
0x18009064b  mov     r12, rax
0x18009064e  mov     rcx, rdi
0x180090651  call    ?UTCFromDateTime@Private@CapabilityAccess@Internal@Windows@@YA_KUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(Windows::Foundation::DateTime)
0x180090656  mov     r15, rax
0x180090659  mov     r14d, [rsi+14h]
0x18009065d  lea     rdx, [rsp+2B8h+var_98]
0x180090665  mov     rcx, [rsp+2B8h+var_238]
0x18009066d  mov     rcx, [rcx+28h]
0x180090671  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
0x180090676  nop
0x180090677  mov     [rsp+2B8h+var_278], r12
0x18009067c  mov     ecx, [rsp+2B8h+dwProcessId]
0x180090680  mov     dword ptr [rsp+2B8h+var_280], ecx
0x180090684  mov     [rsp+2B8h+var_288], r15
0x180090689  mov     dword ptr [rsp+2B8h+var_290], 0
0x180090691  mov     dword ptr [rsp+2B8h+var_298], r14d
0x180090696  lea     r9, [rsi+38h]
0x18009069a  mov     r8, rax
0x18009069d  lea     rdx, [rsp+2B8h+var_D8]
0x1800906a5  call    ?SetLastUsedTime@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4AppIdType@2345@W4CapabilityUsageTimestampType@2345@_KK0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetLastUsedTime(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType,Windows::Internal::CapabilityAccess::Private::CapabilityUsageTimestampType,unsigned __int64,ulong,std::wstring const &)
0x1800906aa  nop
0x1800906ab  lea     rcx, [rsp+2B8h+var_98]
0x1800906b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800906b8  mov     rcx, rsi
0x1800906bb  call    ?get_AppFriendlyName@AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName(void)
0x1800906c0  mov     r12, rax
0x1800906c3  mov     rcx, rbx
0x1800906c6  call    ?UTCFromDateTime@Private@CapabilityAccess@Internal@Windows@@YA_KUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(Windows::Foundation::DateTime)
0x1800906cb  mov     r15, rax
0x1800906ce  mov     r14d, [rsi+14h]
0x1800906d2  lea     rdx, [rsp+2B8h+var_98]
0x1800906da  mov     rax, [rsp+2B8h+var_238]
0x1800906e2  mov     rcx, [rax+28h]
0x1800906e6  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
0x1800906eb  nop
0x1800906ec  mov     [rsp+2B8h+var_278], r12
0x1800906f1  mov     ecx, [rsp+2B8h+dwProcessId]
0x1800906f5  mov     dword ptr [rsp+2B8h+var_280], ecx
0x1800906f9  mov     [rsp+2B8h+var_288], r15
0x1800906fe  mov     dword ptr [rsp+2B8h+var_290], 1
0x180090706  mov     dword ptr [rsp+2B8h+var_298], r14d
0x18009070b  lea     r12, [rsi+38h]
0x18009070f  mov     r9, r12
0x180090712  mov     r8, rax
0x180090715  lea     rdx, [rsp+2B8h+var_D8]
0x18009071d  call    ?SetLastUsedTime@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4AppIdType@2345@W4CapabilityUsageTimestampType@2345@_KK0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetLastUsedTime(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType,Windows::Internal::CapabilityAccess::Private::CapabilityUsageTimestampType,unsigned __int64,ulong,std::wstring const &)
0x180090722  nop
0x180090723  lea     rcx, [rsp+2B8h+var_98]
0x18009072b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090730  mov     dl, 1
0x180090732  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se> `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl(void)'::`2'::impl
0x180090739  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009073e  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x180090743  test    al, al
0x180090745  jz      loc_180090851
0x18009074b  xorps   xmm0, xmm0
0x18009074e  movups  [rsp+2B8h+var_B8], xmm0
0x180090756  mov     [rsp+2B8h+var_A8], 0
0x180090762  mov     ecx, 7
0x180090767  mov     [rsp+2B8h+var_A0], rcx
0x18009076f  xor     eax, eax
0x180090771  mov     word ptr [rsp+2B8h+var_B8], ax
0x180090779  movups  [rsp+2B8h+var_F8], xmm0
0x180090781  mov     [rsp+2B8h+var_E8], rax
0x180090789  mov     [rsp+2B8h+var_E0], rcx
0x180090791  mov     word ptr [rsp+2B8h+var_F8], ax
0x180090799  mov     rcx, rsi
0x18009079c  call    ?get_AppFriendlyName@AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName(void)
0x1800907a1  mov     r15, rax
0x1800907a4  mov     esi, [rsi+14h]
0x1800907a7  mov     rcx, rbx
0x1800907aa  call    ?UTCFromDateTime@Private@CapabilityAccess@Internal@Windows@@YA_KUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(Windows::Foundation::DateTime)
0x1800907af  mov     r14, rax
0x1800907b2  mov     rcx, rdi
0x1800907b5  call    ?UTCFromDateTime@Private@CapabilityAccess@Internal@Windows@@YA_KUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::UTCFromDateTime(Windows::Foundation::DateTime)
0x1800907ba  mov     rbx, rax
0x1800907bd  lea     rdx, [rsp+2B8h+var_98]
0x1800907c5  mov     rax, [rsp+2B8h+var_238]
0x1800907cd  mov     rcx, [rax+28h]
0x1800907d1  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
  ... truncated ...
```

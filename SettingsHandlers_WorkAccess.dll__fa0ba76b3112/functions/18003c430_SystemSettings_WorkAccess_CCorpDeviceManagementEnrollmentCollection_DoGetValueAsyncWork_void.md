# SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection::DoGetValueAsyncWork(void)

- ea: `0x18003c430`
- end: `0x18003c7fc`
- name: `?DoGetValueAsyncWork@CCorpDeviceManagementEnrollmentCollection@WorkAccess@SystemSettings@@UEAAXXZ`
- size: `972`
- prototype: `void __fastcall(SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x18000c3f8`
- `0x180011710`
- `0x180015464`
- `0x180017a84`
- `0x180023164`
- `0x1800236d8`
- `0x1800236fc`
- `0x1800291ec`
- `0x180029234`
- `0x180029764`
- `0x18003ab34`
- `0x18003ab74`
- `0x18003b42c`
- `0x18003b6cc`
- `0x18003c430`
- `0x18003e154`
- `0x18003f5d0`
- `0x18004cba0`
- `0x18004cbdc`
- `0x18004cc18`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c4b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c4b3`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18003c4e0`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18003c4e0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c7d3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c7d3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003c45d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003c45d`

## string_xrefs

- `0x18003c477`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003c520`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003c5c7`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003c65d`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003c6fa`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
void __fastcall SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection::DoGetValueAsyncWork(
        SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection *this)
{
  char v2; // si
  int v3; // eax
  __int64 v4; // rdx
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  unsigned int (__fastcall *v9)(__int64, int *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int16 **); // rbx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  const unsigned __int16 *v16; // rax
  int v17; // eax
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int CurrentUserSid; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25[2]; // [rsp+20h] [rbp-99h] BYREF
  unsigned __int16 *v26; // [rsp+28h] [rbp-91h] BYREF
  __int64 v27; // [rsp+30h] [rbp-89h] BYREF
  __int64 v28; // [rsp+38h] [rbp-81h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-71h] BYREF
  __int64 v31; // [rsp+50h] [rbp-69h] BYREF
  int v32; // [rsp+58h] [rbp-61h]
  PSRWLOCK *p_SRWLock; // [rsp+60h] [rbp-59h] BYREF
  __int64 v34; // [rsp+68h] [rbp-51h] BYREF
  char v35; // [rsp+70h] [rbp-49h]
  _BYTE v36[32]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v37[32]; // [rsp+98h] [rbp-21h] BYREF
  _BYTE v38[32]; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = 1;
  v3 = RoInitialize(1);
  v32 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v3,
      v25[0]);
    return;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 264);
  Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*((_QWORD *)this + 26));
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v27 = 0;
  *(_QWORD *)v25 = 0;
  LOBYTE(v4) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage>::GetImpl'::`2'::impl,
    v4);
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v6 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v7 = v6(DatabaseManagerInstance, 134217729, &v27);
  if ( v7 >= 0 )
  {
    v8 = v27;
    v9 = *(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
    if ( v9(v8, v25) )
      goto LABEL_29;
    v28 = 0;
    v31 = 0;
    SRWLock = 0;
    if ( !SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton )
    {
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SRWLock);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
      goto LABEL_29;
    }
    v26 = 0;
    v10 = *(_QWORD *)v25;
    v11 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(**(_QWORD **)v25 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    v12 = v11(v10, &v26);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)(unsigned int)v12,
        v25[0]);
LABEL_27:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
      goto LABEL_28;
    }
    SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentID(v26);
    v13 = std::wstring::wstring(v38, v26);
    v15 = std::operator+<unsigned short>(v37, v14, v13);
    std::operator+<unsigned short>(v36, v15);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v38);
    v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
    SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentIDWithBraces(v16);
    v30 = 0;
    v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v25 + 48LL))(*(_QWORD *)v25, &v30);
    v18 = retaddr;
    if ( v17 >= 0 )
    {
      v17 = SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentType(v30);
      v18 = retaddr;
      if ( v17 >= 0 )
      {
        if ( ((1LL << v30) & 0x4000040) == 0 )
        {
          v20 = *(_QWORD *)v25;
          v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v25 + 112LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v31,
            0);
          v17 = v21(v20, &v31);
          v18 = retaddr;
          if ( v17 < 0 )
          {
            v19 = 203;
            goto LABEL_13;
          }
          p_SRWLock = &SRWLock;
          v34 = 0;
          v35 = 1;
          CurrentUserSid = SystemSettings::WorkAccess::GetCurrentUserSid(&v34);
          if ( CurrentUserSid >= 0 )
            v2 = 0;
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xD0,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
              (const char *)(unsigned int)CurrentUserSid,
              v25[0]);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_SRWLock);
          if ( v2 )
            goto LABEL_26;
        }
        v23 = *(_QWORD *)v25;
        v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v25 + 104LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v28,
          0);
        v17 = v24(v23, &v28);
        v18 = retaddr;
        if ( v17 >= 0 )
        {
          SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection::AddEnrollmentToSettingsList(
            (__int64)this - 32,
            v28,
            v30);
          SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18005B678);
          SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
          goto LABEL_26;
        }
        v19 = 214;
      }
      else
      {
        v19 = 195;
      }
    }
    else
    {
      v19 = 190;
    }
LABEL_13:
    wil::details::in1diag3::_Log_Hr(
      v18,
      (void *)v19,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v17,
      v25[0]);
LABEL_26:
    std::wstring::_Tidy_deallocate(v36);
    goto LABEL_27;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
    (const char *)(unsigned int)v7,
    v25[0]);
LABEL_29:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  RoUninitialize();
}

```

## disassembly

```asm
0x18003c430  push    rbp
0x18003c432  push    rbx
0x18003c433  push    rsi
0x18003c434  push    rdi
0x18003c435  push    r14
0x18003c437  push    r15
0x18003c439  lea     rbp, [rsp-2Fh]
0x18003c43e  sub     rsp, 0E8h
0x18003c445  mov     rax, cs:__security_cookie
0x18003c44c  xor     rax, rsp
0x18003c44f  mov     [rbp+57h+var_38], rax
0x18003c453  mov     r14, rcx
0x18003c456  mov     esi, 1
0x18003c45b  mov     ecx, esi
0x18003c45d  call    cs:__imp_RoInitialize
0x18003c464  nop     dword ptr [rax+rax+00h]
0x18003c469  mov     [rbp+57h+var_B8], eax
0x18003c46c  mov     rcx, [rbp+5Fh]; this
0x18003c470  test    eax, eax
0x18003c472  jns     short loc_18003C48E
0x18003c474  mov     r9d, eax; char *
0x18003c477  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003c47e  mov     edx, 86h; void *
0x18003c483  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c488  nop
0x18003c489  jmp     loc_18003C7DF
0x18003c48e  lea     rdx, [r14+108h]
0x18003c495  lea     rcx, [rbp+57h+SRWLock]
0x18003c499  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003c49e  mov     rcx, [r14+0D0h]
0x18003c4a5  call    ?Clear@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJXZ; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(void)
0x18003c4aa  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003c4ae  test    rcx, rcx
0x18003c4b1  jz      short loc_18003C4BF
0x18003c4b3  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c4ba  nop     dword ptr [rax+rax+00h]
0x18003c4bf  mov     [rsp+110h+var_E0], 0
0x18003c4c8  mov     qword ptr [rsp+110h+var_F0], 0; int
0x18003c4d1  mov     dl, sil
0x18003c4d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage> `wil::Feature<__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage>::GetImpl(void)'::`2'::impl
0x18003c4db  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedEnrollmentLandingPage>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003c4e0  call    cs:__imp_GetDatabaseManagerInstance
0x18003c4e7  nop     dword ptr [rax+rax+00h]
0x18003c4ec  mov     rdi, rax
0x18003c4ef  mov     rcx, [rax]
0x18003c4f2  mov     rbx, [rcx+20h]
0x18003c4f6  lea     rcx, [rsp+110h+var_E0]
0x18003c4fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c500  lea     r8, [rsp+110h+var_E0]
0x18003c505  mov     edx, 8000001h
0x18003c50a  mov     rcx, rdi
0x18003c50d  mov     rax, rbx
0x18003c510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c515  mov     rcx, [rbp+5Fh]; this
0x18003c519  test    eax, eax
0x18003c51b  jns     short loc_18003C536
0x18003c51d  mov     r9d, eax; char *
0x18003c520  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003c527  mov     edx, 0A5h; void *
0x18003c52c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c531  jmp     loc_18003C7BD
0x18003c536  mov     rdi, [rsp+110h+var_E0]
0x18003c53b  mov     rax, [rdi]
0x18003c53e  mov     rbx, [rax+18h]
0x18003c542  lea     rcx, [rsp+110h+var_F0]
0x18003c547  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c54c  lea     rdx, [rsp+110h+var_F0]
0x18003c551  mov     rcx, rdi
0x18003c554  mov     rax, rbx
0x18003c557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c55c  test    eax, eax
0x18003c55e  jnz     loc_18003C7BD
0x18003c564  mov     [rsp+110h+var_D8], 0
0x18003c56d  mov     [rbp+57h+var_C0], 0
0x18003c575  mov     [rbp+57h+SRWLock], 0
0x18003c57d  cmp     cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A, 0; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x18003c585  jz      loc_18003C79E
0x18003c58b  mov     [rsp+110h+var_E8], 0
0x18003c594  mov     rdi, qword ptr [rsp+110h+var_F0]
0x18003c599  mov     rax, [rdi]
0x18003c59c  mov     rbx, [rax+20h]
0x18003c5a0  xor     edx, edx
0x18003c5a2  lea     rcx, [rsp+110h+var_E8]
0x18003c5a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003c5ac  lea     rdx, [rsp+110h+var_E8]
0x18003c5b1  mov     rcx, rdi
0x18003c5b4  mov     rax, rbx
0x18003c5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5bc  mov     rcx, [rbp+5Fh]; this
0x18003c5c0  test    eax, eax
0x18003c5c2  jns     short loc_18003C5DD
0x18003c5c4  mov     r9d, eax; char *
0x18003c5c7  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003c5ce  mov     edx, 0B4h; void *
0x18003c5d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c5d8  jmp     loc_18003C793
0x18003c5dd  mov     rcx, [rsp+110h+var_E8]; unsigned __int16 *
0x18003c5e2  call    ?SetEnrollmentID@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJQEBG@Z; SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentID(ushort const * const)
0x18003c5e7  mov     rdx, [rsp+110h+var_E8]
0x18003c5ec  lea     rcx, [rbp+57h+var_58]
0x18003c5f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c5f5  nop
0x18003c5f6  mov     r8, rax
0x18003c5f9  lea     rcx, [rbp+57h+var_78]
0x18003c5fd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G$$QEAV10@@Z; std::operator+<ushort>(ushort,std::wstring &&)
0x18003c602  nop
0x18003c603  mov     rdx, rax
0x18003c606  lea     rcx, [rbp+57h+var_98]
0x18003c60a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@G@Z; std::operator+<ushort>(std::wstring &&,ushort)
0x18003c60f  nop
0x18003c610  lea     rcx, [rbp+57h+var_78]
0x18003c614  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c619  nop
0x18003c61a  lea     rcx, [rbp+57h+var_58]
0x18003c61e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c623  lea     rcx, [rbp+57h+var_98]
0x18003c627  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c62c  mov     rcx, rax; unsigned __int16 *
0x18003c62f  call    ?SetEnrollmentIDWithBraces@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJQEBG@Z; SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentIDWithBraces(ushort const * const)
0x18003c634  mov     [rbp+57h+var_C8], 0
0x18003c63b  mov     rcx, qword ptr [rsp+110h+var_F0]
0x18003c640  mov     rax, [rcx]
0x18003c643  lea     rdx, [rbp+57h+var_C8]
0x18003c647  mov     rax, [rax+30h]
0x18003c64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c650  mov     rcx, [rbp+5Fh]; this
0x18003c654  test    eax, eax
0x18003c656  jns     short loc_18003C671
0x18003c658  mov     edx, 0BEh; void *
0x18003c65d  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003c664  mov     r9d, eax; char *
0x18003c667  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c66c  jmp     loc_18003C789
0x18003c671  mov     ecx, [rbp+57h+var_C8]
0x18003c674  call    ?SetEnrollmentType@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJW4EnrollmentEnrollType@@@Z; SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentType(EnrollmentEnrollType)
0x18003c679  mov     rcx, [rbp+5Fh]
0x18003c67d  test    eax, eax
0x18003c67f  jns     short loc_18003C688
0x18003c681  mov     edx, 0C3h
0x18003c686  jmp     short loc_18003C65D
0x18003c688  mov     ecx, [rbp+57h+var_C8]
0x18003c68b  mov     rax, rsi
0x18003c68e  shl     rax, cl
0x18003c691  test    rax, 4000040h
0x18003c697  jnz     loc_18003C71E
0x18003c69d  mov     rdi, qword ptr [rsp+110h+var_F0]
0x18003c6a2  mov     rax, [rdi]
0x18003c6a5  mov     rbx, [rax+70h]
0x18003c6a9  xor     edx, edx
0x18003c6ab  lea     rcx, [rbp+57h+var_C0]
0x18003c6af  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003c6b4  lea     rdx, [rbp+57h+var_C0]
0x18003c6b8  mov     rcx, rdi
0x18003c6bb  mov     rax, rbx
0x18003c6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6c3  mov     rcx, [rbp+5Fh]
0x18003c6c7  test    eax, eax
0x18003c6c9  jns     short loc_18003C6D2
0x18003c6cb  mov     edx, 0CBh
0x18003c6d0  jmp     short loc_18003C65D
0x18003c6d2  lea     rax, [rbp+57h+SRWLock]
0x18003c6d6  mov     [rbp+57h+var_B0], rax
0x18003c6da  mov     [rbp+57h+var_A8], 0
0x18003c6e2  mov     [rbp+57h+var_A0], sil
0x18003c6e6  lea     rcx, [rbp+57h+var_A8]
0x18003c6ea  call    SystemSettings__WorkAccess__GetCurrentUserSid
0x18003c6ef  mov     rcx, [rbp+5Fh]; this
0x18003c6f3  test    eax, eax
0x18003c6f5  jns     short loc_18003C70D
0x18003c6f7  mov     r9d, eax; char *
0x18003c6fa  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003c701  mov     edx, 0D0h; void *
0x18003c706  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c70b  jmp     short loc_18003C710
0x18003c70d  xor     sil, sil
0x18003c710  lea     rcx, [rbp+57h+var_B0]
0x18003c714  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18003c719  test    sil, sil
0x18003c71c  jnz     short loc_18003C789
0x18003c71e  mov     rdi, qword ptr [rsp+110h+var_F0]
0x18003c723  mov     rax, [rdi]
0x18003c726  mov     rbx, [rax+68h]
0x18003c72a  xor     edx, edx
0x18003c72c  lea     rcx, [rsp+110h+var_D8]
0x18003c731  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003c736  lea     rdx, [rsp+110h+var_D8]
0x18003c73b  mov     rcx, rdi
0x18003c73e  mov     rax, rbx
0x18003c741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c746  mov     rcx, [rbp+5Fh]
0x18003c74a  test    eax, eax
0x18003c74c  jns     short loc_18003C758
0x18003c74e  mov     edx, 0D6h
0x18003c753  jmp     loc_18003C65D
0x18003c758  mov     r8d, [rbp+57h+var_C8]
0x18003c75c  mov     rdx, [rsp+110h+var_D8]
0x18003c761  lea     rcx, [r14-20h]
0x18003c765  call    ?AddEnrollmentToSettingsList@CCorpDeviceManagementEnrollmentCollection@WorkAccess@SystemSettings@@AEAAJPEBGW4EnrollmentEnrollType@@@Z; SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection::AddEnrollmentToSettingsList(ushort const *,EnrollmentEnrollType)
0x18003c76a  lea     rdx, stru_18005B678; unsigned __int16 *
0x18003c771  mov     rcx, r14; this
0x18003c774  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18003c779  lea     rdx, aIsapplicable; "IsApplicable"
0x18003c780  mov     rcx, r14; this
0x18003c783  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18003c788  nop
0x18003c789  lea     rcx, [rbp+57h+var_98]
0x18003c78d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c792  nop
0x18003c793  lea     rcx, [rsp+110h+var_E8]
0x18003c798  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c79d  nop
0x18003c79e  lea     rcx, [rbp+57h+SRWLock]
0x18003c7a2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c7a7  nop
0x18003c7a8  lea     rcx, [rbp+57h+var_C0]
0x18003c7ac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c7b1  nop
0x18003c7b2  lea     rcx, [rsp+110h+var_D8]
0x18003c7b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c7bc  nop
0x18003c7bd  lea     rcx, [rsp+110h+var_F0]
0x18003c7c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c7c7  nop
0x18003c7c8  lea     rcx, [rsp+110h+var_E0]
0x18003c7cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c7d2  nop
0x18003c7d3  call    cs:__imp_RoUninitialize
0x18003c7da  nop     dword ptr [rax+rax+00h]
0x18003c7df  mov     rcx, [rbp+57h+var_38]
0x18003c7e3  xor     rcx, rsp; StackCookie
0x18003c7e6  call    __security_check_cookie
0x18003c7eb  add     rsp, 0E8h
0x18003c7f2  pop     r15
0x18003c7f4  pop     r14
0x18003c7f6  pop     rdi
0x18003c7f7  pop     rsi
0x18003c7f8  pop     rbx
0x18003c7f9  pop     rbp
0x18003c7fa  retn
```

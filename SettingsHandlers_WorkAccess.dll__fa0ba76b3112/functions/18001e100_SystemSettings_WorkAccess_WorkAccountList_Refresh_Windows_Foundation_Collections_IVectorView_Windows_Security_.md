# SystemSettings::WorkAccess::WorkAccountList::Refresh(Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *)

- ea: `0x18001e100`
- end: `0x18001e937`
- name: `?Refresh@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `2103`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b060`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x180015464`
- `0x180016840`
- `0x180018c94`
- `0x18001937c`
- `0x18001947c`
- `0x18001af64`
- `0x18001beac`
- `0x18001ce98`
- `0x18001d088`
- `0x18001d538`
- `0x18001d5c0`
- `0x18001e100`
- `0x18001efe0`
- `0x18001f81c`
- `0x180020584`
- `0x180042c88`
- `0x180043448`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e830`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e859`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e8b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e830`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e859`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e8b2`

## string_xrefs

- `0x18001e144`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e17d`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e356`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e3a1`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e40d`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e49d`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e4f8`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e5cd`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e647`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e6a4`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e7bb`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001e816`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::Refresh(PSRWLOCK *this, __int64 a2)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  CloudDomainJoin::DataModel *v8; // rcx
  char v9; // si
  unsigned int v10; // r14d
  __int64 (__fastcall *v11)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **); // rbx
  int v12; // eax
  __int64 v13; // rdx
  unsigned __int16 **v14; // r8
  int CloudDomainInfo; // eax
  __int64 v16; // rdx
  unsigned __int16 **v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  RTL_SRWLOCK *v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  unsigned __int16 **v24; // r9
  int Name; // eax
  __int64 v26; // rdx
  unsigned __int64 v27; // r9
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  void *v32; // rcx
  PSRWLOCK v33; // rsi
  int v34; // eax
  int v35; // eax
  PSRWLOCK *v37; // [rsp+20h] [rbp-89h]
  struct Windows::Security::Credentials::IWebAccount *v38; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 *v39; // [rsp+38h] [rbp-71h] BYREF
  __int64 v40; // [rsp+40h] [rbp-69h]
  __int64 v41; // [rsp+48h] [rbp-61h]
  unsigned __int16 *v42; // [rsp+50h] [rbp-59h] BYREF
  __int64 v43; // [rsp+58h] [rbp-51h]
  __int64 v44; // [rsp+60h] [rbp-49h]
  __int64 v45; // [rsp+68h] [rbp-41h] BYREF
  __int64 v46; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int64 v47; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v48; // [rsp+80h] [rbp-29h] BYREF
  PSRWLOCK v49; // [rsp+88h] [rbp-21h]
  __int64 v50; // [rsp+90h] [rbp-19h]
  PSRWLOCK SRWLock[2]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v53; // [rsp+B0h] [rbp+7h] BYREF
  _QWORD v54[9]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  PSRWLOCK v56; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned int v57; // [rsp+120h] [rbp+77h] BYREF
  int v58; // [rsp+128h] [rbp+7Fh] BYREF

  v57 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v57);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v4,
      (int)v37);
    return (unsigned int)v5;
  }
  v46 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<SystemSettings::DataModel::ISettingItem,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<SystemSettings::DataModel::ISettingItem *>>>(
         v6,
         &v46);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v7,
      (int)v37);
    goto LABEL_88;
  }
  v9 = 0;
  if ( !v57 )
    goto LABEL_20;
  v10 = 0;
  do
  {
    v38 = 0;
    v45 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v12 = v11(a2, v10, &v38);
    v5 = v12;
    if ( v12 < 0 )
    {
      v13 = 83;
      goto LABEL_29;
    }
    LOBYTE(v56) = 0;
    if ( (int)SystemSettings::WorkAccess::WorkAccountList::IsAADJAccount(
                (SystemSettings::WorkAccess::WorkAccountList *)this,
                v38,
                (bool *)&v56) >= 0
      && (_BYTE)v56 )
    {
      SRWLock[0] = this[38];
      LODWORD(v56) = 1;
      v47 = (unsigned __int64)v38;
      v12 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,enum SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(
              &v45,
              &v47,
              &v56,
              SRWLock);
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 88;
        goto LABEL_29;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 104LL))(v46, v45);
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 89;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v12,
          (int)v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        goto LABEL_88;
      }
      goto LABEL_17;
    }
    if ( (int)SystemSettings::WorkAccess::WorkAccountList::IsWorkAccount(
                (SystemSettings::WorkAccess::WorkAccountList *)this,
                v38,
                (bool *)&v56) >= 0
      && (_BYTE)v56 )
    {
      SRWLock[0] = this[38];
      LODWORD(v56) = 0;
      v47 = (unsigned __int64)v38;
      v12 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,enum SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(
              &v45,
              &v47,
              &v56,
              SRWLock);
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 94;
        goto LABEL_29;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 104LL))(v46, v45);
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 95;
        goto LABEL_29;
      }
LABEL_17:
      v9 = 1;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    ++v10;
  }
  while ( v10 < v57 );
  if ( v9 )
    goto LABEL_48;
LABEL_20:
  if ( !CloudDomainJoin::DataModel::IsMachineCloudDomainJoined(v8) )
    goto LABEL_48;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
  v43 = -1;
  v44 = -1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v39);
  v40 = -1;
  v41 = -1;
  CloudDomainInfo = SystemSettings::WorkAccess::GetCloudDomainInfo((SystemSettings::WorkAccess *)&v39, &v42, v14);
  v5 = CloudDomainInfo;
  if ( CloudDomainInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)CloudDomainInfo,
      (int)v37);
    goto LABEL_23;
  }
  v48 = 0;
  v49 = 0;
  v50 = 0;
  if ( v39 )
  {
    LOBYTE(v16) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::GetImpl'::`2'::impl,
      v16);
    v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v48,
            &_ImageBase,
            128);
    v5 = v18;
    if ( v18 >= 0 )
      goto LABEL_37;
    v19 = 128;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v18,
      (int)v37);
    goto LABEL_34;
  }
  LOBYTE(v16) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::GetImpl'::`2'::impl,
    v16);
  v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
          &v48,
          &_ImageBase,
          129);
  v5 = v18;
  if ( v18 < 0 )
  {
    v19 = 115;
    goto LABEL_33;
  }
LABEL_37:
  v20 = 0;
  memset(v54, 0, 24);
  if ( v42 )
  {
    v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            v54,
            &_ImageBase,
            105);
    v5 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v21,
        (int)v37);
      goto LABEL_40;
    }
    v20 = (RTL_SRWLOCK *)v54[0];
  }
  v52 = 0;
  LODWORD(v56) = 2;
  SRWLock[0] = v20;
  v47 = v48;
  v22 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,unsigned short const *,unsigned short const *,enum SystemSettings::WorkAccess::WorkAccountType>(
          &v52,
          &v47,
          SRWLock,
          &v56);
  v5 = v22;
  if ( v22 >= 0 )
  {
    v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 104LL))(v46, v52);
    v5 = v22;
    if ( v22 < 0 )
    {
      v23 = 148;
      goto LABEL_44;
    }
    v9 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v54);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v48);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v39);
LABEL_48:
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    LOBYTE(v56) = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v39);
    v40 = -1;
    v41 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
    v43 = -1;
    v44 = -1;
    Name = SystemSettings::WorkAccess::IsMachineDomainJoinedAndGetName(
             (SystemSettings::WorkAccess *)&v56,
             (bool *)&v42,
             &v39,
             v24);
    v5 = Name;
    if ( Name < 0 )
    {
      v26 = 157;
LABEL_50:
      v27 = (unsigned int)Name;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)v27,
        (int)v37);
LABEL_52:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v39);
      v17 = &v42;
      goto LABEL_24;
    }
    if ( (_BYTE)v56 )
    {
      v48 = 0;
      v49 = 0;
      v50 = 0;
      if ( v39 )
      {
        v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
                &v48,
                &_ImageBase,
                111);
        v5 = v28;
        if ( v28 < 0 )
        {
          v29 = 165;
          goto LABEL_59;
        }
      }
      else
      {
        v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
                &v48,
                &_ImageBase,
                112);
        v5 = v28;
        if ( v28 < 0 )
        {
          v29 = 170;
LABEL_59:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
            (const char *)(unsigned int)v28,
            (int)v37);
LABEL_60:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v48);
          goto LABEL_52;
        }
      }
      v53 = 0;
      LODWORD(v56) = 3;
      SRWLock[0] = (PSRWLOCK)v42;
      v47 = v48;
      v30 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,unsigned short const *,unsigned short const *,enum SystemSettings::WorkAccess::WorkAccountType>(
              &v53,
              &v47,
              SRWLock,
              &v56);
      v5 = v30;
      if ( v30 < 0 )
      {
        v31 = 175;
LABEL_63:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v30,
          (int)v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
        goto LABEL_60;
      }
      v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 104LL))(v46, v53);
      v5 = v30;
      if ( v30 < 0 )
      {
        v31 = 177;
        goto LABEL_63;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v48);
    }
    else if ( !v9 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v56, this + 36);
      *((_BYTE *)this + 296) = 1;
      if ( v56 )
        ReleaseSRWLockExclusive(v56);
      goto LABEL_85;
    }
    LODWORD(v56) = 0;
    Name = (*(__int64 (__fastcall **)(__int64, PSRWLOCK *))(*(_QWORD *)v46 + 56LL))(v46, &v56);
    v5 = Name;
    if ( Name < 0 )
    {
      v26 = 184;
      goto LABEL_50;
    }
    if ( (_DWORD)v56 )
    {
      SRWLock[0] = 0;
      v47 = 0;
      v5 = ULongLongMult((unsigned int)v56, 8u, &v47);
      if ( v5 < 0 || (v5 = CTCoAllocPolicy::Alloc(v32, 1u, v47, (void **)SRWLock), v5 < 0) )
      {
        v27 = (unsigned int)v5;
        v26 = 190;
        goto LABEL_51;
      }
      v33 = SRWLock[0];
      v48 = __PAIR64__(HIDWORD(SRWLock[0]), (unsigned int)v56);
      v49 = SRWLock[0];
      LOBYTE(v50) = 1;
      v37 = &v56;
      v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, PSRWLOCK))(*(_QWORD *)v46 + 128LL))(
              v46,
              0,
              (unsigned int)v56,
              SRWLock[0]);
      v5 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCF,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v34,
          (int)&v56);
        LOBYTE(v50) = 0;
        lambda_48055febb604107426bae3a2468c7611_::operator()(&v48);
        goto LABEL_52;
      }
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, this + 36);
      *((_BYTE *)this + 296) = 1;
      v35 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::ReplaceAll(
              this[26],
              (unsigned int)v56,
              v33);
      v5 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v35,
          (int)&v56);
        if ( SRWLock[0] )
          ReleaseSRWLockExclusive(SRWLock[0]);
        LOBYTE(v50) = 0;
        lambda_48055febb604107426bae3a2468c7611_::operator()(&v48);
        goto LABEL_52;
      }
      if ( SRWLock[0] )
        ReleaseSRWLockExclusive(SRWLock[0]);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(
        (SystemSettings::DataModel::CSettingBase *)this,
        (const unsigned __int16 *)&stru_18005B678);
      LOBYTE(v50) = 0;
      lambda_48055febb604107426bae3a2468c7611_::operator()(&v48);
    }
LABEL_85:
    v58 = 0;
    Name = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 56LL))(v46, &v58);
    v5 = Name;
    if ( Name >= 0 )
    {
      *((_BYTE *)this + 298) = v58 != 0;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(
        (SystemSettings::DataModel::CSettingBase *)this,
        L"IsApplicable");
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v39);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
      v5 = 0;
      goto LABEL_88;
    }
    v26 = 230;
    goto LABEL_50;
  }
  v23 = 147;
LABEL_44:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
    (const char *)(unsigned int)v22,
    (int)v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
LABEL_40:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v54);
LABEL_34:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v48);
LABEL_23:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
  v17 = &v39;
LABEL_24:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v17);
LABEL_88:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e100  push    rbp
0x18001e102  push    rbx
0x18001e103  push    rsi
0x18001e104  push    rdi
0x18001e105  push    r12
0x18001e107  push    r14
0x18001e109  push    r15
0x18001e10b  lea     rbp, [rsp-27h]
0x18001e110  sub     rsp, 0D0h
0x18001e117  mov     r15, rdx
0x18001e11a  mov     rdi, rcx
0x18001e11d  xor     r12d, r12d
0x18001e120  mov     [rbp+57h+arg_10], r12d
0x18001e124  mov     rax, [rdx]
0x18001e127  lea     rdx, [rbp+57h+arg_10]
0x18001e12b  mov     rcx, r15
0x18001e12e  mov     rax, [rax+38h]
0x18001e132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e137  mov     ebx, eax
0x18001e139  test    eax, eax
0x18001e13b  jns     short loc_18001E15A
0x18001e13d  mov     rcx, [rbp+5Fh]; this
0x18001e141  mov     r9d, eax; char *
0x18001e144  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001e14b  lea     edx, [r12+47h]; void *
0x18001e150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e155  jmp     loc_18001E922
0x18001e15a  mov     [rbp+57h+var_90], r12
0x18001e15e  lea     rcx, [rbp+57h+var_90]
0x18001e162  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e167  lea     rdx, [rbp+57h+var_90]
0x18001e16b  call    ??$CreateExternalObjectVector@UISettingItem@DataModel@SystemSettings@@V?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$DefaultVectorOptions@PEAUISettingItem@DataModel@SystemSettings@@@5678@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$DefaultVectorOptions@PEAUISettingItem@DataModel@SystemSettings@@@5678@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<SystemSettings::DataModel::ISettingItem,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<SystemSettings::DataModel::ISettingItem *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<SystemSettings::DataModel::ISettingItem *>> * *)
0x18001e170  mov     ebx, eax
0x18001e172  test    eax, eax
0x18001e174  jns     short loc_18001E193
0x18001e176  mov     rcx, [rbp+5Fh]; this
0x18001e17a  mov     r9d, eax; char *
0x18001e17d  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001e184  mov     edx, 49h ; 'I'; void *
0x18001e189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e18e  jmp     loc_18001E919
0x18001e193  mov     sil, r12b
0x18001e196  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001e19a  mov     eax, [rbp+57h+arg_10]
0x18001e19d  test    eax, eax
0x18001e19f  jz      loc_18001E2F5
0x18001e1a5  mov     r14d, r12d
0x18001e1a8  mov     [rbp+57h+var_D0], r12
0x18001e1ac  mov     [rbp+57h+var_98], r12
0x18001e1b0  mov     rax, [r15]
0x18001e1b3  mov     rbx, [rax+30h]
0x18001e1b7  lea     rcx, [rbp+57h+var_D0]
0x18001e1bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e1c0  lea     r8, [rbp+57h+var_D0]
0x18001e1c4  mov     edx, r14d
0x18001e1c7  mov     rcx, r15
0x18001e1ca  mov     rax, rbx
0x18001e1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1d2  mov     ebx, eax
0x18001e1d4  test    eax, eax
0x18001e1d6  js      loc_18001E395
0x18001e1dc  mov     byte ptr [rbp+57h+arg_8], r12b
0x18001e1e0  lea     r8, [rbp+57h+arg_8]; bool *
0x18001e1e4  mov     rdx, [rbp+57h+var_D0]; struct Windows::Security::Credentials::IWebAccount *
0x18001e1e8  mov     rcx, rdi; this
0x18001e1eb  call    ?IsAADJAccount@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z; SystemSettings::WorkAccess::WorkAccountList::IsAADJAccount(Windows::Security::Credentials::IWebAccount *,bool *)
0x18001e1f0  test    eax, eax
0x18001e1f2  js      short loc_18001E257
0x18001e1f4  cmp     byte ptr [rbp+57h+arg_8], r12b
0x18001e1f8  jz      short loc_18001E257
0x18001e1fa  mov     rax, [rdi+130h]
0x18001e201  mov     [rbp+57h+SRWLock], rax
0x18001e205  mov     dword ptr [rbp+57h+arg_8], 1
0x18001e20c  mov     rax, [rbp+57h+var_D0]
0x18001e210  mov     [rbp+57h+var_88], rax
0x18001e214  lea     r9, [rbp+57h+SRWLock]
0x18001e218  lea     r8, [rbp+57h+arg_8]
0x18001e21c  lea     rdx, [rbp+57h+var_88]
0x18001e220  lea     rcx, [rbp+57h+var_98]
0x18001e224  call    ??$MakeAndInitialize@VWorkAccountItem@WorkAccess@SystemSettings@@UISettingItem@DataModel@3@PEAUIWebAccount@Credentials@Security@Windows@@W4WorkAccountType@23@PEAUITokenBrokerInternalStatics@Web@Authentication@8Internal@9@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@012@$$QEAPEAUIWebAccount@Credentials@Security@Windows@@$$QEAW4WorkAccountType@WorkAccess@SystemSettings@@$$QEAPEAUITokenBrokerInternalStatics@Web@Authentication@6Internal@7@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>,Windows::Security::Credentials::IWebAccount * &&,SystemSettings::WorkAccess::WorkAccountType &&,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &&)
0x18001e229  mov     ebx, eax
0x18001e22b  test    eax, eax
0x18001e22d  js      loc_18001E380
0x18001e233  mov     rcx, [rbp+57h+var_90]
0x18001e237  mov     rax, [rcx]
0x18001e23a  mov     rdx, [rbp+57h+var_98]
0x18001e23e  mov     rax, [rax+68h]
0x18001e242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e247  mov     ebx, eax
0x18001e249  test    eax, eax
0x18001e24b  jns     short loc_18001E2C5
0x18001e24d  mov     edx, 59h ; 'Y'
0x18001e252  jmp     loc_18001E39A
0x18001e257  lea     r8, [rbp+57h+arg_8]; bool *
0x18001e25b  mov     rdx, [rbp+57h+var_D0]; struct Windows::Security::Credentials::IWebAccount *
0x18001e25f  mov     rcx, rdi; this
0x18001e262  call    ?IsWorkAccount@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z; SystemSettings::WorkAccess::WorkAccountList::IsWorkAccount(Windows::Security::Credentials::IWebAccount *,bool *)
0x18001e267  test    eax, eax
0x18001e269  js      short loc_18001E2C8
0x18001e26b  cmp     byte ptr [rbp+57h+arg_8], r12b
0x18001e26f  jz      short loc_18001E2C8
0x18001e271  mov     rax, [rdi+130h]
0x18001e278  mov     [rbp+57h+SRWLock], rax
0x18001e27c  mov     dword ptr [rbp+57h+arg_8], r12d
0x18001e280  mov     rax, [rbp+57h+var_D0]
0x18001e284  mov     [rbp+57h+var_88], rax
0x18001e288  lea     r9, [rbp+57h+SRWLock]
0x18001e28c  lea     r8, [rbp+57h+arg_8]
0x18001e290  lea     rdx, [rbp+57h+var_88]
0x18001e294  lea     rcx, [rbp+57h+var_98]
0x18001e298  call    ??$MakeAndInitialize@VWorkAccountItem@WorkAccess@SystemSettings@@UISettingItem@DataModel@3@PEAUIWebAccount@Credentials@Security@Windows@@W4WorkAccountType@23@PEAUITokenBrokerInternalStatics@Web@Authentication@8Internal@9@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@012@$$QEAPEAUIWebAccount@Credentials@Security@Windows@@$$QEAW4WorkAccountType@WorkAccess@SystemSettings@@$$QEAPEAUITokenBrokerInternalStatics@Web@Authentication@6Internal@7@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>,Windows::Security::Credentials::IWebAccount * &&,SystemSettings::WorkAccess::WorkAccountType &&,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &&)
0x18001e29d  mov     ebx, eax
0x18001e29f  test    eax, eax
0x18001e2a1  js      loc_18001E38E
0x18001e2a7  mov     rcx, [rbp+57h+var_90]
0x18001e2ab  mov     rax, [rcx]
0x18001e2ae  mov     rdx, [rbp+57h+var_98]
0x18001e2b2  mov     rax, [rax+68h]
0x18001e2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2bb  mov     ebx, eax
0x18001e2bd  test    eax, eax
0x18001e2bf  js      loc_18001E387
0x18001e2c5  mov     sil, 1
0x18001e2c8  lea     rcx, [rbp+57h+var_98]
0x18001e2cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e2d1  nop
0x18001e2d2  lea     rcx, [rbp+57h+var_D0]
0x18001e2d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e2db  inc     r14d
0x18001e2de  cmp     r14d, [rbp+57h+arg_10]
0x18001e2e2  jb      loc_18001E1A8
0x18001e2e8  test    sil, sil
0x18001e2eb  jnz     loc_18001E56C
0x18001e2f1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001e2f5  call    ?IsMachineCloudDomainJoined@DataModel@CloudDomainJoin@@YA_NXZ; CloudDomainJoin::DataModel::IsMachineCloudDomainJoined(void)
0x18001e2fa  test    al, al
0x18001e2fc  jz      loc_18001E56C
0x18001e302  mov     [rbp+57h+var_C8], r12
0x18001e306  mov     [rbp+57h+var_C0], r12
0x18001e30a  mov     [rbp+57h+var_B8], r12
0x18001e30e  mov     [rbp+57h+var_B0], r12
0x18001e312  mov     [rbp+57h+var_A8], r12
0x18001e316  mov     [rbp+57h+var_A0], r12
0x18001e31a  lea     rcx, [rbp+57h+var_B0]
0x18001e31e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e323  mov     [rbp+57h+var_A8], rbx
0x18001e327  mov     [rbp+57h+var_A0], rbx
0x18001e32b  lea     rcx, [rbp+57h+var_C8]
0x18001e32f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e334  mov     [rbp+57h+var_C0], rbx
0x18001e338  mov     [rbp+57h+var_B8], rbx
0x18001e33c  lea     rdx, [rbp+57h+var_B0]; unsigned __int16 **
0x18001e340  lea     rcx, [rbp+57h+var_C8]; this
0x18001e344  call    ?GetCloudDomainInfo@WorkAccess@SystemSettings@@YAJPEAPEAG0@Z; SystemSettings::WorkAccess::GetCloudDomainInfo(ushort * *,ushort * *)
0x18001e349  mov     ebx, eax
0x18001e34b  test    eax, eax
0x18001e34d  jns     short loc_18001E3C6
0x18001e34f  mov     rcx, [rbp+5Fh]; this
0x18001e353  mov     r9d, eax; char *
0x18001e356  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001e35d  mov     edx, 6Bh ; 'k'; void *
0x18001e362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e367  nop
0x18001e368  lea     rcx, [rbp+57h+var_B0]
0x18001e36c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e371  nop
0x18001e372  lea     rcx, [rbp+57h+var_C8]
0x18001e376  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e37b  jmp     loc_18001E919
0x18001e380  mov     edx, 58h ; 'X'
0x18001e385  jmp     short loc_18001E39A
0x18001e387  mov     edx, 5Fh ; '_'
0x18001e38c  jmp     short loc_18001E39A
0x18001e38e  mov     edx, 5Eh ; '^'
0x18001e393  jmp     short loc_18001E39A
0x18001e395  mov     edx, 53h ; 'S'; void *
0x18001e39a  mov     rcx, [rbp+5Fh]; this
0x18001e39e  mov     r9d, eax; char *
0x18001e3a1  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001e3a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e3ad  nop
0x18001e3ae  lea     rcx, [rbp+57h+var_98]
0x18001e3b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e3b7  nop
0x18001e3b8  lea     rcx, [rbp+57h+var_D0]
0x18001e3bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e3c1  jmp     loc_18001E919
0x18001e3c6  mov     [rbp+57h+var_80], r12
0x18001e3ca  mov     [rbp+57h+var_78], r12
0x18001e3ce  mov     [rbp+57h+var_70], r12
0x18001e3d2  mov     rbx, [rbp+57h+var_C8]
0x18001e3d6  test    rbx, rbx
0x18001e3d9  jnz     short loc_18001E42F
0x18001e3db  mov     dl, 1
0x18001e3dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra> `wil::Feature<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::GetImpl(void)'::`2'::impl
0x18001e3e4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e3e9  xor     r9d, r9d
0x18001e3ec  mov     r8d, 81h
0x18001e3f2  lea     rdx, __ImageBase
0x18001e3f9  lea     rcx, [rbp+57h+var_80]
0x18001e3fd  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18001e402  mov     ebx, eax
0x18001e404  test    eax, eax
0x18001e406  jns     short loc_18001E462
0x18001e408  mov     edx, 73h ; 's'; void *
0x18001e40d  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001e414  mov     r9d, eax; char *
0x18001e417  mov     rcx, [rbp+5Fh]; this
0x18001e41b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e420  nop
0x18001e421  lea     rcx, [rbp+57h+var_80]
0x18001e425  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e42a  jmp     loc_18001E368
0x18001e42f  mov     dl, 1
0x18001e431  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra> `wil::Feature<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::GetImpl(void)'::`2'::impl
0x18001e438  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e43d  mov     r9, rbx
0x18001e440  mov     esi, 80h
0x18001e445  mov     r8d, esi
0x18001e448  lea     rdx, __ImageBase
0x18001e44f  lea     rcx, [rbp+57h+var_80]
0x18001e453  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18001e458  mov     ebx, eax
0x18001e45a  test    eax, eax
0x18001e45c  jns     short loc_18001E462
0x18001e45e  mov     edx, esi
0x18001e460  jmp     short loc_18001E40D
0x18001e462  mov     rax, r12
0x18001e465  mov     [rbp+57h+var_48], rax
0x18001e469  mov     [rbp+57h+var_40], r12
0x18001e46d  mov     [rbp+57h+var_38], r12
0x18001e471  mov     r9, [rbp+57h+var_B0]
0x18001e475  test    r9, r9
0x18001e478  jz      short loc_18001E4C1
0x18001e47a  mov     r8d, 69h ; 'i'
0x18001e480  lea     rdx, __ImageBase
0x18001e487  lea     rcx, [rbp+57h+var_48]
0x18001e48b  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18001e490  mov     ebx, eax
0x18001e492  test    eax, eax
0x18001e494  jns     short loc_18001E4BD
0x18001e496  mov     rcx, [rbp+5Fh]; this
0x18001e49a  mov     r9d, eax; char *
0x18001e49d  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001e4a4  mov     edx, 8Fh; void *
0x18001e4a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4ae  nop
0x18001e4af  lea     rcx, [rbp+57h+var_48]
0x18001e4b3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e4b8  jmp     loc_18001E421
0x18001e4bd  mov     rax, [rbp+57h+var_48]
0x18001e4c1  mov     [rbp+57h+var_58], r12
0x18001e4c5  mov     dword ptr [rbp+57h+arg_8], 2
0x18001e4cc  mov     [rbp+57h+SRWLock], rax
0x18001e4d0  mov     rax, [rbp+57h+var_80]
0x18001e4d4  mov     [rbp+57h+var_88], rax
0x18001e4d8  lea     r9, [rbp+57h+arg_8]
0x18001e4dc  lea     r8, [rbp+57h+SRWLock]
0x18001e4e0  lea     rdx, [rbp+57h+var_88]
0x18001e4e4  lea     rcx, [rbp+57h+var_58]
0x18001e4e8  call    ??$MakeAndInitialize@VWorkAccountItem@WorkAccess@SystemSettings@@UISettingItem@DataModel@3@PEBGPEBGW4WorkAccountType@23@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@012@$$QEAPEBG1$$QEAW4WorkAccountType@WorkAccess@SystemSettings@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,ushort const *,ushort const *,SystemSettings::WorkAccess::WorkAccountType>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>,ushort const * &&,ushort const * &&,SystemSettings::WorkAccess::WorkAccountType &&)
0x18001e4ed  mov     ebx, eax
0x18001e4ef  test    eax, eax
0x18001e4f1  jns     short loc_18001E517
0x18001e4f3  mov     edx, 93h; void *
0x18001e4f8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001e4ff  mov     r9d, eax; char *
0x18001e502  mov     rcx, [rbp+5Fh]; this
0x18001e506  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e50b  nop
0x18001e50c  lea     rcx, [rbp+57h+var_58]
0x18001e510  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e515  jmp     short loc_18001E4AF
0x18001e517  mov     rcx, [rbp+57h+var_90]
0x18001e51b  mov     rax, [rcx]
0x18001e51e  mov     rdx, [rbp+57h+var_58]
0x18001e522  mov     rax, [rax+68h]
0x18001e526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e52b  mov     ebx, eax
0x18001e52d  test    eax, eax
0x18001e52f  jns     short loc_18001E538
0x18001e531  mov     edx, 94h
0x18001e536  jmp     short loc_18001E4F8
0x18001e538  mov     sil, 1
0x18001e53b  lea     rcx, [rbp+57h+var_58]
0x18001e53f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e544  nop
0x18001e545  lea     rcx, [rbp+57h+var_48]
0x18001e549  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e54e  nop
0x18001e54f  lea     rcx, [rbp+57h+var_80]
0x18001e553  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e558  nop
0x18001e559  lea     rcx, [rbp+57h+var_B0]
0x18001e55d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e562  nop
0x18001e563  lea     rcx, [rbp+57h+var_C8]
0x18001e567  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e56c  mov     [rbp+57h+var_B0], r12
0x18001e570  mov     [rbp+57h+var_A8], r12
  ... truncated ...
```

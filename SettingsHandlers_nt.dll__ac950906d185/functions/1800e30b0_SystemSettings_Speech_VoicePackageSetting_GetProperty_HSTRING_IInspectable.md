# SystemSettings::Speech::VoicePackageSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1800e30b0`
- end: `0x1800e3c9e`
- name: `?GetProperty@VoicePackageSetting@Speech@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `3054`
- prototype: `__int64 __fastcall(SystemSettings::Speech::VoicePackageSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x180020170`
- `0x1800201c4`
- `0x180020224`
- `0x1800210d0`
- `0x180021398`
- `0x1800234f8`
- `0x180032208`
- `0x18004d218`
- `0x18006956c`
- `0x180086824`
- `0x180094680`
- `0x1800ca52c`
- `0x1800d768c`
- `0x1800d7da0`
- `0x1800d7de0`
- `0x1800e3070`
- `0x1800e30b0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e311f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e31bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e370e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e379a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e391e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e397e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e311f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e31bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e370e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e379a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e391e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e397e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3854`

## string_xrefs

- `0x1800e3568`: `SystemSettings_Speech_VoicePackage_RemoveText`
- `0x1800e3b61`: `SystemSettings_Speech_VoicePackage_RemoveText`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::Speech::VoicePackageSetting::GetProperty(
        SystemSettings::Speech::VoicePackageSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  int UInt32; // ebx
  __int64 v12; // rdx
  HSTRING v13; // rcx
  const unsigned __int16 *v15; // r8
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  unsigned int v18; // ebx
  const unsigned __int16 *v19; // rax
  int v20; // eax
  HSTRING v21; // rdi
  unsigned __int16 **v22; // rbx
  const unsigned __int16 *v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  HSTRING v26; // rcx
  const unsigned __int16 *v27; // r8
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // eax
  __int64 v31; // rdx
  const unsigned __int16 *v32; // r8
  unsigned int v33; // ebx
  __int64 v34; // rdx
  const unsigned __int16 *v35; // rax
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  const unsigned __int16 *v39; // r8
  unsigned int v40; // eax
  __int64 v41; // rcx
  const unsigned __int16 *v42; // r8
  char v43; // di
  __int64 v44; // rcx
  int v45; // eax
  unsigned __int8 v46; // cl
  __int64 v47; // rcx
  const unsigned __int16 *v48; // r8
  unsigned __int8 v49; // al
  __int64 v50; // rcx
  const unsigned __int16 *v51; // r8
  struct IInspectable **v52; // r8
  const unsigned __int16 *v53; // r8
  const unsigned __int16 *v54; // r8
  __int64 v55; // rcx
  const unsigned __int16 *v56; // r8
  char v57; // al
  __int64 v58; // rcx
  const unsigned __int16 *v59; // r8
  unsigned __int8 v60; // al
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  const unsigned __int16 *v64; // rax
  const unsigned __int16 *v65; // r8
  __int64 v66; // rdi
  __int64 (__fastcall *v67)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v68; // r8
  __int64 v69; // rdi
  __int64 (__fastcall *v70)(__int64, HSTRING *); // rbx
  int v71; // eax
  __int64 v72; // rdx
  unsigned int v73; // ebx
  const unsigned __int16 *v74; // rax
  int v75; // eax
  HSTRING v76; // rdi
  unsigned __int16 **StringRawBuffer; // rbx
  const unsigned __int16 *v78; // rax
  int v79; // eax
  __int64 v80; // rdx
  const unsigned __int16 *v81; // r8
  __int64 v82; // rdi
  __int64 (__fastcall *v83)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v84; // r8
  unsigned int PackageSizeInMB; // ebx
  const unsigned __int16 *v86; // rax
  __int64 v87; // rcx
  const unsigned __int16 *v88; // r8
  unsigned int InstallProgress; // eax
  __int64 v90; // rcx
  const unsigned __int16 *v91; // r8
  char IsVoicePackageInTransientState; // di
  __int64 v93; // rcx
  int v94; // eax
  unsigned __int8 v95; // cl
  __int64 v96; // rcx
  const unsigned __int16 *v97; // r8
  unsigned __int8 IsPackageInState; // al
  __int64 v99; // rcx
  const unsigned __int16 *v100; // r8
  struct IInspectable **v101; // r8
  const unsigned __int16 *v102; // r8
  const unsigned __int16 *v103; // r8
  const unsigned __int16 *v104; // r8
  __int64 v105; // rcx
  unsigned __int8 v106; // al
  HSTRING v107; // [rsp+20h] [rbp-20h] BYREF
  HSTRING string; // [rsp+28h] [rbp-18h] BYREF
  HSTRING v109; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  *a3 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NOCDM>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NOCDM>::GetImpl'::`2'::impl) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803001E0, v6) )
    {
      v107 = 0;
      v66 = *((_QWORD *)this + 31);
      v67 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v66 + 56LL);
      WindowsDeleteString(0);
      v107 = 0;
      v30 = v67(v66, &v107);
      UInt32 = v30;
      if ( v30 < 0 )
      {
        v31 = 174;
        goto LABEL_33;
      }
      v30 = SystemSettings::DataModel::PropValueHelper::CreateString(v107, a3);
      UInt32 = v30;
      if ( v30 < 0 )
      {
        v31 = 175;
        goto LABEL_33;
      }
      goto LABEL_110;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301130, v65) )
    {
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301158, v68) )
      {
        v107 = 0;
        v82 = *((_QWORD *)this + 31);
        v83 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v82 + 64LL);
        WindowsDeleteString(0);
        v107 = 0;
        v30 = v83(v82, &v107);
        UInt32 = v30;
        if ( v30 < 0 )
        {
          v31 = 201;
          goto LABEL_33;
        }
        v30 = SystemSettings::DataModel::PropValueHelper::CreateString(v107, a3);
        UInt32 = v30;
        if ( v30 < 0 )
        {
          v31 = 202;
          goto LABEL_33;
        }
        goto LABEL_110;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301228, v81) )
      {
        PackageSizeInMB = SystemSettings::Speech::VoicePackageSetting::GetPackageSizeInMB(this);
        if ( PackageSizeInMB )
        {
          v107 = 0;
          v86 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v107);
          v36 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
                  (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_PackageSize",
                  v86,
                  (unsigned __int16 **)PackageSizeInMB);
          UInt32 = v36;
          if ( v36 < 0 )
          {
            v37 = 214;
            goto LABEL_44;
          }
          v36 = SystemSettings::DataModel::PropValueHelper::CreateString((const unsigned __int16 *)v107, a3);
          UInt32 = v36;
          if ( v36 < 0 )
          {
            v37 = 215;
            goto LABEL_44;
          }
          goto LABEL_121;
        }
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateString(&LocaleName, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 209;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301200, v84) )
      {
        InstallProgress = SystemSettings::Speech::AddVoicesSingleton::GetInstallProgress(v87, (char *)this + 256);
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateUInt32(InstallProgress, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 221;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301260, v88) )
      {
        IsVoicePackageInTransientState = SystemSettings::Speech::AddVoicesSingleton::IsVoicePackageInTransientState(
                                           v90,
                                           (char *)this + 256);
        v94 = SystemSettings::Speech::AddVoicesSingleton::GetInstallProgress(v93, (char *)this + 256);
        if ( IsVoicePackageInTransientState || (v95 = 0, (unsigned int)(v94 - 1) <= 0x62) )
          v95 = 1;
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v95, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 229;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301248, v91) )
      {
        IsPackageInState = SystemSettings::Speech::AddVoicesSingleton::IsPackageInState(v96, (char *)this + 256, 5);
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsPackageInState, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 233;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803013A0, v97) )
      {
        if ( (unsigned __int8)SystemSettings::Speech::AddVoicesSingleton::IsPackageInState(v99, (char *)this + 256, 5) )
        {
          UInt32 = SystemSettings::DataModel::GetResourceStringValue(
                     (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_RemoveText",
                     a3,
                     v101);
          if ( UInt32 >= 0 )
            return 0;
          v34 = 239;
        }
        else
        {
          UInt32 = SystemSettings::DataModel::GetResourceStringValue(
                     (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_RetryText",
                     a3,
                     v101);
          if ( UInt32 >= 0 )
            return 0;
          v34 = 243;
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803013B8, v100) )
      {
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 288), a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 248;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802E4980, v102) )
      {
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 252;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDB70, v103) )
      {
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 256;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301448, v104) )
      {
        v106 = SystemSettings::Speech::AddVoicesSingleton::IsPackageInState(v105, (char *)this + 256, 2);
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v106, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 260;
      }
      else
      {
        UInt32 = SystemSettings::DataModel::CSettingBase::GetValue(this, (HSTRING)a2, a3);
        if ( UInt32 >= 0 )
          return 0;
        v34 = 264;
      }
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)UInt32,
        (int)v107);
      return (unsigned int)UInt32;
    }
    v109 = 0;
    v69 = *((_QWORD *)this + 31);
    v70 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v69 + 56LL);
    WindowsDeleteString(0);
    v109 = 0;
    v71 = v70(v69, &v109);
    UInt32 = v71;
    if ( v71 < 0 )
    {
      v72 = 180;
LABEL_93:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v72,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v71,
        (int)v107);
LABEL_102:
      v13 = v109;
      goto LABEL_9;
    }
    v73 = SystemSettings::Speech::VoicePackageSetting::GetPackageSizeInMB(this);
    if ( !v73 )
    {
      v71 = SystemSettings::DataModel::PropValueHelper::CreateString(v109, a3);
      UInt32 = v71;
      if ( v71 < 0 )
      {
        v72 = 185;
        goto LABEL_93;
      }
LABEL_104:
      v26 = v109;
      goto LABEL_111;
    }
    string = 0;
    v74 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&string);
    v75 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
            (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_PackageSize",
            v74,
            (unsigned __int16 **)v73);
    UInt32 = v75;
    if ( v75 >= 0 )
    {
      v107 = 0;
      v76 = string;
      StringRawBuffer = (unsigned __int16 **)WindowsGetStringRawBuffer(v109, 0);
      v78 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v107);
      v79 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
              (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_LanguageDescription",
              v78,
              StringRawBuffer,
              v76);
      UInt32 = v79;
      if ( v79 >= 0 )
      {
        v79 = SystemSettings::DataModel::PropValueHelper::CreateString((const unsigned __int16 *)v107, a3);
        UInt32 = v79;
        if ( v79 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v107);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&string);
          goto LABEL_104;
        }
        v80 = 195;
      }
      else
      {
        v80 = 193;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v80,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v79,
        (int)v107);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v107);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v75,
        (int)v107);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&string);
    goto LABEL_102;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803001E0, v6) )
  {
    string = 0;
    v8 = *((_QWORD *)this + 31);
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(v8, &string);
    UInt32 = v10;
    if ( v10 < 0 )
    {
      v12 = 72;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v10,
        (int)v107);
LABEL_8:
      v13 = string;
LABEL_9:
      WindowsDeleteString(v13);
      return (unsigned int)UInt32;
    }
    v10 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    UInt32 = v10;
    if ( v10 < 0 )
    {
      v12 = 73;
      goto LABEL_7;
    }
    goto LABEL_27;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301130, v7) )
  {
    string = 0;
    v16 = *((_QWORD *)this + 31);
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v17(v16, &string);
    UInt32 = v10;
    if ( v10 < 0 )
    {
      v12 = 78;
      goto LABEL_7;
    }
    v18 = SystemSettings::Speech::VoicePackageSetting::GetPackageSizeInMB(this);
    if ( !v18 )
    {
      v10 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
      UInt32 = v10;
      if ( v10 < 0 )
      {
        v12 = 83;
        goto LABEL_7;
      }
      goto LABEL_27;
    }
    v109 = 0;
    v19 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v109);
    v20 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
            (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_PackageSize",
            v19,
            (unsigned __int16 **)v18);
    UInt32 = v20;
    if ( v20 >= 0 )
    {
      v107 = 0;
      v21 = v109;
      v22 = (unsigned __int16 **)WindowsGetStringRawBuffer(string, 0);
      v23 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v107);
      v24 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
              (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_LanguageDescription",
              v23,
              v22,
              v21);
      UInt32 = v24;
      if ( v24 >= 0 )
      {
        v24 = SystemSettings::DataModel::PropValueHelper::CreateString((const unsigned __int16 *)v107, a3);
        UInt32 = v24;
        if ( v24 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v107);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v109);
LABEL_27:
          v26 = string;
LABEL_111:
          WindowsDeleteString(v26);
          return 0;
        }
        v25 = 93;
      }
      else
      {
        v25 = 91;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v24,
        (int)v107);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v107);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v20,
        (int)v107);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v109);
    goto LABEL_8;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301158, v15) )
  {
    v107 = 0;
    v28 = *((_QWORD *)this + 31);
    v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 64LL);
    WindowsDeleteString(0);
    v107 = 0;
    v30 = v29(v28, &v107);
    UInt32 = v30;
    if ( v30 < 0 )
    {
      v31 = 99;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v30,
        (int)v107);
      v13 = v107;
      goto LABEL_9;
    }
    v30 = SystemSettings::DataModel::PropValueHelper::CreateString(v107, a3);
    UInt32 = v30;
    if ( v30 < 0 )
    {
      v31 = 100;
      goto LABEL_33;
    }
LABEL_110:
    v26 = v107;
    goto LABEL_111;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301228, v27) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301200, v32) )
    {
      v40 = SystemSettings::Speech::AddVoicesSingleton::GetInstallProgress(v38, (char *)this + 256);
      UInt32 = SystemSettings::DataModel::PropValueHelper::CreateUInt32(v40, a3);
      if ( UInt32 < 0 )
      {
        v34 = 119;
        goto LABEL_39;
      }
      return 0;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301260, v39) )
    {
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301248, v42) )
      {
        v49 = SystemSettings::Speech::AddVoicesSingleton::IsPackageInState(v47, (char *)this + 256, 5);
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v49, a3);
        if ( UInt32 < 0 )
        {
          v34 = 131;
          goto LABEL_39;
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803013A0, v48) )
      {
        if ( (unsigned __int8)SystemSettings::Speech::AddVoicesSingleton::IsPackageInState(v50, (char *)this + 256, 5) )
        {
          UInt32 = SystemSettings::DataModel::GetResourceStringValue(
                     (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_RemoveText",
                     a3,
                     v52);
          if ( UInt32 < 0 )
          {
            v34 = 137;
            goto LABEL_39;
          }
        }
        else
        {
          UInt32 = SystemSettings::DataModel::GetResourceStringValue(
                     (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_RetryText",
                     a3,
                     v52);
          if ( UInt32 < 0 )
          {
            v34 = 141;
            goto LABEL_39;
          }
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803013B8, v51) )
      {
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 288), a3);
        if ( UInt32 < 0 )
        {
          v34 = 146;
          goto LABEL_39;
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802E4980, v53) )
      {
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, a3);
        if ( UInt32 < 0 )
        {
          v34 = 150;
          goto LABEL_39;
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDB70, v54) )
      {
        v57 = SystemSettings::Speech::AddVoicesSingleton::IsVoicePackageInTransientState(v55, (char *)this + 256);
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v57 ^ 1u, a3);
        if ( UInt32 < 0 )
        {
          v34 = 154;
          goto LABEL_39;
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301448, v56) )
      {
        v60 = SystemSettings::Speech::AddVoicesSingleton::IsPackageInState(v58, (char *)this + 256, 2);
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v60, a3);
        if ( UInt32 < 0 )
        {
          v34 = 158;
          goto LABEL_39;
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180301430, v59) )
      {
        v64 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(
                                          (char *)this + 256,
                                          v61,
                                          v62,
                                          v63);
        UInt32 = SystemSettings::DataModel::PropValueHelper::CreateString(v64, a3);
        if ( UInt32 < 0 )
        {
          v34 = 162;
          goto LABEL_39;
        }
      }
      else
      {
        UInt32 = SystemSettings::DataModel::CSettingBase::GetValue(this, (HSTRING)a2, a3);
        if ( UInt32 < 0 )
        {
          v34 = 166;
          goto LABEL_39;
        }
      }
      return 0;
    }
    v43 = SystemSettings::Speech::AddVoicesSingleton::IsVoicePackageInTransientState(v41, (char *)this + 256);
    v45 = SystemSettings::Speech::AddVoicesSingleton::GetInstallProgress(v44, (char *)this + 256);
    if ( v43 || (v46 = 0, (unsigned int)(v45 - 1) <= 0x62) )
      v46 = 1;
    UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v46, a3);
    if ( UInt32 >= 0 )
      return 0;
    v34 = 127;
    goto LABEL_39;
  }
  v33 = SystemSettings::Speech::VoicePackageSetting::GetPackageSizeInMB(this);
  if ( v33 )
  {
    v107 = 0;
    v35 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v107);
    v36 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
            (SystemSettings::DataModel *)L"SystemSettings_Speech_VoicePackage_PackageSize",
            v35,
            (unsigned __int16 **)v33);
    UInt32 = v36;
    if ( v36 < 0 )
    {
      v37 = 112;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\voicepackage.cpp",
        (const char *)(unsigned int)v36,
        (int)v107);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v107);
      return (unsigned int)UInt32;
    }
    v36 = SystemSettings::DataModel::PropValueHelper::CreateString((const unsigned __int16 *)v107, a3);
    UInt32 = v36;
    if ( v36 < 0 )
    {
      v37 = 113;
      goto LABEL_44;
    }
LABEL_121:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v107);
    return 0;
  }
  UInt32 = SystemSettings::DataModel::PropValueHelper::CreateString(&LocaleName, a3);
  if ( UInt32 < 0 )
  {
    v34 = 107;
    goto LABEL_39;
  }
  return 0;
}

```

## disassembly

```asm
0x1800e30b0  mov     [rsp-28h+arg_18], rbx
0x1800e30b5  push    rbp
0x1800e30b6  push    rsi
0x1800e30b7  push    rdi
0x1800e30b8  push    r14
0x1800e30ba  push    r15
0x1800e30bc  mov     rbp, rsp
0x1800e30bf  sub     rsp, 40h
0x1800e30c3  mov     rax, cs:__security_cookie
0x1800e30ca  xor     rax, rsp
0x1800e30cd  mov     [rbp+var_8], rax
0x1800e30d1  mov     rsi, r8
0x1800e30d4  mov     rbx, rdx
0x1800e30d7  mov     r14, rcx
0x1800e30da  xor     r15d, r15d
0x1800e30dd  mov     [r8], r15
0x1800e30e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NOCDM@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NOCDM@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NOCDM> `wil::Feature<__WilFeatureTraits_Feature_NOCDM>::GetImpl(void)'::`2'::impl
0x1800e30e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NOCDM@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NOCDM>::__private_IsEnabled(void)
0x1800e30ec  lea     rdx, stru_1803001E0; HSTRING
0x1800e30f3  mov     rcx, rbx; this
0x1800e30f6  test    al, al
0x1800e30f8  jz      loc_1800E36F1
0x1800e30fe  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800e3103  test    al, al
0x1800e3105  jz      loc_1800E3191
0x1800e310b  mov     [rbp+string], r15
0x1800e310f  mov     rdi, [r14+0F8h]
0x1800e3116  mov     rax, [rdi]
0x1800e3119  mov     rbx, [rax+38h]
0x1800e311d  xor     ecx, ecx; string
0x1800e311f  call    cs:__imp_WindowsDeleteString
0x1800e3126  nop     dword ptr [rax+rax+00h]
0x1800e312b  mov     [rbp+string], r15
0x1800e312f  lea     rdx, [rbp+string]
0x1800e3133  mov     rcx, rdi
0x1800e3136  mov     rax, rbx
0x1800e3139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e313e  mov     ebx, eax
0x1800e3140  test    eax, eax
0x1800e3142  jns     short loc_1800E314A
0x1800e3144  lea     edx, [r15+48h]
0x1800e3148  jmp     short loc_1800E3161
0x1800e314a  mov     rdx, rsi; struct IInspectable **
0x1800e314d  mov     rcx, [rbp+string]; HSTRING
0x1800e3151  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800e3156  mov     ebx, eax
0x1800e3158  test    eax, eax
0x1800e315a  jns     short loc_1800E318C
0x1800e315c  mov     edx, 49h ; 'I'; void *
0x1800e3161  mov     r9d, eax; char *
0x1800e3164  lea     r8, aShellSystemset_1; "shell\\systemsettingsthreshold\\handler"...
0x1800e316b  mov     rcx, [rbp+28h]; this
0x1800e316f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3174  nop
0x1800e3175  mov     rcx, [rbp+string]; string
0x1800e3179  call    cs:__imp_WindowsDeleteString
0x1800e3180  nop     dword ptr [rax+rax+00h]
0x1800e3185  mov     eax, ebx
0x1800e3187  jmp     loc_1800E398C
0x1800e318c  jmp     loc_1800E3308
0x1800e3191  lea     rdx, stru_180301130; HSTRING
0x1800e3198  mov     rcx, rbx; this
0x1800e319b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800e31a0  test    al, al
0x1800e31a2  jz      loc_1800E3311
0x1800e31a8  mov     [rbp+string], r15
0x1800e31ac  mov     rdi, [r14+0F8h]
0x1800e31b3  mov     rax, [rdi]
0x1800e31b6  mov     rbx, [rax+38h]
0x1800e31ba  xor     ecx, ecx; string
0x1800e31bc  call    cs:__imp_WindowsDeleteString
0x1800e31c3  nop     dword ptr [rax+rax+00h]
0x1800e31c8  mov     [rbp+string], r15
0x1800e31cc  lea     rdx, [rbp+string]
0x1800e31d0  mov     rcx, rdi
0x1800e31d3  mov     rax, rbx
0x1800e31d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e31db  mov     ebx, eax
0x1800e31dd  test    eax, eax
0x1800e31df  jns     short loc_1800E31E8
0x1800e31e1  mov     edx, 4Eh ; 'N'
0x1800e31e6  jmp     short loc_1800E3211
0x1800e31e8  mov     rcx, r14; this
0x1800e31eb  call    ?GetPackageSizeInMB@VoicePackageSetting@Speech@SystemSettings@@AEBAIXZ; SystemSettings::Speech::VoicePackageSetting::GetPackageSizeInMB(void)
0x1800e31f0  mov     ebx, eax
0x1800e31f2  test    eax, eax
0x1800e31f4  jnz     short loc_1800E3229
0x1800e31f6  mov     rdx, rsi; struct IInspectable **
0x1800e31f9  mov     rcx, [rbp+string]; HSTRING
0x1800e31fd  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800e3202  mov     ebx, eax
0x1800e3204  test    eax, eax
0x1800e3206  jns     loc_1800E3308
0x1800e320c  mov     edx, 53h ; 'S'; void *
0x1800e3211  lea     r8, aShellSystemset_1; "shell\\systemsettingsthreshold\\handler"...
0x1800e3218  mov     r9d, eax; char *
0x1800e321b  mov     rcx, [rbp+28h]; this
0x1800e321f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3224  jmp     loc_1800E32EF
0x1800e3229  mov     [rbp+var_10], r15
0x1800e322d  lea     rcx, [rbp+var_10]
0x1800e3231  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800e3236  mov     r8d, ebx; unsigned __int16 **
0x1800e3239  mov     rdx, rax; unsigned __int16 *
0x1800e323c  lea     rcx, aSystemsettings_1090; "SystemSettings_Speech_VoicePackage_Pack"...
0x1800e3243  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x1800e3248  mov     ebx, eax
0x1800e324a  test    eax, eax
0x1800e324c  jns     short loc_1800E3268
0x1800e324e  mov     rcx, [rbp+28h]; this
0x1800e3252  mov     r9d, eax; char *
0x1800e3255  lea     r8, aShellSystemset_1; "shell\\systemsettingsthreshold\\handler"...
0x1800e325c  mov     edx, 58h ; 'X'; void *
0x1800e3261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3266  jmp     short loc_1800E32E5
0x1800e3268  mov     [rbp+var_20], r15
0x1800e326c  mov     rdi, [rbp+var_10]
0x1800e3270  xor     edx, edx; length
0x1800e3272  mov     rcx, [rbp+string]; string
0x1800e3276  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e327d  nop     dword ptr [rax+rax+00h]
0x1800e3282  mov     rbx, rax
0x1800e3285  lea     rcx, [rbp+var_20]
0x1800e3289  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800e328e  mov     r9, rdi
0x1800e3291  mov     r8, rbx; unsigned __int16 **
0x1800e3294  mov     rdx, rax; unsigned __int16 *
0x1800e3297  lea     rcx, aSystemsettings_1101; "SystemSettings_Speech_VoicePackage_Lang"...
0x1800e329e  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x1800e32a3  mov     ebx, eax
0x1800e32a5  test    eax, eax
0x1800e32a7  jns     short loc_1800E32B0
0x1800e32a9  mov     edx, 5Bh ; '['
0x1800e32ae  jmp     short loc_1800E32C7
0x1800e32b0  mov     rdx, rsi; struct IInspectable **
0x1800e32b3  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1800e32b7  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800e32bc  mov     ebx, eax
0x1800e32be  test    eax, eax
0x1800e32c0  jns     short loc_1800E32F4
0x1800e32c2  mov     edx, 5Dh ; ']'; void *
0x1800e32c7  mov     r9d, eax; char *
0x1800e32ca  lea     r8, aShellSystemset_1; "shell\\systemsettingsthreshold\\handler"...
0x1800e32d1  mov     rcx, [rbp+28h]; this
0x1800e32d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e32da  nop
0x1800e32db  lea     rcx, [rbp+var_20]
0x1800e32df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800e32e4  nop
0x1800e32e5  lea     rcx, [rbp+var_10]
0x1800e32e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800e32ee  nop
0x1800e32ef  jmp     loc_1800E3175
0x1800e32f4  lea     rcx, [rbp+var_20]
0x1800e32f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800e32fd  nop
0x1800e32fe  lea     rcx, [rbp+var_10]
0x1800e3302  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800e3307  nop
0x1800e3308  mov     rcx, [rbp+string]
0x1800e330c  jmp     loc_1800E397E
0x1800e3311  lea     rdx, stru_180301158; HSTRING
0x1800e3318  mov     rcx, rbx; this
0x1800e331b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800e3320  test    al, al
0x1800e3322  jz      short loc_1800E339D
0x1800e3324  mov     [rbp+var_20], r15
0x1800e3328  mov     rdi, [r14+0F8h]
0x1800e332f  mov     rax, [rdi]
0x1800e3332  mov     rbx, [rax+40h]
0x1800e3336  xor     ecx, ecx; string
0x1800e3338  call    cs:__imp_WindowsDeleteString
0x1800e333f  nop     dword ptr [rax+rax+00h]
0x1800e3344  mov     [rbp+var_20], r15
0x1800e3348  lea     rdx, [rbp+var_20]
0x1800e334c  mov     rcx, rdi
0x1800e334f  mov     rax, rbx
0x1800e3352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3357  mov     ebx, eax
0x1800e3359  test    eax, eax
0x1800e335b  jns     short loc_1800E3364
0x1800e335d  mov     edx, 63h ; 'c'
0x1800e3362  jmp     short loc_1800E337B
0x1800e3364  mov     rdx, rsi; struct IInspectable **
0x1800e3367  mov     rcx, [rbp+var_20]; HSTRING
0x1800e336b  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800e3370  mov     ebx, eax
0x1800e3372  test    eax, eax
0x1800e3374  jns     short loc_1800E3398
0x1800e3376  mov     edx, 64h ; 'd'; void *
0x1800e337b  mov     r9d, eax; char *
0x1800e337e  lea     r8, aShellSystemset_1; "shell\\systemsettingsthreshold\\handler"...
0x1800e3385  mov     rcx, [rbp+28h]; this
0x1800e3389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e338e  nop
0x1800e338f  mov     rcx, [rbp+var_20]
0x1800e3393  jmp     loc_1800E3179
0x1800e3398  jmp     loc_1800E397A
0x1800e339d  lea     rdx, stru_180301228; HSTRING
0x1800e33a4  mov     rcx, rbx; this
0x1800e33a7  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800e33ac  test    al, al
0x1800e33ae  jz      loc_1800E3462
0x1800e33b4  mov     rcx, r14; this
0x1800e33b7  call    ?GetPackageSizeInMB@VoicePackageSetting@Speech@SystemSettings@@AEBAIXZ; SystemSettings::Speech::VoicePackageSetting::GetPackageSizeInMB(void)
0x1800e33bc  mov     ebx, eax
0x1800e33be  test    eax, eax
0x1800e33c0  jnz     short loc_1800E33F8
0x1800e33c2  mov     rdx, rsi; struct IInspectable **
0x1800e33c5  lea     rcx, LocaleName; unsigned __int16 *
0x1800e33cc  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800e33d1  mov     ebx, eax
0x1800e33d3  test    eax, eax
0x1800e33d5  jns     loc_1800E398A
0x1800e33db  mov     edx, 6Bh ; 'k'; void *
0x1800e33e0  mov     rcx, [rbp+28h]; this
0x1800e33e4  mov     r9d, ebx; char *
0x1800e33e7  lea     r8, aShellSystemset_1; "shell\\systemsettingsthreshold\\handler"...
0x1800e33ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e33f3  jmp     loc_1800E3185
0x1800e33f8  mov     [rbp+var_20], r15
0x1800e33fc  lea     rcx, [rbp+var_20]
0x1800e3400  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800e3405  mov     r8d, ebx; unsigned __int16 **
0x1800e3408  mov     rdx, rax; unsigned __int16 *
0x1800e340b  lea     rcx, aSystemsettings_1090; "SystemSettings_Speech_VoicePackage_Pack"...
0x1800e3412  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x1800e3417  mov     ebx, eax
0x1800e3419  test    eax, eax
0x1800e341b  jns     short loc_1800E3424
0x1800e341d  mov     edx, 70h ; 'p'
0x1800e3422  jmp     short loc_1800E343B
0x1800e3424  mov     rdx, rsi; struct IInspectable **
0x1800e3427  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1800e342b  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800e3430  mov     ebx, eax
0x1800e3432  test    eax, eax
0x1800e3434  jns     short loc_1800E345D
0x1800e3436  mov     edx, 71h ; 'q'; void *
0x1800e343b  mov     r9d, eax; char *
0x1800e343e  lea     r8, aShellSystemset_1; "shell\\systemsettingsthreshold\\handler"...
0x1800e3445  mov     rcx, [rbp+28h]; this
0x1800e3449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e344e  nop
0x1800e344f  lea     rcx, [rbp+var_20]
0x1800e3453  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800e3458  jmp     loc_1800E3185
0x1800e345d  jmp     loc_1800E3A4D
0x1800e3462  lea     rdx, stru_180301200; HSTRING
0x1800e3469  mov     rcx, rbx; this
0x1800e346c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800e3471  test    al, al
0x1800e3473  jz      short loc_1800E349F
0x1800e3475  lea     rdx, [r14+100h]
0x1800e347c  call    ?GetInstallProgress@AddVoicesSingleton@Speech@SystemSettings@@QEBAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Speech::AddVoicesSingleton::GetInstallProgress(std::wstring const &)
0x1800e3481  mov     rdx, rsi; struct IInspectable **
0x1800e3484  mov     ecx, eax; unsigned int
0x1800e3486  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x1800e348b  mov     ebx, eax
0x1800e348d  test    eax, eax
0x1800e348f  jns     loc_1800E398A
0x1800e3495  mov     edx, 77h ; 'w'
0x1800e349a  jmp     loc_1800E33E0
0x1800e349f  lea     rdx, stru_180301260; HSTRING
0x1800e34a6  mov     rcx, rbx; this
0x1800e34a9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800e34ae  test    al, al
0x1800e34b0  jz      short loc_1800E34F9
0x1800e34b2  lea     rbx, [r14+100h]
0x1800e34b9  mov     rdx, rbx
0x1800e34bc  call    ?IsVoicePackageInTransientState@AddVoicesSingleton@Speech@SystemSettings@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Speech::AddVoicesSingleton::IsVoicePackageInTransientState(std::wstring const &)
0x1800e34c1  mov     dil, al
0x1800e34c4  mov     rdx, rbx
0x1800e34c7  call    ?GetInstallProgress@AddVoicesSingleton@Speech@SystemSettings@@QEBAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Speech::AddVoicesSingleton::GetInstallProgress(std::wstring const &)
0x1800e34cc  test    dil, dil
0x1800e34cf  jnz     short loc_1800E34DB
0x1800e34d1  dec     eax
0x1800e34d3  cmp     eax, 62h ; 'b'
0x1800e34d6  mov     cl, r15b
0x1800e34d9  ja      short loc_1800E34DD
0x1800e34db  mov     cl, 1; unsigned __int8
0x1800e34dd  mov     rdx, rsi; struct IInspectable **
0x1800e34e0  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800e34e5  mov     ebx, eax
0x1800e34e7  test    eax, eax
0x1800e34e9  jns     loc_1800E398A
0x1800e34ef  mov     edx, 7Fh
0x1800e34f4  jmp     loc_1800E33E0
0x1800e34f9  lea     rdx, stru_180301248; HSTRING
0x1800e3500  mov     rcx, rbx; this
0x1800e3503  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800e3508  test    al, al
0x1800e350a  jz      short loc_1800E353C
0x1800e350c  lea     rdx, [r14+100h]
0x1800e3513  mov     r8d, 5
0x1800e3519  call    ?IsPackageInState@AddVoicesSingleton@Speech@SystemSettings@@AEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PayloadState@@@Z; SystemSettings::Speech::AddVoicesSingleton::IsPackageInState(std::wstring const &,PayloadState)
0x1800e351e  mov     cl, al; unsigned __int8
0x1800e3520  mov     rdx, rsi; struct IInspectable **
0x1800e3523  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800e3528  mov     ebx, eax
  ... truncated ...
```

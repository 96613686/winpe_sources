# SystemSettings::PenSettings::EnumerateModernAppsSingleton::EnumerateApplications(void)

- ea: `0x180051668`
- end: `0x180051ef0`
- name: `?EnumerateApplications@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@AEAAJXZ`
- size: `2184`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::EnumerateModernAppsSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800515a0`

## callees

- `0x1800030e0`
- `0x180005eec`
- `0x180005f0c`
- `0x180008128`
- `0x18000a2bc`
- `0x18001033c`
- `0x1800111f0`
- `0x1800115d8`
- `0x1800127cc`
- `0x18001a378`
- `0x18001b364`
- `0x18001bb98`
- `0x18001bbd4`
- `0x180020d54`
- `0x18003105c`
- `0x180031514`
- `0x1800317a4`
- `0x1800318e0`
- `0x1800332fc`
- `0x180050398`
- `0x1800504dc`
- `0x1800506d4`
- `0x180050fe0`
- `0x1800510ac`
- `0x180051110`
- `0x180051290`
- `0x18005146c`
- `0x1800514c0`
- `0x180051668`
- `0x180051ef8`
- `0x180051f70`
- `0x180052384`
- `0x1800523e4`
- `0x180052444`
- `0x180052780`
- `0x180052978`
- `0x1800529d8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180051b64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180051b64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051957`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051d8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051957`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051d8f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800516dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800516dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800516c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800516c5`

## string_xrefs

- `0x1800519f9`: `com.microsoft.windows.copilotkeyprovider`
- `0x180051709`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x18005175d`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x1800517f9`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x18005186d`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x180051930`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall SystemSettings::PenSettings::EnumerateModernAppsSingleton::EnumerateApplications(
        SystemSettings::PenSettings::EnumerateModernAppsSingleton *this)
{
  SystemSettings::PenSettings::EnumerateModernAppsSingleton *v1; // r15
  int v2; // r14d
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // r12d
  __m128i si128; // xmm6
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, SystemSettings::PenSettings **); // rbx
  int v14; // eax
  struct SystemSettings::PenSettings::PenLaunchableAppInfo *v15; // r9
  int AppInfo; // eax
  const char *v17; // r9
  int v18; // r12d
  unsigned int v19; // eax
  __int64 Application; // rax
  __int64 DisplayNameLocalized; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  const char *v27; // r9
  int v29; // [rsp+20h] [rbp-228h] BYREF
  SystemSettings::PenSettings *v30; // [rsp+28h] [rbp-220h] BYREF
  int v31; // [rsp+30h] [rbp-218h]
  __int64 v32; // [rsp+38h] [rbp-210h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-208h] BYREF
  int v34; // [rsp+44h] [rbp-204h] BYREF
  char v35[8]; // [rsp+48h] [rbp-200h] BYREF
  char v36[8]; // [rsp+50h] [rbp-1F8h] BYREF
  char v37[8]; // [rsp+58h] [rbp-1F0h] BYREF
  struct Windows::Internal::StateRepository::IApplication *v38; // [rsp+60h] [rbp-1E8h] BYREF
  char *v39; // [rsp+68h] [rbp-1E0h] BYREF
  char *v40; // [rsp+70h] [rbp-1D8h] BYREF
  __int64 v41; // [rsp+78h] [rbp-1D0h] BYREF
  char v42[8]; // [rsp+80h] [rbp-1C8h] BYREF
  char v43[8]; // [rsp+88h] [rbp-1C0h] BYREF
  __int64 v44; // [rsp+90h] [rbp-1B8h] BYREF
  __int64 v45; // [rsp+98h] [rbp-1B0h] BYREF
  int *v46; // [rsp+A0h] [rbp-1A8h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-1A0h] BYREF
  SystemSettings::PenSettings::EnumerateModernAppsSingleton *v48; // [rsp+B0h] [rbp-198h]
  char v49[8]; // [rsp+B8h] [rbp-190h] BYREF
  char v50[8]; // [rsp+C0h] [rbp-188h] BYREF
  __int64 *v51; // [rsp+C8h] [rbp-180h] BYREF
  int v52; // [rsp+D0h] [rbp-178h]
  char *v53; // [rsp+D8h] [rbp-170h]
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-150h] BYREF
  __int64 v55; // [rsp+110h] [rbp-138h]
  __int128 v56; // [rsp+120h] [rbp-128h] BYREF
  __m128i v57; // [rsp+130h] [rbp-118h]
  __int128 v58; // [rsp+140h] [rbp-108h] BYREF
  __m128i v59; // [rsp+150h] [rbp-F8h]
  __int128 v60; // [rsp+160h] [rbp-E8h] BYREF
  __m128i v61; // [rsp+170h] [rbp-D8h]
  __int128 v62; // [rsp+180h] [rbp-C8h] BYREF
  __m128i v63; // [rsp+190h] [rbp-B8h]
  char v64; // [rsp+1A0h] [rbp-A8h]
  int v65; // [rsp+1A1h] [rbp-A7h]
  __int16 v66; // [rsp+1A5h] [rbp-A3h]
  char v67; // [rsp+1A7h] [rbp-A1h]
  _BYTE v68[32]; // [rsp+1B0h] [rbp-98h] BYREF
  _BYTE v69[32]; // [rsp+1D0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v1 = this;
  v48 = this;
  v2 = 0;
  v31 = 0;
  v45 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.Application",
         0x2Cu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
         hstringHeader.Reserved.Reserved1,
         &v45);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
      (const char *)(unsigned int)v3,
      v29);
    goto LABEL_50;
  }
  v32 = 0;
  v5 = v45;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 320LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v7 = v6(v5, 0, &v32);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 128;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
      (const char *)(unsigned int)v7,
      v29);
LABEL_8:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    goto LABEL_50;
  }
  v33 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v33);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 130;
    goto LABEL_7;
  }
  v38 = 0;
  v55 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.ApplicationResourceResolver",
    0x3Du,
    0x3Cu);
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(
         v55,
         &v38);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
      (const char *)(unsigned int)v9,
      v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    goto LABEL_8;
  }
  v10 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v10 < v33 )
  {
    v30 = 0;
    v12 = v32;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, SystemSettings::PenSettings **))(*(_QWORD *)v32 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    try
    {
      v14 = v13(v12, v10, &v30);
      if ( v14 >= 0 )
      {
        v56 = 0;
        v57 = si128;
        LOWORD(v56) = 0;
        v58 = 0;
        v59 = si128;
        LOWORD(v58) = 0;
        v60 = 0;
        v61 = si128;
        LOWORD(v60) = 0;
        v62 = 0;
        v63 = si128;
        LOWORD(v62) = 0;
        v64 = 0;
        v65 = 0;
        v66 = 0;
        v67 = 0;
        AppInfo = SystemSettings::PenSettings::GetAppInfo(
                    v30,
                    v38,
                    (struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *)&v56,
                    v15);
        if ( AppInfo >= 0 )
        {
          if ( v64 )
          {
            AcquireSRWLockExclusive((PSRWLOCK)v1 + 37);
            v40 = (char *)v1 + 296;
            if ( *((_QWORD *)v1 + 35) == *((_QWORD *)v1 + 36) )
            {
              std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Emplace_reallocate<SystemSettings::PenSettings::PenLaunchableAppInfo const &>(
                (char *)v1 + 272,
                *((_QWORD *)v1 + 35),
                &v56);
            }
            else
            {
              SystemSettings::PenSettings::PenLaunchableAppInfo::PenLaunchableAppInfo(
                *((SystemSettings::PenSettings::PenLaunchableAppInfo **)v1 + 35),
                (const struct SystemSettings::PenSettings::PenLaunchableAppInfo *)&v56);
              *((_QWORD *)v1 + 35) += 136LL;
            }
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v40);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x92,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
            (const char *)(unsigned int)AppInfo,
            v29);
        }
        SystemSettings::PenSettings::PenLaunchableAppInfo::~PenLaunchableAppInfo((SystemSettings::PenSettings::PenLaunchableAppInfo *)&v56);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8F,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
          (const char *)(unsigned int)v14,
          v29);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      ++v10;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x9C,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
        v17);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v2 = v31;
      v1 = v48;
      break;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
  {
    try
    {
      winrt::hstring::hstring((winrt::hstring *)&v40, L"com.microsoft.windows.copilotkeyprovider");
      v53 = v40;
      v47 = 0;
      winrt::Windows::Internal::StateRepository::AppExtension::FindByUserOrDefaultAccountAndName(
        (const struct winrt::Windows::Internal::StateRepository::User *)&v44,
        (const struct winrt::param::hstring *)&v47);
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v47);
      if ( v44 )
      {
        v51 = &v44;
        v18 = 0;
        v52 = 0;
        v34 = 0;
        LODWORD(hstringHeader.Reserved.Reserved1) = 0;
        *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 56LL))(v44, &v34);
        winrt::check_hresult(&v30, v19, &hstringHeader);
        while ( v18 != v34 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::AppExtension>>::operator*(
            &v51,
            v37);
          winrt::impl::consume_Windows_Internal_StateRepository_IAppExtension<winrt::Windows::Internal::StateRepository::IAppExtension>::GetExtension(
            v37,
            v36);
          winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::GetApplication(
            v36,
            &v30);
          if ( (unsigned int)winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::AppListEntry(&v30) != 1 )
          {
            winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::GetApplication(
              &v30,
              v35);
            Application = winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::GetApplication(
                            v35,
                            v49);
            winrt::impl::consume_Windows_Internal_StateRepository_IPackageFamily<winrt::Windows::Internal::StateRepository::IPackageFamily>::PackageFamilyName(
              Application,
              v43);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v49);
            std::wstring::wstring(&hstringHeader, v43);
            AcquireSRWLockShared((PSRWLOCK)v1 + 37);
            v39 = (char *)v1 + 296;
            if ( (unsigned __int8)std::any_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_SystemSettings::PenSettings::PenLaunchableAppInfo_______lambda_a0927790aae09644f5c2dccac6dd8005___(
                                    *((_QWORD *)v1 + 34),
                                    *((_QWORD *)v1 + 35),
                                    &hstringHeader) )
            {
              wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v39);
            }
            else
            {
              wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v39);
              winrt::Windows::Internal::StateRepository::ApplicationResourceResolver::Create((const struct Application *)v42);
              winrt::impl::consume_Windows_Internal_StateRepository_IApplicationResourceResolver<winrt::Windows::Internal::StateRepository::IApplicationResourceResolver>::GetSquare44x44LogoLocalized(
                v42,
                &v41);
              v56 = 0;
              v57 = si128;
              LOWORD(v56) = 0;
              v58 = 0;
              v59 = si128;
              LOWORD(v58) = 0;
              v60 = 0;
              v61 = si128;
              LOWORD(v60) = 0;
              v62 = 0;
              v63 = si128;
              LOWORD(v62) = 0;
              v65 = 0;
              v66 = 0;
              v67 = 0;
              v64 = 1;
              DisplayNameLocalized = winrt::impl::consume_Windows_Internal_StateRepository_IApplicationResourceResolver<winrt::Windows::Internal::StateRepository::IApplicationResourceResolver>::GetDisplayNameLocalized(
                                       v42,
                                       v50);
              v22 = std::wstring::wstring(v68, DisplayNameLocalized);
              std::wstring::operator=(&v56, v22);
              std::wstring::_Tidy_deallocate(v68);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v50);
              std::wstring::operator=(&v58, &hstringHeader);
              v23 = winrt::impl::consume_Windows_Internal_StateRepository_IPackage<winrt::Windows::Internal::StateRepository::IPackage>::PackageFullName(
                      v35,
                      &v46);
              v24 = std::wstring::wstring(v68, v23);
              std::wstring::operator=(&v62, v24);
              std::wstring::_Tidy_deallocate(v68);
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v46);
              if ( v41 )
              {
                v25 = std::wstring::wstring(v68, &v41);
                v2 |= 2u;
              }
              else
              {
                v25 = std::wstring::wstring(v69, &word_1800679F0);
                v2 |= 1u;
              }
              v31 = v2;
              std::wstring::operator=(&v60, v25);
              if ( (v2 & 2) != 0 )
              {
                v2 &= ~2u;
                v31 = v2;
                std::wstring::_Tidy_deallocate(v68);
              }
              if ( (v2 & 1) != 0 )
              {
                v2 &= ~1u;
                v31 = v2;
                std::wstring::_Tidy_deallocate(v69);
              }
              AcquireSRWLockExclusive((PSRWLOCK)v1 + 37);
              v39 = (char *)v1 + 296;
              v26 = *((_QWORD *)v1 + 35);
              if ( v26 == *((_QWORD *)v1 + 36) )
              {
                std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Emplace_reallocate<SystemSettings::PenSettings::PenLaunchableAppInfo>(
                  (char *)v1 + 272,
                  *((_QWORD *)v1 + 35),
                  &v56);
              }
              else
              {
                SystemSettings::PenSettings::PenLaunchableAppInfo::PenLaunchableAppInfo(v26, &v56);
                *((_QWORD *)v1 + 35) += 136LL;
              }
              wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v39);
              SystemSettings::PenSettings::PenLaunchableAppInfo::~PenLaunchableAppInfo((SystemSettings::PenSettings::PenLaunchableAppInfo *)&v56);
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v41);
              winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v42);
            }
            std::wstring::_Tidy_deallocate(&hstringHeader);
            winrt::handle_type<winrt::impl::hstring_traits>::close(v43);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v35);
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v30);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v36);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v37);
          v52 = ++v18;
        }
      }
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v44);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v40);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xD7,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
        v27);
      v1 = v48;
    }
  }
  LOBYTE(v29) = 1;
  v46 = &v29;
  SystemSettings::DataModel::CSingletonHelper<bool>::_Notify<_lambda_78304fa1fdd572e2ab51f23c1c705858_>(
    (char *)v1 + 40,
    &v46);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v4 = 0;
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  return v4;
}

```

## disassembly

```asm
0x180051668  mov     r11, rsp
0x18005166b  push    rbx
0x18005166c  push    rsi
0x18005166d  push    rdi
0x18005166e  push    r12
0x180051670  push    r14
0x180051672  push    r15
0x180051674  sub     rsp, 218h
0x18005167b  movaps  xmmword ptr [r11-48h], xmm6
0x180051680  mov     rax, cs:__security_cookie
0x180051687  xor     rax, rsp
0x18005168a  mov     [rsp+248h+var_58], rax
0x180051692  mov     r15, rcx
0x180051695  mov     [rsp+248h+var_198], rcx
0x18005169d  xor     esi, esi
0x18005169f  mov     r14d, esi
0x1800516a2  mov     [rsp+248h+var_218], esi
0x1800516a6  mov     [r11-1B0h], rsi
0x1800516ad  lea     r9, [r11-150h]; string
0x1800516b4  lea     r8, [r11-148h]; hstringHeader
0x1800516bb  lea     edx, [rsi+2Ch]; length
0x1800516be  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800516c5  call    cs:__imp_WindowsCreateStringReference
0x1800516cb  test    eax, eax
0x1800516cd  jns     short loc_1800516E3
0x1800516cf  xor     r9d, r9d; lpArguments
0x1800516d2  xor     r8d, r8d; nNumberOfArguments
0x1800516d5  lea     edx, [rsi+1]; dwExceptionFlags
0x1800516d8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800516dd  call    cs:__imp_RaiseException
0x1800516e3  lea     rdx, [rsp+248h+var_1B0]
0x1800516eb  mov     rcx, qword ptr [rsp+248h+hstringHeader.Reserved]
0x1800516f3  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x1800516f8  mov     ebx, eax
0x1800516fa  test    eax, eax
0x1800516fc  jns     short loc_18005171F
0x1800516fe  mov     rcx, [rsp+248h]; this
0x180051706  mov     r9d, eax; char *
0x180051709  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x180051710  mov     edx, 7Eh ; '~'; void *
0x180051715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005171a  jmp     loc_180051EB8
0x18005171f  mov     [rsp+248h+var_210], rsi
0x180051724  mov     rdi, [rsp+248h+var_1B0]
0x18005172c  mov     rax, [rdi]
0x18005172f  mov     rbx, [rax+140h]
0x180051736  lea     rcx, [rsp+248h+var_210]
0x18005173b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051740  lea     r8, [rsp+248h+var_210]
0x180051745  xor     edx, edx
0x180051747  mov     rcx, rdi
0x18005174a  mov     rax, rbx
0x18005174d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051752  mov     ebx, eax
0x180051754  test    eax, eax
0x180051756  jns     short loc_180051784
0x180051758  mov     edx, 80h; void *
0x18005175d  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x180051764  mov     r9d, eax; char *
0x180051767  mov     rcx, [rsp+248h]; this
0x18005176f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051774  nop
0x180051775  lea     rcx, [rsp+248h+var_210]
0x18005177a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005177f  jmp     loc_180051EB8
0x180051784  mov     [rsp+248h+var_208], esi
0x180051788  mov     rcx, [rsp+248h+var_210]
0x18005178d  mov     rax, [rcx]
0x180051790  lea     rdx, [rsp+248h+var_208]
0x180051795  mov     rax, [rax+38h]
0x180051799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005179e  mov     ebx, eax
0x1800517a0  test    eax, eax
0x1800517a2  jns     short loc_1800517AB
0x1800517a4  mov     edx, 82h
0x1800517a9  jmp     short loc_18005175D
0x1800517ab  mov     [rsp+248h+var_1E8], rsi
0x1800517b0  mov     [rsp+248h+var_138], rsi
0x1800517b8  mov     r9d, 3Ch ; '<'; unsigned int
0x1800517be  lea     r8d, [r9+1]; unsigned int
0x1800517c2  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800517c9  lea     rcx, [rsp+248h+hstringHeader]; hstringHeader
0x1800517d1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800517d6  lea     rdx, [rsp+248h+var_1E8]
0x1800517db  mov     rcx, [rsp+248h+var_138]
0x1800517e3  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>)
0x1800517e8  mov     ebx, eax
0x1800517ea  test    eax, eax
0x1800517ec  jns     short loc_18005181A
0x1800517ee  mov     rcx, [rsp+248h]; this
0x1800517f6  mov     r9d, eax; char *
0x1800517f9  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x180051800  mov     edx, 88h; void *
0x180051805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005180a  nop
0x18005180b  lea     rcx, [rsp+248h+var_1E8]
0x180051810  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180051815  jmp     loc_180051775
0x18005181a  mov     r12d, esi
0x18005181d  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180051825  cmp     r12d, [rsp+248h+var_208]
0x18005182a  jnb     loc_1800519CC
0x180051830  mov     [rsp+248h+var_220], rsi
0x180051835  mov     rdi, [rsp+248h+var_210]
0x18005183a  mov     rax, [rdi]
0x18005183d  mov     rbx, [rax+30h]
0x180051841  lea     rcx, [rsp+248h+var_220]
0x180051846  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005184b  lea     r8, [rsp+248h+var_220]
0x180051850  mov     edx, r12d
0x180051853  mov     rcx, rdi
0x180051856  mov     rax, rbx
0x180051859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005185e  mov     rcx, [rsp+248h]; this
0x180051866  test    eax, eax
0x180051868  jns     short loc_180051883
0x18005186a  mov     r9d, eax; char *
0x18005186d  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x180051874  mov     edx, 8Fh; void *
0x180051879  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005187e  jmp     loc_1800519BA
0x180051883  xorps   xmm0, xmm0
0x180051886  movups  [rsp+248h+var_128], xmm0
0x18005188e  movdqa  [rsp+248h+var_118], xmm6
0x180051897  mov     word ptr [rsp+248h+var_128], si
0x18005189f  movups  [rsp+248h+var_108], xmm0
0x1800518a7  movdqa  [rsp+248h+var_F8], xmm6
0x1800518b0  mov     word ptr [rsp+248h+var_108], si
0x1800518b8  movups  [rsp+248h+var_E8], xmm0
0x1800518c0  movdqa  [rsp+248h+var_D8], xmm6
0x1800518c9  mov     word ptr [rsp+248h+var_E8], si
0x1800518d1  movups  [rsp+248h+var_C8], xmm0
0x1800518d9  movdqa  [rsp+248h+var_B8], xmm6
0x1800518e2  mov     word ptr [rsp+248h+var_C8], si
0x1800518ea  mov     [rsp+248h+var_A8], sil
0x1800518f2  xor     eax, eax
0x1800518f4  mov     [rsp+248h+var_A7], eax
0x1800518fb  mov     [rsp+248h+var_A3], ax
0x180051903  mov     [rsp+248h+var_A1], al
0x18005190a  lea     r8, [rsp+248h+var_128]; struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *
0x180051912  mov     rdx, [rsp+248h+var_1E8]; struct Windows::Internal::StateRepository::IApplication *
0x180051917  mov     rcx, [rsp+248h+var_220]; this
0x18005191c  call    ?GetAppInfo@PenSettings@SystemSettings@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAUIApplicationResourceResolverStatics@456@PEAUPenLaunchableAppInfo@12@@Z; SystemSettings::PenSettings::GetAppInfo(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationResourceResolverStatics *,SystemSettings::PenSettings::PenLaunchableAppInfo *)
0x180051921  mov     rcx, [rsp+248h]; this
0x180051929  test    eax, eax
0x18005192b  jns     short loc_180051943
0x18005192d  mov     r9d, eax; char *
0x180051930  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x180051937  mov     edx, 92h; void *
0x18005193c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051941  jmp     short loc_1800519AC
0x180051943  cmp     [rsp+248h+var_A8], sil
0x18005194b  jz      short loc_1800519AC
0x18005194d  lea     rbx, [r15+128h]
0x180051954  mov     rcx, rbx; SRWLock
0x180051957  call    cs:__imp_AcquireSRWLockExclusive
0x18005195d  mov     [rsp+248h+var_1D8], rbx
0x180051962  lea     rbx, [r15+110h]
0x180051969  mov     rax, [rbx+8]
0x18005196d  cmp     rax, [rbx+10h]
0x180051971  jz      short loc_18005198D
0x180051973  lea     rdx, [rsp+248h+var_128]; struct SystemSettings::PenSettings::PenLaunchableAppInfo *
0x18005197b  mov     rcx, rax; this
0x18005197e  call    ??0PenLaunchableAppInfo@PenSettings@SystemSettings@@QEAA@AEBU012@@Z; SystemSettings::PenSettings::PenLaunchableAppInfo::PenLaunchableAppInfo(SystemSettings::PenSettings::PenLaunchableAppInfo const &)
0x180051983  add     qword ptr [rbx+8], 88h
0x18005198b  jmp     short loc_1800519A1
0x18005198d  lea     r8, [rsp+248h+var_128]
0x180051995  mov     rdx, rax
0x180051998  mov     rcx, rbx
0x18005199b  call    ??$_Emplace_reallocate@AEBUPenLaunchableAppInfo@PenSettings@SystemSettings@@@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAPEAUPenLaunchableAppInfo@PenSettings@SystemSettings@@QEAU234@AEBU234@@Z; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Emplace_reallocate<SystemSettings::PenSettings::PenLaunchableAppInfo const &>(SystemSettings::PenSettings::PenLaunchableAppInfo * const,SystemSettings::PenSettings::PenLaunchableAppInfo const &)
0x1800519a0  nop
0x1800519a1  lea     rcx, [rsp+248h+var_1D8]
0x1800519a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800519ab  nop
0x1800519ac  lea     rcx, [rsp+248h+var_128]; this
0x1800519b4  call    ??1PenLaunchableAppInfo@PenSettings@SystemSettings@@QEAA@XZ; SystemSettings::PenSettings::PenLaunchableAppInfo::~PenLaunchableAppInfo(void)
0x1800519b9  nop
0x1800519ba  lea     rcx, [rsp+248h+var_220]
0x1800519bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800519c4  inc     r12d
0x1800519c7  jmp     loc_180051825
0x1800519cc  jmp     short loc_1800519E5
0x1800519ce  xor     esi, esi
0x1800519d0  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800519d8  mov     r14d, [rsp+248h+var_218]
0x1800519dd  mov     r15, [rsp+248h+var_198]
0x1800519e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x1800519ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x1800519f1  test    al, al
0x1800519f3  jz      loc_180051E7D
0x1800519f9  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.copilotkeyprovide"...
0x180051a00  lea     rcx, [rsp+248h+var_1D8]; this
0x180051a05  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180051a0a  nop
0x180051a0b  mov     rax, [rsp+248h+var_1D8]
0x180051a10  mov     [rsp+248h+var_170], rax
0x180051a18  mov     [rsp+248h+var_1A0], rsi
0x180051a20  lea     r8, [rsp+248h+var_170]
0x180051a28  lea     rdx, [rsp+248h+var_1A0]; struct winrt::param::hstring *
0x180051a30  lea     rcx, [rsp+248h+var_1B8]; struct winrt::Windows::Internal::StateRepository::User *
0x180051a38  call    ?FindByUserOrDefaultAccountAndName@AppExtension@StateRepository@Internal@Windows@winrt@@SA@AEBUUser@2345@AEBUhstring@param@5@@Z; winrt::Windows::Internal::StateRepository::AppExtension::FindByUserOrDefaultAccountAndName(winrt::Windows::Internal::StateRepository::User const &,winrt::param::hstring const &)
0x180051a3d  nop
0x180051a3e  lea     rcx, [rsp+248h+var_1A0]; this
0x180051a46  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180051a4b  mov     rcx, [rsp+248h+var_1B8]
0x180051a53  test    rcx, rcx
0x180051a56  jz      loc_180051E58
0x180051a5c  lea     rax, [rsp+248h+var_1B8]
0x180051a64  mov     [rsp+248h+var_180], rax
0x180051a6c  mov     r12d, esi
0x180051a6f  mov     [rsp+248h+var_178], esi
0x180051a76  mov     [rsp+248h+var_204], esi
0x180051a7a  mov     dword ptr [rsp+248h+hstringHeader.Reserved], esi
0x180051a81  xorps   xmm0, xmm0
0x180051a84  movdqu  xmmword ptr [rsp+248h+hstringHeader.Reserved+8], xmm0
0x180051a8d  mov     rax, [rcx]
0x180051a90  lea     rdx, [rsp+248h+var_204]
0x180051a95  mov     rax, [rax+38h]
0x180051a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a9e  lea     r8, [rsp+248h+hstringHeader]
0x180051aa6  mov     edx, eax
0x180051aa8  lea     rcx, [rsp+248h+var_220]
0x180051aad  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180051ab2  cmp     r12d, [rsp+248h+var_204]
0x180051ab7  jz      loc_180051E58
0x180051abd  lea     rdx, [rsp+248h+var_1F0]
0x180051ac2  lea     rcx, [rsp+248h+var_180]
0x180051aca  call    ??D?$fast_iterator@U?$IVectorView@UAppExtension@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@QEBA?AUAppExtension@StateRepository@Internal@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::AppExtension>>::operator*(void)
0x180051acf  nop
0x180051ad0  lea     rdx, [rsp+248h+var_1F8]
0x180051ad5  lea     rcx, [rsp+248h+var_1F0]
0x180051ada  call    ?GetExtension@?$consume_Windows_Internal_StateRepository_IAppExtension@UIAppExtension@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IAppExtension<winrt::Windows::Internal::StateRepository::IAppExtension>::GetExtension(void)
0x180051adf  nop
0x180051ae0  lea     rdx, [rsp+248h+var_220]
0x180051ae5  lea     rcx, [rsp+248h+var_1F8]
0x180051aea  call    ?GetApplication@?$consume_Windows_Internal_StateRepository_IApplicationExtension@UIApplicationExtension@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::GetApplication(void)
0x180051aef  nop
0x180051af0  lea     rcx, [rsp+248h+var_220]
0x180051af5  call    ?AppListEntry@?$consume_Windows_Internal_StateRepository_IApplication@UIApplication@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::AppListEntry(void)
0x180051afa  cmp     eax, 1
0x180051afd  jz      loc_180051E28
0x180051b03  lea     rdx, [rsp+248h+var_200]
0x180051b08  lea     rcx, [rsp+248h+var_220]
0x180051b0d  call    ?GetApplication@?$consume_Windows_Internal_StateRepository_IApplicationExtension@UIApplicationExtension@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::GetApplication(void)
0x180051b12  nop
0x180051b13  lea     rdx, [rsp+248h+var_190]
0x180051b1b  lea     rcx, [rsp+248h+var_200]
0x180051b20  call    ?GetApplication@?$consume_Windows_Internal_StateRepository_IApplicationExtension@UIApplicationExtension@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::GetApplication(void)
0x180051b25  nop
0x180051b26  lea     rdx, [rsp+248h+var_1C0]
0x180051b2e  mov     rcx, rax
0x180051b31  call    ?PackageFamilyName@?$consume_Windows_Internal_StateRepository_IPackageFamily@UIPackageFamily@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IPackageFamily<winrt::Windows::Internal::StateRepository::IPackageFamily>::PackageFamilyName(void)
0x180051b36  nop
0x180051b37  lea     rcx, [rsp+248h+var_190]; this
0x180051b3f  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180051b44  lea     rdx, [rsp+248h+var_1C0]
0x180051b4c  lea     rcx, [rsp+248h+hstringHeader]
0x180051b54  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180051b59  nop
0x180051b5a  lea     rdi, [r15+128h]
0x180051b61  mov     rcx, rdi; SRWLock
0x180051b64  call    cs:__imp_AcquireSRWLockShared
0x180051b6a  mov     [rsp+248h+var_1E0], rdi
0x180051b6f  lea     rbx, [r15+110h]
0x180051b76  lea     r8, [rsp+248h+hstringHeader]
0x180051b7e  mov     rdx, [r15+118h]
0x180051b85  mov     rcx, [rbx]
0x180051b88  call    std__any_of_std___Vector_iterator_std___Vector_val_std___Simple_types_SystemSettings__PenSettings__PenLaunchableAppInfo_______lambda_a0927790aae09644f5c2dccac6dd8005___
0x180051b8d  lea     rcx, [rsp+248h+var_1E0]
0x180051b92  test    al, al
0x180051b94  jz      short loc_180051BA0
0x180051b96  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180051b9b  jmp     loc_180051E01
0x180051ba0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180051ba5  lea     rdx, [rsp+248h+var_220]
0x180051baa  lea     rcx, [rsp+248h+var_1C8]; struct Application *
0x180051bb2  call    ?Create@ApplicationResourceResolver@StateRepository@Internal@Windows@winrt@@SA@AEBUApplication@2345@@Z; winrt::Windows::Internal::StateRepository::ApplicationResourceResolver::Create(winrt::Windows::Internal::StateRepository::Application const &)
0x180051bb7  nop
0x180051bb8  lea     rdx, [rsp+248h+var_1D0]
0x180051bbd  lea     rcx, [rsp+248h+var_1C8]
0x180051bc5  call    ?GetSquare44x44LogoLocalized@?$consume_Windows_Internal_StateRepository_IApplicationResourceResolver@UIApplicationResourceResolver@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationResourceResolver<winrt::Windows::Internal::StateRepository::IApplicationResourceResolver>::GetSquare44x44LogoLocalized(void)
0x180051bca  nop
0x180051bcb  xorps   xmm0, xmm0
0x180051bce  movups  [rsp+248h+var_128], xmm0
0x180051bd6  movdqa  [rsp+248h+var_118], xmm6
0x180051bdf  mov     word ptr [rsp+248h+var_128], si
0x180051be7  movups  [rsp+248h+var_108], xmm0
0x180051bef  movdqa  [rsp+248h+var_F8], xmm6
0x180051bf8  mov     word ptr [rsp+248h+var_108], si
0x180051c00  movups  [rsp+248h+var_E8], xmm0
0x180051c08  movdqa  [rsp+248h+var_D8], xmm6
0x180051c11  mov     word ptr [rsp+248h+var_E8], si
0x180051c19  movups  [rsp+248h+var_C8], xmm0
0x180051c21  movdqa  [rsp+248h+var_B8], xmm6
0x180051c2a  mov     word ptr [rsp+248h+var_C8], si
0x180051c32  xor     eax, eax
0x180051c34  mov     [rsp+248h+var_A7], eax
0x180051c3b  mov     [rsp+248h+var_A3], ax
0x180051c43  mov     [rsp+248h+var_A1], al
0x180051c4a  mov     [rsp+248h+var_A8], 1
  ... truncated ...
```

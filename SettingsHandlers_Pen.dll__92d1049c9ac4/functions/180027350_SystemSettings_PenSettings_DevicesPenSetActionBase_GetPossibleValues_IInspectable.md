# SystemSettings::PenSettings::DevicesPenSetActionBase::GetPossibleValues(IInspectable * *)

- ea: `0x180027350`
- end: `0x180027b11`
- name: `?GetPossibleValues@DevicesPenSetActionBase@PenSettings@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `1985`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenSetActionBase *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180003110`
- `0x180005b2c`
- `0x18000a2bc`
- `0x18000d02c`
- `0x18001012c`
- `0x18001033c`
- `0x180012154`
- `0x1800161a0`
- `0x180019a40`
- `0x180019fcc`
- `0x18001a378`
- `0x180022654`
- `0x18002668c`
- `0x18002674c`
- `0x1800271d0`
- `0x180027350`
- `0x180027dcc`
- `0x1800284f8`
- `0x18002bb6c`
- `0x18002bbb0`
- `0x18002c1d0`
- `0x18002c3c8`
- `0x18002c44c`
- `0x18002cc6c`
- `0x18002efa4`
- `0x18002f090`
- `0x180031514`
- `0x180054394`
- `0x1800543f4`
- `0x1800550e0`
- `0x180057a24`

## string_xrefs

- `0x1800273f4`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800275a2`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800275f0`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002776f`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180027872`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800278c0`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800279bc`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180027a49`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionBase::GetPossibleValues(
        SystemSettings::PenSettings::DevicesPenSetActionBase *this,
        struct IInspectable **a2)
{
  unsigned int v3; // r12d
  char **v4; // rax
  __int64 v5; // rdi
  int v6; // ebx
  __int64 v7; // rdx
  SystemSettings::PenSettings *v9; // rcx
  bool IsDesktop; // r13
  char IsEnabled; // al
  unsigned __int16 *v12; // r15
  unsigned int v13; // ebx
  unsigned int v14; // eax
  char *i; // rax
  bool v16; // zf
  unsigned __int16 **v17; // r8
  int ResourceStringById; // eax
  unsigned int v19; // ebx
  int appended; // eax
  unsigned int v21; // ebx
  __m128i si128; // xmm6
  __int64 v23; // rcx
  const WCHAR *v24; // rax
  const unsigned __int16 *v25; // rdx
  SystemSettings::PenSettings *v26; // rax
  const unsigned __int16 *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // ebx
  SystemSettings::DataModel *v31; // rdi
  unsigned __int16 **v32; // r8
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // rax
  int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // rax
  int v41; // eax
  unsigned int v42; // ebx
  int v43; // [rsp+20h] [rbp-138h]
  __int64 v44; // [rsp+30h] [rbp-128h] BYREF
  unsigned __int16 *v45; // [rsp+38h] [rbp-120h] BYREF
  char **v46; // [rsp+40h] [rbp-118h] BYREF
  unsigned int v47; // [rsp+48h] [rbp-110h] BYREF
  int v48[2]; // [rsp+50h] [rbp-108h] BYREF
  __int64 v49; // [rsp+58h] [rbp-100h] BYREF
  __int64 v50; // [rsp+60h] [rbp-F8h] BYREF
  struct IInspectable **v51; // [rsp+68h] [rbp-F0h]
  unsigned __int16 v52[8]; // [rsp+70h] [rbp-E8h] BYREF
  __m128i v53; // [rsp+80h] [rbp-D8h]
  _BYTE v54[16]; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-B8h]
  _BYTE v56[32]; // [rsp+B0h] [rbp-A8h] BYREF
  _BYTE v57[32]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v58[32]; // [rsp+F0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v51 = a2;
  v3 = 0;
  *a2 = 0;
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
  v44 = 0;
  v4 = (char **)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v46 = v4;
  v5 = 0;
  if ( v4 )
  {
    v5 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v4);
    v46 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>::~MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>(&v46);
  if ( v5 )
  {
    v6 = 0;
    v44 = v5;
  }
  else
  {
    v6 = -2147024882;
  }
  if ( v6 < 0 )
  {
    v7 = 2029;
    goto LABEL_8;
  }
  v50 = 0;
  v45 = 0;
  v46 = 0;
  *(_QWORD *)v48 = 0;
  v49 = 0;
  SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(
    *((_DWORD *)this + 68),
    (unsigned int)&v45,
    (unsigned int)&v50,
    (unsigned int)&v46,
    (__int64)v48,
    (__int64)&v49);
  IsDesktop = SystemSettings::PenSettings::IsDesktop(v9);
  if ( !IsDesktop )
  {
    v12 = v45;
    goto LABEL_33;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl);
  v12 = v45;
  if ( IsEnabled )
  {
    v47 = -1;
    SHRegGetDWORD(HKEY_CURRENT_USER, v45, L"Override", &v47);
    v13 = v47;
    if ( v47 == -1 )
    {
LABEL_27:
      memset(v52, 0, sizeof(v52));
      v53.m128i_i64[0] = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
      *(_QWORD *)&v52[4] = -1;
      v53.m128i_i64[0] = -1;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_NoneSelected",
                             v52,
                             v17);
      v19 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x83A,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
          (const char *)(unsigned int)ResourceStringById,
          v43);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
        return v19;
      }
      appended = SystemSettings::DataModel::AppendStringToVector(*(_QWORD *)v52, v44);
      v21 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x83B,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
          (const char *)(unsigned int)appended,
          v43);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
        return v21;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
      goto LABEL_33;
    }
    if ( !SystemSettings::PenSettings::DevicesPenSetActionBase::IsActionMigrated(v12) )
    {
      v14 = SystemSettings::PenSettings::DevicesPenSetActionBase::MigrateLegacyAction(v13, v12);
      if ( v14 != v13 )
        v13 = v14;
    }
    if ( v13 == 18 )
    {
      LODWORD(v45) = 0;
      SHRegGetDWORD(HKEY_CURRENT_USER, v12, L"AppType", (unsigned int *)&v45);
      if ( !(_DWORD)v45 )
      {
        SystemSettings::PenSettings::DevicesPenSetActionBase::SetAppsList(this);
        v16 = !SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomAppAvailable(this);
        goto LABEL_26;
      }
      if ( SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomDesktopAppAvailable(this) )
        goto LABEL_33;
    }
    else
    {
      for ( i = *v46; i != v46[1]; i += 16 )
      {
        if ( *(_DWORD *)i == v13 )
          goto LABEL_25;
      }
    }
    v13 = -1;
LABEL_25:
    v16 = v13 == -1;
LABEL_26:
    if ( v16 )
      goto LABEL_27;
  }
LABEL_33:
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v3 < (unsigned __int64)((v46[1] - *v46) >> 4) )
  {
    v23 = *(unsigned int *)&(*v46)[16 * v3];
    if ( (_DWORD)v23 == 12 )
    {
      std::wstring::wstring(v57, *(_QWORD *)v48);
      SystemSettings::PenSettings::GetOemPolicyValue(v54, v57);
      std::wstring::_Tidy_deallocate(v57);
      std::wstring::wstring(v58, v49);
      SystemSettings::PenSettings::GetOemPolicyValue(v56, v58);
      std::wstring::_Tidy_deallocate(v58);
      *(_OWORD *)v52 = 0;
      v53 = si128;
      v52[0] = 0;
      if ( v55 )
      {
        v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
        if ( SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(v24, v25) )
        {
          v26 = (SystemSettings::PenSettings *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
          if ( SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(v26, v27)
            && (int)SystemSettings::PenSettings::GetAppDisplayNameByAumid(v54, v52) >= 0 )
          {
            v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
            v29 = SystemSettings::DataModel::AppendStringToVector(v28, v44);
            v30 = v29;
            if ( v29 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x84B,
                (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
                (const char *)(unsigned int)v29,
                v43);
              std::wstring::_Tidy_deallocate(v52);
              std::wstring::_Tidy_deallocate(v56);
              std::wstring::_Tidy_deallocate(v54);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
              return v30;
            }
          }
        }
      }
      std::wstring::_Tidy_deallocate(v52);
      std::wstring::_Tidy_deallocate(v56);
      std::wstring::_Tidy_deallocate(v54);
    }
    else
    {
      if ( (_DWORD)v23 || !(unsigned int)SHRegSubKeyExistsW(v23, v50) )
        v31 = *(SystemSettings::DataModel **)&(*v46)[16 * v3 + 8];
      else
        v31 = (SystemSettings::DataModel *)L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_DeviceDefault";
      if ( IsDesktop
        || SystemSettings::PenSettings::ActionTypeOptionManager::IsActionValid((const unsigned __int16 *)v31) )
      {
        memset(v52, 0, sizeof(v52));
        v53.m128i_i64[0] = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
        *(_QWORD *)&v52[4] = -1;
        v53.m128i_i64[0] = -1;
        v33 = SystemSettings::DataModel::GetResourceStringById(v31, v52, v32);
        v34 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x860,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)v33,
            v43);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
          return v34;
        }
        v35 = SystemSettings::DataModel::AppendStringToVector(*(_QWORD *)v52, v44);
        v36 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x861,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)v35,
            v43);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
          return v36;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl)
          && (!wcscmp_0((const wchar_t *)v31, L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_DoNothing")
           || !wcscmp_0((const wchar_t *)v31, L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_Disabled")) )
        {
          LODWORD(v45) = 0;
          SHRegGetDWORD(HKEY_CURRENT_USER, v12, L"AppType", (unsigned int *)&v45);
          if ( (_DWORD)v45 )
          {
            if ( SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomDesktopAppAvailable(this) )
            {
              SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomDesktopAppDisplayName(this, v54);
              if ( v55 )
              {
                v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
                v41 = SystemSettings::DataModel::AppendStringToVector(v40, v44);
                v42 = v41;
                if ( v41 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x882,
                    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
                    (const char *)(unsigned int)v41,
                    v43);
                  std::wstring::_Tidy_deallocate(v54);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
                  return v42;
                }
              }
LABEL_65:
              std::wstring::_Tidy_deallocate(v54);
            }
          }
          else
          {
            SystemSettings::PenSettings::DevicesPenSetActionBase::SetAppsList(this);
            if ( SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomAppAvailable(this) )
            {
              SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomAppDisplayName(this, v54);
              if ( v55 )
              {
                v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
                v38 = SystemSettings::DataModel::AppendStringToVector(v37, v44);
                v39 = v38;
                if ( v38 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x876,
                    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
                    (const char *)(unsigned int)v38,
                    v43);
                  std::wstring::_Tidy_deallocate(v54);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
                  return v39;
                }
              }
              goto LABEL_65;
            }
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v52);
      }
    }
    ++v3;
  }
  v6 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
         v44,
         &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
         v51);
  if ( v6 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
    return 0;
  }
  else
  {
    v7 = 2188;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v6,
      v43);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v44);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180027350  mov     rax, rsp
0x180027353  mov     [rax+18h], rbx
0x180027357  push    rdi
0x180027358  push    r12
0x18002735a  push    r13
0x18002735c  push    r14
0x18002735e  push    r15
0x180027360  sub     rsp, 130h
0x180027367  movaps  xmmword ptr [rax-38h], xmm6
0x18002736b  mov     rax, cs:__security_cookie
0x180027372  xor     rax, rsp
0x180027375  mov     [rsp+158h+var_48], rax
0x18002737d  mov     [rsp+158h+var_F0], rdx
0x180027382  mov     r14, rcx
0x180027385  xor     r12d, r12d
0x180027388  mov     [rdx], r12
0x18002738b  mov     [rsp+158h+var_128], r12
0x180027390  lea     rcx, [rsp+158h+var_128]
0x180027395  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x18002739a  mov     [rsp+158h+var_128], r12
0x18002739f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800273a6  mov     ecx, 0B8h; unsigned __int64
0x1800273ab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800273b0  mov     [rsp+158h+var_118], rax
0x1800273b5  mov     edi, r12d
0x1800273b8  test    rax, rax
0x1800273bb  jz      short loc_1800273CD
0x1800273bd  mov     rcx, rax
0x1800273c0  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x1800273c5  mov     rdi, rax
0x1800273c8  mov     [rsp+158h+var_118], r12
0x1800273cd  lea     rcx, [rsp+158h+var_118]
0x1800273d2  call    ??1?$MakeAllocator@VCDevicesPenEnableKeyPressedDisplay@PenSettings@SystemSettings@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>::~MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>(void)
0x1800273d7  test    rdi, rdi
0x1800273da  jnz     short loc_1800273E3
0x1800273dc  mov     ebx, 8007000Eh
0x1800273e1  jmp     short loc_1800273EB
0x1800273e3  mov     ebx, r12d
0x1800273e6  mov     [rsp+158h+var_128], rdi
0x1800273eb  test    ebx, ebx
0x1800273ed  jns     short loc_18002741D
0x1800273ef  mov     edx, 7EDh; void *
0x1800273f4  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800273fb  mov     r9d, ebx; char *
0x1800273fe  mov     rcx, [rsp+158h]; this
0x180027406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002740b  nop
0x18002740c  lea     rcx, [rsp+158h+var_128]
0x180027411  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180027416  mov     eax, ebx
0x180027418  jmp     loc_180027AE3
0x18002741d  mov     [rsp+158h+var_F8], r12
0x180027422  mov     [rsp+158h+var_120], r12
0x180027427  mov     [rsp+158h+var_118], r12
0x18002742c  mov     qword ptr [rsp+158h+var_108], r12
0x180027431  mov     [rsp+158h+var_100], r12
0x180027436  lea     rax, [rsp+158h+var_100]
0x18002743b  mov     [rsp+158h+var_130], rax
0x180027440  lea     rax, [rsp+158h+var_108]
0x180027445  mov     qword ptr [rsp+158h+var_138], rax; int
0x18002744a  lea     r9, [rsp+158h+var_118]
0x18002744f  lea     r8, [rsp+158h+var_F8]
0x180027454  lea     rdx, [rsp+158h+var_120]
0x180027459  mov     ecx, [r14+110h]
0x180027460  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x180027465  call    ?IsDesktop@PenSettings@SystemSettings@@YA_NXZ; SystemSettings::PenSettings::IsDesktop(void)
0x18002746a  mov     r13b, al
0x18002746d  test    al, al
0x18002746f  jz      loc_18002762A
0x180027475  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x18002747c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180027481  mov     r15, [rsp+158h+var_120]
0x180027486  test    al, al
0x180027488  jz      loc_18002762F
0x18002748e  mov     [rsp+158h+var_110], 0FFFFFFFFh
0x180027496  lea     r9, [rsp+158h+var_110]; unsigned int *
0x18002749b  lea     r8, aOverride; "Override"
0x1800274a2  mov     rdx, r15; unsigned __int16 *
0x1800274a5  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800274ac  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800274b1  mov     ebx, [rsp+158h+var_110]
0x1800274b5  cmp     ebx, 0FFFFFFFFh
0x1800274b8  jz      loc_18002754F
0x1800274be  mov     rcx, r15; unsigned __int16 *
0x1800274c1  call    ?IsActionMigrated@DevicesPenSetActionBase@PenSettings@SystemSettings@@CA_NPEBG@Z; SystemSettings::PenSettings::DevicesPenSetActionBase::IsActionMigrated(ushort const *)
0x1800274c6  test    al, al
0x1800274c8  jnz     short loc_1800274D9
0x1800274ca  mov     rdx, r15
0x1800274cd  mov     ecx, ebx
0x1800274cf  call    ?MigrateLegacyAction@DevicesPenSetActionBase@PenSettings@SystemSettings@@CA?AW4PenClickOverride@@W44@PEBG@Z; SystemSettings::PenSettings::DevicesPenSetActionBase::MigrateLegacyAction(PenClickOverride,ushort const *)
0x1800274d4  cmp     eax, ebx
0x1800274d6  cmovnz  ebx, eax
0x1800274d9  cmp     ebx, 12h
0x1800274dc  jz      short loc_1800274FB
0x1800274de  mov     rcx, [rsp+158h+var_118]
0x1800274e3  mov     rax, [rcx]
0x1800274e6  mov     rdx, [rcx+8]
0x1800274ea  jmp     short loc_1800274F4
0x1800274ec  cmp     [rax], ebx
0x1800274ee  jz      short loc_180027546
0x1800274f0  add     rax, 10h
0x1800274f4  cmp     rax, rdx
0x1800274f7  jnz     short loc_1800274EC
0x1800274f9  jmp     short loc_180027543
0x1800274fb  mov     dword ptr [rsp+158h+var_120], r12d
0x180027500  lea     r9, [rsp+158h+var_120]; unsigned int *
0x180027505  lea     r8, aApptype; "AppType"
0x18002750c  mov     rdx, r15; unsigned __int16 *
0x18002750f  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180027516  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002751b  mov     rcx, r14; this
0x18002751e  cmp     dword ptr [rsp+158h+var_120], r12d
0x180027523  jnz     short loc_180027536
0x180027525  call    ?SetAppsList@DevicesPenSetActionBase@PenSettings@SystemSettings@@QEAAXXZ; SystemSettings::PenSettings::DevicesPenSetActionBase::SetAppsList(void)
0x18002752a  mov     rcx, r14; this
0x18002752d  call    ?IsCustomAppAvailable@DevicesPenSetActionBase@PenSettings@SystemSettings@@AEAA_NXZ; SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomAppAvailable(void)
0x180027532  test    al, al
0x180027534  jmp     short loc_180027549
0x180027536  call    ?IsCustomDesktopAppAvailable@DevicesPenSetActionBase@PenSettings@SystemSettings@@AEAA_NXZ; SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomDesktopAppAvailable(void)
0x18002753b  test    al, al
0x18002753d  jnz     loc_18002762F
0x180027543  or      ebx, 0FFFFFFFFh
0x180027546  cmp     ebx, 0FFFFFFFFh
0x180027549  jnz     loc_18002762F
0x18002754f  mov     qword ptr [rsp+158h+var_E8], r12
0x180027554  mov     qword ptr [rsp+158h+var_E8+8], r12
0x180027559  mov     qword ptr [rsp+158h+var_D8], r12
0x180027561  lea     rcx, [rsp+158h+var_E8]
0x180027566  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002756b  mov     qword ptr [rsp+158h+var_E8+8], 0FFFFFFFFFFFFFFFFh
0x180027574  mov     qword ptr [rsp+158h+var_D8], 0FFFFFFFFFFFFFFFFh
0x180027580  lea     rdx, [rsp+158h+var_E8]; unsigned __int16 *
0x180027585  lea     rcx, aSystemsettings_19; "SystemSettings_Devices_Pen_ButtonCustom"...
0x18002758c  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x180027591  mov     ebx, eax
0x180027593  test    eax, eax
0x180027595  jns     short loc_1800275D0
0x180027597  mov     rcx, [rsp+158h]; this
0x18002759f  mov     r9d, eax; char *
0x1800275a2  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800275a9  mov     edx, 83Ah; void *
0x1800275ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800275b3  nop
0x1800275b4  lea     rcx, [rsp+158h+var_E8]
0x1800275b9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800275be  nop
0x1800275bf  lea     rcx, [rsp+158h+var_128]
0x1800275c4  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x1800275c9  mov     eax, ebx
0x1800275cb  jmp     loc_180027AE3
0x1800275d0  mov     rdx, [rsp+158h+var_128]
0x1800275d5  mov     rcx, qword ptr [rsp+158h+var_E8]
0x1800275da  call    ?AppendStringToVector@DataModel@SystemSettings@@YAJPEBGPEAV?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@Z; SystemSettings::DataModel::AppendStringToVector(ushort const *,Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>> *)
0x1800275df  mov     ebx, eax
0x1800275e1  test    eax, eax
0x1800275e3  jns     short loc_18002761E
0x1800275e5  mov     rcx, [rsp+158h]; this
0x1800275ed  mov     r9d, eax; char *
0x1800275f0  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800275f7  mov     edx, 83Bh; void *
0x1800275fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027601  nop
0x180027602  lea     rcx, [rsp+158h+var_E8]
0x180027607  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002760c  nop
0x18002760d  lea     rcx, [rsp+158h+var_128]
0x180027612  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180027617  mov     eax, ebx
0x180027619  jmp     loc_180027AE3
0x18002761e  lea     rcx, [rsp+158h+var_E8]
0x180027623  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027628  jmp     short loc_18002762F
0x18002762a  mov     r15, [rsp+158h+var_120]
0x18002762f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180027637  mov     rcx, [rsp+158h+var_118]
0x18002763c  mov     edi, r12d
0x18002763f  mov     rax, [rcx+8]
0x180027643  sub     rax, [rcx]
0x180027646  sar     rax, 4
0x18002764a  cmp     rdi, rax
0x18002764d  jnb     loc_180027AA1
0x180027653  add     rdi, rdi
0x180027656  mov     rax, [rcx]
0x180027659  mov     ecx, [rax+rdi*8]
0x18002765c  cmp     ecx, 0Ch
0x18002765f  jnz     loc_1800277E4
0x180027665  mov     rdx, qword ptr [rsp+158h+var_108]
0x18002766a  lea     rcx, [rsp+158h+var_88]
0x180027672  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027677  nop
0x180027678  lea     rdx, [rsp+158h+var_88]
0x180027680  lea     rcx, [rsp+158h+var_C8]
0x180027688  call    ?GetOemPolicyValue@PenSettings@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; SystemSettings::PenSettings::GetOemPolicyValue(std::wstring const &)
0x18002768d  nop
0x18002768e  lea     rcx, [rsp+158h+var_88]
0x180027696  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002769b  mov     rdx, [rsp+158h+var_100]
0x1800276a0  lea     rcx, [rsp+158h+var_68]
0x1800276a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800276ad  nop
0x1800276ae  lea     rdx, [rsp+158h+var_68]
0x1800276b6  lea     rcx, [rsp+158h+var_A8]
0x1800276be  call    ?GetOemPolicyValue@PenSettings@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; SystemSettings::PenSettings::GetOemPolicyValue(std::wstring const &)
0x1800276c3  nop
0x1800276c4  lea     rcx, [rsp+158h+var_68]
0x1800276cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800276d1  xorps   xmm0, xmm0
0x1800276d4  movups  xmmword ptr [rsp+158h+var_E8], xmm0
0x1800276d9  movdqu  [rsp+158h+var_D8], xmm6
0x1800276e2  xor     eax, eax
0x1800276e4  mov     [rsp+158h+var_E8], ax
0x1800276e9  cmp     [rsp+158h+var_B8], rax
0x1800276f1  jz      loc_1800277B9
0x1800276f7  lea     rcx, [rsp+158h+var_C8]
0x1800276ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027704  mov     rcx, rax; lpString1
0x180027707  call    ?IsOemAumidAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(ushort const *)
0x18002770c  test    al, al
0x18002770e  jz      loc_1800277B9
0x180027714  lea     rcx, [rsp+158h+var_A8]
0x18002771c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027721  mov     rcx, rax; this
0x180027724  call    ?IsOemUriAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(ushort const *)
0x180027729  test    al, al
0x18002772b  jz      loc_1800277B9
0x180027731  lea     rdx, [rsp+158h+var_E8]
0x180027736  lea     rcx, [rsp+158h+var_C8]
0x18002773e  call    ?GetAppDisplayNameByAumid@PenSettings@SystemSettings@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; SystemSettings::PenSettings::GetAppDisplayNameByAumid(std::wstring const &,std::wstring &)
0x180027743  test    eax, eax
0x180027745  js      short loc_1800277B9
0x180027747  lea     rcx, [rsp+158h+var_E8]
0x18002774c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027751  mov     rcx, rax
0x180027754  mov     rdx, [rsp+158h+var_128]
0x180027759  call    ?AppendStringToVector@DataModel@SystemSettings@@YAJPEBGPEAV?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@Z; SystemSettings::DataModel::AppendStringToVector(ushort const *,Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>> *)
0x18002775e  mov     ebx, eax
0x180027760  test    eax, eax
0x180027762  jns     short loc_1800277B9
0x180027764  mov     rcx, [rsp+158h]; this
0x18002776c  mov     r9d, eax; char *
0x18002776f  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180027776  mov     edx, 84Bh; void *
0x18002777b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027780  nop
0x180027781  lea     rcx, [rsp+158h+var_E8]
0x180027786  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002778b  nop
0x18002778c  lea     rcx, [rsp+158h+var_A8]
0x180027794  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027799  nop
0x18002779a  lea     rcx, [rsp+158h+var_C8]
0x1800277a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277a7  nop
0x1800277a8  lea     rcx, [rsp+158h+var_128]
0x1800277ad  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x1800277b2  mov     eax, ebx
0x1800277b4  jmp     loc_180027AE3
0x1800277b9  lea     rcx, [rsp+158h+var_E8]
0x1800277be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277c3  nop
0x1800277c4  lea     rcx, [rsp+158h+var_A8]
0x1800277cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277d1  nop
0x1800277d2  lea     rcx, [rsp+158h+var_C8]
0x1800277da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277df  jmp     loc_180027A99
0x1800277e4  xor     ebx, ebx
0x1800277e6  test    ecx, ecx
0x1800277e8  jnz     short loc_180027801
0x1800277ea  mov     rdx, [rsp+158h+var_F8]
0x1800277ef  call    SHRegSubKeyExistsW
0x1800277f4  test    eax, eax
0x1800277f6  jz      short loc_180027801
0x1800277f8  lea     rdi, String1; "SystemSettings_Devices_Pen_ButtonCustom"...
0x1800277ff  jmp     short loc_18002780E
0x180027801  mov     rax, [rsp+158h+var_118]
0x180027806  mov     rcx, [rax]
0x180027809  mov     rdi, [rcx+rdi*8+8]
0x18002780e  test    r13b, r13b
0x180027811  jnz     short loc_180027823
0x180027813  mov     rcx, rdi; unsigned __int16 *
0x180027816  call    ?IsActionValid@ActionTypeOptionManager@PenSettings@SystemSettings@@SA_NPEBG@Z; SystemSettings::PenSettings::ActionTypeOptionManager::IsActionValid(ushort const *)
0x18002781b  test    al, al
0x18002781d  jz      loc_180027A99
0x180027823  mov     qword ptr [rsp+158h+var_E8], rbx
0x180027828  mov     qword ptr [rsp+158h+var_E8+8], rbx
0x18002782d  mov     qword ptr [rsp+158h+var_D8], rbx
0x180027835  lea     rcx, [rsp+158h+var_E8]
0x18002783a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002783f  mov     qword ptr [rsp+158h+var_E8+8], 0FFFFFFFFFFFFFFFFh
0x180027848  mov     qword ptr [rsp+158h+var_D8], 0FFFFFFFFFFFFFFFFh
0x180027854  lea     rdx, [rsp+158h+var_E8]; unsigned __int16 *
0x180027859  mov     rcx, rdi; this
0x18002785c  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x180027861  mov     ebx, eax
0x180027863  test    eax, eax
0x180027865  jns     short loc_1800278A0
0x180027867  mov     rcx, [rsp+158h]; this
0x18002786f  mov     r9d, eax; char *
0x180027872  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
  ... truncated ...
```

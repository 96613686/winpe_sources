# SystemSettings::PenSettings::DevicesPenSetActionBase::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x18002faf0`
- end: `0x180030124`
- name: `?SetValue@DevicesPenSetActionBase@PenSettings@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `1588`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenSetActionBase *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005f0c`
- `0x18000a2bc`
- `0x18001033c`
- `0x1800168b4`
- `0x180016d6c`
- `0x180019a40`
- `0x180019fcc`
- `0x18001a378`
- `0x18001b9c0`
- `0x18001da60`
- `0x180022654`
- `0x18002668c`
- `0x18002674c`
- `0x1800271d0`
- `0x180027dcc`
- `0x1800284f8`
- `0x18002c44c`
- `0x18002c690`
- `0x18002efec`
- `0x18002f090`
- `0x18002faf0`
- `0x180031514`
- `0x18004c1cc`
- `0x18004c3f4`
- `0x18004c554`
- `0x18004fe28`
- `0x1800525c4`
- `0x180052dc4`
- `0x180052e6c`
- `0x180052eec`
- `0x180054394`
- `0x1800543f4`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180030097`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180030097`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ffc4`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002fff6`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ffc4`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002fff6`

## string_xrefs

- `0x18002ffe5`: `CustomAppPath`
- `0x18002fb4e`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002fbed`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionBase::SetValue(
        SystemSettings::PenSettings::DevicesPenSetActionBase *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned __int16 **v5; // r8
  int ResourceStringById; // eax
  const unsigned __int16 *v7; // r8
  const WCHAR *v8; // rax
  const unsigned __int16 *v9; // rdx
  SystemSettings::PenSettings *v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // esi
  SystemSettings::PenSettings *v13; // rcx
  const unsigned __int16 *v14; // r14
  HSTRING v15; // rax
  const unsigned __int16 *v16; // r8
  HSTRING v17; // rax
  const unsigned __int16 *v18; // r8
  char v19; // bl
  HSTRING v20; // rax
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // rdx
  unsigned int v24; // ebx
  int v25; // eax
  struct SystemSettings::PenSettings::PenButtonCustomizationSingleton *Instance; // rax
  int v27; // [rsp+20h] [rbp-118h]
  int v28; // [rsp+20h] [rbp-118h]
  RTL_SRWLOCK *v29; // [rsp+30h] [rbp-108h] BYREF
  SystemSettings::DataModel *v30; // [rsp+38h] [rbp-100h] BYREF
  LPCWSTR pszSubKey; // [rsp+40h] [rbp-F8h] BYREF
  RTL_SRWLOCK **v32; // [rsp+48h] [rbp-F0h] BYREF
  HSTRING v33; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-E0h]
  __int64 v35; // [rsp+60h] [rbp-D8h]
  int v36[2]; // [rsp+68h] [rbp-D0h] BYREF
  _OWORD v37[2]; // [rsp+70h] [rbp-C8h] BYREF
  _BYTE v38[16]; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-98h]
  _BYTE v40[16]; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-78h]
  _BYTE v42[16]; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v43; // [rsp+E0h] [rbp-58h]
  _BYTE v44[32]; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v30 = 0;
  v3 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, SystemSettings::DataModel **))(*(_QWORD *)a2 + 152LL))(
         a2,
         &v30);
  v4 = v3;
  if ( v3 >= 0 )
  {
    pszSubKey = 0;
    v29 = 0;
    *(_QWORD *)v36 = 0;
    v32 = 0;
    SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(
      *((_DWORD *)this + 68),
      (unsigned int)&pszSubKey,
      0,
      (unsigned int)&v29,
      (__int64)v36,
      (__int64)&v32);
    v33 = 0;
    v34 = 0;
    v35 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
    v34 = -1;
    v35 = -1;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_DeviceDefault",
                           (const unsigned __int16 *)&v33,
                           v5);
    v4 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A0,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)ResourceStringById,
        v28);
LABEL_49:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
      return v4;
    }
    std::wstring::wstring(v42, *(_QWORD *)v36);
    SystemSettings::PenSettings::GetOemPolicyValue(v38, v42);
    std::wstring::_Tidy_deallocate(v42);
    std::wstring::wstring(v40, v32);
    SystemSettings::PenSettings::GetOemPolicyValue(v44, v40);
    std::wstring::_Tidy_deallocate(v40);
    v37[0] = 0;
    v37[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v37[0]) = 0;
    if ( v39 )
    {
      v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
      if ( SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(v8, v9) )
      {
        v10 = (SystemSettings::PenSettings *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
        if ( SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(v10, v11) )
          SystemSettings::PenSettings::GetAppDisplayNameByAumid(v38, v37);
      }
    }
    if ( SystemSettings::DataModel::IsHstringEqual(v30, v33, v7) )
    {
      v12 = 0;
LABEL_11:
      if ( v12 != -1 )
      {
        if ( (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl)
           || !SystemSettings::PenSettings::IsDesktop(v13))
          && (v12 == 5 || v12 == 11) )
        {
          v14 = pszSubKey;
          SHRegSetDWORD((HKEY)v13, pszSubKey, L"PenWorkspaceVerb", v12 != 5);
          SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(
            *((unsigned int *)this + 68),
            v12 != 5);
          v12 = 5;
        }
        else
        {
          v14 = pszSubKey;
        }
        *((_DWORD *)this + 69) = v12;
        SHRegSetDWORD((HKEY)v13, v14, L"Override", v12);
        SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(
          *((unsigned int *)this + 68),
          *((unsigned int *)this + 69));
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
        {
          if ( *((_DWORD *)this + 69) != 2 )
          {
            SHDeleteValueW(HKEY_CURRENT_USER, v14, L"CustomAppId");
            SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(
              *((unsigned int *)this + 68),
              &word_1800679F0);
          }
          if ( *((_DWORD *)this + 69) != 3 )
          {
            SHDeleteValueW(HKEY_CURRENT_USER, v14, L"CustomAppPath");
            SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(
              *((unsigned int *)this + 68),
              &word_1800679F0);
          }
        }
        v25 = *((_DWORD *)this + 68);
        switch ( v25 )
        {
          case 1:
            CloudDataPenSettings::SaveSingleClickShortcutAsync(
              (SystemSettings::PenSettings::DevicesPenSetActionBase *)((char *)this + 312),
              *((_DWORD *)this + 69));
            break;
          case 2:
            CloudDataPenSettings::SaveDoubleClickShortcutAsync(
              (SystemSettings::PenSettings::DevicesPenSetActionBase *)((char *)this + 312),
              *((_DWORD *)this + 69));
            break;
          case 3:
            CloudDataPenSettings::SaveLongPressShortcutAsync(
              (SystemSettings::PenSettings::DevicesPenSetActionBase *)((char *)this + 312),
              *((_DWORD *)this + 69));
            break;
        }
        v29 = (RTL_SRWLOCK *)*((_QWORD *)this + 34);
        Instance = SystemSettings::PenSettings::PenButtonCustomizationSingleton::GetInstance();
        v32 = &v29;
        SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenGestureActionChangedEventArgs>::_Notify<_lambda_6640fc61c1b66f34ece762adb396642f_>(
          Instance,
          &v32);
      }
      AcquireSRWLockShared(&SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock);
      v29 = &SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock;
      PenSettingsTelemetry::LogPenSettingsTelemetry(
        L"UserOverrideSetting",
        *((unsigned int *)this + 68),
        &SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCache);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
      v4 = 0;
      std::wstring::_Tidy_deallocate(v37);
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(v38);
      goto LABEL_49;
    }
    v15 = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
    if ( SystemSettings::DataModel::IsHstringEqual(v30, v15, v16) )
    {
      v12 = 12;
      goto LABEL_11;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
    {
LABEL_30:
      v12 = SystemSettings::PenSettings::FindEnumFromStringArray<enum PenClickOverride,SystemSettings::PenSettings::PenActionTypeResourceMapping_>(v30);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
      {
        if ( v12 == 2 )
        {
          *(_WORD *)((char *)this + 281) = 1;
          SystemSettings::PenSettings::DevicesPenSetActionBase::SetAppsList(this);
          SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18006A460);
          SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18006A4F8);
          std::wstring::_Tidy_deallocate(v37);
          std::wstring::_Tidy_deallocate(v44);
          std::wstring::_Tidy_deallocate(v38);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
          return 0;
        }
        if ( v12 == 3 )
        {
          v24 = SystemSettings::PenSettings::DevicesPenSetActionBase::LaunchDesktopAppPicker(this, v22);
          std::wstring::_Tidy_deallocate(v37);
          std::wstring::_Tidy_deallocate(v44);
          std::wstring::_Tidy_deallocate(v38);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
          return v24;
        }
      }
      goto LABEL_11;
    }
    SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomAppDisplayName(this, v40);
    if ( v41
      && (v17 = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40),
          SystemSettings::DataModel::IsHstringEqual(v30, v17, v18)) )
    {
      v19 = 1;
      v12 = 18;
    }
    else
    {
      v12 = -1;
      v19 = 0;
      SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomDesktopAppDisplayName(this, v42);
      if ( v43 )
      {
        v20 = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
        if ( SystemSettings::DataModel::IsHstringEqual(v30, v20, v21) )
        {
          v19 = 1;
          v12 = 18;
        }
      }
      std::wstring::_Tidy_deallocate(v42);
      if ( !v19 )
        goto LABEL_29;
    }
    if ( *((_DWORD *)this + 69) == 18 )
    {
      std::wstring::_Tidy_deallocate(v40);
      std::wstring::_Tidy_deallocate(v37);
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(v38);
      v4 = 0;
      goto LABEL_49;
    }
LABEL_29:
    std::wstring::_Tidy_deallocate(v40);
    if ( v19 )
      goto LABEL_11;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x896,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
    (const char *)(unsigned int)v3,
    v27);
  return v4;
}

```

## disassembly

```asm
0x18002faf0  mov     [rsp+arg_10], rbx
0x18002faf5  mov     [rsp+arg_18], rsi
0x18002fafa  push    rdi
0x18002fafb  push    r14
0x18002fafd  push    r15
0x18002faff  sub     rsp, 120h
0x18002fb06  mov     rax, cs:__security_cookie
0x18002fb0d  xor     rax, rsp
0x18002fb10  mov     [rsp+138h+var_28], rax
0x18002fb18  mov     r8, rdx
0x18002fb1b  mov     rdi, rcx
0x18002fb1e  xor     r15d, r15d
0x18002fb21  mov     [rsp+138h+var_100], r15
0x18002fb26  mov     rax, [rdx]
0x18002fb29  lea     rdx, [rsp+138h+var_100]
0x18002fb2e  mov     rcx, r8
0x18002fb31  mov     rax, [rax+98h]
0x18002fb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb3d  mov     ebx, eax
0x18002fb3f  test    eax, eax
0x18002fb41  jns     short loc_18002FB64
0x18002fb43  mov     rcx, [rsp+138h]; this
0x18002fb4b  mov     r9d, eax; char *
0x18002fb4e  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002fb55  mov     edx, 896h; void *
0x18002fb5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb5f  jmp     loc_1800300F9
0x18002fb64  mov     [rsp+138h+pszSubKey], r15
0x18002fb69  mov     [rsp+138h+var_108], r15
0x18002fb6e  mov     qword ptr [rsp+138h+var_D0], r15
0x18002fb73  mov     [rsp+138h+var_F0], r15
0x18002fb78  lea     rax, [rsp+138h+var_F0]
0x18002fb7d  mov     [rsp+138h+var_110], rax
0x18002fb82  lea     rax, [rsp+138h+var_D0]
0x18002fb87  mov     qword ptr [rsp+138h+var_118], rax; int
0x18002fb8c  lea     r9, [rsp+138h+var_108]
0x18002fb91  xor     r8d, r8d
0x18002fb94  lea     rdx, [rsp+138h+pszSubKey]
0x18002fb99  mov     ecx, [rdi+110h]
0x18002fb9f  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x18002fba4  mov     [rsp+138h+var_E8], r15
0x18002fba9  mov     [rsp+138h+var_E0], r15
0x18002fbae  mov     [rsp+138h+var_D8], r15
0x18002fbb3  lea     rcx, [rsp+138h+var_E8]
0x18002fbb8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002fbbd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002fbc1  mov     [rsp+138h+var_E0], r14
0x18002fbc6  mov     [rsp+138h+var_D8], r14
0x18002fbcb  lea     rdx, [rsp+138h+var_E8]; unsigned __int16 *
0x18002fbd0  lea     rcx, String1; "SystemSettings_Devices_Pen_ButtonCustom"...
0x18002fbd7  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x18002fbdc  mov     ebx, eax
0x18002fbde  test    eax, eax
0x18002fbe0  jns     short loc_18002FC03
0x18002fbe2  mov     rcx, [rsp+138h]; this
0x18002fbea  mov     r9d, eax; char *
0x18002fbed  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002fbf4  mov     edx, 8A0h; void *
0x18002fbf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fbfe  jmp     loc_1800300EF
0x18002fc03  mov     rdx, qword ptr [rsp+138h+var_D0]
0x18002fc08  lea     rcx, [rsp+138h+var_68]
0x18002fc10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002fc15  nop
0x18002fc16  lea     rdx, [rsp+138h+var_68]
0x18002fc1e  lea     rcx, [rsp+138h+var_A8]
0x18002fc26  call    ?GetOemPolicyValue@PenSettings@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; SystemSettings::PenSettings::GetOemPolicyValue(std::wstring const &)
0x18002fc2b  nop
0x18002fc2c  lea     rcx, [rsp+138h+var_68]
0x18002fc34  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fc39  mov     rdx, [rsp+138h+var_F0]
0x18002fc3e  lea     rcx, [rsp+138h+var_88]
0x18002fc46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002fc4b  nop
0x18002fc4c  lea     rdx, [rsp+138h+var_88]
0x18002fc54  lea     rcx, [rsp+138h+var_48]
0x18002fc5c  call    ?GetOemPolicyValue@PenSettings@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; SystemSettings::PenSettings::GetOemPolicyValue(std::wstring const &)
0x18002fc61  nop
0x18002fc62  lea     rcx, [rsp+138h+var_88]
0x18002fc6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fc6f  xorps   xmm0, xmm0
0x18002fc72  movups  [rsp+138h+var_C8], xmm0
0x18002fc77  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002fc7f  movdqu  [rsp+138h+var_B8], xmm1
0x18002fc88  mov     word ptr [rsp+138h+var_C8], r15w
0x18002fc8e  cmp     [rsp+138h+var_98], r15
0x18002fc96  jz      short loc_18002FCDC
0x18002fc98  lea     rcx, [rsp+138h+var_A8]
0x18002fca0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002fca5  mov     rcx, rax; lpString1
0x18002fca8  call    ?IsOemAumidAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(ushort const *)
0x18002fcad  test    al, al
0x18002fcaf  jz      short loc_18002FCDC
0x18002fcb1  lea     rcx, [rsp+138h+var_48]
0x18002fcb9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002fcbe  mov     rcx, rax; this
0x18002fcc1  call    ?IsOemUriAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(ushort const *)
0x18002fcc6  test    al, al
0x18002fcc8  jz      short loc_18002FCDC
0x18002fcca  lea     rdx, [rsp+138h+var_C8]
0x18002fccf  lea     rcx, [rsp+138h+var_A8]
0x18002fcd7  call    ?GetAppDisplayNameByAumid@PenSettings@SystemSettings@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; SystemSettings::PenSettings::GetAppDisplayNameByAumid(std::wstring const &,std::wstring &)
0x18002fcdc  mov     rdx, [rsp+138h+var_E8]; HSTRING
0x18002fce1  mov     rcx, [rsp+138h+var_100]; this
0x18002fce6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fceb  test    al, al
0x18002fced  jz      short loc_18002FD30
0x18002fcef  mov     esi, r15d
0x18002fcf2  cmp     esi, r14d
0x18002fcf5  jz      loc_18003008D
0x18002fcfb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x18002fd02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x18002fd07  test    al, al
0x18002fd09  jz      short loc_18002FD14
0x18002fd0b  call    ?IsDesktop@PenSettings@SystemSettings@@YA_NXZ; SystemSettings::PenSettings::IsDesktop(void)
0x18002fd10  test    al, al
0x18002fd12  jnz     short loc_18002FD26
0x18002fd14  cmp     esi, 5
0x18002fd17  jz      loc_18002FF3F
0x18002fd1d  cmp     esi, 0Bh
0x18002fd20  jz      loc_18002FF3F
0x18002fd26  mov     r14, [rsp+138h+pszSubKey]
0x18002fd2b  jmp     loc_18002FF71
0x18002fd30  lea     rcx, [rsp+138h+var_C8]
0x18002fd35  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002fd3a  mov     rdx, rax; HSTRING
0x18002fd3d  mov     rcx, [rsp+138h+var_100]; this
0x18002fd42  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fd47  test    al, al
0x18002fd49  jz      short loc_18002FD52
0x18002fd4b  mov     esi, 0Ch
0x18002fd50  jmp     short loc_18002FCF2
0x18002fd52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x18002fd59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x18002fd5e  test    al, al
0x18002fd60  jz      loc_18002FE58
0x18002fd66  lea     rdx, [rsp+138h+var_88]
0x18002fd6e  mov     rcx, rdi
0x18002fd71  call    ?GetCustomAppDisplayName@DevicesPenSetActionBase@PenSettings@SystemSettings@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomAppDisplayName(void)
0x18002fd76  nop
0x18002fd77  cmp     [rsp+138h+var_78], r15
0x18002fd7f  jz      short loc_18002FDA8
0x18002fd81  lea     rcx, [rsp+138h+var_88]
0x18002fd89  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002fd8e  mov     rdx, rax; HSTRING
0x18002fd91  mov     rcx, [rsp+138h+var_100]; this
0x18002fd96  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fd9b  test    al, al
0x18002fd9d  jz      short loc_18002FDA8
0x18002fd9f  mov     bl, 1
0x18002fda1  mov     esi, 12h
0x18002fda6  jmp     short loc_18002FDFE
0x18002fda8  mov     esi, r14d
0x18002fdab  mov     bl, r15b
0x18002fdae  lea     rdx, [rsp+138h+var_68]
0x18002fdb6  mov     rcx, rdi
0x18002fdb9  call    ?GetCustomDesktopAppDisplayName@DevicesPenSetActionBase@PenSettings@SystemSettings@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomDesktopAppDisplayName(void)
0x18002fdbe  cmp     [rsp+138h+var_58], r15
0x18002fdc6  jz      short loc_18002FDED
0x18002fdc8  lea     rcx, [rsp+138h+var_68]
0x18002fdd0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002fdd5  mov     rdx, rax; HSTRING
0x18002fdd8  mov     rcx, [rsp+138h+var_100]; this
0x18002fddd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fde2  test    al, al
0x18002fde4  jz      short loc_18002FDED
0x18002fde6  mov     bl, 1
0x18002fde8  mov     esi, 12h
0x18002fded  lea     rcx, [rsp+138h+var_68]
0x18002fdf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fdfa  test    bl, bl
0x18002fdfc  jz      short loc_18002FE43
0x18002fdfe  cmp     dword ptr [rdi+114h], 12h
0x18002fe05  jnz     short loc_18002FE43
0x18002fe07  lea     rcx, [rsp+138h+var_88]
0x18002fe0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fe14  nop
0x18002fe15  lea     rcx, [rsp+138h+var_C8]
0x18002fe1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fe1f  nop
0x18002fe20  lea     rcx, [rsp+138h+var_48]
0x18002fe28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fe2d  nop
0x18002fe2e  lea     rcx, [rsp+138h+var_A8]
0x18002fe36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fe3b  mov     ebx, r15d
0x18002fe3e  jmp     loc_1800300EF
0x18002fe43  lea     rcx, [rsp+138h+var_88]
0x18002fe4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fe50  test    bl, bl
0x18002fe52  jnz     loc_18002FCF2
0x18002fe58  mov     rdx, [rsp+138h+var_108]
0x18002fe5d  mov     rcx, [rsp+138h+var_100]; this
0x18002fe62  call    ??$FindEnumFromStringArray@W4PenClickOverride@@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@PenSettings@SystemSettings@@YA?AW4PenClickOverride@@PEAUHSTRING__@@PEBV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@@Z; SystemSettings::PenSettings::FindEnumFromStringArray<PenClickOverride,SystemSettings::PenSettings::PenActionTypeResourceMapping_>(HSTRING__ *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> const *)
0x18002fe67  mov     esi, eax
0x18002fe69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x18002fe70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x18002fe75  test    al, al
0x18002fe77  jz      loc_18002FF31
0x18002fe7d  cmp     esi, 2
0x18002fe80  jnz     short loc_18002FEEA
0x18002fe82  mov     word ptr [rdi+119h], 1
0x18002fe8b  mov     rcx, rdi; this
0x18002fe8e  call    ?SetAppsList@DevicesPenSetActionBase@PenSettings@SystemSettings@@QEAAXXZ; SystemSettings::PenSettings::DevicesPenSetActionBase::SetAppsList(void)
0x18002fe93  lea     rdx, stru_18006A460; unsigned __int16 *
0x18002fe9a  mov     rcx, rdi; this
0x18002fe9d  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18002fea2  lea     rdx, stru_18006A4F8; unsigned __int16 *
0x18002fea9  mov     rcx, rdi; this
0x18002feac  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18002feb1  nop
0x18002feb2  lea     rcx, [rsp+138h+var_C8]
0x18002feb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002febc  nop
0x18002febd  lea     rcx, [rsp+138h+var_48]
0x18002fec5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002feca  nop
0x18002fecb  lea     rcx, [rsp+138h+var_A8]
0x18002fed3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fed8  nop
0x18002fed9  lea     rcx, [rsp+138h+var_E8]
0x18002fede  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002fee3  xor     eax, eax
0x18002fee5  jmp     loc_1800300FB
0x18002feea  cmp     esi, 3
0x18002feed  jnz     short loc_18002FF31
0x18002feef  mov     rcx, rdi; this
0x18002fef2  call    ?LaunchDesktopAppPicker@DevicesPenSetActionBase@PenSettings@SystemSettings@@AEAAJXZ; SystemSettings::PenSettings::DevicesPenSetActionBase::LaunchDesktopAppPicker(void)
0x18002fef7  mov     ebx, eax
0x18002fef9  lea     rcx, [rsp+138h+var_C8]
0x18002fefe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ff03  nop
0x18002ff04  lea     rcx, [rsp+138h+var_48]
0x18002ff0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ff11  nop
0x18002ff12  lea     rcx, [rsp+138h+var_A8]
0x18002ff1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ff1f  nop
0x18002ff20  lea     rcx, [rsp+138h+var_E8]
0x18002ff25  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002ff2a  mov     eax, ebx
0x18002ff2c  jmp     loc_1800300FB
0x18002ff31  jmp     loc_18002FCF2
0x18002ff36  mov     ebx, dword ptr [rsp+138h+pszSubKey]
0x18002ff3a  jmp     loc_1800300C8
0x18002ff3f  mov     ebx, r15d
0x18002ff42  cmp     esi, 5
0x18002ff45  setnz   bl
0x18002ff48  mov     r9d, ebx; unsigned int
0x18002ff4b  lea     r8, aPenworkspaceve; "PenWorkspaceVerb"
0x18002ff52  mov     r14, [rsp+138h+pszSubKey]
0x18002ff57  mov     rdx, r14; unsigned __int16 *
0x18002ff5a  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002ff5f  mov     edx, ebx
0x18002ff61  mov     ecx, [rdi+110h]
0x18002ff67  call    ?UpdateActionValueCachePenWorkspace@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@K@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(PenClickType,ulong)
0x18002ff6c  mov     esi, 5
0x18002ff71  mov     [rdi+114h], esi
0x18002ff77  mov     r9d, esi; unsigned int
0x18002ff7a  lea     r8, aOverride; "Override"
0x18002ff81  mov     rdx, r14; unsigned __int16 *
0x18002ff84  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002ff89  mov     edx, [rdi+114h]
0x18002ff8f  mov     ecx, [rdi+110h]
0x18002ff95  call    ?UpdateActionCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@K@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(PenClickType,ulong)
0x18002ff9a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x18002ffa1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x18002ffa6  test    al, al
0x18002ffa8  jnz     short loc_18003000E
0x18002ffaa  cmp     dword ptr [rdi+114h], 2
0x18002ffb1  jz      short loc_18002FFDC
0x18002ffb3  lea     r8, pszValue; "CustomAppId"
0x18002ffba  mov     rdx, r14; pszSubKey
0x18002ffbd  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18002ffc4  call    cs:__imp_SHDeleteValueW
0x18002ffca  lea     rdx, word_1800679F0
0x18002ffd1  mov     ecx, [rdi+110h]
0x18002ffd7  call    ?UpdateActionValueCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@PEBG@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(PenClickType,ushort const *)
0x18002ffdc  cmp     dword ptr [rdi+114h], 3
0x18002ffe3  jz      short loc_18003000E
0x18002ffe5  lea     r8, aCustomapppath; "CustomAppPath"
0x18002ffec  mov     rdx, r14; pszSubKey
0x18002ffef  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18002fff6  call    cs:__imp_SHDeleteValueW
0x18002fffc  lea     rdx, word_1800679F0
0x180030003  mov     ecx, [rdi+110h]
0x180030009  call    ?UpdateActionValueCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@PEBG@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(PenClickType,ushort const *)
0x18003000e  mov     eax, [rdi+110h]
0x180030014  cmp     eax, 1
0x180030017  jnz     short loc_18003002D
0x180030019  lea     rcx, [rdi+138h]; this
0x180030020  mov     edx, [rdi+114h]; unsigned int
0x180030026  call    ?SaveSingleClickShortcutAsync@CloudDataPenSettings@@QEAAXI@Z; CloudDataPenSettings::SaveSingleClickShortcutAsync(uint)
0x18003002b  jmp     short loc_18003005D
0x18003002d  cmp     eax, 2
0x180030030  jnz     short loc_180030046
0x180030032  lea     rcx, [rdi+138h]; this
0x180030039  mov     edx, [rdi+114h]; unsigned int
0x18003003f  call    ?SaveDoubleClickShortcutAsync@CloudDataPenSettings@@QEAAXI@Z; CloudDataPenSettings::SaveDoubleClickShortcutAsync(uint)
0x180030044  jmp     short loc_18003005D
  ... truncated ...
```

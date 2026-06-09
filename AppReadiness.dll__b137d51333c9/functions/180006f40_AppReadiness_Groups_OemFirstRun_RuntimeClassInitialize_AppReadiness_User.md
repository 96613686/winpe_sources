# AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize(AppReadiness::User *)

- ea: `0x180006f40`
- end: `0x1800077bb`
- name: `?RuntimeClassInitialize@OemFirstRun@Groups@AppReadiness@@QEAAJPEAVUser@3@@Z`
- size: `2171`
- prototype: `__int64 __fastcall(AppReadiness::Groups::OemFirstRun *__hidden this, struct AppReadiness::User *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006ce0`

## callees

- `0x180002958`
- `0x180002a48`
- `0x18000426c`
- `0x180006630`
- `0x180006b54`
- `0x180006da0`
- `0x180006f40`
- `0x18000780c`
- `0x1800078b4`
- `0x18000a470`
- `0x18000b1b0`
- `0x18000bb50`
- `0x18000c000`
- `0x18000e4a0`
- `0x18001f8b4`
- `0x180020680`
- `0x180021858`
- `0x180026954`
- `0x180027a4c`
- `0x180028814`
- `0x180028cd8`
- `0x180029a38`
- `0x18002b63c`
- `0x18002c38c`
- `0x18003235c`
- `0x180036a04`
- `0x180038b90`
- `0x18003935c`
- `0x18003e210`
- `0x18003ecb4`
- `0x18006073c`
- `0x180061610`
- `0x180065120`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000726b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007651`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007664`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000726b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007651`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007664`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007681`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000723f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000723f`

## string_xrefs

- `0x180007289`: `ActivatableClsid`
- `0x180007007`: `AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize`
- `0x1800070fc`: `AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize`
- `0x1800076c0`: `AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize`
- `0x1800076fc`: `AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize`
- `0x18000700e`: `__super::RuntimeClassInitialize(user, APPREADINESS_TASK_OEM_FIRST_RUN, LogonOptimizationPermitted(LogonOptimizationFlags::DisableAppInstallsOnFirstLogon) ? TaskPriority::Low : TaskPriority::High)`
- `0x180006ffb`: `onecoreuap\shell\appreadiness\src\groups\oemfirstrun.cpp`
- `0x1800070f0`: `onecoreuap\shell\appreadiness\src\groups\oemfirstrun.cpp`
- `0x1800076b4`: `onecoreuap\shell\appreadiness\src\groups\oemfirstrun.cpp`
- `0x1800076f0`: `onecoreuap\shell\appreadiness\src\groups\oemfirstrun.cpp`
- `0x1800076c7`: `MakeAndInitialize<Tasks::ActivateApps>(&task, GetUser(), acid.Get(), packageInfo)`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize(
        AppReadiness::Groups::OemFirstRun *this,
        struct AppReadiness::User *a2)
{
  int v2; // edi
  unsigned __int16 *v4; // rsi
  int v5; // ebx
  int v6; // ebx
  char *v7; // r14
  AppReadiness::User *v8; // rax
  int v9; // edx
  __int64 v10; // r8
  unsigned int v11; // r12d
  __m128i si128; // xmm6
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rbx
  unsigned __int16 *v17; // rdi
  int v18; // ebx
  unsigned __int16 **v19; // r8
  unsigned __int16 *v20; // rbx
  __int64 v21; // r8
  __int64 v22; // rax
  int v23; // eax
  __int128 *p_pExceptionObject; // rbx
  __int64 v25; // rax
  _QWORD *v26; // r9
  int v27; // edx
  LPVOID v28; // rdi
  __int128 *v29; // rbx
  __int64 v30; // rbx
  __int128 *v31; // rsi
  __int64 v32; // rax
  _QWORD *v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v37; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B8h]
  __int64 v41; // [rsp+58h] [rbp-B0h]
  __int64 v42; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-98h] BYREF
  __int128 v45; // [rsp+78h] [rbp-90h] BYREF
  __int64 v46; // [rsp+88h] [rbp-80h]
  __int64 v47; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v48; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v49; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-60h]
  __int64 v51; // [rsp+B0h] [rbp-58h]
  unsigned __int16 *v52; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-48h]
  __int64 v54; // [rsp+C8h] [rbp-40h]
  __int128 v55; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v56; // [rsp+E8h] [rbp-20h] BYREF
  LPVOID v57; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v58; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v59[2]; // [rsp+100h] [rbp-8h] BYREF
  __int128 pExceptionObject; // [rsp+110h] [rbp+8h] BYREF
  __m128i v61; // [rsp+120h] [rbp+18h]
  PROPVARIANT pvar[6]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v63[32]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v64[32]; // [rsp+188h] [rbp+80h] BYREF

  v2 = (int)a2;
  v4 = 0;
  v5 = 2 * ((unsigned __int8)LogonOptimizationPermitted() ^ 1) + 2;
  pExceptionObject = 0;
  v61 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject);
  v55 = 0;
  v6 = AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize(
         (_DWORD)this,
         v2,
         (unsigned int)&pExceptionObject,
         (unsigned int)&v55,
         v5);
  if ( v61.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>((void *)pExceptionObject, 2 * v61.m128i_i64[1] + 2);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v6,
      "__super::RuntimeClassInitialize(user, APPREADINESS_TASK_OEM_FIRST_RUN, LogonOptimizationPermitted(LogonOptimizatio"
      "nFlags::DisableAppInstallsOnFirstLogon) ? TaskPriority::Low : TaskPriority::High)",
      "AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize",
      "onecoreuap\\shell\\appreadiness\\src\\groups\\oemfirstrun.cpp",
      27);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v7 = (char *)this + 8;
  v8 = (AppReadiness::User *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 112LL))((char *)this + 8);
  if ( AppReadiness::User::CheckBlockLogonForCriticalAppsOnlyPolicy(v8) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 112LL))((char *)this + 8);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_705c8620f7e334c3a51a94a1f9219017_Traceguids);
    }
    return 0;
  }
  AppReadiness::ImmersivePolicy::ImmersivePolicy((AppReadiness::ImmersivePolicy *)v59);
  AppReadiness::ImmersivePolicy::GetAllDefaultApps(v59, &v44);
  LODWORD(v38) = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 24LL))(v44, &v38);
  if ( v9 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v9,
      "apps->GetCount(&numApps)",
      "AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize",
      "onecoreuap\\shell\\appreadiness\\src\\groups\\oemfirstrun.cpp",
      41);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>(&v45);
  v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v11 < (unsigned int)v38 )
  {
    v37 = 0;
    v13 = v44;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v44 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    v15 = v14(v13, v11, &GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &v37);
    if ( v15 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pvar,
        v15,
        "apps->GetAt(appIndex, IID_PPV_ARGS(&app))",
        "AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize",
        "onecoreuap\\shell\\appreadiness\\src\\groups\\oemfirstrun.cpp",
        46);
      throw (Windows::HResultException *)pvar;
    }
    v49 = 0;
    v50 = 0;
    v51 = 0;
    pv = 0;
    v40 = 0;
    v41 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v16 = v37;
    v43 = v37;
    if ( v37 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 8LL))(v37, (unsigned int)v15);
    v50 = -1;
    v51 = -1;
    v17 = 0;
    v49 = 0;
    LOWORD(pvar[0]) = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v16 + 24LL))(
            v16,
            L"AppId",
            pvar);
    if ( v18 < 0 || LOWORD(pvar[0]) )
    {
      if ( v18 >= 0 )
      {
        if ( !wil::PropVariant::TryDetachString((wil::PropVariant *)pvar, &v49) )
          v18 = -2147352571;
        v17 = v49;
      }
    }
    else
    {
      v18 = -2147023728;
    }
    PropVariantClear(pvar);
    if ( v18 < 0 || !v17 || !*v17 )
      goto LABEL_72;
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v40 = -1;
    v41 = -1;
    if ( (int)wil::PropertyStoreHelperBase<INamedPropertyStore>::GetString<unsigned short const *>(
                &v43,
                L"ActivatableClsid",
                &pv) < 0
      || !pv
      || !*(_WORD *)pv )
    {
      goto LABEL_72;
    }
    v53 = -1;
    v54 = -1;
    v4 = 0;
    if ( (int)ParseAppUserModelId(v17, &v52, v19) < 0 )
    {
      v4 = v52;
LABEL_72:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      if ( v4 )
        CoTaskMemFree(v4);
      v4 = 0;
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v40 = 0;
      v41 = 0;
      if ( v17 )
        CoTaskMemFree(v17);
      goto LABEL_78;
    }
    v20 = v52;
    pExceptionObject = 0;
    v61 = 0;
    v21 = -1;
    do
      ++v21;
    while ( v52[v21] );
    std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject);
    v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 112LL))((char *)this + 8);
    AppReadiness::User::FindPackageInfo(v22, &v47, &pExceptionObject);
    if ( v47 )
    {
      v23 = *(_DWORD *)(v47 + 140);
      if ( (v23 & 2) != 0 )
      {
        if ( (v23 & 0x200) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            p_pExceptionObject = &pExceptionObject;
            if ( v61.m128i_i64[1] > 7uLL )
              p_pExceptionObject = (__int128 *)pExceptionObject;
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 112LL))((char *)this + 8);
            v26 = (_QWORD *)(v25 + 64);
            if ( *(_QWORD *)(v25 + 88) > 7u )
              v26 = (_QWORD *)*v26;
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              (unsigned int)WPP_705c8620f7e334c3a51a94a1f9219017_Traceguids,
              (_DWORD)v26,
              (__int64)p_pExceptionObject);
          }
        }
        else
        {
          *(_QWORD *)&v55 = &pExceptionObject;
          *((_QWORD *)&v55 + 1) = &pv;
          std::find_if_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____________lambda_a24606b8e41ba75914860b625caa12b9___(
            &v56,
            v45,
            *((_QWORD *)&v45 + 1),
            &v55);
          if ( v56 == *((_QWORD *)&v45 + 1) )
          {
            v42 = 0;
            v57 = pv;
            v58 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 112LL))((char *)this + 8);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
            v27 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::ActivateApps,AppReadiness::ITask,AppReadiness::User *,unsigned short const *,std::shared_ptr<AppReadiness::PackageInfo> &>(
                    &v42,
                    &v58,
                    &v57,
                    (__int64)&v47);
            if ( v27 < 0 )
            {
              Windows::HResultException::HResultException(
                (Windows::HResultException *)pvar,
                v27,
                "MakeAndInitialize<Tasks::ActivateApps>(&task, GetUser(), acid.Get(), packageInfo)",
                "AppReadiness::Groups::OemFirstRun::RuntimeClassInitialize",
                "onecoreuap\\shell\\appreadiness\\src\\groups\\oemfirstrun.cpp",
                87);
              throw (Windows::HResultException *)pvar;
            }
            (*(void (__fastcall **)(AppReadiness::Groups::OemFirstRun *, __int64))(*(_QWORD *)this + 24LL))(this, v42);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v28 = pv;
              v29 = &pExceptionObject;
              if ( v61.m128i_i64[1] > 7uLL )
                v29 = (__int128 *)pExceptionObject;
              (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 112LL))((char *)this + 8);
              WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v29, (__int64)v28);
            }
            v30 = std::wstring::wstring((__int64)pvar, (__int64)pv);
            std::wstring::wstring(v63, &pExceptionObject);
            std::wstring::wstring((__int64)v64, v30);
            std::vector<std::pair<std::wstring,std::wstring>>::push_back(&v45, v63);
            std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v63);
            std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(pvar);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
          }
        }
        if ( v48 )
          std::_Ref_count_base::_Decref(v48);
        std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(&pExceptionObject);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v43);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        goto LABEL_80;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v31 = &pExceptionObject;
      if ( v61.m128i_i64[1] > 7uLL )
        v31 = (__int128 *)pExceptionObject;
      v32 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 112LL))((char *)this + 8);
      v33 = (_QWORD *)(v32 + 64);
      if ( *(_QWORD *)(v32 + 88) > 7u )
        v33 = (_QWORD *)*v33;
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_705c8620f7e334c3a51a94a1f9219017_Traceguids,
        (_DWORD)v33,
        (__int64)v31);
      v4 = 0;
    }
    if ( v48 )
      std::_Ref_count_base::_Decref(v48);
    if ( v61.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)pExceptionObject, 2 * v61.m128i_i64[1] + 2);
    v61 = si128;
    LOWORD(pExceptionObject) = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    if ( v20 )
      CoTaskMemFree(v20);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v40 = 0;
    v41 = 0;
    CoTaskMemFree(v17);
LABEL_78:
    v34 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
LABEL_80:
    ++v11;
  }
  if ( (_QWORD)v45 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::wstring,std::wstring>>>(v45, *((_QWORD *)&v45 + 1), v10);
    std::_Deallocate<16>((void *)v45, (v46 - v45) & 0xFFFFFFFFFFFFFFC0uLL);
    v45 = 0;
    v46 = 0;
  }
  v35 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v59[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(v59);
  return 0;
}

```

## disassembly

```asm
0x180006f40  mov     rax, rsp
0x180006f43  mov     [rax+18h], rbx
0x180006f47  push    rbp
0x180006f48  push    rsi
0x180006f49  push    rdi
0x180006f4a  push    r12
0x180006f4c  push    r13
0x180006f4e  push    r14
0x180006f50  push    r15
0x180006f52  lea     rbp, [rax-0F8h]
0x180006f59  sub     rsp, 1C0h
0x180006f60  movaps  xmmword ptr [rax-48h], xmm6
0x180006f64  mov     rax, cs:__security_cookie
0x180006f6b  xor     rax, rsp
0x180006f6e  mov     [rbp+0F0h+var_50], rax
0x180006f75  mov     rdi, rdx
0x180006f78  mov     r13, rcx
0x180006f7b  xor     esi, esi
0x180006f7d  call    ?LogonOptimizationPermitted@@YA_NW4LogonOptimizationFlags@@_N@Z; LogonOptimizationPermitted(LogonOptimizationFlags,bool)
0x180006f82  movzx   eax, al
0x180006f85  xor     eax, 1
0x180006f88  lea     ebx, ds:2[rax*2]
0x180006f8f  xorps   xmm0, xmm0
0x180006f92  movups  [rbp+0F0h+pExceptionObject], xmm0
0x180006f96  xorps   xmm1, xmm1
0x180006f99  movdqu  [rbp+0F0h+var_D8], xmm1
0x180006f9e  lea     r8d, [rsi+0Fh]
0x180006fa2  lea     rdx, aArtOemfirstrun; "ART:OemFirstRun"
0x180006fa9  lea     rcx, [rbp+0F0h+pExceptionObject]
0x180006fad  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180006fb2  nop
0x180006fb3  xorps   xmm0, xmm0
0x180006fb6  movdqu  [rbp+0F0h+var_120], xmm0
0x180006fbb  mov     dword ptr [rsp+1F0h+var_1D0], ebx
0x180006fbf  lea     r9, [rbp+0F0h+var_120]
0x180006fc3  lea     r8, [rbp+0F0h+pExceptionObject]
0x180006fc7  mov     rdx, rdi
0x180006fca  mov     rcx, r13
0x180006fcd  call    ?RuntimeClassInitialize@BaseTaskGroup@Impl@AppReadiness@@IEAAJPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$weak_ptr@VPackageInfo@AppReadiness@@@6@W4TaskPriority@3@@Z; AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize(AppReadiness::User *,std::wstring const &,std::weak_ptr<AppReadiness::PackageInfo> const &,AppReadiness::TaskPriority)
0x180006fd2  mov     ebx, eax
0x180006fd4  mov     rdx, qword ptr [rbp+0F0h+var_D8+8]
0x180006fd8  cmp     rdx, 7
0x180006fdc  jbe     short loc_180006FEF
0x180006fde  lea     rdx, ds:2[rdx*2]
0x180006fe6  mov     rcx, qword ptr [rbp+0F0h+pExceptionObject]
0x180006fea  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006fef  test    ebx, ebx
0x180006ff1  jns     short loc_180007031
0x180006ff3  mov     dword ptr [rsp+1F0h+var_1C8], 1Bh; int
0x180006ffb  lea     rax, aOnecoreuapShel_16; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180007002  mov     [rsp+1F0h+var_1D0], rax; char *
0x180007007  lea     r9, aAppreadinessGr_7; "AppReadiness::Groups::OemFirstRun::Runt"...
0x18000700e  lea     r8, aSuperRuntimecl; "__super::RuntimeClassInitialize(user, A"...
0x180007015  mov     edx, ebx; int
0x180007017  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18000701b  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180007020  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180007027  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18000702b  call    _CxxThrowException_0
0x180007031  lea     r14, [r13+8]
0x180007035  mov     rax, [r14]
0x180007038  mov     rcx, r14
0x18000703b  mov     rax, [rax+70h]
0x18000703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007044  mov     rcx, rax; this
0x180007047  call    ?CheckBlockLogonForCriticalAppsOnlyPolicy@User@AppReadiness@@IEAA_NXZ; AppReadiness::User::CheckBlockLogonForCriticalAppsOnlyPolicy(void)
0x18000704c  test    al, al
0x18000704e  jz      short loc_1800070AF
0x180007050  lea     r15, WPP_GLOBAL_Control
0x180007057  mov     rax, cs:WPP_GLOBAL_Control
0x18000705e  cmp     rax, r15
0x180007061  jz      loc_18000778A
0x180007067  test    byte ptr [rax+1Ch], 4
0x18000706b  jz      loc_18000778A
0x180007071  mov     rax, [r14]
0x180007074  mov     rcx, r14
0x180007077  mov     rax, [rax+70h]
0x18000707b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007080  lea     r9, [rax+40h]
0x180007084  cmp     qword ptr [r9+18h], 7
0x180007089  jbe     short loc_18000708E
0x18000708b  mov     r9, [r9]
0x18000708e  mov     edx, 0Ah
0x180007093  lea     r8, WPP_705c8620f7e334c3a51a94a1f9219017_Traceguids
0x18000709a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070a1  mov     rcx, [rcx+10h]
0x1800070a5  call    WPP_SF_S
0x1800070aa  jmp     loc_18000778A
0x1800070af  lea     rcx, [rbp+0F0h+var_F8]; this
0x1800070b3  call    ??0ImmersivePolicy@AppReadiness@@QEAA@XZ; AppReadiness::ImmersivePolicy::ImmersivePolicy(void)
0x1800070b8  nop
0x1800070b9  lea     rdx, [rsp+1F0h+var_188]
0x1800070be  lea     rcx, [rbp+0F0h+var_F8]
0x1800070c2  call    ?GetAllDefaultApps@ImmersivePolicy@AppReadiness@@QEAA?AV?$ComPtr@UIObjectCollection@@@WRL@Microsoft@@XZ; AppReadiness::ImmersivePolicy::GetAllDefaultApps(void)
0x1800070c7  nop
0x1800070c8  mov     dword ptr [rsp+1F0h+var_1B8], esi
0x1800070cc  mov     rcx, qword ptr [rsp+1F0h+var_188]
0x1800070d1  mov     rax, [rcx]
0x1800070d4  lea     rdx, [rsp+1F0h+var_1B8]
0x1800070d9  mov     rax, [rax+18h]
0x1800070dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070e2  mov     edx, eax; int
0x1800070e4  test    eax, eax
0x1800070e6  jns     short loc_180007124
0x1800070e8  mov     dword ptr [rsp+1F0h+var_1C8], 29h ; ')'; int
0x1800070f0  lea     rax, aOnecoreuapShel_16; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800070f7  mov     [rsp+1F0h+var_1D0], rax; char *
0x1800070fc  lea     r9, aAppreadinessGr_7; "AppReadiness::Groups::OemFirstRun::Runt"...
0x180007103  lea     r8, aAppsGetcountNu; "apps->GetCount(&numApps)"
0x18000710a  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18000710e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180007113  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18000711a  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18000711e  call    _CxxThrowException_0
0x180007124  lea     rcx, [rsp+1F0h+var_188+8]
0x180007129  call    ??0?$vector@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@V?$allocator@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>(void)
0x18000712e  nop
0x18000712f  mov     r12d, esi
0x180007132  lea     r15, WPP_GLOBAL_Control
0x180007139  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180007141  cmp     r12d, dword ptr [rsp+1F0h+var_1B8]
0x180007146  jnb     loc_180007724
0x18000714c  mov     [rsp+1F0h+var_1C0], rsi
0x180007151  mov     rdi, qword ptr [rsp+1F0h+var_188]
0x180007156  mov     rax, [rdi]
0x180007159  mov     rbx, [rax+20h]
0x18000715d  lea     rcx, [rsp+1F0h+var_1C0]
0x180007162  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007167  lea     r9, [rsp+1F0h+var_1C0]
0x18000716c  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180007173  mov     edx, r12d
0x180007176  mov     rcx, rdi
0x180007179  mov     rax, rbx
0x18000717c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007181  mov     edx, eax; int
0x180007183  test    eax, eax
0x180007185  js      loc_1800076E8
0x18000718b  mov     [rbp+0F0h+var_158], rsi
0x18000718f  mov     [rbp+0F0h+var_150], rsi
0x180007193  mov     [rbp+0F0h+var_148], rsi
0x180007197  mov     [rsp+1F0h+pv], rsi
0x18000719c  mov     [rsp+1F0h+var_1A8], rsi
0x1800071a1  mov     [rsp+1F0h+var_1A0], rsi
0x1800071a6  mov     [rbp+0F0h+var_140], rsi
0x1800071aa  xor     eax, eax
0x1800071ac  mov     [rbp+0F0h+var_138], rax
0x1800071b0  mov     [rbp+0F0h+var_130], rax
0x1800071b4  mov     rbx, [rsp+1F0h+var_1C0]
0x1800071b9  mov     [rsp+1F0h+var_190], rbx
0x1800071be  test    rbx, rbx
0x1800071c1  jz      short loc_1800071D4
0x1800071c3  mov     rax, [rbx]
0x1800071c6  mov     rcx, rbx
0x1800071c9  mov     rax, [rax+8]
0x1800071cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d2  xor     eax, eax
0x1800071d4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800071d8  mov     [rbp+0F0h+var_150], rcx
0x1800071dc  mov     [rbp+0F0h+var_148], rcx
0x1800071e0  mov     rdi, rax
0x1800071e3  mov     [rbp+0F0h+var_158], rax
0x1800071e7  mov     word ptr [rbp+0F0h+pvar], ax
0x1800071eb  mov     rax, [rbx]
0x1800071ee  lea     r8, [rbp+0F0h+pvar]
0x1800071f2  lea     rdx, aAppid; "AppId"
0x1800071f9  mov     rcx, rbx
0x1800071fc  mov     rax, [rax+18h]
0x180007200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007205  mov     ebx, eax
0x180007207  xor     r9d, r9d
0x18000720a  test    eax, eax
0x18000720c  js      short loc_18000721C
0x18000720e  cmp     word ptr [rbp+0F0h+pvar], r9w
0x180007213  jnz     short loc_18000721C
0x180007215  mov     ebx, 80070490h
0x18000721a  jmp     short loc_18000723B
0x18000721c  test    ebx, ebx
0x18000721e  js      short loc_18000723B
0x180007220  lea     rdx, [rbp+0F0h+var_158]; unsigned __int16 **
0x180007224  lea     rcx, [rbp+0F0h+pvar]; this
0x180007228  call    ?TryDetachString@PropVariant@wil@@QEAA_NPEAPEAG@Z; wil::PropVariant::TryDetachString(ushort * *)
0x18000722d  mov     ecx, 80020005h
0x180007232  test    al, al
0x180007234  cmovz   ebx, ecx
0x180007237  mov     rdi, [rbp+0F0h+var_158]
0x18000723b  lea     rcx, [rbp+0F0h+pvar]; pvar
0x18000723f  call    cs:__imp_PropVariantClear
0x180007245  test    ebx, ebx
0x180007247  js      loc_18000763E
0x18000724d  xor     ebx, ebx
0x18000724f  test    rdi, rdi
0x180007252  jz      loc_18000763E
0x180007258  cmp     [rdi], bx
0x18000725b  jz      loc_18000763E
0x180007261  mov     rcx, [rsp+1F0h+pv]; pv
0x180007266  test    rcx, rcx
0x180007269  jz      short loc_180007276
0x18000726b  call    cs:__imp_CoTaskMemFree
0x180007271  mov     [rsp+1F0h+pv], rbx
0x180007276  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000727a  mov     [rsp+1F0h+var_1A8], rax
0x18000727f  mov     [rsp+1F0h+var_1A0], rax
0x180007284  lea     r8, [rsp+1F0h+pv]
0x180007289  lea     rdx, aActivatablecls; "ActivatableClsid"
0x180007290  lea     rcx, [rsp+1F0h+var_190]
0x180007295  call    ??$GetString@PEBG@?$PropertyStoreHelperBase@UINamedPropertyStore@@@wil@@QEBAJPEBGPEAPEAG@Z; wil::PropertyStoreHelperBase<INamedPropertyStore>::GetString<ushort const *>(ushort const *,ushort * *)
0x18000729a  test    eax, eax
0x18000729c  js      loc_18000763E
0x1800072a2  mov     rax, [rsp+1F0h+pv]
0x1800072a7  test    rax, rax
0x1800072aa  jz      loc_18000763E
0x1800072b0  cmp     [rax], bx
0x1800072b3  jz      loc_18000763E
0x1800072b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800072bd  mov     [rbp+0F0h+var_138], rax
0x1800072c1  mov     [rbp+0F0h+var_130], rax
0x1800072c5  lea     rdx, [rbp+0F0h+var_140]; unsigned __int16 **
0x1800072c9  mov     rcx, rdi; unsigned __int16 *
0x1800072cc  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x1800072d1  xor     esi, esi
0x1800072d3  test    eax, eax
0x1800072d5  js      loc_18000763A
0x1800072db  mov     rbx, [rbp+0F0h+var_140]
0x1800072df  xorps   xmm0, xmm0
0x1800072e2  movups  [rbp+0F0h+pExceptionObject], xmm0
0x1800072e6  xorps   xmm1, xmm1
0x1800072e9  movdqu  [rbp+0F0h+var_D8], xmm1
0x1800072ee  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800072f2  inc     r8
0x1800072f5  cmp     [rbx+r8*2], si
0x1800072fa  jnz     short loc_1800072F2
0x1800072fc  mov     rdx, rbx
0x1800072ff  lea     rcx, [rbp+0F0h+pExceptionObject]
0x180007303  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007308  nop
0x180007309  mov     rax, [r14]
0x18000730c  mov     rcx, r14
0x18000730f  mov     rax, [rax+70h]
0x180007313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007318  lea     r8, [rbp+0F0h+pExceptionObject]
0x18000731c  lea     rdx, [rbp+0F0h+var_168]
0x180007320  mov     rcx, rax
0x180007323  call    ?FindPackageInfo@User@AppReadiness@@QEAA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; AppReadiness::User::FindPackageInfo(std::wstring const &)
0x180007328  nop
0x180007329  mov     rax, [rbp+0F0h+var_168]
0x18000732d  test    rax, rax
0x180007330  jz      loc_180007562
0x180007336  mov     eax, [rax+8Ch]
0x18000733c  test    al, 2
0x18000733e  jz      loc_180007562
0x180007344  bt      eax, 9
0x180007348  jnb     short loc_1800073B5
0x18000734a  mov     rax, cs:WPP_GLOBAL_Control
0x180007351  cmp     rax, r15
0x180007354  jz      loc_180007510
0x18000735a  test    byte ptr [rax+1Ch], 4
0x18000735e  jz      loc_180007510
0x180007364  lea     rbx, [rbp+0F0h+pExceptionObject]
0x180007368  cmp     qword ptr [rbp+0F0h+var_D8+8], 7
0x18000736d  cmova   rbx, qword ptr [rbp+0F0h+pExceptionObject]
0x180007372  mov     rax, [r14]
0x180007375  mov     rcx, r14
0x180007378  mov     rax, [rax+70h]
0x18000737c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007381  lea     r9, [rax+40h]
0x180007385  cmp     qword ptr [rax+58h], 7
0x18000738a  jbe     short loc_18000738F
0x18000738c  mov     r9, [r9]
0x18000738f  mov     edx, 0Ch
0x180007394  mov     [rsp+1F0h+var_1D0], rbx
0x180007399  lea     r8, WPP_705c8620f7e334c3a51a94a1f9219017_Traceguids
0x1800073a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073a7  mov     rcx, [rcx+10h]
0x1800073ab  call    WPP_SF_SS
0x1800073b0  jmp     loc_180007510
0x1800073b5  lea     rax, [rbp+0F0h+pExceptionObject]
0x1800073b9  mov     qword ptr [rbp+0F0h+var_120], rax
0x1800073bd  lea     rax, [rsp+1F0h+pv]
0x1800073c2  mov     qword ptr [rbp+0F0h+var_120+8], rax
0x1800073c6  lea     r9, [rbp+0F0h+var_120]
0x1800073ca  mov     r8, [rsp+1F0h+var_178]
0x1800073cf  mov     rdx, qword ptr [rsp+1F0h+var_188+8]
0x1800073d4  lea     rcx, [rbp+0F0h+var_110]
0x1800073d8  call    std__find_if_std___Vector_const_iterator_std___Vector_val_std___Simple_types_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____________lambda_a24606b8e41ba75914860b625caa12b9___
0x1800073dd  mov     rax, [rsp+1F0h+var_178]
0x1800073e2  cmp     [rbp+0F0h+var_110], rax
0x1800073e6  jnz     loc_180007510
0x1800073ec  mov     [rsp+1F0h+var_198], rsi
0x1800073f1  mov     rax, [rsp+1F0h+pv]
0x1800073f6  mov     [rbp+0F0h+var_108], rax
0x1800073fa  mov     rax, [r14]
0x1800073fd  mov     rcx, r14
0x180007400  mov     rax, [rax+70h]
0x180007404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007409  mov     [rbp+0F0h+var_100], rax
0x18000740d  lea     rcx, [rsp+1F0h+var_198]
0x180007412  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007417  lea     r9, [rbp+0F0h+var_168]
0x18000741b  lea     r8, [rbp+0F0h+var_108]
0x18000741f  lea     rdx, [rbp+0F0h+var_100]
  ... truncated ...
```

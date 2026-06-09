# AppReadiness::PackageInfo::HasLockScreenApp(AppReadiness::User *)

- ea: `0x180007b70`
- end: `0x18000840e`
- name: `?HasLockScreenApp@PackageInfo@AppReadiness@@QEAA_NPEAVUser@2@@Z`
- size: `2206`
- prototype: `bool __fastcall(AppReadiness::PackageInfo *__hidden this, struct AppReadiness::User *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007ad0`
- `0x18002db60`

## callees

- `0x180002958`
- `0x1800041e0`
- `0x18000426c`
- `0x18000780c`
- `0x1800078b4`
- `0x180007b70`
- `0x180008420`
- `0x1800097d0`
- `0x180009d60`
- `0x18001f8b4`
- `0x180021858`
- `0x180027a4c`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180007f4b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180007f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081d4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ec0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800081a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ec0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800081a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007c85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000802f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007c85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000802f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008010`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008157`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008157`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007d3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007d3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007fd6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007fd6`
- `PROPSYS!PropVariantToStringAlloc` at `0x180007eb4`
- `PROPSYS!PropVariantToStringAlloc` at `0x180007eb4`
- `PROPSYS!PropVariantToUInt32` at `0x18000822c`
- `PROPSYS!PropVariantToUInt32` at `0x18000822c`

## string_xrefs

- `0x1800082f1`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x18000839a`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x1800082fd`: `AppReadiness::PackageInfo::HasLockScreenApp`
- `0x1800083a6`: `AppReadiness::PackageInfo::HasLockScreenApp`
- `0x1800083d8`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x1800083e4`: `AppReadiness::Storage::PackageMetadata::Set`
- `0x1800083eb`: `SHRegSetDWORD(key.Get(), nullptr, MetadataTypeToValueName(type), value)`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_BOOL8 __fastcall AppReadiness::PackageInfo::HasLockScreenApp(
        AppReadiness::PackageInfo *this,
        struct AppReadiness::User *a2)
{
  bool v4; // r14
  int v5; // eax
  HKEY v6; // rax
  char v7; // bl
  int LastError; // eax
  __int64 v9; // rcx
  struct AppReadiness::User *v10; // rcx
  LSTATUS ValueW; // eax
  bool v13; // sf
  int v14; // eax
  DWORD v15; // esi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, GUID *, void ***); // rbx
  int v18; // eax
  void *v19; // rcx
  void **v20; // rbx
  HRESULT v21; // edi
  void *v22; // rdx
  WCHAR *v23; // rdi
  __int64 v24; // rcx
  __int64 *v25; // r9
  __int64 v26; // r8
  wchar_t *v27; // rax
  wchar_t v28; // r10
  wchar_t *v29; // rcx
  __int64 v30; // rcx
  _WORD *v31; // r10
  __int64 v32; // rdx
  int v33; // eax
  bool v34; // sf
  int v35; // eax
  void **v36; // rcx
  void **v37; // rcx
  const WCHAR *v38; // r8
  HRESULT v39; // ebx
  void **v40; // rcx
  __int64 v41; // rax
  wchar_t *v42; // rcx
  wchar_t v43; // dx
  __int64 v44; // rax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  void **v47; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h]
  __int64 v50; // [rsp+68h] [rbp-98h]
  void **v51; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT propvar[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h]
  struct AppReadiness::User *v56; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v57[2]; // [rsp+A8h] [rbp-58h] BYREF
  LPCWCH lpString1[5]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v59[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v60[18]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t Str[136]; // [rsp+180h] [rbp+80h] BYREF

  v4 = 0;
  v5 = *((_DWORD *)this + 35);
  if ( (v5 & 0x40) != 0 || (v5 & 4) != 0 || (v5 & 2) == 0 )
    return v4;
  if ( a2 )
    (*(void (__fastcall **)(struct AppReadiness::User *))(*(_QWORD *)a2 + 8LL))(a2);
  v56 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct AppReadiness::User *))(*(_QWORD *)a2 + 8LL))(a2);
  v57[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  v57[1] = 0;
  if ( a2 )
    (*(void (__fastcall **)(struct AppReadiness::User *))(*(_QWORD *)a2 + 16LL))(a2);
  *(_DWORD *)Data = 0;
  AppReadiness::Storage::PackageMetadata::CreateMetadataKey((__int64)&v56, &v51, (const WCHAR *)this + 20, 1u);
  v6 = hkey;
  if ( !hkey )
    goto LABEL_11;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"LockScreenApps", 0x10u, 0, Data, &pcbData);
  v13 = ValueW < 0;
  if ( ValueW > 0 )
    v13 = 1;
  v6 = hkey;
  if ( v13 )
LABEL_11:
    v7 = 0;
  else
    v7 = 1;
  v51 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  if ( v6
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v51) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    goto LABEL_17;
  }
  if ( v7 )
  {
    v4 = *(_DWORD *)Data != 0;
    goto LABEL_20;
  }
  AppReadiness::ImmersivePolicy::ImmersivePolicy((AppReadiness::ImmersivePolicy *)v59);
  AppReadiness::ImmersivePolicy::GetAllDefaultApps(v59, &v53);
  pcbData = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v53 + 24LL))(v53, &pcbData);
  if ( v14 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)lpString1,
      v14,
      "apps->GetCount(&numApps)",
      "AppReadiness::PackageInfo::HasLockScreenApp",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
      274);
    throw (Windows::HResultException *)lpString1;
  }
  v15 = 0;
  while ( !v4 && v15 < pcbData )
  {
    v47 = 0;
    v16 = v53;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, void ***))(*(_QWORD *)v53 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v18 = v17(v16, v15, &GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &v47);
    if ( v18 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)lpString1,
        v18,
        "apps->GetAt(appIndex, IID_PPV_ARGS(&app))",
        "AppReadiness::PackageInfo::HasLockScreenApp",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        278);
      throw (Windows::HResultException *)lpString1;
    }
    v19 = 0;
    pv = 0;
    v49 = 0;
    v50 = 0;
    v20 = v47;
    v51 = v47;
    if ( v47 )
    {
      (*((void (__fastcall **)(void **))*v47 + 1))(v47);
      v19 = pv;
    }
    if ( v19 )
      CoTaskMemFree(v19);
    v49 = -1;
    v50 = -1;
    pv = 0;
    LOWORD(propvar[0]) = 0;
    v21 = (*((__int64 (__fastcall **)(void **, const wchar_t *, PROPVARIANT *))*v20 + 3))(v20, L"AppId", propvar);
    if ( v21 >= 0 )
    {
      if ( LOWORD(propvar[0]) )
      {
        if ( LOWORD(propvar[0]) == 31 && propvar[1] )
        {
          pv = propvar[1];
          *(_OWORD *)propvar = 0;
          v55 = 0;
          v21 = 0;
        }
        else
        {
          pv = 0;
          v21 = PropVariantToStringAlloc(propvar, (PWSTR *)&pv);
        }
      }
      else
      {
        v21 = -2147023728;
      }
    }
    PropVariantClear(propvar);
    if ( v21 >= 0 && (v22 = pv) != 0 && *(_WORD *)pv )
    {
      lpString1[1] = (LPCWCH)-1LL;
      lpString1[2] = (LPCWCH)-1LL;
      v23 = 0;
      lpString1[0] = 0;
      LOWORD(v60[0]) = 0;
      v24 = 2147483646;
      v25 = (__int64 *)pv;
      v26 = 130;
      v27 = Str;
      do
      {
        if ( !v24 )
          break;
        v28 = *(_WORD *)v25;
        if ( !*(_WORD *)v25 )
          break;
        v25 = (__int64 *)((char *)v25 + 2);
        *v27++ = v28;
        --v24;
        --v26;
      }
      while ( v26 );
      v29 = v27 - 1;
      if ( v26 )
        v29 = v27;
      *v29 = 0;
      if ( !v26 )
        goto LABEL_75;
      v30 = (__int64)wcsrchr(Str, 0x21u);
      if ( Str[0] != 33 && v30 && (v31 = (_WORD *)(v30 + 2), *(_WORD *)(v30 + 2)) )
      {
        *(_WORD *)v30 = 0;
        v41 = 2147483646;
        v42 = Str;
        v26 = 65;
        v25 = v60;
        do
        {
          if ( !v41 )
            break;
          v43 = *v42;
          if ( !*v42 )
            break;
          ++v42;
          *(_WORD *)v25 = v43;
          v25 = (__int64 *)((char *)v25 + 2);
          --v41;
          --v26;
        }
        while ( v26 );
        v32 = 2147942522LL;
        if ( v26 )
          v32 = 0;
        v30 = (__int64)v25 - 2;
        if ( v26 )
          v30 = (__int64)v25;
        *(_WORD *)v30 = 0;
        if ( v26 )
        {
          v44 = 2147483646;
          v30 = 65;
          do
          {
            if ( !v44 )
              break;
            if ( !*v31 )
              break;
            ++v31;
            --v44;
            --v30;
          }
          while ( v30 );
          v32 = 2147942522LL;
          if ( v30 )
            v32 = 0;
        }
      }
      else
      {
        v32 = 2147942487LL;
      }
      if ( (int)v32 < 0 )
        goto LABEL_74;
      if ( (int)_AllocString<CTCoAllocPolicy>(v30, v32, v60, lpString1) < 0 )
      {
        v23 = (WCHAR *)lpString1[0];
LABEL_74:
        v22 = pv;
LABEL_75:
        if ( v23 )
        {
          CoTaskMemFree(v23);
          v22 = pv;
        }
        if ( v20 )
        {
          (*((void (__fastcall **)(void **, void *, __int64, __int64 *))*v20 + 2))(v20, v22, v26, v25);
          v22 = pv;
        }
        if ( v22 )
        {
          CoTaskMemFree(v22);
          pv = 0;
        }
        v49 = 0;
        v50 = 0;
        v37 = v47;
        if ( v47 )
        {
          v47 = 0;
          (*((void (__fastcall **)(void **, void *, __int64, __int64 *))*v37 + 2))(v37, v22, v26, v25);
        }
        goto LABEL_83;
      }
      if ( *((_QWORD *)this + 8) <= 7u )
        v38 = (const WCHAR *)((char *)this + 40);
      else
        v38 = (const WCHAR *)*((_QWORD *)this + 5);
      v23 = (WCHAR *)lpString1[0];
      if ( CompareStringOrdinal(lpString1[0], -1, v38, -1, 1) != 2 )
        goto LABEL_74;
      *(_DWORD *)Data = 0;
      LOWORD(propvar[0]) = 0;
      v39 = (*((__int64 (__fastcall **)(void **, const wchar_t *, PROPVARIANT *))*v20 + 3))(v20, L"Type", propvar);
      if ( v39 >= 0 )
      {
        if ( LOWORD(propvar[0]) )
        {
          *(_DWORD *)Data = 0;
          v39 = PropVariantToUInt32(propvar, (ULONG *)Data);
        }
        else
        {
          v39 = -2147023728;
        }
      }
      PropVariantClear(propvar);
      if ( v39 >= 0 && *(_DWORD *)Data )
      {
        v4 = 1;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpString1);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v51);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
        goto LABEL_83;
      }
      if ( v23 )
        CoTaskMemFree(v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v49 = 0;
      v50 = 0;
      v40 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*((void (__fastcall **)(void **))*v40 + 2))(v40);
      }
      ++v15;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v49 = 0;
      v50 = 0;
      v36 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*((void (__fastcall **)(void **))*v36 + 2))(v36);
      }
LABEL_83:
      ++v15;
    }
  }
  AppReadiness::Storage::PackageMetadata::CreateMetadataKey((__int64)&v56, &v51, (const WCHAR *)this + 20, 0x20006u);
  *(_DWORD *)Data = v4;
  v33 = RegSetValueExW(hkey, L"LockScreenApps", 0, 4u, Data, 4u);
  v34 = v33 < 0;
  if ( v33 > 0 )
    goto LABEL_62;
  while ( 1 )
  {
    if ( v34 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)lpString1,
        v33,
        "SHRegSetDWORD(key.Get(), nullptr, MetadataTypeToValueName(type), value)",
        "AppReadiness::Storage::PackageMetadata::Set",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
        100);
      throw (Windows::HResultException *)lpString1;
    }
    v51 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
    if ( !hkey
      || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v51) )
    {
      break;
    }
    v35 = GetLastError();
    if ( v35 > 0 )
      v35 = (unsigned __int16)v35 | 0x80070000;
    RaiseException(v35, 1u, 0, 0);
LABEL_62:
    v33 = (unsigned __int16)v33 | 0x80070000;
    v34 = v33 < 0;
  }
LABEL_17:
  v9 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v59[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(v59);
LABEL_20:
  v57[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v57);
  v10 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(struct AppReadiness::User *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return v4;
}

```

## disassembly

```asm
0x180007b70  push    rbp
0x180007b72  push    rbx
0x180007b73  push    rsi
0x180007b74  push    rdi
0x180007b75  push    r12
0x180007b77  push    r13
0x180007b79  push    r14
0x180007b7b  push    r15
0x180007b7d  lea     rbp, [rsp-1A8h]
0x180007b85  sub     rsp, 2A8h
0x180007b8c  mov     rax, cs:__security_cookie
0x180007b93  xor     rax, rsp
0x180007b96  mov     [rbp+1E0h+var_50], rax
0x180007b9d  mov     rbx, rdx
0x180007ba0  mov     r13, rcx
0x180007ba3  xor     r12d, r12d
0x180007ba6  xor     r14b, r14b
0x180007ba9  mov     eax, [rcx+8Ch]
0x180007baf  test    al, 40h
0x180007bb1  jnz     loc_180007CE3
0x180007bb7  test    al, 4
0x180007bb9  jnz     loc_180007CE3
0x180007bbf  test    al, 2
0x180007bc1  jz      loc_180007CE3
0x180007bc7  test    rdx, rdx
0x180007bca  jz      short loc_180007BDC
0x180007bcc  mov     rax, [rdx]
0x180007bcf  mov     rcx, rdx
0x180007bd2  mov     rax, [rax+8]
0x180007bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bdb  nop
0x180007bdc  mov     [rbp+1E0h+var_240], rbx
0x180007be0  test    rbx, rbx
0x180007be3  jz      short loc_180007BF5
0x180007be5  mov     rax, [rbx]
0x180007be8  mov     rcx, rbx
0x180007beb  mov     rax, [rax+8]
0x180007bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf4  nop
0x180007bf5  lea     rdi, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x180007bfc  mov     [rbp+1E0h+var_238], rdi
0x180007c00  mov     [rbp+1E0h+var_230], r12
0x180007c04  test    rbx, rbx
0x180007c07  jz      short loc_180007C19
0x180007c09  mov     rax, [rbx]
0x180007c0c  mov     rcx, rbx
0x180007c0f  mov     rax, [rax+10h]
0x180007c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c18  nop
0x180007c19  mov     dword ptr [rsp+2E0h+Data], r12d
0x180007c1e  mov     r9d, 1
0x180007c24  lea     r8, [r13+28h]
0x180007c28  lea     rdx, [rsp+2E0h+var_270]
0x180007c2d  lea     rcx, [rbp+1E0h+var_240]
0x180007c31  call    ?CreateMetadataKey@PackageMetadata@Storage@AppReadiness@@AEAA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; AppReadiness::Storage::PackageMetadata::CreateMetadataKey(std::wstring const &,ulong)
0x180007c36  mov     rax, [rsp+2E0h+hkey]
0x180007c3b  test    rax, rax
0x180007c3e  jnz     loc_180007D0A
0x180007c44  xor     bl, bl
0x180007c46  mov     [rsp+2E0h+var_270], rdi
0x180007c4b  test    rax, rax
0x180007c4e  jz      loc_180007D65
0x180007c54  lea     rcx, [rsp+2E0h+var_270]
0x180007c59  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x180007c5e  test    al, al
0x180007c60  jnz     loc_180007D65
0x180007c66  call    cs:__imp_GetLastError
0x180007c6c  test    eax, eax
0x180007c6e  jle     short loc_180007C78
0x180007c70  movzx   eax, ax
0x180007c73  or      eax, 80070000h
0x180007c78  xor     r9d, r9d; lpArguments
0x180007c7b  xor     r8d, r8d; nNumberOfArguments
0x180007c7e  mov     edx, 1; dwExceptionFlags
0x180007c83  mov     ecx, eax; dwExceptionCode
0x180007c85  call    cs:__imp_RaiseException
0x180007c8b  nop
0x180007c8c  mov     rcx, [rbp+1E0h+var_260]
0x180007c90  test    rcx, rcx
0x180007c93  jz      short loc_180007CA6
0x180007c95  mov     [rbp+1E0h+var_260], r12
0x180007c99  mov     rax, [rcx]
0x180007c9c  mov     rax, [rax+10h]
0x180007ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ca5  nop
0x180007ca6  lea     rax, ??_7?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable'
0x180007cad  mov     [rbp+1E0h+var_200], rax
0x180007cb1  lea     rcx, [rbp+1E0h+var_200]
0x180007cb5  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180007cba  nop
0x180007cbb  mov     [rbp+1E0h+var_238], rdi
0x180007cbf  lea     rcx, [rbp+1E0h+var_238]
0x180007cc3  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180007cc8  nop
0x180007cc9  mov     rcx, [rbp+1E0h+var_240]
0x180007ccd  test    rcx, rcx
0x180007cd0  jz      short loc_180007CE3
0x180007cd2  mov     [rbp+1E0h+var_240], r12
0x180007cd6  mov     rdx, [rcx]
0x180007cd9  mov     rax, [rdx+10h]
0x180007cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce2  nop
0x180007ce3  movzx   eax, r14b
0x180007ce7  mov     rcx, [rbp+1E0h+var_50]
0x180007cee  xor     rcx, rsp; StackCookie
0x180007cf1  call    __security_check_cookie
0x180007cf6  add     rsp, 2A8h
0x180007cfd  pop     r15
0x180007cff  pop     r14
0x180007d01  pop     r13
0x180007d03  pop     r12
0x180007d05  pop     rdi
0x180007d06  pop     rsi
0x180007d07  pop     rbx
0x180007d08  pop     rbp
0x180007d09  retn
0x180007d0a  mov     [rsp+2E0h+var_298], 4
0x180007d12  lea     rcx, [rsp+2E0h+var_298]
0x180007d17  mov     [rsp+2E0h+pcbData], rcx; pcbData
0x180007d1c  lea     rcx, [rsp+2E0h+Data]
0x180007d21  mov     [rsp+2E0h+pvData], rcx; pvData
0x180007d26  mov     [rsp+2E0h+pdwType], r12; pdwType
0x180007d2b  mov     r9d, 10h; dwFlags
0x180007d31  mov     r8, cs:lpValueName; lpValue
0x180007d38  xor     edx, edx; lpSubKey
0x180007d3a  mov     rcx, rax; hkey
0x180007d3d  call    cs:__imp_RegGetValueW
0x180007d43  test    eax, eax
0x180007d45  jg      short loc_180007D59
0x180007d47  mov     rax, [rsp+2E0h+hkey]
0x180007d4c  js      loc_180007C44
0x180007d52  mov     bl, 1
0x180007d54  jmp     loc_180007C46
0x180007d59  movzx   eax, ax
0x180007d5c  or      eax, 80070000h
0x180007d61  test    eax, eax
0x180007d63  jmp     short loc_180007D47
0x180007d65  test    bl, bl
0x180007d67  jnz     loc_180008042
0x180007d6d  lea     rcx, [rbp+1E0h+var_200]; this
0x180007d71  call    ??0ImmersivePolicy@AppReadiness@@QEAA@XZ; AppReadiness::ImmersivePolicy::ImmersivePolicy(void)
0x180007d76  nop
0x180007d77  lea     rdx, [rbp+1E0h+var_260]
0x180007d7b  lea     rcx, [rbp+1E0h+var_200]
0x180007d7f  call    ?GetAllDefaultApps@ImmersivePolicy@AppReadiness@@QEAA?AV?$ComPtr@UIObjectCollection@@@WRL@Microsoft@@XZ; AppReadiness::ImmersivePolicy::GetAllDefaultApps(void)
0x180007d84  nop
0x180007d85  mov     [rsp+2E0h+var_298], r12d
0x180007d8a  mov     rcx, [rbp+1E0h+var_260]
0x180007d8e  mov     rax, [rcx]
0x180007d91  lea     rdx, [rsp+2E0h+var_298]
0x180007d96  mov     rax, [rax+18h]
0x180007d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9f  test    eax, eax
0x180007da1  js      loc_1800082E9
0x180007da7  mov     esi, r12d
0x180007daa  nop     word ptr [rax+rax+00h]
0x180007db0  test    r14b, r14b
0x180007db3  jnz     loc_180007F89
0x180007db9  cmp     esi, [rsp+2E0h+var_298]
0x180007dbd  jnb     loc_180007F89
0x180007dc3  mov     [rsp+2E0h+var_290], r12
0x180007dc8  mov     rdi, [rbp+1E0h+var_260]
0x180007dcc  mov     rax, [rdi]
0x180007dcf  mov     rbx, [rax+20h]
0x180007dd3  lea     rcx, [rsp+2E0h+var_290]
0x180007dd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007ddd  lea     r9, [rsp+2E0h+var_290]
0x180007de2  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180007de9  mov     edx, esi
0x180007deb  mov     rcx, rdi
0x180007dee  mov     rax, rbx
0x180007df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df6  test    eax, eax
0x180007df8  js      loc_180008392
0x180007dfe  mov     rcx, r12
0x180007e01  mov     [rsp+2E0h+pv], rcx
0x180007e06  mov     [rsp+2E0h+var_280], r12
0x180007e0b  mov     [rsp+2E0h+var_278], r12
0x180007e10  mov     rbx, [rsp+2E0h+var_290]
0x180007e15  mov     [rsp+2E0h+var_270], rbx
0x180007e1a  test    rbx, rbx
0x180007e1d  jz      short loc_180007E33
0x180007e1f  mov     rax, [rbx]
0x180007e22  mov     rcx, rbx
0x180007e25  mov     rax, [rax+8]
0x180007e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e2e  mov     rcx, [rsp+2E0h+pv]; pv
0x180007e33  mov     rdi, rbx
0x180007e36  test    rcx, rcx
0x180007e39  jz      short loc_180007E41
0x180007e3b  call    cs:__imp_CoTaskMemFree
0x180007e41  mov     [rsp+2E0h+var_280], 0FFFFFFFFFFFFFFFFh
0x180007e4a  mov     [rsp+2E0h+var_278], 0FFFFFFFFFFFFFFFFh
0x180007e53  mov     [rsp+2E0h+pv], r12
0x180007e58  mov     word ptr [rbp+1E0h+propvar], r12w
0x180007e5d  mov     rax, [rdi]
0x180007e60  lea     r8, [rbp+1E0h+propvar]
0x180007e64  lea     rdx, aAppid; "AppId"
0x180007e6b  mov     rcx, rdi
0x180007e6e  mov     rax, [rax+18h]
0x180007e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e77  mov     edi, eax
0x180007e79  test    eax, eax
0x180007e7b  js      short loc_180007EBC
0x180007e7d  movzx   ecx, word ptr [rbp+1E0h+propvar]
0x180007e81  test    cx, cx
0x180007e84  jz      loc_180008327
0x180007e8a  cmp     cx, 1Fh
0x180007e8e  jnz     short loc_180007E9D
0x180007e90  mov     rax, [rbp+1E0h+propvar+8]
0x180007e94  test    rax, rax
0x180007e97  jnz     loc_180008331
0x180007e9d  mov     [rsp+2E0h+pv], r12
0x180007ea2  test    cx, cx
0x180007ea5  jz      loc_180007F7F
0x180007eab  lea     rdx, [rsp+2E0h+pv]; ppszOut
0x180007eb0  lea     rcx, [rbp+1E0h+propvar]; propvar
0x180007eb4  call    cs:__imp_PropVariantToStringAlloc
0x180007eba  mov     edi, eax
0x180007ebc  lea     rcx, [rbp+1E0h+propvar]; pvar
0x180007ec0  call    cs:__imp_PropVariantClear
0x180007ec6  test    edi, edi
0x180007ec8  js      loc_180008050
0x180007ece  mov     rdx, [rsp+2E0h+pv]
0x180007ed3  test    rdx, rdx
0x180007ed6  jz      loc_180008050
0x180007edc  cmp     word ptr [rdx], 0
0x180007ee0  jz      loc_180008050
0x180007ee6  mov     [rbp+1E0h+var_220], 0FFFFFFFFFFFFFFFFh
0x180007eee  mov     [rbp+1E0h+var_218], 0FFFFFFFFFFFFFFFFh
0x180007ef6  mov     rdi, r12
0x180007ef9  mov     [rbp+1E0h+lpString1], r12
0x180007efd  mov     word ptr [rbp+1E0h+var_1F0], r12w
0x180007f02  mov     ecx, 7FFFFFFEh
0x180007f07  mov     r9, rdx
0x180007f0a  mov     r8d, 82h
0x180007f10  lea     rax, [rbp+1E0h+Str]
0x180007f17  test    rcx, rcx
0x180007f1a  jz      short loc_180007F2A
0x180007f1c  movzx   r10d, word ptr [r9]
0x180007f20  test    r10w, r10w
0x180007f24  jnz     loc_1800082AD
0x180007f2a  lea     rcx, [rax-2]
0x180007f2e  test    r8, r8
0x180007f31  cmovnz  rcx, rax
0x180007f35  mov     [rcx], r12w
0x180007f39  jz      loc_1800080C5
0x180007f3f  mov     edx, 21h ; '!'; Ch
0x180007f44  lea     rcx, [rbp+1E0h+Str]; Str
0x180007f4b  call    cs:__imp_wcsrchr
0x180007f51  mov     rcx, rax
0x180007f54  mov     eax, 21h ; '!'
0x180007f59  cmp     ax, [rbp+1E0h+Str]
0x180007f60  jz      short loc_180007F75
0x180007f62  test    rcx, rcx
0x180007f65  jz      short loc_180007F75
0x180007f67  lea     r10, [rcx+2]
0x180007f6b  cmp     r12w, [r10]
0x180007f6f  jnz     loc_180008239
0x180007f75  mov     edx, 80070057h
0x180007f7a  jmp     loc_1800080A7
0x180007f7f  mov     edi, 80070490h
0x180007f84  jmp     loc_180007EBC
0x180007f89  mov     ebx, r12d
0x180007f8c  test    r14b, r14b
0x180007f8f  setnz   bl
0x180007f92  mov     r9d, 20006h
0x180007f98  lea     r8, [r13+28h]
0x180007f9c  lea     rdx, [rsp+2E0h+var_270]
0x180007fa1  lea     rcx, [rbp+1E0h+var_240]
0x180007fa5  call    ?CreateMetadataKey@PackageMetadata@Storage@AppReadiness@@AEAA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; AppReadiness::Storage::PackageMetadata::CreateMetadataKey(std::wstring const &,ulong)
0x180007faa  nop
0x180007fab  mov     dword ptr [rsp+2E0h+Data], ebx
0x180007faf  mov     dword ptr [rsp+2E0h+pvData], 4; cbData
0x180007fb7  lea     rax, [rsp+2E0h+Data]
0x180007fbc  mov     [rsp+2E0h+pdwType], rax; lpData
0x180007fc1  mov     r9d, 4; dwType
0x180007fc7  xor     r8d, r8d; Reserved
0x180007fca  mov     rdx, cs:lpValueName; lpValueName
0x180007fd1  mov     rcx, [rsp+2E0h+hkey]; hKey
0x180007fd6  call    cs:__imp_RegSetValueExW
0x180007fdc  test    eax, eax
0x180007fde  jg      short loc_180008036
0x180007fe0  js      loc_1800083D0
0x180007fe6  lea     rdi, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x180007fed  mov     [rsp+2E0h+var_270], rdi
0x180007ff2  cmp     [rsp+2E0h+hkey], 0
0x180007ff8  jz      loc_180007C8C
0x180007ffe  lea     rcx, [rsp+2E0h+var_270]
0x180008003  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x180008008  test    al, al
0x18000800a  jnz     loc_180007C8C
0x180008010  call    cs:__imp_GetLastError
0x180008016  test    eax, eax
0x180008018  jle     short loc_180008022
0x18000801a  movzx   eax, ax
0x18000801d  or      eax, 80070000h
0x180008022  xor     r9d, r9d; lpArguments
0x180008025  xor     r8d, r8d; nNumberOfArguments
0x180008028  mov     edx, 1; dwExceptionFlags
  ... truncated ...
```

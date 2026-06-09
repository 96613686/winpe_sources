# wpcplugs::AppRepository::StateRepo::AppRepository::GetApplicationPackages(void)

- ea: `0x18006c4d0`
- end: `0x18006caed`
- name: `?GetApplicationPackages@AppRepository@StateRepo@1wpcplugs@@UEBA?AV?$vector@V?$shared_ptr@UIAppPackage@AppRepository@wpcplugs@@@std@@V?$allocator@V?$shared_ptr@UIAppPackage@AppRepository@wpcplugs@@@std@@@2@@std@@XZ`
- size: `1565`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x18001ccf0`
- `0x18002eb3c`
- `0x18002f3ac`
- `0x180069ba0`
- `0x18006b5a8`
- `0x18006c4d0`
- `0x18006e83c`
- `0x18006ef5c`
- `0x1800715e4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c5a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c60c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c5a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c60c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006c571`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006c5dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006c649`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006c571`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006c5dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006c649`

## string_xrefs

- `0x18006ca5a`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ca77`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ca94`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006cab1`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006cac6`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006cadb`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
_QWORD *__fastcall wpcplugs::AppRepository::StateRepo::AppRepository::GetApplicationPackages(__int64 a1, _QWORD *a2)
{
  int v3; // edi
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v8; // rcx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  int v17; // eax
  wil::details::in1diag3 *v18; // rcx
  int v19; // eax
  int v20; // ecx
  wpcplugs::AppRepository::StateRepo **Reserved1; // r13
  int v22; // eax
  int v23; // eax
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **); // rdi
  wpcplugs::AppRepository::StateRepo *v26; // rcx
  int v27; // eax
  unsigned int v28; // r14d
  unsigned int v29; // r12d
  int v30; // eax
  struct Windows::Internal::StateRepository::IPackageFamily *v31; // rdx
  struct Windows::Internal::StateRepository::IApplicationStatics *v32; // r8
  char *v33; // rdi
  _QWORD *v34; // r15
  wpcplugs::AppRepository::StateRepo *v35; // rbx
  _QWORD *v36; // rdx
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **); // rdi
  wpcplugs::AppRepository::StateRepo *v39; // rcx
  int v40; // eax
  wpcplugs::AppRepository::StateRepo *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  struct Windows::Internal::StateRepository::IPackage *v46; // rcx
  __int64 v47; // rcx
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+30h] [rbp-D0h]
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v52; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+48h] [rbp-B8h] BYREF
  int v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h]
  unsigned int v56; // [rsp+60h] [rbp-A0h] BYREF
  int *v57; // [rsp+68h] [rbp-98h]
  int v58; // [rsp+70h] [rbp-90h] BYREF
  wpcplugs::AppRepository::StateRepo *v59; // [rsp+78h] [rbp-88h] BYREF
  __int64 v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+88h] [rbp-78h] BYREF
  int i; // [rsp+90h] [rbp-70h]
  char *v63; // [rsp+98h] [rbp-68h] BYREF
  char *v64; // [rsp+A0h] [rbp-60h]
  _QWORD *v65; // [rsp+A8h] [rbp-58h]
  char *v66; // [rsp+B0h] [rbp-50h]
  char v67[8]; // [rsp+B8h] [rbp-48h] BYREF
  int v68; // [rsp+C0h] [rbp-40h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v65 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v3 = 1;
  v53 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageFamily", 0x2Eu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
LABEL_58:
    wil::details::in1diag3::Throw_Hr(
      v8,
      (void *)0xD8,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v49);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v53);
  v8 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_58;
  v52 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
LABEL_60:
    wil::details::in1diag3::Throw_Hr(
      v13,
      (void *)0xDB,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v12,
      v49);
  }
  v12 = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v52);
  v13 = retaddr;
  if ( v12 < 0 )
    goto LABEL_60;
  v51 = 0;
  string = 0;
  v14 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
LABEL_62:
    wil::details::in1diag3::Throw_Hr(
      v18,
      (void *)0xDE,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v17,
      v49);
  }
  v17 = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v51);
  v18 = retaddr;
  if ( v17 < 0 )
    goto LABEL_62;
  v61 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 144LL))(v53, &v61);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v19,
      v49);
  wil::GetRangeNoThrow<Windows::Internal::StateRepository::PackageFamily *>(v67, v61);
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::begin(
    v67,
    &hstringHeader);
  v20 = v68;
  for ( i = v68; ; v20 = i )
  {
    Reserved1 = (wpcplugs::AppRepository::StateRepo **)hstringHeader.Reserved.Reserved1;
    if ( **((int **)hstringHeader.Reserved.Reserved1 + 2) < 0 || *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] == v20 )
      break;
    v60 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v51 + 216LL))(
            v51,
            *((_QWORD *)hstringHeader.Reserved.Reserved1 + 4),
            1,
            &v60);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v22,
        v49);
    v55 = v60;
    v57 = &v58;
    v58 = 0;
    v59 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v60 + 56LL))(v60, &v56);
    *v57 = v23;
    v50 = v3 | 6;
    if ( v23 >= 0 && v56 )
    {
      v24 = v55;
      v25 = *(__int64 (__fastcall **)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **))(*(_QWORD *)v55 + 48LL);
      v26 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v27 = v25(v24, 0, &v59);
      *v57 = v27;
    }
    v28 = 0;
    v29 = v56;
    while ( *v57 >= 0 && v28 != v29 )
    {
      v54 = 0;
      v30 = (*(__int64 (__fastcall **)(wpcplugs::AppRepository::StateRepo *, int *))(*(_QWORD *)v59 + 1008LL))(
              v59,
              &v54);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
          (const char *)(unsigned int)v30,
          v49);
      if ( v54 == 3
        && (!wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(Reserved1[4], v31)
         || wpcplugs::AppRepository::StateRepo::HasAppListEntry(v59, v52, v32)) )
      {
        v33 = (char *)operator new(0x20u);
        v66 = v33;
        *(_OWORD *)v33 = 0;
        *((_DWORD *)v33 + 2) = 1;
        *((_DWORD *)v33 + 3) = 1;
        *(_QWORD *)v33 = &std::_Ref_count_obj2<wpcplugs::AppRepository::StateRepo::AppPackage>::`vftable';
        v34 = v33 + 16;
        v35 = v59;
        if ( v59 )
          (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v59 + 8LL))(v59);
        *v34 = &wpcplugs::AppRepository::StateRepo::AppPackage::`vftable';
        *((_QWORD *)v33 + 3) = v35;
        if ( v35 )
        {
          (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v35 + 8LL))(v35);
          (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v35 + 16LL))(v35);
        }
        v50 |= 8u;
        v63 = v33 + 16;
        v64 = v33;
        v36 = (_QWORD *)a2[1];
        if ( v36 == (_QWORD *)a2[2] )
        {
          std::vector<std::shared_ptr<wpcplugs::AppRepository::IAppPackage>>::_Emplace_reallocate<std::shared_ptr<wpcplugs::AppRepository::StateRepo::AppPackage> &>(
            a2,
            v36,
            &v63);
          v33 = v64;
        }
        else
        {
          *v36 = 0;
          v36[1] = 0;
          _InterlockedIncrement((volatile signed __int32 *)v33 + 2);
          *v36 = v34;
          v36[1] = v33;
          a2[1] += 16LL;
        }
        if ( v33 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(void *))v33)(v33);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 8LL))(v33);
          }
        }
      }
      ++v28;
      if ( *v57 >= 0 && v28 < v56 )
      {
        v37 = v55;
        v38 = *(__int64 (__fastcall **)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **))(*(_QWORD *)v55 + 48LL);
        v39 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v39 + 16LL))(v39);
        }
        v40 = v38(v37, v28, &v59);
        *v57 = v40;
      }
    }
    v41 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::vector_iterator_nothrow::operator++(&hstringHeader);
    v3 = v50;
  }
  v43 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  return a2;
}

```

## disassembly

```asm
0x18006c4d0  push    rbp
0x18006c4d2  push    rbx
0x18006c4d3  push    rsi
0x18006c4d4  push    rdi
0x18006c4d5  push    r12
0x18006c4d7  push    r13
0x18006c4d9  push    r14
0x18006c4db  push    r15
0x18006c4dd  lea     rbp, [rsp-18h]
0x18006c4e2  sub     rsp, 118h
0x18006c4e9  mov     rax, cs:__security_cookie
0x18006c4f0  xor     rax, rsp
0x18006c4f3  mov     [rbp+50h+var_50], rax
0x18006c4f7  mov     rsi, rdx
0x18006c4fa  mov     [rbp+50h+var_A8], rdx
0x18006c4fe  xor     r15d, r15d
0x18006c501  mov     [rsp+150h+var_120], r15d
0x18006c506  mov     [rdx], r15
0x18006c509  mov     [rdx+8], r15
0x18006c50d  mov     [rdx+10h], r15
0x18006c511  lea     edi, [r15+1]
0x18006c515  mov     [rsp+150h+var_120], edi
0x18006c519  mov     [rsp+150h+var_108], r15
0x18006c51e  mov     [rbp+50h+string], r15
0x18006c522  lea     r9, [rbp+50h+string]; string
0x18006c526  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x18006c52a  lea     edx, [rdi+2Dh]; length
0x18006c52d  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006c534  call    cs:__imp_WindowsCreateStringReference
0x18006c53a  test    eax, eax
0x18006c53c  js      loc_18006CA6C
0x18006c542  mov     rbx, [rbp+50h+string]
0x18006c546  mov     rcx, [rsp+150h+var_108]
0x18006c54b  test    rcx, rcx
0x18006c54e  jz      short loc_18006C562
0x18006c550  mov     [rsp+150h+var_108], r15
0x18006c555  mov     rax, [rcx]
0x18006c558  mov     rax, [rax+10h]
0x18006c55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c561  nop
0x18006c562  lea     r8, [rsp+150h+var_108]
0x18006c567  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x18006c56e  mov     rcx, rbx
0x18006c571  call    cs:__imp_RoGetActivationFactory
0x18006c577  mov     rcx, [rbp+58h]
0x18006c57b  test    eax, eax
0x18006c57d  js      loc_18006CA74
0x18006c583  mov     [rsp+150h+var_110], r15
0x18006c588  mov     [rbp+50h+string], r15
0x18006c58c  lea     r9, [rbp+50h+string]; string
0x18006c590  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x18006c594  mov     edx, 2Ch ; ','; length
0x18006c599  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18006c5a0  call    cs:__imp_WindowsCreateStringReference
0x18006c5a6  test    eax, eax
0x18006c5a8  js      loc_18006CA89
0x18006c5ae  mov     rbx, [rbp+50h+string]
0x18006c5b2  mov     rcx, [rsp+150h+var_110]
0x18006c5b7  test    rcx, rcx
0x18006c5ba  jz      short loc_18006C5CE
0x18006c5bc  mov     [rsp+150h+var_110], r15
0x18006c5c1  mov     rax, [rcx]
0x18006c5c4  mov     rax, [rax+10h]
0x18006c5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5cd  nop
0x18006c5ce  lea     r8, [rsp+150h+var_110]
0x18006c5d3  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18006c5da  mov     rcx, rbx
0x18006c5dd  call    cs:__imp_RoGetActivationFactory
0x18006c5e3  mov     rcx, [rbp+58h]
0x18006c5e7  test    eax, eax
0x18006c5e9  js      loc_18006CA91
0x18006c5ef  mov     [rsp+150h+var_118], r15
0x18006c5f4  mov     [rbp+50h+string], r15
0x18006c5f8  lea     r9, [rbp+50h+string]; string
0x18006c5fc  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x18006c600  mov     edx, 28h ; '('; length
0x18006c605  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006c60c  call    cs:__imp_WindowsCreateStringReference
0x18006c612  test    eax, eax
0x18006c614  js      loc_18006CAA6
0x18006c61a  mov     rbx, [rbp+50h+string]
0x18006c61e  mov     rcx, [rsp+150h+var_118]
0x18006c623  test    rcx, rcx
0x18006c626  jz      short loc_18006C63A
0x18006c628  mov     [rsp+150h+var_118], r15
0x18006c62d  mov     rax, [rcx]
0x18006c630  mov     rax, [rax+10h]
0x18006c634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c639  nop
0x18006c63a  lea     r8, [rsp+150h+var_118]
0x18006c63f  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18006c646  mov     rcx, rbx
0x18006c649  call    cs:__imp_RoGetActivationFactory
0x18006c64f  mov     rcx, [rbp+58h]
0x18006c653  test    eax, eax
0x18006c655  js      loc_18006CAAE
0x18006c65b  mov     [rbp+50h+var_C8], r15
0x18006c65f  mov     rcx, [rsp+150h+var_108]
0x18006c664  mov     rax, [rcx]
0x18006c667  lea     rdx, [rbp+50h+var_C8]
0x18006c66b  mov     rax, [rax+90h]
0x18006c672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c677  mov     rcx, [rbp+58h]; this
0x18006c67b  test    eax, eax
0x18006c67d  js      loc_18006CAC3
0x18006c683  mov     rdx, [rbp+50h+var_C8]
0x18006c687  lea     rcx, [rbp+50h+var_98]
0x18006c68b  call    ??$GetRangeNoThrow@PEAVPackageFamily@StateRepository@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Internal::StateRepository::PackageFamily *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *> *,long *)
0x18006c690  nop
0x18006c691  lea     rdx, [rbp+50h+hstringHeader]
0x18006c695  lea     rcx, [rbp+50h+var_98]
0x18006c699  call    ?begin@?$vector_range_nothrow@U?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAA?AVvector_iterator_nothrow@12@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::begin(void)
0x18006c69e  mov     ecx, [rbp+50h+var_90]
0x18006c6a1  mov     [rbp+50h+var_C0], ecx
0x18006c6a4  mov     r13, qword ptr [rbp+50h+hstringHeader.Reserved]
0x18006c6a8  mov     rax, [r13+10h]
0x18006c6ac  cmp     [rax], r15d
0x18006c6af  jl      loc_18006C9AC
0x18006c6b5  cmp     dword ptr [rbp+50h+hstringHeader.Reserved+8], ecx
0x18006c6b8  jz      loc_18006C9AC
0x18006c6be  mov     [rbp+50h+var_D0], r15
0x18006c6c2  mov     rcx, [rsp+150h+var_118]
0x18006c6c7  mov     rax, [rcx]
0x18006c6ca  lea     r9, [rbp+50h+var_D0]
0x18006c6ce  mov     r8d, 1
0x18006c6d4  mov     rdx, [r13+20h]
0x18006c6d8  mov     rax, [rax+0D8h]
0x18006c6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c6e4  mov     rcx, [rbp+58h]; this
0x18006c6e8  test    eax, eax
0x18006c6ea  js      loc_18006CA57
0x18006c6f0  mov     rcx, [rbp+50h+var_D0]
0x18006c6f4  mov     [rsp+150h+var_F8], rcx
0x18006c6f9  lea     rax, [rsp+150h+var_E0]
0x18006c6fe  mov     [rsp+150h+var_E8], rax
0x18006c703  mov     [rsp+150h+var_E0], r15d
0x18006c708  mov     [rsp+150h+var_D8], r15
0x18006c70d  mov     rax, [rcx]
0x18006c710  lea     rdx, [rsp+150h+var_F0]
0x18006c715  mov     rax, [rax+38h]
0x18006c719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c71e  mov     ecx, eax
0x18006c720  mov     rax, [rsp+150h+var_E8]
0x18006c725  mov     [rax], ecx
0x18006c727  or      edi, 6
0x18006c72a  mov     [rsp+150h+var_120], edi
0x18006c72e  test    ecx, ecx
0x18006c730  js      short loc_18006C77C
0x18006c732  cmp     [rsp+150h+var_F0], r15d
0x18006c737  jbe     short loc_18006C77C
0x18006c739  mov     rbx, [rsp+150h+var_F8]
0x18006c73e  mov     rax, [rbx]
0x18006c741  mov     rdi, [rax+30h]
0x18006c745  mov     rcx, [rsp+150h+var_D8]
0x18006c74a  test    rcx, rcx
0x18006c74d  jz      short loc_18006C761
0x18006c74f  mov     [rsp+150h+var_D8], r15
0x18006c754  mov     rax, [rcx]
0x18006c757  mov     rax, [rax+10h]
0x18006c75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c760  nop
0x18006c761  lea     r8, [rsp+150h+var_D8]
0x18006c766  xor     edx, edx
0x18006c768  mov     rcx, rbx
0x18006c76b  mov     rax, rdi
0x18006c76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c773  mov     ecx, eax
0x18006c775  mov     rax, [rsp+150h+var_E8]
0x18006c77a  mov     [rax], ecx
0x18006c77c  mov     r14d, r15d
0x18006c77f  mov     r12d, [rsp+150h+var_F0]
0x18006c784  mov     rax, [rsp+150h+var_E8]
0x18006c789  cmp     [rax], r15d
0x18006c78c  jl      loc_18006C961
0x18006c792  cmp     r14d, r12d
0x18006c795  jz      loc_18006C961
0x18006c79b  mov     [rsp+150h+var_100], r15d
0x18006c7a0  mov     rcx, [rsp+150h+var_D8]
0x18006c7a5  mov     rax, [rcx]
0x18006c7a8  lea     rdx, [rsp+150h+var_100]
0x18006c7ad  mov     rax, [rax+3F0h]
0x18006c7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7b9  mov     rcx, [rbp+58h]; this
0x18006c7bd  test    eax, eax
0x18006c7bf  js      loc_18006CAD8
0x18006c7c5  cmp     [rsp+150h+var_100], 3
0x18006c7ca  jnz     loc_18006C8FC
0x18006c7d0  mov     rcx, [r13+20h]; this
0x18006c7d4  call    ?IsFirstPartyPackage@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackageFamily@StateRepository@Internal@Windows@@@Z; wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(Windows::Internal::StateRepository::IPackageFamily *)
0x18006c7d9  test    al, al
0x18006c7db  jz      short loc_18006C7F4
0x18006c7dd  mov     rdx, [rsp+150h+var_110]; struct Windows::Internal::StateRepository::IPackage *
0x18006c7e2  mov     rcx, [rsp+150h+var_D8]; this
0x18006c7e7  call    ?HasAppListEntry@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackage@StateRepository@Internal@Windows@@PEAUIApplicationStatics@567@@Z; wpcplugs::AppRepository::StateRepo::HasAppListEntry(Windows::Internal::StateRepository::IPackage *,Windows::Internal::StateRepository::IApplicationStatics *)
0x18006c7ec  test    al, al
0x18006c7ee  jz      loc_18006C8FC
0x18006c7f4  mov     ecx, 20h ; ' '; Size
0x18006c7f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c7fe  mov     rdi, rax
0x18006c801  mov     [rbp+50h+var_A0], rax
0x18006c805  xorps   xmm0, xmm0
0x18006c808  movups  xmmword ptr [rax], xmm0
0x18006c80b  mov     eax, 1
0x18006c810  mov     [rdi+8], eax
0x18006c813  mov     [rdi+0Ch], eax
0x18006c816  lea     rax, ??_7?$_Ref_count_obj2@VAppPackage@StateRepo@AppRepository@wpcplugs@@@std@@6B@; const std::_Ref_count_obj2<wpcplugs::AppRepository::StateRepo::AppPackage>::`vftable'
0x18006c81d  mov     [rdi], rax
0x18006c820  lea     r15, [rdi+10h]
0x18006c824  mov     rbx, [rsp+150h+var_D8]
0x18006c829  test    rbx, rbx
0x18006c82c  jz      short loc_18006C83E
0x18006c82e  mov     rax, [rbx]
0x18006c831  mov     rcx, rbx
0x18006c834  mov     rax, [rax+8]
0x18006c838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c83d  nop
0x18006c83e  lea     rax, ??_7AppPackage@StateRepo@AppRepository@wpcplugs@@6B@; const wpcplugs::AppRepository::StateRepo::AppPackage::`vftable'
0x18006c845  mov     [r15], rax
0x18006c848  mov     [r15+8], rbx
0x18006c84c  test    rbx, rbx
0x18006c84f  jz      short loc_18006C861
0x18006c851  mov     rax, [rbx]
0x18006c854  mov     rcx, rbx
0x18006c857  mov     rax, [rax+8]
0x18006c85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c860  nop
0x18006c861  test    rbx, rbx
0x18006c864  jz      short loc_18006C876
0x18006c866  mov     rax, [rbx]
0x18006c869  mov     rcx, rbx
0x18006c86c  mov     rax, [rax+10h]
0x18006c870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c875  nop
0x18006c876  or      [rsp+150h+var_120], 8
0x18006c87b  mov     [rbp+50h+var_B8], r15
0x18006c87f  mov     [rbp+50h+var_B0], rdi
0x18006c883  mov     rdx, [rsi+8]
0x18006c887  cmp     rdx, [rsi+10h]
0x18006c88b  jz      short loc_18006C8AE
0x18006c88d  mov     qword ptr [rdx], 0
0x18006c894  mov     qword ptr [rdx+8], 0
0x18006c89c  lock inc dword ptr [rdi+8]
0x18006c8a0  mov     [rdx], r15
0x18006c8a3  mov     [rdx+8], rdi
0x18006c8a7  add     qword ptr [rsi+8], 10h
0x18006c8ac  jmp     short loc_18006C8BE
0x18006c8ae  lea     r8, [rbp+50h+var_B8]
0x18006c8b2  mov     rcx, rsi
0x18006c8b5  call    ??$_Emplace_reallocate@AEAV?$shared_ptr@VAppPackage@StateRepo@AppRepository@wpcplugs@@@std@@@?$vector@V?$shared_ptr@UIAppPackage@AppRepository@wpcplugs@@@std@@V?$allocator@V?$shared_ptr@UIAppPackage@AppRepository@wpcplugs@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAppPackage@AppRepository@wpcplugs@@@1@QEAV21@AEAV?$shared_ptr@VAppPackage@StateRepo@AppRepository@wpcplugs@@@1@@Z; std::vector<std::shared_ptr<wpcplugs::AppRepository::IAppPackage>>::_Emplace_reallocate<std::shared_ptr<wpcplugs::AppRepository::StateRepo::AppPackage> &>(std::shared_ptr<wpcplugs::AppRepository::IAppPackage> * const,std::shared_ptr<wpcplugs::AppRepository::StateRepo::AppPackage> &)
0x18006c8ba  mov     rdi, [rbp+50h+var_B0]
0x18006c8be  xor     r15d, r15d
0x18006c8c1  test    rdi, rdi
0x18006c8c4  jz      short loc_18006C8FC
0x18006c8c6  or      ebx, 0FFFFFFFFh
0x18006c8c9  mov     eax, ebx
0x18006c8cb  lock xadd [rdi+8], eax
0x18006c8d0  add     eax, ebx
0x18006c8d2  jnz     short loc_18006C8FC
0x18006c8d4  mov     rax, [rdi]
0x18006c8d7  mov     rcx, rdi
0x18006c8da  mov     rax, [rax]
0x18006c8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8e2  mov     eax, ebx
0x18006c8e4  lock xadd [rdi+0Ch], eax
0x18006c8e9  add     eax, ebx
0x18006c8eb  jnz     short loc_18006C8FC
0x18006c8ed  mov     rax, [rdi]
0x18006c8f0  mov     rcx, rdi
0x18006c8f3  mov     rax, [rax+8]
0x18006c8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8fc  inc     r14d
0x18006c8ff  mov     rax, [rsp+150h+var_E8]
0x18006c904  cmp     [rax], r15d
0x18006c907  jl      loc_18006C784
0x18006c90d  cmp     r14d, [rsp+150h+var_F0]
0x18006c912  jnb     loc_18006C784
0x18006c918  mov     rbx, [rsp+150h+var_F8]
0x18006c91d  mov     rax, [rbx]
0x18006c920  mov     rdi, [rax+30h]
0x18006c924  mov     rcx, [rsp+150h+var_D8]
0x18006c929  test    rcx, rcx
0x18006c92c  jz      short loc_18006C940
0x18006c92e  mov     [rsp+150h+var_D8], r15
0x18006c933  mov     rax, [rcx]
0x18006c936  mov     rax, [rax+10h]
0x18006c93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c93f  nop
0x18006c940  lea     r8, [rsp+150h+var_D8]
0x18006c945  mov     edx, r14d
0x18006c948  mov     rcx, rbx
0x18006c94b  mov     rax, rdi
0x18006c94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c953  mov     ecx, eax
0x18006c955  mov     rax, [rsp+150h+var_E8]
0x18006c95a  mov     [rax], ecx
0x18006c95c  jmp     loc_18006C784
0x18006c961  mov     rcx, [rsp+150h+var_D8]
0x18006c966  test    rcx, rcx
0x18006c969  jz      short loc_18006C97D
  ... truncated ...
```

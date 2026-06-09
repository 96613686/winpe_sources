# _lambda_0061cceb18921e52647aee7f46b95944_::operator()_wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser_

- ea: `0x1800694cc`
- end: `0x180069b98`
- name: `_lambda_0061cceb18921e52647aee7f46b95944_::operator()_wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser_`
- size: `1740`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180070f80`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x180017450`
- `0x18001ccf0`
- `0x18002eb3c`
- `0x18003b410`
- `0x18004d388`
- `0x1800694cc`
- `0x180069ba0`
- `0x18006a304`
- `0x18006a610`
- `0x18006a854`
- `0x18006aa80`
- `0x18006b5a8`
- `0x18006e4f4`
- `0x18006e83c`
- `0x18006ef5c`
- `0x18006f020`
- `0x1800715e4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800695e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800695e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006977f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800699f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006977f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800699f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800697a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800697a1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800695b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069621`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069690`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800695b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069621`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069690`

## string_xrefs

- `0x180069af0`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180069b0d`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180069b2a`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180069b47`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180069b5c`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180069b71`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180069b86`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
_QWORD *__fastcall lambda_0061cceb18921e52647aee7f46b95944_::operator()_wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser_(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rcx
  HRESULT StringReference; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v9; // rcx
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  wil::details::in1diag3 *v19; // rcx
  int v20; // eax
  _QWORD *v21; // rax
  int v22; // r12d
  __int64 v23; // r14
  __int64 v24; // rdi
  void (__fastcall *v25)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // r8
  __int128 *p_hstringHeader; // rdx
  __int64 v29; // r9
  unsigned __int64 i; // rcx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  struct Windows::Internal::StateRepository::IApplicationStatics *v34; // r8
  struct Windows::Internal::StateRepository::IPackageFamily *v35; // rdx
  _QWORD *v36; // rax
  _QWORD *v37; // rdx
  volatile signed __int32 *v38; // rbx
  wpcplugs::AppRepository::StateRepo *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  struct Windows::Internal::StateRepository::IPackage *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  int v47; // [rsp+20h] [rbp-E0h]
  wpcplugs::AppRepository::StateRepo *v48; // [rsp+30h] [rbp-D0h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v49; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v50; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+48h] [rbp-B8h] BYREF
  int v52; // [rsp+50h] [rbp-B0h]
  int v53; // [rsp+54h] [rbp-ACh] BYREF
  int v54[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v56; // [rsp+68h] [rbp-98h] BYREF
  __int64 v57; // [rsp+70h] [rbp-90h] BYREF
  __int64 v58; // [rsp+78h] [rbp-88h] BYREF
  int v59; // [rsp+80h] [rbp-80h]
  int v60; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v61[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  _QWORD *v66; // [rsp+D0h] [rbp-30h]
  _BYTE v67[8]; // [rsp+D8h] [rbp-28h] BYREF
  volatile signed __int32 *v68; // [rsp+E0h] [rbp-20h]
  _BYTE v69[8]; // [rsp+E8h] [rbp-18h] BYREF
  int v70; // [rsp+F0h] [rbp-10h]
  __int64 v71; // [rsp+108h] [rbp+8h]
  _BYTE v72[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v73[16]; // [rsp+120h] [rbp+20h] BYREF
  __int128 hstringHeader; // [rsp+130h] [rbp+30h] BYREF
  __int128 hstringHeader_16; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v66 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v52 = 1;
  std::wstring::wstring(&hstringHeader, *(_QWORD *)a1 + 72LL);
  v52 = 3;
  anonymous_namespace_::GetUserFromStateRepo(&v55, &hstringHeader);
  std::wstring::~wstring(&hstringHeader);
  v4 = v55;
  if ( !v55 )
    goto LABEL_50;
  v51 = 0;
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.StateRepository.PackageFamily",
                      0x2Eu,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v6, v7);
LABEL_55:
    wil::details::in1diag3::Throw_Hr(
      v9,
      (void *)0x17E,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v47);
  }
  ActivationFactory = RoGetActivationFactory(
                        *((_QWORD *)&hstringHeader_16 + 1),
                        &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426,
                        &v51);
  v9 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_55;
  v50 = 0;
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  v10 = WindowsCreateStringReference(
          L"Windows.Internal.StateRepository.Package",
          0x28u,
          (HSTRING_HEADER *)&hstringHeader,
          (HSTRING *)&hstringHeader_16 + 1);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
LABEL_57:
    wil::details::in1diag3::Throw_Hr(
      v14,
      (void *)0x181,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v13,
      v47);
  }
  v13 = RoGetActivationFactory(*((_QWORD *)&hstringHeader_16 + 1), &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v50);
  v14 = retaddr;
  if ( v13 < 0 )
    goto LABEL_57;
  v49 = 0;
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  v15 = WindowsCreateStringReference(
          L"Windows.Internal.StateRepository.Application",
          0x2Cu,
          (HSTRING_HEADER *)&hstringHeader,
          (HSTRING *)&hstringHeader_16 + 1);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
LABEL_59:
    wil::details::in1diag3::Throw_Hr(
      v19,
      (void *)0x184,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v18,
      v47);
  }
  v18 = RoGetActivationFactory(*((_QWORD *)&hstringHeader_16 + 1), &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v49);
  v19 = retaddr;
  if ( v18 < 0 )
    goto LABEL_59;
  v57 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v51 + 200LL))(v51, v55, &v57);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v20,
      v47);
  v60 = 0;
  v61[0] = 0;
  v61[1] = 0;
  v21 = operator new(0x30u);
  *v21 = v21;
  v21[1] = v21;
  v61[0] = v21;
  v62 = 0;
  v63 = 0;
  v64 = 7;
  v65 = 8;
  v60 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &v62,
    16,
    v21);
  wil::GetRangeNoThrow<Windows::Internal::StateRepository::PackageFamily *>(v69, v57);
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::begin(
    v69,
    &v58);
  v22 = v70;
  while ( 1 )
  {
    v23 = v58;
    if ( **(int **)(v58 + 16) < 0 || v59 == v22 )
      break;
    v56 = 0;
    v24 = *(_QWORD *)(v58 + 32);
    v25 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 88LL);
    WindowsDeleteString(0);
    v56 = 0;
    v25(v24, &v56);
    StringRawBuffer = WindowsGetStringRawBuffer(v56, 0);
    hstringHeader = 0;
    hstringHeader_16 = 0;
    v27 = -1;
    do
      ++v27;
    while ( StringRawBuffer[v27] );
    std::wstring::_Construct<1,unsigned short const *>(&hstringHeader, StringRawBuffer, v27);
    p_hstringHeader = &hstringHeader;
    if ( *((_QWORD *)&hstringHeader_16 + 1) > 7u )
      p_hstringHeader = (__int128 *)hstringHeader;
    v29 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * (__int64)hstringHeader_16; ++i )
      v29 = 0x100000001B3LL * (*((unsigned __int8 *)p_hstringHeader + i) ^ (unsigned __int64)v29);
    if ( !*(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                        &v60,
                        v72,
                        &hstringHeader,
                        v29)
                    + 8) )
    {
      *(_QWORD *)v54 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v50 + 408LL))(
              v50,
              v55,
              *(_QWORD *)(v23 + 32),
              1);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19B,
          (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
          (const char *)(unsigned int)v31,
          (int)v54);
      v53 = 0;
      v32 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v54 + 56LL))(*(_QWORD *)v54, &v53);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19E,
          (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
          (const char *)(unsigned int)v32,
          (int)v54);
      if ( v53 )
      {
        v48 = 0;
        v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, wpcplugs::AppRepository::StateRepo **))(**(_QWORD **)v54 + 48LL))(
                *(_QWORD *)v54,
                0,
                &v48);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A3,
            (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
            (const char *)(unsigned int)v33,
            (int)v54);
        if ( (wpcplugs::AppRepository::StateRepo::HasAppListEntry(v48, v49, v34)
           || !wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(
                 *(wpcplugs::AppRepository::StateRepo **)(v23 + 32),
                 v35))
          && (!**(_BYTE **)(a1 + 8) || !wpcplugs::AppRepository::StateRepo::IsXboxDlc(v48, v35)) )
        {
          v36 = (_QWORD *)std::make_shared<wpcplugs::AppRepository::StateRepo::AppPackageFamily,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> &,Sid const &>(
                            v67,
                            &v48,
                            *(_QWORD *)a1);
          v37 = (_QWORD *)a2[1];
          if ( v37 == (_QWORD *)a2[2] )
          {
            std::vector<std::shared_ptr<wpcplugs::AppRepository::IAppPackageFamily>>::_Emplace_reallocate<std::shared_ptr<wpcplugs::AppRepository::StateRepo::AppPackageFamily>>(
              a2,
              v37,
              v36);
          }
          else
          {
            *v37 = 0;
            v37[1] = 0;
            *v37 = *v36;
            v37[1] = v36[1];
            *v36 = 0;
            v36[1] = 0;
            a2[1] += 16LL;
          }
          v38 = v68;
          if ( v68 )
          {
            if ( !_InterlockedDecrement(v68 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
              if ( !_InterlockedDecrement(v38 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
            }
          }
        }
        v39 = v48;
        if ( v48 )
        {
          v48 = 0;
          (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v39 + 16LL))(v39);
        }
      }
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
        &v60,
        v73,
        &hstringHeader);
      v40 = *(_QWORD *)v54;
      if ( *(_QWORD *)v54 )
      {
        *(_QWORD *)v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
    }
    std::wstring::~wstring(&hstringHeader);
    WindowsDeleteString(v56);
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::vector_iterator_nothrow::operator++(&v58);
  }
  v41 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v62);
  std::list<std::wstring>::~list<std::wstring>(v61);
  v42 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v4 = v55;
LABEL_50:
  if ( v4 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return a2;
}

```

## disassembly

```asm
0x1800694cc  mov     [rsp-8+arg_10], rbx
0x1800694d1  push    rbp
0x1800694d2  push    rsi
0x1800694d3  push    rdi
0x1800694d4  push    r12
0x1800694d6  push    r13
0x1800694d8  push    r14
0x1800694da  push    r15
0x1800694dc  lea     rbp, [rsp-60h]
0x1800694e1  sub     rsp, 160h
0x1800694e8  mov     rax, cs:__security_cookie
0x1800694ef  xor     rax, rsp
0x1800694f2  mov     [rbp+90h+var_40], rax
0x1800694f6  mov     rsi, rdx
0x1800694f9  mov     r15, rcx
0x1800694fc  mov     [rbp+90h+var_C0], rdx
0x180069500  xor     r13d, r13d
0x180069503  mov     [rsp+190h+var_140], r13d
0x180069508  mov     [rdx], r13
0x18006950b  mov     [rdx+8], r13
0x18006950f  mov     [rdx+10h], r13
0x180069513  mov     [rsp+190h+var_140], 1
0x18006951b  mov     rdx, [rcx]
0x18006951e  add     rdx, 48h ; 'H'
0x180069522  lea     rcx, [rbp+90h+hstringHeader]
0x180069526  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006952b  mov     [rsp+190h+var_140], 3
0x180069533  lea     rdx, [rbp+90h+hstringHeader]
0x180069537  lea     rcx, [rsp+190h+var_130]
0x18006953c  call    _anonymous_namespace___GetUserFromStateRepo
0x180069541  nop
0x180069542  lea     rcx, [rbp+90h+hstringHeader]
0x180069546  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006954b  mov     rcx, [rsp+190h+var_130]
0x180069550  test    rcx, rcx
0x180069553  jz      loc_180069AAC
0x180069559  mov     [rsp+190h+var_148], r13
0x18006955e  mov     [rbp+90h+string], r13
0x180069562  lea     r9, [rbp+90h+string]; string
0x180069566  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18006956a  lea     edx, [r13+2Eh]; length
0x18006956e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180069575  call    cs:__imp_WindowsCreateStringReference
0x18006957b  test    eax, eax
0x18006957d  js      loc_180069B02
0x180069583  mov     rbx, [rbp+90h+string]
0x180069587  mov     rcx, [rsp+190h+var_148]
0x18006958c  test    rcx, rcx
0x18006958f  jz      short loc_1800695A3
0x180069591  mov     [rsp+190h+var_148], r13
0x180069596  mov     rax, [rcx]
0x180069599  mov     rax, [rax+10h]
0x18006959d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695a2  nop
0x1800695a3  lea     r8, [rsp+190h+var_148]
0x1800695a8  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x1800695af  mov     rcx, rbx
0x1800695b2  call    cs:__imp_RoGetActivationFactory
0x1800695b8  mov     rcx, [rbp+98h]
0x1800695bf  test    eax, eax
0x1800695c1  js      loc_180069B0A
0x1800695c7  mov     [rsp+190h+var_150], r13
0x1800695cc  mov     [rbp+90h+string], r13
0x1800695d0  lea     r9, [rbp+90h+string]; string
0x1800695d4  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x1800695d8  mov     edx, 28h ; '('; length
0x1800695dd  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800695e4  call    cs:__imp_WindowsCreateStringReference
0x1800695ea  test    eax, eax
0x1800695ec  js      loc_180069B1F
0x1800695f2  mov     rbx, [rbp+90h+string]
0x1800695f6  mov     rcx, [rsp+190h+var_150]
0x1800695fb  test    rcx, rcx
0x1800695fe  jz      short loc_180069612
0x180069600  mov     [rsp+190h+var_150], r13
0x180069605  mov     rax, [rcx]
0x180069608  mov     rax, [rax+10h]
0x18006960c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069611  nop
0x180069612  lea     r8, [rsp+190h+var_150]
0x180069617  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18006961e  mov     rcx, rbx
0x180069621  call    cs:__imp_RoGetActivationFactory
0x180069627  mov     rcx, [rbp+98h]
0x18006962e  test    eax, eax
0x180069630  js      loc_180069B27
0x180069636  mov     [rsp+190h+var_158], r13
0x18006963b  mov     [rbp+90h+string], r13
0x18006963f  lea     r9, [rbp+90h+string]; string
0x180069643  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x180069647  mov     edx, 2Ch ; ','; length
0x18006964c  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180069653  call    cs:__imp_WindowsCreateStringReference
0x180069659  test    eax, eax
0x18006965b  js      loc_180069B3C
0x180069661  mov     rbx, [rbp+90h+string]
0x180069665  mov     rcx, [rsp+190h+var_158]
0x18006966a  test    rcx, rcx
0x18006966d  jz      short loc_180069681
0x18006966f  mov     [rsp+190h+var_158], r13
0x180069674  mov     rax, [rcx]
0x180069677  mov     rax, [rax+10h]
0x18006967b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069680  nop
0x180069681  lea     r8, [rsp+190h+var_158]
0x180069686  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18006968d  mov     rcx, rbx
0x180069690  call    cs:__imp_RoGetActivationFactory
0x180069696  mov     rcx, [rbp+98h]
0x18006969d  test    eax, eax
0x18006969f  js      loc_180069B44
0x1800696a5  mov     [rsp+190h+var_120], r13
0x1800696aa  mov     rcx, [rsp+190h+var_148]
0x1800696af  mov     rax, [rcx]
0x1800696b2  lea     r8, [rsp+190h+var_120]
0x1800696b7  mov     rdx, [rsp+190h+var_130]
0x1800696bc  mov     rax, [rax+0C8h]
0x1800696c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696c8  mov     rcx, [rbp+98h]; this
0x1800696cf  test    eax, eax
0x1800696d1  js      loc_180069B59
0x1800696d7  mov     [rbp+90h+var_100], 0
0x1800696de  mov     [rbp+90h+var_F8], r13
0x1800696e2  mov     [rbp+90h+var_F0], r13
0x1800696e6  mov     ecx, 30h ; '0'; Size
0x1800696eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800696f0  mov     [rax], rax
0x1800696f3  mov     [rax+8], rax
0x1800696f7  mov     [rbp+90h+var_F8], rax
0x1800696fb  mov     [rbp+90h+var_E8], r13
0x1800696ff  xorps   xmm0, xmm0
0x180069702  movdqa  [rbp+90h+var_E0], xmm0
0x180069707  mov     [rbp+90h+var_D0], 7
0x18006970f  mov     [rbp+90h+var_C8], 8
0x180069717  mov     [rbp+90h+var_100], 3F800000h
0x18006971e  mov     r8, rax
0x180069721  mov     edx, 10h
0x180069726  lea     rcx, [rbp+90h+var_E8]
0x18006972a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18006972f  nop
0x180069730  mov     rdx, [rsp+190h+var_120]
0x180069735  lea     rcx, [rbp+90h+var_A8]
0x180069739  call    ??$GetRangeNoThrow@PEAVPackageFamily@StateRepository@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Internal::StateRepository::PackageFamily *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *> *,long *)
0x18006973e  nop
0x18006973f  lea     rdx, [rsp+190h+var_118]
0x180069744  lea     rcx, [rbp+90h+var_A8]
0x180069748  call    ?begin@?$vector_range_nothrow@U?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAA?AVvector_iterator_nothrow@12@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::begin(void)
0x18006974d  mov     r12d, [rbp+90h+var_A0]
0x180069751  mov     r14, [rsp+190h+var_118]
0x180069756  mov     rax, [r14+10h]
0x18006975a  cmp     [rax], r13d
0x18006975d  jl      loc_180069A0A
0x180069763  cmp     [rbp+90h+var_110], r12d
0x180069767  jz      loc_180069A0A
0x18006976d  mov     [rsp+190h+var_128], r13
0x180069772  mov     rdi, [r14+20h]
0x180069776  mov     rax, [rdi]
0x180069779  mov     rbx, [rax+58h]
0x18006977d  xor     ecx, ecx; string
0x18006977f  call    cs:__imp_WindowsDeleteString
0x180069785  mov     [rsp+190h+var_128], r13
0x18006978a  lea     rdx, [rsp+190h+var_128]
0x18006978f  mov     rcx, rdi
0x180069792  mov     rax, rbx
0x180069795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006979a  xor     edx, edx; length
0x18006979c  mov     rcx, [rsp+190h+var_128]; string
0x1800697a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800697a7  xorps   xmm0, xmm0
0x1800697aa  movups  xmmword ptr [rbp+90h+hstringHeader.Reserved], xmm0
0x1800697ae  xorps   xmm1, xmm1
0x1800697b1  movdqu  xmmword ptr [rbp+40h], xmm1
0x1800697b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800697ba  mov     r8, rdi
0x1800697bd  inc     r8
0x1800697c0  cmp     [rax+r8*2], r13w
0x1800697c5  jnz     short loc_1800697BD
0x1800697c7  mov     rdx, rax
0x1800697ca  lea     rcx, [rbp+90h+hstringHeader]
0x1800697ce  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800697d3  nop
0x1800697d4  mov     rax, qword ptr [rbp+90h+hstringHeader.Reserved+10h]
0x1800697d8  lea     rdx, [rbp+90h+hstringHeader]
0x1800697dc  cmp     [rbp+90h+string], 7
0x1800697e1  cmova   rdx, qword ptr [rbp+90h+hstringHeader.Reserved]
0x1800697e6  mov     r9, 0CBF29CE484222325h
0x1800697f0  lea     r8, [rax+rax]
0x1800697f4  mov     rcx, r13
0x1800697f7  test    r8, r8
0x1800697fa  jz      short loc_180069819
0x1800697fc  movzx   eax, byte ptr [rcx+rdx]
0x180069800  xor     r9, rax
0x180069803  mov     r10, 100000001B3h
0x18006980d  imul    r9, r10
0x180069811  inc     rcx
0x180069814  cmp     rcx, r8
0x180069817  jb      short loc_1800697FC
0x180069819  lea     r8, [rbp+90h+hstringHeader]
0x18006981d  lea     rdx, [rbp+90h+var_80]
0x180069821  lea     rcx, [rbp+90h+var_100]
0x180069825  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18006982a  cmp     [rax+8], r13
0x18006982e  jnz     loc_1800699E6
0x180069834  mov     qword ptr [rsp+190h+var_138], r13
0x180069839  mov     rcx, [rsp+190h+var_150]
0x18006983e  mov     rax, [rcx]
0x180069841  lea     rdx, [rsp+190h+var_138]
0x180069846  mov     qword ptr [rsp+190h+var_170], rdx; int
0x18006984b  mov     r9d, 1
0x180069851  mov     r8, [r14+20h]
0x180069855  mov     rdx, [rsp+190h+var_130]
0x18006985a  mov     rax, [rax+198h]
0x180069861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069866  mov     rcx, [rbp+98h]; this
0x18006986d  test    eax, eax
0x18006986f  js      loc_180069AED
0x180069875  mov     [rsp+190h+var_13C], r13d
0x18006987a  mov     rcx, qword ptr [rsp+190h+var_138]
0x18006987f  mov     rax, [rcx]
0x180069882  lea     rdx, [rsp+190h+var_13C]
0x180069887  mov     rax, [rax+38h]
0x18006988b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069890  mov     rcx, [rbp+98h]; this
0x180069897  test    eax, eax
0x180069899  js      loc_180069B83
0x18006989f  cmp     [rsp+190h+var_13C], r13d
0x1800698a4  jbe     loc_1800699B8
0x1800698aa  mov     [rsp+190h+var_160], r13
0x1800698af  mov     rcx, qword ptr [rsp+190h+var_138]
0x1800698b4  mov     rax, [rcx]
0x1800698b7  lea     r8, [rsp+190h+var_160]
0x1800698bc  xor     edx, edx
0x1800698be  mov     rax, [rax+30h]
0x1800698c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698c7  mov     rcx, [rbp+98h]; this
0x1800698ce  test    eax, eax
0x1800698d0  js      loc_180069B6E
0x1800698d6  mov     rdx, [rsp+190h+var_158]; struct Windows::Internal::StateRepository::IPackage *
0x1800698db  mov     rcx, [rsp+190h+var_160]; this
0x1800698e0  call    ?HasAppListEntry@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackage@StateRepository@Internal@Windows@@PEAUIApplicationStatics@567@@Z; wpcplugs::AppRepository::StateRepo::HasAppListEntry(Windows::Internal::StateRepository::IPackage *,Windows::Internal::StateRepository::IApplicationStatics *)
0x1800698e5  test    al, al
0x1800698e7  jnz     short loc_1800698FA
0x1800698e9  mov     rcx, [r14+20h]; this
0x1800698ed  call    ?IsFirstPartyPackage@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackageFamily@StateRepository@Internal@Windows@@@Z; wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(Windows::Internal::StateRepository::IPackageFamily *)
0x1800698f2  test    al, al
0x1800698f4  jnz     loc_18006999C
0x1800698fa  mov     rax, [r15+8]
0x1800698fe  cmp     [rax], r13b
0x180069901  jz      short loc_180069915
0x180069903  mov     rcx, [rsp+190h+var_160]; this
0x180069908  call    ?IsXboxDlc@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackage@StateRepository@Internal@Windows@@@Z; wpcplugs::AppRepository::StateRepo::IsXboxDlc(Windows::Internal::StateRepository::IPackage *)
0x18006990d  test    al, al
0x18006990f  jnz     loc_18006999C
0x180069915  mov     r8, [r15]
0x180069918  lea     rdx, [rsp+190h+var_160]
0x18006991d  lea     rcx, [rbp+90h+var_B8]
0x180069921  call    ??$make_shared@VAppPackageFamily@StateRepo@AppRepository@wpcplugs@@AEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBVSid@@@std@@YA?AV?$shared_ptr@VAppPackageFamily@StateRepo@AppRepository@wpcplugs@@@0@AEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBVSid@@@Z; std::make_shared<wpcplugs::AppRepository::StateRepo::AppPackageFamily,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> &,Sid const &>(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> &,Sid const &)
0x180069926  mov     r8, rax
0x180069929  mov     rdx, [rsi+8]
0x18006992d  cmp     rdx, [rsi+10h]
0x180069931  jz      short loc_180069956
0x180069933  mov     [rdx], r13
0x180069936  mov     [rdx+8], r13
0x18006993a  mov     rax, [rax]
0x18006993d  mov     [rdx], rax
0x180069940  mov     rax, [r8+8]
0x180069944  mov     [rdx+8], rax
0x180069948  mov     [r8], r13
0x18006994b  mov     [r8+8], r13
0x18006994f  add     qword ptr [rsi+8], 10h
0x180069954  jmp     short loc_18006995F
0x180069956  mov     rcx, rsi
0x180069959  call    ??$_Emplace_reallocate@V?$shared_ptr@VAppPackageFamily@StateRepo@AppRepository@wpcplugs@@@std@@@?$vector@V?$shared_ptr@UIAppPackageFamily@AppRepository@wpcplugs@@@std@@V?$allocator@V?$shared_ptr@UIAppPackageFamily@AppRepository@wpcplugs@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAppPackageFamily@AppRepository@wpcplugs@@@1@QEAV21@$$QEAV?$shared_ptr@VAppPackageFamily@StateRepo@AppRepository@wpcplugs@@@1@@Z; std::vector<std::shared_ptr<wpcplugs::AppRepository::IAppPackageFamily>>::_Emplace_reallocate<std::shared_ptr<wpcplugs::AppRepository::StateRepo::AppPackageFamily>>(std::shared_ptr<wpcplugs::AppRepository::IAppPackageFamily> * const,std::shared_ptr<wpcplugs::AppRepository::StateRepo::AppPackageFamily> &&)
0x18006995e  nop
0x18006995f  mov     rbx, [rbp+90h+var_B0]
0x180069963  test    rbx, rbx
0x180069966  jz      short loc_18006999C
0x180069968  mov     eax, edi
0x18006996a  lock xadd [rbx+8], eax
0x18006996f  add     eax, edi
0x180069971  jnz     short loc_18006999C
0x180069973  mov     rax, [rbx]
0x180069976  mov     rcx, rbx
0x180069979  mov     rax, [rax]
0x18006997c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069981  mov     eax, edi
0x180069983  lock xadd [rbx+0Ch], eax
0x180069988  add     eax, edi
0x18006998a  jnz     short loc_18006999C
0x18006998c  mov     rax, [rbx]
0x18006998f  mov     rcx, rbx
0x180069992  mov     rax, [rax+8]
0x180069996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006999b  nop
0x18006999c  mov     rcx, [rsp+190h+var_160]
0x1800699a1  test    rcx, rcx
0x1800699a4  jz      short loc_1800699B8
0x1800699a6  mov     [rsp+190h+var_160], r13
0x1800699ab  mov     rax, [rcx]
0x1800699ae  mov     rax, [rax+10h]
  ... truncated ...
```

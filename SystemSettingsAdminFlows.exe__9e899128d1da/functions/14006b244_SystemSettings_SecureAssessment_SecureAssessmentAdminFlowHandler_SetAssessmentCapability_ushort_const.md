# SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::SetAssessmentCapability(ushort const *)

- ea: `0x14006b244`
- end: `0x14006b79f`
- name: `?SetAssessmentCapability@SecureAssessmentAdminFlowHandler@SecureAssessment@SystemSettings@@SAJPEBG@Z`
- size: `1371`
- prototype: `__int64 __fastcall(wchar_t *String)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140020120`
- `0x14006a94c`

## callees

- `0x14001a2a0`
- `0x14002a2c0`
- `0x14003ff9c`
- `0x1400407b0`
- `0x1400408dc`
- `0x140062ac4`
- `0x140063e9c`
- `0x140069e70`
- `0x140069f24`
- `0x140069f48`
- `0x14006b244`
- `0x14007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x14006b376`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x14006b3f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x14006b376`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x14006b3f2`
- `KERNEL32!CompareStringOrdinal` at `0x14006b4b4`
- `KERNEL32!CompareStringOrdinal` at `0x14006b519`
- `KERNEL32!CompareStringOrdinal` at `0x14006b56f`
- `KERNEL32!CompareStringOrdinal` at `0x14006b5cb`
- `KERNEL32!CompareStringOrdinal` at `0x14006b4b4`
- `KERNEL32!CompareStringOrdinal` at `0x14006b519`
- `KERNEL32!CompareStringOrdinal` at `0x14006b56f`
- `KERNEL32!CompareStringOrdinal` at `0x14006b5cb`
- `ole32!CoUninitialize` at `0x14006b755`
- `ole32!CoUninitialize` at `0x14006b755`
- `ole32!CoInitializeEx` at `0x14006b25f`
- `ole32!CoInitializeEx` at `0x14006b25f`
- `ole32!CoCreateInstance` at `0x14006b2ca`
- `ole32!CoCreateInstance` at `0x14006b2ca`
- `OLEAUT32!__imp_VariantInit` at `0x14006b462`
- `OLEAUT32!__imp_VariantInit` at `0x14006b462`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::SetAssessmentCapability(
        wchar_t *String)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  size_t v8; // rsi
  const wchar_t *v9; // r8
  const WCHAR *v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // r14
  size_t v13; // rsi
  const wchar_t *v14; // r8
  STRSAFE_LPWSTR v15; // r14
  __int64 v16; // rdx
  const WCHAR *v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rsi
  const WCHAR *v21; // rcx
  const unsigned __int16 *v22; // rdx
  __int64 bstr; // rax
  __int64 v24; // rdx
  const WCHAR *v25; // rcx
  LPVOID v26; // rdi
  __int64 (__fastcall *v27)(LPVOID, __int64, __int64 *); // rbx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  const char *v31; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-D8h]
  int ppva; // [rsp+20h] [rbp-D8h]
  int ppvb; // [rsp+20h] [rbp-D8h]
  _BYTE v36[8]; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest[2]; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-A8h]
  STRSAFE_LPWSTR v40; // [rsp+60h] [rbp-98h] BYREF
  size_t v41; // [rsp+68h] [rbp-90h]
  __int64 v42; // [rsp+70h] [rbp-88h]
  __int64 v43; // [rsp+78h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-78h] BYREF
  __int128 v45; // [rsp+98h] [rbp-60h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-50h]
  VARIANTARG v47; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  LPVOID v49; // [rsp+110h] [rbp+18h] BYREF
  __int64 v50; // [rsp+118h] [rbp+20h] BYREF

  v2 = CoInitializeEx(0, 0);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v2,
        ppv);
    v49 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v3 = CoCreateInstance(
           &GUID_66d0db14_5638_475f_a386_629522d8c461,
           0,
           1u,
           &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
           &v49);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v3,
        ppva);
    wil::make_bstr(&v43, L"OMADM::AccountID");
    _variant_t::_variant_t((_variant_t *)&v45, v4);
    *(_OWORD *)pszDest = v45;
    v39 = v46;
    v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, STRSAFE_LPWSTR *))(*(_QWORD *)v49 + 104LL))(v49, v43, pszDest);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v5,
        ppva);
    v6 = wcstok(String, L":", 0);
    v7 = v6;
    pszDest[0] = 0;
    pszDest[1] = 0;
    v39 = 0;
    if ( v6 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                  pszDest,
                  v8) >= 0 )
      {
        v9 = v7;
        v10 = pszDest[0];
        StringCchCopyNW(pszDest[0], v8 + 1, v9, v8);
        pszDest[1] = (STRSAFE_LPWSTR)v8;
        goto LABEL_15;
      }
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszDest);
    }
    v10 = pszDest[0];
LABEL_15:
    v11 = wcstok(0, L":", 0);
    v12 = v11;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    if ( v11 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v11[v13] );
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                  &v40,
                  v13) >= 0 )
      {
        v14 = v12;
        v15 = v40;
        StringCchCopyNW(v40, v13 + 1, v14, v13);
        v41 = v13;
        goto LABEL_22;
      }
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
    }
    v15 = v40;
LABEL_22:
    VariantInit(&pvarg);
    pvarg.vt = 11;
    LODWORD(v16) = v41;
    if ( v41 == -1 )
    {
      if ( v15 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
      }
      else
      {
        LODWORD(v16) = 0;
      }
    }
    v17 = &Data;
    if ( v15 )
      v17 = v15;
    v18 = CompareStringOrdinal(v17, v16, L"true", -1, 1);
    pvarg.iVal = -1;
    if ( v18 != 2 )
      pvarg.iVal = 0;
    v50 = 0;
    LODWORD(v19) = pszDest[1];
    v20 = (__int64)pszDest[1];
    if ( pszDest[1] == (STRSAFE_LPWSTR)-1LL )
    {
      if ( v10 )
      {
        v19 = -1;
        do
          ++v19;
        while ( v10[v19] );
      }
      else
      {
        LODWORD(v19) = 0;
      }
    }
    v21 = &Data;
    if ( v10 )
      v21 = v10;
    if ( CompareStringOrdinal(v21, v19, L"screenCapture", -1, 1) == 2 )
    {
      v22 = L"./Vendor/MSFT/SecureAssessment/AllowScreenMonitoring";
LABEL_42:
      bstr = wil::make_bstr(v36, v22);
LABEL_64:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v50,
        bstr);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v36);
      v37 = 0;
      v26 = v49;
      v27 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v49 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      v28 = v27(v26, v50, &v37);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v28,
          ppvb);
      v47 = pvarg;
      v29 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v37 + 96LL))(v37, &v47, 5);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v29,
          ppvb);
      v30 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 24LL))(v49);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v30,
          ppvb);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszDest);
      _variant_t::~_variant_t((_variant_t *)&v45);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
      CoUninitialize();
      return 0;
    }
    LODWORD(v24) = v20;
    if ( v20 == -1 )
    {
      if ( v10 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v10[v24] );
        goto LABEL_53;
      }
      LODWORD(v24) = 0;
    }
    else if ( v10 )
    {
LABEL_53:
      v25 = v10;
LABEL_50:
      if ( CompareStringOrdinal(v25, v24, L"printing", -1, 1) == 2 )
      {
        v22 = L"./Vendor/MSFT/SecureAssessment/RequirePrinting";
        goto LABEL_42;
      }
      if ( v20 == -1 )
      {
        if ( v10 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v10[v20] );
          goto LABEL_62;
        }
        LODWORD(v20) = 0;
      }
      else if ( v10 )
      {
LABEL_62:
        if ( CompareStringOrdinal(v10, v20, L"textSuggestions", -1, 1) != 2 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x50,
            (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
            (const char *)0x80070057LL,
            ppvb);
        bstr = wil::make_bstr(v36, L"./Vendor/MSFT/SecureAssessment/AllowTextSuggestions");
        goto LABEL_64;
      }
      v10 = &Data;
      goto LABEL_62;
    }
    v25 = &Data;
    goto LABEL_50;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5C,
                           (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureas"
                                         "sessmentadminflowhandler.cpp",
                           v31);
  }
  return result;
}

```

## disassembly

```asm
0x14006b244  mov     [rsp+arg_0], rbx
0x14006b249  push    rsi
0x14006b24a  push    rdi
0x14006b24b  push    r13
0x14006b24d  push    r14
0x14006b24f  push    r15
0x14006b251  sub     rsp, 0D0h
0x14006b258  mov     rbx, rcx
0x14006b25b  xor     edx, edx; dwCoInit
0x14006b25d  xor     ecx, ecx; pvReserved
0x14006b25f  call    cs:__imp_CoInitializeEx
0x14006b265  mov     rcx, [rsp+0F8h]; this
0x14006b26d  xor     r15d, r15d
0x14006b270  test    eax, eax
0x14006b272  jns     short loc_14006B287
0x14006b274  mov     r9d, eax; char *
0x14006b277  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b27e  lea     edx, [r15+25h]; void *
0x14006b282  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b287  mov     r13d, 1
0x14006b28d  mov     [rsp+0F8h+arg_9], r13b
0x14006b295  mov     [rsp+0F8h+arg_10], r15
0x14006b29d  lea     rcx, [rsp+0F8h+arg_10]
0x14006b2a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006b2aa  lea     rax, [rsp+0F8h+arg_10]
0x14006b2b2  mov     qword ptr [rsp+0F8h+ppv], rax; int
0x14006b2b7  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x14006b2be  mov     r8d, r13d; dwClsContext
0x14006b2c1  xor     edx, edx; pUnkOuter
0x14006b2c3  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x14006b2ca  call    cs:__imp_CoCreateInstance
0x14006b2d0  mov     rcx, [rsp+0F8h]; this
0x14006b2d8  test    eax, eax
0x14006b2da  jns     short loc_14006B2EF
0x14006b2dc  mov     r9d, eax; char *
0x14006b2df  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b2e6  lea     edx, [r13+2Bh]; void *
0x14006b2ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b2ef  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x14006b2f6  lea     rcx, [rsp+0F8h+var_80]
0x14006b2fb  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006b300  nop
0x14006b301  lea     rcx, [rsp+0F8h+var_60]; this
0x14006b309  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14006b30e  nop
0x14006b30f  mov     rcx, [rsp+0F8h+arg_10]
0x14006b317  movups  xmm0, [rsp+0F8h+var_60]
0x14006b31f  movsd   xmm1, [rsp+0F8h+var_50]
0x14006b328  movaps  xmmword ptr [rsp+0F8h+pszDest], xmm0
0x14006b32d  movsd   [rsp+0F8h+var_A8], xmm1
0x14006b333  mov     rax, [rcx]
0x14006b336  lea     r8, [rsp+0F8h+pszDest]
0x14006b33b  mov     rdx, [rsp+0F8h+var_80]
0x14006b340  mov     rax, [rax+68h]
0x14006b344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b349  mov     rcx, [rsp+0F8h]; this
0x14006b351  test    eax, eax
0x14006b353  jns     short loc_14006B369
0x14006b355  mov     r9d, eax; char *
0x14006b358  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b35f  mov     edx, 32h ; '2'; void *
0x14006b364  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b369  xor     r8d, r8d; Context
0x14006b36c  lea     rdx, asc_14008D994; ":"
0x14006b373  mov     rcx, rbx; String
0x14006b376  call    cs:__imp_wcstok
0x14006b37c  mov     rbx, rax
0x14006b37f  mov     [rsp+0F8h+pszDest], r15
0x14006b384  mov     [rsp+0F8h+pszDest+8], r15
0x14006b389  mov     [rsp+0F8h+var_A8], r15
0x14006b38e  test    rax, rax
0x14006b391  jz      short loc_14006B3D3
0x14006b393  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14006b397  mov     rsi, rdi
0x14006b39a  inc     rsi
0x14006b39d  cmp     [rax+rsi*2], r15w
0x14006b3a2  jnz     short loc_14006B39A
0x14006b3a4  mov     rdx, rsi
0x14006b3a7  lea     rcx, [rsp+0F8h+pszDest]
0x14006b3ac  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006b3b1  test    eax, eax
0x14006b3b3  js      short loc_14006B3E1
0x14006b3b5  lea     rdx, [rsi+1]; cchDest
0x14006b3b9  mov     r9, rsi; cchToCopy
0x14006b3bc  mov     r8, rbx; pszSrc
0x14006b3bf  mov     rbx, [rsp+0F8h+pszDest]
0x14006b3c4  mov     rcx, rbx; pszDest
0x14006b3c7  call    StringCchCopyNW
0x14006b3cc  mov     [rsp+0F8h+pszDest+8], rsi
0x14006b3d1  jmp     short loc_14006B3E6
0x14006b3d3  lea     rcx, [rsp+0F8h+pszDest]
0x14006b3d8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006b3dd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14006b3e1  mov     rbx, [rsp+0F8h+pszDest]
0x14006b3e6  xor     r8d, r8d; Context
0x14006b3e9  lea     rdx, asc_14008D994; ":"
0x14006b3f0  xor     ecx, ecx; String
0x14006b3f2  call    cs:__imp_wcstok
0x14006b3f8  mov     r14, rax
0x14006b3fb  mov     [rsp+0F8h+var_98], r15
0x14006b400  mov     [rsp+0F8h+var_90], r15
0x14006b405  mov     [rsp+0F8h+var_88], r15
0x14006b40a  test    rax, rax
0x14006b40d  jz      short loc_14006B44B
0x14006b40f  mov     rsi, rdi
0x14006b412  inc     rsi
0x14006b415  cmp     [rax+rsi*2], r15w
0x14006b41a  jnz     short loc_14006B412
0x14006b41c  mov     rdx, rsi
0x14006b41f  lea     rcx, [rsp+0F8h+var_98]
0x14006b424  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006b429  test    eax, eax
0x14006b42b  js      short loc_14006B455
0x14006b42d  lea     rdx, [rsi+1]; cchDest
0x14006b431  mov     r9, rsi; cchToCopy
0x14006b434  mov     r8, r14; pszSrc
0x14006b437  mov     r14, [rsp+0F8h+var_98]
0x14006b43c  mov     rcx, r14; pszDest
0x14006b43f  call    StringCchCopyNW
0x14006b444  mov     [rsp+0F8h+var_90], rsi
0x14006b449  jmp     short loc_14006B45A
0x14006b44b  lea     rcx, [rsp+0F8h+var_98]
0x14006b450  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006b455  mov     r14, [rsp+0F8h+var_98]
0x14006b45a  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x14006b462  call    cs:__imp_VariantInit
0x14006b468  nop
0x14006b469  mov     eax, 0Bh
0x14006b46e  mov     word ptr [rsp+0F8h+pvarg], ax
0x14006b476  mov     rdx, [rsp+0F8h+var_90]
0x14006b47b  cmp     rdx, rdi
0x14006b47e  jnz     short loc_14006B497
0x14006b480  test    r14, r14
0x14006b483  jz      short loc_14006B494
0x14006b485  mov     rdx, rdi
0x14006b488  inc     rdx
0x14006b48b  cmp     [r14+rdx*2], r15w
0x14006b490  jnz     short loc_14006B488
0x14006b492  jmp     short loc_14006B497
0x14006b494  mov     rdx, r15; cchCount1
0x14006b497  lea     rcx, Data
0x14006b49e  test    r14, r14
0x14006b4a1  cmovnz  rcx, r14; lpString1
0x14006b4a5  mov     [rsp+0F8h+ppv], r13d; bIgnoreCase
0x14006b4aa  mov     r9d, edi; cchCount2
0x14006b4ad  lea     r8, aTrue; "true"
0x14006b4b4  call    cs:__imp_CompareStringOrdinal
0x14006b4ba  cmp     eax, 2
0x14006b4bd  mov     word ptr [rsp+0F8h+pvarg+8], di
0x14006b4c5  jz      short loc_14006B4D0
0x14006b4c7  mov     word ptr [rsp+0F8h+pvarg+8], r15w
0x14006b4d0  mov     [rsp+0F8h+arg_18], r15
0x14006b4d8  mov     rdx, [rsp+0F8h+pszDest+8]
0x14006b4dd  mov     rsi, rdx
0x14006b4e0  cmp     rdx, rdi
0x14006b4e3  jnz     short loc_14006B4FC
0x14006b4e5  test    rbx, rbx
0x14006b4e8  jz      short loc_14006B4F9
0x14006b4ea  mov     rdx, rdi
0x14006b4ed  inc     rdx
0x14006b4f0  cmp     [rbx+rdx*2], r15w
0x14006b4f5  jnz     short loc_14006B4ED
0x14006b4f7  jmp     short loc_14006B4FC
0x14006b4f9  mov     rdx, r15; cchCount1
0x14006b4fc  lea     rcx, Data
0x14006b503  test    rbx, rbx
0x14006b506  cmovnz  rcx, rbx; lpString1
0x14006b50a  mov     [rsp+0F8h+ppv], r13d; bIgnoreCase
0x14006b50f  mov     r9d, edi; cchCount2
0x14006b512  lea     r8, ?c_screenCaptureCap@@3QBGB; "screenCapture"
0x14006b519  call    cs:__imp_CompareStringOrdinal
0x14006b51f  cmp     eax, 2
0x14006b522  jnz     short loc_14006B53A
0x14006b524  lea     rdx, aVendorMsftSecu; "./Vendor/MSFT/SecureAssessment/AllowScr"...
0x14006b52b  lea     rcx, [rsp+0F8h+var_C8]
0x14006b530  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006b535  jmp     loc_14006B5EB
0x14006b53a  mov     rdx, rsi
0x14006b53d  cmp     rsi, rdi
0x14006b540  jnz     short loc_14006B583
0x14006b542  test    rbx, rbx
0x14006b545  jz      short loc_14006B556
0x14006b547  mov     rdx, rdi
0x14006b54a  inc     rdx
0x14006b54d  cmp     [rbx+rdx*2], r15w
0x14006b552  jnz     short loc_14006B54A
0x14006b554  jmp     short loc_14006B588
0x14006b556  mov     rdx, r15; cchCount1
0x14006b559  lea     rcx, Data; lpString1
0x14006b560  mov     [rsp+0F8h+ppv], r13d; bIgnoreCase
0x14006b565  mov     r9d, edi; cchCount2
0x14006b568  lea     r8, ?c_printingCap@@3QBGB; "printing"
0x14006b56f  call    cs:__imp_CompareStringOrdinal
0x14006b575  cmp     eax, 2
0x14006b578  jnz     short loc_14006B58D
0x14006b57a  lea     rdx, aVendorMsftSecu_0; "./Vendor/MSFT/SecureAssessment/RequireP"...
0x14006b581  jmp     short loc_14006B52B
0x14006b583  test    rbx, rbx
0x14006b586  jz      short loc_14006B559
0x14006b588  mov     rcx, rbx
0x14006b58b  jmp     short loc_14006B560
0x14006b58d  cmp     rsi, rdi
0x14006b590  jnz     short loc_14006B5AB
0x14006b592  test    rbx, rbx
0x14006b595  jz      short loc_14006B5A6
0x14006b597  mov     rsi, rdi
0x14006b59a  inc     rsi
0x14006b59d  cmp     [rbx+rsi*2], r15w
0x14006b5a2  jnz     short loc_14006B59A
0x14006b5a4  jmp     short loc_14006B5B7
0x14006b5a6  mov     rsi, r15
0x14006b5a9  jmp     short loc_14006B5B0
0x14006b5ab  test    rbx, rbx
0x14006b5ae  jnz     short loc_14006B5B7
0x14006b5b0  lea     rbx, Data
0x14006b5b7  mov     edx, esi; cchCount1
0x14006b5b9  mov     [rsp+0F8h+ppv], r13d; int
0x14006b5be  mov     r9d, edi; cchCount2
0x14006b5c1  lea     r8, ?c_textSuggestionsCap@@3QBGB; "textSuggestions"
0x14006b5c8  mov     rcx, rbx; lpString1
0x14006b5cb  call    cs:__imp_CompareStringOrdinal
0x14006b5d1  cmp     eax, 2
0x14006b5d4  jnz     loc_14006B75F
0x14006b5da  lea     rdx, aVendorMsftSecu_2; "./Vendor/MSFT/SecureAssessment/AllowTex"...
0x14006b5e1  lea     rcx, [rsp+0F8h+var_C8]
0x14006b5e6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006b5eb  mov     rdx, rax
0x14006b5ee  lea     rcx, [rsp+0F8h+arg_18]
0x14006b5f6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x14006b5fb  lea     rcx, [rsp+0F8h+var_C8]
0x14006b600  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006b605  mov     [rsp+0F8h+var_C0], r15
0x14006b60a  mov     rdi, [rsp+0F8h+arg_10]
0x14006b612  mov     rax, [rdi]
0x14006b615  mov     rbx, [rax+50h]
0x14006b619  lea     rcx, [rsp+0F8h+var_C0]
0x14006b61e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006b623  lea     r8, [rsp+0F8h+var_C0]
0x14006b628  mov     rdx, [rsp+0F8h+arg_18]
0x14006b630  mov     rcx, rdi
0x14006b633  mov     rax, rbx
0x14006b636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b63b  mov     rcx, [rsp+0F8h]; this
0x14006b643  test    eax, eax
0x14006b645  jns     short loc_14006B65B
0x14006b647  mov     r9d, eax; char *
0x14006b64a  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b651  mov     edx, 54h ; 'T'; void *
0x14006b656  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b65b  mov     rcx, [rsp+0F8h+var_C0]
0x14006b660  movups  xmm0, xmmword ptr [rsp+0F8h+pvarg]
0x14006b668  movaps  [rsp+0F8h+var_48], xmm0
0x14006b670  movsd   xmm1, qword ptr [rsp+0F8h+pvarg+10h]
0x14006b679  movsd   [rsp+0F8h+var_38], xmm1
0x14006b682  mov     rax, [rcx]
0x14006b685  mov     r8d, 5
0x14006b68b  lea     rdx, [rsp+0F8h+var_48]
0x14006b693  mov     rax, [rax+60h]
0x14006b697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b69c  mov     rcx, [rsp+0F8h]; this
0x14006b6a4  test    eax, eax
0x14006b6a6  jns     short loc_14006B6BC
0x14006b6a8  mov     r9d, eax; char *
0x14006b6ab  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b6b2  mov     edx, 55h ; 'U'; void *
0x14006b6b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b6bc  mov     rcx, [rsp+0F8h+arg_10]
0x14006b6c4  mov     rax, [rcx]
0x14006b6c7  mov     rax, [rax+18h]
0x14006b6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b6d0  mov     rcx, [rsp+0F8h]; this
0x14006b6d8  test    eax, eax
0x14006b6da  jns     short loc_14006B6F1
0x14006b6dc  mov     r9d, eax; char *
0x14006b6df  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b6e6  mov     edx, 58h ; 'X'; void *
0x14006b6eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b6f1  lea     rcx, [rsp+0F8h+var_C0]
0x14006b6f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006b6fb  nop
0x14006b6fc  lea     rcx, [rsp+0F8h+arg_18]
0x14006b704  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006b709  nop
0x14006b70a  lea     rcx, [rsp+0F8h+pvarg]; this
0x14006b712  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14006b717  nop
0x14006b718  lea     rcx, [rsp+0F8h+var_98]
0x14006b71d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006b722  nop
0x14006b723  lea     rcx, [rsp+0F8h+pszDest]
0x14006b728  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006b72d  nop
0x14006b72e  lea     rcx, [rsp+0F8h+var_60]; this
0x14006b736  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14006b73b  nop
0x14006b73c  lea     rcx, [rsp+0F8h+var_80]
0x14006b741  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006b746  nop
0x14006b747  lea     rcx, [rsp+0F8h+arg_10]
0x14006b74f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```

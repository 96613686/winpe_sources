# RetailDemoUtil::PolicyManagerConfigure(RetailDemoUtil::PolicyType,ushort const *,ushort const *,tagVARIANT const &)

- ea: `0x1800314dc`
- end: `0x180031bf8`
- name: `?PolicyManagerConfigure@RetailDemoUtil@@YAXW4PolicyType@1@PEBG1AEBUtagVARIANT@@@Z`
- size: `1820`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022bfc`

## callees

- `0x180003390`
- `0x1800068f0`
- `0x180007114`
- `0x180008bbc`
- `0x18001094c`
- `0x18001ff9c`
- `0x180022298`
- `0x18002231c`
- `0x180022448`
- `0x18002315c`
- `0x1800237f0`
- `0x18002dfb0`
- `0x18002ec68`
- `0x180030f00`
- `0x1800314dc`
- `0x180050010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800316fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800316fe`
- `OLEAUT32!__imp_VariantClear` at `0x180031ba9`
- `OLEAUT32!__imp_VariantClear` at `0x180031bbf`
- `OLEAUT32!__imp_VariantClear` at `0x180031ba9`
- `OLEAUT32!__imp_VariantClear` at `0x180031bbf`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x180031673`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x180031673`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003157a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003157a`
- `dmEnrollEngine!BeginEnrollmentScope` at `0x180031642`
- `dmEnrollEngine!BeginEnrollmentScope` at `0x180031642`

## string_xrefs

- `0x180031537`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18003158b`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800315be`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18003161c`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031653`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031684`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800316b4`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18003175e`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800317a8`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800317fe`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031853`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800318e8`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031973`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031a07`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031a52`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031ac2`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031af5`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031b51`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031b7f`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031ada`: `./Vendor/MSFT/Policy/Config/%s/%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall RetailDemoUtil::PolicyManagerConfigure(int a1, __int64 a2, __int64 a3, _WORD *a4)
{
  int v6; // ecx
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  BSTR *bstr; // rbx
  OLECHAR *v15; // rsi
  OLECHAR *v16; // rdi
  int v17; // eax
  int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  LPVOID v21; // rdi
  __int64 (__fastcall *v22)(LPVOID, _QWORD, __int64 *); // rbx
  _QWORD *v23; // rax
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64, VARIANTARG *); // rbx
  __int64 v27; // rdx
  __int64 v28; // r8
  _QWORD *v29; // rax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rbx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  const wchar_t *v38; // rsi
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, _QWORD, __int64, VARIANTARG *); // rbx
  _QWORD *v41; // rax
  int v42; // eax
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  LPVOID v50; // rdi
  __int64 (__fastcall *v51)(LPVOID, _QWORD, __int64 *); // rbx
  _QWORD *v52; // rax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r8
  int ppv; // [rsp+20h] [rbp-E0h]
  int *ppva; // [rsp+20h] [rbp-E0h]
  LPVOID v64; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v65; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v66; // [rsp+40h] [rbp-C0h] BYREF
  int v67[2]; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v69; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v70; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v71; // [rsp+88h] [rbp-78h] BYREF
  __int64 v72; // [rsp+90h] [rbp-70h]
  __int64 v73; // [rsp+98h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v75; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v76; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v77[40]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  if ( *a4 > 0x13u || (v6 = 524552, !_bittest(&v6, (unsigned __int16)*a4)) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)0x80070057LL,
      ppv);
  v64 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, a2, a3);
  v8 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v64);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v8,
      (int)ppva);
  v75.vt = 0;
  v9 = wil::Variant::SetString((wil::Variant *)&v75, L"{d1957e49-8dd3-4970-bd7c-f8e6957612bf}");
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v9,
      (int)ppva);
  wil::make_bstr(bstrString, L"OMADM::ServerID");
  v69 = v75;
  v10 = (*(__int64 (__fastcall **)(LPVOID, BSTR, VARIANTARG *))(*(_QWORD *)v64 + 104LL))(v64, bstrString[0], &v69);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v10,
      (int)ppva);
  v76 = 0;
  v11 = BeginEnrollmentScope(8, &v76);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v11,
      (int)ppva);
  v12 = SHStringFromGUIDW(&v76, v77, 39);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v12,
      (int)ppva);
  pvarg.vt = 0;
  v13 = wil::Variant::SetString((wil::Variant *)&pvarg, v77);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v13,
      (int)ppva);
  bstr = (BSTR *)wil::make_bstr(&v65, L"OMADM::AccountID");
  if ( bstrString != bstr )
  {
    v15 = *bstr;
    v16 = bstrString[0];
    if ( bstrString[0] )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v67);
      SysFreeString(v16);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v67);
    }
    bstrString[0] = v15;
    *bstr = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
  v69 = pvarg;
  v17 = (*(__int64 (__fastcall **)(LPVOID, BSTR, VARIANTARG *))(*(_QWORD *)v64 + 104LL))(v64, bstrString[0], &v69);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v17,
      (int)ppva);
  v71 = 0;
  v72 = 0;
  v73 = 0;
  if ( a1 )
  {
    if ( (unsigned int)(a1 - 1) >= 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)0x80070057LL,
        (int)ppva);
    v65 = 0;
    v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(&v71, 53);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FA,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v18,
        (int)ppva);
    StringCchCopyNW(v71, 0x36u, L"./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions", 0x35u);
    v72 = 53;
    v21 = v64;
    v22 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v64 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v19, v20);
    v23 = (_QWORD *)wil::make_bstr(&v66, v71);
    v24 = v22(v21, *v23, &v65);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v24,
        (int)ppva);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
    *(_QWORD *)v67 = 0;
    v25 = v65;
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)v65 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v67, v27, v28);
    v29 = (_QWORD *)wil::make_bstr(&v66, L"RetailDemo");
    v69.vt = 0;
    v30 = v26(v25, *v29, 8, &v69);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v30,
        (int)v67);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v64 + 24LL))(v64);
    v33 = v65;
    v34 = *(_QWORD *)v67;
    if ( v65 != *(_QWORD *)v67 )
    {
      if ( *(_QWORD *)v67 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v67 + 8LL))(*(_QWORD *)v67);
        v33 = v65;
      }
      v66 = v33;
      v65 = v34;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v31, v32);
    }
    v35 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
            &v71,
            L"/%s",
            L"RetailDemo");
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v35,
        (int)v67);
    v38 = L"StoreApps";
    if ( a1 != 1 )
      v38 = L"Exe";
    v39 = v65;
    v40 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)v65 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v67, v36, v37);
    v41 = (_QWORD *)wil::make_bstr(&v66, v38);
    v69.vt = 0;
    ppva = v67;
    v42 = v40(v39, *v41, 8, &v69);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x206,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v42,
        (int)v67);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v64 + 24LL))(v64);
    v43 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
            &v71,
            L"/%s/Policy",
            v38);
    if ( v43 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20A,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v43,
        (int)v67);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v67, v44, v45);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v46, v47);
  }
  else
  {
    v54 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &v71,
            L"./Vendor/MSFT/Policy/Config/%s/%s",
            0,
            0);
    if ( v54 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v54,
        (int)ppva);
  }
  v70 = 0;
  v50 = v64;
  v51 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v64 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70, v48, v49);
  v52 = (_QWORD *)wil::make_bstr(&v66, v71);
  v53 = v51(v50, *v52, &v70);
  if ( v53 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x215,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v53,
      (int)ppva);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
  v69 = *(VARIANTARG *)a4;
  v55 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, bool))(*(_QWORD *)v70 + 96LL))(v70, &v69, *a4 == 8);
  if ( v55 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x219,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v55,
      (int)ppva);
  v56 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v64 + 24LL))(v64);
  if ( v56 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v56,
      (int)ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70, v57, v58);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v71);
  VariantClear(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(bstrString);
  VariantClear(&v75);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, v59, v60);
}

```

## disassembly

```asm
0x1800314dc  mov     [rsp-8+arg_0], rbx
0x1800314e1  mov     [rsp-8+arg_8], rsi
0x1800314e6  push    rbp
0x1800314e7  push    rdi
0x1800314e8  push    r13
0x1800314ea  push    r14
0x1800314ec  push    r15
0x1800314ee  lea     rbp, [rsp-40h]
0x1800314f3  sub     rsp, 140h
0x1800314fa  mov     rax, cs:__security_cookie
0x180031501  xor     rax, rsp
0x180031504  mov     [rbp+60h+var_30], rax
0x180031508  mov     r15, r9
0x18003150b  mov     r14d, ecx
0x18003150e  cmp     word ptr [r9], 13h
0x180031513  ja      short loc_180031527
0x180031515  movzx   eax, word ptr [r9]
0x180031519  mov     ecx, 80108h
0x18003151e  bt      ecx, eax
0x180031521  jnb     short loc_180031527
0x180031523  mov     al, 1
0x180031525  jmp     short loc_180031529
0x180031527  xor     al, al
0x180031529  mov     rcx, [rbp+68h]; this
0x18003152d  test    al, al
0x18003152f  jnz     short loc_180031549
0x180031531  mov     r9d, 80070057h; char *
0x180031537  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003153e  mov     edx, 1D8h; void *
0x180031543  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031549  mov     [rsp+160h+var_130], 0
0x180031552  lea     rcx, [rsp+160h+var_130]
0x180031557  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003155c  lea     rax, [rsp+160h+var_130]
0x180031561  mov     [rsp+160h+ppv], rax; int
0x180031566  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18003156d  xor     edx, edx; pUnkOuter
0x18003156f  lea     r8d, [rdx+1]; dwClsContext
0x180031573  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18003157a  call    cs:__imp_CoCreateInstance
0x180031580  mov     rcx, [rbp+68h]; this
0x180031584  test    eax, eax
0x180031586  jns     short loc_18003159D
0x180031588  mov     r9d, eax; char *
0x18003158b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180031592  mov     edx, 1DBh; void *
0x180031597  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003159d  xor     eax, eax
0x18003159f  mov     word ptr [rbp+60h+var_A8], ax
0x1800315a3  lea     rdx, aD1957e498dd349; "{d1957e49-8dd3-4970-bd7c-f8e6957612bf}"
0x1800315aa  lea     rcx, [rbp+60h+var_A8]; this
0x1800315ae  call    ?SetString@Variant@wil@@QEAAJPEBG@Z; wil::Variant::SetString(ushort const *)
0x1800315b3  mov     rcx, [rbp+68h]; this
0x1800315b7  test    eax, eax
0x1800315b9  jns     short loc_1800315D0
0x1800315bb  mov     r9d, eax; char *
0x1800315be  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800315c5  mov     edx, 1DFh; void *
0x1800315ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800315d0  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x1800315d7  lea     rcx, [rsp+160h+bstrString]
0x1800315dc  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800315e1  nop
0x1800315e2  mov     rcx, [rsp+160h+var_130]
0x1800315e7  movups  xmm0, xmmword ptr [rbp+60h+var_A8]
0x1800315eb  movaps  [rsp+160h+var_100], xmm0
0x1800315f0  movsd   xmm1, qword ptr [rbp+60h+var_A8+10h]
0x1800315f5  movsd   [rsp+160h+var_F0], xmm1
0x1800315fb  mov     rax, [rcx]
0x1800315fe  lea     r8, [rsp+160h+var_100]
0x180031603  mov     rdx, [rsp+160h+bstrString]
0x180031608  mov     rax, [rax+68h]
0x18003160c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031611  mov     rcx, [rbp+68h]; this
0x180031615  test    eax, eax
0x180031617  jns     short loc_18003162E
0x180031619  mov     r9d, eax; char *
0x18003161c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180031623  mov     edx, 1E1h; void *
0x180031628  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003162e  xorps   xmm0, xmm0
0x180031631  movups  [rbp+60h+var_90], xmm0
0x180031635  lea     rdx, [rbp+60h+var_90]
0x180031639  mov     r13d, 8
0x18003163f  mov     ecx, r13d
0x180031642  call    cs:__imp_BeginEnrollmentScope
0x180031648  mov     rcx, [rbp+68h]; this
0x18003164c  test    eax, eax
0x18003164e  jns     short loc_180031665
0x180031650  mov     r9d, eax; char *
0x180031653  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003165a  mov     edx, 1E5h; void *
0x18003165f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031665  mov     r8d, 27h ; '''
0x18003166b  lea     rdx, [rbp+60h+var_80]
0x18003166f  lea     rcx, [rbp+60h+var_90]
0x180031673  call    cs:__imp_SHStringFromGUIDW
0x180031679  mov     rcx, [rbp+68h]; this
0x18003167d  test    eax, eax
0x18003167f  jns     short loc_180031696
0x180031681  mov     r9d, eax; char *
0x180031684  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003168b  mov     edx, 1E7h; void *
0x180031690  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031696  xor     eax, eax
0x180031698  mov     word ptr [rbp+60h+pvarg], ax
0x18003169c  lea     rdx, [rbp+60h+var_80]; unsigned __int16 *
0x1800316a0  lea     rcx, [rbp+60h+pvarg]; this
0x1800316a4  call    ?SetString@Variant@wil@@QEAAJPEBG@Z; wil::Variant::SetString(ushort const *)
0x1800316a9  mov     rcx, [rbp+68h]; this
0x1800316ad  test    eax, eax
0x1800316af  jns     short loc_1800316C6
0x1800316b1  mov     r9d, eax; char *
0x1800316b4  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800316bb  mov     edx, 1E9h; void *
0x1800316c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800316c6  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x1800316cd  lea     rcx, [rsp+160h+var_128]
0x1800316d2  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800316d7  mov     rbx, rax
0x1800316da  lea     rax, [rsp+160h+bstrString]
0x1800316df  cmp     rax, rbx
0x1800316e2  jz      short loc_18003171A
0x1800316e4  mov     rsi, [rbx]
0x1800316e7  mov     rdi, [rsp+160h+bstrString]
0x1800316ec  test    rdi, rdi
0x1800316ef  jz      short loc_18003170E
0x1800316f1  lea     rcx, [rsp+160h+var_118]; this
0x1800316f6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800316fb  mov     rcx, rdi; bstrString
0x1800316fe  call    cs:__imp_SysFreeString
0x180031704  lea     rcx, [rsp+160h+var_118]; this
0x180031709  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003170e  mov     [rsp+160h+bstrString], rsi
0x180031713  mov     qword ptr [rbx], 0
0x18003171a  lea     rcx, [rsp+160h+var_128]
0x18003171f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031724  mov     rcx, [rsp+160h+var_130]
0x180031729  movups  xmm0, xmmword ptr [rbp+60h+pvarg]
0x18003172d  movaps  [rsp+160h+var_100], xmm0
0x180031732  movsd   xmm1, qword ptr [rbp+60h+pvarg+10h]
0x180031737  movsd   [rsp+160h+var_F0], xmm1
0x18003173d  mov     rax, [rcx]
0x180031740  lea     r8, [rsp+160h+var_100]
0x180031745  mov     rdx, [rsp+160h+bstrString]
0x18003174a  mov     rax, [rax+68h]
0x18003174e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031753  mov     rcx, [rbp+68h]; this
0x180031757  test    eax, eax
0x180031759  jns     short loc_180031770
0x18003175b  mov     r9d, eax; char *
0x18003175e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180031765  mov     edx, 1EBh; void *
0x18003176a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031770  mov     [rbp+60h+var_D8], 0
0x180031778  mov     [rbp+60h+var_D0], 0
0x180031780  mov     [rbp+60h+var_C8], 0
0x180031788  mov     ecx, r14d
0x18003178b  test    r14d, r14d
0x18003178e  jz      loc_180031AD4
0x180031794  sub     ecx, 1
0x180031797  jz      short loc_1800317BA
0x180031799  cmp     ecx, 1
0x18003179c  jz      short loc_1800317BA
0x18003179e  mov     rcx, [rbp+68h]; this
0x1800317a2  mov     r9d, 80070057h; char *
0x1800317a8  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800317af  mov     edx, 20Fh; void *
0x1800317b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800317ba  mov     [rsp+160h+var_128], 0
0x1800317c3  mov     edi, 35h ; '5'
0x1800317c8  mov     edx, edi
0x1800317ca  lea     rcx, [rbp+60h+var_D8]
0x1800317ce  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800317d3  mov     ebx, eax
0x1800317d5  test    eax, eax
0x1800317d7  js      short loc_1800317F3
0x1800317d9  mov     r9d, edi; unsigned __int64
0x1800317dc  lea     r8, aVendorMsftAppl; "./Vendor/MSFT/AppLocker/ApplicationLaun"...
0x1800317e3  lea     edx, [rdi+1]; unsigned __int64
0x1800317e6  mov     rcx, [rbp+60h+var_D8]; unsigned __int16 *
0x1800317ea  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800317ef  mov     [rbp+60h+var_D0], rdi
0x1800317f3  mov     rcx, [rbp+68h]; this
0x1800317f7  test    ebx, ebx
0x1800317f9  jns     short loc_180031810
0x1800317fb  mov     r9d, ebx; char *
0x1800317fe  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180031805  mov     edx, 1FAh; void *
0x18003180a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031810  mov     rdi, [rsp+160h+var_130]
0x180031815  mov     rax, [rdi]
0x180031818  mov     rbx, [rax+50h]
0x18003181c  lea     rcx, [rsp+160h+var_128]
0x180031821  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031826  mov     rdx, [rbp+60h+var_D8]
0x18003182a  lea     rcx, [rsp+160h+var_120]
0x18003182f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180031834  nop
0x180031835  lea     r8, [rsp+160h+var_128]
0x18003183a  mov     rdx, [rax]
0x18003183d  mov     rcx, rdi
0x180031840  mov     rax, rbx
0x180031843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031848  mov     rcx, [rbp+68h]; this
0x18003184c  test    eax, eax
0x18003184e  jns     short loc_180031865
0x180031850  mov     r9d, eax; char *
0x180031853  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003185a  mov     edx, 1FBh; void *
0x18003185f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031865  lea     rcx, [rsp+160h+var_120]
0x18003186a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003186f  mov     qword ptr [rsp+160h+var_118], 0
0x180031878  mov     rdi, [rsp+160h+var_128]
0x18003187d  mov     rax, [rdi]
0x180031880  mov     rbx, [rax+18h]
0x180031884  lea     rcx, [rsp+160h+var_118]
0x180031889  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003188e  lea     rdx, aRetaildemo; "RetailDemo"
0x180031895  lea     rcx, [rsp+160h+var_120]
0x18003189a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18003189f  nop
0x1800318a0  xor     edx, edx
0x1800318a2  mov     word ptr [rsp+160h+var_100], dx
0x1800318a7  movups  xmm0, [rsp+160h+var_100+2]
0x1800318ac  movups  [rsp+160h+var_100+2], xmm0
0x1800318b1  movsd   xmm1, [rsp+160h+var_F0]
0x1800318b7  movsd   [rsp+160h+var_F0], xmm1
0x1800318bd  lea     rcx, [rsp+160h+var_118]
0x1800318c2  mov     [rsp+160h+ppv], rcx; int
0x1800318c7  lea     r9, [rsp+160h+var_100]
0x1800318cc  mov     r8d, r13d
0x1800318cf  mov     rdx, [rax]
0x1800318d2  mov     rcx, rdi
0x1800318d5  mov     rax, rbx
0x1800318d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318dd  mov     rcx, [rbp+68h]; this
0x1800318e1  test    eax, eax
0x1800318e3  jns     short loc_1800318FA
0x1800318e5  mov     r9d, eax; char *
0x1800318e8  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800318ef  mov     edx, 1FFh; void *
0x1800318f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800318fa  lea     rcx, [rsp+160h+var_120]
0x1800318ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031904  mov     rcx, [rsp+160h+var_130]
0x180031909  mov     rax, [rcx]
0x18003190c  mov     rax, [rax+18h]
0x180031910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031915  mov     rax, [rsp+160h+var_128]
0x18003191a  mov     rbx, qword ptr [rsp+160h+var_118]
0x18003191f  cmp     rax, rbx
0x180031922  jz      short loc_180031951
0x180031924  test    rbx, rbx
0x180031927  jz      short loc_18003193D
0x180031929  mov     rax, [rbx]
0x18003192c  mov     rcx, rbx
0x18003192f  mov     rax, [rax+8]
0x180031933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031938  mov     rax, [rsp+160h+var_128]
0x18003193d  mov     [rsp+160h+var_120], rax
0x180031942  mov     [rsp+160h+var_128], rbx
0x180031947  lea     rcx, [rsp+160h+var_120]
0x18003194c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031951  lea     r8, aRetaildemo; "RetailDemo"
0x180031958  lea     rdx, aS; "/%s"
0x18003195f  lea     rcx, [rbp+60h+var_D8]
0x180031963  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180031968  mov     rcx, [rbp+68h]; this
0x18003196c  test    eax, eax
0x18003196e  jns     short loc_180031985
0x180031970  mov     r9d, eax; char *
0x180031973  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003197a  mov     edx, 202h; void *
0x18003197f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031985  lea     rax, aExe; "Exe"
0x18003198c  lea     rsi, aStoreapps; "StoreApps"
0x180031993  cmp     r14d, 1
0x180031997  cmovnz  rsi, rax
0x18003199b  mov     rdi, [rsp+160h+var_128]
0x1800319a0  mov     rax, [rdi]
0x1800319a3  mov     rbx, [rax+18h]
0x1800319a7  lea     rcx, [rsp+160h+var_118]
0x1800319ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800319b1  mov     rdx, rsi
0x1800319b4  lea     rcx, [rsp+160h+var_120]
0x1800319b9  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800319be  nop
0x1800319bf  xor     edx, edx
0x1800319c1  mov     word ptr [rsp+160h+var_100], dx
0x1800319c6  movups  xmm0, [rsp+160h+var_100+2]
0x1800319cb  movups  [rsp+160h+var_100+2], xmm0
0x1800319d0  movsd   xmm1, [rsp+160h+var_F0]
0x1800319d6  movsd   [rsp+160h+var_F0], xmm1
0x1800319dc  lea     rcx, [rsp+160h+var_118]
0x1800319e1  mov     [rsp+160h+ppv], rcx; int
0x1800319e6  lea     r9, [rsp+160h+var_100]
0x1800319eb  mov     r8d, r13d
0x1800319ee  mov     rdx, [rax]
  ... truncated ...
```

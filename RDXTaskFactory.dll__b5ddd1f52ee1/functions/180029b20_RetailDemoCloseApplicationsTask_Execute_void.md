# RetailDemoCloseApplicationsTask::Execute(void)

- ea: `0x180029b20`
- end: `0x180029eb6`
- name: `?Execute@RetailDemoCloseApplicationsTask@@MEAAXXZ`
- size: `918`
- prototype: `void __fastcall(RetailDemoCloseApplicationsTask *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180006450`
- `0x180008bbc`
- `0x18000e0f0`
- `0x18000e330`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x1800181b0`
- `0x180028ccc`
- `0x180028e14`
- `0x18002941c`
- `0x1800297d0`
- `0x180029b20`
- `0x18002e5b8`
- `0x18002fc68`
- `0x180050010`

## string_xrefs

- `0x180029b93`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029bcb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029c02`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029d92`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029da7`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029dbc`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029dd1`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029dfe`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029e48`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall RetailDemoCloseApplicationsTask::Execute(RetailDemoCloseApplicationsTask *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 **); // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  unsigned int i; // esi
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  _QWORD *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  int v29; // [rsp+20h] [rbp-99h]
  unsigned int v30; // [rsp+30h] [rbp-89h] BYREF
  int v31; // [rsp+34h] [rbp-85h] BYREF
  int v32; // [rsp+38h] [rbp-81h] BYREF
  __int64 v33; // [rsp+40h] [rbp-79h] BYREF
  __int64 *v34; // [rsp+48h] [rbp-71h] BYREF
  __int64 v35; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v36; // [rsp+58h] [rbp-61h] BYREF
  __int64 v37; // [rsp+60h] [rbp-59h] BYREF
  __int64 v38; // [rsp+68h] [rbp-51h] BYREF
  void *v39; // [rsp+70h] [rbp-49h] BYREF
  __int64 v40; // [rsp+78h] [rbp-41h]
  __int64 v41; // [rsp+80h] [rbp-39h]
  _QWORD v42[7]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD *v43; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  std::vector<std::wstring>::vector<std::wstring>(&v39);
  LOBYTE(v2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
    v2);
  v36 = 0;
  v3 = *((_QWORD *)this + 8);
  v4 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v3 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36, v5, v6);
  v7 = v4(v3, &v36);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v7,
      v29);
  v34 = 0;
  v8 = *v36;
  v34 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v8 + 88))(v36, &v34);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v9,
      v29);
  v30 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v34 + 24))(v34, &v30);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v10,
      v29);
  v32 = 0;
  for ( i = 0; i < v30; ++i )
  {
    v33 = 0;
    v12 = *v34;
    v33 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v12 + 32))(
            v34,
            i,
            &GUID_368af30e_7a5f_4cca_a390_c844bb9ade09,
            &v33);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
        (const char *)(unsigned int)v13,
        v29);
    v31 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 56LL))(v33, &v31);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
        (const char *)(unsigned int)v14,
        v29);
    if ( v31 )
    {
      v35 = 0;
      v15 = v33;
      v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 24LL);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v35,
        0);
      v17 = v16(v15, &v35);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
          (const char *)(unsigned int)v17,
          v29);
      v38 = 0;
      v42[0] = off_180052D48;
      v42[1] = &v32;
      v42[2] = &v35;
      v42[3] = &v38;
      v43 = v42;
      RetailDemoUtil::ExecuteAsDemoUser(v42);
      if ( v43 )
      {
        v18 = v42;
        LOBYTE(v18) = v43 != v42;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v43 + 32LL))(v43, v18);
      }
      if ( v32 >= 0 )
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (__int64 *)&v39,
          &v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
    }
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v33);
  }
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36, v19, v20);
  RetailDemoUtil::GetUserAgent(&v37, 0);
  v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 216LL))(v37);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v21,
      v29);
  v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 64LL))(v37);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v22,
      v29);
  LOBYTE(v23) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
    v23);
  v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 48LL))(v37, (v40 - (__int64)v39) >> 3);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v24,
      v29);
  RetailDemoCloseApplicationsTask::CloseModernApps(this, v25, v26);
  RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<19,long>(0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37, v27, v28);
  if ( v39 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
      (__int64)v39,
      v40);
    std::_Deallocate<16>(v39, (v41 - (_QWORD)v39) & 0xFFFFFFFFFFFFFFF8uLL);
  }
}

```

## disassembly

```asm
0x180029b20  push    rbp
0x180029b22  push    rbx
0x180029b23  push    rsi
0x180029b24  push    rdi
0x180029b25  push    r14
0x180029b27  push    r15
0x180029b29  lea     rbp, [rsp-2Fh]
0x180029b2e  sub     rsp, 0E8h
0x180029b35  mov     rax, cs:__security_cookie
0x180029b3c  xor     rax, rsp
0x180029b3f  mov     [rbp+57h+var_40], rax
0x180029b43  mov     r14, rcx
0x180029b46  lea     rcx, [rbp+57h+var_A0]
0x180029b4a  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180029b4f  nop
0x180029b50  mov     dl, 1
0x180029b52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x180029b59  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029b5e  xor     r15d, r15d
0x180029b61  mov     [rbp+57h+var_B8], r15
0x180029b65  mov     rdi, [r14+40h]
0x180029b69  mov     rax, [rdi]
0x180029b6c  mov     rbx, [rax+60h]
0x180029b70  lea     rcx, [rbp+57h+var_B8]
0x180029b74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029b79  lea     rdx, [rbp+57h+var_B8]
0x180029b7d  mov     rcx, rdi
0x180029b80  mov     rax, rbx
0x180029b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b88  mov     rcx, [rbp+5Fh]; this
0x180029b8c  test    eax, eax
0x180029b8e  jns     short loc_180029BA4
0x180029b90  mov     r9d, eax; char *
0x180029b93  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029b9a  lea     edx, [r15+2Ch]; void *
0x180029b9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029ba4  mov     [rbp+57h+var_C8], r15
0x180029ba8  mov     rcx, [rbp+57h+var_B8]
0x180029bac  mov     rax, [rcx]
0x180029baf  mov     [rbp+57h+var_C8], r15
0x180029bb3  lea     rdx, [rbp+57h+var_C8]
0x180029bb7  mov     rax, [rax+58h]
0x180029bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bc0  mov     rcx, [rbp+5Fh]; this
0x180029bc4  test    eax, eax
0x180029bc6  jns     short loc_180029BDD
0x180029bc8  mov     r9d, eax; char *
0x180029bcb  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029bd2  mov     edx, 2Eh ; '.'; void *
0x180029bd7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029bdd  mov     [rsp+110h+var_E0], r15d
0x180029be2  mov     rcx, [rbp+57h+var_C8]
0x180029be6  mov     rax, [rcx]
0x180029be9  lea     rdx, [rsp+110h+var_E0]
0x180029bee  mov     rax, [rax+18h]
0x180029bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bf7  mov     rcx, [rbp+5Fh]; this
0x180029bfb  test    eax, eax
0x180029bfd  jns     short loc_180029C14
0x180029bff  mov     r9d, eax; char *
0x180029c02  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029c09  mov     edx, 30h ; '0'; void *
0x180029c0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029c14  mov     [rsp+110h+var_D8], r15d
0x180029c19  mov     esi, r15d
0x180029c1c  cmp     [rsp+110h+var_E0], r15d
0x180029c21  jbe     loc_180029D55
0x180029c27  mov     [rbp+57h+var_D0], r15
0x180029c2b  mov     rcx, [rbp+57h+var_C8]
0x180029c2f  mov     rax, [rcx]
0x180029c32  mov     [rbp+57h+var_D0], r15
0x180029c36  lea     r9, [rbp+57h+var_D0]
0x180029c3a  lea     r8, _GUID_368af30e_7a5f_4cca_a390_c844bb9ade09
0x180029c41  mov     edx, esi
0x180029c43  mov     rax, [rax+20h]
0x180029c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c4c  mov     rcx, [rbp+5Fh]; this
0x180029c50  test    eax, eax
0x180029c52  js      loc_180029DCE
0x180029c58  mov     [rsp+110h+var_DC], r15d
0x180029c5d  mov     rcx, [rbp+57h+var_D0]
0x180029c61  mov     rax, [rcx]
0x180029c64  lea     rdx, [rsp+110h+var_DC]
0x180029c69  mov     rax, [rax+38h]
0x180029c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c72  mov     rcx, [rbp+5Fh]; this
0x180029c76  test    eax, eax
0x180029c78  js      loc_180029DB9
0x180029c7e  cmp     [rsp+110h+var_DC], r15d
0x180029c83  jz      loc_180029D40
0x180029c89  mov     [rbp+57h+var_C0], r15
0x180029c8d  mov     rdi, [rbp+57h+var_D0]
0x180029c91  mov     rax, [rdi]
0x180029c94  mov     rbx, [rax+18h]
0x180029c98  xor     edx, edx
0x180029c9a  lea     rcx, [rbp+57h+var_C0]
0x180029c9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180029ca3  lea     rdx, [rbp+57h+var_C0]
0x180029ca7  mov     rcx, rdi
0x180029caa  mov     rax, rbx
0x180029cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cb2  mov     rcx, [rbp+5Fh]; this
0x180029cb6  test    eax, eax
0x180029cb8  js      loc_180029DA4
0x180029cbe  mov     [rbp+57h+var_A8], r15
0x180029cc2  lea     rax, off_180052D48
0x180029cc9  mov     [rbp+57h+var_80], rax
0x180029ccd  lea     rax, [rsp+110h+var_D8]
0x180029cd2  mov     [rbp+57h+var_78], rax
0x180029cd6  lea     rax, [rbp+57h+var_C0]
0x180029cda  mov     [rbp+57h+var_70], rax
0x180029cde  lea     rax, [rbp+57h+var_A8]
0x180029ce2  mov     [rbp+57h+var_68], rax
0x180029ce6  lea     rax, [rbp+57h+var_80]
0x180029cea  mov     [rbp+57h+var_48], rax
0x180029cee  lea     rcx, [rbp+57h+var_80]
0x180029cf2  call    ?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z; RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)
0x180029cf7  nop
0x180029cf8  mov     rcx, [rbp+57h+var_48]
0x180029cfc  test    rcx, rcx
0x180029cff  jz      short loc_180029D17
0x180029d01  mov     rax, [rcx]
0x180029d04  lea     rdx, [rbp+57h+var_80]
0x180029d08  cmp     rcx, rdx
0x180029d0b  setnz   dl
0x180029d0e  mov     rax, [rax+20h]
0x180029d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d17  cmp     [rsp+110h+var_D8], r15d
0x180029d1c  jl      short loc_180029D2C
0x180029d1e  lea     rdx, [rbp+57h+var_A8]
0x180029d22  lea     rcx, [rbp+57h+var_A0]
0x180029d26  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180029d2b  nop
0x180029d2c  lea     rcx, [rbp+57h+var_A8]
0x180029d30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029d35  nop
0x180029d36  lea     rcx, [rbp+57h+var_C0]
0x180029d3a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029d3f  nop
0x180029d40  lea     rcx, [rbp+57h+var_D0]
0x180029d44  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180029d49  inc     esi
0x180029d4b  cmp     esi, [rsp+110h+var_E0]
0x180029d4f  jb      loc_180029C27
0x180029d55  lea     rcx, [rbp+57h+var_C8]
0x180029d59  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180029d5e  nop
0x180029d5f  lea     rcx, [rbp+57h+var_B8]
0x180029d63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029d68  xor     edx, edx
0x180029d6a  lea     rcx, [rbp+57h+var_B0]
0x180029d6e  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x180029d73  nop
0x180029d74  mov     rcx, [rbp+57h+var_B0]
0x180029d78  mov     rax, [rcx]
0x180029d7b  mov     rax, [rax+0D8h]
0x180029d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d87  mov     rcx, [rbp+5Fh]; this
0x180029d8b  test    eax, eax
0x180029d8d  jns     short loc_180029DE3
0x180029d8f  mov     r9d, eax; char *
0x180029d92  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029d99  mov     edx, 4Dh ; 'M'; void *
0x180029d9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029da4  mov     r9d, eax; char *
0x180029da7  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029dae  mov     edx, 3Eh ; '>'; void *
0x180029db3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029db9  mov     r9d, eax; char *
0x180029dbc  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029dc3  mov     edx, 39h ; '9'; void *
0x180029dc8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029dce  mov     r9d, eax; char *
0x180029dd1  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029dd8  mov     edx, 36h ; '6'; void *
0x180029ddd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029de3  mov     rcx, [rbp+57h+var_B0]
0x180029de7  mov     rax, [rcx]
0x180029dea  mov     rax, [rax+40h]
0x180029dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029df3  mov     rcx, [rbp+5Fh]; this
0x180029df7  test    eax, eax
0x180029df9  jns     short loc_180029E10
0x180029dfb  mov     r9d, eax; char *
0x180029dfe  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029e05  mov     edx, 4Eh ; 'N'; void *
0x180029e0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029e10  mov     dl, 1
0x180029e12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x180029e19  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029e1e  mov     rcx, [rbp+57h+var_B0]
0x180029e22  mov     r8, [rbp+57h+var_A0]
0x180029e26  mov     rax, [rcx]
0x180029e29  mov     rdx, [rbp+57h+var_98]
0x180029e2d  sub     rdx, r8
0x180029e30  sar     rdx, 3
0x180029e34  mov     rax, [rax+30h]
0x180029e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e3d  mov     rcx, [rbp+5Fh]; this
0x180029e41  test    eax, eax
0x180029e43  jns     short loc_180029E5A
0x180029e45  mov     r9d, eax; char *
0x180029e48  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029e4f  mov     edx, 51h ; 'Q'; void *
0x180029e54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029e5a  mov     rcx, r14; this
0x180029e5d  call    ?CloseModernApps@RetailDemoCloseApplicationsTask@@AEAAXXZ; RetailDemoCloseApplicationsTask::CloseModernApps(void)
0x180029e62  xor     ecx, ecx
0x180029e64  call    ??$HandleEvent@$0BD@J@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@SAXJ@Z; RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<19,long>(long)
0x180029e69  nop
0x180029e6a  lea     rcx, [rbp+57h+var_B0]
0x180029e6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029e73  nop
0x180029e74  mov     rcx, [rbp+57h+var_A0]
0x180029e78  test    rcx, rcx
0x180029e7b  jz      short loc_180029E9A
0x180029e7d  mov     rdx, [rbp+57h+var_98]
0x180029e81  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x180029e86  mov     rcx, [rbp+57h+var_A0]
0x180029e8a  mov     rdx, [rbp+57h+var_90]
0x180029e8e  sub     rdx, rcx
0x180029e91  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180029e95  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180029e9a  mov     rcx, [rbp+57h+var_40]
0x180029e9e  xor     rcx, rsp; StackCookie
0x180029ea1  call    __security_check_cookie
0x180029ea6  add     rsp, 0E8h
0x180029ead  pop     r15
0x180029eaf  pop     r14
0x180029eb1  pop     rdi
0x180029eb2  pop     rsi
0x180029eb3  pop     rbx
0x180029eb4  pop     rbp
0x180029eb5  retn
```

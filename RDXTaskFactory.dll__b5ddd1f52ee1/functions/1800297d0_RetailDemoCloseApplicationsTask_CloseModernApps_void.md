# RetailDemoCloseApplicationsTask::CloseModernApps(void)

- ea: `0x1800297d0`
- end: `0x180029b16`
- name: `?CloseModernApps@RetailDemoCloseApplicationsTask@@AEAAXXZ`
- size: `838`
- prototype: `void __fastcall(RetailDemoCloseApplicationsTask *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029b20`

## callees

- `0x180003390`
- `0x18000649c`
- `0x180008bbc`
- `0x18000c168`
- `0x18000e3bc`
- `0x18001094c`
- `0x18001e55c`
- `0x180029258`
- `0x180029328`
- `0x1800294bc`
- `0x180029614`
- `0x1800297d0`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18002986a`
- `SHCORE!IUnknown_QueryService` at `0x180029a1b`
- `SHCORE!IUnknown_QueryService` at `0x18002986a`
- `SHCORE!IUnknown_QueryService` at `0x180029a1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029820`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029820`

## string_xrefs

- `0x180029831`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x18002987b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x1800298c3`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x1800298fb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029ac5`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029ada`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029aef`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`
- `0x180029b04`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskcloseapplications.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall RetailDemoCloseApplicationsTask::CloseModernApps(
        RetailDemoCloseApplicationsTask *this,
        __int64 a2,
        __int64 a3)
{
  HRESULT Instance; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  void *v10; // rdi
  __int64 (__fastcall *v11)(void *, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int i; // esi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, GUID *, __int64 **); // rbx
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  char v23; // al
  __int64 v24; // rcx
  bool v25; // bl
  __int64 v26; // rdx
  __int64 v27; // r8
  HRESULT v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  int ppv; // [rsp+20h] [rbp-69h]
  unsigned int v41; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v42; // [rsp+38h] [rbp-51h] BYREF
  __int64 v43; // [rsp+40h] [rbp-49h] BYREF
  IUnknown *punk; // [rsp+48h] [rbp-41h] BYREF
  void *v45; // [rsp+50h] [rbp-39h] BYREF
  void *ppvOut; // [rsp+58h] [rbp-31h] BYREF
  __int64 v47; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v48; // [rsp+68h] [rbp-21h] BYREF
  __int64 v49; // [rsp+70h] [rbp-19h] BYREF
  __int64 v50; // [rsp+78h] [rbp-11h]
  _QWORD v51[2]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v52[32]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  punk = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, a2, a3);
  Instance = CoCreateInstance(
               &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
               0,
               4u,
               &GUID_00000000_0000_0000_c000_000000000046,
               (LPVOID *)&punk);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v5, v6);
  v7 = IUnknown_QueryService(
         punk,
         (const GUID *const)&SID_ImmersiveApplicationArrayService,
         &GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a,
         &ppvOut);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v43 = 0;
  v10 = ppvOut;
  v11 = *(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvOut + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v8, v9);
  v12 = v11(v10, &v43);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v12,
      ppv);
  v41 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 24LL))(v43, &v41);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
      (const char *)(unsigned int)v13,
      ppv);
  RetailDemoCloseApplicationsTask::BuildModernAppExclusionList(this, v51);
  for ( i = 0; i < v41; ++i )
  {
    v42 = 0;
    v17 = v43;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 **))(*(_QWORD *)v43 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v14, v15);
    v19 = v18(v17, i, &GUID_8b14e88b_5663_4caf_b196_c31479262831, &v42);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
        (const char *)(unsigned int)v19,
        ppv);
    v47 = 0;
    v20 = *v42;
    v48 = &v47;
    v49 = 0;
    LOBYTE(v50) = 1;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v20 + 32))(v42, &v49);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
        (const char *)(unsigned int)v21,
        ppv);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v48);
    std::wstring::wstring((__int64)v52, v47);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
      v51,
      &v48,
      v52);
    v23 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
            v22,
            v50,
            v52);
    v24 = v51[0];
    if ( v23 )
      v24 = v50;
    v25 = v24 == v51[0];
    std::wstring::_Tidy_deallocate(v52);
    if ( v25 )
    {
      v45 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45, v26, v27);
      v28 = IUnknown_QueryService(punk, &stru_18005C5A0, &GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a, &v45);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x77,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
          (const char *)(unsigned int)v28,
          ppv);
      ppv = 6;
      v29 = (*(__int64 (__fastcall **)(void *, __int64 *, __int64))(*(_QWORD *)v45 + 32LL))(v45, v42, 10);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskcloseapplications.cpp",
          (const char *)(unsigned int)v29,
          6);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45, v30, v31);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v32, v33);
  }
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v34, v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v36, v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v38, v39);
}

```

## disassembly

```asm
0x1800297d0  push    rbp
0x1800297d2  push    rbx
0x1800297d3  push    rsi
0x1800297d4  push    rdi
0x1800297d5  lea     rbp, [rsp-3Fh]
0x1800297da  sub     rsp, 0C8h
0x1800297e1  mov     rax, cs:__security_cookie
0x1800297e8  xor     rax, rsp
0x1800297eb  mov     [rbp+57h+var_30], rax
0x1800297ef  mov     rsi, rcx
0x1800297f2  mov     [rbp+57h+punk], 0
0x1800297fa  lea     rcx, [rbp+57h+punk]
0x1800297fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029803  lea     rax, [rbp+57h+punk]
0x180029807  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x18002980c  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180029813  xor     edx, edx; pUnkOuter
0x180029815  lea     r8d, [rdx+4]; dwClsContext
0x180029819  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180029820  call    cs:__imp_CoCreateInstance
0x180029826  mov     rcx, [rbp+5Fh]; this
0x18002982a  test    eax, eax
0x18002982c  jns     short loc_180029843
0x18002982e  mov     r9d, eax; char *
0x180029831  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029838  mov     edx, 63h ; 'c'; void *
0x18002983d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029843  mov     [rbp+57h+ppvOut], 0
0x18002984b  lea     rcx, [rbp+57h+ppvOut]
0x18002984f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029854  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180029858  lea     r8, _GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a; riid
0x18002985f  lea     rdx, SID_ImmersiveApplicationArrayService; guidService
0x180029866  mov     rcx, [rbp+57h+punk]; punk
0x18002986a  call    cs:__imp_IUnknown_QueryService
0x180029870  mov     rcx, [rbp+5Fh]; this
0x180029874  test    eax, eax
0x180029876  jns     short loc_18002988D
0x180029878  mov     r9d, eax; char *
0x18002987b  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029882  mov     edx, 65h ; 'e'; void *
0x180029887  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002988d  mov     [rbp+57h+var_A0], 0
0x180029895  mov     rdi, [rbp+57h+ppvOut]
0x180029899  mov     rax, [rdi]
0x18002989c  mov     rbx, [rax+18h]
0x1800298a0  lea     rcx, [rbp+57h+var_A0]
0x1800298a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800298a9  lea     rdx, [rbp+57h+var_A0]
0x1800298ad  mov     rcx, rdi
0x1800298b0  mov     rax, rbx
0x1800298b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298b8  mov     rcx, [rbp+5Fh]; this
0x1800298bc  test    eax, eax
0x1800298be  jns     short loc_1800298D5
0x1800298c0  mov     r9d, eax; char *
0x1800298c3  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800298ca  mov     edx, 67h ; 'g'; void *
0x1800298cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800298d5  mov     [rbp+57h+var_B0], 0
0x1800298dc  mov     rcx, [rbp+57h+var_A0]
0x1800298e0  mov     rax, [rcx]
0x1800298e3  lea     rdx, [rbp+57h+var_B0]
0x1800298e7  mov     rax, [rax+18h]
0x1800298eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298f0  mov     rcx, [rbp+5Fh]; this
0x1800298f4  test    eax, eax
0x1800298f6  jns     short loc_18002990D
0x1800298f8  mov     r9d, eax; char *
0x1800298fb  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029902  mov     edx, 69h ; 'i'; void *
0x180029907  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002990d  lea     rdx, [rbp+57h+var_60]
0x180029911  mov     rcx, rsi
0x180029914  call    ?BuildModernAppExclusionList@RetailDemoCloseApplicationsTask@@AEAA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; RetailDemoCloseApplicationsTask::BuildModernAppExclusionList(void)
0x180029919  nop
0x18002991a  xor     esi, esi
0x18002991c  cmp     [rbp+57h+var_B0], esi
0x18002991f  jbe     loc_180029A83
0x180029925  mov     [rbp+57h+var_A8], 0
0x18002992d  mov     rdi, [rbp+57h+var_A0]
0x180029931  mov     rax, [rdi]
0x180029934  mov     rbx, [rax+20h]
0x180029938  lea     rcx, [rbp+57h+var_A8]
0x18002993c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029941  lea     r9, [rbp+57h+var_A8]
0x180029945  lea     r8, _GUID_8b14e88b_5663_4caf_b196_c31479262831
0x18002994c  mov     edx, esi
0x18002994e  mov     rcx, rdi
0x180029951  mov     rax, rbx
0x180029954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029959  mov     rcx, [rbp+5Fh]; this
0x18002995d  test    eax, eax
0x18002995f  js      loc_180029B01
0x180029965  mov     [rbp+57h+var_80], 0
0x18002996d  mov     rcx, [rbp+57h+var_A8]
0x180029971  mov     rax, [rcx]
0x180029974  lea     rdx, [rbp+57h+var_80]
0x180029978  mov     [rbp+57h+var_78], rdx
0x18002997c  mov     [rbp+57h+var_70], 0
0x180029984  mov     byte ptr [rbp+57h+var_68], 1
0x180029988  lea     rdx, [rbp+57h+var_70]
0x18002998c  mov     rax, [rax+20h]
0x180029990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029995  mov     rcx, [rbp+5Fh]; this
0x180029999  test    eax, eax
0x18002999b  js      loc_180029AEC
0x1800299a1  lea     rcx, [rbp+57h+var_78]
0x1800299a5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800299aa  mov     rdx, [rbp+57h+var_80]
0x1800299ae  lea     rcx, [rbp+57h+var_50]
0x1800299b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800299b7  lea     r8, [rbp+57h+var_50]
0x1800299bb  lea     rdx, [rbp+57h+var_78]
0x1800299bf  lea     rcx, [rbp+57h+var_60]
0x1800299c3  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800299c8  lea     r8, [rbp+57h+var_50]
0x1800299cc  mov     rdx, [rbp+57h+var_68]
0x1800299d0  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x1800299d5  mov     rcx, [rbp+57h+var_60]
0x1800299d9  test    al, al
0x1800299db  cmovnz  rcx, [rbp+57h+var_68]
0x1800299e0  cmp     rcx, [rbp+57h+var_60]
0x1800299e4  setz    bl
0x1800299e7  lea     rcx, [rbp+57h+var_50]
0x1800299eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800299f0  test    bl, bl
0x1800299f2  jz      short loc_180029A65
0x1800299f4  mov     [rbp+57h+var_90], 0
0x1800299fc  lea     rcx, [rbp+57h+var_90]
0x180029a00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a05  lea     r9, [rbp+57h+var_90]; ppvOut
0x180029a09  lea     r8, _GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a; riid
0x180029a10  lea     rdx, stru_18005C5A0; guidService
0x180029a17  mov     rcx, [rbp+57h+punk]; punk
0x180029a1b  call    cs:__imp_IUnknown_QueryService
0x180029a21  mov     rcx, [rbp+5Fh]; this
0x180029a25  test    eax, eax
0x180029a27  js      loc_180029AD7
0x180029a2d  mov     rcx, [rbp+57h+var_90]
0x180029a31  mov     rax, [rcx]
0x180029a34  mov     [rsp+0E0h+ppv], 6; int
0x180029a3c  mov     r9d, 2
0x180029a42  lea     r8d, [r9+8]
0x180029a46  mov     rdx, [rbp+57h+var_A8]
0x180029a4a  mov     rax, [rax+20h]
0x180029a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a53  mov     rcx, [rbp+5Fh]; this
0x180029a57  test    eax, eax
0x180029a59  js      short loc_180029AC2
0x180029a5b  lea     rcx, [rbp+57h+var_90]
0x180029a5f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a64  nop
0x180029a65  lea     rcx, [rbp+57h+var_80]
0x180029a69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029a6e  nop
0x180029a6f  lea     rcx, [rbp+57h+var_A8]
0x180029a73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a78  inc     esi
0x180029a7a  cmp     esi, [rbp+57h+var_B0]
0x180029a7d  jb      loc_180029925
0x180029a83  lea     rcx, [rbp+57h+var_60]
0x180029a87  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180029a8c  nop
0x180029a8d  lea     rcx, [rbp+57h+var_A0]
0x180029a91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a96  nop
0x180029a97  lea     rcx, [rbp+57h+ppvOut]
0x180029a9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029aa0  nop
0x180029aa1  lea     rcx, [rbp+57h+punk]
0x180029aa5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029aaa  mov     rcx, [rbp+57h+var_30]
0x180029aae  xor     rcx, rsp; StackCookie
0x180029ab1  call    __security_check_cookie
0x180029ab6  add     rsp, 0C8h
0x180029abd  pop     rdi
0x180029abe  pop     rsi
0x180029abf  pop     rbx
0x180029ac0  pop     rbp
0x180029ac1  retn
0x180029ac2  mov     r9d, eax; char *
0x180029ac5  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029acc  mov     edx, 78h ; 'x'; void *
0x180029ad1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029ad7  mov     r9d, eax; char *
0x180029ada  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029ae1  mov     edx, 77h ; 'w'; void *
0x180029ae6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029aec  mov     r9d, eax; char *
0x180029aef  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029af6  mov     edx, 73h ; 's'; void *
0x180029afb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029b01  mov     r9d, eax; char *
0x180029b04  lea     r8, aPcshellShellRe_29; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180029b0b  mov     edx, 70h ; 'p'; void *
0x180029b10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

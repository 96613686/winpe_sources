# RetailDemoUtil::DeleteScheduledTaskToRemoveRetailDemoFolders(void)

- ea: `0x18002e174`
- end: `0x18002e3c8`
- name: `?DeleteScheduledTaskToRemoveRetailDemoFolders@RetailDemoUtil@@YAXXZ`
- size: `596`
- prototype: `void __fastcall(RetailDemoUtil *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800125ac`
- `0x180026030`

## callees

- `0x180003390`
- `0x18000e330`
- `0x18001094c`
- `0x18002dfb0`
- `0x18002e174`
- `0x18002ec68`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002e28e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002e28e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e1c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e1c5`

## string_xrefs

- `0x18002e1d9`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002e265`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002e2a2`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002e309`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002e36b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall RetailDemoUtil::DeleteScheduledTaskToRemoveRetailDemoFolders(RetailDemoUtil *this)
{
  bool v1; // bl
  HRESULT v2; // eax
  int v3; // eax
  HRESULT v4; // eax
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[22]; // [rsp+52h] [rbp-AEh]
  _QWORD v15[3]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v16; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v17[22]; // [rsp+92h] [rbp-6Eh]
  __int16 v18; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v19[22]; // [rsp+B2h] [rbp-4Eh]
  WCHAR pszPathOut[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v10 = 0;
  v1 = 1;
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v10);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  LOWORD(v15[0]) = 0;
  *(_OWORD *)((char *)v15 + 2) = *(_OWORD *)v14;
  v15[2] = *(_QWORD *)&v14[14];
  v16 = 0;
  *(_OWORD *)v17 = *(_OWORD *)v14;
  *(_QWORD *)&v17[14] = *(_QWORD *)&v14[14];
  v18 = 0;
  *(_OWORD *)v19 = *(_OWORD *)v14;
  *(_QWORD *)&v19[14] = *(_QWORD *)&v14[14];
  v13 = 0;
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int16 *, __int16 *, __int16 *))(*(_QWORD *)v10 + 80LL))(
         v10,
         &v13,
         &v18,
         &v16);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v3,
      (int)v15);
  v4 = PathCchCombine(pszPathOut, 0x104u, L"Microsoft\\Windows", L"RetailDemo");
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v4,
      (int)v15);
  wil::make_bstr(&v12, pszPathOut);
  v9 = 0;
  v5 = *(_QWORD *)v10;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(v5 + 56))(v10, v12, &v9);
  if ( v6 != -2147024894 )
  {
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        (const char *)(unsigned int)v6,
        (int)v15);
    wil::make_bstr(&v11, L"CleanupOfflineContent");
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 120LL))(v9, v11, 0);
    if ( v7 > -2147024895 )
      v1 = (unsigned int)(v7 + 2147024892) <= 0x7FF8FFFB;
    if ( v1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        (const char *)(unsigned int)v7,
        (int)v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  }
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v9);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v10);
}

```

## disassembly

```asm
0x18002e174  mov     [rsp-8+arg_0], rbx
0x18002e179  push    rbp
0x18002e17a  lea     rbp, [rsp-1F0h]
0x18002e182  sub     rsp, 2F0h
0x18002e189  mov     rax, cs:__security_cookie
0x18002e190  xor     rax, rsp
0x18002e193  mov     [rbp+1F0h+var_10], rax
0x18002e19a  mov     [rsp+2F0h+var_2B8], 0
0x18002e1a3  lea     rax, [rsp+2F0h+var_2B8]
0x18002e1a8  mov     qword ptr [rsp+2F0h+ppv], rax; int
0x18002e1ad  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002e1b4  mov     ebx, 1
0x18002e1b9  mov     r8d, ebx; dwClsContext
0x18002e1bc  xor     edx, edx; pUnkOuter
0x18002e1be  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002e1c5  call    cs:__imp_CoCreateInstance
0x18002e1cb  mov     rcx, [rbp+1F8h]; this
0x18002e1d2  test    eax, eax
0x18002e1d4  jns     short loc_18002E1E9
0x18002e1d6  mov     r9d, eax; char *
0x18002e1d9  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e1e0  lea     edx, [rbx+5Eh]; void *
0x18002e1e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e1e9  mov     rcx, [rsp+2F0h+var_2B8]
0x18002e1ee  xor     eax, eax
0x18002e1f0  mov     word ptr [rsp+2F0h+var_280], ax
0x18002e1f5  movups  xmm1, xmmword ptr [rsp+2F0h+var_29E]
0x18002e1fa  movups  xmmword ptr [rsp+2F0h+var_280+2], xmm1
0x18002e1ff  movsd   xmm0, qword ptr [rsp+2F0h+var_29E+0Eh]
0x18002e205  movsd   qword ptr [rbp+1F0h+var_280+10h], xmm0
0x18002e20a  mov     [rbp+1F0h+var_260], ax
0x18002e20e  movups  xmmword ptr [rbp+1F0h+var_25E], xmm1
0x18002e212  movsd   qword ptr [rbp+1F0h+var_25E+0Eh], xmm0
0x18002e217  mov     [rbp+1F0h+var_240], ax
0x18002e21b  movups  xmmword ptr [rbp+1F0h+var_23E], xmm1
0x18002e21f  movsd   qword ptr [rbp+1F0h+var_23E+0Eh], xmm0
0x18002e224  mov     [rsp+2F0h+var_2A0], ax
0x18002e229  movups  xmmword ptr [rsp+2F0h+var_29E], xmm1
0x18002e22e  movsd   qword ptr [rsp+2F0h+var_29E+0Eh], xmm0
0x18002e234  mov     rax, [rcx]
0x18002e237  lea     rdx, [rsp+2F0h+var_280]
0x18002e23c  mov     qword ptr [rsp+2F0h+ppv], rdx; int
0x18002e241  lea     r9, [rbp+1F0h+var_260]
0x18002e245  lea     r8, [rbp+1F0h+var_240]
0x18002e249  lea     rdx, [rsp+2F0h+var_2A0]
0x18002e24e  mov     rax, [rax+50h]
0x18002e252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e257  mov     rcx, [rbp+1F8h]; this
0x18002e25e  test    eax, eax
0x18002e260  jns     short loc_18002E277
0x18002e262  mov     r9d, eax; char *
0x18002e265  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e26c  mov     edx, 61h ; 'a'; void *
0x18002e271  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e277  lea     r9, aRetaildemo_0; "RetailDemo"
0x18002e27e  lea     r8, pszPathIn; "Microsoft\\Windows"
0x18002e285  mov     edx, 104h; cchPathOut
0x18002e28a  lea     rcx, [rbp+1F0h+pszPathOut]; pszPathOut
0x18002e28e  call    cs:__imp_PathCchCombine
0x18002e294  mov     rcx, [rbp+1F8h]; this
0x18002e29b  test    eax, eax
0x18002e29d  jns     short loc_18002E2B4
0x18002e29f  mov     r9d, eax; char *
0x18002e2a2  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e2a9  mov     edx, 65h ; 'e'; void *
0x18002e2ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e2b4  lea     rdx, [rbp+1F0h+pszPathOut]
0x18002e2b8  lea     rcx, [rsp+2F0h+var_2A8]
0x18002e2bd  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002e2c2  nop
0x18002e2c3  mov     [rsp+2F0h+var_2C0], 0
0x18002e2cc  mov     rcx, [rsp+2F0h+var_2B8]
0x18002e2d1  mov     rax, [rcx]
0x18002e2d4  mov     [rsp+2F0h+var_2C0], 0
0x18002e2dd  lea     r8, [rsp+2F0h+var_2C0]
0x18002e2e2  mov     rdx, [rsp+2F0h+var_2A8]
0x18002e2e7  mov     rax, [rax+38h]
0x18002e2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2f0  cmp     eax, 80070002h
0x18002e2f5  jz      loc_18002E388
0x18002e2fb  mov     rcx, [rbp+1F8h]; this
0x18002e302  test    eax, eax
0x18002e304  jns     short loc_18002E31B
0x18002e306  mov     r9d, eax; char *
0x18002e309  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e310  mov     edx, 6Ch ; 'l'; void *
0x18002e315  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e31b  lea     rdx, aCleanupoffline; "CleanupOfflineContent"
0x18002e322  lea     rcx, [rsp+2F0h+var_2B0]
0x18002e327  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002e32c  nop
0x18002e32d  mov     rcx, [rsp+2F0h+var_2C0]
0x18002e332  mov     rax, [rcx]
0x18002e335  xor     r8d, r8d
0x18002e338  mov     rdx, [rsp+2F0h+var_2B0]
0x18002e33d  mov     rax, [rax+78h]
0x18002e341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e346  cmp     eax, 80070001h
0x18002e34b  jle     short loc_18002E35D
0x18002e34d  lea     ecx, [rax+7FF8FFFCh]
0x18002e353  cmp     ecx, 7FF8FFFBh
0x18002e359  jbe     short loc_18002E35D
0x18002e35b  xor     bl, bl
0x18002e35d  mov     rcx, [rbp+1F8h]; this
0x18002e364  test    bl, bl
0x18002e366  jz      short loc_18002E37D
0x18002e368  mov     r9d, eax; char *
0x18002e36b  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e372  mov     edx, 72h ; 'r'; void *
0x18002e377  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e37d  lea     rcx, [rsp+2F0h+var_2B0]
0x18002e382  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e387  nop
0x18002e388  lea     rcx, [rsp+2F0h+var_2C0]
0x18002e38d  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002e392  nop
0x18002e393  lea     rcx, [rsp+2F0h+var_2A8]
0x18002e398  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e39d  nop
0x18002e39e  lea     rcx, [rsp+2F0h+var_2B8]
0x18002e3a3  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002e3a8  mov     rcx, [rbp+1F0h+var_10]
0x18002e3af  xor     rcx, rsp; StackCookie
0x18002e3b2  call    __security_check_cookie
0x18002e3b7  mov     rbx, [rsp+2F0h+arg_0]
0x18002e3bf  add     rsp, 2F0h
0x18002e3c6  pop     rbp
0x18002e3c7  retn
```

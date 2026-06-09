# RetailDemoUtil::IsShortcutTargetValid(ushort const *)

- ea: `0x18002e6e8`
- end: `0x18002ebca`
- name: `?IsShortcutTargetValid@RetailDemoUtil@@YA_NPEBG@Z`
- size: `1250`
- prototype: `bool __fastcall(RetailDemoUtil *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b150`

## callees

- `0x180003390`
- `0x180003e00`
- `0x18000e330`
- `0x18001094c`
- `0x180011a10`
- `0x180014d04`
- `0x18002df4c`
- `0x18002e6e8`
- `0x180050010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18002e913`
- `SHLWAPI!PathFileExistsW` at `0x18002e913`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e901`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e901`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e73d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e83f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e73d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e83f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ea54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ea54`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18002ea0a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18002ea0a`

## string_xrefs

- `0x18002e94a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eaa2`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eaea`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eb02`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eb17`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eb2c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eb41`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eb56`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eb6b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eb8e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002eba3`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002ebb8`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002e938`: `Trying to process %ws, but the icon of the link does not exist(%ws).`
- `0x18002eac9`: `Trying to process %ws, but the destination of the link does not exist(%ws).`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
bool __fastcall RetailDemoUtil::IsShortcutTargetValid(RetailDemoUtil *this, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  __int64 (__fastcall **v4)(LPVOID, GUID *, __int64 *); // rax
  int v5; // eax
  int v6; // eax
  __int64 (__fastcall **v7)(LPVOID, GUID *, __int64 *); // rax
  int v8; // eax
  int v9; // eax
  bool v10; // di
  HRESULT v11; // eax
  __int64 (__fastcall **v12)(LPVOID, GUID *, LPCITEMIDLIST *); // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  __int64 (__fastcall **v18)(LPVOID, GUID *, __int64 *); // rax
  int v19; // ebx
  ITEMIDLIST *v20; // rcx
  int v21; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  LPCITEMIDLIST *p_pidl; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  char v33; // [rsp+88h] [rbp-78h]
  WCHAR Dst[296]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Src[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v27 = 0;
  v3 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &v27);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  v30 = 0;
  v4 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v27;
  v30 = 0;
  v5 = (*v4)(v27, &GUID_0000010b_0000_0000_c000_000000000046, &v30);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v6 = (*(__int64 (__fastcall **)(__int64, RetailDemoUtil *, _QWORD))(*(_QWORD *)v30 + 40LL))(v30, this, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v29 = 0;
  v7 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v27;
  v29 = 0;
  v8 = (*v7)(v27, &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1, &v29);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  v28 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 48LL))(v29, &v28);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  if ( (v28 & 0x1000) != 0 )
  {
    v10 = 1;
LABEL_8:
    v25 = 0;
    v11 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &v25);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        (const char *)(unsigned int)v11,
        ppva);
    pidl = 0;
    v12 = *(__int64 (__fastcall ***)(LPVOID, GUID *, LPCITEMIDLIST *))v25;
    pidl = 0;
    v13 = (*v12)(v25, &GUID_0000010b_0000_0000_c000_000000000046, &pidl);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        (const char *)(unsigned int)v13,
        ppva);
    v14 = (*(__int64 (__fastcall **)(LPCITEMIDLIST, RetailDemoUtil *, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 40LL))(
            pidl,
            this,
            0);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        (const char *)(unsigned int)v14,
        ppva);
    v26 = 0;
    v15 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, int *))(*(_QWORD *)v25 + 128LL))(v25, Src, 260, &v26);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        (const char *)(unsigned int)v15,
        ppva);
    if ( !ExpandEnvironmentStringsW(Src, Dst, 0x104u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB4,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        v16);
    if ( !PathFileExistsW(Dst) )
    {
      v10 = 0;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xB9,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
        (const char *)0x80070002LL,
        (int)"Trying to process %ws, but the icon of the link does not exist(%ws).",
        (const char *)this,
        Src);
    }
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&pidl);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v25);
    goto LABEL_16;
  }
  v10 = 0;
  pidl = 0;
  v18 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v27;
  p_pidl = &pidl;
  v32 = 0;
  v33 = 1;
  v19 = ((__int64 (__fastcall *)(LPVOID, __int64 *))v18[4])(v27, &v32);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
  if ( !v19 )
  {
    v25 = 0;
    if ( SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v25) >= 0 )
    {
      v26 = 0;
      v10 = (*(int (__fastcall **)(LPVOID, __int64, int *))(*(_QWORD *)v25 + 48LL))(v25, 0x1000000, &v26) >= 0;
    }
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v25);
  }
  v20 = (ITEMIDLIST *)pidl;
  pidl = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  if ( v10 )
    goto LABEL_8;
  memset_0(Dst, 0, sizeof(Dst));
  v21 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, WCHAR *))(*(_QWORD *)v27 + 24LL))(v27, Src, 260, Dst);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v21,
      1);
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0xA1,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
    (const char *)0x80070002LL,
    (int)"Trying to process %ws, but the destination of the link does not exist(%ws).",
    (const char *)this,
    Src);
LABEL_16:
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v29);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v30);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v27);
  return v10;
}

```

## disassembly

```asm
0x18002e6e8  push    rbp
0x18002e6ea  push    rbx
0x18002e6eb  push    rsi
0x18002e6ec  push    rdi
0x18002e6ed  push    r14
0x18002e6ef  push    r15
0x18002e6f1  lea     rbp, [rsp-408h]
0x18002e6f9  sub     rsp, 508h
0x18002e700  mov     rax, cs:__security_cookie
0x18002e707  xor     rax, rsp
0x18002e70a  mov     [rbp+430h+var_40], rax
0x18002e711  mov     rsi, rcx
0x18002e714  xor     r14d, r14d
0x18002e717  mov     [rsp+530h+var_4D8], r14
0x18002e71c  lea     rax, [rsp+530h+var_4D8]
0x18002e721  mov     [rsp+530h+ppv], rax; int
0x18002e726  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18002e72d  lea     r15d, [r14+1]
0x18002e731  mov     r8d, r15d; dwClsContext
0x18002e734  xor     edx, edx; pUnkOuter
0x18002e736  lea     rcx, CLSID_ShellLink; rclsid
0x18002e73d  call    cs:__imp_CoCreateInstance
0x18002e743  mov     rcx, [rbp+438h]; this
0x18002e74a  test    eax, eax
0x18002e74c  js      loc_18002EAFF
0x18002e752  mov     [rsp+530h+var_4C0], r14
0x18002e757  mov     rcx, [rsp+530h+var_4D8]
0x18002e75c  mov     rax, [rcx]
0x18002e75f  mov     [rsp+530h+var_4C0], r14
0x18002e764  lea     r8, [rsp+530h+var_4C0]
0x18002e769  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18002e770  mov     rax, [rax]
0x18002e773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e778  mov     rcx, [rbp+438h]; this
0x18002e77f  test    eax, eax
0x18002e781  js      loc_18002EB14
0x18002e787  mov     rcx, [rsp+530h+var_4C0]
0x18002e78c  mov     rax, [rcx]
0x18002e78f  xor     r8d, r8d
0x18002e792  mov     rdx, rsi
0x18002e795  mov     rax, [rax+28h]
0x18002e799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e79e  mov     rcx, [rbp+438h]; this
0x18002e7a5  test    eax, eax
0x18002e7a7  js      loc_18002EB29
0x18002e7ad  mov     [rsp+530h+var_4C8], r14
0x18002e7b2  mov     rcx, [rsp+530h+var_4D8]
0x18002e7b7  mov     rax, [rcx]
0x18002e7ba  mov     [rsp+530h+var_4C8], r14
0x18002e7bf  lea     r8, [rsp+530h+var_4C8]
0x18002e7c4  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x18002e7cb  mov     rax, [rax]
0x18002e7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7d3  mov     rcx, [rbp+438h]; this
0x18002e7da  test    eax, eax
0x18002e7dc  js      loc_18002EB3E
0x18002e7e2  mov     [rsp+530h+var_4D0], r14d
0x18002e7e7  mov     rcx, [rsp+530h+var_4C8]
0x18002e7ec  mov     rax, [rcx]
0x18002e7ef  lea     rdx, [rsp+530h+var_4D0]
0x18002e7f4  mov     rax, [rax+30h]
0x18002e7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7fd  mov     rcx, [rbp+438h]; this
0x18002e804  test    eax, eax
0x18002e806  js      loc_18002EB53
0x18002e80c  test    [rsp+530h+var_4D0], 1000h
0x18002e814  jz      loc_18002E9B4
0x18002e81a  mov     dil, r15b
0x18002e81d  mov     [rsp+530h+var_4E8], r14
0x18002e822  lea     rax, [rsp+530h+var_4E8]
0x18002e827  mov     [rsp+530h+ppv], rax; int
0x18002e82c  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18002e833  mov     r8d, r15d; dwClsContext
0x18002e836  xor     edx, edx; pUnkOuter
0x18002e838  lea     rcx, CLSID_ShellLink; rclsid
0x18002e83f  call    cs:__imp_CoCreateInstance
0x18002e845  mov     rcx, [rbp+438h]; this
0x18002e84c  test    eax, eax
0x18002e84e  js      loc_18002EB68
0x18002e854  mov     [rsp+530h+pidl], r14
0x18002e859  mov     rcx, [rsp+530h+var_4E8]
0x18002e85e  mov     rax, [rcx]
0x18002e861  mov     [rsp+530h+pidl], r14
0x18002e866  lea     r8, [rsp+530h+pidl]
0x18002e86b  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18002e872  mov     rax, [rax]
0x18002e875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e87a  mov     rcx, [rbp+438h]; this
0x18002e881  test    eax, eax
0x18002e883  js      loc_18002EB8B
0x18002e889  mov     rcx, [rsp+530h+pidl]
0x18002e88e  mov     rax, [rcx]
0x18002e891  xor     r8d, r8d
0x18002e894  mov     rdx, rsi
0x18002e897  mov     rax, [rax+28h]
0x18002e89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8a0  mov     rcx, [rbp+438h]; this
0x18002e8a7  test    eax, eax
0x18002e8a9  js      loc_18002EBA0
0x18002e8af  mov     [rsp+530h+var_4E0], r14d
0x18002e8b4  mov     rcx, [rsp+530h+var_4E8]
0x18002e8b9  mov     rax, [rcx]
0x18002e8bc  lea     r9, [rsp+530h+var_4E0]
0x18002e8c1  mov     r8d, 104h
0x18002e8c7  lea     rdx, [rbp+430h+Src]
0x18002e8ce  mov     rax, [rax+80h]
0x18002e8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8da  mov     rcx, [rbp+438h]; this
0x18002e8e1  test    eax, eax
0x18002e8e3  js      loc_18002EBB5
0x18002e8e9  mov     rbx, [rbp+438h]
0x18002e8f0  mov     r8d, 104h; nSize
0x18002e8f6  lea     rdx, [rbp+430h+Dst]; lpDst
0x18002e8fa  lea     rcx, [rbp+430h+Src]; lpSrc
0x18002e901  call    cs:__imp_ExpandEnvironmentStringsW
0x18002e907  test    eax, eax
0x18002e909  jz      loc_18002EAEA
0x18002e90f  lea     rcx, [rbp+430h+Dst]; pszPath
0x18002e913  call    cs:__imp_PathFileExistsW
0x18002e919  test    eax, eax
0x18002e91b  jnz     short loc_18002E95C
0x18002e91d  mov     dil, r14b
0x18002e920  mov     rcx, [rbp+438h]; this
0x18002e927  lea     rax, [rbp+430h+Src]
0x18002e92e  mov     [rsp+530h+var_500], rax
0x18002e933  mov     [rsp+530h+var_508], rsi; char *
0x18002e938  lea     rax, aTryingToProces_0; "Trying to process %ws, but the icon of "...
0x18002e93f  mov     [rsp+530h+ppv], rax; int
0x18002e944  mov     r9d, 80070002h; char *
0x18002e94a  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e951  mov     edx, 0B9h; void *
0x18002e956  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002e95b  nop
0x18002e95c  lea     rcx, [rsp+530h+pidl]
0x18002e961  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002e966  nop
0x18002e967  lea     rcx, [rsp+530h+var_4E8]
0x18002e96c  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002e971  nop
0x18002e972  lea     rcx, [rsp+530h+var_4C8]
0x18002e977  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002e97c  nop
0x18002e97d  lea     rcx, [rsp+530h+var_4C0]
0x18002e982  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002e987  nop
0x18002e988  lea     rcx, [rsp+530h+var_4D8]
0x18002e98d  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002e992  mov     al, dil
0x18002e995  mov     rcx, [rbp+430h+var_40]
0x18002e99c  xor     rcx, rsp; StackCookie
0x18002e99f  call    __security_check_cookie
0x18002e9a4  add     rsp, 508h
0x18002e9ab  pop     r15
0x18002e9ad  pop     r14
0x18002e9af  pop     rdi
0x18002e9b0  pop     rsi
0x18002e9b1  pop     rbx
0x18002e9b2  pop     rbp
0x18002e9b3  retn
0x18002e9b4  movzx   edi, r14b
0x18002e9b8  mov     [rsp+530h+pidl], r14
0x18002e9bd  mov     rcx, [rsp+530h+var_4D8]
0x18002e9c2  mov     rax, [rcx]
0x18002e9c5  lea     rdx, [rsp+530h+pidl]
0x18002e9ca  mov     [rsp+530h+var_4B8], rdx
0x18002e9cf  mov     [rbp+430h+var_4B0], r14
0x18002e9d3  mov     [rbp+430h+var_4A8], r15b
0x18002e9d7  lea     rdx, [rbp+430h+var_4B0]
0x18002e9db  mov     rax, [rax+20h]
0x18002e9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9e4  mov     ebx, eax
0x18002e9e6  lea     rcx, [rsp+530h+var_4B8]
0x18002e9eb  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18002e9f0  test    ebx, ebx
0x18002e9f2  jnz     short loc_18002EA45
0x18002e9f4  mov     [rsp+530h+var_4E8], r14
0x18002e9f9  lea     r8, [rsp+530h+var_4E8]; ppv
0x18002e9fe  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002ea05  mov     rcx, [rsp+530h+pidl]; pidl
0x18002ea0a  call    cs:__imp_SHCreateItemFromIDList
0x18002ea10  test    eax, eax
0x18002ea12  js      short loc_18002EA3A
0x18002ea14  mov     [rsp+530h+var_4E0], r14d
0x18002ea19  mov     rcx, [rsp+530h+var_4E8]
0x18002ea1e  mov     rax, [rcx]
0x18002ea21  lea     r8, [rsp+530h+var_4E0]
0x18002ea26  mov     edx, 1000000h
0x18002ea2b  mov     rax, [rax+30h]
0x18002ea2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea34  test    eax, eax
0x18002ea36  cmovns  edi, r15d
0x18002ea3a  lea     rcx, [rsp+530h+var_4E8]
0x18002ea3f  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002ea44  nop
0x18002ea45  mov     rcx, [rsp+530h+pidl]; pv
0x18002ea4a  mov     [rsp+530h+pidl], r14
0x18002ea4f  test    rcx, rcx
0x18002ea52  jz      short loc_18002EA5A
0x18002ea54  call    cs:__imp_CoTaskMemFree
0x18002ea5a  test    dil, dil
0x18002ea5d  jnz     loc_18002E81D
0x18002ea63  xor     edx, edx; Val
0x18002ea65  mov     r8d, 250h; Size
0x18002ea6b  lea     rcx, [rbp+430h+Dst]; void *
0x18002ea6f  call    memset_0
0x18002ea74  mov     rcx, [rsp+530h+var_4D8]
0x18002ea79  mov     rax, [rcx]
0x18002ea7c  mov     dword ptr [rsp+530h+ppv], r15d; int
0x18002ea81  lea     r9, [rbp+430h+Dst]
0x18002ea85  mov     r8d, 104h
0x18002ea8b  lea     rdx, [rbp+430h+Src]
0x18002ea92  mov     rax, [rax+18h]
0x18002ea96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea9b  mov     rcx, [rbp+438h]; this
0x18002eaa2  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eaa9  test    eax, eax
0x18002eaab  js      loc_18002EB7D
0x18002eab1  mov     rcx, [rbp+438h]; this
0x18002eab8  lea     rax, [rbp+430h+Src]
0x18002eabf  mov     [rsp+530h+var_500], rax
0x18002eac4  mov     [rsp+530h+var_508], rsi; char *
0x18002eac9  lea     rax, aTryingToProces; "Trying to process %ws, but the destinat"...
0x18002ead0  mov     [rsp+530h+ppv], rax; int
0x18002ead5  mov     r9d, 80070002h; char *
0x18002eadb  mov     edx, 0A1h; void *
0x18002eae0  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002eae5  jmp     loc_18002E972
0x18002eaea  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eaf1  mov     edx, 0B4h; void *
0x18002eaf6  mov     rcx, rbx; this
0x18002eaf9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002eaff  mov     r9d, eax; char *
0x18002eb02  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eb09  mov     edx, 79h ; 'y'; void *
0x18002eb0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb14  mov     r9d, eax; char *
0x18002eb17  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eb1e  mov     edx, 7Bh ; '{'; void *
0x18002eb23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb29  mov     r9d, eax; char *
0x18002eb2c  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eb33  mov     edx, 7Ch ; '|'; void *
0x18002eb38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb3e  mov     r9d, eax; char *
0x18002eb41  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eb48  mov     edx, 80h; void *
0x18002eb4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb53  mov     r9d, eax; char *
0x18002eb56  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eb5d  mov     edx, 82h; void *
0x18002eb62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb68  mov     r9d, eax; char *
0x18002eb6b  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eb72  mov     edx, 0A7h; void *
0x18002eb77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb7d  mov     r9d, eax; char *
0x18002eb80  mov     edx, 0A0h; void *
0x18002eb85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb8b  mov     r9d, eax; char *
0x18002eb8e  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002eb95  mov     edx, 0ABh; void *
0x18002eb9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eba0  mov     r9d, eax; char *
0x18002eba3  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002ebaa  mov     edx, 0ADh; void *
0x18002ebaf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ebb5  mov     r9d, eax; char *
0x18002ebb8  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002ebbf  mov     edx, 0B0h; void *
0x18002ebc4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

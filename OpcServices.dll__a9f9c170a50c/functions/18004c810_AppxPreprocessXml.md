# AppxPreprocessXml

- ea: `0x18004c810`
- end: `0x18004cc85`
- name: `AppxPreprocessXml`
- size: `1141`
- prototype: `__int64 __fastcall(__int64, __int64, struct Stream *, unsigned int, __int64, wchar_t **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001a810`
- `0x1800427fc`
- `0x1800460f0`
- `0x18004c810`
- `0x18004dc94`
- `0x1800517a0`
- `0x1800654b0`
- `0x1800cd38c`
- `0x180117740`
- `0x18012a010`

## string_xrefs

- `0x18004c95e`: `AppxPreprocessXml parameter inputStream cannot be NULL`
- `0x18004c9d0`: `AppxPreprocessXml parameter processedStream cannot be NULL`
- `0x18004ca42`: `AppxPreprocessXml parameter namespaces cannot be NULL`
- `0x18004cab4`: `AppxPreprocessXml parameter namespaceCount cannot be 0`
- `0x18004cb26`: `AppxPreprocessXml parameter errorMessage cannot be NULL`
- `0x18004cb98`: `AppxPreprocessXml parameter lineNumber cannot be NULL`
- `0x18004cc0a`: `AppxPreprocessXml parameter columnNumber cannot be NULL`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppxPreprocessXml(
        __int64 a1,
        __int64 a2,
        struct Stream *a3,
        unsigned int a4,
        __int64 a5,
        wchar_t **a6,
        unsigned int *a7)
{
  win_musl *v10; // rcx
  win_musl::Formatter *v12; // rcx
  struct win_musl::TStringEllipseBase *v13; // rax
  win_musl::Formatter *v14; // rax
  struct win_musl::TStringEllipseBase *v15; // rax
  win_musl::Formatter *v16; // rax
  struct win_musl::TStringEllipseBase *v17; // rax
  win_musl::Formatter *v18; // rax
  struct win_musl::TStringEllipseBase *v19; // rax
  win_musl::Formatter *v20; // rax
  struct win_musl::TStringEllipseBase *v21; // rax
  win_musl::Formatter *v22; // rax
  struct win_musl::TStringEllipseBase *v23; // rax
  win_musl::Formatter *v24; // rax
  struct win_musl::TStringEllipseBase *v25; // rax
  unsigned int *v26; // [rsp+38h] [rbp-550h]
  __int64 v27; // [rsp+40h] [rbp-548h] BYREF
  __int64 v28; // [rsp+48h] [rbp-540h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-538h] BYREF
  _BYTE v30[48]; // [rsp+60h] [rbp-528h] BYREF
  _BYTE v31[96]; // [rsp+90h] [rbp-4F8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-498h] BYREF
  _BYTE v33[160]; // [rsp+190h] [rbp-3F8h] BYREF
  _BYTE v34[160]; // [rsp+230h] [rbp-358h] BYREF
  _BYTE v35[160]; // [rsp+2D0h] [rbp-2B8h] BYREF
  _BYTE v36[160]; // [rsp+370h] [rbp-218h] BYREF
  _BYTE v37[160]; // [rsp+410h] [rbp-178h] BYREF
  _BYTE v38[160]; // [rsp+4B0h] [rbp-D8h] BYREF

  v29[1] = -2;
  try
  {
    if ( !a1 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter inputStream cannot be NULL");
      v12 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v13 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v12);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x18Du,
        0x80004003,
        v13);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !a2 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter processedStream cannot be NULL");
      v14 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v15 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v14);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v33,
        0x195u,
        0x80004003,
        v15);
      throw (SplException::THResultException *)v33;
    }
    if ( !a3 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter namespaces cannot be NULL");
      v16 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v17 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v16);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v34,
        0x19Du,
        0x80004003,
        v17);
      throw (SplException::THResultException *)v34;
    }
    if ( !a4 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter namespaceCount cannot be 0");
      v18 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v19 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v18);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v35,
        0x1A5u,
        0x80004003,
        v19);
      throw (SplException::THResultException *)v35;
    }
    if ( !a5 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter errorMessage cannot be NULL");
      v20 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v21 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v20);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v36,
        0x1ADu,
        0x80004003,
        v21);
      throw (SplException::THResultException *)v36;
    }
    if ( !a6 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter lineNumber cannot be NULL");
      v22 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v23 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v22);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v37,
        0x1B5u,
        0x80004003,
        v23);
      throw (SplException::THResultException *)v37;
    }
    if ( !a7 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter columnNumber cannot be NULL");
      v24 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v25 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v24);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v38,
        0x1BDu,
        0x80004003,
        v25);
      throw (SplException::THResultException *)v38;
    }
    v27 = a1;
    v29[0] = 0;
    win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(
      v29,
      &v27);
    v28 = a2;
    v27 = 0;
    win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(
      &v27,
      &v28);
    win_musl::consumption::InternalAppxPreprocessXml(
      (win_musl::consumption *)v29,
      (struct Stream *)&v27,
      a3,
      (const wchar_t **)a4,
      a5,
      a6,
      a7,
      v26);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v10 = (win_musl *)v29[0];
    if ( v29[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
  }
  catch ( ... )
  {
    win_musl::detail_process_errors(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18004c810  mov     rax, rsp
0x18004c813  push    rdi
0x18004c814  push    r12
0x18004c816  push    r13
0x18004c818  push    r14
0x18004c81a  push    r15
0x18004c81c  sub     rsp, 560h
0x18004c823  mov     [rsp+588h+var_530], 0FFFFFFFFFFFFFFFEh
0x18004c82c  mov     [rax+8], rbx
0x18004c830  mov     [rax+10h], rsi
0x18004c834  mov     rax, cs:__security_cookie
0x18004c83b  xor     rax, rsp
0x18004c83e  mov     [rsp+588h+var_38], rax
0x18004c846  mov     r14d, r9d
0x18004c849  mov     rsi, r8
0x18004c84c  mov     rdi, rdx
0x18004c84f  mov     r15, [rsp+588h+arg_20]
0x18004c857  mov     r12, [rsp+588h+arg_28]
0x18004c85f  mov     r13, [rsp+588h+arg_30]
0x18004c867  xor     ebx, ebx
0x18004c869  test    rcx, rcx
0x18004c86c  jz      loc_18004C95E
0x18004c872  test    rdx, rdx
0x18004c875  jz      loc_18004C9D0
0x18004c87b  test    r8, r8
0x18004c87e  jz      loc_18004CA42
0x18004c884  test    r9d, r9d
0x18004c887  jz      loc_18004CAB4
0x18004c88d  test    r15, r15
0x18004c890  jz      loc_18004CB26
0x18004c896  test    r12, r12
0x18004c899  jz      loc_18004CB98
0x18004c89f  test    r13, r13
0x18004c8a2  jz      loc_18004CC0A
0x18004c8a8  mov     [rsp+588h+var_548], rcx
0x18004c8ad  mov     [rsp+588h+var_538], rbx
0x18004c8b2  lea     rdx, [rsp+588h+var_548]
0x18004c8b7  lea     rcx, [rsp+588h+var_538]
0x18004c8bc  call    ??$construct_acquire@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIPackageSettings@@@Z; win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(win_scope::scope<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>> *,IPackageSettings * *)
0x18004c8c1  nop
0x18004c8c2  mov     [rsp+588h+var_540], rdi
0x18004c8c7  mov     [rsp+588h+var_548], rbx
0x18004c8cc  lea     rdx, [rsp+588h+var_540]
0x18004c8d1  lea     rcx, [rsp+588h+var_548]
0x18004c8d6  call    ??$construct_acquire@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIPackageSettings@@@Z; win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(win_scope::scope<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>> *,IPackageSettings * *)
0x18004c8db  nop
0x18004c8dc  mov     [rsp+588h+var_558], r13; unsigned int *
0x18004c8e1  mov     [rsp+588h+var_560], r12; wchar_t **
0x18004c8e6  mov     qword ptr [rsp+588h+var_568], r15; unsigned int
0x18004c8eb  mov     r9d, r14d; wchar_t **
0x18004c8ee  mov     r8, rsi; struct Stream *
0x18004c8f1  lea     rdx, [rsp+588h+var_548]; struct Stream *
0x18004c8f6  lea     rcx, [rsp+588h+var_538]; this
0x18004c8fb  call    ?InternalAppxPreprocessXml@consumption@win_musl@@YAXAEAVStream@win_dox@@0PEAPEB_WKPEAPEA_WPEAK3@Z; win_musl::consumption::InternalAppxPreprocessXml(win_dox::Stream &,win_dox::Stream &,wchar_t const * *,ulong,wchar_t * *,ulong *,ulong *)
0x18004c900  nop
0x18004c901  mov     rcx, [rsp+588h+var_548]
0x18004c906  test    rcx, rcx
0x18004c909  jz      short loc_18004C918
0x18004c90b  mov     rax, [rcx]
0x18004c90e  mov     rax, [rax+10h]
0x18004c912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c917  nop
0x18004c918  mov     rcx, [rsp+588h+var_538]
0x18004c91d  test    rcx, rcx
0x18004c920  jz      short loc_18004C92F
0x18004c922  mov     rax, [rcx]
0x18004c925  mov     rax, [rax+10h]
0x18004c929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c92e  nop
0x18004c92f  mov     eax, ebx
0x18004c931  mov     rcx, [rsp+588h+var_38]
0x18004c939  xor     rcx, rsp; StackCookie
0x18004c93c  call    __security_check_cookie
0x18004c941  lea     r11, [rsp+588h+var_28]
0x18004c949  mov     rbx, [r11+30h]
0x18004c94d  mov     rsi, [r11+38h]
0x18004c951  mov     rsp, r11
0x18004c954  pop     r15
0x18004c956  pop     r14
0x18004c958  pop     r13
0x18004c95a  pop     r12
0x18004c95c  pop     rdi
0x18004c95d  retn
0x18004c95e  lea     rdx, aAppxpreprocess_3; "AppxPreprocessXml parameter inputStream"...
0x18004c965  lea     rcx, [rsp+588h+var_528]
0x18004c96a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004c96f  nop
0x18004c970  lea     rdx, [rsp+588h+var_528]
0x18004c975  lea     rcx, [rsp+588h+var_4F8]
0x18004c97d  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004c982  nop
0x18004c983  mov     rcx, rax; this
0x18004c986  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18004c98b  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18004c990  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18004c998  mov     [rsp+588h+var_568], 18Dh; unsigned int
0x18004c9a0  lea     r9, word_18013A0B6
0x18004c9a7  lea     r8, aNoFilename; "(no filename)"
0x18004c9ae  lea     rcx, [rsp+588h+pExceptionObject]; this
0x18004c9b6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004c9bb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004c9c2  lea     rcx, [rsp+588h+pExceptionObject]; pExceptionObject
0x18004c9ca  call    _CxxThrowException_0
0x18004c9d0  lea     rdx, aAppxpreprocess; "AppxPreprocessXml parameter processedSt"...
0x18004c9d7  lea     rcx, [rsp+588h+var_528]
0x18004c9dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004c9e1  nop
0x18004c9e2  lea     rdx, [rsp+588h+var_528]
0x18004c9e7  lea     rcx, [rsp+588h+var_4F8]
0x18004c9ef  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004c9f4  nop
0x18004c9f5  mov     rcx, rax; this
0x18004c9f8  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18004c9fd  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18004ca02  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18004ca0a  mov     [rsp+588h+var_568], 195h; unsigned int
0x18004ca12  lea     r9, word_18013A0B6
0x18004ca19  lea     r8, aNoFilename; "(no filename)"
0x18004ca20  lea     rcx, [rsp+588h+var_3F8]; this
0x18004ca28  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004ca2d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004ca34  lea     rcx, [rsp+588h+var_3F8]; pExceptionObject
0x18004ca3c  call    _CxxThrowException_0
0x18004ca42  lea     rdx, aAppxpreprocess_0; "AppxPreprocessXml parameter namespaces "...
0x18004ca49  lea     rcx, [rsp+588h+var_528]
0x18004ca4e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004ca53  nop
0x18004ca54  lea     rdx, [rsp+588h+var_528]
0x18004ca59  lea     rcx, [rsp+588h+var_4F8]
0x18004ca61  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004ca66  nop
0x18004ca67  mov     rcx, rax; this
0x18004ca6a  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18004ca6f  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18004ca74  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18004ca7c  mov     [rsp+588h+var_568], 19Dh; unsigned int
0x18004ca84  lea     r9, word_18013A0B6
0x18004ca8b  lea     r8, aNoFilename; "(no filename)"
0x18004ca92  lea     rcx, [rsp+588h+var_358]; this
0x18004ca9a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004ca9f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004caa6  lea     rcx, [rsp+588h+var_358]; pExceptionObject
0x18004caae  call    _CxxThrowException_0
0x18004cab4  lea     rdx, aAppxpreprocess_2; "AppxPreprocessXml parameter namespaceCo"...
0x18004cabb  lea     rcx, [rsp+588h+var_528]
0x18004cac0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004cac5  nop
0x18004cac6  lea     rdx, [rsp+588h+var_528]
0x18004cacb  lea     rcx, [rsp+588h+var_4F8]
0x18004cad3  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004cad8  nop
0x18004cad9  mov     rcx, rax; this
0x18004cadc  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18004cae1  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18004cae6  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18004caee  mov     [rsp+588h+var_568], 1A5h; unsigned int
0x18004caf6  lea     r9, word_18013A0B6
0x18004cafd  lea     r8, aNoFilename; "(no filename)"
0x18004cb04  lea     rcx, [rsp+588h+var_2B8]; this
0x18004cb0c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004cb11  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004cb18  lea     rcx, [rsp+588h+var_2B8]; pExceptionObject
0x18004cb20  call    _CxxThrowException_0
0x18004cb26  lea     rdx, aAppxpreprocess_9; "AppxPreprocessXml parameter errorMessag"...
0x18004cb2d  lea     rcx, [rsp+588h+var_528]
0x18004cb32  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004cb37  nop
0x18004cb38  lea     rdx, [rsp+588h+var_528]
0x18004cb3d  lea     rcx, [rsp+588h+var_4F8]
0x18004cb45  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004cb4a  nop
0x18004cb4b  mov     rcx, rax; this
0x18004cb4e  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18004cb53  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18004cb58  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18004cb60  mov     [rsp+588h+var_568], 1ADh; unsigned int
0x18004cb68  lea     r9, word_18013A0B6
0x18004cb6f  lea     r8, aNoFilename; "(no filename)"
0x18004cb76  lea     rcx, [rsp+588h+var_218]; this
0x18004cb7e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004cb83  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004cb8a  lea     rcx, [rsp+588h+var_218]; pExceptionObject
0x18004cb92  call    _CxxThrowException_0
0x18004cb98  lea     rdx, aAppxpreprocess_10; "AppxPreprocessXml parameter lineNumber "...
0x18004cb9f  lea     rcx, [rsp+588h+var_528]
0x18004cba4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004cba9  nop
0x18004cbaa  lea     rdx, [rsp+588h+var_528]
0x18004cbaf  lea     rcx, [rsp+588h+var_4F8]
0x18004cbb7  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004cbbc  nop
0x18004cbbd  mov     rcx, rax; this
0x18004cbc0  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18004cbc5  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18004cbca  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18004cbd2  mov     [rsp+588h+var_568], 1B5h; unsigned int
0x18004cbda  lea     r9, word_18013A0B6
0x18004cbe1  lea     r8, aNoFilename; "(no filename)"
0x18004cbe8  lea     rcx, [rsp+588h+var_178]; this
0x18004cbf0  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004cbf5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004cbfc  lea     rcx, [rsp+588h+var_178]; pExceptionObject
0x18004cc04  call    _CxxThrowException_0
0x18004cc0a  lea     rdx, aAppxpreprocess_4; "AppxPreprocessXml parameter columnNumbe"...
0x18004cc11  lea     rcx, [rsp+588h+var_528]
0x18004cc16  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004cc1b  nop
0x18004cc1c  lea     rdx, [rsp+588h+var_528]
0x18004cc21  lea     rcx, [rsp+588h+var_4F8]
0x18004cc29  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004cc2e  nop
0x18004cc2f  mov     rcx, rax; this
0x18004cc32  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18004cc37  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18004cc3c  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18004cc44  mov     [rsp+588h+var_568], 1BDh; unsigned int
0x18004cc4c  lea     r9, word_18013A0B6
0x18004cc53  lea     r8, aNoFilename; "(no filename)"
0x18004cc5a  lea     rcx, [rsp+588h+var_D8]; this
0x18004cc62  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004cc67  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004cc6e  lea     rcx, [rsp+588h+var_D8]; pExceptionObject
0x18004cc76  call    _CxxThrowException_0
0x18004cc7c  mov     ebx, dword ptr [rsp+588h+var_548]
0x18004cc80  jmp     loc_18004C92F
```

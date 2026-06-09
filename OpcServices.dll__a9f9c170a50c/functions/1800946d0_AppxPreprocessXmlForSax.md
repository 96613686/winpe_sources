# AppxPreprocessXmlForSax

- ea: `0x1800946d0`
- end: `0x180094a44`
- name: `AppxPreprocessXmlForSax`
- size: `884`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const struct win_musl::consumption::SaxErrorHandler *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800016dc`
- `0x18001a810`
- `0x1800427fc`
- `0x1800460f0`
- `0x1800517a0`
- `0x180054bd4`
- `0x1800654b0`
- `0x1800946d0`
- `0x1800cd38c`
- `0x180117740`
- `0x18012a010`

## string_xrefs

- `0x18009470a`: `AppxPreprocessXmlForSax parameter inputStream cannot be NULL`
- `0x180094781`: `AppxPreprocessXmlForSax parameter contentHandler cannot be NULL`
- `0x1800947f8`: `AppxPreprocessXmlForSax parameter errorHandler cannot be NULL`
- `0x18009486f`: `AppxPreprocessXmlForSax parameter namespaces cannot be NULL`
- `0x1800948ec`: `AppxPreprocessXmlForSax parameter namespaceCount cannot be 0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AppxPreprocessXmlForSax(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const struct win_musl::consumption::SaxErrorHandler *a4,
        int a5)
{
  win_musl::Formatter *v8; // rcx
  struct win_musl::TStringEllipseBase *v9; // rax
  win_musl::Formatter *v10; // rax
  struct win_musl::TStringEllipseBase *v11; // rax
  win_musl::Formatter *v12; // rax
  struct win_musl::TStringEllipseBase *v13; // rax
  win_musl::Formatter *v14; // rax
  struct win_musl::TStringEllipseBase *v15; // rax
  win_musl::Formatter *v16; // rax
  struct win_musl::TStringEllipseBase *v17; // rax
  unsigned int *v18; // rcx
  wchar_t **v20; // [rsp+20h] [rbp-428h]
  unsigned int *v21; // [rsp+40h] [rbp-408h] BYREF
  __int64 v22; // [rsp+48h] [rbp-400h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-3F8h] BYREF
  _BYTE v24[40]; // [rsp+68h] [rbp-3E0h] BYREF
  _BYTE v25[96]; // [rsp+90h] [rbp-3B8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-358h] BYREF
  _BYTE v27[160]; // [rsp+190h] [rbp-2B8h] BYREF
  _BYTE v28[160]; // [rsp+230h] [rbp-218h] BYREF
  _BYTE v29[160]; // [rsp+2D0h] [rbp-178h] BYREF
  _BYTE v30[160]; // [rsp+370h] [rbp-D8h] BYREF

  v23[1] = -2;
  try
  {
    if ( !a1 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter inputStream cannot be NULL");
      v8 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v9 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v8);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EEu,
        0x80004003,
        v9);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !a2 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter contentHandler cannot be NULL");
      v10 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v11 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v10);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v27,
        0x1F6u,
        0x80004003,
        v11);
      throw (SplException::THResultException *)v27;
    }
    if ( !a3 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter errorHandler cannot be NULL");
      v12 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v13 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v12);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v28,
        0x1FEu,
        0x80004003,
        v13);
      throw (SplException::THResultException *)v28;
    }
    if ( !a4 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter namespaces cannot be NULL");
      v14 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v15 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v14);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v29,
        0x206u,
        0x80004003,
        v15);
      throw (SplException::THResultException *)v29;
    }
    if ( !a5 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter namespaceCount cannot be 0");
      v16 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v17 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v16);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v30,
        0x20Eu,
        0x80004003,
        v17);
      throw (SplException::THResultException *)v30;
    }
    v22 = a1;
    v21 = 0;
    win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(
      &v21,
      &v22);
    win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(
      v23,
      a2);
    win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(
      &v22,
      a3);
    v23[2] = 0;
    LODWORD(v20) = a5;
    win_musl::consumption::ParseAndPreprocessXml(
      (win_musl::consumption *)&v21,
      (struct Stream *)v23,
      (const struct win_musl::consumption::SaxContentHandler *)&v22,
      a4,
      (const wchar_t **)v20,
      0,
      0,
      0);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    v18 = v21;
    if ( v21 )
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  catch ( ... )
  {
    win_musl::detail_process_errors((win_musl *)v18);
  }
  return 0;
}

```

## disassembly

```asm
0x1800946d0  push    rbx
0x1800946d2  push    rsi
0x1800946d3  push    rdi
0x1800946d4  push    r14
0x1800946d6  push    r15
0x1800946d8  sub     rsp, 420h
0x1800946df  mov     [rsp+448h+var_3F0], 0FFFFFFFFFFFFFFFEh
0x1800946e8  mov     rax, cs:__security_cookie
0x1800946ef  xor     rax, rsp
0x1800946f2  mov     [rsp+448h+var_38], rax
0x1800946fa  mov     r15, r9
0x1800946fd  mov     r14, r8
0x180094700  mov     rsi, rdx
0x180094703  xor     edi, edi
0x180094705  test    rcx, rcx
0x180094708  jnz     short loc_18009477C
0x18009470a  lea     rdx, aAppxpreprocess_8; "AppxPreprocessXmlForSax parameter input"...
0x180094711  lea     rcx, [rsp+448h+var_3E0]
0x180094716  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009471b  nop
0x18009471c  lea     rdx, [rsp+448h+var_3E0]
0x180094721  lea     rcx, [rsp+448h+var_3B8]
0x180094729  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18009472e  nop
0x18009472f  mov     rcx, rax; this
0x180094732  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180094737  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x18009473c  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x180094744  mov     dword ptr [rsp+448h+var_428], 1EEh; unsigned int
0x18009474c  lea     r9, word_18013A0B6
0x180094753  lea     r8, aNoFilename; "(no filename)"
0x18009475a  lea     rcx, [rsp+448h+pExceptionObject]; this
0x180094762  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180094767  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009476e  lea     rcx, [rsp+448h+pExceptionObject]; pExceptionObject
0x180094776  call    _CxxThrowException_0
0x18009477c  test    rsi, rsi
0x18009477f  jnz     short loc_1800947F3
0x180094781  lea     rdx, aAppxpreprocess_6; "AppxPreprocessXmlForSax parameter conte"...
0x180094788  lea     rcx, [rsp+448h+var_3E0]
0x18009478d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180094792  nop
0x180094793  lea     rdx, [rsp+448h+var_3E0]
0x180094798  lea     rcx, [rsp+448h+var_3B8]
0x1800947a0  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800947a5  nop
0x1800947a6  mov     rcx, rax; this
0x1800947a9  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800947ae  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x1800947b3  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x1800947bb  mov     dword ptr [rsp+448h+var_428], 1F6h; unsigned int
0x1800947c3  lea     r9, word_18013A0B6
0x1800947ca  lea     r8, aNoFilename; "(no filename)"
0x1800947d1  lea     rcx, [rsp+448h+var_2B8]; this
0x1800947d9  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800947de  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800947e5  lea     rcx, [rsp+448h+var_2B8]; pExceptionObject
0x1800947ed  call    _CxxThrowException_0
0x1800947f3  test    r14, r14
0x1800947f6  jnz     short loc_18009486A
0x1800947f8  lea     rdx, aAppxpreprocess_7; "AppxPreprocessXmlForSax parameter error"...
0x1800947ff  lea     rcx, [rsp+448h+var_3E0]
0x180094804  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180094809  nop
0x18009480a  lea     rdx, [rsp+448h+var_3E0]
0x18009480f  lea     rcx, [rsp+448h+var_3B8]
0x180094817  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18009481c  nop
0x18009481d  mov     rcx, rax; this
0x180094820  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180094825  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x18009482a  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x180094832  mov     dword ptr [rsp+448h+var_428], 1FEh; unsigned int
0x18009483a  lea     r9, word_18013A0B6
0x180094841  lea     r8, aNoFilename; "(no filename)"
0x180094848  lea     rcx, [rsp+448h+var_218]; this
0x180094850  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180094855  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009485c  lea     rcx, [rsp+448h+var_218]; pExceptionObject
0x180094864  call    _CxxThrowException_0
0x18009486a  test    r15, r15
0x18009486d  jnz     short loc_1800948E1
0x18009486f  lea     rdx, aAppxpreprocess_5; "AppxPreprocessXmlForSax parameter names"...
0x180094876  lea     rcx, [rsp+448h+var_3E0]
0x18009487b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180094880  nop
0x180094881  lea     rdx, [rsp+448h+var_3E0]
0x180094886  lea     rcx, [rsp+448h+var_3B8]
0x18009488e  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180094893  nop
0x180094894  mov     rcx, rax; this
0x180094897  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18009489c  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x1800948a1  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x1800948a9  mov     dword ptr [rsp+448h+var_428], 206h; unsigned int
0x1800948b1  lea     r9, word_18013A0B6
0x1800948b8  lea     r8, aNoFilename; "(no filename)"
0x1800948bf  lea     rcx, [rsp+448h+var_178]; this
0x1800948c7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800948cc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800948d3  lea     rcx, [rsp+448h+var_178]; pExceptionObject
0x1800948db  call    _CxxThrowException_0
0x1800948e1  mov     ebx, dword ptr [rsp+448h+arg_20]
0x1800948e8  test    ebx, ebx
0x1800948ea  jnz     short loc_18009495E
0x1800948ec  lea     rdx, aAppxpreprocess_1; "AppxPreprocessXmlForSax parameter names"...
0x1800948f3  lea     rcx, [rsp+448h+var_3E0]
0x1800948f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800948fd  nop
0x1800948fe  lea     rdx, [rsp+448h+var_3E0]
0x180094903  lea     rcx, [rsp+448h+var_3B8]
0x18009490b  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180094910  nop
0x180094911  mov     rcx, rax; this
0x180094914  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180094919  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x18009491e  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x180094926  mov     dword ptr [rsp+448h+var_428], 20Eh; unsigned int
0x18009492e  lea     r9, word_18013A0B6
0x180094935  lea     r8, aNoFilename; "(no filename)"
0x18009493c  lea     rcx, [rsp+448h+var_D8]; this
0x180094944  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180094949  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180094950  lea     rcx, [rsp+448h+var_D8]; pExceptionObject
0x180094958  call    _CxxThrowException_0
0x18009495e  mov     [rsp+448h+var_400], rcx
0x180094963  mov     [rsp+448h+var_408], 0; unsigned int *
0x18009496c  lea     rdx, [rsp+448h+var_400]
0x180094971  lea     rcx, [rsp+448h+var_408]
0x180094976  call    ??$construct_acquire@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIPackageSettings@@@Z; win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(win_scope::scope<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>> *,IPackageSettings * *)
0x18009497b  nop
0x18009497c  mov     rdx, rsi
0x18009497f  lea     rcx, [rsp+448h+var_3F8]
0x180094984  call    ??0?$scope@PEAUIWin7InternalPartSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAUIWin7InternalPartSender@@@Z; win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(IWin7InternalPartSender *)
0x180094989  nop
0x18009498a  mov     rdx, r14
0x18009498d  lea     rcx, [rsp+448h+var_400]
0x180094992  call    ??0?$scope@PEAUIWin7InternalPartSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAUIWin7InternalPartSender@@@Z; win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(IWin7InternalPartSender *)
0x180094997  nop
0x180094998  mov     [rsp+448h+var_3E8], 0
0x1800949a1  mov     [rsp+448h+var_410], 0; unsigned int *
0x1800949aa  mov     [rsp+448h+var_418], 0; wchar_t **
0x1800949b3  mov     qword ptr [rsp+448h+var_420], 0; unsigned int
0x1800949bc  mov     dword ptr [rsp+448h+var_428], ebx; wchar_t **
0x1800949c0  mov     r9, r15; struct win_musl::consumption::SaxErrorHandler *
0x1800949c3  lea     r8, [rsp+448h+var_400]; struct win_musl::consumption::SaxContentHandler *
0x1800949c8  lea     rdx, [rsp+448h+var_3F8]; struct Stream *
0x1800949cd  lea     rcx, [rsp+448h+var_408]; this
0x1800949d2  call    ?ParseAndPreprocessXml@consumption@win_musl@@YAXAEAVStream@win_dox@@AEBVSaxContentHandler@12@AEBVSaxErrorHandler@12@PEAPEB_WKPEAPEA_WPEAK5@Z; win_musl::consumption::ParseAndPreprocessXml(win_dox::Stream &,win_musl::consumption::SaxContentHandler const &,win_musl::consumption::SaxErrorHandler const &,wchar_t const * *,ulong,wchar_t * *,ulong *,ulong *)
0x1800949d7  nop
0x1800949d8  mov     rcx, [rsp+448h+var_400]
0x1800949dd  test    rcx, rcx
0x1800949e0  jz      short loc_1800949EF
0x1800949e2  mov     rax, [rcx]
0x1800949e5  mov     rax, [rax+10h]
0x1800949e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800949ee  nop
0x1800949ef  mov     rcx, [rsp+448h+var_3F8]
0x1800949f4  test    rcx, rcx
0x1800949f7  jz      short loc_180094A06
0x1800949f9  mov     rax, [rcx]
0x1800949fc  mov     rax, [rax+10h]
0x180094a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a05  nop
0x180094a06  mov     rcx, [rsp+448h+var_408]
0x180094a0b  test    rcx, rcx
0x180094a0e  jz      short loc_180094A1D
0x180094a10  mov     rax, [rcx]
0x180094a13  mov     rax, [rax+10h]
0x180094a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a1c  nop
0x180094a1d  jmp     short loc_180094A23
0x180094a1f  mov     edi, dword ptr [rsp+448h+var_408]
0x180094a23  mov     eax, edi
0x180094a25  mov     rcx, [rsp+448h+var_38]
0x180094a2d  xor     rcx, rsp; StackCookie
0x180094a30  call    __security_check_cookie
0x180094a35  add     rsp, 420h
0x180094a3c  pop     r15
0x180094a3e  pop     r14
0x180094a40  pop     rdi
0x180094a41  pop     rsi
0x180094a42  pop     rbx
0x180094a43  retn
```

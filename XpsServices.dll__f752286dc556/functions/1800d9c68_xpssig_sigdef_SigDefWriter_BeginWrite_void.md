# xpssig::sigdef::SigDefWriter::BeginWrite(void)

- ea: `0x1800d9c68`
- end: `0x1800da14b`
- name: `?BeginWrite@SigDefWriter@sigdef@xpssig@@QEAAXXZ`
- size: `1251`
- prototype: `void __fastcall(xpssig::sigdef::SigDefWriter *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d99a8`

## callees

- `0x180005664`
- `0x180008cc8`
- `0x180012450`
- `0x1800549bc`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c20c4`
- `0x1800d8d4c`
- `0x1800d9c68`
- `0x180134b70`
- `0x1801359ce`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800d9e95`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9ebf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9ee7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9f13`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9f3c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9e95`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9ebf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9ee7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9f13`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9f3c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9f99`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fb7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fc6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fd5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9f99`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fb7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fc6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9fd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d9d7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d9d7f`

## string_xrefs

- `0x1800d9ee0`: `xmlns`
- `0x1800d9f0c`: `xmlns`
- `0x1800d9cf7`: `Writer: ISAXContentHandler::startDocument() fails`
- `0x1800d9fe0`: `Writer: IMXAttributes::addAttribute('xmlns') fails`
- `0x1800da096`: `Writer: ISAXContentHandler::startElement('SignatureDefinitions') fails`
- `0x1800d9d8b`: `Writer: CoCreateInstance(CLSID_SAXAttributes60, IID_IMXAttributes) fails`
- `0x1800d9e21`: `Writer: IMXAttributes::QueryInterface(IID_ISAXAttributes) fails`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall xpssig::sigdef::SigDefWriter::BeginWrite(const OLECHAR **this)
{
  __int64 v2; // rax
  OLECHAR *v3; // r14
  int v4; // ebx
  win_musl::Formatter *v5; // rax
  const wchar_t *v6; // rax
  HRESULT v7; // ebx
  win_musl::Formatter *v8; // rax
  const wchar_t *v9; // rax
  LPVOID v10; // rdi
  __int64 (__fastcall **v11)(LPVOID, GUID *, __int64 *); // rbx
  int v12; // ebx
  win_musl::Formatter *v13; // rax
  const wchar_t *v14; // rax
  BSTR v15; // rax
  BSTR v16; // r12
  OLECHAR *v17; // rbx
  BSTR v18; // rax
  BSTR v19; // r13
  OLECHAR *v20; // rdi
  BSTR v21; // rax
  OLECHAR *v22; // rsi
  BSTR v23; // rax
  BSTR v24; // rax
  OLECHAR *v25; // r15
  int v26; // r12d
  win_musl::Formatter *v27; // rax
  const wchar_t *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // ebx
  win_musl::Formatter *v32; // rax
  const wchar_t *v33; // rax
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v36; // [rsp+60h] [rbp-A0h]
  BSTR v37; // [rsp+68h] [rbp-98h]
  BSTR v38; // [rsp+70h] [rbp-90h]
  BSTR v39; // [rsp+78h] [rbp-88h]
  BSTR v40; // [rsp+80h] [rbp-80h]
  BSTR v41; // [rsp+88h] [rbp-78h]
  BSTR v42; // [rsp+90h] [rbp-70h]
  BSTR v43; // [rsp+98h] [rbp-68h]
  LPVOID v44; // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall **v45)(LPVOID, GUID *, __int64 *); // [rsp+A8h] [rbp-58h]
  _QWORD *v46; // [rsp+B0h] [rbp-50h]
  xpssig::sigdef::SigDefWriter *v47; // [rsp+B8h] [rbp-48h]
  _BYTE v48[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v49[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+130h] [rbp+30h] BYREF

  v47 = (xpssig::sigdef::SigDefWriter *)this;
  win_musl::production::MXmlWriter::WriteHeader((win_musl::production::MXmlWriter *)(this + 1));
  v2 = win_musl::production::MXmlWriter::StartWriteContent((win_musl::production::MXWriter *)(this + 1));
  v46 = this + 4;
  win_scope::scope<win_musl::Fiber<win_musl::FiberData<win_musl::FiberStreamData>> *,win_scope::const_policies<win_scope::com_policies>>::operator=(
    this + 4,
    v2);
  v3 = 0;
  if ( v36 )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v36 + 16LL))(v36);
  v4 = (*(__int64 (__fastcall **)(const OLECHAR *))(*(_QWORD *)this[4] + 32LL))(this[4]);
  if ( v4 < 0 )
  {
    std::wstring::wstring(v48, L"Writer: ISAXContentHandler::startDocument() fails");
    v5 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v49, v48);
    v6 = win_musl::Formatter::c_str(v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x373u,
      v4,
      (__int64)v6);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v34 = 0;
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_SAXAttributes60, 0, 0x17u, &IID_IMXAttributes, &ppv);
  if ( v7 < 0 )
  {
    std::wstring::wstring(v48, L"Writer: CoCreateInstance(CLSID_SAXAttributes60, IID_IMXAttributes) fails");
    v8 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v49, v48);
    v9 = win_musl::Formatter::c_str(v8);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x385u,
      v7,
      (__int64)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v10 = ppv;
  v11 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v34,
    0);
  v34 = 0;
  v12 = (*v11)(v10, &IID_ISAXAttributes, &v34);
  if ( v12 < 0 )
  {
    std::wstring::wstring(v48, L"Writer: IMXAttributes::QueryInterface(IID_ISAXAttributes) fails");
    v13 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v49, v48);
    v14 = win_musl::Formatter::c_str(v13);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x38Fu,
      v12,
      (__int64)v14);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v44 = ppv;
  v45 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
  v15 = SysAllocString(this[5]);
  v16 = v15;
  v17 = 0;
  v39 = 0;
  if ( v15 )
  {
    v17 = v15;
    v39 = v15;
  }
  else
  {
    v16 = 0;
  }
  v18 = SysAllocString(&word_1801DC754);
  v19 = v18;
  v20 = 0;
  v40 = 0;
  if ( v18 )
  {
    v20 = v18;
    v40 = v18;
  }
  else
  {
    v19 = 0;
  }
  v21 = SysAllocString(L"xmlns");
  v37 = v21;
  v22 = 0;
  v41 = 0;
  if ( v21 )
  {
    v22 = v21;
    v41 = v21;
  }
  else
  {
    v37 = 0;
  }
  v23 = SysAllocString(L"xmlns");
  v38 = v23;
  v42 = 0;
  if ( v23 )
  {
    v3 = v23;
    v42 = v23;
  }
  else
  {
    v38 = 0;
  }
  v24 = SysAllocString(&word_1801DC754);
  v36 = v24;
  v25 = 0;
  v43 = 0;
  if ( v24 )
  {
    v25 = v24;
    v43 = v24;
  }
  else
  {
    v36 = 0;
  }
  v26 = ((__int64 (__fastcall *)(LPVOID, BSTR, BSTR, BSTR, BSTR, BSTR))v45[7])(v44, v24, v38, v37, v19, v16);
  if ( v36 )
    SysFreeString(v25);
  if ( v3 )
    SysFreeString(v3);
  if ( v22 )
    SysFreeString(v22);
  if ( v20 )
    SysFreeString(v20);
  if ( v17 )
    SysFreeString(v17);
  if ( v26 < 0 )
  {
    std::wstring::wstring(v48, L"Writer: IMXAttributes::addAttribute('xmlns') fails");
    v27 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v49, v48);
    v28 = win_musl::Formatter::c_str(v27);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x39Fu,
      v26,
      (__int64)v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v29 = *((_QWORD *)v47 + 5);
  v30 = -1;
  do
    ++v30;
  while ( *(_WORD *)(v29 + 2 * v30) );
  v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, const wchar_t *))(*(_QWORD *)*v46 + 64LL))(
          *v46,
          v29,
          v30,
          L"SignatureDefinitions");
  if ( v31 < 0 )
  {
    std::wstring::wstring(v48, L"Writer: ISAXContentHandler::startElement('SignatureDefinitions') fails");
    v32 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v49, v48);
    v33 = win_musl::Formatter::c_str(v32);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x3ADu,
      v31,
      (__int64)v33);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x1800d9c68  push    rbp
0x1800d9c6a  push    rbx
0x1800d9c6b  push    rsi
0x1800d9c6c  push    rdi
0x1800d9c6d  push    r12
0x1800d9c6f  push    r13
0x1800d9c71  push    r14
0x1800d9c73  push    r15
0x1800d9c75  lea     rbp, [rsp-0E8h]
0x1800d9c7d  sub     rsp, 1E8h
0x1800d9c84  mov     rax, cs:__security_cookie
0x1800d9c8b  xor     rax, rsp
0x1800d9c8e  mov     [rbp+120h+var_50], rax
0x1800d9c95  mov     rsi, rcx
0x1800d9c98  mov     [rbp+120h+var_168], rcx
0x1800d9c9c  add     rcx, 8; this
0x1800d9ca0  call    ?WriteHeader@MXmlWriter@production@win_musl@@QEAAXXZ; win_musl::production::MXmlWriter::WriteHeader(void)
0x1800d9ca5  lea     rdx, [rsp+220h+var_1C0]
0x1800d9caa  lea     rcx, [rsi+8]; this
0x1800d9cae  call    ?StartWriteContent@MXmlWriter@production@win_musl@@QEAA?AV?$scope@PEAUISAXContentHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_musl::production::MXmlWriter::StartWriteContent(void)
0x1800d9cb3  nop
0x1800d9cb4  lea     rbx, [rsi+20h]
0x1800d9cb8  mov     [rbp+120h+var_170], rbx
0x1800d9cbc  mov     rdx, rax
0x1800d9cbf  mov     rcx, rbx
0x1800d9cc2  call    ??4?$scope@PEAV?$Fiber@V?$FiberData@UFiberStreamData@win_musl@@@win_musl@@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAAAEAV01@AEBV01@@Z; win_scope::scope<win_musl::Fiber<win_musl::FiberData<win_musl::FiberStreamData>> *,win_scope::const_policies<win_scope::com_policies>>::operator=(win_scope::scope<win_musl::Fiber<win_musl::FiberData<win_musl::FiberStreamData>> *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800d9cc7  nop
0x1800d9cc8  mov     rcx, [rsp+220h+var_1C0]
0x1800d9ccd  xor     r14d, r14d
0x1800d9cd0  test    rcx, rcx
0x1800d9cd3  jz      short loc_1800D9CE2
0x1800d9cd5  mov     rax, [rcx]
0x1800d9cd8  mov     rax, [rax+10h]
0x1800d9cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ce1  nop
0x1800d9ce2  mov     rcx, [rbx]
0x1800d9ce5  mov     rax, [rcx]
0x1800d9ce8  mov     rax, [rax+20h]
0x1800d9cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9cf1  mov     ebx, eax
0x1800d9cf3  test    eax, eax
0x1800d9cf5  jns     short loc_1800D9D57
0x1800d9cf7  lea     rdx, aWriterIsaxcont_0; "Writer: ISAXContentHandler::startDocume"...
0x1800d9cfe  lea     rcx, [rbp+120h+var_160]
0x1800d9d02  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d9d07  nop
0x1800d9d08  lea     rdx, [rbp+120h+var_160]
0x1800d9d0c  lea     rcx, [rbp+120h+var_140]
0x1800d9d10  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800d9d15  nop
0x1800d9d16  mov     rcx, rax; this
0x1800d9d19  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800d9d1e  mov     [rsp+220h+var_1F0], rax; __int64
0x1800d9d23  mov     [rsp+220h+var_1F8], ebx; int
0x1800d9d27  mov     dword ptr [rsp+220h+ppv], 373h; unsigned int
0x1800d9d2f  lea     r9, Src
0x1800d9d36  lea     r8, aNoFilename; "(no filename)"
0x1800d9d3d  lea     rcx, [rbp+120h+pExceptionObject]; this
0x1800d9d41  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d9d46  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d9d4d  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x1800d9d51  call    _CxxThrowException_0
0x1800d9d57  mov     [rsp+220h+var_1D0], r14
0x1800d9d5c  mov     [rsp+220h+var_1C8], r14
0x1800d9d61  lea     rax, [rsp+220h+var_1C8]
0x1800d9d66  mov     [rsp+220h+ppv], rax; ppv
0x1800d9d6b  lea     r9, IID_IMXAttributes; riid
0x1800d9d72  xor     edx, edx; pUnkOuter
0x1800d9d74  lea     r8d, [rdx+17h]; dwClsContext
0x1800d9d78  lea     rcx, CLSID_SAXAttributes60; rclsid
0x1800d9d7f  call    cs:__imp_CoCreateInstance
0x1800d9d85  mov     ebx, eax
0x1800d9d87  test    eax, eax
0x1800d9d89  jns     short loc_1800D9DEB
0x1800d9d8b  lea     rdx, aWriterCocreate; "Writer: CoCreateInstance(CLSID_SAXAttri"...
0x1800d9d92  lea     rcx, [rbp+120h+var_160]
0x1800d9d96  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d9d9b  nop
0x1800d9d9c  lea     rdx, [rbp+120h+var_160]
0x1800d9da0  lea     rcx, [rbp+120h+var_140]
0x1800d9da4  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800d9da9  nop
0x1800d9daa  mov     rcx, rax; this
0x1800d9dad  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800d9db2  mov     [rsp+220h+var_1F0], rax; __int64
0x1800d9db7  mov     [rsp+220h+var_1F8], ebx; int
0x1800d9dbb  mov     dword ptr [rsp+220h+ppv], 385h; unsigned int
0x1800d9dc3  lea     r9, Src
0x1800d9dca  lea     r8, aNoFilename; "(no filename)"
0x1800d9dd1  lea     rcx, [rbp+120h+pExceptionObject]; this
0x1800d9dd5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d9dda  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d9de1  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x1800d9de5  call    _CxxThrowException_0
0x1800d9deb  mov     rdi, [rsp+220h+var_1C8]
0x1800d9df0  mov     rbx, [rdi]
0x1800d9df3  xor     edx, edx
0x1800d9df5  lea     rcx, [rsp+220h+var_1D0]
0x1800d9dfa  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800d9dff  mov     [rsp+220h+var_1D0], r14
0x1800d9e04  lea     r8, [rsp+220h+var_1D0]
0x1800d9e09  lea     rdx, IID_ISAXAttributes
0x1800d9e10  mov     rcx, rdi
0x1800d9e13  mov     rax, [rbx]
0x1800d9e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9e1b  mov     ebx, eax
0x1800d9e1d  test    eax, eax
0x1800d9e1f  jns     short loc_1800D9E81
0x1800d9e21  lea     rdx, aWriterImxattri; "Writer: IMXAttributes::QueryInterface(I"...
0x1800d9e28  lea     rcx, [rbp+120h+var_160]
0x1800d9e2c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d9e31  nop
0x1800d9e32  lea     rdx, [rbp+120h+var_160]
0x1800d9e36  lea     rcx, [rbp+120h+var_140]
0x1800d9e3a  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800d9e3f  nop
0x1800d9e40  mov     rcx, rax; this
0x1800d9e43  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800d9e48  mov     [rsp+220h+var_1F0], rax; __int64
0x1800d9e4d  mov     [rsp+220h+var_1F8], ebx; int
0x1800d9e51  mov     dword ptr [rsp+220h+ppv], 38Fh; unsigned int
0x1800d9e59  lea     r9, Src
0x1800d9e60  lea     r8, aNoFilename; "(no filename)"
0x1800d9e67  lea     rcx, [rbp+120h+pExceptionObject]; this
0x1800d9e6b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d9e70  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d9e77  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x1800d9e7b  call    _CxxThrowException_0
0x1800d9e81  mov     rax, [rsp+220h+var_1C8]
0x1800d9e86  mov     [rbp+120h+var_180], rax
0x1800d9e8a  mov     rax, [rax]
0x1800d9e8d  mov     [rbp+120h+var_178], rax
0x1800d9e91  mov     rcx, [rsi+28h]; psz
0x1800d9e95  call    cs:__imp_SysAllocString
0x1800d9e9b  mov     r12, rax
0x1800d9e9e  mov     rbx, r14
0x1800d9ea1  mov     [rsp+220h+var_1A8], rbx
0x1800d9ea6  test    rax, rax
0x1800d9ea9  jnz     short loc_1800D9EB0
0x1800d9eab  mov     r12, r14
0x1800d9eae  jmp     short loc_1800D9EB8
0x1800d9eb0  mov     rbx, rax
0x1800d9eb3  mov     [rsp+220h+var_1A8], rax
0x1800d9eb8  lea     rcx, word_1801DC754; psz
0x1800d9ebf  call    cs:__imp_SysAllocString
0x1800d9ec5  mov     r13, rax
0x1800d9ec8  mov     rdi, r14
0x1800d9ecb  mov     [rbp+120h+var_1A0], r14
0x1800d9ecf  test    rax, rax
0x1800d9ed2  jnz     short loc_1800D9ED9
0x1800d9ed4  mov     r13, r14
0x1800d9ed7  jmp     short loc_1800D9EE0
0x1800d9ed9  mov     rdi, rax
0x1800d9edc  mov     [rbp+120h+var_1A0], rax
0x1800d9ee0  lea     rcx, aXmlns; "xmlns"
0x1800d9ee7  call    cs:__imp_SysAllocString
0x1800d9eed  mov     [rsp+220h+var_1B8], rax
0x1800d9ef2  mov     rsi, r14
0x1800d9ef5  mov     [rbp+120h+var_198], r14
0x1800d9ef9  test    rax, rax
0x1800d9efc  jnz     short loc_1800D9F05
0x1800d9efe  mov     [rsp+220h+var_1B8], r14
0x1800d9f03  jmp     short loc_1800D9F0C
0x1800d9f05  mov     rsi, rax
0x1800d9f08  mov     [rbp+120h+var_198], rax
0x1800d9f0c  lea     rcx, aXmlns; "xmlns"
0x1800d9f13  call    cs:__imp_SysAllocString
0x1800d9f19  mov     [rsp+220h+var_1B0], rax
0x1800d9f1e  mov     [rbp+120h+var_190], r14
0x1800d9f22  test    rax, rax
0x1800d9f25  jnz     short loc_1800D9F2E
0x1800d9f27  mov     [rsp+220h+var_1B0], rax
0x1800d9f2c  jmp     short loc_1800D9F35
0x1800d9f2e  mov     r14, rax
0x1800d9f31  mov     [rbp+120h+var_190], rax
0x1800d9f35  lea     rcx, word_1801DC754; psz
0x1800d9f3c  call    cs:__imp_SysAllocString
0x1800d9f42  mov     [rsp+220h+var_1C0], rax
0x1800d9f47  xor     r15d, r15d
0x1800d9f4a  mov     [rbp+120h+var_188], r15
0x1800d9f4e  test    rax, rax
0x1800d9f51  jnz     short loc_1800D9F5A
0x1800d9f53  mov     [rsp+220h+var_1C0], rax
0x1800d9f58  jmp     short loc_1800D9F61
0x1800d9f5a  mov     r15, rax
0x1800d9f5d  mov     [rbp+120h+var_188], rax
0x1800d9f61  mov     qword ptr [rsp+220h+var_1F8], r12
0x1800d9f66  mov     [rsp+220h+ppv], r13
0x1800d9f6b  mov     r9, [rsp+220h+var_1B8]
0x1800d9f70  mov     r8, [rsp+220h+var_1B0]
0x1800d9f75  mov     rdx, rax
0x1800d9f78  mov     rcx, [rbp+120h+var_180]
0x1800d9f7c  mov     rax, [rbp+120h+var_178]
0x1800d9f80  mov     rax, [rax+38h]
0x1800d9f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f89  mov     r12d, eax
0x1800d9f8c  xor     r13d, r13d
0x1800d9f8f  cmp     [rsp+220h+var_1C0], r13
0x1800d9f94  jz      short loc_1800D9FA0
0x1800d9f96  mov     rcx, r15; bstrString
0x1800d9f99  call    cs:__imp_SysFreeString
0x1800d9f9f  nop
0x1800d9fa0  test    r14, r14
0x1800d9fa3  jz      short loc_1800D9FAF
0x1800d9fa5  mov     rcx, r14; bstrString
0x1800d9fa8  call    cs:__imp_SysFreeString
0x1800d9fae  nop
0x1800d9faf  test    rsi, rsi
0x1800d9fb2  jz      short loc_1800D9FBE
0x1800d9fb4  mov     rcx, rsi; bstrString
0x1800d9fb7  call    cs:__imp_SysFreeString
0x1800d9fbd  nop
0x1800d9fbe  test    rdi, rdi
0x1800d9fc1  jz      short loc_1800D9FCD
0x1800d9fc3  mov     rcx, rdi; bstrString
0x1800d9fc6  call    cs:__imp_SysFreeString
0x1800d9fcc  nop
0x1800d9fcd  test    rbx, rbx
0x1800d9fd0  jz      short loc_1800D9FDB
0x1800d9fd2  mov     rcx, rbx; bstrString
0x1800d9fd5  call    cs:__imp_SysFreeString
0x1800d9fdb  test    r12d, r12d
0x1800d9fde  jns     short loc_1800DA041
0x1800d9fe0  lea     rdx, aWriterImxattri_1; "Writer: IMXAttributes::addAttribute('xm"...
0x1800d9fe7  lea     rcx, [rbp+120h+var_160]
0x1800d9feb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d9ff0  nop
0x1800d9ff1  lea     rdx, [rbp+120h+var_160]
0x1800d9ff5  lea     rcx, [rbp+120h+var_140]
0x1800d9ff9  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800d9ffe  nop
0x1800d9fff  mov     rcx, rax; this
0x1800da002  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800da007  mov     [rsp+220h+var_1F0], rax; __int64
0x1800da00c  mov     [rsp+220h+var_1F8], r12d; int
0x1800da011  mov     dword ptr [rsp+220h+ppv], 39Fh; unsigned int
0x1800da019  lea     r9, Src
0x1800da020  lea     r8, aNoFilename; "(no filename)"
0x1800da027  lea     rcx, [rbp+120h+pExceptionObject]; this
0x1800da02b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800da030  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800da037  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x1800da03b  call    _CxxThrowException_0
0x1800da041  mov     rcx, [rbp+120h+var_170]
0x1800da045  mov     rcx, [rcx]
0x1800da048  mov     rax, [rcx]
0x1800da04b  mov     r9, [rsp+220h+var_1D0]
0x1800da050  mov     rdx, [rbp+120h+var_168]
0x1800da054  mov     rdx, [rdx+28h]
0x1800da058  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800da05c  inc     r8
0x1800da05f  cmp     [rdx+r8*2], r13w
0x1800da064  jnz     short loc_1800DA05C
0x1800da066  mov     [rsp+220h+var_1E8], r9
0x1800da06b  mov     r10d, 14h
0x1800da071  mov     dword ptr [rsp+220h+var_1F0], r10d
0x1800da076  lea     r9, ?gc_signatureDefinitions@Element@Xps@win_musl@@3QB_WB; "SignatureDefinitions"
0x1800da07d  mov     qword ptr [rsp+220h+var_1F8], r9
0x1800da082  mov     dword ptr [rsp+220h+ppv], r10d
0x1800da087  mov     rax, [rax+40h]
0x1800da08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da090  mov     ebx, eax
0x1800da092  test    eax, eax
0x1800da094  jns     short loc_1800DA0F6
0x1800da096  lea     rdx, aWriterIsaxcont_5; "Writer: ISAXContentHandler::startElemen"...
0x1800da09d  lea     rcx, [rbp+120h+var_160]
0x1800da0a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800da0a6  nop
0x1800da0a7  lea     rdx, [rbp+120h+var_160]
0x1800da0ab  lea     rcx, [rbp+120h+var_140]
0x1800da0af  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800da0b4  nop
0x1800da0b5  mov     rcx, rax; this
0x1800da0b8  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800da0bd  mov     [rsp+220h+var_1F0], rax; __int64
0x1800da0c2  mov     [rsp+220h+var_1F8], ebx; int
0x1800da0c6  mov     dword ptr [rsp+220h+ppv], 3ADh; unsigned int
0x1800da0ce  lea     r9, Src
0x1800da0d5  lea     r8, aNoFilename; "(no filename)"
0x1800da0dc  lea     rcx, [rbp+120h+pExceptionObject]; this
0x1800da0e0  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800da0e5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800da0ec  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x1800da0f0  call    _CxxThrowException_0
0x1800da0f6  mov     rcx, [rsp+220h+var_1D0]
0x1800da0fb  test    rcx, rcx
0x1800da0fe  jz      short loc_1800DA111
0x1800da100  mov     rax, [rcx]
0x1800da103  mov     rax, [rax+10h]
0x1800da107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da10c  mov     [rsp+220h+var_1D0], r13
0x1800da111  mov     rcx, [rsp+220h+var_1C8]
0x1800da116  test    rcx, rcx
0x1800da119  jz      short loc_1800DA128
0x1800da11b  mov     rax, [rcx]
0x1800da11e  mov     rax, [rax+10h]
0x1800da122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da127  nop
0x1800da128  mov     rcx, [rbp+120h+var_50]
0x1800da12f  xor     rcx, rsp; StackCookie
  ... truncated ...
```

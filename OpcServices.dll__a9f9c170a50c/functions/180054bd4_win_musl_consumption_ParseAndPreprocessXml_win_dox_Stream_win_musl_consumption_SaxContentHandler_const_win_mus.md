# win_musl::consumption::ParseAndPreprocessXml(win_dox::Stream &,win_musl::consumption::SaxContentHandler const &,win_musl::consumption::SaxErrorHandler const &,wchar_t const * *,ulong,wchar_t * *,ulong *,ulong *)

- ea: `0x180054bd4`
- end: `0x180054ff7`
- name: `?ParseAndPreprocessXml@consumption@win_musl@@YAXAEAVStream@win_dox@@AEBVSaxContentHandler@12@AEBVSaxErrorHandler@12@PEAPEB_WKPEAPEA_WPEAK5@Z`
- size: `1059`
- prototype: `void __fastcall(win_musl::consumption *this, struct Stream *, const struct win_musl::consumption::SaxContentHandler *, const struct win_musl::consumption::SaxErrorHandler *, const wchar_t **, wchar_t **, wchar_t **, unsigned int *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004dc94`
- `0x1800946d0`

## callees

- `0x1800016b0`
- `0x180018b9c`
- `0x180018c00`
- `0x18001a810`
- `0x180029dd4`
- `0x1800460f0`
- `0x1800517a0`
- `0x18005343c`
- `0x180054bd4`
- `0x180055000`
- `0x1800550ec`
- `0x1800552ac`
- `0x180055344`
- `0x1800553f0`
- `0x1800654b0`
- `0x1800695bc`
- `0x18006afbc`
- `0x1800cce54`
- `0x1800cd38c`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054fe6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall win_musl::consumption::ParseAndPreprocessXml(
        win_musl::consumption *this,
        struct Stream *a2,
        const struct win_musl::consumption::SaxContentHandler *a3,
        const struct win_musl::consumption::SaxErrorHandler *a4,
        const wchar_t **a5,
        wchar_t **a6,
        wchar_t **a7,
        unsigned int *a8)
{
  const struct win_musl::consumption::SaxErrorHandler *v8; // r14
  __int64 v9; // rbx
  unsigned __int128 v10; // rax
  win_musl::sax::ns *v11; // rax
  win_musl::sax::ns *v12; // rdi
  win_musl::sax::ns *v13; // r14
  win_musl::sax::ns *v14; // rbx
  unsigned int i; // edx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  const char *v19; // rdx
  unsigned int v20; // r8d
  unsigned int *v21; // r14
  unsigned int *v22; // r15
  wchar_t **p_pv; // rdi
  win_musl::consumption::AppxXmlPreprocessor *v24; // rax
  __int64 v25; // rax
  signed int v26; // r12d
  struct win_musl::consumption::SaxErrorHandler *v27; // rdi
  const OLECHAR *v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rbx
  const OLECHAR *v32; // rcx
  win_musl::Formatter *v33; // rax
  struct win_musl::TStringEllipseBase *v34; // rax
  struct win_musl::consumption::SaxErrorHandler *v35; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A8h] BYREF
  const struct win_musl::consumption::SaxErrorHandler *v39; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-98h] BYREF
  struct win_musl::consumption::SaxContentHandler *v41; // [rsp+78h] [rbp-90h] BYREF
  win_musl::consumption *v42; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v43[2]; // [rsp+88h] [rbp-80h] BYREF
  win_musl::sax::ns *v44; // [rsp+98h] [rbp-70h]
  win_musl::consumption::AppxXmlPreprocessor *v45; // [rsp+A0h] [rbp-68h]
  __int64 v46; // [rsp+A8h] [rbp-60h]
  __int128 v47; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-40h]
  _BYTE v49[40]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v50[40]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v51[48]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+168h] [rbp+60h] BYREF
  char v53[96]; // [rsp+208h] [rbp+100h] BYREF

  v46 = -2;
  v8 = a4;
  v39 = a4;
  v35 = a3;
  v41 = a2;
  v42 = this;
  v9 = (unsigned int)a5;
  v10 = (unsigned int)a5 * (unsigned __int128)0x10uLL;
  if ( !is_mul_ok((unsigned int)a5, 0x10u) )
    *(_QWORD *)&v10 = -1;
  v11 = (win_musl::sax::ns *)operator new[](v10, *((const char **)&v10 + 1), (unsigned int)a3);
  v12 = v11;
  v44 = v11;
  if ( v11 )
  {
    v13 = v11;
    if ( (_DWORD)a5 )
    {
      do
      {
        win_musl::sax::ns::ns(v13);
        v13 = (win_musl::sax::ns *)((char *)v13 + 16);
        --v9;
      }
      while ( v9 );
    }
    v8 = v39;
  }
  else
  {
    v12 = 0;
  }
  v14 = 0;
  if ( v12 )
    v14 = v12;
  v44 = v14;
  for ( i = 0; i < (unsigned int)a5; ++i )
  {
    v16 = *((_QWORD *)v8 + i);
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(v16 + 2 * v17) );
    v18 = 2LL * (int)i;
    *((_QWORD *)v14 + v18) = v16;
    *((_QWORD *)v14 + v18 + 1) = v16 + 2 * v17;
  }
  win_musl::consumption::CreateMarkupQueryKnownNs<win_musl::sax::ns *>(&v39, v14, (char *)v14 + 16 * (int)a5);
  pv = 0;
  LODWORD(v36) = 0;
  LODWORD(v40) = 0;
  v21 = (unsigned int *)&v40;
  if ( a8 )
    v21 = a8;
  v22 = (unsigned int *)&v36;
  if ( a7 )
    v22 = (unsigned int *)a7;
  if ( a6 )
  {
    p_pv = a6;
  }
  else
  {
    pv = 0;
    p_pv = (wchar_t **)&pv;
  }
  v24 = (win_musl::consumption::AppxXmlPreprocessor *)operator new(0x60u, v19, v20);
  v45 = v24;
  if ( v24 )
    v25 = win_musl::consumption::AppxXmlPreprocessor::AppxXmlPreprocessor(
            v24,
            (struct win_musl::consumption::MarkupQuery *)&v39,
            v41,
            v35,
            p_pv,
            v22,
            v21);
  else
    v25 = 0;
  win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>(
    v43,
    v25);
  win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>>(&ppv);
  v47 = 0;
  LOWORD(v47) = 13;
  *((_QWORD *)&v47 + 1) = *(_QWORD *)win_dox::Stream::GetInterface(v42, &v41);
  if ( v41 )
    (*(void (__fastcall **)(struct win_musl::consumption::SaxContentHandler *))(*(_QWORD *)v41 + 16LL))(v41);
  v48 = 0;
  v26 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 152LL))(ppv, &v47);
  if ( v26 < 0 )
  {
    if ( a6 )
      v28 = *a6;
    else
      v28 = (const OLECHAR *)pv;
    std::wstring::wstring(&v47, L"Sax Parse failed <Line Number: %{line}, Column Number: %{col}, Reason: %{message}>");
    v29 = win_musl::Formatter::Formatter(v53, &v47);
    std::wstring::wstring(v49, L"line");
    v30 = win_musl::Formatter::insert<unsigned long>(v29, v49, v22);
    std::wstring::wstring(v50, L"col");
    v31 = win_musl::Formatter::insert<unsigned long>(v30, v50, v21);
    v32 = &psz;
    if ( v28 )
      v32 = v28;
    v42 = (win_musl::consumption *)v32;
    std::wstring::wstring(v51, L"message");
    v33 = (win_musl::Formatter *)win_musl::Formatter::insert<wchar_t const *>(v31, v51, &v42);
    v34 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v33);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x5Du,
      v26,
      v34);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v35 = 0;
  v27 = (struct win_musl::consumption::SaxErrorHandler *)ppv;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
  else
    v27 = 0;
  v35 = v27;
  win_musl::consumption::ValidateSaxEncoding(&v35);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v43[1] && v43[0] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v43);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v39 )
    (*(void (__fastcall **)(const struct win_musl::consumption::SaxErrorHandler *))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v14 )
    operator delete(v14);
}

```

## disassembly

```asm
0x180054bd4  mov     rax, rsp
0x180054bd7  push    rbp
0x180054bd8  push    rsi
0x180054bd9  push    rdi
0x180054bda  push    r12
0x180054bdc  push    r13
0x180054bde  push    r14
0x180054be0  push    r15
0x180054be2  lea     rbp, [rax-1A8h]
0x180054be9  sub     rsp, 270h
0x180054bf0  mov     [rbp+1A0h+var_200], 0FFFFFFFFFFFFFFFEh
0x180054bf8  mov     [rax+20h], rbx
0x180054bfc  mov     rax, cs:__security_cookie
0x180054c03  xor     rax, rsp
0x180054c06  mov     [rbp+1A0h+var_40], rax
0x180054c0d  mov     r14, r9
0x180054c10  mov     [rsp+2A0h+var_240], r9
0x180054c15  mov     [rsp+2A0h+var_260], r8
0x180054c1a  mov     [rsp+2A0h+var_230], rdx
0x180054c1f  mov     [rsp+2A0h+var_228], rcx
0x180054c24  mov     r12, [rbp+1A0h+arg_30]
0x180054c2b  mov     r13, [rbp+1A0h+arg_38]
0x180054c32  movsxd  r15, dword ptr [rbp+1A0h+arg_20]
0x180054c39  mov     rsi, [rbp+1A0h+arg_28]
0x180054c40  mov     ebx, r15d
0x180054c43  mov     eax, 10h
0x180054c48  mul     rbx
0x180054c4b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180054c52  cmovb   rax, rcx
0x180054c56  mov     rcx, rax; unsigned __int64
0x180054c59  call    ??_U@YAPEAX_KPEBDK@Z; operator new[](unsigned __int64,char const *,ulong)
0x180054c5e  mov     rdi, rax
0x180054c61  mov     [rbp+1A0h+var_210], rax
0x180054c65  xor     ecx, ecx
0x180054c67  test    rax, rax
0x180054c6a  jz      loc_180054EEE
0x180054c70  mov     r14, rax
0x180054c73  test    r15d, r15d
0x180054c76  jz      short loc_180054C8C
0x180054c78  mov     rcx, r14; this
0x180054c7b  call    ??0ns@sax@win_musl@@QEAA@XZ; win_musl::sax::ns::ns(void)
0x180054c80  add     r14, 10h
0x180054c84  xor     ecx, ecx
0x180054c86  sub     rbx, 1
0x180054c8a  jnz     short loc_180054C78
0x180054c8c  mov     r14, [rsp+2A0h+var_240]
0x180054c91  mov     rbx, rcx
0x180054c94  test    rdi, rdi
0x180054c97  cmovnz  rbx, rdi
0x180054c9b  mov     [rbp+1A0h+var_210], rbx
0x180054c9f  mov     edx, ecx
0x180054ca1  test    r15d, r15d
0x180054ca4  jz      short loc_180054CD9
0x180054ca6  mov     eax, edx
0x180054ca8  mov     r8, [r14+rax*8]
0x180054cac  or      rax, 0FFFFFFFFFFFFFFFFh
0x180054cb0  inc     rax
0x180054cb3  cmp     [r8+rax*2], cx
0x180054cb8  jnz     short loc_180054CB0
0x180054cba  movsxd  rcx, edx
0x180054cbd  add     rcx, rcx
0x180054cc0  mov     [rbx+rcx*8], r8
0x180054cc4  lea     rax, [r8+rax*2]
0x180054cc8  mov     [rbx+rcx*8+8], rax
0x180054ccd  inc     edx
0x180054ccf  cmp     edx, r15d
0x180054cd2  mov     ecx, 0
0x180054cd7  jb      short loc_180054CA6
0x180054cd9  mov     r8, r15
0x180054cdc  shl     r8, 4
0x180054ce0  add     r8, rbx
0x180054ce3  mov     rdx, rbx
0x180054ce6  lea     rcx, [rsp+2A0h+var_240]
0x180054ceb  call    ??$CreateMarkupQueryKnownNs@PEAUns@sax@win_musl@@@consumption@win_musl@@YA?AVMarkupQuery@01@PEAUns@sax@1@0@Z; win_musl::consumption::CreateMarkupQueryKnownNs<win_musl::sax::ns *>(win_musl::sax::ns *,win_musl::sax::ns *)
0x180054cf0  nop
0x180054cf1  xor     eax, eax
0x180054cf3  mov     [rsp+2A0h+pv], rax
0x180054cf8  mov     dword ptr [rsp+2A0h+var_258], eax
0x180054cfc  mov     dword ptr [rsp+2A0h+var_238], eax
0x180054d00  lea     r14, [rsp+2A0h+var_238]
0x180054d05  test    r13, r13
0x180054d08  cmovnz  r14, r13
0x180054d0c  lea     r15, [rsp+2A0h+var_258]
0x180054d11  xor     r13d, r13d
0x180054d14  test    r12, r12
0x180054d17  cmovnz  r15, r12
0x180054d1b  test    rsi, rsi
0x180054d1e  jz      loc_180054EDF
0x180054d24  mov     rdi, rsi
0x180054d27  mov     ecx, 60h ; '`'; unsigned __int64
0x180054d2c  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180054d31  mov     [rbp+1A0h+var_208], rax
0x180054d35  test    rax, rax
0x180054d38  jz      loc_180054ED7
0x180054d3e  mov     [rsp+30h], r14; unsigned int *
0x180054d43  mov     [rsp+2A0h+var_278], r15; unsigned int *
0x180054d48  mov     [rsp+2A0h+var_280], rdi; wchar_t **
0x180054d4d  mov     r9, [rsp+2A0h+var_260]; struct win_musl::consumption::SaxErrorHandler *
0x180054d52  mov     r8, [rsp+2A0h+var_230]; struct win_musl::consumption::SaxContentHandler *
0x180054d57  lea     rdx, [rsp+2A0h+var_240]; struct win_musl::consumption::MarkupQuery *
0x180054d5c  mov     rcx, rax; this
0x180054d5f  call    ??0AppxXmlPreprocessor@consumption@win_musl@@QEAA@AEAVMarkupQuery@12@AEBVSaxContentHandler@12@AEBVSaxErrorHandler@12@PEAPEA_WPEAK4@Z; win_musl::consumption::AppxXmlPreprocessor::AppxXmlPreprocessor(win_musl::consumption::MarkupQuery &,win_musl::consumption::SaxContentHandler const &,win_musl::consumption::SaxErrorHandler const &,wchar_t * *,ulong *,ulong *)
0x180054d64  nop
0x180054d65  mov     rdx, rax
0x180054d68  lea     rcx, [rbp+1A0h+var_220]
0x180054d6c  call    ??0?$scope@PEAVAppxXmlPreprocessor@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVAppxXmlPreprocessor@consumption@win_musl@@@Z; win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>(win_musl::consumption::AppxXmlPreprocessor *)
0x180054d71  nop
0x180054d72  lea     rdx, [rbp+1A0h+var_220]
0x180054d76  lea     rcx, [rsp+2A0h+ppv]; ppv
0x180054d7b  call    ??$CreateSaxParser@V?$scope@PEAVAppxXmlPreprocessor@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@consumption@win_musl@@YA?AV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAV?$scope@PEAVAppxXmlPreprocessor@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@@Z; win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>> &)
0x180054d80  nop
0x180054d81  xorps   xmm0, xmm0
0x180054d84  xor     edi, edi
0x180054d86  movups  [rbp+1A0h+var_1F0], xmm0
0x180054d8a  lea     eax, [rdi+0Dh]
0x180054d8d  mov     word ptr [rbp+1A0h+var_1F0], ax
0x180054d91  lea     rdx, [rsp+2A0h+var_230]
0x180054d96  mov     rcx, [rsp+2A0h+var_228]
0x180054d9b  call    ?GetInterface@Stream@win_dox@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::Stream::GetInterface(void)
0x180054da0  mov     rcx, [rax]
0x180054da3  mov     qword ptr [rbp+1A0h+var_1F0+8], rcx
0x180054da7  mov     rcx, [rsp+2A0h+var_230]
0x180054dac  test    rcx, rcx
0x180054daf  jz      short loc_180054DBE
0x180054db1  mov     rax, [rcx]
0x180054db4  mov     rax, [rax+10h]
0x180054db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054dbd  nop
0x180054dbe  mov     rcx, [rsp+2A0h+ppv]
0x180054dc3  movups  xmm0, [rbp+1A0h+var_1F0]
0x180054dc7  movaps  [rbp+1A0h+var_1F0], xmm0
0x180054dcb  mov     [rbp+1A0h+var_1E0], rdi
0x180054dcf  mov     rax, [rcx]
0x180054dd2  lea     rdx, [rbp+1A0h+var_1F0]
0x180054dd6  mov     rax, [rax+98h]
0x180054ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054de2  mov     r12d, eax
0x180054de5  test    eax, eax
0x180054de7  js      loc_180054EF6
0x180054ded  mov     rcx, r13
0x180054df0  mov     [rsp+2A0h+var_260], rcx
0x180054df5  mov     rdi, [rsp+2A0h+ppv]
0x180054dfa  test    rdi, rdi
0x180054dfd  jnz     loc_180054EA8
0x180054e03  mov     rdi, r13
0x180054e06  mov     [rsp+2A0h+var_260], rdi
0x180054e0b  test    rcx, rcx
0x180054e0e  jz      short loc_180054E1D
0x180054e10  mov     rax, [rcx]
0x180054e13  mov     rax, [rax+10h]
0x180054e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e1c  nop
0x180054e1d  lea     rcx, [rsp+2A0h+var_260]
0x180054e22  call    ?ValidateSaxEncoding@consumption@win_musl@@YAXV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@J@Z; win_musl::consumption::ValidateSaxEncoding(win_scope::scope<ISAXXMLReader *,win_scope::const_policies<win_scope::com_policies>>,long)
0x180054e27  nop
0x180054e28  mov     rcx, [rsp+2A0h+ppv]
0x180054e2d  test    rcx, rcx
0x180054e30  jnz     loc_180054EC1
0x180054e36  cmp     [rbp+1A0h+var_218], r13
0x180054e3a  jz      short loc_180054E4C
0x180054e3c  cmp     [rbp+1A0h+var_220], r13
0x180054e40  jz      short loc_180054E4C
0x180054e42  lea     rcx, [rbp+1A0h+var_220]
0x180054e46  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180054e4b  nop
0x180054e4c  mov     rcx, [rsp+2A0h+pv]; pv
0x180054e51  test    rcx, rcx
0x180054e54  jnz     loc_180054FE6
0x180054e5a  mov     rcx, [rsp+2A0h+var_240]
0x180054e5f  test    rcx, rcx
0x180054e62  jz      short loc_180054E71
0x180054e64  mov     rax, [rcx]
0x180054e67  mov     rax, [rax+10h]
0x180054e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e70  nop
0x180054e71  test    rbx, rbx
0x180054e74  jz      short loc_180054E7E
0x180054e76  mov     rcx, rbx; Block
0x180054e79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180054e7e  mov     rcx, [rbp+1A0h+var_40]
0x180054e85  xor     rcx, rsp; StackCookie
0x180054e88  call    __security_check_cookie
0x180054e8d  mov     rbx, [rsp+2A0h+arg_18]
0x180054e95  add     rsp, 270h
0x180054e9c  pop     r15
0x180054e9e  pop     r14
0x180054ea0  pop     r13
0x180054ea2  pop     r12
0x180054ea4  pop     rdi
0x180054ea5  pop     rsi
0x180054ea6  pop     rbp
0x180054ea7  retn
0x180054ea8  mov     rax, [rdi]
0x180054eab  mov     rcx, rdi
0x180054eae  mov     rax, [rax+8]
0x180054eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054eb7  mov     rcx, [rsp+2A0h+var_260]
0x180054ebc  jmp     loc_180054E06
0x180054ec1  mov     rax, [rcx]
0x180054ec4  mov     rax, [rax+10h]
0x180054ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ecd  mov     [rsp+2A0h+ppv], r13
0x180054ed2  jmp     loc_180054E36
0x180054ed7  mov     rax, r13
0x180054eda  jmp     loc_180054D65
0x180054edf  mov     [rsp+2A0h+pv], r13
0x180054ee4  lea     rdi, [rsp+2A0h+pv]
0x180054ee9  jmp     loc_180054D27
0x180054eee  mov     rdi, rcx
0x180054ef1  jmp     loc_180054C91
0x180054ef6  test    rsi, rsi
0x180054ef9  jz      short loc_180054F00
0x180054efb  mov     rdi, [rsi]
0x180054efe  jmp     short loc_180054F05
0x180054f00  mov     rdi, [rsp+2A0h+pv]
0x180054f05  lea     rdx, aSaxParseFailed; "Sax Parse failed <Line Number: %{line},"...
0x180054f0c  lea     rcx, [rbp+1A0h+var_1F0]
0x180054f10  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180054f15  nop
0x180054f16  lea     rdx, [rbp+1A0h+var_1F0]
0x180054f1a  lea     rcx, [rbp+1A0h+var_A0]
0x180054f21  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180054f26  mov     rbx, rax
0x180054f29  lea     rdx, aLine; "line"
0x180054f30  lea     rcx, [rbp+1A0h+var_1C0]
0x180054f34  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180054f39  nop
0x180054f3a  mov     r8, r15
0x180054f3d  lea     rdx, [rbp+1A0h+var_1C0]
0x180054f41  mov     rcx, rbx
0x180054f44  call    ??$insert@K@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBK@Z; win_musl::Formatter::insert<ulong>(std::wstring const &,ulong const &)
0x180054f49  mov     rbx, rax
0x180054f4c  lea     rdx, aCol; "col"
0x180054f53  lea     rcx, [rbp+1A0h+var_198]
0x180054f57  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180054f5c  nop
0x180054f5d  mov     r8, r14
0x180054f60  lea     rdx, [rbp+1A0h+var_198]
0x180054f64  mov     rcx, rbx
0x180054f67  call    ??$insert@K@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBK@Z; win_musl::Formatter::insert<ulong>(std::wstring const &,ulong const &)
0x180054f6c  mov     rbx, rax
0x180054f6f  lea     rcx, psz
0x180054f76  test    rdi, rdi
0x180054f79  cmovnz  rcx, rdi
0x180054f7d  mov     [rsp+2A0h+var_228], rcx
0x180054f82  lea     rdx, aMessage; "message"
0x180054f89  lea     rcx, [rbp+1A0h+var_170]
0x180054f8d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180054f92  nop
0x180054f93  lea     r8, [rsp+2A0h+var_228]
0x180054f98  lea     rdx, [rbp+1A0h+var_170]
0x180054f9c  mov     rcx, rbx
0x180054f9f  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x180054fa4  mov     rcx, rax; this
0x180054fa7  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180054fac  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180054fb1  mov     dword ptr [rsp+2A0h+var_278], r12d; unsigned int
0x180054fb6  mov     dword ptr [rsp+2A0h+var_280], 5Dh ; ']'; unsigned int
0x180054fbe  lea     r9, word_18013A0B6
0x180054fc5  lea     r8, aNoFilename; "(no filename)"
0x180054fcc  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x180054fd0  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180054fd5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180054fdc  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x180054fe0  call    _CxxThrowException_0
0x180054fe6  call    cs:__imp_CoTaskMemFree
0x180054fec  mov     [rsp+2A0h+pv], r13
0x180054ff1  jmp     loc_180054E5A
```

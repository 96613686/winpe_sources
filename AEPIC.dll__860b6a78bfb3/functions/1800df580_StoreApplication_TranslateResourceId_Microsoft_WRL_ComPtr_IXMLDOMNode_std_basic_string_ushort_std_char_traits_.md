# StoreApplication::TranslateResourceId(Microsoft::WRL::ComPtr<IXMLDOMNode> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800df580`
- end: `0x1800dfbf1`
- name: `?TranslateResourceId@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `1649`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dfbf8`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000ed74`
- `0x18000faac`
- `0x18000faf0`
- `0x1800108a8`
- `0x18001c5f0`
- `0x18001c6d8`
- `0x1800c97f0`
- `0x1800c9810`
- `0x1800ca3fc`
- `0x1800ca928`
- `0x1800cc8cc`
- `0x1800ceab0`
- `0x1800cff18`
- `0x1800d00c0`
- `0x1800d940c`
- `0x1800d94a8`
- `0x1800d9514`
- `0x1800d9758`
- `0x1800d994c`
- `0x1800df580`
- `0x1800dfe24`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800df8cd`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800df964`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800dfa37`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800dfac2`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800df8cd`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800df964`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800dfa37`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800dfac2`
- `OLEAUT32!__imp_VariantInit` at `0x1800df75c`
- `OLEAUT32!__imp_VariantInit` at `0x1800df75c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800df76c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800df76c`

## string_xrefs

- `0x1800df5f0`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800df613`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800df690`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800df736`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
__int64 __fastcall StoreApplication::TranslateResourceId(
        _QWORD *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  HRESULT v19; // eax
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 v23; // rcx
  WCHAR *v24; // rdx
  const WCHAR *v25; // rcx
  PWSTR *v26; // rdx
  PWSTR v27; // rcx
  unsigned __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rax
  WCHAR *v31; // rdx
  const WCHAR *v32; // rcx
  PWSTR *v33; // rdx
  __int64 v34; // rax
  __int64 last_of; // rax
  __int64 v36; // rax
  WCHAR *v37; // rdx
  const WCHAR *v38; // rcx
  PWSTR *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rax
  WCHAR *v42; // rdx
  const WCHAR *v43; // rcx
  PWSTR *v44; // rax
  __int64 v45; // rdi
  void (__fastcall *v46)(__int64, VARIANTARG *); // rbx
  PWSTR *v47; // rdx
  __int64 v48; // rbx
  void (__fastcall *v49)(__int64, VARIANTARG *); // rdi
  int v51; // [rsp+20h] [rbp-E0h]
  __int64 v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v54[2]; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvargSrc; // [rsp+70h] [rbp-90h] BYREF
  PWSTR pszOutBuf[2]; // [rsp+88h] [rbp-78h] BYREF
  UINT cchOutBuf[2]; // [rsp+98h] [rbp-68h]
  unsigned __int64 v59; // [rsp+A0h] [rbp-60h]
  _QWORD v60[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B8h] [rbp-48h]
  PCWSTR pszSource[3]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v63; // [rsp+E0h] [rbp-20h]
  wchar_t Buffer[16]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD Src[3]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v66[3]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v67[16]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v68; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v53 = 0;
  v8 = *a1;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a1 + 136LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  v10 = v9(v8, &v53);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7DB,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      v51);
  v12 = v53;
  if ( !v53 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x7DC,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      v11);
  if ( !*((_QWORD *)a3 + 2) )
  {
LABEL_17:
    memset(&pvargSrc, 0, sizeof(pvargSrc));
    pvargSrc.vt = 13;
    v18 = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *))(*(_QWORD *)*a1 + 240LL))(*a1, &pvargSrc);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7F1,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v51);
    VariantInit(&pvarg);
    v19 = VariantCopy(&pvarg, &pvargSrc);
    _com_util::CheckError(v19);
    v20 = _bstr_t::_bstr_t((_bstr_t *)v54, (const struct _variant_t *)&pvarg);
    if ( *(_QWORD *)v20 )
      v21 = **(_QWORD **)v20;
    else
      v21 = 0;
    std::wstring::wstring(v60, v21);
    _bstr_t::_Free((_bstr_t *)v54);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    std::wstring::wstring(v66, v60);
    if ( !v61 )
      goto LABEL_73;
    std::wstring::wstring(v67, L"ms-resource:");
    if ( std::wstring::find(v60, v67) )
    {
LABEL_72:
      std::wstring::_Tidy_deallocate(v67);
LABEL_73:
      std::wstring::_Tidy_deallocate(v66);
      std::wstring::_Tidy_deallocate(v60);
      return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    }
    v22 = -1;
    std::wstring::wstring(Buffer, v60, v68, -1);
    std::wstring::operator=(v60, Buffer);
    std::wstring::_Tidy_deallocate(Buffer);
    Utility::TrimChar(v23, v60);
    Utility::GetDirectoryFromPath(Src, a2);
    std::wstring::_Append<unsigned short>(Src);
    Utility::FormatWstring((wchar_t *)pszSource, (wchar_t *)L"@{%ws? ms-resource://%ws/resources/%ws}");
    *(_OWORD *)pszOutBuf = 0;
    *(_QWORD *)cchOutBuf = 0;
    v59 = 7;
    LOWORD(pszOutBuf[0]) = 0;
    std::wstring::resize(pszOutBuf, 260);
    v24 = (WCHAR *)pszOutBuf;
    if ( v59 > 7 )
      v24 = pszOutBuf[0];
    v25 = (const WCHAR *)pszSource;
    if ( v63 > 7 )
      v25 = pszSource[0];
    SHLoadIndirectString(v25, v24, cchOutBuf[0], 0);
    v26 = pszOutBuf;
    v27 = pszOutBuf[0];
    v28 = v59;
    if ( v59 > 7 )
      v26 = (PWSTR *)pszOutBuf[0];
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v26 + v29) );
    if ( !v29 )
    {
      v30 = Utility::FormatWstring(Buffer, (wchar_t *)L"@{%ws? ms-resource://%ws/%ws}");
      std::wstring::operator=(pszSource, v30);
      std::wstring::_Tidy_deallocate(Buffer);
      v31 = (WCHAR *)pszOutBuf;
      if ( v59 > 7 )
        v31 = pszOutBuf[0];
      v32 = (const WCHAR *)pszSource;
      if ( v63 > 7 )
        v32 = pszSource[0];
      SHLoadIndirectString(v32, v31, cchOutBuf[0], 0);
      v33 = pszOutBuf;
      v27 = pszOutBuf[0];
      v28 = v59;
      if ( v59 > 7 )
        v33 = (PWSTR *)pszOutBuf[0];
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v33 + v34) );
      if ( !v34 )
      {
        last_of = std::wstring::find_last_of(v60, 47);
        if ( last_of != -1 )
        {
          std::wstring::wstring(Buffer, v60, last_of + 1, v61);
          std::wstring::operator=(v60, Buffer);
          std::wstring::_Tidy_deallocate(Buffer);
        }
        v36 = Utility::FormatWstring(Buffer, (wchar_t *)L"@{%ws? ms-resource://%ws/%ws}");
        std::wstring::operator=(pszSource, v36);
        std::wstring::_Tidy_deallocate(Buffer);
        v37 = (WCHAR *)pszOutBuf;
        if ( v59 > 7 )
          v37 = pszOutBuf[0];
        v38 = (const WCHAR *)pszSource;
        if ( v63 > 7 )
          v38 = pszSource[0];
        SHLoadIndirectString(v38, v37, cchOutBuf[0], 0);
        v39 = pszOutBuf;
        v27 = pszOutBuf[0];
        v28 = v59;
        if ( v59 > 7 )
          v39 = (PWSTR *)pszOutBuf[0];
        v40 = -1;
        do
          ++v40;
        while ( *((_WORD *)v39 + v40) );
        if ( !v40 )
        {
          v41 = Utility::FormatWstring(Buffer, (wchar_t *)L"@{%ws? %ws}");
          std::wstring::operator=(pszSource, v41);
          std::wstring::_Tidy_deallocate(Buffer);
          v42 = (WCHAR *)pszOutBuf;
          if ( v59 > 7 )
            v42 = pszOutBuf[0];
          v43 = (const WCHAR *)pszSource;
          if ( v63 > 7 )
            v43 = pszSource[0];
          SHLoadIndirectString(v43, v42, cchOutBuf[0], 0);
          v28 = v59;
          v27 = pszOutBuf[0];
        }
      }
    }
    v44 = pszOutBuf;
    if ( v28 > 7 )
      v44 = (PWSTR *)v27;
    do
      ++v22;
    while ( *((_WORD *)v44 + v22) );
    if ( v22 )
    {
      v45 = *a1;
      v46 = *(void (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)*a1 + 248LL);
      v47 = pszOutBuf;
      if ( v28 > 7 )
        v47 = (PWSTR *)v27;
      pvarg = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)Buffer, (const unsigned __int16 *)v47);
      v46(v45, &pvarg);
    }
    else
    {
      if ( !*((_QWORD *)a4 + 2) )
      {
LABEL_71:
        std::wstring::_Tidy_deallocate(pszOutBuf);
        std::wstring::_Tidy_deallocate(pszSource);
        std::wstring::_Tidy_deallocate(Src);
        goto LABEL_72;
      }
      v48 = *a1;
      v49 = *(void (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)*a1 + 248LL);
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const unsigned __int16 **)a4;
      pvarg = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)Buffer, a4);
      v49(v48, &pvarg);
    }
    _variant_t::~_variant_t((_variant_t *)Buffer);
    goto LABEL_71;
  }
  v52 = 0;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const unsigned __int16 **)a3;
  v14 = _bstr_t::_bstr_t((_bstr_t *)v54, a3);
  if ( *(_QWORD *)v14 )
    v15 = **(_QWORD **)v14;
  else
    v15 = 0;
  v16 = v13(v12, v15, &v52);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7E2,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v16,
      v51);
  _bstr_t::_Free((_bstr_t *)v54);
  v17 = v52;
  if ( v52 )
  {
    if ( *a1 != v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
      v54[0] = *a1;
      *a1 = v17;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v54);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    goto LABEL_17;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
}

```

## disassembly

```asm
0x1800df580  push    rbp
0x1800df582  push    rbx
0x1800df583  push    rsi
0x1800df584  push    rdi
0x1800df585  push    r12
0x1800df587  push    r13
0x1800df589  push    r14
0x1800df58b  push    r15
0x1800df58d  lea     rbp, [rsp-78h]
0x1800df592  sub     rsp, 178h
0x1800df599  mov     rax, cs:__security_cookie
0x1800df5a0  xor     rax, rsp
0x1800df5a3  mov     [rbp+0B0h+var_48], rax
0x1800df5a7  mov     r15, r9
0x1800df5aa  mov     rsi, r8
0x1800df5ad  mov     r12, rdx
0x1800df5b0  mov     r14, rcx
0x1800df5b3  xor     r13d, r13d
0x1800df5b6  mov     [rsp+1B0h+var_178], r13
0x1800df5bb  mov     rdi, [rcx]
0x1800df5be  mov     rax, [rdi]
0x1800df5c1  mov     rbx, [rax+88h]
0x1800df5c8  lea     rcx, [rsp+1B0h+var_178]
0x1800df5cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800df5d2  lea     rdx, [rsp+1B0h+var_178]
0x1800df5d7  mov     rcx, rdi
0x1800df5da  mov     rax, rbx
0x1800df5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df5e2  mov     rcx, [rbp+0B8h]; this
0x1800df5e9  test    eax, eax
0x1800df5eb  jns     short loc_1800DF602
0x1800df5ed  mov     r9d, eax; char *
0x1800df5f0  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800df5f7  mov     edx, 7DBh; void *
0x1800df5fc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800df602  mov     rcx, [rbp+0B8h]; this
0x1800df609  mov     rbx, [rsp+1B0h+var_178]
0x1800df60e  test    rbx, rbx
0x1800df611  jnz     short loc_1800DF625
0x1800df613  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800df61a  mov     edx, 7DCh; void *
0x1800df61f  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800df625  mov     edi, 7
0x1800df62a  cmp     [rsi+10h], r13
0x1800df62e  jbe     loc_1800DF6F9
0x1800df634  mov     [rsp+1B0h+var_180], r13
0x1800df639  mov     rax, [rbx]
0x1800df63c  mov     rdi, [rax+38h]
0x1800df640  lea     rcx, [rsp+1B0h+var_180]
0x1800df645  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800df64a  cmp     qword ptr [rsi+18h], 7
0x1800df64f  jbe     short loc_1800DF654
0x1800df651  mov     rsi, [rsi]
0x1800df654  mov     rdx, rsi; unsigned __int16 *
0x1800df657  lea     rcx, [rsp+1B0h+var_170]; this
0x1800df65c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800df661  nop
0x1800df662  mov     rdx, [rax]
0x1800df665  test    rdx, rdx
0x1800df668  jz      short loc_1800DF66F
0x1800df66a  mov     rdx, [rdx]
0x1800df66d  jmp     short loc_1800DF672
0x1800df66f  mov     rdx, r13
0x1800df672  lea     r8, [rsp+1B0h+var_180]
0x1800df677  mov     rcx, rbx
0x1800df67a  mov     rax, rdi
0x1800df67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df682  mov     rcx, [rbp+0B8h]; this
0x1800df689  test    eax, eax
0x1800df68b  jns     short loc_1800DF6A2
0x1800df68d  mov     r9d, eax; char *
0x1800df690  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800df697  mov     edx, 7E2h; void *
0x1800df69c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800df6a2  lea     rcx, [rsp+1B0h+var_170]; this
0x1800df6a7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800df6ac  mov     rbx, [rsp+1B0h+var_180]
0x1800df6b1  test    rbx, rbx
0x1800df6b4  jz      loc_1800DF748
0x1800df6ba  cmp     [r14], rbx
0x1800df6bd  jz      short loc_1800DF6EA
0x1800df6bf  test    rbx, rbx
0x1800df6c2  jz      short loc_1800DF6D4
0x1800df6c4  mov     rax, [rbx]
0x1800df6c7  mov     rcx, rbx
0x1800df6ca  mov     rax, [rax+8]
0x1800df6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df6d3  nop
0x1800df6d4  mov     rax, [r14]
0x1800df6d7  mov     [rsp+1B0h+var_170], rax
0x1800df6dc  mov     [r14], rbx
0x1800df6df  lea     rcx, [rsp+1B0h+var_170]
0x1800df6e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800df6e9  nop
0x1800df6ea  lea     rcx, [rsp+1B0h+var_180]
0x1800df6ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800df6f4  mov     edi, 7
0x1800df6f9  xorps   xmm0, xmm0
0x1800df6fc  xor     eax, eax
0x1800df6fe  movups  xmmword ptr [rsp+1B0h+pvargSrc], xmm0
0x1800df703  mov     qword ptr [rbp+0B0h+pvargSrc+10h], rax
0x1800df707  mov     eax, 0Dh
0x1800df70c  mov     word ptr [rsp+1B0h+pvargSrc], ax
0x1800df711  mov     rcx, [r14]
0x1800df714  mov     rax, [rcx]
0x1800df717  lea     rdx, [rsp+1B0h+pvargSrc]
0x1800df71c  mov     rax, [rax+0F0h]
0x1800df723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df728  mov     rcx, [rbp+0B8h]; this
0x1800df72f  test    eax, eax
0x1800df731  jns     short loc_1800DF757
0x1800df733  mov     r9d, eax; char *
0x1800df736  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800df73d  mov     edx, 7F1h; void *
0x1800df742  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800df748  lea     rcx, [rsp+1B0h+var_180]
0x1800df74d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800df752  jmp     loc_1800DFBC7
0x1800df757  lea     rcx, [rsp+1B0h+pvarg]; pvarg
0x1800df75c  call    cs:__imp_VariantInit
0x1800df762  lea     rdx, [rsp+1B0h+pvargSrc]; pvargSrc
0x1800df767  lea     rcx, [rsp+1B0h+pvarg]; pvargDest
0x1800df76c  call    cs:__imp_VariantCopy
0x1800df772  mov     ecx, eax; int
0x1800df774  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x1800df779  nop
0x1800df77a  lea     rdx, [rsp+1B0h+pvarg]; struct _variant_t *
0x1800df77f  lea     rcx, [rsp+1B0h+var_170]; this
0x1800df784  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x1800df789  nop
0x1800df78a  mov     rdx, [rax]
0x1800df78d  test    rdx, rdx
0x1800df790  jz      short loc_1800DF797
0x1800df792  mov     rdx, [rdx]
0x1800df795  jmp     short loc_1800DF79A
0x1800df797  mov     rdx, r13
0x1800df79a  lea     rcx, [rbp+0B0h+var_108]
0x1800df79e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df7a3  nop
0x1800df7a4  lea     rcx, [rsp+1B0h+var_170]; this
0x1800df7a9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800df7ae  nop
0x1800df7af  lea     rcx, [rsp+1B0h+pvarg]; this
0x1800df7b4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800df7b9  lea     rdx, [rbp+0B0h+var_108]
0x1800df7bd  lea     rcx, [rbp+0B0h+var_88]
0x1800df7c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800df7c6  nop
0x1800df7c7  cmp     [rbp+0B0h+var_F8], r13
0x1800df7cb  jz      loc_1800DFBB3
0x1800df7d1  lea     rdx, aMsResource; "ms-resource:"
0x1800df7d8  lea     rcx, [rbp+0B0h+var_68]
0x1800df7dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df7e1  nop
0x1800df7e2  lea     rdx, [rbp+0B0h+var_68]
0x1800df7e6  lea     rcx, [rbp+0B0h+var_108]
0x1800df7ea  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800df7ef  test    rax, rax
0x1800df7f2  jnz     loc_1800DFBA9
0x1800df7f8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800df7fc  mov     r9, rbx
0x1800df7ff  mov     r8, [rbp+0B0h+var_58]
0x1800df803  lea     rdx, [rbp+0B0h+var_108]
0x1800df807  lea     rcx, [rbp+0B0h+Buffer]
0x1800df80b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800df810  lea     rdx, [rbp+0B0h+Buffer]
0x1800df814  lea     rcx, [rbp+0B0h+var_108]
0x1800df818  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800df81d  lea     rcx, [rbp+0B0h+Buffer]
0x1800df821  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df826  lea     rdx, [rbp+0B0h+var_108]
0x1800df82a  call    ?TrimChar@Utility@@SAXDAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::TrimChar(char,std::wstring &)
0x1800df82f  mov     rdx, r12
0x1800df832  lea     rcx, [rbp+0B0h+Src]
0x1800df836  call    ?GetDirectoryFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetDirectoryFromPath(std::wstring const &)
0x1800df83b  nop
0x1800df83c  lea     r8d, [rbx+0Fh]
0x1800df840  lea     rdx, aResourcesPri; "\\resources.pri"
0x1800df847  lea     rcx, [rbp+0B0h+Src]; Src
0x1800df84b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800df850  lea     rax, [rbp+0B0h+var_108]
0x1800df854  cmp     [rbp+0B0h+var_F0], rdi
0x1800df858  cmova   rax, [rbp+0B0h+var_108]
0x1800df85d  lea     r8, [rbp+0B0h+Src]
0x1800df861  cmp     [rbp+0B0h+var_90], rdi
0x1800df865  cmova   r8, [rbp+0B0h+Src]
0x1800df86a  mov     qword ptr [rsp+1B0h+var_190], rax
0x1800df86f  lea     rsi, pszFormat
0x1800df876  mov     r9, rsi
0x1800df879  lea     rdx, aWsMsResourceWs; "@{%ws? ms-resource://%ws/resources/%ws}"
0x1800df880  lea     rcx, [rbp+0B0h+pszSource]; Buffer
0x1800df884  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x1800df889  nop
0x1800df88a  xorps   xmm0, xmm0
0x1800df88d  movups  xmmword ptr [rbp+0B0h+pszOutBuf], xmm0
0x1800df891  mov     qword ptr [rbp+0B0h+cchOutBuf], r13
0x1800df895  mov     [rbp+0B0h+var_110], rdi
0x1800df899  mov     word ptr [rbp+0B0h+pszOutBuf], r13w
0x1800df89e  mov     edx, 104h
0x1800df8a3  lea     rcx, [rbp+0B0h+pszOutBuf]
0x1800df8a7  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800df8ac  lea     rdx, [rbp+0B0h+pszOutBuf]
0x1800df8b0  cmp     [rbp+0B0h+var_110], rdi
0x1800df8b4  cmova   rdx, [rbp+0B0h+pszOutBuf]; pszOutBuf
0x1800df8b9  lea     rcx, [rbp+0B0h+pszSource]
0x1800df8bd  cmp     [rbp+0B0h+var_D0], rdi
0x1800df8c1  cmova   rcx, [rbp+0B0h+pszSource]; pszSource
0x1800df8c6  xor     r9d, r9d; ppvReserved
0x1800df8c9  mov     r8d, [rbp+0B0h+cchOutBuf]; cchOutBuf
0x1800df8cd  call    cs:__imp_SHLoadIndirectString
0x1800df8d3  lea     rdx, [rbp+0B0h+pszOutBuf]
0x1800df8d7  mov     rcx, [rbp+0B0h+pszOutBuf]
0x1800df8db  mov     r8, [rbp+0B0h+var_110]
0x1800df8df  cmp     r8, rdi
0x1800df8e2  cmova   rdx, rcx
0x1800df8e6  mov     rax, rbx
0x1800df8e9  inc     rax
0x1800df8ec  cmp     [rdx+rax*2], r13w
0x1800df8f1  jnz     short loc_1800DF8E9
0x1800df8f3  test    rax, rax
0x1800df8f6  jnz     loc_1800DFAD0
0x1800df8fc  lea     rax, [rbp+0B0h+var_108]
0x1800df900  cmp     [rbp+0B0h+var_F0], rdi
0x1800df904  cmova   rax, [rbp+0B0h+var_108]
0x1800df909  lea     r8, [rbp+0B0h+Src]
0x1800df90d  cmp     [rbp+0B0h+var_90], rdi
0x1800df911  cmova   r8, [rbp+0B0h+Src]
0x1800df916  mov     qword ptr [rsp+1B0h+var_190], rax
0x1800df91b  mov     r9, rsi
0x1800df91e  lea     rdx, aWsMsResourceWs_0; "@{%ws? ms-resource://%ws/%ws}"
0x1800df925  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x1800df929  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x1800df92e  mov     rdx, rax
0x1800df931  lea     rcx, [rbp+0B0h+pszSource]
0x1800df935  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800df93a  lea     rcx, [rbp+0B0h+Buffer]
0x1800df93e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df943  lea     rdx, [rbp+0B0h+pszOutBuf]
0x1800df947  cmp     [rbp+0B0h+var_110], rdi
0x1800df94b  cmova   rdx, [rbp+0B0h+pszOutBuf]; pszOutBuf
0x1800df950  lea     rcx, [rbp+0B0h+pszSource]
0x1800df954  cmp     [rbp+0B0h+var_D0], rdi
0x1800df958  cmova   rcx, [rbp+0B0h+pszSource]; pszSource
0x1800df95d  xor     r9d, r9d; ppvReserved
0x1800df960  mov     r8d, [rbp+0B0h+cchOutBuf]; cchOutBuf
0x1800df964  call    cs:__imp_SHLoadIndirectString
0x1800df96a  lea     rdx, [rbp+0B0h+pszOutBuf]
0x1800df96e  mov     rcx, [rbp+0B0h+pszOutBuf]
0x1800df972  mov     r8, [rbp+0B0h+var_110]
0x1800df976  cmp     r8, rdi
0x1800df979  cmova   rdx, rcx
0x1800df97d  mov     rax, rbx
0x1800df980  inc     rax
0x1800df983  cmp     [rdx+rax*2], r13w
0x1800df988  jnz     short loc_1800DF980
0x1800df98a  test    rax, rax
0x1800df98d  jnz     loc_1800DFAD0
0x1800df993  lea     edx, [rax+2Fh]
0x1800df996  lea     rcx, [rbp+0B0h+var_108]
0x1800df99a  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x1800df99f  cmp     rax, rbx
0x1800df9a2  jz      short loc_1800DF9CF
0x1800df9a4  lea     r8, [rax+1]
0x1800df9a8  mov     r9, [rbp+0B0h+var_F8]
0x1800df9ac  lea     rdx, [rbp+0B0h+var_108]
0x1800df9b0  lea     rcx, [rbp+0B0h+Buffer]
0x1800df9b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800df9b9  lea     rdx, [rbp+0B0h+Buffer]
0x1800df9bd  lea     rcx, [rbp+0B0h+var_108]
0x1800df9c1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800df9c6  lea     rcx, [rbp+0B0h+Buffer]
0x1800df9ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df9cf  lea     rax, [rbp+0B0h+var_108]
0x1800df9d3  cmp     [rbp+0B0h+var_F0], rdi
0x1800df9d7  cmova   rax, [rbp+0B0h+var_108]
0x1800df9dc  lea     r8, [rbp+0B0h+Src]
0x1800df9e0  cmp     [rbp+0B0h+var_90], rdi
0x1800df9e4  cmova   r8, [rbp+0B0h+Src]
0x1800df9e9  mov     qword ptr [rsp+1B0h+var_190], rax
0x1800df9ee  mov     r9, rsi
0x1800df9f1  lea     rdx, aWsMsResourceWs_0; "@{%ws? ms-resource://%ws/%ws}"
0x1800df9f8  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x1800df9fc  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x1800dfa01  mov     rdx, rax
0x1800dfa04  lea     rcx, [rbp+0B0h+pszSource]
0x1800dfa08  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800dfa0d  lea     rcx, [rbp+0B0h+Buffer]
0x1800dfa11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dfa16  lea     rdx, [rbp+0B0h+pszOutBuf]
0x1800dfa1a  cmp     [rbp+0B0h+var_110], rdi
0x1800dfa1e  cmova   rdx, [rbp+0B0h+pszOutBuf]; pszOutBuf
0x1800dfa23  lea     rcx, [rbp+0B0h+pszSource]
0x1800dfa27  cmp     [rbp+0B0h+var_D0], rdi
0x1800dfa2b  cmova   rcx, [rbp+0B0h+pszSource]; pszSource
0x1800dfa30  xor     r9d, r9d; ppvReserved
0x1800dfa33  mov     r8d, [rbp+0B0h+cchOutBuf]; cchOutBuf
0x1800dfa37  call    cs:__imp_SHLoadIndirectString
0x1800dfa3d  lea     rdx, [rbp+0B0h+pszOutBuf]
0x1800dfa41  mov     rcx, [rbp+0B0h+pszOutBuf]
0x1800dfa45  mov     r8, [rbp+0B0h+var_110]
  ... truncated ...
```

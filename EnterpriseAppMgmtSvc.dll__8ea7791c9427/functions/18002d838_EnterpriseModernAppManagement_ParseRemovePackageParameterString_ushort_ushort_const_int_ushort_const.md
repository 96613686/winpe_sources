# EnterpriseModernAppManagement::ParseRemovePackageParameterString(ushort *,ushort const * *,int *,ushort const * *)

- ea: `0x18002d838`
- end: `0x18002dda9`
- name: `?ParseRemovePackageParameterString@EnterpriseModernAppManagement@@YAJPEAGPEAPEBGPEAH1@Z`
- size: `1393`
- prototype: `__int64 __fastcall(EnterpriseModernAppManagement *__hidden this, unsigned __int16 *, const unsigned __int16 **, int *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001c26c`

## callees

- `0x18000715c`
- `0x18000cfe8`
- `0x18002a090`
- `0x18002d838`
- `0x180065a64`
- `0x18006a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dabe`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dbbb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dc1c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dc47`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dc60`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dabe`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dbbb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dc1c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dc47`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002dc60`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d9d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dae4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d9d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dae4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da00`
- `OLEAUT32!__imp_SysFreeString` at `0x18002db11`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da00`
- `OLEAUT32!__imp_SysFreeString` at `0x18002db11`
- `OLEAUT32!__imp_SysStringLen` at `0x18002da6c`
- `OLEAUT32!__imp_SysStringLen` at `0x18002db69`
- `OLEAUT32!__imp_SysStringLen` at `0x18002da6c`
- `OLEAUT32!__imp_SysStringLen` at `0x18002db69`
- `OLEAUT32!__imp_VariantClear` at `0x18002da26`
- `OLEAUT32!__imp_VariantClear` at `0x18002db37`
- `OLEAUT32!__imp_VariantClear` at `0x18002dc51`
- `OLEAUT32!__imp_VariantClear` at `0x18002dc6a`
- `OLEAUT32!__imp_VariantClear` at `0x18002dca1`
- `OLEAUT32!__imp_VariantClear` at `0x18002dcab`
- `OLEAUT32!__imp_VariantClear` at `0x18002dd22`
- `OLEAUT32!__imp_VariantClear` at `0x18002dd65`
- `OLEAUT32!__imp_VariantClear` at `0x18002da26`
- `OLEAUT32!__imp_VariantClear` at `0x18002db37`
- `OLEAUT32!__imp_VariantClear` at `0x18002dc51`
- `OLEAUT32!__imp_VariantClear` at `0x18002dc6a`
- `OLEAUT32!__imp_VariantClear` at `0x18002dca1`
- `OLEAUT32!__imp_VariantClear` at `0x18002dcab`
- `OLEAUT32!__imp_VariantClear` at `0x18002dd22`
- `OLEAUT32!__imp_VariantClear` at `0x18002dd65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dbe7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dc05`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dbe7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dc05`

## string_xrefs

- `0x18002dacd`: `RemoveForAllUsers`

## pseudocode

```c
__int64 __fastcall EnterpriseModernAppManagement::ParseRemovePackageParameterString(
        EnterpriseModernAppManagement *this,
        struct IXMLDOMDocument2 **a2,
        const unsigned __int16 **a3,
        int *a4)
{
  int XmlDomDocument; // eax
  unsigned int v8; // ebx
  __int64 v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  void (*v14)(void); // rax
  __int64 *v15; // rdi
  __int64 v16; // r15
  BSTR v17; // rax
  OLECHAR *v18; // rsi
  int v19; // eax
  __int64 *v20; // rdi
  __int64 v21; // r15
  BSTR v22; // rax
  OLECHAR *v23; // rsi
  int v24; // eax
  WCHAR *v25; // rdi
  int v26; // esi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-49h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-49h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG v30; // [rsp+48h] [rbp-21h] BYREF
  __int128 v31; // [rsp+60h] [rbp-9h] BYREF
  int v32; // [rsp+70h] [rbp+7h]
  LPCWCH lpString1[2]; // [rsp+78h] [rbp+Fh] BYREF
  int v34; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  __int64 *v36; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v37; // [rsp+E0h] [rbp+77h] BYREF
  int *v38; // [rsp+E8h] [rbp+7Fh] BYREF

  v38 = a4;
  *a2 = 0;
  *(_DWORD *)a3 = 0;
  v37 = 0;
  XmlDomDocument = EnterpriseModernAppManagement::CreateXmlDomDocument((EnterpriseModernAppManagement *)&v37, a2);
  v8 = XmlDomDocument;
  if ( XmlDomDocument < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BF,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)XmlDomDocument,
      bIgnoreCase);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    return v8;
  }
  v10 = v37;
  LOWORD(v38) = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, EnterpriseModernAppManagement *, int **))(*(_QWORD *)v37 + 520LL))(
          v37,
          this,
          &v38);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C3,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
    goto LABEL_7;
  }
  if ( (_WORD)v38 != 0xFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C4,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    goto LABEL_12;
  }
  v36 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v10 + 360LL))(v10, &v36);
  v12 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    if ( !v36 )
      goto LABEL_18;
    v14 = *(void (**)(void))(*v36 + 16);
    goto LABEL_17;
  }
  v15 = v36;
  memset(&pvarg, 0, sizeof(pvarg));
  v16 = *v36;
  v17 = SysAllocString(L"Name");
  v18 = v17;
  if ( !v17 )
    goto LABEL_69;
  v12 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *))(v16 + 352))(v15, v17, &pvarg);
  SysFreeString(v18);
  if ( (v12 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D0,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)v12,
      bIgnoreCase);
LABEL_23:
    VariantClear(&pvarg);
    if ( !v36 )
    {
LABEL_18:
      if ( !v10 )
        return v12;
      goto LABEL_8;
    }
    v14 = *(void (**)(void))(*v36 + 16);
LABEL_17:
    v14();
    goto LABEL_18;
  }
  if ( (pvarg.vt & 0xFFF6) != 0 || pvarg.vt == 9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    VariantClear(&pvarg);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    if ( !v10 )
      return 2147942487LL;
    goto LABEL_67;
  }
  if ( !pvarg.llVal || !SysStringLen(pvarg.bstrVal) )
  {
    v12 = -2146958844;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D3,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)0x80080204LL,
      bIgnoreCase);
    VariantClear(&pvarg);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
LABEL_7:
    if ( !v10 )
      return v12;
LABEL_8:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return v12;
  }
  v31 = 0;
  v32 = 0;
  v19 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v31, pvarg.bstrVal);
  v12 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v19,
      bIgnoreCase);
    goto LABEL_31;
  }
  v20 = v36;
  memset(&v30, 0, sizeof(v30));
  v21 = *v36;
  v22 = SysAllocString(L"RemoveForAllUsers");
  v23 = v22;
  if ( !v22 )
LABEL_69:
    ATL::AtlThrowImpl(-2147024882);
  v12 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *))(v21 + 352))(v20, v22, &v30);
  SysFreeString(v23);
  if ( (v12 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)v12,
      bIgnoreCase);
LABEL_36:
    VariantClear(&v30);
LABEL_31:
    if ( *((_QWORD *)&v31 + 1) )
      operator delete[](*((void **)&v31 + 1));
    goto LABEL_23;
  }
  if ( (v30.vt & 0xFFF6) != 0 || v30.vt == 9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    goto LABEL_51;
  }
  if ( v30.llVal && SysStringLen(v30.bstrVal) )
  {
    *(_OWORD *)lpString1 = 0;
    v34 = 0;
    v24 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)lpString1, v30.bstrVal);
    v12 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E5,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)(unsigned int)v24,
        bIgnoreCase);
      if ( lpString1[1] )
        operator delete[]((void *)lpString1[1]);
      goto LABEL_36;
    }
    v25 = (WCHAR *)lpString1[1];
    v26 = 1;
    if ( CompareStringOrdinal(lpString1[1], (int)lpString1[0], L"1", 1, 0) )
      goto LABEL_47;
    if ( CompareStringOrdinal(v25, (int)lpString1[0], L"0", 1, 0) )
    {
      v26 = 0;
LABEL_47:
      *(_DWORD *)a3 = v26;
      if ( v25 )
        operator delete[](v25);
      goto LABEL_56;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)0x80070057LL,
      bIgnoreCasea);
    if ( v25 )
      operator delete[](v25);
LABEL_51:
    VariantClear(&v30);
    if ( *((_QWORD *)&v31 + 1) )
      operator delete[](*((void **)&v31 + 1));
    VariantClear(&pvarg);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
LABEL_12:
    if ( !v10 )
      return 2147942487LL;
LABEL_67:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return 2147942487LL;
  }
  *(_DWORD *)a3 = 0;
LABEL_56:
  *a2 = (struct IXMLDOMDocument2 *)*((_QWORD *)&v31 + 1);
  VariantClear(&v30);
  VariantClear(&pvarg);
  if ( v36 )
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x18002d838  mov     [rsp-8+arg_18], r9
0x18002d83d  push    rbp
0x18002d83e  push    rbx
0x18002d83f  push    rsi
0x18002d840  push    rdi
0x18002d841  push    r12
0x18002d843  push    r14
0x18002d845  push    r15
0x18002d847  lea     rbp, [rsp-27h]
0x18002d84c  sub     rsp, 90h
0x18002d853  mov     rdi, rcx
0x18002d856  mov     qword ptr [rdx], 0
0x18002d85d  lea     rcx, [rbp+57h+arg_10]; this
0x18002d861  mov     dword ptr [r8], 0
0x18002d868  mov     r14, r8
0x18002d86b  mov     [rbp+57h+arg_10], 0
0x18002d873  mov     r12, rdx
0x18002d876  call    ?CreateXmlDomDocument@EnterpriseModernAppManagement@@YAJPEAPEAUIXMLDOMDocument2@@@Z; EnterpriseModernAppManagement::CreateXmlDomDocument(IXMLDOMDocument2 * *)
0x18002d87b  mov     ebx, eax
0x18002d87d  test    eax, eax
0x18002d87f  jns     short loc_18002D8C2
0x18002d881  mov     rcx, [rbp+5Fh]; this
0x18002d885  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002d88c  mov     r9d, eax; char *
0x18002d88f  mov     edx, 2BFh; void *
0x18002d894  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d899  mov     rcx, [rbp+57h+arg_10]
0x18002d89d  test    rcx, rcx
0x18002d8a0  jz      short loc_18002D8AE
0x18002d8a2  mov     rdx, [rcx]
0x18002d8a5  mov     rax, [rdx+10h]
0x18002d8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8ae  mov     eax, ebx
0x18002d8b0  add     rsp, 90h
0x18002d8b7  pop     r15
0x18002d8b9  pop     r14
0x18002d8bb  pop     r12
0x18002d8bd  pop     rdi
0x18002d8be  pop     rsi
0x18002d8bf  pop     rbx
0x18002d8c0  pop     rbp
0x18002d8c1  retn
0x18002d8c2  mov     rbx, [rbp+57h+arg_10]
0x18002d8c6  lea     r8, [rbp+57h+arg_18]
0x18002d8ca  xor     eax, eax
0x18002d8cc  mov     rdx, rdi
0x18002d8cf  mov     word ptr [rbp+57h+arg_18], ax
0x18002d8d3  mov     rcx, rbx
0x18002d8d6  mov     rax, [rbx]
0x18002d8d9  mov     rax, [rax+208h]
0x18002d8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8e5  mov     edi, eax
0x18002d8e7  test    eax, eax
0x18002d8e9  jns     short loc_18002D91B
0x18002d8eb  mov     rcx, [rbp+5Fh]; this
0x18002d8ef  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002d8f6  mov     r9d, eax; char *
0x18002d8f9  mov     edx, 2C3h; void *
0x18002d8fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d903  test    rbx, rbx
0x18002d906  jz      short loc_18002D917
0x18002d908  mov     rcx, [rbx]
0x18002d90b  mov     rax, [rcx+10h]
0x18002d90f  mov     rcx, rbx
0x18002d912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d917  mov     eax, edi
0x18002d919  jmp     short loc_18002D8B0
0x18002d91b  cmp     word ptr [rbp+57h+arg_18], 0FFFFh
0x18002d920  jz      short loc_18002D952
0x18002d922  mov     rcx, [rbp+5Fh]; this
0x18002d926  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002d92d  mov     r9d, 80070057h; char *
0x18002d933  mov     edx, 2C4h; void *
0x18002d938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d93d  test    rbx, rbx
0x18002d940  jz      loc_18002DD94
0x18002d946  mov     rax, [rbx]
0x18002d949  mov     rax, [rax+10h]
0x18002d94d  jmp     loc_18002DD8C
0x18002d952  mov     [rbp+57h+arg_8], 0
0x18002d95a  lea     rdx, [rbp+57h+arg_8]
0x18002d95e  mov     rax, [rbx]
0x18002d961  mov     rcx, rbx
0x18002d964  mov     rax, [rax+168h]
0x18002d96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d970  mov     edi, eax
0x18002d972  test    eax, eax
0x18002d974  jns     short loc_18002D9B8
0x18002d976  mov     rcx, [rbp+5Fh]; this
0x18002d97a  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002d981  mov     r9d, eax; char *
0x18002d984  mov     edx, 2CCh; void *
0x18002d989  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d98e  mov     rcx, [rbp+57h+arg_8]
0x18002d992  test    rcx, rcx
0x18002d995  jz      short loc_18002D9A3
0x18002d997  mov     rdx, [rcx]
0x18002d99a  mov     rax, [rdx+10h]
0x18002d99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9a3  test    rbx, rbx
0x18002d9a6  jz      loc_18002D917
0x18002d9ac  mov     rax, [rbx]
0x18002d9af  mov     rax, [rax+10h]
0x18002d9b3  jmp     loc_18002D90F
0x18002d9b8  mov     rdi, [rbp+57h+arg_8]
0x18002d9bc  lea     rcx, ?c_PackageName@EnterpriseModernAppManagement@@3QBGB; "Name"
0x18002d9c3  xorps   xmm0, xmm0
0x18002d9c6  xor     eax, eax
0x18002d9c8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002d9cc  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002d9d0  mov     r15, [rdi]
0x18002d9d3  call    cs:__imp_SysAllocString
0x18002d9d9  mov     rsi, rax
0x18002d9dc  test    rax, rax
0x18002d9df  jz      loc_18002DD9E
0x18002d9e5  mov     rdx, rax
0x18002d9e8  lea     r8, [rbp+57h+pvarg]
0x18002d9ec  mov     rax, [r15+160h]
0x18002d9f3  mov     rcx, rdi
0x18002d9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9fb  mov     rcx, rsi; bstrString
0x18002d9fe  mov     edi, eax
0x18002da00  call    cs:__imp_SysFreeString
0x18002da06  test    edi, edi
0x18002da08  jns     short loc_18002DA45
0x18002da0a  mov     rcx, [rbp+5Fh]; this
0x18002da0e  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002da15  mov     r9d, edi; char *
0x18002da18  mov     edx, 2D0h; void *
0x18002da1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da22  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002da26  call    cs:__imp_VariantClear
0x18002da2c  mov     rcx, [rbp+57h+arg_8]
0x18002da30  test    rcx, rcx
0x18002da33  jz      loc_18002D9A3
0x18002da39  mov     rax, [rcx]
0x18002da3c  mov     rax, [rax+10h]
0x18002da40  jmp     loc_18002D99E
0x18002da45  mov     eax, 0FFF6h
0x18002da4a  test    word ptr [rbp+57h+pvarg], ax
0x18002da4e  jnz     loc_18002DD46
0x18002da54  cmp     word ptr [rbp+57h+pvarg], 9
0x18002da59  jz      loc_18002DD46
0x18002da5f  mov     rcx, qword ptr [rbp+57h+pvarg+8]; pbstr
0x18002da63  test    rcx, rcx
0x18002da66  jz      loc_18002DD01
0x18002da6c  call    cs:__imp_SysStringLen
0x18002da72  test    eax, eax
0x18002da74  jz      loc_18002DD01
0x18002da7a  mov     rdx, qword ptr [rbp+57h+pvarg+8]; Src
0x18002da7e  lea     rcx, [rbp+57h+var_60]; this
0x18002da82  xor     eax, eax
0x18002da84  xorps   xmm0, xmm0
0x18002da87  movups  [rbp+57h+var_60], xmm0
0x18002da8b  mov     [rbp+57h+var_50], eax
0x18002da8e  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002da93  mov     edi, eax
0x18002da95  test    eax, eax
0x18002da97  jns     short loc_18002DAC9
0x18002da99  mov     rcx, [rbp+5Fh]; this
0x18002da9d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002daa4  mov     r9d, eax; char *
0x18002daa7  mov     edx, 2D6h; void *
0x18002daac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dab1  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x18002dab5  test    rcx, rcx
0x18002dab8  jz      loc_18002DA22
0x18002dabe  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002dac4  jmp     loc_18002DA22
0x18002dac9  mov     rdi, [rbp+57h+arg_8]
0x18002dacd  lea     rcx, ?c_RemoveForAllUsers@EnterpriseModernAppManagement@@3QBGB; "RemoveForAllUsers"
0x18002dad4  xorps   xmm0, xmm0
0x18002dad7  xor     eax, eax
0x18002dad9  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18002dadd  mov     qword ptr [rbp+57h+var_78+10h], rax
0x18002dae1  mov     r15, [rdi]
0x18002dae4  call    cs:__imp_SysAllocString
0x18002daea  mov     rsi, rax
0x18002daed  test    rax, rax
0x18002daf0  jz      loc_18002DD9E
0x18002daf6  mov     rdx, rax
0x18002daf9  lea     r8, [rbp+57h+var_78]
0x18002dafd  mov     rax, [r15+160h]
0x18002db04  mov     rcx, rdi
0x18002db07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db0c  mov     rcx, rsi; bstrString
0x18002db0f  mov     edi, eax
0x18002db11  call    cs:__imp_SysFreeString
0x18002db17  test    edi, edi
0x18002db19  jns     short loc_18002DB42
0x18002db1b  mov     rcx, [rbp+5Fh]; this
0x18002db1f  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002db26  mov     r9d, edi; char *
0x18002db29  mov     edx, 2DAh; void *
0x18002db2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002db33  lea     rcx, [rbp+57h+var_78]; pvarg
0x18002db37  call    cs:__imp_VariantClear
0x18002db3d  jmp     loc_18002DAB1
0x18002db42  mov     eax, 0FFF6h
0x18002db47  test    word ptr [rbp+57h+var_78], ax
0x18002db4b  jnz     loc_18002DCE1
0x18002db51  cmp     word ptr [rbp+57h+var_78], 9
0x18002db56  jz      loc_18002DCE1
0x18002db5c  mov     rcx, qword ptr [rbp+57h+var_78+8]; pbstr
0x18002db60  test    rcx, rcx
0x18002db63  jz      loc_18002DC8E
0x18002db69  call    cs:__imp_SysStringLen
0x18002db6f  test    eax, eax
0x18002db71  jz      loc_18002DC8E
0x18002db77  mov     rdx, qword ptr [rbp+57h+var_78+8]; Src
0x18002db7b  lea     rcx, [rbp+57h+lpString1]; this
0x18002db7f  xor     eax, eax
0x18002db81  xorps   xmm0, xmm0
0x18002db84  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x18002db88  mov     [rbp+57h+var_38], eax
0x18002db8b  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002db90  mov     edi, eax
0x18002db92  test    eax, eax
0x18002db94  jns     short loc_18002DBC6
0x18002db96  mov     rcx, [rbp+5Fh]; this
0x18002db9a  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002dba1  mov     r9d, eax; char *
0x18002dba4  mov     edx, 2E5h; void *
0x18002dba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dbae  mov     rcx, [rbp+57h+lpString1+8]
0x18002dbb2  test    rcx, rcx
0x18002dbb5  jz      loc_18002DB33
0x18002dbbb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002dbc1  jmp     loc_18002DB33
0x18002dbc6  mov     rdi, [rbp+57h+lpString1+8]
0x18002dbca  lea     r8, a1; "1"
0x18002dbd1  mov     edx, dword ptr [rbp+57h+lpString1]; cchCount1
0x18002dbd4  mov     esi, 1
0x18002dbd9  mov     r9d, esi; cchCount2
0x18002dbdc  mov     [rsp+0C0h+bIgnoreCase], 0; bIgnoreCase
0x18002dbe4  mov     rcx, rdi; lpString1
0x18002dbe7  call    cs:__imp_CompareStringOrdinal
0x18002dbed  test    eax, eax
0x18002dbef  jnz     short loc_18002DC11
0x18002dbf1  mov     edx, dword ptr [rbp+57h+lpString1]; cchCount1
0x18002dbf4  lea     r8, a0; "0"
0x18002dbfb  mov     r9d, esi; cchCount2
0x18002dbfe  mov     [rsp+0C0h+bIgnoreCase], eax; int
0x18002dc02  mov     rcx, rdi; lpString1
0x18002dc05  call    cs:__imp_CompareStringOrdinal
0x18002dc0b  test    eax, eax
0x18002dc0d  jz      short loc_18002DC24
0x18002dc0f  xor     esi, esi
0x18002dc11  mov     [r14], esi
0x18002dc14  test    rdi, rdi
0x18002dc17  jz      short loc_18002DC95
0x18002dc19  mov     rcx, rdi
0x18002dc1c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002dc22  jmp     short loc_18002DC95
0x18002dc24  mov     rcx, [rbp+5Fh]; this
0x18002dc28  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002dc2f  mov     r9d, 80070057h; char *
0x18002dc35  mov     edx, 2F2h; void *
0x18002dc3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc3f  test    rdi, rdi
0x18002dc42  jz      short loc_18002DC4D
0x18002dc44  mov     rcx, rdi
0x18002dc47  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002dc4d  lea     rcx, [rbp+57h+var_78]; pvarg
0x18002dc51  call    cs:__imp_VariantClear
0x18002dc57  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x18002dc5b  test    rcx, rcx
0x18002dc5e  jz      short loc_18002DC66
0x18002dc60  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002dc66  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002dc6a  call    cs:__imp_VariantClear
0x18002dc70  mov     rcx, [rbp+57h+arg_8]
0x18002dc74  test    rcx, rcx
0x18002dc77  jz      loc_18002D93D
0x18002dc7d  mov     rax, [rcx]
0x18002dc80  mov     rax, [rax+10h]
0x18002dc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc89  jmp     loc_18002D93D
0x18002dc8e  mov     dword ptr [r14], 0
0x18002dc95  mov     rax, qword ptr [rbp+57h+var_60+8]
0x18002dc99  lea     rcx, [rbp+57h+var_78]; pvarg
0x18002dc9d  mov     [r12], rax
0x18002dca1  call    cs:__imp_VariantClear
0x18002dca7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002dcab  call    cs:__imp_VariantClear
0x18002dcb1  mov     rcx, [rbp+57h+arg_8]
0x18002dcb5  test    rcx, rcx
0x18002dcb8  jz      short loc_18002DCC6
0x18002dcba  mov     rax, [rcx]
0x18002dcbd  mov     rax, [rax+10h]
0x18002dcc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcc6  test    rbx, rbx
0x18002dcc9  jz      short loc_18002DCDA
0x18002dccb  mov     rax, [rbx]
0x18002dcce  mov     rcx, rbx
0x18002dcd1  mov     rax, [rax+10h]
0x18002dcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcda  xor     eax, eax
0x18002dcdc  jmp     loc_18002D8B0
0x18002dce1  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```

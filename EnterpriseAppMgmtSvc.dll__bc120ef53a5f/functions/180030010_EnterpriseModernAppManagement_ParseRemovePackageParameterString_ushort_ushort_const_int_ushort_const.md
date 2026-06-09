# EnterpriseModernAppManagement::ParseRemovePackageParameterString(ushort *,ushort const * *,int *,ushort const * *)

- ea: `0x180030010`
- end: `0x180030607`
- name: `?ParseRemovePackageParameterString@EnterpriseModernAppManagement@@YAJPEAGPEAPEBGPEAH1@Z`
- size: `1527`
- prototype: `__int64 __fastcall(EnterpriseModernAppManagement *__hidden this, unsigned __int16 *, const unsigned __int16 **, int *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180027f80`

## callees

- `0x180007404`
- `0x18000d3dc`
- `0x18002c2bc`
- `0x180030010`
- `0x18006b444`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800302af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800303ca`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030441`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030475`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003049a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800302af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800303ca`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030441`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030475`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003049a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800301ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800302db`
- `OLEAUT32!__imp_SysAllocString` at `0x1800301ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800302db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800301df`
- `OLEAUT32!__imp_SysFreeString` at `0x18003030e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800301df`
- `OLEAUT32!__imp_SysFreeString` at `0x18003030e`
- `OLEAUT32!__imp_SysStringLen` at `0x180030257`
- `OLEAUT32!__imp_SysStringLen` at `0x180030372`
- `OLEAUT32!__imp_SysStringLen` at `0x180030257`
- `OLEAUT32!__imp_SysStringLen` at `0x180030372`
- `OLEAUT32!__imp_VariantClear` at `0x18003020b`
- `OLEAUT32!__imp_VariantClear` at `0x18003033a`
- `OLEAUT32!__imp_VariantClear` at `0x180030485`
- `OLEAUT32!__imp_VariantClear` at `0x1800304aa`
- `OLEAUT32!__imp_VariantClear` at `0x1800304e7`
- `OLEAUT32!__imp_VariantClear` at `0x1800304f7`
- `OLEAUT32!__imp_VariantClear` at `0x180030574`
- `OLEAUT32!__imp_VariantClear` at `0x1800305bd`
- `OLEAUT32!__imp_VariantClear` at `0x18003020b`
- `OLEAUT32!__imp_VariantClear` at `0x18003033a`
- `OLEAUT32!__imp_VariantClear` at `0x180030485`
- `OLEAUT32!__imp_VariantClear` at `0x1800304aa`
- `OLEAUT32!__imp_VariantClear` at `0x1800304e7`
- `OLEAUT32!__imp_VariantClear` at `0x1800304f7`
- `OLEAUT32!__imp_VariantClear` at `0x180030574`
- `OLEAUT32!__imp_VariantClear` at `0x1800305bd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800303fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030420`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800303fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030420`

## string_xrefs

- `0x1800302c4`: `RemoveForAllUsers`

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
0x180030010  mov     [rsp-8+arg_18], r9
0x180030015  push    rbp
0x180030016  push    rbx
0x180030017  push    rsi
0x180030018  push    rdi
0x180030019  push    r12
0x18003001b  push    r14
0x18003001d  push    r15
0x18003001f  lea     rbp, [rsp-27h]
0x180030024  sub     rsp, 90h
0x18003002b  mov     rdi, rcx
0x18003002e  mov     qword ptr [rdx], 0
0x180030035  lea     rcx, [rbp+57h+arg_10]; this
0x180030039  mov     dword ptr [r8], 0
0x180030040  mov     r14, r8
0x180030043  mov     [rbp+57h+arg_10], 0
0x18003004b  mov     r12, rdx
0x18003004e  call    ?CreateXmlDomDocument@EnterpriseModernAppManagement@@YAJPEAPEAUIXMLDOMDocument2@@@Z; EnterpriseModernAppManagement::CreateXmlDomDocument(IXMLDOMDocument2 * *)
0x180030053  mov     ebx, eax
0x180030055  test    eax, eax
0x180030057  jns     short loc_18003009B
0x180030059  mov     rcx, [rbp+5Fh]; this
0x18003005d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180030064  mov     r9d, eax; char *
0x180030067  mov     edx, 2BFh; void *
0x18003006c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030071  mov     rcx, [rbp+57h+arg_10]
0x180030075  test    rcx, rcx
0x180030078  jz      short loc_180030086
0x18003007a  mov     rdx, [rcx]
0x18003007d  mov     rax, [rdx+10h]
0x180030081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030086  mov     eax, ebx
0x180030088  add     rsp, 90h
0x18003008f  pop     r15
0x180030091  pop     r14
0x180030093  pop     r12
0x180030095  pop     rdi
0x180030096  pop     rsi
0x180030097  pop     rbx
0x180030098  pop     rbp
0x180030099  retn
0x18003009b  mov     rbx, [rbp+57h+arg_10]
0x18003009f  lea     r8, [rbp+57h+arg_18]
0x1800300a3  xor     eax, eax
0x1800300a5  mov     rdx, rdi
0x1800300a8  mov     word ptr [rbp+57h+arg_18], ax
0x1800300ac  mov     rcx, rbx
0x1800300af  mov     rax, [rbx]
0x1800300b2  mov     rax, [rax+208h]
0x1800300b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300be  mov     edi, eax
0x1800300c0  test    eax, eax
0x1800300c2  jns     short loc_1800300F4
0x1800300c4  mov     rcx, [rbp+5Fh]; this
0x1800300c8  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800300cf  mov     r9d, eax; char *
0x1800300d2  mov     edx, 2C3h; void *
0x1800300d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800300dc  test    rbx, rbx
0x1800300df  jz      short loc_1800300F0
0x1800300e1  mov     rcx, [rbx]
0x1800300e4  mov     rax, [rcx+10h]
0x1800300e8  mov     rcx, rbx
0x1800300eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300f0  mov     eax, edi
0x1800300f2  jmp     short loc_180030088
0x1800300f4  cmp     word ptr [rbp+57h+arg_18], 0FFFFh
0x1800300f9  jz      short loc_18003012B
0x1800300fb  mov     rcx, [rbp+5Fh]; this
0x1800300ff  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180030106  mov     r9d, 80070057h; char *
0x18003010c  mov     edx, 2C4h; void *
0x180030111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030116  test    rbx, rbx
0x180030119  jz      loc_1800305F2
0x18003011f  mov     rax, [rbx]
0x180030122  mov     rax, [rax+10h]
0x180030126  jmp     loc_1800305EA
0x18003012b  mov     [rbp+57h+arg_8], 0
0x180030133  lea     rdx, [rbp+57h+arg_8]
0x180030137  mov     rax, [rbx]
0x18003013a  mov     rcx, rbx
0x18003013d  mov     rax, [rax+168h]
0x180030144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030149  mov     edi, eax
0x18003014b  test    eax, eax
0x18003014d  jns     short loc_180030191
0x18003014f  mov     rcx, [rbp+5Fh]; this
0x180030153  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18003015a  mov     r9d, eax; char *
0x18003015d  mov     edx, 2CCh; void *
0x180030162  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030167  mov     rcx, [rbp+57h+arg_8]
0x18003016b  test    rcx, rcx
0x18003016e  jz      short loc_18003017C
0x180030170  mov     rdx, [rcx]
0x180030173  mov     rax, [rdx+10h]
0x180030177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003017c  test    rbx, rbx
0x18003017f  jz      loc_1800300F0
0x180030185  mov     rax, [rbx]
0x180030188  mov     rax, [rax+10h]
0x18003018c  jmp     loc_1800300E8
0x180030191  mov     rdi, [rbp+57h+arg_8]
0x180030195  lea     rcx, ?c_PackageName@EnterpriseModernAppManagement@@3QBGB; "Name"
0x18003019c  xorps   xmm0, xmm0
0x18003019f  xor     eax, eax
0x1800301a1  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800301a5  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800301a9  mov     r15, [rdi]
0x1800301ac  call    cs:__imp_SysAllocString
0x1800301b3  nop     dword ptr [rax+rax+00h]
0x1800301b8  mov     rsi, rax
0x1800301bb  test    rax, rax
0x1800301be  jz      loc_1800305FC
0x1800301c4  mov     rdx, rax
0x1800301c7  lea     r8, [rbp+57h+pvarg]
0x1800301cb  mov     rax, [r15+160h]
0x1800301d2  mov     rcx, rdi
0x1800301d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301da  mov     rcx, rsi; bstrString
0x1800301dd  mov     edi, eax
0x1800301df  call    cs:__imp_SysFreeString
0x1800301e6  nop     dword ptr [rax+rax+00h]
0x1800301eb  test    edi, edi
0x1800301ed  jns     short loc_180030230
0x1800301ef  mov     rcx, [rbp+5Fh]; this
0x1800301f3  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800301fa  mov     r9d, edi; char *
0x1800301fd  mov     edx, 2D0h; void *
0x180030202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030207  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003020b  call    cs:__imp_VariantClear
0x180030212  nop     dword ptr [rax+rax+00h]
0x180030217  mov     rcx, [rbp+57h+arg_8]
0x18003021b  test    rcx, rcx
0x18003021e  jz      loc_18003017C
0x180030224  mov     rax, [rcx]
0x180030227  mov     rax, [rax+10h]
0x18003022b  jmp     loc_180030177
0x180030230  mov     eax, 0FFF6h
0x180030235  test    word ptr [rbp+57h+pvarg], ax
0x180030239  jnz     loc_18003059E
0x18003023f  cmp     word ptr [rbp+57h+pvarg], 9
0x180030244  jz      loc_18003059E
0x18003024a  mov     rcx, qword ptr [rbp+57h+pvarg+8]; pbstr
0x18003024e  test    rcx, rcx
0x180030251  jz      loc_180030553
0x180030257  call    cs:__imp_SysStringLen
0x18003025e  nop     dword ptr [rax+rax+00h]
0x180030263  test    eax, eax
0x180030265  jz      loc_180030553
0x18003026b  mov     rdx, qword ptr [rbp+57h+pvarg+8]; Src
0x18003026f  lea     rcx, [rbp+57h+var_60]; this
0x180030273  xor     eax, eax
0x180030275  xorps   xmm0, xmm0
0x180030278  movups  [rbp+57h+var_60], xmm0
0x18003027c  mov     [rbp+57h+var_50], eax
0x18003027f  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180030284  mov     edi, eax
0x180030286  test    eax, eax
0x180030288  jns     short loc_1800302C0
0x18003028a  mov     rcx, [rbp+5Fh]; this
0x18003028e  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180030295  mov     r9d, eax; char *
0x180030298  mov     edx, 2D6h; void *
0x18003029d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302a2  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x1800302a6  test    rcx, rcx
0x1800302a9  jz      loc_180030207
0x1800302af  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800302b6  nop     dword ptr [rax+rax+00h]
0x1800302bb  jmp     loc_180030207
0x1800302c0  mov     rdi, [rbp+57h+arg_8]
0x1800302c4  lea     rcx, ?c_RemoveForAllUsers@EnterpriseModernAppManagement@@3QBGB; "RemoveForAllUsers"
0x1800302cb  xorps   xmm0, xmm0
0x1800302ce  xor     eax, eax
0x1800302d0  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1800302d4  mov     qword ptr [rbp+57h+var_78+10h], rax
0x1800302d8  mov     r15, [rdi]
0x1800302db  call    cs:__imp_SysAllocString
0x1800302e2  nop     dword ptr [rax+rax+00h]
0x1800302e7  mov     rsi, rax
0x1800302ea  test    rax, rax
0x1800302ed  jz      loc_1800305FC
0x1800302f3  mov     rdx, rax
0x1800302f6  lea     r8, [rbp+57h+var_78]
0x1800302fa  mov     rax, [r15+160h]
0x180030301  mov     rcx, rdi
0x180030304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030309  mov     rcx, rsi; bstrString
0x18003030c  mov     edi, eax
0x18003030e  call    cs:__imp_SysFreeString
0x180030315  nop     dword ptr [rax+rax+00h]
0x18003031a  test    edi, edi
0x18003031c  jns     short loc_18003034B
0x18003031e  mov     rcx, [rbp+5Fh]; this
0x180030322  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180030329  mov     r9d, edi; char *
0x18003032c  mov     edx, 2DAh; void *
0x180030331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030336  lea     rcx, [rbp+57h+var_78]; pvarg
0x18003033a  call    cs:__imp_VariantClear
0x180030341  nop     dword ptr [rax+rax+00h]
0x180030346  jmp     loc_1800302A2
0x18003034b  mov     eax, 0FFF6h
0x180030350  test    word ptr [rbp+57h+var_78], ax
0x180030354  jnz     loc_180030533
0x18003035a  cmp     word ptr [rbp+57h+var_78], 9
0x18003035f  jz      loc_180030533
0x180030365  mov     rcx, qword ptr [rbp+57h+var_78+8]; pbstr
0x180030369  test    rcx, rcx
0x18003036c  jz      loc_1800304D4
0x180030372  call    cs:__imp_SysStringLen
0x180030379  nop     dword ptr [rax+rax+00h]
0x18003037e  test    eax, eax
0x180030380  jz      loc_1800304D4
0x180030386  mov     rdx, qword ptr [rbp+57h+var_78+8]; Src
0x18003038a  lea     rcx, [rbp+57h+lpString1]; this
0x18003038e  xor     eax, eax
0x180030390  xorps   xmm0, xmm0
0x180030393  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x180030397  mov     [rbp+57h+var_38], eax
0x18003039a  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18003039f  mov     edi, eax
0x1800303a1  test    eax, eax
0x1800303a3  jns     short loc_1800303DB
0x1800303a5  mov     rcx, [rbp+5Fh]; this
0x1800303a9  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800303b0  mov     r9d, eax; char *
0x1800303b3  mov     edx, 2E5h; void *
0x1800303b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800303bd  mov     rcx, [rbp+57h+lpString1+8]
0x1800303c1  test    rcx, rcx
0x1800303c4  jz      loc_180030336
0x1800303ca  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800303d1  nop     dword ptr [rax+rax+00h]
0x1800303d6  jmp     loc_180030336
0x1800303db  mov     rdi, [rbp+57h+lpString1+8]
0x1800303df  lea     r8, a1; "1"
0x1800303e6  mov     edx, dword ptr [rbp+57h+lpString1]; cchCount1
0x1800303e9  mov     esi, 1
0x1800303ee  mov     r9d, esi; cchCount2
0x1800303f1  mov     [rsp+0C0h+bIgnoreCase], 0; bIgnoreCase
0x1800303f9  mov     rcx, rdi; lpString1
0x1800303fc  call    cs:__imp_CompareStringOrdinal
0x180030403  nop     dword ptr [rax+rax+00h]
0x180030408  test    eax, eax
0x18003040a  jnz     short loc_180030432
0x18003040c  mov     edx, dword ptr [rbp+57h+lpString1]; cchCount1
0x18003040f  lea     r8, a0; "0"
0x180030416  mov     r9d, esi; cchCount2
0x180030419  mov     [rsp+0C0h+bIgnoreCase], eax; int
0x18003041d  mov     rcx, rdi; lpString1
0x180030420  call    cs:__imp_CompareStringOrdinal
0x180030427  nop     dword ptr [rax+rax+00h]
0x18003042c  test    eax, eax
0x18003042e  jz      short loc_180030452
0x180030430  xor     esi, esi
0x180030432  mov     [r14], esi
0x180030435  test    rdi, rdi
0x180030438  jz      loc_1800304DB
0x18003043e  mov     rcx, rdi
0x180030441  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180030448  nop     dword ptr [rax+rax+00h]
0x18003044d  jmp     loc_1800304DB
0x180030452  mov     rcx, [rbp+5Fh]; this
0x180030456  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18003045d  mov     r9d, 80070057h; char *
0x180030463  mov     edx, 2F2h; void *
0x180030468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003046d  test    rdi, rdi
0x180030470  jz      short loc_180030481
0x180030472  mov     rcx, rdi
0x180030475  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003047c  nop     dword ptr [rax+rax+00h]
0x180030481  lea     rcx, [rbp+57h+var_78]; pvarg
0x180030485  call    cs:__imp_VariantClear
0x18003048c  nop     dword ptr [rax+rax+00h]
0x180030491  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x180030495  test    rcx, rcx
0x180030498  jz      short loc_1800304A6
0x18003049a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800304a1  nop     dword ptr [rax+rax+00h]
0x1800304a6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800304aa  call    cs:__imp_VariantClear
0x1800304b1  nop     dword ptr [rax+rax+00h]
0x1800304b6  mov     rcx, [rbp+57h+arg_8]
0x1800304ba  test    rcx, rcx
0x1800304bd  jz      loc_180030116
0x1800304c3  mov     rax, [rcx]
0x1800304c6  mov     rax, [rax+10h]
0x1800304ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304cf  jmp     loc_180030116
0x1800304d4  mov     dword ptr [r14], 0
0x1800304db  mov     rax, qword ptr [rbp+57h+var_60+8]
0x1800304df  lea     rcx, [rbp+57h+var_78]; pvarg
0x1800304e3  mov     [r12], rax
0x1800304e7  call    cs:__imp_VariantClear
  ... truncated ...
```

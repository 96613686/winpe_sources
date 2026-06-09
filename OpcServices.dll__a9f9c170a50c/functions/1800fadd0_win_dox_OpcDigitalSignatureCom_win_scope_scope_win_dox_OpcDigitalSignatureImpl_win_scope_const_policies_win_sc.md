# win_dox::OpcDigitalSignatureCom<win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignature>::GetNamespaces_Safe(wchar_t * * *,wchar_t * * *,uint *)

- ea: `0x1800fadd0`
- end: `0x1800fb0e1`
- name: `?GetNamespaces_Safe@?$OpcDigitalSignatureCom@V?$scope@PEAVOpcDigitalSignatureImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcDigitalSignature@@@win_dox@@AEAAXPEAPEAPEA_W0PEAI@Z`
- size: `785`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800517a0`
- `0x18005ab90`
- `0x1800914f8`
- `0x1800af8d8`
- `0x1800b8068`
- `0x1800cd38c`
- `0x1800d0694`
- `0x1800ec840`
- `0x1800ec910`
- `0x1800ec9b0`
- `0x1800fadd0`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800faf4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fafb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800faf4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fafb3`

## string_xrefs

- `0x1800fafc1`: `Unable to allocate memory for XML namespaces`
- `0x1800faf5c`: `Unable to allocate memory for XML prefixes`
- `0x1800fae40`: `OpcDigitalSignatureCom`
- `0x1800fae82`: `OpcDigitalSignatureCom`
- `0x1800faec1`: `OpcDigitalSignatureCom`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall win_dox::OpcDigitalSignatureCom<win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignature>::GetNamespaces_Safe(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _DWORD *a4)
{
  int v6; // eax
  SIZE_T v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // r14
  _QWORD *v10; // rax
  _QWORD *v11; // r12
  _QWORD *v12; // r13
  __int64 v13; // rbx
  int v14; // esi
  __int64 i; // rax
  char v18[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v19; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+A0h] [rbp-60h] BYREF

  v21 = -2;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      78,
      L"OpcDigitalSignatureCom",
      L"GetNamespaces",
      L"prefixes",
      0);
  *a2 = 0;
  if ( !a3 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      0,
      81,
      L"OpcDigitalSignatureCom",
      L"GetNamespaces",
      L"namespaces",
      0);
  if ( !a4 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      82,
      L"OpcDigitalSignatureCom",
      L"GetNamespaces",
      L"count",
      0);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
    v18,
    *(_QWORD *)(a1 + 16) + 184LL);
  v6 = v20;
  if ( v20 > 0x1FFFFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x5Bu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"too many strings.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *a4 = v20;
  v7 = (unsigned int)(8 * v6);
  v8 = CoTaskMemAlloc(v7);
  v9 = v8;
  if ( !v8 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x66u,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to allocate memory for XML prefixes");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(v23, v8, (unsigned int)*a4);
  v10 = CoTaskMemAlloc(v7);
  v11 = v10;
  if ( !v10 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x71u,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to allocate memory for XML namespaces");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(v22, v10, (unsigned int)*a4);
  v12 = v19;
  v13 = *v19;
  v14 = 0;
  while ( (_QWORD *)v13 != v12 )
  {
    v9[v14] = win_dox::AllocAndCopyString(v13 + 24);
    v11[v14++] = win_dox::AllocAndCopyString(v13 + 64);
    if ( *(_BYTE *)(v13 + 105) )
      invalid_parameter(0, 0, 0, 0, 0);
    if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 105LL) )
    {
      for ( i = *(_QWORD *)(v13 + 8); !*(_BYTE *)(i + 105) && v13 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v13 = i;
    }
    else
    {
      i = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min();
    }
    v13 = i;
  }
  *a2 = v9;
  *a3 = v11;
  v23[16] = 1;
  v22[16] = 1;
  win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(v22);
  win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(v23);
  return std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tidy(v18);
}

```

## disassembly

```asm
0x1800fadd0  push    rbp
0x1800fadd2  push    rbx
0x1800fadd3  push    rsi
0x1800fadd4  push    rdi
0x1800fadd5  push    r12
0x1800fadd7  push    r13
0x1800fadd9  push    r14
0x1800faddb  push    r15
0x1800faddd  lea     rbp, [rsp-58h]
0x1800fade2  sub     rsp, 158h
0x1800fade9  mov     [rsp+190h+var_128], 0FFFFFFFFFFFFFFFEh
0x1800fadf2  mov     rax, cs:__security_cookie
0x1800fadf9  xor     rax, rsp
0x1800fadfc  mov     [rbp+90h+var_50], rax
0x1800fae00  mov     rbx, r9
0x1800fae03  mov     [rsp+190h+var_148], r8
0x1800fae08  mov     r15, rdx
0x1800fae0b  xor     r13d, r13d
0x1800fae0e  test    r8, r8
0x1800fae11  jz      short loc_1800FAE16
0x1800fae13  mov     [r8], r13
0x1800fae16  test    rbx, rbx
0x1800fae19  jz      short loc_1800FAE1E
0x1800fae1b  mov     [r9], r13d
0x1800fae1e  test    r15, r15
0x1800fae21  jnz     short loc_1800FAE5D
0x1800fae23  mov     [rsp+190h+var_158], r13d
0x1800fae28  lea     rax, aPrefixes; "prefixes"
0x1800fae2f  mov     [rsp+190h+var_160], rax
0x1800fae34  lea     rax, aGetnamespaces; "GetNamespaces"
0x1800fae3b  mov     qword ptr [rsp+190h+var_168], rax
0x1800fae40  lea     rax, aOpcdigitalsign_0; "OpcDigitalSignatureCom"
0x1800fae47  mov     [rsp+190h+Reserved], rax
0x1800fae4c  lea     r9d, [r15+4Eh]
0x1800fae50  lea     rdx, aNoFilename; "(no filename)"
0x1800fae57  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800fae5d  mov     [rdx], r13
0x1800fae60  test    r8, r8
0x1800fae63  jnz     short loc_1800FAE9F
0x1800fae65  mov     [rsp+190h+var_158], r13d
0x1800fae6a  lea     rax, aNamespaces; "namespaces"
0x1800fae71  mov     [rsp+190h+var_160], rax
0x1800fae76  lea     rax, aGetnamespaces; "GetNamespaces"
0x1800fae7d  mov     qword ptr [rsp+190h+var_168], rax
0x1800fae82  lea     rax, aOpcdigitalsign_0; "OpcDigitalSignatureCom"
0x1800fae89  mov     [rsp+190h+Reserved], rax
0x1800fae8e  lea     r9d, [r8+51h]
0x1800fae92  lea     rdx, aNoFilename; "(no filename)"
0x1800fae99  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800fae9f  test    rbx, rbx
0x1800faea2  jnz     short loc_1800FAEDE
0x1800faea4  mov     [rsp+190h+var_158], r13d
0x1800faea9  lea     rax, aCount; "count"
0x1800faeb0  mov     [rsp+190h+var_160], rax
0x1800faeb5  lea     rax, aGetnamespaces; "GetNamespaces"
0x1800faebc  mov     qword ptr [rsp+190h+var_168], rax
0x1800faec1  lea     rax, aOpcdigitalsign_0; "OpcDigitalSignatureCom"
0x1800faec8  mov     [rsp+190h+Reserved], rax
0x1800faecd  lea     r9d, [rbx+52h]
0x1800faed1  lea     rdx, aNoFilename; "(no filename)"
0x1800faed8  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800faede  mov     rdx, [rcx+10h]
0x1800faee2  add     rdx, 0B8h
0x1800faee9  lea     rcx, [rsp+190h+var_140]
0x1800faeee  call    ??0?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>> const &)
0x1800faef3  nop
0x1800faef4  mov     rax, [rsp+190h+var_130]
0x1800faef9  cmp     rax, 1FFFFFFFh
0x1800faeff  jbe     short loc_1800FAF45
0x1800faf01  lea     rax, aTooManyStrings; "too many strings."
0x1800faf08  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800faf0d  mov     [rsp+190h+var_168], 8000FFFFh; unsigned int
0x1800faf15  mov     dword ptr [rsp+190h+Reserved], 5Bh ; '['; unsigned int
0x1800faf1d  lea     r9, word_18013A0B6
0x1800faf24  lea     r8, aNoFilename; "(no filename)"
0x1800faf2b  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800faf2f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800faf34  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800faf3b  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800faf3f  call    _CxxThrowException_0
0x1800faf45  mov     [rbx], eax
0x1800faf47  shl     eax, 3
0x1800faf4a  mov     edi, eax
0x1800faf4c  mov     ecx, eax; cb
0x1800faf4e  call    cs:__imp_CoTaskMemAlloc
0x1800faf54  mov     r14, rax
0x1800faf57  test    rax, rax
0x1800faf5a  jnz     short loc_1800FAFA0
0x1800faf5c  lea     rax, aUnableToAlloca; "Unable to allocate memory for XML prefi"...
0x1800faf63  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800faf68  mov     [rsp+190h+var_168], 8007000Eh; unsigned int
0x1800faf70  mov     dword ptr [rsp+190h+Reserved], 66h ; 'f'; unsigned int
0x1800faf78  lea     r9, word_18013A0B6
0x1800faf7f  lea     r8, aNoFilename; "(no filename)"
0x1800faf86  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800faf8a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800faf8f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800faf96  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800faf9a  call    _CxxThrowException_0
0x1800fafa0  mov     r8d, [rbx]
0x1800fafa3  mov     rdx, r14
0x1800fafa6  lea     rcx, [rbp+90h+var_108]
0x1800fafaa  call    ??0?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@PEAPEA_W_K_N@Z; win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(wchar_t * *,unsigned __int64,bool)
0x1800fafaf  nop
0x1800fafb0  mov     rcx, rdi; cb
0x1800fafb3  call    cs:__imp_CoTaskMemAlloc
0x1800fafb9  mov     r12, rax
0x1800fafbc  test    rax, rax
0x1800fafbf  jnz     short loc_1800FB005
0x1800fafc1  lea     rax, aUnableToAlloca_0; "Unable to allocate memory for XML names"...
0x1800fafc8  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800fafcd  mov     [rsp+190h+var_168], 8007000Eh; unsigned int
0x1800fafd5  mov     dword ptr [rsp+190h+Reserved], 71h ; 'q'; unsigned int
0x1800fafdd  lea     r9, word_18013A0B6
0x1800fafe4  lea     r8, aNoFilename; "(no filename)"
0x1800fafeb  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800fafef  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800faff4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800faffb  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800fafff  call    _CxxThrowException_0
0x1800fb005  mov     r8d, [rbx]
0x1800fb008  mov     rdx, r12
0x1800fb00b  lea     rcx, [rsp+190h+var_120]
0x1800fb010  call    ??0?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@PEAPEA_W_K_N@Z; win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(wchar_t * *,unsigned __int64,bool)
0x1800fb015  nop
0x1800fb016  mov     r13, [rsp+190h+var_138]
0x1800fb01b  mov     rbx, [r13+0]
0x1800fb01f  xor     edx, edx
0x1800fb021  mov     esi, edx
0x1800fb023  cmp     rbx, r13
0x1800fb026  jz      short loc_1800FB08E
0x1800fb028  mov     edi, esi
0x1800fb02a  lea     rcx, [rbx+18h]
0x1800fb02e  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800fb033  mov     [r14+rdi*8], rax
0x1800fb037  lea     rcx, [rbx+40h]
0x1800fb03b  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800fb040  mov     [r12+rdi*8], rax
0x1800fb044  inc     esi
0x1800fb046  xor     edx, edx; FunctionName
0x1800fb048  cmp     [rbx+69h], dl
0x1800fb04b  jz      short loc_1800FB061
0x1800fb04d  mov     [rsp+190h+Reserved], rdx; Reserved
0x1800fb052  xor     r9d, r9d; LineNo
0x1800fb055  xor     r8d, r8d; FileName
0x1800fb058  xor     ecx, ecx; Expression
0x1800fb05a  call    _invalid_parameter
0x1800fb05f  jmp     short loc_1800FB023
0x1800fb061  mov     rcx, [rbx+10h]
0x1800fb065  cmp     [rcx+69h], dl
0x1800fb068  jnz     short loc_1800FB071
0x1800fb06a  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Node *)
0x1800fb06f  jmp     short loc_1800FB089
0x1800fb071  mov     rax, [rbx+8]
0x1800fb075  jmp     short loc_1800FB084
0x1800fb077  cmp     rbx, [rax+10h]
0x1800fb07b  jnz     short loc_1800FB089
0x1800fb07d  mov     rbx, rax
0x1800fb080  mov     rax, [rax+8]
0x1800fb084  cmp     [rax+69h], dl
0x1800fb087  jz      short loc_1800FB077
0x1800fb089  mov     rbx, rax
0x1800fb08c  jmp     short loc_1800FB023
0x1800fb08e  mov     [r15], r14
0x1800fb091  mov     rsi, [rsp+190h+var_148]
0x1800fb096  mov     [rsi], r12
0x1800fb099  mov     [rbp+90h+var_F8], 1
0x1800fb09d  mov     [rbp+90h+var_110], 1
0x1800fb0a1  lea     rcx, [rsp+190h+var_120]
0x1800fb0a6  call    ??1?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@XZ; win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(void)
0x1800fb0ab  nop
0x1800fb0ac  lea     rcx, [rbp+90h+var_108]
0x1800fb0b0  call    ??1?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@XZ; win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(void)
0x1800fb0b5  nop
0x1800fb0b6  lea     rcx, [rsp+190h+var_140]
0x1800fb0bb  call    ?_Tidy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tidy(void)
0x1800fb0c0  nop
0x1800fb0c1  mov     rcx, [rbp+90h+var_50]
0x1800fb0c5  xor     rcx, rsp; StackCookie
0x1800fb0c8  call    __security_check_cookie
0x1800fb0cd  add     rsp, 158h
0x1800fb0d4  pop     r15
0x1800fb0d6  pop     r14
0x1800fb0d8  pop     r13
0x1800fb0da  pop     r12
0x1800fb0dc  pop     rdi
0x1800fb0dd  pop     rsi
0x1800fb0de  pop     rbx
0x1800fb0df  pop     rbp
0x1800fb0e0  retn
```

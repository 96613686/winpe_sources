# DataStoreReader::GetHistoryValueFromDocument(IXMLDOMDocument2 *,ulong &)

- ea: `0x180007128`
- end: `0x1800074e0`
- name: `?GetHistoryValueFromDocument@DataStoreReader@@KAJPEAUIXMLDOMDocument2@@AEAK@Z`
- size: `952`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180003970`

## callees

- `0x180007128`
- `0x180007850`
- `0x18000a0b0`
- `0x180011e70`
- `0x180011ee0`
- `0x180012bf3`
- `0x180012c06`

## import_xrefs

- `msvcrt!iswdigit` at `0x1800073fc`
- `msvcrt!iswdigit` at `0x180007428`
- `msvcrt!iswdigit` at `0x1800073fc`
- `msvcrt!iswdigit` at `0x180007428`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180007211`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000734f`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180007211`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000734f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000744f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000745e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007492`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800074a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000744f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000745e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007492`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800074a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180007471`
- `OLEAUT32!__imp_SysFreeString` at `0x180007471`

## string_xrefs

- `0x18000718c`: `/WinSAT/SystemConfig/HistoryVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DataStoreReader::GetHistoryValueFromDocument(struct IXMLDOMDocument2 *a1, unsigned int *a2)
{
  int v4; // r14d
  __int64 *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rcx
  const wchar_t *i; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  void *v12; // rax
  __int64 v13; // rcx
  int NodeValue; // r12d
  BSTR v15; // rdi
  __int64 *v16; // rax
  __int64 *v17; // rbx
  BSTR j; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  void *v21; // rax
  __int64 v22; // r8
  BSTR v23; // rdx
  __int64 v24; // rcx
  unsigned int v25; // r15d
  __int64 v26; // rsi
  wint_t *v27; // rdi
  bool v28; // zf
  void *v29; // rcx
  __int64 *v30; // rbx
  void *v31; // rcx
  int v33; // [rsp+20h] [rbp-40h]
  const char *v34[3]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-18h] BYREF
  char v36; // [rsp+A8h] [rbp+48h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp+50h] BYREF
  __int64 *v38; // [rsp+B8h] [rbp+58h] BYREF

  v34[1] = (const char *)-2LL;
  v4 = 0;
  *a2 = 0;
  v5 = (__int64 *)operator new(0x28u);
  v6 = v5;
  if ( !v5 )
    std::_Xbad_alloc();
  v38 = v5;
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 1;
  v5[3] = 0;
  v7 = 0x10000;
  v8 = 0x10000;
  for ( i = L"/WinSAT/SystemConfig/HistoryVersion"; ; ++i )
  {
    if ( !v8 )
      goto LABEL_63;
    if ( !*i )
      break;
    --v8;
  }
  if ( !i )
LABEL_63:
    throw (mlib::CStringTooBig *)&v36;
  v10 = i - L"/WinSAT/SystemConfig/HistoryVersion";
  *v6 = v10;
  v6[1] = v10;
  v11 = v10 + 1;
  v12 = 0;
  if ( v11 )
  {
    if ( v11 > 0x7FFFFFFFFFFFFFFFLL || (v12 = operator new(2 * v11)) == 0 )
      std::_Xbad_alloc();
  }
  v6[3] = (__int64)v12;
  if ( !v12 )
  {
    bstrString = (BSTR)"bad allocation";
    exception::exception((exception *)pExceptionObject, (const char *const *)&bstrString, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  if ( *v6 )
    memcpy_0(v12, L"/WinSAT/SystemConfig/HistoryVersion", 2 * *v6);
  v13 = v6[3];
  if ( v13 )
    *(_WORD *)(v13 + 2 * *v6) = 0;
  v38 = v6;
  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue((__int64)a1, (__int64)&v38, 1, (__int64)&bstrString, v33);
  if ( NodeValue < 0 )
    goto LABEL_56;
  v15 = bstrString;
  if ( !bstrString )
    goto LABEL_57;
  v16 = (__int64 *)operator new(0x28u);
  v17 = v16;
  if ( !v16 )
    std::_Xbad_alloc();
  v34[2] = (const char *)v16;
  *v16 = 0;
  v16[1] = 0;
  v16[2] = 1;
  v16[3] = 0;
  if ( v15 && *v15 )
  {
    for ( j = v15; ; ++j )
    {
      if ( !v7 )
        goto LABEL_37;
      if ( !*j )
        break;
      --v7;
    }
    if ( !j )
LABEL_37:
      throw (mlib::CStringTooBig *)&v36;
    v19 = j - v15;
    *v17 = v19;
    v17[1] = v19;
    v20 = v19 + 1;
    v21 = 0;
    if ( v20 )
    {
      if ( v20 > 0x7FFFFFFFFFFFFFFFLL || (v21 = operator new(2 * v20)) == 0 )
        std::_Xbad_alloc();
    }
    v17[3] = (__int64)v21;
    if ( !v21 )
    {
      v34[0] = "bad allocation";
      exception::exception((exception *)pExceptionObject, v34, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v22 = *v17;
    if ( !*v17 )
      goto LABEL_42;
    v23 = v15;
  }
  else
  {
    v21 = operator new(2u);
    if ( !v21 )
      std::_Xbad_alloc();
    v17[3] = (__int64)v21;
    v22 = *v17;
    if ( !*v17 )
      goto LABEL_42;
    v23 = 0;
  }
  memcpy_0(v21, v23, 2 * v22);
LABEL_42:
  v24 = v17[3];
  if ( v24 )
    *(_WORD *)(v24 + 2 * *v17) = 0;
  v25 = 0;
  v26 = *v17;
  v27 = (wint_t *)v17[3];
  if ( *v17 )
  {
    while ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v27) )
    {
      ++v27;
      if ( !--v26 )
        goto LABEL_52;
    }
    if ( iswdigit(*v27) )
    {
      do
      {
        v4 = *v27 + 2 * (5 * v4 - 24);
        if ( !--v26 )
          break;
        ++v27;
      }
      while ( iswdigit(*v27) );
      v25 = v4;
    }
  }
LABEL_52:
  *a2 = v25;
  v28 = v17[2]-- == 1;
  if ( v28 )
  {
    v29 = (void *)v17[3];
    if ( v29 )
      operator delete(v29);
    operator delete(v17);
  }
LABEL_56:
  v15 = bstrString;
LABEL_57:
  SysFreeString(v15);
  v30 = v38;
  v28 = v38[2]-- == 1;
  if ( v28 )
  {
    v31 = (void *)v30[3];
    if ( v31 )
      operator delete(v31);
    operator delete(v30);
  }
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x180007128  mov     rax, rsp
0x18000712b  push    rbp
0x18000712c  push    rsi
0x18000712d  push    rdi
0x18000712e  push    r12
0x180007130  push    r13
0x180007132  push    r14
0x180007134  push    r15
0x180007136  mov     rbp, rsp
0x180007139  sub     rsp, 60h
0x18000713d  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x180007145  mov     [rax+8], rbx
0x180007149  mov     r13, rdx
0x18000714c  mov     rdi, rcx
0x18000714f  xor     r14d, r14d
0x180007152  mov     [rdx], r14d
0x180007155  lea     ecx, [r14+28h]; Size
0x180007159  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000715e  mov     rbx, rax
0x180007161  test    rax, rax
0x180007164  jnz     short loc_18000716C
0x180007166  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000716c  mov     [rbp+arg_18], rbx
0x180007170  mov     [rax], r14
0x180007173  mov     [rax+8], r14
0x180007177  mov     r15d, 1
0x18000717d  mov     [rax+10h], r15
0x180007181  mov     [rax+18h], r14
0x180007185  mov     esi, 10000h
0x18000718a  mov     ecx, esi
0x18000718c  lea     r12, aWinsatSystemco; "/WinSAT/SystemConfig/HistoryVersion"
0x180007193  mov     rax, r12
0x180007196  test    rcx, rcx
0x180007199  jz      loc_1800074CF
0x18000719f  cmp     [rax], r14w
0x1800071a3  jz      short loc_1800071AE
0x1800071a5  add     rax, 2
0x1800071a9  sub     rcx, r15
0x1800071ac  jmp     short loc_180007196
0x1800071ae  test    rax, rax
0x1800071b1  jz      loc_1800074CF
0x1800071b7  sub     rax, r12
0x1800071ba  sar     rax, 1
0x1800071bd  mov     [rbx], rax
0x1800071c0  mov     [rbx+8], rax
0x1800071c4  lea     rcx, [rax+1]
0x1800071c8  mov     rax, r14
0x1800071cb  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1800071d5  test    rcx, rcx
0x1800071d8  jz      short loc_1800071F2
0x1800071da  cmp     rcx, rdx
0x1800071dd  ja      short loc_1800071EC
0x1800071df  add     rcx, rcx; Size
0x1800071e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800071e7  test    rax, rax
0x1800071ea  jnz     short loc_1800071F2
0x1800071ec  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800071f2  mov     [rbx+18h], rax
0x1800071f6  test    rax, rax
0x1800071f9  jnz     short loc_180007239
0x1800071fb  lea     rax, aBadAllocation; "bad allocation"
0x180007202  mov     [rbp+bstrString], rax
0x180007206  mov     r8d, r15d
0x180007209  lea     rdx, [rbp+bstrString]
0x18000720d  lea     rcx, [rbp+pExceptionObject]
0x180007211  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180007218  nop     dword ptr [rax+rax+00h]
0x18000721d  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180007224  mov     [rbp+pExceptionObject], rax
0x180007228  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000722f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007233  call    _CxxThrowException_0
0x180007239  mov     r8, [rbx]
0x18000723c  test    r8, r8
0x18000723f  jz      short loc_18000724F
0x180007241  add     r8, r8; Size
0x180007244  mov     rdx, r12; Src
0x180007247  mov     rcx, rax; void *
0x18000724a  call    memcpy_0
0x18000724f  mov     rcx, [rbx+18h]
0x180007253  test    rcx, rcx
0x180007256  jz      short loc_180007260
0x180007258  mov     rax, [rbx]
0x18000725b  mov     [rcx+rax*2], r14w
0x180007260  mov     [rbp+arg_18], rbx
0x180007264  mov     [rbp+bstrString], r14
0x180007268  lea     r9, [rbp+bstrString]
0x18000726c  mov     r8b, r15b
0x18000726f  lea     rdx, [rbp+arg_18]
0x180007273  mov     rcx, rdi
0x180007276  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18000727b  mov     r12d, eax
0x18000727e  test    eax, eax
0x180007280  js      loc_18000746A
0x180007286  mov     rdi, [rbp+bstrString]
0x18000728a  test    rdi, rdi
0x18000728d  jz      loc_18000746E
0x180007293  mov     ecx, 28h ; '('; Size
0x180007298  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000729d  mov     rbx, rax
0x1800072a0  test    rax, rax
0x1800072a3  jnz     short loc_1800072AB
0x1800072a5  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800072ab  mov     [rbp+var_20], rbx
0x1800072af  mov     [rax], r14
0x1800072b2  mov     [rax+8], r14
0x1800072b6  mov     [rax+10h], r15
0x1800072ba  mov     [rax+18h], r14
0x1800072be  test    rdi, rdi
0x1800072c1  jz      loc_180007395
0x1800072c7  cmp     [rdi], r14w
0x1800072cb  jz      loc_180007395
0x1800072d1  mov     rax, rdi
0x1800072d4  test    rsi, rsi
0x1800072d7  jz      loc_180007384
0x1800072dd  cmp     [rax], r14w
0x1800072e1  jz      short loc_1800072EC
0x1800072e3  add     rax, 2
0x1800072e7  sub     rsi, r15
0x1800072ea  jmp     short loc_1800072D4
0x1800072ec  test    rax, rax
0x1800072ef  jz      loc_180007384
0x1800072f5  sub     rax, rdi
0x1800072f8  sar     rax, 1
0x1800072fb  mov     [rbx], rax
0x1800072fe  mov     [rbx+8], rax
0x180007302  lea     rcx, [rax+1]
0x180007306  mov     rax, r14
0x180007309  test    rcx, rcx
0x18000730c  jz      short loc_180007330
0x18000730e  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007318  cmp     rcx, rax
0x18000731b  ja      short loc_18000732A
0x18000731d  add     rcx, rcx; Size
0x180007320  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007325  test    rax, rax
0x180007328  jnz     short loc_180007330
0x18000732a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007330  mov     [rbx+18h], rax
0x180007334  test    rax, rax
0x180007337  jnz     short loc_180007377
0x180007339  lea     rax, aBadAllocation; "bad allocation"
0x180007340  mov     [rbp+var_30], rax
0x180007344  mov     r8d, r15d
0x180007347  lea     rdx, [rbp+var_30]
0x18000734b  lea     rcx, [rbp+pExceptionObject]
0x18000734f  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180007356  nop     dword ptr [rax+rax+00h]
0x18000735b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180007362  mov     [rbp+pExceptionObject], rax
0x180007366  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000736d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007371  call    _CxxThrowException_0
0x180007377  mov     r8, [rbx]
0x18000737a  test    r8, r8
0x18000737d  jz      short loc_1800073C1
0x18000737f  mov     rdx, rdi
0x180007382  jmp     short loc_1800073B6
0x180007384  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x18000738b  lea     rcx, [rbp+arg_8]; pExceptionObject
0x18000738f  call    _CxxThrowException_0
0x180007395  mov     ecx, 2; Size
0x18000739a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000739f  test    rax, rax
0x1800073a2  jz      loc_1800074C9
0x1800073a8  mov     [rbx+18h], rax
0x1800073ac  mov     r8, [rbx]
0x1800073af  test    r8, r8
0x1800073b2  jz      short loc_1800073C1
0x1800073b4  xor     edx, edx; Src
0x1800073b6  add     r8, r8; Size
0x1800073b9  mov     rcx, rax; void *
0x1800073bc  call    memcpy_0
0x1800073c1  mov     rcx, [rbx+18h]
0x1800073c5  test    rcx, rcx
0x1800073c8  jz      short loc_1800073D2
0x1800073ca  mov     rax, [rbx]
0x1800073cd  mov     [rcx+rax*2], r14w
0x1800073d2  mov     r15d, r14d
0x1800073d5  mov     rsi, [rbx]
0x1800073d8  mov     rdi, [rbx+18h]
0x1800073dc  test    rsi, rsi
0x1800073df  jz      short loc_18000743B
0x1800073e1  movzx   ecx, word ptr [rdi]
0x1800073e4  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x1800073e9  test    al, al
0x1800073eb  jz      short loc_1800073F9
0x1800073ed  add     rdi, 2
0x1800073f1  sub     rsi, 1
0x1800073f5  jnz     short loc_1800073E1
0x1800073f7  jmp     short loc_18000743B
0x1800073f9  movzx   ecx, word ptr [rdi]; C
0x1800073fc  call    cs:__imp_iswdigit
0x180007403  nop     dword ptr [rax+rax+00h]
0x180007408  test    eax, eax
0x18000740a  jz      short loc_18000743B
0x18000740c  lea     r14d, [r14+r14*4]
0x180007410  movzx   eax, word ptr [rdi]
0x180007413  lea     r14d, [r14-18h]
0x180007417  lea     r14d, [rax+r14*2]
0x18000741b  sub     rsi, 1
0x18000741f  jz      short loc_180007438
0x180007421  add     rdi, 2
0x180007425  movzx   ecx, word ptr [rdi]; C
0x180007428  call    cs:__imp_iswdigit
0x18000742f  nop     dword ptr [rax+rax+00h]
0x180007434  test    eax, eax
0x180007436  jnz     short loc_18000740C
0x180007438  mov     r15d, r14d
0x18000743b  mov     [r13+0], r15d
0x18000743f  sub     qword ptr [rbx+10h], 1
0x180007444  jnz     short loc_18000746A
0x180007446  mov     rcx, [rbx+18h]
0x18000744a  test    rcx, rcx
0x18000744d  jz      short loc_18000745B
0x18000744f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007456  nop     dword ptr [rax+rax+00h]
0x18000745b  mov     rcx, rbx
0x18000745e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007465  nop     dword ptr [rax+rax+00h]
0x18000746a  mov     rdi, [rbp+bstrString]
0x18000746e  mov     rcx, rdi; bstrString
0x180007471  call    cs:__imp_SysFreeString
0x180007478  nop     dword ptr [rax+rax+00h]
0x18000747d  nop
0x18000747e  mov     rbx, [rbp+arg_18]
0x180007482  sub     qword ptr [rbx+10h], 1
0x180007487  jnz     short loc_1800074AD
0x180007489  mov     rcx, [rbx+18h]
0x18000748d  test    rcx, rcx
0x180007490  jz      short loc_18000749E
0x180007492  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007499  nop     dword ptr [rax+rax+00h]
0x18000749e  mov     rcx, rbx
0x1800074a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800074a8  nop     dword ptr [rax+rax+00h]
0x1800074ad  mov     eax, r12d
0x1800074b0  mov     rbx, [rsp+60h+arg_0]
0x1800074b8  add     rsp, 60h
0x1800074bc  pop     r15
0x1800074be  pop     r14
0x1800074c0  pop     r13
0x1800074c2  pop     r12
0x1800074c4  pop     rdi
0x1800074c5  pop     rsi
0x1800074c6  pop     rbp
0x1800074c7  retn
0x1800074c9  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800074cf  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x1800074d6  lea     rcx, [rbp+arg_8]; pExceptionObject
0x1800074da  call    _CxxThrowException_0
```

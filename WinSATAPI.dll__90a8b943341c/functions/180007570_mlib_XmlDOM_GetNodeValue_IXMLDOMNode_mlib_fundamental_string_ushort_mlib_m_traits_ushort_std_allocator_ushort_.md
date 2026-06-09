# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180007570`
- end: `0x18000784a`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z`
- size: `730`
- prototype: `__int64 __fastcall(int, int, int, int, WORD CharType)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002cbd0`
- `0x18002ccd8`
- `0x18002d020`

## callees

- `0x180007570`
- `0x180007850`
- `0x180011e70`
- `0x180011ee0`
- `0x180012bf3`
- `0x180012c06`

## import_xrefs

- `msvcrt!iswdigit` at `0x180007749`
- `msvcrt!iswdigit` at `0x18000777d`
- `msvcrt!iswdigit` at `0x180007749`
- `msvcrt!iswdigit` at `0x18000777d`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800077f9`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800077f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007635`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007644`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007635`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007644`
- `OLEAUT32!__imp_SysFreeString` at `0x180007658`
- `OLEAUT32!__imp_SysFreeString` at `0x180007658`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x180007732`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x180007732`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, char a3, int *a4, WORD CharType)
{
  int v6; // edi
  int NodeValue; // r14d
  BSTR v8; // rsi
  __int64 *v9; // rax
  __int64 *v10; // rbx
  __int64 v11; // rcx
  BSTR i; // rax
  void *v14; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  void *v18; // rax
  __int64 v19; // r8
  BSTR v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rbp
  WCHAR *v23; // rsi
  int lpCharType; // [rsp+20h] [rbp-68h]
  WCHAR SrcStr; // [rsp+30h] [rbp-58h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-50h] BYREF
  const char *v27[3]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+58h] [rbp-30h] BYREF

  v27[1] = (const char *)-2LL;
  v6 = 0;
  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, a3, (__int64)&bstrString, lpCharType);
  if ( NodeValue < 0 )
  {
LABEL_15:
    v8 = bstrString;
    goto LABEL_16;
  }
  v8 = bstrString;
  if ( bstrString )
  {
    v9 = (__int64 *)operator new(0x28u);
    v10 = v9;
    if ( !v9 )
      std::_Xbad_alloc();
    v27[2] = (const char *)v9;
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 1;
    v9[3] = 0;
    if ( v8 && *v8 )
    {
      v11 = 0x10000;
      for ( i = v8; ; ++i )
      {
        if ( !v11 )
          throw (mlib::CStringTooBig *)&CharType;
        if ( !*i )
          break;
        --v11;
      }
      v16 = i - v8;
      *v10 = v16;
      v10[1] = v16;
      v17 = v16 + 1;
      v18 = 0;
      if ( v17 )
      {
        if ( v17 > 0x7FFFFFFFFFFFFFFFLL || (v18 = operator new(2 * v17)) == 0 )
          std::_Xbad_alloc();
      }
      v10[3] = (__int64)v18;
      if ( !v18 )
      {
        v27[0] = "bad allocation";
        exception::exception((exception *)pExceptionObject, v27, 1);
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      v19 = *v10;
      if ( !*v10 )
        goto LABEL_24;
      v20 = v8;
    }
    else
    {
      v18 = operator new(2u);
      if ( !v18 )
        std::_Xbad_alloc();
      v10[3] = (__int64)v18;
      v19 = *v10;
      if ( !*v10 )
        goto LABEL_24;
      v20 = 0;
    }
    memcpy_0(v18, v20, 2 * v19);
LABEL_24:
    v21 = v10[3];
    if ( v21 )
      *(_WORD *)(v21 + 2 * *v10) = 0;
    v22 = *v10;
    v23 = (WCHAR *)v10[3];
    if ( *v10 )
    {
      while ( 1 )
      {
        SrcStr = *v23;
        CharType = 0;
        if ( !GetStringTypeExW(0x400u, 1u, &SrcStr, 1, &CharType) )
          break;
        if ( (CharType & 0x48) == 0 )
        {
          if ( !v22 )
            goto LABEL_11;
          break;
        }
        ++v23;
        if ( !--v22 )
          goto LABEL_11;
      }
      while ( iswdigit(*v23) )
      {
        v6 = *v23 + 2 * (5 * v6 - 24);
        if ( !--v22 )
          break;
        ++v23;
      }
    }
LABEL_11:
    *a4 = v6;
    if ( v10[2]-- == 1 )
    {
      v14 = (void *)v10[3];
      if ( v14 )
        operator delete(v14);
      operator delete(v10);
    }
    goto LABEL_15;
  }
LABEL_16:
  SysFreeString(v8);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x180007570  mov     rax, rsp
0x180007573  push    rdi
0x180007574  push    r14
0x180007576  push    r15
0x180007578  sub     rsp, 70h
0x18000757c  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x180007584  mov     [rax+8], rbx
0x180007588  mov     [rax+10h], rbp
0x18000758c  mov     [rax+18h], rsi
0x180007590  mov     r15, r9
0x180007593  xor     edi, edi
0x180007595  mov     [rax-50h], rdi
0x180007599  lea     r9, [rax-50h]
0x18000759d  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1800075a2  mov     r14d, eax
0x1800075a5  test    eax, eax
0x1800075a7  js      loc_180007650
0x1800075ad  mov     rsi, [rsp+88h+bstrString]
0x1800075b2  test    rsi, rsi
0x1800075b5  jz      loc_180007655
0x1800075bb  lea     ecx, [rdi+28h]; Size
0x1800075be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800075c3  mov     rbx, rax
0x1800075c6  test    rax, rax
0x1800075c9  jz      loc_1800077D1
0x1800075cf  mov     [rsp+88h+var_38], rax
0x1800075d4  mov     [rax], rdi
0x1800075d7  mov     [rax+8], rdi
0x1800075db  mov     qword ptr [rax+10h], 1
0x1800075e3  mov     [rax+18h], rdi
0x1800075e7  test    rsi, rsi
0x1800075ea  jz      loc_1800077A7
0x1800075f0  cmp     [rsi], di
0x1800075f3  jz      loc_1800077A7
0x1800075f9  mov     ecx, 10000h
0x1800075fe  mov     rax, rsi
0x180007601  test    rcx, rcx
0x180007604  jz      loc_180007792
0x18000760a  cmp     word ptr [rax], 0
0x18000760e  jz      short loc_180007682
0x180007610  add     rax, 2
0x180007614  dec     rcx
0x180007617  jmp     short loc_180007601
0x180007619  test    rbp, rbp
0x18000761c  jnz     loc_180007746
0x180007622  mov     [r15], edi
0x180007625  sub     qword ptr [rbx+10h], 1
0x18000762a  jnz     short loc_180007650
0x18000762c  mov     rcx, [rbx+18h]
0x180007630  test    rcx, rcx
0x180007633  jz      short loc_180007641
0x180007635  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000763c  nop     dword ptr [rax+rax+00h]
0x180007641  mov     rcx, rbx
0x180007644  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000764b  nop     dword ptr [rax+rax+00h]
0x180007650  mov     rsi, [rsp+88h+bstrString]
0x180007655  mov     rcx, rsi; bstrString
0x180007658  call    cs:__imp_SysFreeString
0x18000765f  nop     dword ptr [rax+rax+00h]
0x180007664  mov     eax, r14d
0x180007667  lea     r11, [rsp+88h+var_18]
0x18000766c  mov     rbx, [r11+20h]
0x180007670  mov     rbp, [r11+28h]
0x180007674  mov     rsi, [r11+30h]
0x180007678  mov     rsp, r11
0x18000767b  pop     r15
0x18000767d  pop     r14
0x18000767f  pop     rdi
0x180007680  retn
0x180007682  sub     rax, rsi
0x180007685  sar     rax, 1
0x180007688  mov     [rbx], rax
0x18000768b  mov     [rbx+8], rax
0x18000768f  lea     rcx, [rax+1]
0x180007693  mov     rax, rdi
0x180007696  test    rcx, rcx
0x180007699  jz      short loc_1800076BF
0x18000769b  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800076a5  cmp     rcx, rax
0x1800076a8  ja      loc_1800077D7
0x1800076ae  add     rcx, rcx; Size
0x1800076b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076b6  test    rax, rax
0x1800076b9  jz      loc_1800077D7
0x1800076bf  mov     [rbx+18h], rax
0x1800076c3  test    rax, rax
0x1800076c6  jz      loc_1800077DD
0x1800076cc  mov     r8, [rbx]
0x1800076cf  test    r8, r8
0x1800076d2  jz      short loc_1800076E2
0x1800076d4  mov     rdx, rsi; Src
0x1800076d7  add     r8, r8; Size
0x1800076da  mov     rcx, rax; void *
0x1800076dd  call    memcpy_0
0x1800076e2  mov     rcx, [rbx+18h]
0x1800076e6  test    rcx, rcx
0x1800076e9  jz      short loc_1800076F2
0x1800076eb  mov     rax, [rbx]
0x1800076ee  mov     [rcx+rax*2], di
0x1800076f2  mov     rbp, [rbx]
0x1800076f5  mov     rsi, [rbx+18h]
0x1800076f9  test    rbp, rbp
0x1800076fc  jz      loc_180007622
0x180007702  movzx   eax, word ptr [rsi]
0x180007705  mov     [rsp+88h+SrcStr], ax
0x18000770a  mov     [rsp+88h+CharType], di
0x180007712  lea     rax, [rsp+88h+CharType]
0x18000771a  mov     qword ptr [rsp+88h+lpCharType], rax; lpCharType
0x18000771f  mov     r9d, 1; cchSrc
0x180007725  lea     r8, [rsp+88h+SrcStr]; lpSrcStr
0x18000772a  mov     edx, r9d; dwInfoType
0x18000772d  mov     ecx, 400h; Locale
0x180007732  call    cs:__imp_GetStringTypeExW
0x180007739  nop     dword ptr [rax+rax+00h]
0x18000773e  test    eax, eax
0x180007740  jnz     loc_180007823
0x180007746  movzx   ecx, word ptr [rsi]; C
0x180007749  call    cs:__imp_iswdigit
0x180007750  nop     dword ptr [rax+rax+00h]
0x180007755  test    eax, eax
0x180007757  jz      loc_180007622
0x18000775d  nop     dword ptr [rax]
0x180007760  lea     edi, [rdi+rdi*4]
0x180007763  movzx   eax, word ptr [rsi]
0x180007766  lea     edi, [rdi-18h]
0x180007769  lea     edi, [rax+rdi*2]
0x18000776c  sub     rbp, 1
0x180007770  jz      loc_180007622
0x180007776  add     rsi, 2
0x18000777a  movzx   ecx, word ptr [rsi]; C
0x18000777d  call    cs:__imp_iswdigit
0x180007784  nop     dword ptr [rax+rax+00h]
0x180007789  test    eax, eax
0x18000778b  jnz     short loc_180007760
0x18000778d  jmp     loc_180007622
0x180007792  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x180007799  lea     rcx, [rsp+88h+CharType]; pExceptionObject
0x1800077a1  call    _CxxThrowException_0
0x1800077a7  mov     ecx, 2; Size
0x1800077ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800077b1  test    rax, rax
0x1800077b4  jz      loc_180007844
0x1800077ba  mov     [rbx+18h], rax
0x1800077be  mov     r8, [rbx]
0x1800077c1  test    r8, r8
0x1800077c4  jz      loc_1800076E2
0x1800077ca  xor     edx, edx
0x1800077cc  jmp     loc_1800076D7
0x1800077d1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800077d7  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800077dd  lea     rax, aBadAllocation; "bad allocation"
0x1800077e4  mov     [rsp+88h+var_48], rax
0x1800077e9  mov     r8d, 1
0x1800077ef  lea     rdx, [rsp+88h+var_48]
0x1800077f4  lea     rcx, [rsp+88h+pExceptionObject]
0x1800077f9  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180007800  nop     dword ptr [rax+rax+00h]
0x180007805  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000780c  mov     [rsp+88h+pExceptionObject], rax
0x180007811  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180007818  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000781d  call    _CxxThrowException_0
0x180007823  test    byte ptr [rsp+88h+CharType], 48h
0x18000782b  jz      loc_180007619
0x180007831  add     rsi, 2
0x180007835  sub     rbp, 1
0x180007839  jnz     loc_180007702
0x18000783f  jmp     loc_180007622
0x180007844  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

# JDictsFilterDictionary::GetReplacedWord(ushort const *,ushort const *,ulong,int *,ushort * *)

- ea: `0x180018030`
- end: `0x18001850a`
- name: `?GetReplacedWord@JDictsFilterDictionary@@UEAAJPEBG0KPEAHPEAPEAG@Z`
- size: `1242`
- prototype: `__int64 __fastcall(JDictsFilterDictionary *this, char *, unsigned __int16 *, int, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180005ca4`
- `0x18000cde4`
- `0x18000cef4`
- `0x180018030`
- `0x180018510`
- `0x180018f00`
- `0x18001b2b8`
- `0x18001c924`
- `0x18001ca74`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018442`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018454`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018475`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800184a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800184ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800184db`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018442`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018454`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018475`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800184a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800184ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800184db`
- `OLEAUT32!__imp_SysAllocString` at `0x1800183dc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800183dc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018493`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018493`
- `OLEAUT32!__imp_SysFreeString` at `0x1800183a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800183a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JDictsFilterDictionary::GetReplacedWord(
        JDictsFilterDictionary *this,
        char *a2,
        unsigned __int16 *a3,
        int a4,
        int *a5,
        unsigned __int16 **a6)
{
  int DictData; // eax
  unsigned int v11; // ebx
  __int64 v13; // rax
  _DWORD *v14; // rdx
  _DWORD *v15; // rax
  BOOL v16; // ecx
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // r8
  int v19; // esi
  OLECHAR **v20; // rdx
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  int v23; // eax
  struct FilterReplaceWord *v24; // rcx
  char *v25; // rcx
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // r10
  unsigned __int64 v29; // rcx
  __int64 v30; // r9
  OLECHAR **v31; // rax
  unsigned __int16 v32; // r11
  __int64 v33; // r8
  __int64 v34; // rcx
  unsigned __int64 v35; // r8
  struct FilterReplaceWord *v36; // rcx
  unsigned __int16 *v37; // rax
  unsigned __int64 v38; // rcx
  OLECHAR **v39; // r8
  const OLECHAR *v40; // rcx
  int v41; // [rsp+20h] [rbp-89h]
  struct FilterReplaceWord *v42; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v43; // [rsp+38h] [rbp-71h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int8 *v45; // [rsp+48h] [rbp-61h] BYREF
  OLECHAR *strIn[2]; // [rsp+50h] [rbp-59h] BYREF
  UINT ui[2]; // [rsp+60h] [rbp-49h]
  unsigned __int64 v48; // [rsp+68h] [rbp-41h]
  void *v49[2]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v50; // [rsp+80h] [rbp-29h]
  unsigned __int64 v51; // [rsp+88h] [rbp-21h]
  void *v52[3]; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v53; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]

  *a5 = 0;
  *a6 = 0;
  if ( !*((_DWORD *)this + 12) )
  {
    DictData = JDictsFilterDictionary::InitGetDictData(this);
    v11 = DictData;
    if ( DictData < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsfilterdictionary.cpp",
        (const char *)(unsigned int)DictData,
        v41);
      return v11;
    }
  }
  if ( *((_DWORD *)this + 12) )
  {
    v13 = *((_QWORD *)this + 11);
    if ( v13 )
    {
      v14 = *(_DWORD **)(v13 + 16);
      v15 = *(_DWORD **)(v13 + 8);
      if ( v15 == v14 )
      {
        v16 = 0;
      }
      else
      {
        do
        {
          if ( *v15 == a4 )
            break;
          ++v15;
        }
        while ( v15 != v14 );
        v16 = v14 != v15;
      }
      if ( v16 )
        return 1;
    }
  }
  v48 = 7;
  *(_QWORD *)ui = 0;
  LOWORD(strIn[0]) = 0;
  v17 = -1;
  if ( *(_WORD *)a2 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)&a2[2 * v18] );
  }
  else
  {
    v18 = 0;
  }
  std::wstring::assign(strIn, a2, v18);
  v51 = 7;
  v50 = 0;
  LOWORD(v49[0]) = 0;
  JDictsFilterDictionary::SearchReplaceChar(this, strIn, v49);
  if ( v50 )
    std::wstring::assign((void **)strIn, v49, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v53 = 7;
  v52[2] = 0;
  LOWORD(v52[0]) = 0;
  std::wstring::assign(v52, (void **)strIn, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v19 = 0;
  while ( 1 )
  {
    v45 = 0;
    v43 = 0;
    std::wstring::assign(v49, (char *)&dword_180028204, 0);
    v20 = strIn;
    if ( v48 >= 8 )
      v20 = (OLECHAR **)strIn[0];
    v21 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR **, unsigned __int8 **, unsigned int *))(**((_QWORD **)this + 23)
                                                                                            + 40LL))(
            *((_QWORD *)this + 23),
            v20,
            &v45,
            &v43);
    if ( v21 >= 0 )
      break;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsfilterdictionary.cpp",
      (const char *)(unsigned int)v21,
      v41);
LABEL_30:
    if ( v19 )
    {
      if ( ++v19 >= 2 )
        goto LABEL_35;
    }
    else
    {
      v25 = (char *)strIn;
      if ( v48 >= 8 )
        v25 = (char *)strIn[0];
      FilterReplaceWord::EncodeKey(v25, a3, strIn);
      v19 = 1;
    }
  }
  if ( v21 || !v43 )
    goto LABEL_30;
  bstrString = 0;
  v42 = 0;
  v22 = (const unsigned __int16 *)strIn;
  if ( v48 >= 8 )
    v22 = strIn[0];
  v23 = FilterReplaceWord::CreateInstance(&v42, v22, v45, v43);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsfilterdictionary.cpp",
      (const char *)(unsigned int)v23,
      v41);
    v24 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(struct FilterReplaceWord *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_30;
  }
  if ( !(*(unsigned int (__fastcall **)(struct FilterReplaceWord *, BSTR *))(*(_QWORD *)v42 + 56LL))(v42, &bstrString) )
  {
    if ( *bstrString )
    {
      v35 = -1;
      do
        ++v35;
      while ( bstrString[v35] );
    }
    else
    {
      v35 = 0;
    }
    std::wstring::assign(v49, (char *)bstrString, v35);
  }
  SysFreeString(bstrString);
  v36 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(struct FilterReplaceWord *))(*(_QWORD *)v36 + 16LL))(v36);
  }
  if ( !v50 )
    goto LABEL_62;
LABEL_35:
  std::wstring::assign((void **)strIn, v52, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v50 )
    std::wstring::assign((void **)strIn, v49, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( !*((_DWORD *)this + 12) )
  {
LABEL_50:
    v27 = *(_QWORD *)ui;
    goto LABEL_51;
  }
  v26 = *((_QWORD *)this + 7);
  v27 = *(_QWORD *)ui;
  if ( v26 && *(_QWORD *)ui )
  {
    v28 = *(_QWORD *)(v26 + 8);
    v29 = (unsigned __int64)(*(_QWORD *)(v26 + 16) - v28) >> 1;
    v30 = 0;
    while ( 1 )
    {
      v31 = strIn;
      if ( v48 >= 8 )
        v31 = (OLECHAR **)strIn[0];
      v32 = *((_WORD *)v31 + v30);
      v33 = 0;
      if ( v29 > 1 )
        break;
LABEL_47:
      if ( (unsigned __int64)++v30 >= *(_QWORD *)ui )
        goto LABEL_48;
    }
    while ( v32 < *(_WORD *)(v28 + 2 * v33) || v32 > *(_WORD *)(v28 + 2 * v33 + 2) )
    {
      v33 += 2;
      if ( v33 + 1 >= v29 )
        goto LABEL_47;
    }
    goto LABEL_62;
  }
LABEL_48:
  v34 = *((_QWORD *)this + 8);
  if ( !v34 )
  {
LABEL_51:
    if ( *(_WORD *)a2 )
    {
      do
        ++v17;
      while ( *(_WORD *)&a2[2 * v17] );
    }
    else
    {
      v17 = 0;
    }
    v38 = v27;
    if ( v27 >= v17 )
      v38 = v17;
    v39 = strIn;
    if ( v48 >= 8 )
      v39 = (OLECHAR **)strIn[0];
    if ( v38 )
    {
      while ( *(_WORD *)v39 == *(_WORD *)a2 )
      {
        v39 = (OLECHAR **)((char *)v39 + 2);
        a2 += 2;
        if ( !--v38 )
          goto LABEL_74;
      }
    }
    else
    {
LABEL_74:
      if ( v27 == v17 )
      {
        if ( v53 >= 8 )
          operator delete(v52[0]);
        if ( v51 >= 8 )
          operator delete(v49[0]);
        v51 = 7;
        v50 = 0;
        LOWORD(v49[0]) = 0;
        if ( v48 >= 8 )
          operator delete(strIn[0]);
        return 1;
      }
    }
    v40 = (const OLECHAR *)strIn;
    if ( v48 >= 8 )
      v40 = strIn[0];
    v37 = SysAllocStringLen(v40, ui[0]);
    goto LABEL_85;
  }
  if ( !(unsigned int)FilterChar::fFindChar(v34, strIn) )
    goto LABEL_50;
LABEL_62:
  if ( !*((_DWORD *)this + 24) || !*((_DWORD *)this + 25) )
  {
    *a5 = 1;
    goto LABEL_86;
  }
  v37 = SysAllocString(a3);
LABEL_85:
  *a6 = v37;
LABEL_86:
  if ( v53 >= 8 )
    operator delete(v52[0]);
  if ( v51 >= 8 )
    operator delete(v49[0]);
  v51 = 7;
  v50 = 0;
  LOWORD(v49[0]) = 0;
  if ( v48 >= 8 )
    operator delete(strIn[0]);
  return 0;
}

```

## disassembly

```asm
0x180018030  mov     [rsp-8+arg_18], rbx
0x180018035  push    rbp
0x180018036  push    rsi
0x180018037  push    rdi
0x180018038  push    r12
0x18001803a  push    r13
0x18001803c  push    r14
0x18001803e  push    r15
0x180018040  lea     rbp, [rsp-17h]
0x180018045  sub     rsp, 0C0h
0x18001804c  mov     rax, cs:__security_cookie
0x180018053  xor     rax, rsp
0x180018056  mov     [rbp+47h+var_40], rax
0x18001805a  mov     esi, r9d
0x18001805d  mov     r13, r8
0x180018060  mov     r14, rdx
0x180018063  mov     rdi, rcx
0x180018066  mov     r15, [rbp+47h+arg_20]
0x18001806a  mov     r12, [rbp+47h+arg_28]
0x18001806e  xor     r9d, r9d
0x180018071  mov     [r15], r9d
0x180018074  mov     [r12], r9
0x180018078  cmp     [rcx+30h], r9d
0x18001807c  jnz     short loc_1800180AB
0x18001807e  call    ?InitGetDictData@JDictsFilterDictionary@@AEAAJXZ; JDictsFilterDictionary::InitGetDictData(void)
0x180018083  mov     ebx, eax
0x180018085  xor     r9d, r9d
0x180018088  test    eax, eax
0x18001808a  jns     short loc_1800180AB
0x18001808c  mov     rcx, [rbp+4Fh]; this
0x180018090  mov     r9d, eax; char *
0x180018093  lea     r8, aMincoreTextinp_22; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001809a  mov     edx, 9Fh; void *
0x18001809f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180a4  mov     eax, ebx
0x1800180a6  jmp     loc_1800184E3
0x1800180ab  cmp     [rdi+30h], r9d
0x1800180af  jz      short loc_1800180EA
0x1800180b1  mov     rax, [rdi+58h]
0x1800180b5  test    rax, rax
0x1800180b8  jz      short loc_1800180EA
0x1800180ba  mov     rdx, [rax+10h]
0x1800180be  mov     rax, [rax+8]
0x1800180c2  cmp     rax, rdx
0x1800180c5  jnz     short loc_1800180CC
0x1800180c7  mov     ecx, r9d
0x1800180ca  jmp     short loc_1800180E2
0x1800180cc  cmp     [rax], esi
0x1800180ce  jz      short loc_1800180D9
0x1800180d0  add     rax, 4
0x1800180d4  cmp     rax, rdx
0x1800180d7  jnz     short loc_1800180CC
0x1800180d9  mov     ecx, r9d
0x1800180dc  cmp     rdx, rax
0x1800180df  setnz   cl
0x1800180e2  test    ecx, ecx
0x1800180e4  jnz     loc_18001847B
0x1800180ea  mov     esi, 7
0x1800180ef  mov     [rbp+47h+var_88], rsi
0x1800180f3  mov     qword ptr [rbp+47h+ui], r9
0x1800180f7  mov     word ptr [rbp+47h+strIn], r9w
0x1800180fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018100  cmp     [r14], r9w
0x180018104  jnz     short loc_18001810B
0x180018106  mov     r8, r9
0x180018109  jmp     short loc_180018118
0x18001810b  mov     r8, rbx
0x18001810e  inc     r8
0x180018111  cmp     [r14+r8*2], r9w
0x180018116  jnz     short loc_18001810E
0x180018118  mov     rdx, r14; Src
0x18001811b  lea     rcx, [rbp+47h+strIn]; void *
0x18001811f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180018124  mov     [rbp+47h+var_68], rsi
0x180018128  xor     esi, esi
0x18001812a  mov     [rbp+47h+var_70], rsi
0x18001812e  mov     word ptr [rbp+47h+var_80], si
0x180018132  lea     r8, [rbp+47h+var_80]
0x180018136  lea     rdx, [rbp+47h+strIn]
0x18001813a  mov     rcx, rdi
0x18001813d  call    ?SearchReplaceChar@JDictsFilterDictionary@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JDictsFilterDictionary::SearchReplaceChar(std::wstring const &,std::wstring &)
0x180018142  cmp     [rbp+47h+var_70], rsi
0x180018146  jz      short loc_18001815B
0x180018148  mov     r9, rbx
0x18001814b  xor     r8d, r8d
0x18001814e  lea     rdx, [rbp+47h+var_80]
0x180018152  lea     rcx, [rbp+47h+strIn]; void *
0x180018156  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001815b  mov     [rbp+47h+var_48], 7
0x180018163  mov     [rbp+47h+var_50], rsi
0x180018167  mov     word ptr [rbp+47h+var_60], si
0x18001816b  mov     r9, rbx
0x18001816e  xor     r8d, r8d
0x180018171  lea     rdx, [rbp+47h+strIn]
0x180018175  lea     rcx, [rbp+47h+var_60]; void *
0x180018179  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001817e  nop
0x18001817f  xor     esi, esi
0x180018181  mov     [rbp+47h+var_A8], 0
0x180018189  mov     [rbp+47h+var_B8], 0
0x180018190  xor     r8d, r8d
0x180018193  lea     rdx, dword_180028204; Src
0x18001819a  lea     rcx, [rbp+47h+var_80]; void *
0x18001819e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800181a3  mov     rcx, [rdi+0B8h]
0x1800181aa  mov     rax, [rcx]
0x1800181ad  lea     rdx, [rbp+47h+strIn]
0x1800181b1  cmp     [rbp+47h+var_88], 8
0x1800181b6  cmovnb  rdx, [rbp+47h+strIn]
0x1800181bb  lea     r9, [rbp+47h+var_B8]
0x1800181bf  lea     r8, [rbp+47h+var_A8]
0x1800181c3  mov     rax, [rax+28h]
0x1800181c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181cc  test    eax, eax
0x1800181ce  jns     short loc_1800181EA
0x1800181d0  mov     rcx, [rbp+4Fh]; this
0x1800181d4  mov     r9d, eax; char *
0x1800181d7  lea     r8, aMincoreTextinp_22; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x1800181de  mov     edx, 175h; void *
0x1800181e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181e8  jmp     short loc_18001825F
0x1800181ea  jnz     short loc_18001825F
0x1800181ec  mov     r9d, [rbp+47h+var_B8]; unsigned int
0x1800181f0  test    r9d, r9d
0x1800181f3  jz      short loc_18001825F
0x1800181f5  mov     [rbp+47h+bstrString], 0
0x1800181fd  mov     [rbp+47h+var_C0], 0
0x180018205  lea     rdx, [rbp+47h+strIn]
0x180018209  cmp     [rbp+47h+var_88], 8
0x18001820e  cmovnb  rdx, [rbp+47h+strIn]; unsigned __int16 *
0x180018213  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180018217  lea     rcx, [rbp+47h+var_C0]; struct FilterReplaceWord **
0x18001821b  call    ?CreateInstance@FilterReplaceWord@@SAJPEAPEAV1@PEBGPEBEI@Z; FilterReplaceWord::CreateInstance(FilterReplaceWord * *,ushort const *,uchar const *,uint)
0x180018220  test    eax, eax
0x180018222  jns     loc_180018362
0x180018228  mov     rcx, [rbp+4Fh]; this
0x18001822c  mov     r9d, eax; char *
0x18001822f  lea     r8, aMincoreTextinp_22; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180018236  mov     edx, 17Bh; void *
0x18001823b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018240  nop
0x180018241  mov     rcx, [rbp+47h+var_C0]
0x180018245  test    rcx, rcx
0x180018248  jz      short loc_18001825F
0x18001824a  mov     [rbp+47h+var_C0], 0
0x180018252  mov     rax, [rcx]
0x180018255  mov     rax, [rax+10h]
0x180018259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001825e  nop
0x18001825f  test    esi, esi
0x180018261  jnz     short loc_180018284
0x180018263  lea     rcx, [rbp+47h+strIn]
0x180018267  cmp     [rbp+47h+var_88], 8
0x18001826c  cmovnb  rcx, [rbp+47h+strIn]; Src
0x180018271  lea     r8, [rbp+47h+strIn]; void *
0x180018275  mov     rdx, r13; void *
0x180018278  call    ?EncodeKey@FilterReplaceWord@@SAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FilterReplaceWord::EncodeKey(ushort const *,ushort const *,std::wstring &)
0x18001827d  inc     esi
0x18001827f  jmp     loc_180018181
0x180018284  inc     esi
0x180018286  cmp     esi, 2
0x180018289  jl      loc_180018181
0x18001828f  xor     esi, esi
0x180018291  mov     r9, rbx
0x180018294  xor     r8d, r8d
0x180018297  lea     rdx, [rbp+47h+var_60]
0x18001829b  lea     rcx, [rbp+47h+strIn]; void *
0x18001829f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800182a4  cmp     [rbp+47h+var_70], rsi
0x1800182a8  jz      short loc_1800182BD
0x1800182aa  mov     r9, rbx
0x1800182ad  xor     r8d, r8d
0x1800182b0  lea     rdx, [rbp+47h+var_80]
0x1800182b4  lea     rcx, [rbp+47h+strIn]; void *
0x1800182b8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800182bd  cmp     [rdi+30h], esi
0x1800182c0  jz      loc_18001834C
0x1800182c6  mov     rcx, [rdi+38h]
0x1800182ca  mov     rdx, qword ptr [rbp+47h+ui]
0x1800182ce  test    rcx, rcx
0x1800182d1  jz      short loc_180018332
0x1800182d3  test    rdx, rdx
0x1800182d6  jz      short loc_180018332
0x1800182d8  mov     r10, [rcx+8]
0x1800182dc  mov     rcx, [rcx+10h]
0x1800182e0  sub     rcx, r10
0x1800182e3  shr     rcx, 1
0x1800182e6  mov     r9, rsi
0x1800182e9  test    rdx, rdx
0x1800182ec  jz      short loc_180018332
0x1800182ee  lea     rax, [rbp+47h+strIn]
0x1800182f2  cmp     [rbp+47h+var_88], 8
0x1800182f7  cmovnb  rax, [rbp+47h+strIn]
0x1800182fc  movzx   r11d, word ptr [rax+r9*2]
0x180018301  mov     r8, rsi
0x180018304  cmp     rcx, 1
0x180018308  jbe     short loc_18001832A
0x18001830a  cmp     r11w, [r10+r8*2]
0x18001830f  jb      short loc_18001831D
0x180018311  cmp     r11w, [r10+r8*2+2]
0x180018317  jbe     loc_1800183CF
0x18001831d  add     r8, 2
0x180018321  lea     rax, [r8+1]
0x180018325  cmp     rax, rcx
0x180018328  jb      short loc_18001830A
0x18001832a  inc     r9
0x18001832d  cmp     r9, rdx
0x180018330  jb      short loc_1800182EE
0x180018332  mov     rcx, [rdi+40h]
0x180018336  test    rcx, rcx
0x180018339  jz      short loc_180018350
0x18001833b  lea     rdx, [rbp+47h+strIn]
0x18001833f  call    ?fFindChar@FilterChar@@QEAAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FilterChar::fFindChar(std::wstring const &)
0x180018344  test    eax, eax
0x180018346  jnz     loc_1800183CF
0x18001834c  mov     rdx, qword ptr [rbp+47h+ui]
0x180018350  cmp     [r14], si
0x180018354  jnz     loc_1800183F3
0x18001835a  mov     rbx, rsi
0x18001835d  jmp     loc_1800183FD
0x180018362  mov     rcx, [rbp+47h+var_C0]
0x180018366  mov     rax, [rcx]
0x180018369  lea     rdx, [rbp+47h+bstrString]
0x18001836d  mov     rax, [rax+38h]
0x180018371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018376  xor     esi, esi
0x180018378  test    eax, eax
0x18001837a  jnz     short loc_1800183A0
0x18001837c  mov     rdx, [rbp+47h+bstrString]; Src
0x180018380  cmp     [rdx], si
0x180018383  jnz     short loc_18001838A
0x180018385  mov     r8d, esi
0x180018388  jmp     short loc_180018397
0x18001838a  mov     r8, rbx
0x18001838d  inc     r8
0x180018390  cmp     [rdx+r8*2], si
0x180018395  jnz     short loc_18001838D
0x180018397  lea     rcx, [rbp+47h+var_80]; void *
0x18001839b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800183a0  mov     rcx, [rbp+47h+bstrString]; bstrString
0x1800183a4  call    cs:__imp_SysFreeString
0x1800183aa  nop
0x1800183ab  mov     rcx, [rbp+47h+var_C0]
0x1800183af  test    rcx, rcx
0x1800183b2  jz      short loc_1800183C5
0x1800183b4  mov     [rbp+47h+var_C0], rsi
0x1800183b8  mov     rax, [rcx]
0x1800183bb  mov     rax, [rax+10h]
0x1800183bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183c4  nop
0x1800183c5  cmp     [rbp+47h+var_70], rsi
0x1800183c9  jnz     loc_180018291
0x1800183cf  cmp     [rdi+60h], esi
0x1800183d2  jz      short loc_1800183E7
0x1800183d4  cmp     [rdi+64h], esi
0x1800183d7  jz      short loc_1800183E7
0x1800183d9  mov     rcx, r13; psz
0x1800183dc  call    cs:__imp_SysAllocString
0x1800183e2  jmp     loc_180018499
0x1800183e7  mov     dword ptr [r15], 1
0x1800183ee  jmp     loc_18001849D
0x1800183f3  inc     rbx
0x1800183f6  cmp     [r14+rbx*2], si
0x1800183fb  jnz     short loc_1800183F3
0x1800183fd  mov     rcx, rdx
0x180018400  cmp     rdx, rbx
0x180018403  cmovnb  rcx, rbx
0x180018407  lea     r8, [rbp+47h+strIn]
0x18001840b  cmp     [rbp+47h+var_88], 8
0x180018410  cmovnb  r8, [rbp+47h+strIn]
0x180018415  test    rcx, rcx
0x180018418  jz      short loc_180018432
0x18001841a  movzx   eax, word ptr [r14]
0x18001841e  cmp     [r8], ax
0x180018422  jnz     short loc_180018482
0x180018424  add     r8, 2
0x180018428  add     r14, 2
0x18001842c  sub     rcx, 1
0x180018430  jnz     short loc_18001841A
0x180018432  cmp     rdx, rbx
0x180018435  jnz     short loc_180018482
0x180018437  cmp     [rbp+47h+var_48], 8
0x18001843c  jb      short loc_180018449
0x18001843e  mov     rcx, [rbp+47h+var_60]
0x180018442  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018448  nop
0x180018449  cmp     [rbp+47h+var_68], 8
0x18001844e  jb      short loc_18001845A
0x180018450  mov     rcx, [rbp+47h+var_80]
0x180018454  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001845a  mov     [rbp+47h+var_68], 7
0x180018462  mov     [rbp+47h+var_70], rsi
0x180018466  mov     word ptr [rbp+47h+var_80], si
0x18001846a  cmp     [rbp+47h+var_88], 8
0x18001846f  jb      short loc_18001847B
0x180018471  mov     rcx, [rbp+47h+strIn]
0x180018475  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001847b  mov     eax, 1
0x180018480  jmp     short loc_1800184E3
0x180018482  lea     rcx, [rbp+47h+strIn]
  ... truncated ...
```

# FilterReplaceChar::ReplaceChars(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e060`
- end: `0x18001e32d`
- name: `?ReplaceChars@FilterReplaceChar@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180018f00`

## callees

- `0x180005ca4`
- `0x18000cde4`
- `0x18000cef4`
- `0x18001b37c`
- `0x18001c62c`
- `0x18001dfbc`
- `0x18001e060`
- `0x18001e334`
- `0x180021850`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e25f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e271`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e294`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e2cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e2df`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e302`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e25f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e271`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e294`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e2cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e2df`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e302`

## string_xrefs

- `0x18001e0d3`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacechar.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FilterReplaceChar::ReplaceChars(FilterReplaceChar *a1, void **a2, void **a3)
{
  void **v4; // rbx
  int Strs; // eax
  unsigned int v7; // edi
  __int64 first_of; // rdi
  _WORD *v9; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  void **v12; // rax
  void **v13; // rdx
  void *v14; // r8
  unsigned __int64 v15; // rcx
  char *v16; // r9
  char *v17; // rax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-69h]
  __int16 v20; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v22; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-41h] BYREF
  void *v24[2]; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int64 v25; // [rsp+60h] [rbp-29h]
  unsigned __int64 v26; // [rsp+68h] [rbp-21h]
  void *Src[2]; // [rsp+70h] [rbp-19h] BYREF
  char *v28; // [rsp+80h] [rbp-9h]
  unsigned __int64 v29; // [rsp+88h] [rbp-1h]
  void *v30[3]; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 v31; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = a2;
  if ( !a2[2] )
    return 2147500037LL;
  v22 = 0;
  v23 = 0;
  v21 = 0;
  Strs = FilterReplaceChar::GetStrs(a1, (const unsigned __int16 **)&v22, (const unsigned __int16 **)&v23, &v21);
  v7 = Strs;
  if ( Strs < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacechar.cpp",
      (const char *)(unsigned int)Strs,
      v19);
    return v7;
  }
  v31 = 7;
  v30[2] = 0;
  LOWORD(v30[0]) = 0;
  std::wstring::assign(v30, (char *)v22, v21);
  first_of = std::wstring::find_first_of(v4, v30, 0);
  if ( first_of == -1 )
    goto LABEL_35;
  v26 = 7;
  v25 = 0;
  LOWORD(v24[0]) = 0;
  std::wstring::assign(v24, (char *)v23, v21);
  v29 = 7;
  v28 = 0;
  LOWORD(Src[0]) = 0;
  std::wstring::assign(Src, v4, 0, 0xFFFFFFFFFFFFFFFFuLL);
  do
  {
    if ( (unsigned __int64)v4[3] < 8 )
      v9 = v4;
    else
      v9 = *v4;
    v20 = v9[first_of];
    v10 = std::wstring::find(v30, &v20);
    v11 = v10;
    if ( v10 != -1 && v10 < v25 )
    {
      v12 = v24;
      if ( v26 >= 8 )
        v12 = (void **)v24[0];
      std::wstring::replace(Src, *((_WORD *)v12 + v11));
    }
    first_of = std::wstring::find_first_of(v4, v30, first_of + 1);
  }
  while ( first_of != -1 );
  v13 = Src;
  v14 = Src[0];
  v15 = v29;
  if ( v29 >= 8 )
    v13 = (void **)Src[0];
  v16 = (char *)v4[2];
  v17 = v16;
  if ( v16 >= v28 )
    v17 = v28;
  if ( (unsigned __int64)v4[3] >= 8 )
    v4 = (void **)*v4;
  if ( v17 )
  {
    while ( *(_WORD *)v4 == *(_WORD *)v13 )
    {
      v4 = (void **)((char *)v4 + 2);
      v13 = (void **)((char *)v13 + 2);
      if ( !--v17 )
        goto LABEL_25;
    }
    v18 = *(_WORD *)v4 < *(_WORD *)v13 ? -1 : 1;
  }
  else
  {
LABEL_25:
    if ( v16 >= v28 )
      v18 = v16 != v28;
    else
      v18 = -1;
  }
  if ( !v18 )
  {
    if ( v29 >= 8 )
      operator delete(Src[0]);
    if ( v26 >= 8 )
      operator delete(v24[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(v24[0]) = 0;
LABEL_35:
    if ( v31 >= 8 )
      operator delete(v30[0]);
    return 1;
  }
  if ( a3 != Src )
  {
    std::wstring::assign(a3, Src, 0, 0xFFFFFFFFFFFFFFFFuLL);
    v15 = v29;
    v14 = Src[0];
  }
  if ( v15 >= 8 )
    operator delete(v14);
  if ( v26 >= 8 )
    operator delete(v24[0]);
  v26 = 7;
  v25 = 0;
  LOWORD(v24[0]) = 0;
  if ( v31 >= 8 )
    operator delete(v30[0]);
  return 0;
}

```

## disassembly

```asm
0x18001e060  mov     [rsp-8+arg_18], rbx
0x18001e065  push    rbp
0x18001e066  push    rsi
0x18001e067  push    rdi
0x18001e068  push    r12
0x18001e06a  push    r15
0x18001e06c  lea     rbp, [rsp-37h]
0x18001e071  sub     rsp, 0C0h
0x18001e078  mov     rax, cs:__security_cookie
0x18001e07f  xor     rax, rsp
0x18001e082  mov     [rbp+57h+var_30], rax
0x18001e086  mov     rsi, r8
0x18001e089  mov     rbx, rdx
0x18001e08c  cmp     qword ptr [rdx+10h], 0
0x18001e091  jnz     short loc_18001E09D
0x18001e093  mov     eax, 80004005h
0x18001e098  jmp     loc_18001E30A
0x18001e09d  mov     [rbp+57h+var_A0], 0
0x18001e0a5  mov     [rbp+57h+var_98], 0
0x18001e0ad  mov     [rbp+57h+var_A8], 0
0x18001e0b5  lea     r9, [rbp+57h+var_A8]; unsigned __int64 *
0x18001e0b9  lea     r8, [rbp+57h+var_98]; unsigned __int16 **
0x18001e0bd  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x18001e0c1  call    ?GetStrs@FilterReplaceChar@@AEAAJPEAPEBG0PEA_K@Z; FilterReplaceChar::GetStrs(ushort const * *,ushort const * *,unsigned __int64 *)
0x18001e0c6  mov     edi, eax
0x18001e0c8  test    eax, eax
0x18001e0ca  jns     short loc_18001E0EB
0x18001e0cc  mov     rcx, [rbp+5Fh]; this
0x18001e0d0  mov     r9d, eax; char *
0x18001e0d3  lea     r8, aMincoreTextinp_23; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001e0da  mov     edx, 101h; void *
0x18001e0df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e0e4  mov     eax, edi
0x18001e0e6  jmp     loc_18001E30A
0x18001e0eb  mov     r12d, 7
0x18001e0f1  mov     [rbp+57h+var_38], r12
0x18001e0f5  mov     [rbp+57h+var_40], 0
0x18001e0fd  xor     eax, eax
0x18001e0ff  mov     word ptr [rbp+57h+var_50], ax
0x18001e103  mov     r8, [rbp+57h+var_A8]
0x18001e107  mov     rdx, [rbp+57h+var_A0]; Src
0x18001e10b  lea     rcx, [rbp+57h+var_50]; void *
0x18001e10f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001e114  nop
0x18001e115  xor     r8d, r8d
0x18001e118  lea     rdx, [rbp+57h+var_50]
0x18001e11c  mov     rcx, rbx
0x18001e11f  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find_first_of(std::wstring const &,unsigned __int64)
0x18001e124  mov     rdi, rax
0x18001e127  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001e12b  cmp     rax, r15
0x18001e12e  jz      loc_18001E289
0x18001e134  mov     [rbp+57h+var_78], r12
0x18001e138  mov     [rbp+57h+var_80], 0
0x18001e140  xor     eax, eax
0x18001e142  mov     word ptr [rbp+57h+var_90], ax
0x18001e146  mov     r8, [rbp+57h+var_A8]
0x18001e14a  mov     rdx, [rbp+57h+var_98]; Src
0x18001e14e  lea     rcx, [rbp+57h+var_90]; void *
0x18001e152  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001e157  nop
0x18001e158  mov     [rbp+57h+var_58], r12
0x18001e15c  mov     [rbp+57h+var_60], 0
0x18001e164  xor     eax, eax
0x18001e166  mov     word ptr [rbp+57h+Src], ax
0x18001e16a  mov     r9, r15
0x18001e16d  xor     r8d, r8d
0x18001e170  mov     rdx, rbx
0x18001e173  lea     rcx, [rbp+57h+Src]; void *
0x18001e177  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001e17c  nop
0x18001e17d  cmp     qword ptr [rbx+18h], 8
0x18001e182  jb      short loc_18001E189
0x18001e184  mov     rax, [rbx]
0x18001e187  jmp     short loc_18001E18C
0x18001e189  mov     rax, rbx
0x18001e18c  movzx   eax, word ptr [rax+rdi*2]
0x18001e190  mov     [rbp+57h+var_B0], ax
0x18001e194  lea     rdx, [rbp+57h+var_B0]
0x18001e198  lea     rcx, [rbp+57h+var_50]
0x18001e19c  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18001e1a1  mov     rcx, rax
0x18001e1a4  cmp     rax, r15
0x18001e1a7  jz      short loc_18001E1D2
0x18001e1a9  cmp     rax, [rbp+57h+var_80]
0x18001e1ad  jnb     short loc_18001E1D2
0x18001e1af  lea     rax, [rbp+57h+var_90]
0x18001e1b3  cmp     [rbp+57h+var_78], 8
0x18001e1b8  cmovnb  rax, [rbp+57h+var_90]
0x18001e1bd  movzx   eax, word ptr [rax+rcx*2]
0x18001e1c1  mov     word ptr [rsp+0E0h+var_C0], ax; __int16
0x18001e1c6  mov     rdx, rdi
0x18001e1c9  lea     rcx, [rbp+57h+Src]; Src
0x18001e1cd  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K00G@Z; std::wstring::replace(unsigned __int64,unsigned __int64,unsigned __int64,ushort)
0x18001e1d2  lea     r8, [rdi+1]
0x18001e1d6  lea     rdx, [rbp+57h+var_50]
0x18001e1da  mov     rcx, rbx
0x18001e1dd  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find_first_of(std::wstring const &,unsigned __int64)
0x18001e1e2  mov     rdi, rax
0x18001e1e5  cmp     rax, r15
0x18001e1e8  jnz     short loc_18001E17D
0x18001e1ea  lea     rdx, [rbp+57h+Src]
0x18001e1ee  mov     r8, [rbp+57h+Src]
0x18001e1f2  mov     rcx, [rbp+57h+var_58]
0x18001e1f6  cmp     rcx, 8
0x18001e1fa  cmovnb  rdx, r8
0x18001e1fe  mov     r10, [rbp+57h+var_60]
0x18001e202  mov     r9, [rbx+10h]
0x18001e206  mov     rax, r9
0x18001e209  cmp     r9, r10
0x18001e20c  cmovnb  rax, r10
0x18001e210  cmp     qword ptr [rbx+18h], 8
0x18001e215  jb      short loc_18001E21A
0x18001e217  mov     rbx, [rbx]
0x18001e21a  test    rax, rax
0x18001e21d  jz      short loc_18001E237
0x18001e21f  movzx   r11d, word ptr [rbx]
0x18001e223  cmp     r11w, [rdx]
0x18001e227  jnz     short loc_18001E241
0x18001e229  add     rbx, 2
0x18001e22d  add     rdx, 2
0x18001e231  sub     rax, 1
0x18001e235  jnz     short loc_18001E21F
0x18001e237  cmp     r9, r10
0x18001e23a  jnb     short loc_18001E24A
0x18001e23c  mov     eax, r15d
0x18001e23f  jmp     short loc_18001E252
0x18001e241  sbb     eax, eax
0x18001e243  and     eax, 0FFFFFFFEh
0x18001e246  inc     eax
0x18001e248  jmp     short loc_18001E252
0x18001e24a  xor     eax, eax
0x18001e24c  cmp     r9, r10
0x18001e24f  setnz   al
0x18001e252  test    eax, eax
0x18001e254  jnz     short loc_18001E2A1
0x18001e256  cmp     rcx, 8
0x18001e25a  jb      short loc_18001E266
0x18001e25c  mov     rcx, r8
0x18001e25f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e265  nop
0x18001e266  cmp     [rbp+57h+var_78], 8
0x18001e26b  jb      short loc_18001E277
0x18001e26d  mov     rcx, [rbp+57h+var_90]
0x18001e271  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e277  mov     [rbp+57h+var_78], r12
0x18001e27b  mov     [rbp+57h+var_80], 0
0x18001e283  xor     ecx, ecx
0x18001e285  mov     word ptr [rbp+57h+var_90], cx
0x18001e289  cmp     [rbp+57h+var_38], 8
0x18001e28e  jb      short loc_18001E29A
0x18001e290  mov     rcx, [rbp+57h+var_50]
0x18001e294  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e29a  mov     eax, 1
0x18001e29f  jmp     short loc_18001E30A
0x18001e2a1  lea     rax, [rbp+57h+Src]
0x18001e2a5  cmp     rsi, rax
0x18001e2a8  jz      short loc_18001E2C4
0x18001e2aa  mov     r9, r15
0x18001e2ad  xor     r8d, r8d
0x18001e2b0  lea     rdx, [rbp+57h+Src]
0x18001e2b4  mov     rcx, rsi; void *
0x18001e2b7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001e2bc  mov     rcx, [rbp+57h+var_58]
0x18001e2c0  mov     r8, [rbp+57h+Src]
0x18001e2c4  cmp     rcx, 8
0x18001e2c8  jb      short loc_18001E2D4
0x18001e2ca  mov     rcx, r8
0x18001e2cd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e2d3  nop
0x18001e2d4  cmp     [rbp+57h+var_78], 8
0x18001e2d9  jb      short loc_18001E2E5
0x18001e2db  mov     rcx, [rbp+57h+var_90]
0x18001e2df  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e2e5  mov     [rbp+57h+var_78], r12
0x18001e2e9  mov     [rbp+57h+var_80], 0
0x18001e2f1  xor     eax, eax
0x18001e2f3  mov     word ptr [rbp+57h+var_90], ax
0x18001e2f7  cmp     [rbp+57h+var_38], 8
0x18001e2fc  jb      short loc_18001E308
0x18001e2fe  mov     rcx, [rbp+57h+var_50]
0x18001e302  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e308  xor     eax, eax
0x18001e30a  mov     rcx, [rbp+57h+var_30]
0x18001e30e  xor     rcx, rsp; StackCookie
0x18001e311  call    __security_check_cookie
0x18001e316  mov     rbx, [rsp+0E0h+arg_18]
0x18001e31e  add     rsp, 0C0h
0x18001e325  pop     r15
0x18001e327  pop     r12
0x18001e329  pop     rdi
0x18001e32a  pop     rsi
0x18001e32b  pop     rbp
0x18001e32c  retn
```

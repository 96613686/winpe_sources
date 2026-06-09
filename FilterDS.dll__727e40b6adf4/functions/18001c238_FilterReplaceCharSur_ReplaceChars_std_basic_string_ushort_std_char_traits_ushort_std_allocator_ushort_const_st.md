# FilterReplaceCharSur::ReplaceChars(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001c238`
- end: `0x18001c626`
- name: `?ReplaceChars@FilterReplaceCharSur@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `1006`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180018f00`

## callees

- `0x180005ca4`
- `0x18000cde4`
- `0x18000cef4`
- `0x18000d3f8`
- `0x18001c14c`
- `0x18001c238`
- `0x18001c62c`
- `0x180021850`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001c54c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c55e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c585`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c5e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c5f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c619`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c54c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c55e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c585`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c5e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c5f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c619`

## string_xrefs

- `0x18001c2ab`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FilterReplaceCharSur::ReplaceChars(FilterReplaceCharSur *a1, _QWORD *a2, void **a3)
{
  _QWORD *v4; // rbx
  int Strs; // eax
  unsigned int v7; // edi
  unsigned __int64 v8; // r14
  void **v9; // r8
  __int64 v10; // rcx
  unsigned __int64 *v11; // rsi
  char *v12; // rax
  char *i; // rdi
  __int64 v14; // rcx
  void **v15; // rax
  char *v16; // rax
  _BYTE *v17; // rax
  __int64 v18; // rdi
  _WORD *v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  void **v22; // r8
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // r9
  char *v25; // rax
  char *j; // rdi
  __int64 v27; // rcx
  void **v28; // rax
  char *v29; // rax
  _BYTE *v30; // rax
  void **v31; // rdx
  void *v32; // r8
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // r10
  unsigned __int64 v35; // rax
  int v36; // eax
  int v37; // [rsp+20h] [rbp-69h]
  __int16 v38; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int64 v39; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v40; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v41; // [rsp+48h] [rbp-41h] BYREF
  void *v42[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v43; // [rsp+60h] [rbp-29h]
  unsigned __int64 v44; // [rsp+68h] [rbp-21h]
  void *v45; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int64 v46; // [rsp+80h] [rbp-9h]
  unsigned __int64 v47; // [rsp+88h] [rbp-1h]
  void *Src[2]; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 v49; // [rsp+A0h] [rbp+17h]
  unsigned __int64 v50; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = a2;
  if ( !a2[2] )
    return 2147500037LL;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  Strs = FilterReplaceCharSur::GetStrs(a1, (const unsigned __int16 **)&v40, (const unsigned __int16 **)&v41, &v39);
  v7 = Strs;
  if ( Strs < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacecharsur.cpp",
      (const char *)(unsigned int)Strs,
      v37);
    return v7;
  }
  v8 = v39;
  v44 = 7;
  v43 = 0;
  LOWORD(v42[0]) = 0;
  std::wstring::assign(v42, (char *)v40, v39);
  v9 = v42;
  if ( v44 >= 8 )
    v9 = (void **)v42[0];
  if ( !v43 )
    goto LABEL_78;
  v10 = v4[2];
  if ( !v10 )
    goto LABEL_78;
  v11 = v4 + 3;
  v12 = v4[3] < 8u ? (char *)v4 : (char *)*v4;
  for ( i = &v12[2 * v10 - 2]; ; i -= 2 )
  {
    v14 = v43;
    v15 = v9;
    while ( *(_WORD *)v15 != *(_WORD *)i )
    {
      v15 = (void **)((char *)v15 + 2);
      if ( !--v14 )
      {
        v15 = 0;
        break;
      }
    }
    if ( v15 )
      break;
    if ( *v11 < 8 )
      v16 = (char *)v4;
    else
      v16 = (char *)*v4;
    if ( i == v16 )
      goto LABEL_78;
  }
  v17 = *v11 < 8 ? v4 : (_BYTE *)*v4;
  v18 = (i - v17) >> 1;
  if ( v18 == -1 )
    goto LABEL_78;
  v47 = 7;
  v46 = 0;
  LOWORD(v45) = 0;
  std::wstring::assign(&v45, (char *)v41, 2 * v8);
  v50 = 7;
  v49 = 0;
  LOWORD(Src[0]) = 0;
  std::wstring::assign(Src, (void **)v4, 0, 0xFFFFFFFFFFFFFFFFuLL);
  do
  {
    if ( *v11 < 8 )
      v19 = v4;
    else
      v19 = (_WORD *)*v4;
    v38 = v19[v18];
    v20 = std::wstring::find(v42, &v38);
    if ( v20 != -1 )
    {
      v21 = 2 * v20;
      if ( v21 < v46 )
        std::wstring::replace(Src, v21, 2);
    }
    if ( !v18 )
      break;
    v22 = v42;
    if ( v44 >= 8 )
      v22 = (void **)v42[0];
    if ( !v43 )
      break;
    v23 = v4[2];
    if ( !v23 )
      break;
    if ( v18 - 1 >= v23 )
      v18 = v4[2];
    v24 = *v11;
    v25 = *v11 < 8 ? (char *)v4 : (char *)*v4;
    for ( j = &v25[2 * v18 - 2]; ; j -= 2 )
    {
      v27 = v43;
      v28 = v22;
      while ( *(_WORD *)v28 != *(_WORD *)j )
      {
        v28 = (void **)((char *)v28 + 2);
        if ( !--v27 )
        {
          v28 = 0;
          break;
        }
      }
      if ( v28 )
        break;
      if ( v24 < 8 )
        v29 = (char *)v4;
      else
        v29 = (char *)*v4;
      if ( j == v29 )
        goto LABEL_59;
    }
    v30 = v24 < 8 ? v4 : (_BYTE *)*v4;
    v18 = (j - v30) >> 1;
  }
  while ( v18 != -1 );
LABEL_59:
  v31 = Src;
  v32 = Src[0];
  v33 = v50;
  if ( v50 >= 8 )
    v31 = (void **)Src[0];
  v34 = v4[2];
  v35 = v34;
  if ( v34 >= v49 )
    v35 = v49;
  if ( *v11 >= 8 )
    v4 = (_QWORD *)*v4;
  if ( v35 )
  {
    while ( *(_WORD *)v4 == *(_WORD *)v31 )
    {
      v4 = (_QWORD *)((char *)v4 + 2);
      v31 = (void **)((char *)v31 + 2);
      if ( !--v35 )
        goto LABEL_68;
    }
    v36 = *(_WORD *)v4 < *(_WORD *)v31 ? -1 : 1;
  }
  else
  {
LABEL_68:
    if ( v34 >= v49 )
      v36 = v34 != v49;
    else
      v36 = -1;
  }
  if ( !v36 )
  {
    if ( v50 >= 8 )
      operator delete(Src[0]);
    if ( v47 >= 8 )
      operator delete(v45);
    v47 = 7;
    v46 = 0;
    LOWORD(v45) = 0;
LABEL_78:
    if ( v44 >= 8 )
      operator delete(v42[0]);
    return 1;
  }
  if ( a3 != Src )
  {
    std::wstring::assign(a3, Src, 0, 0xFFFFFFFFFFFFFFFFuLL);
    v33 = v50;
    v32 = Src[0];
  }
  if ( v33 >= 8 )
    operator delete(v32);
  if ( v47 >= 8 )
    operator delete(v45);
  v47 = 7;
  v46 = 0;
  LOWORD(v45) = 0;
  if ( v44 >= 8 )
    operator delete(v42[0]);
  return 0;
}

```

## disassembly

```asm
0x18001c238  mov     [rsp-8+arg_18], rbx
0x18001c23d  push    rbp
0x18001c23e  push    rsi
0x18001c23f  push    rdi
0x18001c240  push    r14
0x18001c242  push    r15
0x18001c244  lea     rbp, [rsp-37h]
0x18001c249  sub     rsp, 0C0h
0x18001c250  mov     rax, cs:__security_cookie
0x18001c257  xor     rax, rsp
0x18001c25a  mov     [rbp+57h+var_30], rax
0x18001c25e  mov     r15, r8
0x18001c261  mov     rbx, rdx
0x18001c264  cmp     qword ptr [rdx+10h], 0
0x18001c269  jnz     short loc_18001C275
0x18001c26b  mov     eax, 80004005h
0x18001c270  jmp     loc_18001C590
0x18001c275  mov     [rbp+57h+var_A0], 0
0x18001c27d  mov     [rbp+57h+var_98], 0
0x18001c285  mov     [rbp+57h+var_A8], 0
0x18001c28d  lea     r9, [rbp+57h+var_A8]; unsigned __int64 *
0x18001c291  lea     r8, [rbp+57h+var_98]; unsigned __int16 **
0x18001c295  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x18001c299  call    ?GetStrs@FilterReplaceCharSur@@AEAAJPEAPEBG0PEA_K@Z; FilterReplaceCharSur::GetStrs(ushort const * *,ushort const * *,unsigned __int64 *)
0x18001c29e  mov     edi, eax
0x18001c2a0  test    eax, eax
0x18001c2a2  jns     short loc_18001C2C3
0x18001c2a4  mov     rcx, [rbp+5Fh]; this
0x18001c2a8  mov     r9d, eax; char *
0x18001c2ab  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001c2b2  mov     edx, 10Ah; void *
0x18001c2b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2bc  mov     eax, edi
0x18001c2be  jmp     loc_18001C590
0x18001c2c3  mov     r14, [rbp+57h+var_A8]
0x18001c2c7  mov     [rbp+57h+var_78], 7
0x18001c2cf  mov     [rbp+57h+var_80], 0
0x18001c2d7  xor     eax, eax
0x18001c2d9  mov     word ptr [rbp+57h+var_90], ax
0x18001c2dd  mov     r8, r14
0x18001c2e0  mov     rdx, [rbp+57h+var_A0]; Src
0x18001c2e4  lea     rcx, [rbp+57h+var_90]; void *
0x18001c2e8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001c2ed  nop
0x18001c2ee  mov     r9, [rbp+57h+var_80]
0x18001c2f2  lea     r8, [rbp+57h+var_90]
0x18001c2f6  cmp     [rbp+57h+var_78], 8
0x18001c2fb  cmovnb  r8, [rbp+57h+var_90]
0x18001c300  test    r9, r9
0x18001c303  jz      loc_18001C57A
0x18001c309  mov     rcx, [rbx+10h]
0x18001c30d  test    rcx, rcx
0x18001c310  jz      loc_18001C57A
0x18001c316  lea     rsi, [rbx+18h]
0x18001c31a  cmp     qword ptr [rsi], 8
0x18001c31e  jb      short loc_18001C325
0x18001c320  mov     rax, [rbx]
0x18001c323  jmp     short loc_18001C328
0x18001c325  mov     rax, rbx
0x18001c328  lea     rdi, [rcx-1]
0x18001c32c  lea     rdi, [rax+rdi*2]
0x18001c330  mov     rcx, r9
0x18001c333  mov     rax, r8
0x18001c336  movzx   edx, word ptr [rdi]
0x18001c339  cmp     [rax], dx
0x18001c33c  jz      short loc_18001C34A
0x18001c33e  add     rax, 2
0x18001c342  sub     rcx, 1
0x18001c346  jnz     short loc_18001C339
0x18001c348  xor     eax, eax
0x18001c34a  test    rax, rax
0x18001c34d  jnz     short loc_18001C36C
0x18001c34f  cmp     qword ptr [rsi], 8
0x18001c353  jb      short loc_18001C35A
0x18001c355  mov     rax, [rbx]
0x18001c358  jmp     short loc_18001C35D
0x18001c35a  mov     rax, rbx
0x18001c35d  cmp     rdi, rax
0x18001c360  jz      loc_18001C57A
0x18001c366  sub     rdi, 2
0x18001c36a  jmp     short loc_18001C330
0x18001c36c  cmp     qword ptr [rsi], 8
0x18001c370  jb      short loc_18001C377
0x18001c372  mov     rax, [rbx]
0x18001c375  jmp     short loc_18001C37A
0x18001c377  mov     rax, rbx
0x18001c37a  sub     rdi, rax
0x18001c37d  sar     rdi, 1
0x18001c380  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001c384  jz      loc_18001C57A
0x18001c38a  mov     [rbp+57h+var_58], 7
0x18001c392  mov     [rbp+57h+var_60], 0
0x18001c39a  xor     eax, eax
0x18001c39c  mov     word ptr [rbp+57h+var_70], ax
0x18001c3a0  lea     r8, [r14+r14]
0x18001c3a4  mov     rdx, [rbp+57h+var_98]; Src
0x18001c3a8  lea     rcx, [rbp+57h+var_70]; void *
0x18001c3ac  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001c3b1  nop
0x18001c3b2  mov     [rbp+57h+var_38], 7
0x18001c3ba  mov     [rbp+57h+var_40], 0
0x18001c3c2  xor     eax, eax
0x18001c3c4  mov     word ptr [rbp+57h+Src], ax
0x18001c3c8  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001c3cc  xor     r8d, r8d
0x18001c3cf  mov     rdx, rbx
0x18001c3d2  lea     rcx, [rbp+57h+Src]; void *
0x18001c3d6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c3db  nop
0x18001c3dc  cmp     qword ptr [rsi], 8
0x18001c3e0  jb      short loc_18001C3E7
0x18001c3e2  mov     rax, [rbx]
0x18001c3e5  jmp     short loc_18001C3EA
0x18001c3e7  mov     rax, rbx
0x18001c3ea  movzx   eax, word ptr [rax+rdi*2]
0x18001c3ee  mov     [rbp+57h+var_B0], ax
0x18001c3f2  lea     rdx, [rbp+57h+var_B0]
0x18001c3f6  lea     rcx, [rbp+57h+var_90]
0x18001c3fa  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18001c3ff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c403  jz      short loc_18001C432
0x18001c405  add     rax, rax
0x18001c408  cmp     rax, [rbp+57h+var_60]
0x18001c40c  jnb     short loc_18001C432
0x18001c40e  mov     [rsp+0E0h+var_B8], 2; __int64
0x18001c417  mov     [rsp+0E0h+var_C0], rax; __int64
0x18001c41c  lea     r9, [rbp+57h+var_70]
0x18001c420  mov     r8d, 1
0x18001c426  mov     rdx, rdi
0x18001c429  lea     rcx, [rbp+57h+Src]; Src
0x18001c42d  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c432  test    rdi, rdi
0x18001c435  jz      loc_18001C4D8
0x18001c43b  mov     r10, [rbp+57h+var_80]
0x18001c43f  lea     r8, [rbp+57h+var_90]
0x18001c443  cmp     [rbp+57h+var_78], 8
0x18001c448  cmovnb  r8, [rbp+57h+var_90]
0x18001c44d  test    r10, r10
0x18001c450  jz      loc_18001C4D8
0x18001c456  mov     rcx, [rbx+10h]
0x18001c45a  test    rcx, rcx
0x18001c45d  jz      short loc_18001C4D8
0x18001c45f  lea     rax, [rdi-1]
0x18001c463  cmp     rax, rcx
0x18001c466  cmovnb  rdi, rcx
0x18001c46a  mov     r9, [rsi]
0x18001c46d  cmp     r9, 8
0x18001c471  jb      short loc_18001C478
0x18001c473  mov     rax, [rbx]
0x18001c476  jmp     short loc_18001C47B
0x18001c478  mov     rax, rbx
0x18001c47b  dec     rdi
0x18001c47e  lea     rdi, [rax+rdi*2]
0x18001c482  mov     rcx, r10
0x18001c485  mov     rax, r8
0x18001c488  movzx   edx, word ptr [rdi]
0x18001c48b  cmp     [rax], dx
0x18001c48e  jz      short loc_18001C49C
0x18001c490  add     rax, 2
0x18001c494  sub     rcx, 1
0x18001c498  jnz     short loc_18001C48B
0x18001c49a  xor     eax, eax
0x18001c49c  test    rax, rax
0x18001c49f  jnz     short loc_18001C4BA
0x18001c4a1  cmp     r9, 8
0x18001c4a5  jb      short loc_18001C4AC
0x18001c4a7  mov     rax, [rbx]
0x18001c4aa  jmp     short loc_18001C4AF
0x18001c4ac  mov     rax, rbx
0x18001c4af  cmp     rdi, rax
0x18001c4b2  jz      short loc_18001C4D8
0x18001c4b4  sub     rdi, 2
0x18001c4b8  jmp     short loc_18001C482
0x18001c4ba  cmp     r9, 8
0x18001c4be  jb      short loc_18001C4C5
0x18001c4c0  mov     rax, [rbx]
0x18001c4c3  jmp     short loc_18001C4C8
0x18001c4c5  mov     rax, rbx
0x18001c4c8  sub     rdi, rax
0x18001c4cb  sar     rdi, 1
0x18001c4ce  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001c4d2  jnz     loc_18001C3DC
0x18001c4d8  lea     rdx, [rbp+57h+Src]
0x18001c4dc  mov     r8, [rbp+57h+Src]
0x18001c4e0  mov     rcx, [rbp+57h+var_38]
0x18001c4e4  cmp     rcx, 8
0x18001c4e8  cmovnb  rdx, r8
0x18001c4ec  mov     r9, [rbp+57h+var_40]
0x18001c4f0  mov     r10, [rbx+10h]
0x18001c4f4  mov     rax, r10
0x18001c4f7  cmp     r10, r9
0x18001c4fa  cmovnb  rax, r9
0x18001c4fe  cmp     qword ptr [rsi], 8
0x18001c502  jb      short loc_18001C507
0x18001c504  mov     rbx, [rbx]
0x18001c507  test    rax, rax
0x18001c50a  jz      short loc_18001C524
0x18001c50c  movzx   r11d, word ptr [rbx]
0x18001c510  cmp     r11w, [rdx]
0x18001c514  jnz     short loc_18001C52E
0x18001c516  add     rbx, 2
0x18001c51a  add     rdx, 2
0x18001c51e  sub     rax, 1
0x18001c522  jnz     short loc_18001C50C
0x18001c524  cmp     r10, r9
0x18001c527  jnb     short loc_18001C537
0x18001c529  or      eax, 0FFFFFFFFh
0x18001c52c  jmp     short loc_18001C53F
0x18001c52e  sbb     eax, eax
0x18001c530  and     eax, 0FFFFFFFEh
0x18001c533  inc     eax
0x18001c535  jmp     short loc_18001C53F
0x18001c537  xor     eax, eax
0x18001c539  cmp     r10, r9
0x18001c53c  setnz   al
0x18001c53f  test    eax, eax
0x18001c541  jnz     short loc_18001C5B3
0x18001c543  cmp     rcx, 8
0x18001c547  jb      short loc_18001C553
0x18001c549  mov     rcx, r8
0x18001c54c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c552  nop
0x18001c553  cmp     [rbp+57h+var_58], 8
0x18001c558  jb      short loc_18001C564
0x18001c55a  mov     rcx, [rbp+57h+var_70]
0x18001c55e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c564  mov     [rbp+57h+var_58], 7
0x18001c56c  mov     [rbp+57h+var_60], 0
0x18001c574  xor     eax, eax
0x18001c576  mov     word ptr [rbp+57h+var_70], ax
0x18001c57a  cmp     [rbp+57h+var_78], 8
0x18001c57f  jb      short loc_18001C58B
0x18001c581  mov     rcx, [rbp+57h+var_90]
0x18001c585  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c58b  mov     eax, 1
0x18001c590  mov     rcx, [rbp+57h+var_30]
0x18001c594  xor     rcx, rsp; StackCookie
0x18001c597  call    __security_check_cookie
0x18001c59c  mov     rbx, [rsp+0E0h+arg_18]
0x18001c5a4  add     rsp, 0C0h
0x18001c5ab  pop     r15
0x18001c5ad  pop     r14
0x18001c5af  pop     rdi
0x18001c5b0  pop     rsi
0x18001c5b1  pop     rbp
0x18001c5b2  retn
0x18001c5b3  lea     rax, [rbp+57h+Src]
0x18001c5b7  cmp     r15, rax
0x18001c5ba  jz      short loc_18001C5D7
0x18001c5bc  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001c5c0  xor     r8d, r8d
0x18001c5c3  lea     rdx, [rbp+57h+Src]
0x18001c5c7  mov     rcx, r15; void *
0x18001c5ca  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c5cf  mov     rcx, [rbp+57h+var_38]
0x18001c5d3  mov     r8, [rbp+57h+Src]
0x18001c5d7  cmp     rcx, 8
0x18001c5db  jb      short loc_18001C5E7
0x18001c5dd  mov     rcx, r8
0x18001c5e0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c5e6  nop
0x18001c5e7  cmp     [rbp+57h+var_58], 8
0x18001c5ec  jb      short loc_18001C5F8
0x18001c5ee  mov     rcx, [rbp+57h+var_70]
0x18001c5f2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c5f8  mov     [rbp+57h+var_58], 7
0x18001c600  mov     [rbp+57h+var_60], 0
0x18001c608  xor     eax, eax
0x18001c60a  mov     word ptr [rbp+57h+var_70], ax
0x18001c60e  cmp     [rbp+57h+var_78], 8
0x18001c613  jb      short loc_18001C61F
0x18001c615  mov     rcx, [rbp+57h+var_90]
0x18001c619  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c61f  xor     eax, eax
0x18001c621  jmp     loc_18001C590
```

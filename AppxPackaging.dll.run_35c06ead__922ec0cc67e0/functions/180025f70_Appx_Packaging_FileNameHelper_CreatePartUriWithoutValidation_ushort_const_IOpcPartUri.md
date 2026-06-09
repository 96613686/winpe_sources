# Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(ushort const *,IOpcPartUri * *)

- ea: `0x180025f70`
- end: `0x180026578`
- name: `?CreatePartUriWithoutValidation@FileNameHelper@Packaging@Appx@@QEAAJPEBGPEAPEAUIOpcPartUri@@@Z`
- size: `1544`
- prototype: `__int64 __fastcall(Appx::Packaging::FileNameHelper *__hidden this, const unsigned __int16 *, struct IOpcPartUri **)`
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005f60`
- `0x1800254c0`
- `0x180025a0c`
- `0x180025d00`
- `0x1800be16c`
- `0x1800f8af4`

## callees

- `0x1800133fc`
- `0x180025f70`
- `0x180026580`
- `0x18002a224`
- `0x180071f50`
- `0x1800992c4`
- `0x1800992d0`
- `0x180099dd8`
- `0x180099e38`
- `0x18009d3d0`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026484`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026534`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026484`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026534`

## string_xrefs

- `0x18002642c`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18002644d`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800264b7`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800264e5`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18002617b`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180026336`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18002638a`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18002639e`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(
        Appx::Packaging::FileNameHelper *this,
        const unsigned __int16 *a2,
        struct IOpcPartUri **a3)
{
  unsigned int *v4; // rax
  unsigned __int64 v5; // rdx
  unsigned int *v6; // r13
  const unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // ebx
  unsigned __int64 v11; // rbp
  unsigned int v12; // ebx
  __int64 v13; // r15
  unsigned int v14; // esi
  _WORD *v15; // r13
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rdx
  _WORD *v18; // r12
  size_t v19; // r15
  unsigned int v20; // eax
  unsigned int *v21; // rcx
  void **v22; // r8
  unsigned __int64 i; // rdi
  __int64 v24; // rbx
  const unsigned __int16 *const near *v25; // rsi
  int v26; // eax
  unsigned int v27; // esi
  unsigned __int64 v29; // rdx
  void *v30; // rcx
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // eax
  unsigned __int64 v34; // rdx
  unsigned int v35; // ebx
  void *v36; // rcx
  __int64 v37; // r15
  int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r9
  unsigned __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  int *v46; // rax
  int v47; // ebx
  void *v48; // rcx
  int v49; // [rsp+20h] [rbp-68h]
  int v50; // [rsp+20h] [rbp-68h]
  int v51; // [rsp+20h] [rbp-68h]
  char *v52; // [rsp+28h] [rbp-60h]
  void **v53; // [rsp+38h] [rbp-50h] BYREF
  unsigned int *v54; // [rsp+40h] [rbp-48h]
  unsigned int *v55; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int *v59; // [rsp+A8h] [rbp+20h]

  v4 = (unsigned int *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v59 = v4;
  v6 = v4;
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
      (const char *)0x8007000ELL,
      v49);
    Common::AutoPtrDeallocate<Common::StringBuffer>(0);
    return 2147942414LL;
  }
  *((_QWORD *)v4 + 2) = 0;
  *(_OWORD *)v4 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
LABEL_36:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
      (const char *)v10,
      v49);
    v30 = (void *)*((_QWORD *)v6 + 1);
    if ( v30 )
      operator delete(v30, v29);
    operator delete(v6, 0x18u);
    return v10;
  }
  v7 = a2;
  v8 = 0x3FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = -2147024809;
  v10 = -2147024809;
  if ( v8 )
  {
    v10 = 0;
    v11 = 0x3FFFFFFF - v8;
  }
  else
  {
    v11 = 0;
  }
  if ( !v8 )
    goto LABEL_36;
  v12 = v11 + 10;
  if ( v11 + 10 > 0x3FFFFFFF )
    v12 = 0x3FFFFFFF;
  if ( !v12 )
  {
    v48 = (void *)*((_QWORD *)v6 + 1);
    if ( v48 )
    {
      operator delete(v48, v5);
      *((_QWORD *)v6 + 1) = 0;
      *v6 = 0;
    }
    v6[4] = 0;
    goto LABEL_26;
  }
  v13 = v6[4];
  v14 = v12 + 1;
  if ( v12 + 1 != (_DWORD)v13 )
  {
    v15 = (_WORD *)*((_QWORD *)v6 + 1);
    if ( v14 <= (unsigned int)v13 )
    {
      v18 = v15;
LABEL_22:
      v6 = v59;
      v20 = *v59;
      v59[4] = v14;
      *((_QWORD *)v59 + 1) = v18;
      if ( v20 > v12 )
      {
        *v59 = v12;
        v18[v12] = 0;
      }
      else if ( v20 < v12 && !v20 )
      {
        *v18 = 0;
      }
      goto LABEL_26;
    }
    v16 = 2LL * v14;
    if ( !is_mul_ok(v14, 2u) )
      v16 = -1;
    v18 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v18 )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x8007000ELL,
        v49);
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v9,
        v51);
      v6 = v59;
      goto LABEL_26;
    }
    v19 = 2 * v13;
    if ( !v19 )
    {
LABEL_21:
      operator delete(v15, v17);
      goto LABEL_22;
    }
    if ( v15 && 2 * (unsigned __int64)v14 >= v19 )
    {
      memcpy_0(v18, v15, v19);
      goto LABEL_21;
    }
    memset_0(v18, 0, 2LL * v14);
    if ( v15 )
    {
      if ( 2 * (unsigned __int64)v14 >= v19 )
      {
        v47 = 22;
        goto LABEL_64;
      }
      v46 = (int *)_o__errno(v44, v43, v45);
      v47 = 34;
    }
    else
    {
      v46 = (int *)_o__errno(v44, v43, v45);
      v47 = 22;
    }
    *v46 = v47;
    invalid_parameter_noinfo();
LABEL_64:
    operator delete(v18, v43);
    LODWORD(v52) = v47;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      (int)"0x%08lx",
      v52);
    goto LABEL_60;
  }
LABEL_26:
  v21 = v6;
  v55 = v6;
  v22 = &Common::StringBufferBuilder::`vftable';
  v54 = v6;
  v53 = &Common::StringBufferBuilder::`vftable';
  for ( i = 0; ; ++i )
  {
    if ( i >= v11 )
    {
      if ( *v21 == 0x3FFFFFFF )
      {
        v32 = -2147023613;
      }
      else
      {
        v31 = ((__int64 (__fastcall *)(void ***, _QWORD))*v22)(&v53, *v21 + 1);
        v32 = v31;
        if ( v31 >= 0 )
        {
          *(_WORD *)(*((_QWORD *)v54 + 1) + 2LL * (*v54 - 1)) = 0;
          v33 = (*((__int64 (__fastcall **)(_QWORD, struct IOpcPartUri **))this + 1))(*((_QWORD *)v6 + 1), a3);
          v35 = v33;
          if ( v33 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
              (const char *)(unsigned int)v33,
              v49);
            Common::AutoPtrDeallocate<Common::StringBuffer>(v6);
            return v35;
          }
          else
          {
            v36 = (void *)*((_QWORD *)v6 + 1);
            if ( v36 )
              operator delete(v36, v34);
            operator delete(v6, 0x18u);
            return 0;
          }
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)(unsigned int)v31,
          v49);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)v32,
        v49);
      Common::AutoPtrDeallocate<Common::StringBuffer>(v6);
      return v32;
    }
    v24 = *a2;
    if ( (unsigned int)v24 >= 0x5E || (v25 = (&Appx::Packaging::FileNameHelper::SpecialCharsEncoding)[v24]) == 0 )
    {
      if ( *v21 == 0x3FFFFFFF )
      {
        v27 = -2147023613;
      }
      else
      {
        v26 = ((__int64 (__fastcall *)(void ***, _QWORD))*v22)(&v53, *v21 + 1);
        v27 = v26;
        if ( v26 >= 0 )
        {
          *(_WORD *)(*((_QWORD *)v54 + 1) + 2LL * (*v54 - 1)) = v24;
          goto LABEL_33;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)(unsigned int)v26,
          v49);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)v27,
        v49);
      Common::AutoPtrDeallocate<Common::StringBuffer>(v6);
      return v27;
    }
    v37 = *v21;
    if ( (unsigned int)v37 > 0xFFFFFFFC )
    {
      v39 = -2147024362;
      v41 = 263;
      v42 = 2147942934LL;
      goto LABEL_53;
    }
    if ( (unsigned int)(v37 + 3) > 0x3FFFFFFF )
    {
      v39 = -2147023613;
      goto LABEL_54;
    }
    v38 = ((__int64 (__fastcall *)(void ***))*v22)(&v53);
    v39 = v38;
    if ( v38 < 0 )
      break;
    v40 = *((_QWORD *)v54 + 1);
    *(_DWORD *)(v40 + 2 * v37) = *(_DWORD *)v25;
    *(_WORD *)(v40 + 2 * v37 + 4) = *((_WORD *)v25 + 2);
LABEL_33:
    v21 = v54;
    v22 = v53;
    ++a2;
  }
  v42 = (unsigned int)v38;
  v41 = 269;
LABEL_53:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v41,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v42,
    v49);
LABEL_54:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x79,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v39,
    v49);
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xFF,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
    (const char *)v39,
    v50);
  Common::AutoPtrDeallocate<Common::StringBuffer>(v6);
  return v39;
}

```

## disassembly

```asm
0x180025f70  mov     [rsp+arg_10], r8
0x180025f75  mov     [rsp+arg_0], rcx
0x180025f7a  push    rdi
0x180025f7b  push    r13
0x180025f7d  push    r14
0x180025f7f  sub     rsp, 70h
0x180025f83  mov     r14, rdx
0x180025f86  mov     ecx, 18h; unsigned __int64
0x180025f8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025f92  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025f97  mov     [rsp+88h+arg_18], rax
0x180025f9f  mov     r13, rax
0x180025fa2  test    rax, rax
0x180025fa5  jz      loc_180026217
0x180025fab  xor     r8d, r8d
0x180025fae  mov     [rsp+88h+arg_8], rbx
0x180025fb6  mov     [rax+10h], r8
0x180025fba  xorps   xmm0, xmm0
0x180025fbd  mov     [rsp+88h+var_20], rbp
0x180025fc2  mov     [rsp+88h+var_38], r15
0x180025fc7  movups  xmmword ptr [rax], xmm0
0x180025fca  test    r14, r14
0x180025fcd  jz      loc_18002656E
0x180025fd3  mov     r15d, 3FFFFFFFh
0x180025fd9  mov     rax, r14
0x180025fdc  mov     ecx, r15d
0x180025fdf  nop
0x180025fe0  cmp     [rax], r8w
0x180025fe4  jz      short loc_180025FF0
0x180025fe6  add     rax, 2
0x180025fea  sub     rcx, 1
0x180025fee  jnz     short loc_180025FE0
0x180025ff0  mov     edi, 80070057h
0x180025ff5  test    rcx, rcx
0x180025ff8  mov     ebx, edi
0x180025ffa  cmovnz  ebx, r8d
0x180025ffe  jz      loc_1800264D5
0x180026004  mov     rbp, r15
0x180026007  sub     rbp, rcx
0x18002600a  test    rcx, rcx
0x18002600d  jz      loc_1800261C1
0x180026013  lea     rbx, [rbp+0Ah]
0x180026017  mov     [rsp+88h+var_30], r12
0x18002601c  cmp     rbx, r15
0x18002601f  mov     [rsp+88h+var_28], rsi
0x180026024  cmova   rbx, r15
0x180026028  cmp     ebx, r15d
0x18002602b  ja      loc_1800264DD
0x180026031  test    ebx, ebx
0x180026033  jz      loc_180026501
0x180026039  mov     r15d, [r13+10h]
0x18002603d  lea     esi, [rbx+1]
0x180026040  cmp     esi, r15d
0x180026043  jz      loc_1800260E4
0x180026049  mov     r13, [r13+8]
0x18002604d  jbe     loc_18002641C
0x180026053  mov     ecx, esi
0x180026055  mov     eax, 2
0x18002605a  mul     rcx
0x18002605d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180026064  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002606b  cmovb   rax, rcx
0x18002606f  mov     rcx, rax; unsigned __int64
0x180026072  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180026077  mov     r12, rax
0x18002607a  test    rax, rax
0x18002607d  jz      loc_180026424
0x180026083  add     r15, r15
0x180026086  jz      short loc_1800260B2
0x180026088  mov     eax, esi
0x18002608a  add     rax, rax
0x18002608d  mov     [rsp+88h+var_58], rax
0x180026092  test    r13, r13
0x180026095  jz      loc_18002646E
0x18002609b  cmp     rax, r15
0x18002609e  jb      loc_18002646E
0x1800260a4  mov     r8, r15; Size
0x1800260a7  mov     rdx, r13; Src
0x1800260aa  mov     rcx, r12; void *
0x1800260ad  call    memcpy_0
0x1800260b2  mov     rcx, r13; void *
0x1800260b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800260ba  xor     r8d, r8d
0x1800260bd  mov     r13, [rsp+88h+arg_18]
0x1800260c5  mov     eax, [r13+0]
0x1800260c9  mov     [r13+10h], esi
0x1800260cd  mov     [r13+8], r12
0x1800260d1  cmp     eax, ebx
0x1800260d3  ja      loc_18002654A
0x1800260d9  jnb     short loc_1800260E4
0x1800260db  test    eax, eax
0x1800260dd  jnz     short loc_1800260E4
0x1800260df  mov     [r12], r8w
0x1800260e4  mov     r15d, 3FFFFFFFh
0x1800260ea  mov     rcx, r13
0x1800260ed  mov     [rsp+88h+var_40], r13
0x1800260f2  lea     r8, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800260f9  mov     [rsp+88h+var_48], rcx
0x1800260fe  mov     [rsp+88h+var_50], r8
0x180026103  lea     r12, ?SpecialCharsEncoding@FileNameHelper@Packaging@Appx@@0QBQEBGB; ushort const * const near * const Appx::Packaging::FileNameHelper::SpecialCharsEncoding
0x18002610a  xor     edi, edi
0x18002610c  nop     dword ptr [rax+00h]
0x180026110  cmp     rdi, rbp
0x180026113  jnb     loc_18002624C
0x180026119  movzx   ebx, word ptr [r14]
0x18002611d  cmp     ebx, 5Eh ; '^'
0x180026120  jnb     short loc_18002612F
0x180026122  mov     rsi, [r12+rbx*8]
0x180026126  test    rsi, rsi
0x180026129  jnz     loc_1800262D6
0x18002612f  mov     edx, [rcx]
0x180026131  cmp     edx, r15d
0x180026134  jz      loc_18002655A
0x18002613a  mov     rax, [r8]
0x18002613d  lea     rcx, [rsp+88h+var_50]
0x180026142  inc     edx
0x180026144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026149  mov     esi, eax
0x18002614b  test    eax, eax
0x18002614d  js      short loc_180026173
0x18002614f  mov     rdx, [rsp+88h+var_48]
0x180026154  mov     ecx, [rdx]
0x180026156  mov     rax, [rdx+8]
0x18002615a  dec     ecx
0x18002615c  mov     [rax+rcx*2], bx
0x180026160  mov     rcx, [rsp+88h+var_48]
0x180026165  inc     rdi
0x180026168  mov     r8, [rsp+88h+var_50]
0x18002616d  add     r14, 2
0x180026171  jmp     short loc_180026110
0x180026173  mov     rcx, [rsp+88h]; this
0x18002617b  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180026182  mov     r9d, eax; char *
0x180026185  mov     edx, 1Bh; void *
0x18002618a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002618f  mov     rcx, [rsp+88h]; this
0x180026197  lea     r8, aOnecorePrintsc_38; "onecore\\printscan\\appxpackaging\\lib"...
0x18002619e  mov     r9d, esi; char *
0x1800261a1  mov     edx, 0FBh; void *
0x1800261a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800261ab  mov     rcx, r13; void *
0x1800261ae  call    ??$AutoPtrDeallocate@VStringBuffer@Common@@@Common@@YAXPEAVStringBuffer@0@@Z; Common::AutoPtrDeallocate<Common::StringBuffer>(Common::StringBuffer *)
0x1800261b3  mov     eax, esi
0x1800261b5  mov     rsi, [rsp+88h+var_28]
0x1800261ba  mov     r12, [rsp+88h+var_30]
0x1800261bf  jmp     short loc_1800261FA
0x1800261c1  mov     rcx, [rsp+88h]; this
0x1800261c9  lea     r8, aOnecorePrintsc_38; "onecore\\printscan\\appxpackaging\\lib"...
0x1800261d0  mov     r9d, ebx; char *
0x1800261d3  mov     edx, 0E2h; void *
0x1800261d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800261dd  mov     rcx, [r13+8]; void *
0x1800261e1  test    rcx, rcx
0x1800261e4  jz      short loc_1800261EB
0x1800261e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800261eb  mov     edx, 18h; unsigned __int64
0x1800261f0  mov     rcx, r13; void *
0x1800261f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800261f8  mov     eax, ebx
0x1800261fa  mov     rbp, [rsp+88h+var_20]
0x1800261ff  mov     rbx, [rsp+88h+arg_8]
0x180026207  mov     r15, [rsp+88h+var_38]
0x18002620c  add     rsp, 70h
0x180026210  pop     r14
0x180026212  pop     r13
0x180026214  pop     rdi
0x180026215  retn
0x180026217  mov     rcx, [rsp+88h]; this
0x18002621f  lea     r8, aOnecorePrintsc_38; "onecore\\printscan\\appxpackaging\\lib"...
0x180026226  mov     edi, 8007000Eh
0x18002622b  mov     edx, 0DFh; void *
0x180026230  mov     r9d, edi; char *
0x180026233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026238  xor     ecx, ecx; void *
0x18002623a  call    ??$AutoPtrDeallocate@VStringBuffer@Common@@@Common@@YAXPEAVStringBuffer@0@@Z; Common::AutoPtrDeallocate<Common::StringBuffer>(Common::StringBuffer *)
0x18002623f  mov     eax, edi
0x180026241  add     rsp, 70h
0x180026245  pop     r14
0x180026247  pop     r13
0x180026249  pop     rdi
0x18002624a  retn
0x18002624c  mov     edx, [rcx]
0x18002624e  cmp     edx, r15d
0x180026251  jz      loc_180026564
0x180026257  mov     rax, [r8]
0x18002625a  lea     rcx, [rsp+88h+var_50]
0x18002625f  inc     edx
0x180026261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026266  mov     ebx, eax
0x180026268  test    eax, eax
0x18002626a  js      loc_18002632E
0x180026270  mov     rcx, [rsp+88h+var_48]
0x180026275  xor     eax, eax
0x180026277  mov     edx, [rcx]
0x180026279  mov     rcx, [rcx+8]
0x18002627d  dec     edx
0x18002627f  mov     [rcx+rdx*2], ax
0x180026283  mov     rax, [rsp+88h+arg_0]
0x18002628b  mov     rdx, [rsp+88h+arg_10]
0x180026293  mov     rcx, [r13+8]
0x180026297  mov     rax, [rax+8]
0x18002629b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262a0  mov     ebx, eax
0x1800262a2  test    eax, eax
0x1800262a4  js      loc_1800263DD
0x1800262aa  mov     rcx, [r13+8]; void *
0x1800262ae  test    rcx, rcx
0x1800262b1  jz      short loc_1800262B8
0x1800262b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800262b8  mov     edx, 18h; unsigned __int64
0x1800262bd  mov     rcx, r13; void *
0x1800262c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800262c5  mov     rsi, [rsp+88h+var_28]
0x1800262ca  xor     eax, eax
0x1800262cc  mov     r12, [rsp+88h+var_30]
0x1800262d1  jmp     loc_1800261FA
0x1800262d6  mov     r15d, [rcx]
0x1800262d9  cmp     r15d, 0FFFFFFFCh
0x1800262dd  ja      loc_180026375
0x1800262e3  lea     edx, [r15+3]
0x1800262e7  cmp     edx, 3FFFFFFFh
0x1800262ed  ja      loc_180026408
0x1800262f3  mov     rax, [r8]
0x1800262f6  lea     rcx, [rsp+88h+var_50]
0x1800262fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026300  mov     ebx, eax
0x180026302  test    eax, eax
0x180026304  js      loc_18002640F
0x18002630a  mov     rax, [rsp+88h+var_48]
0x18002630f  mov     rcx, [rax+8]
0x180026313  mov     eax, [rsi]
0x180026315  mov     [rcx+r15*2], eax
0x180026319  movzx   eax, word ptr [rsi+4]
0x18002631d  mov     [rcx+r15*2+4], ax
0x180026323  mov     r15d, 3FFFFFFFh
0x180026329  jmp     loc_180026160
0x18002632e  mov     rcx, [rsp+88h]; this
0x180026336  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x18002633d  mov     r9d, eax; char *
0x180026340  mov     edx, 1Bh; void *
0x180026345  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002634a  mov     rcx, [rsp+88h]; this
0x180026352  lea     r8, aOnecorePrintsc_38; "onecore\\printscan\\appxpackaging\\lib"...
0x180026359  mov     r9d, ebx; char *
0x18002635c  mov     edx, 102h; void *
0x180026361  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026366  mov     rcx, r13; void *
0x180026369  call    ??$AutoPtrDeallocate@VStringBuffer@Common@@@Common@@YAXPEAVStringBuffer@0@@Z; Common::AutoPtrDeallocate<Common::StringBuffer>(Common::StringBuffer *)
0x18002636e  mov     eax, ebx
0x180026370  jmp     loc_1800261B5
0x180026375  mov     ebx, 80070216h
0x18002637a  mov     edx, 107h; void *
0x18002637f  mov     r9d, ebx; char *
0x180026382  mov     rcx, [rsp+88h]; this
0x18002638a  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180026391  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026396  mov     rcx, [rsp+88h]; this
0x18002639e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x1800263a5  mov     r9d, ebx; char *
0x1800263a8  mov     edx, 79h ; 'y'; void *
0x1800263ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800263b2  mov     rcx, [rsp+88h]; this
0x1800263ba  lea     r8, aOnecorePrintsc_38; "onecore\\printscan\\appxpackaging\\lib"...
0x1800263c1  mov     r9d, ebx; char *
0x1800263c4  mov     edx, 0FFh; void *
0x1800263c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800263ce  mov     rcx, r13; void *
0x1800263d1  call    ??$AutoPtrDeallocate@VStringBuffer@Common@@@Common@@YAXPEAVStringBuffer@0@@Z; Common::AutoPtrDeallocate<Common::StringBuffer>(Common::StringBuffer *)
0x1800263d6  mov     eax, ebx
0x1800263d8  jmp     loc_1800261B5
0x1800263dd  mov     rcx, [rsp+88h]; this
0x1800263e5  lea     r8, aOnecorePrintsc_38; "onecore\\printscan\\appxpackaging\\lib"...
0x1800263ec  mov     r9d, ebx; char *
0x1800263ef  mov     edx, 104h; void *
0x1800263f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800263f9  mov     rcx, r13; void *
0x1800263fc  call    ??$AutoPtrDeallocate@VStringBuffer@Common@@@Common@@YAXPEAVStringBuffer@0@@Z; Common::AutoPtrDeallocate<Common::StringBuffer>(Common::StringBuffer *)
0x180026401  mov     eax, ebx
0x180026403  jmp     loc_1800261B5
0x180026408  mov     ebx, 80070503h
0x18002640d  jmp     short loc_180026396
0x18002640f  mov     r9d, eax
0x180026412  mov     edx, 10Dh
0x180026417  jmp     loc_180026382
0x18002641c  mov     r12, r13
0x18002641f  jmp     loc_1800260BD
0x180026424  mov     rcx, [rsp+88h]; this
0x18002642c  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180026433  mov     edi, 8007000Eh
0x180026438  mov     edx, 193h; void *
0x18002643d  mov     r9d, edi; char *
0x180026440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026445  mov     rcx, [rsp+88h]; this
0x18002644d  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180026454  mov     r9d, edi; char *
0x180026457  mov     edx, 1C4h; void *
0x18002645c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026461  mov     r13, [rsp+88h+arg_18]
0x180026469  jmp     loc_1800260E4
0x18002646e  mov     r8, rax; Size
  ... truncated ...
```

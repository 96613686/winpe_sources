# BreakFilePathToChunks(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800120b0`
- end: `0x180012632`
- name: `?BreakFilePathToChunks@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@AEAV12@@Z`
- size: `1410`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18001540c`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000bbbc`
- `0x18000dfd8`
- `0x18000e0e4`
- `0x18000e428`
- `0x18000e504`
- `0x18001067c`
- `0x180010718`
- `0x180010730`
- `0x18001163c`
- `0x1800118f4`
- `0x180011d40`
- `0x1800120b0`
- `0x1800543c0`
- `0x180054d1c`

## string_xrefs

- `0x18001214f`: `File path doesn't have backslash: %ws`
- `0x18001215c`: `BreakFilePathToChunks`
- `0x180012184`: `BreakFilePathToChunks`
- `0x1800123f2`: `Empty path chunk`
- `0x18001229f`: `Path chunk: %ws`
- `0x1800125a9`: `No path chunks`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall BreakFilePathToChunks(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v6; // rax
  unsigned __int64 v7; // r13
  unsigned __int64 v8; // r8
  _QWORD *v9; // rdx
  unsigned __int64 v10; // r12
  const wchar_t *v11; // rcx
  size_t v12; // r8
  unsigned __int64 v13; // r12
  const wchar_t *v14; // rcx
  size_t v15; // r8
  wchar_t **v16; // rax
  unsigned __int64 v17; // r13
  unsigned __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r8
  _QWORD *v21; // rax
  __int64 v22; // r10
  unsigned __int64 v23; // r13
  unsigned int v24; // ecx
  __int64 v25; // r12
  __int64 v26; // r15
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  _QWORD *v30; // r9
  __int64 v31; // r10
  __int128 *p_Src; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v38; // [rsp+28h] [rbp-99h]
  __int64 v39; // [rsp+28h] [rbp-99h]
  _QWORD *v40; // [rsp+30h] [rbp-91h]
  __int64 v41; // [rsp+38h] [rbp-89h]
  char v42; // [rsp+48h] [rbp-79h]
  unsigned int v43; // [rsp+4Ch] [rbp-75h]
  __int128 v44; // [rsp+50h] [rbp-71h] BYREF
  __int64 v45; // [rsp+60h] [rbp-61h]
  __int64 v46; // [rsp+68h] [rbp-59h]
  _QWORD *v47; // [rsp+70h] [rbp-51h]
  wchar_t *S1[2]; // [rsp+78h] [rbp-49h] BYREF
  unsigned __int64 v49; // [rsp+88h] [rbp-39h]
  unsigned __int64 v50; // [rsp+90h] [rbp-31h]
  __int128 Src; // [rsp+98h] [rbp-29h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-19h]
  unsigned __int64 v53; // [rsp+B0h] [rbp-11h]
  __int128 v54; // [rsp+B8h] [rbp-9h] BYREF
  __int128 v55; // [rsp+C8h] [rbp+7h]

  v46 = -2;
  v47 = a1;
  v42 = 0;
  *(_OWORD *)S1 = 0;
  v49 = 0;
  v50 = 7;
  LOWORD(S1[0]) = 0;
  Src = 0;
  v52 = 0;
  v53 = 7;
  LOWORD(Src) = 0;
  v44 = 0;
  v45 = 0;
  if ( std::wstring::find(a1, L"\\") == -1 )
  {
    if ( a1[3] <= 7u )
      v6 = a1;
    else
      v6 = (_QWORD *)*a1;
    AslLogCallPrintf(1, "BreakFilePathToChunks", 1716, "File path doesn't have backslash: %ws", v6);
    goto LABEL_80;
  }
  v7 = std::wstring::find(a1, L"\\");
  if ( v7 == -1 )
  {
LABEL_36:
    if ( !a1[2] )
    {
      AslLogCallPrintf(1, "BreakFilePathToChunks", 1753, "File name not found.", v38);
      goto LABEL_80;
    }
    std::wstring::operator=(a3, a1);
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    AslLogCallPrintf(3, "BreakFilePathToChunks", 1749, "File name: %ws", a3);
    v22 = v44;
    v23 = (__int64)(*((_QWORD *)&v44 + 1) - v44) >> 5;
    v24 = 0;
    v43 = 0;
    if ( !v23 )
    {
LABEL_76:
      if ( (__int64)(a2[1] - *a2) >> 5 )
        v42 = 1;
      else
        AslLogCallPrintf(1, "BreakFilePathToChunks", 1798, "No path chunks", v39);
      goto LABEL_80;
    }
    while ( 1 )
    {
      v25 = v24;
      v26 = 32LL * v24;
      v27 = v26 + v22;
      if ( *(_QWORD *)(v26 + v22 + 24) > 7u )
        v27 = *(_QWORD *)(v26 + v22);
      if ( (unsigned int)AslStringHasWildcard(v27) )
        break;
      if ( v52 )
      {
        v36 = v30[2];
        if ( 0x7FFFFFFFFFFFFFFELL == v36 )
          std::_Xlen_string();
        if ( v30[3] > 7u )
          v30 = (_QWORD *)*v30;
        v41 = v36;
        v40 = v30;
        v39 = 1;
        std::wstring::wstring(&v54, v28, v29, L"\\");
        std::wstring::append(&Src);
        std::wstring::~wstring(&v54);
      }
      else
      {
        std::wstring::operator=(&Src, v30);
      }
      if ( v23 - 1 == v25 )
      {
        if ( a2[1] == a2[2] )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a2, a2[1], &Src);
        }
        else
        {
          std::wstring::wstring(a2[1], &Src);
          a2[1] += 32LL;
        }
        v34 = (_QWORD *)(a2[1] - 32LL);
        if ( v34[3] > 7u )
          v34 = (_QWORD *)*v34;
        v35 = 1791;
        goto LABEL_73;
      }
LABEL_74:
      v24 = v43 + 1;
      v43 = v24;
      if ( v24 >= v23 )
        goto LABEL_76;
      v22 = v44;
    }
    if ( v52 )
    {
      if ( a2[1] == a2[2] )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a2, a2[1], &Src);
      }
      else
      {
        std::wstring::wstring(a2[1], &Src);
        a2[1] += 32LL;
      }
      v52 = 0;
      p_Src = &Src;
      if ( v53 > 7 )
        p_Src = (__int128 *)Src;
      *(_WORD *)p_Src = 0;
      v33 = (_QWORD *)(a2[1] - 32LL);
      if ( v33[3] > 7u )
        v33 = (_QWORD *)*v33;
      AslLogCallPrintf(3, "BreakFilePathToChunks", 1771, "Merged key chunk: %ws", v33, v40, v41);
      v31 = v44;
    }
    if ( a2[1] == a2[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a2, a2[1], v26 + v31);
    }
    else
    {
      std::wstring::wstring(a2[1], v26 + v31);
      a2[1] += 32LL;
    }
    v34 = (_QWORD *)(a2[1] - 32LL);
    if ( v34[3] > 7u )
      v34 = (_QWORD *)*v34;
    v35 = 1775;
LABEL_73:
    AslLogCallPrintf(3, "BreakFilePathToChunks", v35, "Merged key chunk: %ws", v34);
    goto LABEL_74;
  }
  while ( 1 )
  {
    v54 = 0;
    v55 = 0;
    v8 = a1[2];
    if ( v8 >= v7 )
      v8 = v7;
    v9 = a1[3] <= 7u ? a1 : (_QWORD *)*a1;
    std::wstring::_Construct<1,unsigned short const *>(&v54, v9, v8);
    std::wstring::operator=(S1, &v54);
    std::wstring::~wstring(&v54);
    v10 = v49;
    if ( !v49 )
      break;
    v11 = (const wchar_t *)S1;
    if ( v50 > 7 )
      v11 = S1[0];
    v12 = v49;
    if ( v49 > 1 )
      v12 = 1;
    if ( !wmemcmp(v11, L".", v12) && v10 == 1 )
      goto LABEL_46;
    v13 = v49;
    v14 = (const wchar_t *)S1;
    if ( v50 > 7 )
      v14 = S1[0];
    v15 = v49;
    if ( v49 > 2 )
      v15 = 2;
    if ( !wmemcmp(v14, L"..", v15) && v13 == 2 )
    {
LABEL_46:
      AslLogCallPrintf(1, "BreakFilePathToChunks", 1732, "File subfolder contains . or ..", v38);
      goto LABEL_80;
    }
    if ( *((_QWORD *)&v44 + 1) == v45 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v44, *((_QWORD *)&v44 + 1), S1);
    }
    else
    {
      std::wstring::wstring(*((_QWORD *)&v44 + 1), S1);
      *((_QWORD *)&v44 + 1) += 32LL;
    }
    v16 = S1;
    if ( v50 > 7 )
      v16 = (wchar_t **)S1[0];
    AslLogCallPrintf(3, "BreakFilePathToChunks", 1737, "Path chunk: %ws", v16);
    v17 = v7 + 1;
    v54 = 0;
    v55 = 0;
    v18 = a1[2];
    if ( v18 < v17 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    v19 = v18 - v17;
    v20 = -1;
    if ( v19 != -1 )
      v20 = v19;
    v21 = a1;
    if ( a1[3] > 7u )
      v21 = (_QWORD *)*a1;
    std::wstring::_Construct<1,unsigned short const *>(&v54, (char *)v21 + 2 * v17, v20);
    std::wstring::operator=(a1, &v54);
    std::wstring::~wstring(&v54);
    v7 = std::wstring::find(a1, L"\\");
    if ( v7 == -1 )
      goto LABEL_36;
  }
  AslLogCallPrintf(1, "BreakFilePathToChunks", 1726, "Empty path chunk", v38);
LABEL_80:
  std::vector<std::wstring>::_Tidy(&v44);
  std::wstring::~wstring(&Src);
  std::wstring::~wstring(S1);
  std::wstring::~wstring(a1);
  return v42;
}

```

## disassembly

```asm
0x1800120b0  mov     rax, rsp
0x1800120b3  push    rbp
0x1800120b4  push    rsi
0x1800120b5  push    rdi
0x1800120b6  push    r12
0x1800120b8  push    r13
0x1800120ba  push    r14
0x1800120bc  push    r15
0x1800120be  lea     rbp, [rax-5Fh]
0x1800120c2  sub     rsp, 0E0h
0x1800120c9  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x1800120d1  mov     [rax+20h], rbx
0x1800120d5  mov     rax, cs:__security_cookie
0x1800120dc  xor     rax, rsp
0x1800120df  mov     [rbp+57h+var_40], rax
0x1800120e3  mov     r15, r8
0x1800120e6  mov     rbx, rdx
0x1800120e9  mov     rdi, rcx
0x1800120ec  mov     [rbp+57h+var_A8], rcx
0x1800120f0  xor     r12d, r12d
0x1800120f3  mov     [rbp+57h+var_D0], r12b
0x1800120f7  xorps   xmm0, xmm0
0x1800120fa  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1800120fe  mov     [rbp+57h+var_90], r12
0x180012102  lea     esi, [r12+7]
0x180012107  mov     [rbp+57h+var_88], rsi
0x18001210b  mov     word ptr [rbp+57h+S1], r12w
0x180012110  movups  [rbp+57h+Src], xmm0
0x180012114  mov     [rbp+57h+var_70], r12
0x180012118  mov     [rbp+57h+var_68], rsi
0x18001211c  mov     word ptr [rbp+57h+Src], r12w
0x180012121  movdqu  [rbp+57h+var_C8], xmm0
0x180012126  mov     [rbp+57h+var_B8], r12
0x18001212a  lea     rdx, asc_18006E074; "\\"
0x180012131  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180012136  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001213a  jnz     short loc_180012172
0x18001213c  cmp     [rdi+18h], rsi
0x180012140  jbe     short loc_180012147
0x180012142  mov     rax, [rdi]
0x180012145  jmp     short loc_18001214A
0x180012147  mov     rax, rdi
0x18001214a  mov     [rsp+110h+var_F0], rax
0x18001214f  lea     r9, aFilePathDoesnT; "File path doesn't have backslash: %ws"
0x180012156  mov     r8d, 6B4h
0x18001215c  lea     rdx, aBreakfilepatht; "BreakFilePathToChunks"
0x180012163  mov     ecx, 1
0x180012168  call    AslLogCallPrintf
0x18001216d  jmp     loc_1800125D6
0x180012172  lea     rdx, asc_18006E074; "\\"
0x180012179  mov     rcx, rdi
0x18001217c  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180012181  mov     r13, rax
0x180012184  lea     r14, aBreakfilepatht; "BreakFilePathToChunks"
0x18001218b  mov     esi, 1
0x180012190  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012194  jz      loc_180012334
0x18001219a  xorps   xmm0, xmm0
0x18001219d  movups  [rbp+57h+var_60], xmm0
0x1800121a1  xorps   xmm1, xmm1
0x1800121a4  movdqu  [rbp+57h+var_50], xmm1
0x1800121a9  mov     r8, [rdi+10h]
0x1800121ad  cmp     r8, r13
0x1800121b0  cmovnb  r8, r13
0x1800121b4  cmp     qword ptr [rdi+18h], 7
0x1800121b9  jbe     short loc_1800121C0
0x1800121bb  mov     rdx, [rdi]
0x1800121be  jmp     short loc_1800121C3
0x1800121c0  mov     rdx, rdi
0x1800121c3  lea     rcx, [rbp+57h+var_60]
0x1800121c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800121cc  lea     rdx, [rbp+57h+var_60]
0x1800121d0  lea     rcx, [rbp+57h+S1]
0x1800121d4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800121d9  lea     rcx, [rbp+57h+var_60]; void *
0x1800121dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800121e2  mov     r12, [rbp+57h+var_90]
0x1800121e6  test    r12, r12
0x1800121e9  jz      loc_1800123F2
0x1800121ef  lea     rcx, [rbp+57h+S1]
0x1800121f3  cmp     [rbp+57h+var_88], 7
0x1800121f8  cmova   rcx, [rbp+57h+S1]; S1
0x1800121fd  mov     r8, r12
0x180012200  cmp     r12, rsi
0x180012203  cmova   r8, rsi; N
0x180012207  lea     rdx, asc_180070E44; "."
0x18001220e  call    wmemcmp
0x180012213  test    eax, eax
0x180012215  jnz     short loc_180012220
0x180012217  cmp     r12, rsi
0x18001221a  jz      loc_1800123E0
0x180012220  mov     r12, [rbp+57h+var_90]
0x180012224  lea     rcx, [rbp+57h+S1]
0x180012228  cmp     [rbp+57h+var_88], 7
0x18001222d  cmova   rcx, [rbp+57h+S1]; S1
0x180012232  mov     r8, r12
0x180012235  mov     eax, 2
0x18001223a  cmp     r12, rax
0x18001223d  cmova   r8, rax; N
0x180012241  lea     rdx, asc_180070350; ".."
0x180012248  call    wmemcmp
0x18001224d  test    eax, eax
0x18001224f  jnz     short loc_18001225F
0x180012251  mov     eax, 2
0x180012256  cmp     r12, rax
0x180012259  jz      loc_1800123E0
0x18001225f  mov     rax, qword ptr [rbp+57h+var_C8+8]
0x180012263  cmp     rax, [rbp+57h+var_B8]
0x180012267  jz      short loc_18001227C
0x180012269  lea     rdx, [rbp+57h+S1]
0x18001226d  mov     rcx, rax
0x180012270  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180012275  add     qword ptr [rbp+57h+var_C8+8], 20h ; ' '
0x18001227a  jmp     short loc_18001228C
0x18001227c  lea     r8, [rbp+57h+S1]
0x180012280  mov     rdx, rax
0x180012283  lea     rcx, [rbp+57h+var_C8]
0x180012287  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18001228c  lea     rax, [rbp+57h+S1]
0x180012290  cmp     [rbp+57h+var_88], 7
0x180012295  cmova   rax, [rbp+57h+S1]
0x18001229a  mov     [rsp+110h+var_F0], rax
0x18001229f  lea     r9, aPathChunkWs; "Path chunk: %ws"
0x1800122a6  mov     r8d, 6C9h
0x1800122ac  mov     rdx, r14
0x1800122af  mov     ecx, 3
0x1800122b4  call    AslLogCallPrintf
0x1800122b9  inc     r13
0x1800122bc  xorps   xmm0, xmm0
0x1800122bf  movups  [rbp+57h+var_60], xmm0
0x1800122c3  xorps   xmm1, xmm1
0x1800122c6  movdqu  [rbp+57h+var_50], xmm1
0x1800122cb  mov     rax, [rdi+10h]
0x1800122cf  cmp     rax, r13
0x1800122d2  jb      loc_18001262C
0x1800122d8  sub     rax, r13
0x1800122db  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800122df  cmp     rax, r8
0x1800122e2  cmovb   r8, rax
0x1800122e6  mov     rax, rdi
0x1800122e9  cmp     qword ptr [rdi+18h], 7
0x1800122ee  jbe     short loc_1800122F3
0x1800122f0  mov     rax, [rdi]
0x1800122f3  lea     rdx, [rax+r13*2]
0x1800122f7  lea     rcx, [rbp+57h+var_60]
0x1800122fb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180012300  lea     rdx, [rbp+57h+var_60]
0x180012304  mov     rcx, rdi
0x180012307  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001230c  lea     rcx, [rbp+57h+var_60]; void *
0x180012310  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012315  lea     rdx, asc_18006E074; "\\"
0x18001231c  mov     rcx, rdi
0x18001231f  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180012324  mov     r13, rax
0x180012327  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001232b  jnz     loc_18001219A
0x180012331  xor     r12d, r12d
0x180012334  cmp     [rdi+10h], r12
0x180012338  jz      loc_1800125BE
0x18001233e  mov     rdx, rdi
0x180012341  mov     rcx, r15
0x180012344  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180012349  cmp     qword ptr [r15+18h], 7
0x18001234e  jbe     short loc_180012353
0x180012350  mov     r15, [r15]
0x180012353  mov     [rsp+110h+var_F0], r15
0x180012358  lea     r9, aFileNameWs; "File name: %ws"
0x18001235f  mov     r8d, 6D5h
0x180012365  mov     rdx, r14
0x180012368  mov     ecx, 3
0x18001236d  call    AslLogCallPrintf
0x180012372  mov     r13, qword ptr [rbp+57h+var_C8+8]
0x180012376  mov     r10, qword ptr [rbp+57h+var_C8]
0x18001237a  sub     r13, r10
0x18001237d  sar     r13, 5
0x180012381  mov     ecx, r12d
0x180012384  mov     [rbp+57h+var_CC], ecx
0x180012387  test    r13, r13
0x18001238a  jz      loc_180012599
0x180012390  mov     r12d, ecx
0x180012393  mov     r15d, ecx
0x180012396  shl     r15, 5
0x18001239a  lea     r9, [r15+r10]
0x18001239e  mov     rcx, r9
0x1800123a1  cmp     qword ptr [r9+18h], 7
0x1800123a6  jbe     short loc_1800123AB
0x1800123a8  mov     rcx, [r9]
0x1800123ab  call    AslStringHasWildcard
0x1800123b0  test    eax, eax
0x1800123b2  jz      loc_1800124AB
0x1800123b8  cmp     [rbp+57h+var_70], 0
0x1800123bd  jz      loc_180012463
0x1800123c3  mov     rax, [rbx+8]
0x1800123c7  cmp     rax, [rbx+10h]
0x1800123cb  jz      short loc_180012404
0x1800123cd  lea     rdx, [rbp+57h+Src]
0x1800123d1  mov     rcx, rax
0x1800123d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800123d9  add     qword ptr [rbx+8], 20h ; ' '
0x1800123de  jmp     short loc_180012413
0x1800123e0  lea     r9, aFileSubfolderC; "File subfolder contains . or .."
0x1800123e7  mov     r8d, 6C4h
0x1800123ed  jmp     loc_1800125CB
0x1800123f2  lea     r9, aEmptyPathChunk; "Empty path chunk"
0x1800123f9  mov     r8d, 6BEh
0x1800123ff  jmp     loc_1800125CB
0x180012404  lea     r8, [rbp+57h+Src]
0x180012408  mov     rdx, rax
0x18001240b  mov     rcx, rbx
0x18001240e  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180012413  mov     [rbp+57h+var_70], 0
0x18001241b  lea     rcx, [rbp+57h+Src]
0x18001241f  cmp     [rbp+57h+var_68], 7
0x180012424  cmova   rcx, qword ptr [rbp+57h+Src]
0x180012429  xor     eax, eax
0x18001242b  mov     [rcx], ax
0x18001242e  mov     rax, [rbx+8]
0x180012432  add     rax, 0FFFFFFFFFFFFFFE0h
0x180012436  cmp     qword ptr [rax+18h], 7
0x18001243b  jbe     short loc_180012440
0x18001243d  mov     rax, [rax]
0x180012440  mov     [rsp+110h+var_F0], rax
0x180012445  lea     r9, aMergedKeyChunk; "Merged key chunk: %ws"
0x18001244c  mov     r8d, 6EBh
0x180012452  mov     rdx, r14
0x180012455  mov     ecx, 3
0x18001245a  call    AslLogCallPrintf
0x18001245f  mov     r10, qword ptr [rbp+57h+var_C8]
0x180012463  lea     r8, [r15+r10]
0x180012467  mov     rax, [rbx+8]
0x18001246b  cmp     rax, [rbx+10h]
0x18001246f  jz      short loc_180012483
0x180012471  mov     rdx, r8
0x180012474  mov     rcx, rax
0x180012477  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001247c  add     qword ptr [rbx+8], 20h ; ' '
0x180012481  jmp     short loc_18001248E
0x180012483  mov     rdx, rax
0x180012486  mov     rcx, rbx
0x180012489  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18001248e  mov     rax, [rbx+8]
0x180012492  add     rax, 0FFFFFFFFFFFFFFE0h
0x180012496  cmp     qword ptr [rax+18h], 7
0x18001249b  jbe     short loc_1800124A0
0x18001249d  mov     rax, [rax]
0x1800124a0  mov     r8d, 6EFh
0x1800124a6  jmp     loc_180012568
0x1800124ab  cmp     [rbp+57h+var_70], 0
0x1800124b0  jnz     short loc_1800124C0
0x1800124b2  mov     rdx, r9
0x1800124b5  lea     rcx, [rbp+57h+Src]
0x1800124b9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800124be  jmp     short loc_18001251B
0x1800124c0  mov     rcx, [r9+10h]
0x1800124c4  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800124ce  sub     rax, rcx
0x1800124d1  cmp     rax, rsi
0x1800124d4  jb      loc_180012626
0x1800124da  cmp     qword ptr [r9+18h], 7
0x1800124df  jbe     short loc_1800124E4
0x1800124e1  mov     r9, [r9]
0x1800124e4  mov     [rsp+30h], rcx
0x1800124e9  mov     [rsp+110h+var_E8], r9
0x1800124ee  mov     [rsp+110h+var_F0], rsi
0x1800124f3  lea     r9, asc_18006E074; "\\"
0x1800124fa  lea     rcx, [rbp+57h+var_60]
0x1800124fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180012503  nop
0x180012504  lea     rdx, [rbp+57h+var_60]
0x180012508  lea     rcx, [rbp+57h+Src]; Src
0x18001250c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180012511  nop
0x180012512  lea     rcx, [rbp+57h+var_60]; void *
0x180012516  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001251b  lea     rax, [r13-1]
0x18001251f  cmp     rax, r12
0x180012522  jnz     short loc_180012581
0x180012524  mov     rax, [rbx+8]
0x180012528  cmp     rax, [rbx+10h]
0x18001252c  jz      short loc_180012541
0x18001252e  lea     rdx, [rbp+57h+Src]
0x180012532  mov     rcx, rax
0x180012535  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001253a  add     qword ptr [rbx+8], 20h ; ' '
0x18001253f  jmp     short loc_180012550
0x180012541  lea     r8, [rbp+57h+Src]
0x180012545  mov     rdx, rax
0x180012548  mov     rcx, rbx
0x18001254b  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180012550  mov     rax, [rbx+8]
0x180012554  add     rax, 0FFFFFFFFFFFFFFE0h
0x180012558  cmp     qword ptr [rax+18h], 7
0x18001255d  jbe     short loc_180012562
0x18001255f  mov     rax, [rax]
0x180012562  mov     r8d, 6FFh
0x180012568  mov     [rsp+110h+var_F0], rax
0x18001256d  lea     r9, aMergedKeyChunk; "Merged key chunk: %ws"
0x180012574  mov     rdx, r14
0x180012577  mov     ecx, 3
  ... truncated ...
```

# Csl::EnumerateDirectoryInternal(Csl::FindFirstFileInformation const &,Csl::Path const &,Csl::EnumerateDirectoryOption,ushort const *,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &)

- ea: `0x18000bd28`
- end: `0x18000c1f7`
- name: `?EnumerateDirectoryInternal@Csl@@YAJAEBUFindFirstFileInformation@1@AEBVPath@1@W4EnumerateDirectoryOption@1@PEBGAEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@@Z`
- size: `1231`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18000c200`

## callees

- `0x180002534`
- `0x180003ce4`
- `0x1800045e4`
- `0x18000adb8`
- `0x18000af30`
- `0x18000b9b8`
- `0x18000bb98`
- `0x18000bd28`
- `0x18000c200`
- `0x18000d048`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000c070`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000c070`

## pseudocode

```c
__int64 __fastcall Csl::EnumerateDirectoryInternal(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 *a5)
{
  __int64 *v5; // rbx
  struct _WIN32_FIND_DATAW *v6; // r15
  _WORD *v7; // r14
  __m128i si128; // xmm6
  __int64 v10; // rdi
  __int64 v12; // r8
  const void *v13; // rdx
  __int64 v14; // rax
  const void *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 *v20; // r9
  _QWORD *v21; // rdi
  _QWORD *v22; // rbx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rax
  const char *v27; // r9
  bool v28; // zf
  __int64 v29; // rdx
  __int64 v30; // rax
  _WORD *v31; // rcx
  _WORD *v32; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  int v36; // [rsp+28h] [rbp-B1h]
  void *v37[2]; // [rsp+38h] [rbp-A1h] BYREF
  _WORD v38[8]; // [rsp+48h] [rbp-91h] BYREF
  void *v39[2]; // [rsp+58h] [rbp-81h] BYREF
  _WORD v40[8]; // [rsp+68h] [rbp-71h] BYREF
  void *v41[2]; // [rsp+78h] [rbp-61h] BYREF
  _WORD v42[8]; // [rsp+88h] [rbp-51h] BYREF
  __m128i v43; // [rsp+98h] [rbp-41h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-31h]
  _QWORD v45[2]; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD v46[2]; // [rsp+C0h] [rbp-19h] BYREF
  _QWORD v47[5]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+57h]
  __int64 v49; // [rsp+140h] [rbp+67h]

  v49 = a2;
  v5 = a5;
  v6 = (struct _WIN32_FIND_DATAW *)(a1 + 8);
  v7 = (_WORD *)(a1 + 52);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v10 = a4;
  while ( 1 )
  {
    if ( *v7 == 46 && (!v6->cFileName[1] || v6->cFileName[1] == 46 && !v6->cFileName[2]) )
      goto LABEL_48;
    if ( (a3 & 4) != 0 )
      break;
LABEL_34:
    if ( (v6->dwFileAttributes & 0x10) != 0 )
    {
      v28 = (a3 & 2) == 0;
      goto LABEL_37;
    }
LABEL_36:
    v28 = (a3 & 8) == 0;
LABEL_37:
    if ( !v28 )
    {
      v40[0] = 0;
      v39[0] = v40;
      v39[1] = v40;
      if ( (a3 & 1) != 0 )
      {
        if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                (__int64)v39,
                *(const void **)(a1 + 600),
                (__int64)(*(_QWORD *)(a1 + 608) - *(_QWORD *)(a1 + 600)) >> 1) )
        {
          v29 = 881;
LABEL_68:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
            (const char *)0x8007000ELL,
            v36);
          v31 = v39[0];
          v32 = v40;
          goto LABEL_69;
        }
      }
      else if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                   (__int64)v39,
                   *(const void **)a2,
                   (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) )
      {
        v29 = 885;
        goto LABEL_68;
      }
      v47[0] = v7;
      v30 = -1;
      do
        ++v30;
      while ( v7[v30] );
      v47[1] = v30;
      if ( !Csl::Path::Append((Csl::Path *)v39, (__int64)v47) )
      {
        v29 = 888;
        goto LABEL_68;
      }
      if ( !utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(v5, v39) )
      {
        v29 = 890;
        goto LABEL_68;
      }
      if ( v39[0] != v40 )
        operator delete(v39[0], (const struct std::nothrow_t *)&std::nothrow);
    }
LABEL_48:
    if ( !FindNextFileW(*(HANDLE *)a1, v6) )
      return 0;
    a2 = v49;
  }
  if ( (v6->dwFileAttributes & 0x10) == 0 )
    goto LABEL_36;
  v12 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2;
  v13 = *(const void **)a2;
  v37[0] = v38;
  v37[1] = v38;
  v38[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v37,
          v13,
          v12 >> 1) )
  {
    v35 = 840;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      v36);
    goto LABEL_53;
  }
  v45[0] = v7;
  v14 = -1;
  do
    ++v14;
  while ( v7[v14] );
  v45[1] = v14;
  if ( !Csl::Path::Append((Csl::Path *)v37, (__int64)v45) )
  {
    v35 = 841;
    goto LABEL_63;
  }
  v15 = *(const void **)(a1 + 600);
  v16 = *(_QWORD *)(a1 + 608);
  v41[0] = v42;
  v41[1] = v42;
  v42[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v41,
          v15,
          (v16 - (__int64)v15) >> 1) )
  {
    v34 = 845;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      v36);
    goto LABEL_51;
  }
  v46[0] = v7;
  v17 = -1;
  do
    ++v17;
  while ( v7[v17] );
  v46[1] = v17;
  if ( !Csl::Path::Append((Csl::Path *)v41, (__int64)v46) )
  {
    v34 = 846;
    goto LABEL_60;
  }
  v44 = -1;
  v43 = si128;
  v18 = Csl::EnumerateDirectoryInternal((unsigned int)v41, (unsigned int)v37, a3, (unsigned int)&v43, v10);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v20 = a5;
    v21 = (_QWORD *)v43.m128i_i64[1];
    v22 = (_QWORD *)v43.m128i_i64[0];
    v23 = ((v43.m128i_i64[1] - v43.m128i_i64[0]) >> 5) + ((a5[1] - *a5) >> 5);
    v24 = (a5[2] - *a5) >> 5;
    if ( v23 > v24 )
    {
      v25 = ((v43.m128i_i64[1] - v43.m128i_i64[0]) >> 5) + ((a5[1] - *a5) >> 5);
      v26 = 7 * (v24 >> 2) + 8;
      if ( v26 >= v23 )
        v25 = v26;
      if ( v25 > 0x3FFFFFFFFFFFFFFLL )
        v25 = 0x3FFFFFFFFFFFFFFLL;
      if ( v23 <= v25 && utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_SetCapacity(a5, v25) )
      {
        v21 = (_QWORD *)v43.m128i_i64[1];
        v22 = (_QWORD *)v43.m128i_i64[0];
        goto LABEL_25;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x358,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)0x8007000ELL,
        v36);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v43);
LABEL_51:
      if ( v41[0] != v42 )
        operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_53:
      v31 = v37[0];
      v32 = v38;
LABEL_69:
      if ( v31 != v32 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      return 2147942414LL;
    }
    while ( v22 != v21 )
    {
      if ( !utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(v20, v22) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x35B,
          (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
          v27);
      v22 += 4;
LABEL_25:
      v20 = a5;
    }
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v43);
    if ( v41[0] != v42 )
      operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v37[0] != v38 )
      operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
    v10 = a4;
    a2 = v49;
    v5 = a5;
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x355,
    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
    (const char *)(unsigned int)v18,
    v36);
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v43);
  if ( v41[0] != v42 )
    operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v37[0] != v38 )
    operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
  return v19;
}

```

## disassembly

```asm
0x18000bd28  mov     rax, rsp
0x18000bd2b  mov     [rax+8], rbx
0x18000bd2f  mov     [rax+20h], r9
0x18000bd33  mov     [rax+10h], rdx
0x18000bd37  push    rbp
0x18000bd38  push    rsi
0x18000bd39  push    rdi
0x18000bd3a  push    r12
0x18000bd3c  push    r13
0x18000bd3e  push    r14
0x18000bd40  push    r15
0x18000bd42  lea     rbp, [rax-57h]
0x18000bd46  sub     rsp, 0F0h
0x18000bd4d  mov     rbx, [rbp+4Fh+arg_20]
0x18000bd51  lea     r15, [rcx+8]
0x18000bd55  movaps  xmmword ptr [rax-48h], xmm6
0x18000bd59  lea     r14, [r15+2Ch]
0x18000bd5d  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000bd65  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000bd6c  mov     r13, rcx
0x18000bd6f  mov     rdi, r9
0x18000bd72  mov     r12d, r8d
0x18000bd75  xor     ecx, ecx
0x18000bd77  cmp     word ptr [r14], 2Eh ; '.'
0x18000bd7c  jnz     short loc_18000BD9C
0x18000bd7e  cmp     [r15+2Eh], cx
0x18000bd83  jz      loc_18000C069
0x18000bd89  cmp     word ptr [r15+2Eh], 2Eh ; '.'
0x18000bd8f  jnz     short loc_18000BD9C
0x18000bd91  cmp     [r15+30h], cx
0x18000bd96  jz      loc_18000C069
0x18000bd9c  test    r12b, 4
0x18000bda0  jz      loc_18000BF97
0x18000bda6  test    byte ptr [r15], 10h
0x18000bdaa  jz      loc_18000BFA3
0x18000bdb0  mov     r8, [rdx+8]
0x18000bdb4  lea     rax, [rsp+120h+var_E0]
0x18000bdb9  sub     r8, [rdx]
0x18000bdbc  lea     rcx, [rsp+120h+var_F0]
0x18000bdc1  mov     rdx, [rdx]
0x18000bdc4  xor     ebx, ebx
0x18000bdc6  mov     [rsp+120h+var_F0], rax
0x18000bdcb  lea     rax, [rsp+120h+var_E0]
0x18000bdd0  sar     r8, 1
0x18000bdd3  mov     qword ptr [rsp+120h+var_E8], rax
0x18000bdd8  mov     [rsp+120h+var_E0], bx
0x18000bddd  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000bde2  test    al, al
0x18000bde4  jz      loc_18000C172
0x18000bdea  mov     [rbp+4Fh+var_78], r14
0x18000bdee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bdf2  inc     rax
0x18000bdf5  cmp     [r14+rax*2], bx
0x18000bdfa  jnz     short loc_18000BDF2
0x18000bdfc  lea     rdx, [rbp+4Fh+var_78]
0x18000be00  mov     [rbp+4Fh+var_70], rax
0x18000be04  lea     rcx, [rsp+120h+var_F0]; this
0x18000be09  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18000be0e  test    al, al
0x18000be10  jz      loc_18000C152
0x18000be16  mov     rdx, [r13+258h]
0x18000be1d  lea     rax, [rbp+4Fh+var_A0]
0x18000be21  mov     r8, [r13+260h]
0x18000be28  lea     rcx, [rbp+4Fh+var_B0]
0x18000be2c  mov     [rbp+4Fh+var_B0], rax
0x18000be30  sub     r8, rdx
0x18000be33  lea     rax, [rbp+4Fh+var_A0]
0x18000be37  sar     r8, 1
0x18000be3a  mov     [rbp+4Fh+var_A8], rax
0x18000be3e  mov     [rbp+4Fh+var_A0], bx
0x18000be42  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000be47  test    al, al
0x18000be49  jz      loc_18000C14B
0x18000be4f  mov     [rbp+4Fh+var_68], r14
0x18000be53  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000be57  inc     rax
0x18000be5a  cmp     [r14+rax*2], bx
0x18000be5f  jnz     short loc_18000BE57
0x18000be61  lea     rdx, [rbp+4Fh+var_68]
0x18000be65  mov     [rbp+4Fh+var_60], rax
0x18000be69  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000be6d  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18000be72  test    al, al
0x18000be74  jz      loc_18000C12B
0x18000be7a  lea     r9, [rbp+4Fh+var_90]
0x18000be7e  mov     [rbp+4Fh+var_80], 0FFFFFFFFFFFFFFFFh
0x18000be86  mov     r8d, r12d
0x18000be89  mov     qword ptr [rsp+120h+var_100], rdi; int
0x18000be8e  lea     rdx, [rsp+120h+var_F0]
0x18000be93  lea     rcx, [rbp+4Fh+var_B0]
0x18000be97  movdqu  [rbp+4Fh+var_90], xmm6
0x18000be9c  call    ?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x18000bea1  mov     ebx, eax
0x18000bea3  test    eax, eax
0x18000bea5  js      loc_18000C0D7
0x18000beab  mov     r9, [rbp+4Fh+arg_20]
0x18000beaf  mov     rdi, qword ptr [rbp+4Fh+var_90+8]
0x18000beb3  mov     rbx, qword ptr [rbp+4Fh+var_90]
0x18000beb7  mov     rax, rdi
0x18000beba  sub     rax, rbx
0x18000bebd  mov     r8, [r9+8]
0x18000bec1  sub     r8, [r9]
0x18000bec4  sar     rax, 5
0x18000bec8  sar     r8, 5
0x18000becc  add     r8, rax
0x18000becf  mov     rax, [r9+10h]
0x18000bed3  sub     rax, [r9]
0x18000bed6  sar     rax, 5
0x18000beda  cmp     r8, rax
0x18000bedd  jbe     short loc_18000BF2B
0x18000bedf  shr     rax, 2
0x18000bee3  mov     rdx, r8
0x18000bee6  imul    rax, 7
0x18000beea  add     rax, 8
0x18000beee  cmp     rax, r8
0x18000bef1  cmovnb  rdx, rax
0x18000bef5  mov     rax, 3FFFFFFFFFFFFFFh
0x18000beff  cmp     rdx, rax
0x18000bf02  cmova   rdx, rax
0x18000bf06  cmp     r8, rdx
0x18000bf09  ja      loc_18000C08F
0x18000bf0f  mov     rcx, r9
0x18000bf12  call    ?_SetCapacity@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_SetCapacity(unsigned __int64)
0x18000bf17  test    al, al
0x18000bf19  jz      loc_18000C08F
0x18000bf1f  mov     rdi, qword ptr [rbp+4Fh+var_90+8]
0x18000bf23  mov     rbx, qword ptr [rbp+4Fh+var_90]
0x18000bf27  mov     r9, [rbp+4Fh+arg_20]
0x18000bf2b  cmp     rbx, rdi
0x18000bf2e  jz      short loc_18000BF4D
0x18000bf30  mov     rsi, [rbp+57h]
0x18000bf34  mov     rdx, rbx
0x18000bf37  mov     rcx, r9
0x18000bf3a  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x18000bf3f  test    al, al
0x18000bf41  jz      loc_18000C1E2
0x18000bf47  add     rbx, 20h ; ' '
0x18000bf4b  jmp     short loc_18000BF27
0x18000bf4d  lea     rcx, [rbp+4Fh+var_90]
0x18000bf51  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000bf56  mov     rcx, [rbp+4Fh+var_B0]; void *
0x18000bf5a  lea     rax, [rbp+4Fh+var_A0]
0x18000bf5e  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000bf65  cmp     rcx, rax
0x18000bf68  jz      short loc_18000BF72
0x18000bf6a  mov     rdx, rsi; struct std::nothrow_t *
0x18000bf6d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bf72  mov     rcx, [rsp+120h+var_F0]; void *
0x18000bf77  lea     rax, [rsp+120h+var_E0]
0x18000bf7c  cmp     rcx, rax
0x18000bf7f  jz      short loc_18000BF89
0x18000bf81  mov     rdx, rsi; struct std::nothrow_t *
0x18000bf84  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bf89  mov     rdi, [rbp+4Fh+arg_18]
0x18000bf8d  xor     ecx, ecx
0x18000bf8f  mov     rdx, [rbp+4Fh+arg_8]
0x18000bf93  mov     rbx, [rbp+4Fh+arg_20]
0x18000bf97  test    byte ptr [r15], 10h
0x18000bf9b  jz      short loc_18000BFA3
0x18000bf9d  test    r12b, 2
0x18000bfa1  jmp     short loc_18000BFA7
0x18000bfa3  test    r12b, 8
0x18000bfa7  jz      loc_18000C069
0x18000bfad  mov     [rbp+4Fh+var_C0], cx
0x18000bfb1  lea     rax, [rbp+4Fh+var_C0]
0x18000bfb5  mov     [rsp+120h+var_D0], rax
0x18000bfba  lea     rax, [rbp+4Fh+var_C0]
0x18000bfbe  mov     [rbp+4Fh+var_C8], rax
0x18000bfc2  lea     rcx, [rsp+120h+var_D0]
0x18000bfc7  test    r12b, 1
0x18000bfcb  jz      short loc_18000BFF6
0x18000bfcd  mov     rdx, [r13+258h]
0x18000bfd4  mov     r8, [r13+260h]
0x18000bfdb  sub     r8, rdx
0x18000bfde  sar     r8, 1
0x18000bfe1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000bfe6  xor     ecx, ecx
0x18000bfe8  test    al, al
0x18000bfea  jnz     short loc_18000C012
0x18000bfec  mov     edx, 371h
0x18000bff1  jmp     loc_18000C18C
0x18000bff6  mov     r8, [rdx+8]
0x18000bffa  sub     r8, [rdx]
0x18000bffd  mov     rdx, [rdx]
0x18000c000  sar     r8, 1
0x18000c003  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000c008  xor     ecx, ecx
0x18000c00a  test    al, al
0x18000c00c  jz      loc_18000C187
0x18000c012  mov     [rbp+4Fh+var_58], r14
0x18000c016  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c01a  inc     rax
0x18000c01d  cmp     [r14+rax*2], cx
0x18000c022  jnz     short loc_18000C01A
0x18000c024  lea     rdx, [rbp+4Fh+var_58]
0x18000c028  mov     [rbp+4Fh+var_50], rax
0x18000c02c  lea     rcx, [rsp+120h+var_D0]; this
0x18000c031  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18000c036  test    al, al
0x18000c038  jz      loc_18000C180
0x18000c03e  lea     rdx, [rsp+120h+var_D0]
0x18000c043  mov     rcx, rbx
0x18000c046  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x18000c04b  test    al, al
0x18000c04d  jz      loc_18000C179
0x18000c053  mov     rcx, [rsp+120h+var_D0]; void *
0x18000c058  lea     rax, [rbp+4Fh+var_C0]
0x18000c05c  cmp     rcx, rax
0x18000c05f  jz      short loc_18000C069
0x18000c061  mov     rdx, rsi; struct std::nothrow_t *
0x18000c064  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c069  mov     rcx, [r13+0]; hFindFile
0x18000c06d  mov     rdx, r15; lpFindFileData
0x18000c070  call    cs:__imp_FindNextFileW
0x18000c077  nop     dword ptr [rax+rax+00h]
0x18000c07c  xor     ecx, ecx
0x18000c07e  test    eax, eax
0x18000c080  jz      loc_18000C1BF
0x18000c086  mov     rdx, [rbp+4Fh+arg_8]
0x18000c08a  jmp     loc_18000BD77
0x18000c08f  mov     rcx, [rbp+57h]; this
0x18000c093  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c09a  mov     r9d, 8007000Eh; char *
0x18000c0a0  mov     edx, 358h; void *
0x18000c0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0aa  lea     rcx, [rbp+4Fh+var_90]
0x18000c0ae  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c0b3  mov     rcx, [rbp+4Fh+var_B0]; void *
0x18000c0b7  lea     rax, [rbp+4Fh+var_A0]
0x18000c0bb  cmp     rcx, rax
0x18000c0be  jz      short loc_18000C0C8
0x18000c0c0  mov     rdx, rsi; struct std::nothrow_t *
0x18000c0c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c0c8  mov     rcx, [rsp+120h+var_F0]
0x18000c0cd  lea     rax, [rsp+120h+var_E0]
0x18000c0d2  jmp     loc_18000C1AB
0x18000c0d7  mov     rcx, [rbp+57h]; this
0x18000c0db  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c0e2  mov     r9d, ebx; char *
0x18000c0e5  mov     edx, 355h; void *
0x18000c0ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0ef  lea     rcx, [rbp+4Fh+var_90]
0x18000c0f3  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c0f8  mov     rcx, [rbp+4Fh+var_B0]; void *
0x18000c0fc  lea     rax, [rbp+4Fh+var_A0]
0x18000c100  cmp     rcx, rax
0x18000c103  jz      short loc_18000C10D
0x18000c105  mov     rdx, rsi; struct std::nothrow_t *
0x18000c108  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c10d  mov     rcx, [rsp+120h+var_F0]; void *
0x18000c112  lea     rax, [rsp+120h+var_E0]
0x18000c117  cmp     rcx, rax
0x18000c11a  jz      short loc_18000C124
0x18000c11c  mov     rdx, rsi; struct std::nothrow_t *
0x18000c11f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c124  mov     eax, ebx
0x18000c126  jmp     loc_18000C1C1
0x18000c12b  mov     edx, 34Eh; void *
0x18000c130  mov     rcx, [rbp+57h]; this
0x18000c134  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c13b  mov     r9d, 8007000Eh; char *
0x18000c141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c146  jmp     loc_18000C0B3
0x18000c14b  mov     edx, 34Dh
0x18000c150  jmp     short loc_18000C130
0x18000c152  mov     edx, 349h; void *
0x18000c157  mov     rcx, [rbp+57h]; this
0x18000c15b  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c162  mov     r9d, 8007000Eh; char *
0x18000c168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c16d  jmp     loc_18000C0C8
0x18000c172  mov     edx, 348h
0x18000c177  jmp     short loc_18000C157
0x18000c179  mov     edx, 37Ah
0x18000c17e  jmp     short loc_18000C18C
0x18000c180  mov     edx, 378h
0x18000c185  jmp     short loc_18000C18C
0x18000c187  mov     edx, 375h; void *
0x18000c18c  mov     rcx, [rbp+57h]; this
0x18000c190  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c197  mov     r9d, 8007000Eh; char *
0x18000c19d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1a2  mov     rcx, [rsp+120h+var_D0]; void *
0x18000c1a7  lea     rax, [rbp+4Fh+var_C0]
0x18000c1ab  cmp     rcx, rax
0x18000c1ae  jz      short loc_18000C1B8
0x18000c1b0  mov     rdx, rsi; struct std::nothrow_t *
0x18000c1b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c1b8  mov     eax, 8007000Eh
0x18000c1bd  jmp     short loc_18000C1C1
0x18000c1bf  xor     eax, eax
0x18000c1c1  lea     r11, [rsp+120h+var_30]
0x18000c1c9  mov     rbx, [r11+40h]
0x18000c1cd  movaps  xmm6, xmmword ptr [r11-10h]
0x18000c1d2  mov     rsp, r11
0x18000c1d5  pop     r15
0x18000c1d7  pop     r14
0x18000c1d9  pop     r13
0x18000c1db  pop     r12
0x18000c1dd  pop     rdi
  ... truncated ...
```

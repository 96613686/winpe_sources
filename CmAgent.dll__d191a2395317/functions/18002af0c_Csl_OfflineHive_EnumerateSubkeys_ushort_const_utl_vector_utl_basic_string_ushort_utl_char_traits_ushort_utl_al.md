# Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)

- ea: `0x18002af0c`
- end: `0x18002b5d8`
- name: `?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z`
- size: `1740`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, char)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180028afc`
- `0x18002ad68`
- `0x18002af0c`

## callees

- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x1800045e4`
- `0x180007b4c`
- `0x18000acd0`
- `0x18000adb8`
- `0x18000bb98`
- `0x18000bc38`
- `0x180026998`
- `0x18002a820`
- `0x18002af0c`
- `0x18002c6e0`
- `0x18002cff0`
- `0x18002d190`
- `0x18002d51c`

## string_xrefs

- `0x18002afaa`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b033`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b170`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b30c`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b366`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b3c9`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b423`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b481`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b4e4`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b536`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::EnumerateSubkeys(__int64 a1, __int64 a2, __int64 *a3, char a4)
{
  __m128i si128; // xmm6
  __int64 v7; // r15
  unsigned int v8; // r12d
  __int64 v9; // rsi
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  unsigned int v14; // eax
  unsigned __int64 v15; // rbx
  _WORD *v16; // rax
  _WORD *v17; // r14
  __int64 v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  const struct std::nothrow_t *v22; // rdx
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // r10
  __int64 v27; // rcx
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // r15
  unsigned __int64 v30; // r15
  unsigned __int64 v31; // rdx
  const struct std::nothrow_t *v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  __int64 v39; // rbx
  __int64 v40; // rdi
  const struct std::nothrow_t *v41; // rdx
  unsigned int v43; // [rsp+28h] [rbp-B9h]
  unsigned int v44; // [rsp+28h] [rbp-B9h]
  unsigned int v45; // [rsp+28h] [rbp-B9h]
  void *v46[2]; // [rsp+68h] [rbp-79h] BYREF
  _WORD v47[8]; // [rsp+78h] [rbp-69h] BYREF
  __m128i v48; // [rsp+88h] [rbp-59h] BYREF
  __int64 v49; // [rsp+98h] [rbp-49h]
  int v50; // [rsp+A0h] [rbp-41h]
  __m128i v51; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-29h]
  _QWORD v53[2]; // [rsp+C0h] [rbp-21h] BYREF
  _QWORD v54[2]; // [rsp+D0h] [rbp-11h] BYREF
  _QWORD v55[5]; // [rsp+E0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]
  __int64 v57; // [rsp+148h] [rbp+67h]
  __int64 v58; // [rsp+150h] [rbp+6Fh] BYREF
  unsigned int v59; // [rsp+160h] [rbp+7Fh] BYREF

  LOBYTE(v59) = a4;
  v57 = a1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v48 = si128;
  v7 = -1;
  v49 = -1;
  v8 = 0;
  v9 = 0;
  v58 = 0;
  if ( a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(a2 + 2 * v10) );
    if ( v10 )
    {
      v11 = OROpenKey(*(_QWORD *)(a1 + 8), a2, &v58);
      if ( v11 == 2 )
      {
        if ( v58 )
          ORCloseKey(v58);
        v12 = -2147024894;
        goto LABEL_103;
      }
      if ( v11 )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x43B,
                (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
                (const char *)v11,
                v43);
        if ( v58 )
          ORCloseKey(v58);
        goto LABEL_103;
      }
      v9 = v58;
      a1 = v57;
    }
  }
  v59 = 0;
  LODWORD(v58) = 0;
  if ( v9 )
    LODWORD(v13) = v9;
  else
    v13 = *(_QWORD *)(a1 + 8);
  v14 = ORQueryInfoKey(v13, 0, 0, (unsigned int)&v59, (__int64)&v58, 0, 0, 0, 0, 0, 0);
  if ( v14 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x44D,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v14,
            v44);
    if ( v9 )
      ORCloseKey(v9);
    goto LABEL_103;
  }
  v50 = v58 + 1;
  v15 = 2LL * (unsigned int)(v58 + 1);
  if ( !is_mul_ok((unsigned int)(v58 + 1), 2u) )
    v15 = -1;
  v16 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  v17 = v16;
  if ( v16 )
    memset_0(v16, 0, v15);
  else
    v17 = 0;
  if ( v59 )
  {
    while ( 1 )
    {
      LODWORD(v58) = v50;
      LODWORD(v18) = v9;
      if ( !v9 )
        v18 = *(_QWORD *)(v57 + 8);
      v19 = OREnumKey(v18, v8, (_DWORD)v17, (unsigned int)&v58, 0, 0, 0);
      if ( v19 )
        break;
      v17[(unsigned int)v58] = 0;
      v46[0] = v47;
      v46[1] = v47;
      v47[0] = 0;
      v20 = -1;
      if ( a2 )
      {
        v53[0] = a2;
        do
          ++v20;
        while ( *(_WORD *)(a2 + 2 * v20) );
        v53[1] = v20;
        if ( !Csl::Path::Assign((Csl::Path *)v46, (__int64)v53) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x469,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v45);
          if ( v46[0] != v47 )
            operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v32);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
        v54[0] = v17;
        v21 = -1;
        do
          ++v21;
        while ( v17[v21] );
        v54[1] = v21;
        if ( !Csl::Path::Append((Csl::Path *)v46, (__int64)v54) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x46A,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v45);
          if ( v46[0] != v47 )
            operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v22);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
      }
      else
      {
        v55[0] = v17;
        do
          ++v20;
        while ( v17[v20] );
        v55[1] = v20;
        if ( !Csl::Path::Assign((Csl::Path *)v46, (__int64)v55) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x46E,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v45);
          if ( v46[0] != v47 )
            operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v37);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
      }
      v51 = si128;
      v52 = -1;
      v23 = Csl::OfflineHive::EnumerateSubkeys(v57, v46[0], &v51);
      v12 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x475,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
          (const char *)(unsigned int)v23,
          v45);
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v51);
        if ( v46[0] != v47 )
          operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          operator delete(v17, v36);
        if ( !v9 )
          goto LABEL_103;
        goto LABEL_102;
      }
      v24 = v51.m128i_i64[1];
      v25 = v51.m128i_i64[0];
      v26 = v48.m128i_i64[1];
      v27 = (v48.m128i_i64[1] - v48.m128i_i64[0]) >> 5;
      v28 = v27 + ((v51.m128i_i64[1] - v51.m128i_i64[0]) >> 5);
      v29 = (v7 - v48.m128i_i64[0]) >> 5;
      if ( v28 > v29 )
      {
        v30 = v29 >> 2;
        v31 = v27 + ((v51.m128i_i64[1] - v51.m128i_i64[0]) >> 5);
        if ( 7 * v30 + 8 >= v28 )
          v31 = 7 * v30 + 8;
        if ( v31 > 0x3FFFFFFFFFFFFFFLL )
          v31 = 0x3FFFFFFFFFFFFFFLL;
        if ( v28 > v31
          || !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_SetCapacity(&v48) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x478,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v45);
          utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v51);
          if ( v46[0] != v47 )
            operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v33);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
        v26 = v48.m128i_i64[1];
        v24 = v51.m128i_i64[1];
        v25 = v51.m128i_i64[0];
      }
      v58 = v25;
      if ( !utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_InsertManyFillFn<_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_>(
              &v48,
              v26,
              (v24 - v25) >> 5,
              &v58) )
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
          (const char *)0x8007000ELL,
          v45);
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v51);
        if ( v46[0] != v47 )
          operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          operator delete(v17, v35);
        if ( !v9 )
          goto LABEL_103;
        goto LABEL_102;
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v51);
      if ( !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const &,0>(
                               &v48,
                               v46) )
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47F,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
          (const char *)0x8007000ELL,
          v45);
        if ( v46[0] != v47 )
          operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          operator delete(v17, v34);
        if ( !v9 )
          goto LABEL_103;
        goto LABEL_102;
      }
      if ( v46[0] != v47 )
        operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
      ++v8;
      v7 = v49;
      if ( v8 >= v59 )
        goto LABEL_99;
    }
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x45E,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v19,
            v45);
    if ( v17 )
      operator delete(v17, v38);
    if ( !v9 )
      goto LABEL_103;
    goto LABEL_102;
  }
LABEL_99:
  v40 = v48.m128i_i64[1];
  v39 = v48.m128i_i64[0];
  v48 = si128;
  v49 = -1;
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)a3);
  *a3 = v39;
  a3[1] = v40;
  a3[2] = v7;
  v12 = 0;
  if ( v17 )
    operator delete(v17, v41);
  if ( v9 )
LABEL_102:
    ORCloseKey(v9);
LABEL_103:
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v48);
  return v12;
}

```

## disassembly

```asm
0x18002af0c  mov     rax, rsp
0x18002af0f  mov     [rax+18h], rbx
0x18002af13  mov     [rax+20h], r9b
0x18002af17  mov     [rax+8], rcx
0x18002af1b  push    rbp
0x18002af1c  push    rsi
0x18002af1d  push    rdi
0x18002af1e  push    r12
0x18002af20  push    r13
0x18002af22  push    r14
0x18002af24  push    r15
0x18002af26  lea     rbp, [rax-5Fh]
0x18002af2a  sub     rsp, 100h
0x18002af31  movaps  xmmword ptr [rax-48h], xmm6
0x18002af35  mov     r13, r8
0x18002af38  mov     rdi, rdx
0x18002af3b  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002af43  movdqu  [rbp+57h+var_B0], xmm6
0x18002af48  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002af4c  mov     r15, r14
0x18002af4f  mov     [rbp+57h+var_A0], r14
0x18002af53  xor     r12d, r12d
0x18002af56  mov     esi, r12d
0x18002af59  mov     [rbp+57h+arg_8], r12
0x18002af5d  test    rdx, rdx
0x18002af60  jz      short loc_18002AFDD
0x18002af62  mov     rax, r14
0x18002af65  inc     rax
0x18002af68  cmp     [rdx+rax*2], r12w
0x18002af6d  jnz     short loc_18002AF65
0x18002af6f  test    rax, rax
0x18002af72  jz      short loc_18002AFDD
0x18002af74  lea     r8, [rbp+57h+arg_8]
0x18002af78  mov     rcx, [rcx+8]
0x18002af7c  call    OROpenKey
0x18002af81  cmp     eax, 2
0x18002af84  jnz     short loc_18002AF9F
0x18002af86  mov     rcx, [rbp+57h+arg_8]
0x18002af8a  test    rcx, rcx
0x18002af8d  jz      short loc_18002AF95
0x18002af8f  call    ORCloseKey
0x18002af94  nop
0x18002af95  mov     ebx, 80070002h
0x18002af9a  jmp     loc_18002B5AC
0x18002af9f  test    eax, eax
0x18002afa1  jz      short loc_18002AFD5
0x18002afa3  mov     rcx, [rbp+5Fh]; this
0x18002afa7  mov     r9d, eax; char *
0x18002afaa  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002afb1  mov     edx, 43Bh; void *
0x18002afb6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002afbb  mov     ebx, eax
0x18002afbd  mov     rcx, [rbp+57h+arg_8]
0x18002afc1  test    rcx, rcx
0x18002afc4  jz      loc_18002B5AC
0x18002afca  call    ORCloseKey
0x18002afcf  nop
0x18002afd0  jmp     loc_18002B5AC
0x18002afd5  mov     rsi, [rbp+57h+arg_8]
0x18002afd9  mov     rcx, [rbp+57h+arg_0]
0x18002afdd  mov     [rbp+57h+arg_18], r12d
0x18002afe1  mov     dword ptr [rbp+57h+arg_8], r12d
0x18002afe5  test    rsi, rsi
0x18002afe8  jz      short loc_18002AFEF
0x18002afea  mov     rcx, rsi
0x18002afed  jmp     short loc_18002AFF3
0x18002afef  mov     rcx, [rcx+8]
0x18002aff3  mov     [rsp+130h+var_E0], r12
0x18002aff8  mov     [rsp+130h+var_E8], r12
0x18002affd  mov     [rsp+130h+var_F0], r12
0x18002b002  mov     [rsp+130h+var_F8], r12
0x18002b007  mov     [rsp+130h+var_100], r12
0x18002b00c  mov     [rsp+130h+var_108], r12
0x18002b011  lea     rax, [rbp+57h+arg_8]
0x18002b015  mov     qword ptr [rsp+130h+var_110], rax; unsigned int
0x18002b01a  lea     r9, [rbp+57h+arg_18]
0x18002b01e  xor     r8d, r8d
0x18002b021  xor     edx, edx
0x18002b023  call    ORQueryInfoKey
0x18002b028  test    eax, eax
0x18002b02a  jz      short loc_18002B05D
0x18002b02c  mov     rcx, [rbp+5Fh]; this
0x18002b030  mov     r9d, eax; char *
0x18002b033  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b03a  mov     edx, 44Dh; void *
0x18002b03f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b044  mov     ebx, eax
0x18002b046  test    rsi, rsi
0x18002b049  jz      loc_18002B5AC
0x18002b04f  mov     rcx, rsi
0x18002b052  call    ORCloseKey
0x18002b057  nop
0x18002b058  jmp     loc_18002B5AC
0x18002b05d  mov     eax, dword ptr [rbp+57h+arg_8]
0x18002b060  inc     eax
0x18002b062  mov     [rbp+57h+var_98], eax
0x18002b065  mov     ecx, eax
0x18002b067  mov     eax, 2
0x18002b06c  mul     rcx
0x18002b06f  mov     rbx, rax
0x18002b072  cmovb   rbx, r14
0x18002b076  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b07d  mov     rcx, rbx; unsigned __int64
0x18002b080  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002b085  mov     r14, rax
0x18002b088  test    rax, rax
0x18002b08b  jz      short loc_18002B09C
0x18002b08d  mov     r8, rbx; Size
0x18002b090  xor     edx, edx; Val
0x18002b092  mov     rcx, rax; void *
0x18002b095  call    memset_0
0x18002b09a  jmp     short loc_18002B09F
0x18002b09c  mov     r14, r12
0x18002b09f  xor     edx, edx
0x18002b0a1  cmp     [rbp+57h+arg_18], edx
0x18002b0a4  jbe     loc_18002B566
0x18002b0aa  mov     eax, [rbp+57h+var_98]
0x18002b0ad  mov     dword ptr [rbp+57h+arg_8], eax
0x18002b0b0  mov     rbx, [rbp+57h+arg_0]
0x18002b0b4  test    rsi, rsi
0x18002b0b7  mov     rcx, rsi
0x18002b0ba  jnz     short loc_18002B0C0
0x18002b0bc  mov     rcx, [rbx+8]
0x18002b0c0  mov     [rsp+130h+var_100], rdx
0x18002b0c5  mov     [rsp+130h+var_108], rdx
0x18002b0ca  mov     qword ptr [rsp+130h+var_110], rdx; unsigned int
0x18002b0cf  lea     r9, [rbp+57h+arg_8]
0x18002b0d3  mov     r8, r14
0x18002b0d6  mov     edx, r12d
0x18002b0d9  call    OREnumKey
0x18002b0de  xor     edx, edx
0x18002b0e0  test    eax, eax
0x18002b0e2  jnz     loc_18002B52F
0x18002b0e8  mov     ecx, dword ptr [rbp+57h+arg_8]
0x18002b0eb  mov     [r14+rcx*2], dx
0x18002b0f0  lea     rax, [rbp+57h+var_C0]
0x18002b0f4  mov     [rbp+57h+var_D0], rax
0x18002b0f8  lea     rax, [rbp+57h+var_C0]
0x18002b0fc  mov     [rbp+57h+var_C8], rax
0x18002b100  mov     [rbp+57h+var_C0], dx
0x18002b104  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b108  test    rdi, rdi
0x18002b10b  jz      loc_18002B1BE
0x18002b111  mov     [rbp+57h+var_78], rdi
0x18002b115  inc     rax
0x18002b118  cmp     [rdi+rax*2], dx
0x18002b11c  jnz     short loc_18002B115
0x18002b11e  mov     [rbp+57h+var_70], rax
0x18002b122  lea     rdx, [rbp+57h+var_78]
0x18002b126  lea     rcx, [rbp+57h+var_D0]; this
0x18002b12a  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18002b12f  xor     ecx, ecx
0x18002b131  test    al, al
0x18002b133  jz      loc_18002B300
0x18002b139  mov     [rbp+57h+var_68], r14
0x18002b13d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b141  inc     rax
0x18002b144  cmp     [r14+rax*2], cx
0x18002b149  jnz     short loc_18002B141
0x18002b14b  mov     [rbp+57h+var_60], rax
0x18002b14f  lea     rdx, [rbp+57h+var_68]
0x18002b153  lea     rcx, [rbp+57h+var_D0]; this
0x18002b157  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18002b15c  test    al, al
0x18002b15e  jnz     loc_18002B1E5
0x18002b164  mov     rcx, [rbp+5Fh]; this
0x18002b168  mov     ebx, 8007000Eh
0x18002b16d  mov     r9d, ebx; char *
0x18002b170  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b177  mov     edx, 46Ah; void *
0x18002b17c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b181  mov     rcx, [rbp+57h+var_D0]; void *
0x18002b185  lea     rax, [rbp+57h+var_C0]
0x18002b189  cmp     rcx, rax
0x18002b18c  jz      short loc_18002B19A
0x18002b18e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b195  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b19a  test    r14, r14
0x18002b19d  jz      short loc_18002B1A7
0x18002b19f  mov     rcx, r14; void *
0x18002b1a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b1a7  test    rsi, rsi
0x18002b1aa  jz      loc_18002B5AC
0x18002b1b0  mov     rcx, rsi
0x18002b1b3  call    ORCloseKey
0x18002b1b8  nop
0x18002b1b9  jmp     loc_18002B5AC
0x18002b1be  mov     [rbp+57h+var_58], r14
0x18002b1c2  inc     rax
0x18002b1c5  cmp     [r14+rax*2], dx
0x18002b1ca  jnz     short loc_18002B1C2
0x18002b1cc  mov     [rbp+57h+var_50], rax
0x18002b1d0  lea     rdx, [rbp+57h+var_58]
0x18002b1d4  lea     rcx, [rbp+57h+var_D0]; this
0x18002b1d8  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18002b1dd  test    al, al
0x18002b1df  jz      loc_18002B4D8
0x18002b1e5  movdqu  [rbp+57h+var_90], xmm6
0x18002b1ea  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x18002b1f2  mov     r9b, 1
0x18002b1f5  lea     r8, [rbp+57h+var_90]
0x18002b1f9  mov     rdx, [rbp+57h+var_D0]
0x18002b1fd  mov     rcx, rbx
0x18002b200  call    ?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z; Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)
0x18002b205  mov     ebx, eax
0x18002b207  test    eax, eax
0x18002b209  js      loc_18002B47A
0x18002b20f  mov     r8, qword ptr [rbp+57h+var_90+8]
0x18002b213  mov     r9, r8
0x18002b216  mov     rax, qword ptr [rbp+57h+var_90]
0x18002b21a  sub     r9, rax
0x18002b21d  sar     r9, 5
0x18002b221  mov     r10, qword ptr [rbp+57h+var_B0+8]
0x18002b225  mov     rcx, r10
0x18002b228  sub     rcx, qword ptr [rbp+57h+var_B0]
0x18002b22c  sar     rcx, 5
0x18002b230  add     r9, rcx
0x18002b233  sub     r15, qword ptr [rbp+57h+var_B0]
0x18002b237  sar     r15, 5
0x18002b23b  cmp     r9, r15
0x18002b23e  jbe     short loc_18002B28D
0x18002b240  shr     r15, 2
0x18002b244  imul    rax, r15, 7
0x18002b248  add     rax, 8
0x18002b24c  mov     rdx, r9
0x18002b24f  cmp     rax, r9
0x18002b252  cmovnb  rdx, rax
0x18002b256  mov     rbx, 3FFFFFFFFFFFFFFh
0x18002b260  cmp     rdx, rbx
0x18002b263  cmova   rdx, rbx
0x18002b267  cmp     r9, rdx
0x18002b26a  ja      loc_18002B35A
0x18002b270  lea     rcx, [rbp+57h+var_B0]
0x18002b274  call    ?_SetCapacity@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_SetCapacity(unsigned __int64)
0x18002b279  test    al, al
0x18002b27b  jz      loc_18002B35A
0x18002b281  mov     r10, qword ptr [rbp+57h+var_B0+8]
0x18002b285  mov     r8, qword ptr [rbp+57h+var_90+8]
0x18002b289  mov     rax, qword ptr [rbp+57h+var_90]
0x18002b28d  mov     [rbp+57h+arg_8], rax
0x18002b291  sub     r8, rax
0x18002b294  sar     r8, 5
0x18002b298  lea     r9, [rbp+57h+arg_8]
0x18002b29c  mov     rdx, r10
0x18002b29f  lea     rcx, [rbp+57h+var_B0]
0x18002b2a3  call    ??$_InsertManyFillFn@V_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_@@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@PEAV21@_KV_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_@@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_InsertManyFillFn<_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,unsigned __int64,_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_)
0x18002b2a8  test    rax, rax
0x18002b2ab  jz      loc_18002B417
0x18002b2b1  lea     rcx, [rbp+57h+var_90]
0x18002b2b5  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002b2ba  lea     rdx, [rbp+57h+var_D0]
0x18002b2be  lea     rcx, [rbp+57h+var_B0]
0x18002b2c2  call    ??$emplace_back@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::emplace_back<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18002b2c7  test    al, al
0x18002b2c9  jz      loc_18002B3BD
0x18002b2cf  mov     rcx, [rbp+57h+var_D0]; void *
0x18002b2d3  lea     rax, [rbp+57h+var_C0]
0x18002b2d7  cmp     rcx, rax
0x18002b2da  jz      short loc_18002B2E8
0x18002b2dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b2e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b2e8  inc     r12d
0x18002b2eb  mov     r15, [rbp+57h+var_A0]
0x18002b2ef  cmp     r12d, [rbp+57h+arg_18]
0x18002b2f3  jnb     loc_18002B566
0x18002b2f9  xor     edx, edx
0x18002b2fb  jmp     loc_18002B0AA
0x18002b300  mov     rcx, [rbp+5Fh]; this
0x18002b304  mov     ebx, 8007000Eh
0x18002b309  mov     r9d, ebx; char *
0x18002b30c  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b313  mov     edx, 469h; void *
0x18002b318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b31d  mov     rcx, [rbp+57h+var_D0]; void *
0x18002b321  lea     rax, [rbp+57h+var_C0]
0x18002b325  cmp     rcx, rax
0x18002b328  jz      short loc_18002B336
0x18002b32a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b331  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b336  test    r14, r14
0x18002b339  jz      short loc_18002B343
0x18002b33b  mov     rcx, r14; void *
0x18002b33e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b343  test    rsi, rsi
0x18002b346  jz      loc_18002B5AC
0x18002b34c  mov     rcx, rsi
0x18002b34f  call    ORCloseKey
0x18002b354  nop
0x18002b355  jmp     loc_18002B5AC
0x18002b35a  mov     rcx, [rbp+5Fh]; this
0x18002b35e  mov     ebx, 8007000Eh
0x18002b363  mov     r9d, ebx; char *
0x18002b366  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b36d  mov     edx, 478h; void *
0x18002b372  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b377  lea     rcx, [rbp+57h+var_90]
0x18002b37b  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002b380  mov     rcx, [rbp+57h+var_D0]; void *
0x18002b384  lea     rax, [rbp+57h+var_C0]
0x18002b388  cmp     rcx, rax
  ... truncated ...
```

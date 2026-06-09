# Container::Manager::Image::_anonymous_namespace_::ProcessRegistryAdjustment

- ea: `0x180029264`
- end: `0x18002967c`
- name: `Container::Manager::Image::_anonymous_namespace_::ProcessRegistryAdjustment`
- size: `1048`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180029070`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180007b4c`
- `0x180009e10`
- `0x18000a790`
- `0x18000adb8`
- `0x18000bc38`
- `0x180026998`
- `0x180027e10`
- `0x180029264`
- `0x180029ef8`
- `0x18002ad68`
- `0x18002ae38`
- `0x18002b5e0`
- `0x18002bca8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800293ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002946f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800293ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002946f`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::ProcessRegistryAdjustment(
        Csl::OfflineHive *this,
        __int64 a2)
{
  Csl::OfflineHive *v3; // r13
  int v4; // edx
  int v5; // edx
  __int64 v6; // rdx
  __m128i si128; // xmm6
  __int64 v9; // r8
  __int64 v10; // rdx
  int MultiStringValue; // eax
  unsigned int KeyRecursive; // ebx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  char v17; // r12
  void **v18; // rbx
  __int64 i; // rdi
  __int64 j; // rsi
  __int64 v21; // r13
  __int64 v22; // r12
  __int64 v23; // rbx
  __int64 k; // rdi
  int v25; // eax
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // [rsp+38h] [rbp-59h] BYREF
  __int64 v35; // [rsp+40h] [rbp-51h]
  __m128i v36; // [rsp+48h] [rbp-49h] BYREF
  __int64 v37; // [rsp+58h] [rbp-39h]
  __m128i v38; // [rsp+60h] [rbp-31h] BYREF
  __int64 v39; // [rsp+70h] [rbp-21h]
  void *v40[2]; // [rsp+78h] [rbp-19h] BYREF
  __int16 v41; // [rsp+88h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v3 = this;
  v4 = *(_DWORD *)(a2 + 4) - 1;
  if ( !v4 )
  {
    v31 = *(_QWORD *)(a2 + 16);
    v40[0] = &v41;
    v40[1] = &v41;
    v32 = *(_QWORD *)(a2 + 8);
    v41 = 0;
    v35 = (v31 - v32) >> 1;
    v34 = v32;
    if ( Csl::Path::Assign((Csl::Path *)v40, (__int64)&v34) )
    {
      KeyRecursive = Container::Manager::Image::_anonymous_namespace_::CreateKeyRecursive(v3);
      if ( (KeyRecursive & 0x80000000) == 0 )
      {
        KeyRecursive = Container::Manager::Image::_anonymous_namespace_::SetKeyValueInOfflineHive(
                         v3,
                         *(_DWORD *)(a2 + 104));
        if ( (KeyRecursive & 0x80000000) == 0 )
        {
          if ( v40[0] != &v41 )
            operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
          return 0;
        }
        v33 = 373;
      }
      else
      {
        v33 = 366;
      }
    }
    else
    {
      KeyRecursive = -2147024882;
      v33 = 363;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)KeyRecursive);
    if ( v40[0] != &v41 )
      operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
    return KeyRecursive;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v26 = *(const unsigned __int16 **)(a2 + 40);
    v27 = *(const unsigned __int16 **)(a2 + 8);
    if ( v26 == *(const unsigned __int16 **)(a2 + 48) )
    {
      v28 = Csl::OfflineHive::DeleteKeyRecursive(this, v27);
      KeyRecursive = v28;
      if ( (int)(v28 + 0x80000000) < 0 || v28 == -2147024894 )
        return 0;
      v29 = 391;
    }
    else
    {
      v30 = Csl::OfflineHive::DeleteValue(this, v27, v26);
      KeyRecursive = v30;
      if ( (int)(v30 + 0x80000000) < 0 || v30 == -2147024894 )
        return 0;
      v29 = 402;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)KeyRecursive);
    return KeyRecursive;
  }
  if ( v5 != 1 )
  {
    v6 = 494;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
             (const char *)0x32);
  }
  if ( (unsigned int)(*(_DWORD *)(a2 + 112) - 1) > 1 )
  {
    v6 = 484;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
             (const char *)0x32);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v9 = *(_QWORD *)(a2 + 40);
  v10 = *(_QWORD *)(a2 + 8);
  v36 = si128;
  v37 = -1;
  MultiStringValue = Csl::OfflineHive::GetMultiStringValue((int)this, v10, v9, (__int64)&v36);
  KeyRecursive = MultiStringValue;
  if ( MultiStringValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A7,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)MultiStringValue);
LABEL_39:
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v36);
    return KeyRecursive;
  }
  v13 = *(_QWORD *)(a2 + 72);
  v14 = *(_QWORD *)(a2 + 80) - v13;
  v39 = -1;
  v35 = v14 >> 1;
  v38 = si128;
  v34 = v13;
  if ( !(unsigned __int8)Csl::StringSplit(&v34, 44, &v38) )
  {
    KeyRecursive = -2147024882;
    v15 = 426;
    v16 = 2147942414LL;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)v16);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v38);
    goto LABEL_39;
  }
  v17 = 0;
  if ( *(_DWORD *)(a2 + 112) == 1 )
  {
    v18 = (void **)v36.m128i_i64[1];
    for ( i = v36.m128i_i64[0]; (void **)i != v18; i += 32 )
    {
      for ( j = v38.m128i_i64[0]; j != v38.m128i_i64[1]; j += 32 )
      {
        if ( CompareStringOrdinal(
               *(LPCWCH *)i,
               (__int64)(*(_QWORD *)(i + 8) - *(_QWORD *)i) >> 1,
               *(LPCWCH *)j,
               (__int64)(*(_QWORD *)(j + 8) - *(_QWORD *)j) >> 1,
               1) == 2 )
        {
          v21 = 0;
          v22 = ((__int64)v18 - i - 32) >> 5;
          if ( v22 )
          {
            do
            {
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
                32 * v21 + i,
                i + 32 * v21 + 32);
              ++v21;
            }
            while ( v21 != v22 );
          }
          v18 -= 4;
          if ( *v18 != v18 + 2 )
            operator delete(*v18, (const struct std::nothrow_t *)&std::nothrow);
          v17 = 1;
        }
      }
      v3 = this;
      v36.m128i_i64[1] = (__int64)v18;
    }
  }
  else
  {
    v23 = v38.m128i_i64[0];
    while ( 2 )
    {
      if ( v23 != v38.m128i_i64[1] )
      {
        for ( k = v36.m128i_i64[0]; k != v36.m128i_i64[1]; k += 32 )
        {
          if ( CompareStringOrdinal(
                 *(LPCWCH *)k,
                 (__int64)(*(_QWORD *)(k + 8) - *(_QWORD *)k) >> 1,
                 *(LPCWCH *)v23,
                 (__int64)(*(_QWORD *)(v23 + 8) - *(_QWORD *)v23) >> 1,
                 1) == 2 )
            goto LABEL_33;
        }
        if ( (unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const &,0>(
                                &v36,
                                v23) )
        {
          v17 = 1;
LABEL_33:
          v23 += 32;
          continue;
        }
        KeyRecursive = -2147024882;
        v15 = 464;
        v16 = 2147942414LL;
        goto LABEL_38;
      }
      break;
    }
  }
  if ( v17 )
  {
    v25 = Csl::OfflineHive::SetMultiStringValue(
            v3,
            *(const unsigned __int16 **)(a2 + 8),
            *(const unsigned __int16 **)(a2 + 40),
            v36.m128i_i64);
    KeyRecursive = v25;
    if ( v25 < 0 )
    {
      v16 = (unsigned int)v25;
      v15 = 478;
      goto LABEL_38;
    }
  }
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v38);
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v36);
  return 0;
}

```

## disassembly

```asm
0x180029264  mov     rax, rsp
0x180029267  mov     [rax+8], rcx
0x18002926b  push    rbp
0x18002926c  push    rbx
0x18002926d  push    rsi
0x18002926e  push    rdi
0x18002926f  push    r12
0x180029271  push    r13
0x180029273  push    r14
0x180029275  push    r15
0x180029277  lea     rbp, [rax-5Fh]
0x18002927b  sub     rsp, 0A8h
0x180029282  mov     r14, rdx
0x180029285  movaps  xmmword ptr [rax-58h], xmm6
0x180029289  mov     edx, [rdx+4]
0x18002928c  mov     r13, rcx
0x18002928f  sub     edx, 1
0x180029292  jz      loc_180029589
0x180029298  sub     edx, 1
0x18002929b  jz      loc_180029513
0x1800292a1  cmp     edx, 1
0x1800292a4  jz      short loc_1800292AD
0x1800292a6  mov     edx, 1EEh
0x1800292ab  jmp     short loc_1800292BD
0x1800292ad  mov     eax, [r14+70h]
0x1800292b1  dec     eax
0x1800292b3  cmp     eax, 1
0x1800292b6  jbe     short loc_1800292D8
0x1800292b8  mov     edx, 1E4h; void *
0x1800292bd  mov     rcx, [rbp+5Fh]; this
0x1800292c1  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800292c8  mov     r9d, 32h ; '2'; char *
0x1800292ce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800292d3  jmp     loc_18002965F
0x1800292d8  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800292e0  lea     r9, [rbp+57h+var_A0]
0x1800292e4  mov     r8, [r14+28h]
0x1800292e8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800292ec  mov     rdx, [r14+8]
0x1800292f0  movdqu  [rbp+57h+var_A0], xmm6
0x1800292f5  mov     [rbp+57h+var_90], rdi
0x1800292f9  call    ?GetMultiStringValue@OfflineHive@Csl@@QEBAJPEBG0AEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; Csl::OfflineHive::GetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1800292fe  xor     r15d, r15d
0x180029301  mov     ebx, eax
0x180029303  test    eax, eax
0x180029305  jns     short loc_180029324
0x180029307  mov     rcx, [rbp+5Fh]; this
0x18002930b  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029312  mov     r9d, eax; char *
0x180029315  mov     edx, 1A7h; void *
0x18002931a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002931f  jmp     loc_1800294EE
0x180029324  mov     rax, [r14+48h]
0x180029328  lea     r8, [rbp+57h+var_88]
0x18002932c  mov     rcx, [r14+50h]
0x180029330  mov     edx, 2Ch ; ','
0x180029335  sub     rcx, rax
0x180029338  mov     [rbp+57h+var_78], rdi
0x18002933c  sar     rcx, 1
0x18002933f  mov     [rbp+57h+var_A8], rcx
0x180029343  lea     rcx, [rbp+57h+var_B0]
0x180029347  movdqu  [rbp+57h+var_88], xmm6
0x18002934c  mov     [rbp+57h+var_B0], rax
0x180029350  call    ?StringSplit@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@GAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@3@@Z; Csl::StringSplit(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,ushort,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180029355  test    al, al
0x180029357  jnz     short loc_18002936B
0x180029359  mov     ebx, 8007000Eh
0x18002935e  mov     edx, 1AAh
0x180029363  mov     r9d, ebx
0x180029366  jmp     loc_1800294D5
0x18002936b  cmp     dword ptr [r14+70h], 1
0x180029370  mov     r12b, r15b
0x180029373  jnz     loc_180029439
0x180029379  mov     rdi, qword ptr [rbp+57h+var_A0]
0x18002937d  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x180029381  cmp     rdi, rbx
0x180029384  jz      loc_1800294AE
0x18002938a  mov     rsi, qword ptr [rbp+57h+var_88]
0x18002938e  cmp     rsi, qword ptr [rbp+57h+var_88+8]
0x180029392  jz      loc_180029428
0x180029398  mov     r9, [rsi+8]
0x18002939c  mov     rdx, [rdi+8]
0x1800293a0  sub     r9, [rsi]
0x1800293a3  sub     rdx, [rdi]
0x1800293a6  mov     r8, [rsi]; lpString2
0x1800293a9  mov     rcx, [rdi]; lpString1
0x1800293ac  sar     r9, 1; cchCount2
0x1800293af  sar     rdx, 1; cchCount1
0x1800293b2  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x1800293ba  call    cs:__imp_CompareStringOrdinal
0x1800293c1  nop     dword ptr [rax+rax+00h]
0x1800293c6  cmp     eax, 2
0x1800293c9  jnz     short loc_18002941F
0x1800293cb  mov     r12, rbx
0x1800293ce  mov     r13, r15
0x1800293d1  sub     r12, rdi
0x1800293d4  sub     r12, 20h ; ' '
0x1800293d8  sar     r12, 5
0x1800293dc  test    r12, r12
0x1800293df  jz      short loc_180029400
0x1800293e1  mov     rax, r13
0x1800293e4  shl     rax, 5
0x1800293e8  lea     rdx, [rax+20h]
0x1800293ec  add     rdx, rdi
0x1800293ef  lea     rcx, [rax+rdi]
0x1800293f3  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800293f8  inc     r13
0x1800293fb  cmp     r13, r12
0x1800293fe  jnz     short loc_1800293E1
0x180029400  sub     rbx, 20h ; ' '
0x180029404  lea     rax, [rbx+10h]
0x180029408  cmp     [rbx], rax
0x18002940b  jz      short loc_18002941C
0x18002940d  mov     rcx, [rbx]; void *
0x180029410  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029417  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002941c  mov     r12b, 1
0x18002941f  add     rsi, 20h ; ' '
0x180029423  jmp     loc_18002938E
0x180029428  mov     r13, [rbp+57h+arg_0]
0x18002942c  add     rdi, 20h ; ' '
0x180029430  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x180029434  jmp     loc_180029381
0x180029439  mov     rbx, qword ptr [rbp+57h+var_88]
0x18002943d  cmp     rbx, qword ptr [rbp+57h+var_88+8]
0x180029441  jz      short loc_1800294AE
0x180029443  mov     rdi, qword ptr [rbp+57h+var_A0]
0x180029447  cmp     rdi, qword ptr [rbp+57h+var_A0+8]
0x18002944b  jz      short loc_180029486
0x18002944d  mov     r9, [rbx+8]
0x180029451  mov     rdx, [rdi+8]
0x180029455  sub     r9, [rbx]
0x180029458  sub     rdx, [rdi]
0x18002945b  mov     r8, [rbx]; lpString2
0x18002945e  mov     rcx, [rdi]; lpString1
0x180029461  sar     r9, 1; cchCount2
0x180029464  sar     rdx, 1; cchCount1
0x180029467  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x18002946f  call    cs:__imp_CompareStringOrdinal
0x180029476  nop     dword ptr [rax+rax+00h]
0x18002947b  cmp     eax, 2
0x18002947e  jz      short loc_180029499
0x180029480  add     rdi, 20h ; ' '
0x180029484  jmp     short loc_180029447
0x180029486  mov     rdx, rbx
0x180029489  lea     rcx, [rbp+57h+var_A0]
0x18002948d  call    ??$emplace_back@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::emplace_back<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180029492  test    al, al
0x180029494  jz      short loc_18002949F
0x180029496  mov     r12b, 1
0x180029499  add     rbx, 20h ; ' '
0x18002949d  jmp     short loc_18002943D
0x18002949f  mov     ebx, 8007000Eh
0x1800294a4  mov     edx, 1D0h
0x1800294a9  mov     r9d, ebx
0x1800294ac  jmp     short loc_1800294D5
0x1800294ae  test    r12b, r12b
0x1800294b1  jz      short loc_1800294FC
0x1800294b3  mov     r8, [r14+28h]
0x1800294b7  lea     r9, [rbp+57h+var_A0]
0x1800294bb  mov     rdx, [r14+8]
0x1800294bf  mov     rcx, r13
0x1800294c2  call    ?SetMultiStringValue@OfflineHive@Csl@@QEAAJPEBG0AEBV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; Csl::OfflineHive::SetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> const &)
0x1800294c7  mov     ebx, eax
0x1800294c9  test    eax, eax
0x1800294cb  jns     short loc_1800294FC
0x1800294cd  mov     r9d, eax; char *
0x1800294d0  mov     edx, 1DEh; void *
0x1800294d5  mov     rcx, [rbp+5Fh]; this
0x1800294d9  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800294e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800294e5  lea     rcx, [rbp+57h+var_88]
0x1800294e9  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x1800294ee  lea     rcx, [rbp+57h+var_A0]
0x1800294f2  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x1800294f7  jmp     loc_1800295FE
0x1800294fc  lea     rcx, [rbp+57h+var_88]
0x180029500  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x180029505  lea     rcx, [rbp+57h+var_A0]
0x180029509  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002950e  jmp     loc_18002965D
0x180029513  mov     r8, [r14+28h]; unsigned __int16 *
0x180029517  mov     rdx, [r14+8]; unsigned __int16 *
0x18002951b  cmp     r8, [r14+30h]
0x18002951f  jnz     short loc_180029560
0x180029521  call    ?DeleteKeyRecursive@OfflineHive@Csl@@QEAAJPEBG@Z; Csl::OfflineHive::DeleteKeyRecursive(ushort const *)
0x180029526  mov     edx, 80000000h
0x18002952b  mov     ebx, eax
0x18002952d  lea     ecx, [rax+rdx]
0x180029530  test    edx, ecx
0x180029532  jnz     loc_18002965D
0x180029538  cmp     eax, 80070002h
0x18002953d  jz      loc_18002965D
0x180029543  mov     edx, 187h; void *
0x180029548  mov     rcx, [rbp+5Fh]; this
0x18002954c  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029553  mov     r9d, ebx; char *
0x180029556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002955b  jmp     loc_1800295FE
0x180029560  call    ?DeleteValue@OfflineHive@Csl@@QEAAJQEBG0@Z; Csl::OfflineHive::DeleteValue(ushort const * const,ushort const * const)
0x180029565  mov     edx, 80000000h
0x18002956a  mov     ebx, eax
0x18002956c  lea     ecx, [rax+rdx]
0x18002956f  test    edx, ecx
0x180029571  jnz     loc_18002965D
0x180029577  cmp     eax, 80070002h
0x18002957c  jz      loc_18002965D
0x180029582  mov     edx, 192h
0x180029587  jmp     short loc_180029548
0x180029589  mov     rcx, [r14+10h]
0x18002958d  lea     rax, [rbp+57h+var_60]
0x180029591  mov     [rbp+57h+var_70], rax
0x180029595  lea     rdx, [rbp+57h+var_B0]
0x180029599  lea     rax, [rbp+57h+var_60]
0x18002959d  xor     r15d, r15d
0x1800295a0  mov     [rbp+57h+var_68], rax
0x1800295a4  mov     rax, [r14+8]
0x1800295a8  sub     rcx, rax
0x1800295ab  mov     [rbp+57h+var_60], r15w
0x1800295b0  sar     rcx, 1
0x1800295b3  mov     [rbp+57h+var_A8], rcx
0x1800295b7  lea     rcx, [rbp+57h+var_70]; this
0x1800295bb  mov     [rbp+57h+var_B0], rax
0x1800295bf  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800295c4  test    al, al
0x1800295c6  jnz     short loc_180029602
0x1800295c8  mov     ebx, 8007000Eh
0x1800295cd  mov     edx, 16Bh; void *
0x1800295d2  mov     rcx, [rbp+5Fh]; this
0x1800295d6  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800295dd  mov     r9d, ebx; char *
0x1800295e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800295e5  mov     rcx, [rbp+57h+var_70]; void *
0x1800295e9  lea     rax, [rbp+57h+var_60]
0x1800295ed  cmp     rcx, rax
0x1800295f0  jz      short loc_1800295FE
0x1800295f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800295f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800295fe  mov     eax, ebx
0x180029600  jmp     short loc_18002965F
0x180029602  lea     rdx, [rbp+57h+var_70]
0x180029606  mov     rcx, r13; this
0x180029609  call    Container__Manager__Image___anonymous_namespace___CreateKeyRecursive
0x18002960e  mov     ebx, eax
0x180029610  test    eax, eax
0x180029612  jns     short loc_18002961B
0x180029614  mov     edx, 16Eh
0x180029619  jmp     short loc_1800295D2
0x18002961b  mov     eax, [r14+68h]
0x18002961f  lea     r9, [r14+48h]
0x180029623  lea     r8, [r14+28h]
0x180029627  mov     [rsp+20h], eax; unsigned __int8
0x18002962b  lea     rdx, [r14+8]
0x18002962f  mov     rcx, r13; this
0x180029632  call    Container__Manager__Image___anonymous_namespace___SetKeyValueInOfflineHive
0x180029637  mov     ebx, eax
0x180029639  test    eax, eax
0x18002963b  jns     short loc_180029644
0x18002963d  mov     edx, 175h
0x180029642  jmp     short loc_1800295D2
0x180029644  mov     rcx, [rbp+57h+var_70]; void *
0x180029648  lea     rax, [rbp+57h+var_60]
0x18002964c  cmp     rcx, rax
0x18002964f  jz      short loc_18002965D
0x180029651  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029658  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002965d  xor     eax, eax
0x18002965f  movaps  xmm6, [rsp+0E0h+var_58+8]
0x180029667  add     rsp, 0A8h
0x18002966e  pop     r15
0x180029670  pop     r14
0x180029672  pop     r13
0x180029674  pop     r12
0x180029676  pop     rdi
0x180029677  pop     rsi
0x180029678  pop     rbx
0x180029679  pop     rbp
0x18002967a  retn
```

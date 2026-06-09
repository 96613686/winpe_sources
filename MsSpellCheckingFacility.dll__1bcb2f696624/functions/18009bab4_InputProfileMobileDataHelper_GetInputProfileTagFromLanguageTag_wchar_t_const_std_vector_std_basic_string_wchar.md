# InputProfileMobileDataHelper::GetInputProfileTagFromLanguageTag(wchar_t const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x18009bab4`
- end: `0x18009bd1d`
- name: `?GetInputProfileTagFromLanguageTag@InputProfileMobileDataHelper@@YAJPEB_WAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005b860`

## callees

- `0x18001ef5c`
- `0x180032378`
- `0x18003245c`
- `0x180061320`
- `0x180062308`
- `0x1800980e0`
- `0x18009b6f8`
- `0x18009b8a8`
- `0x18009bab4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009bbea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009bc6a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009bbea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009bc6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall InputProfileMobileDataHelper::GetInputProfileTagFromLanguageTag(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdi
  LPCWCH *v7; // rbx
  __int64 v8; // rcx
  LPCWCH *v9; // rax
  __int16 *v10; // rbx
  char v11; // di
  int v12; // r15d
  const WCHAR *v13; // r8
  __m128i si128; // xmm6
  const WCHAR *v16; // r8
  __int64 v17; // rdx
  LPCWCH lpString2[2]; // [rsp+38h] [rbp-80h] BYREF
  int cchCount1[2]; // [rsp+48h] [rbp-70h]
  unsigned __int64 v20; // [rsp+50h] [rbp-68h]
  __m256i v21; // [rsp+58h] [rbp-60h] BYREF

  v4 = a2[1];
  if ( *a2 != v4 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(*a2, v4);
    a2[1] = *a2;
  }
  std::wstring::wstring(lpString2, a1);
  v5 = *(_QWORD *)cchCount1;
  if ( v20 - *(_QWORD *)cchCount1 < 3 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(
      lpString2,
      3);
  }
  else
  {
    v6 = *(_QWORD *)cchCount1 + 3LL;
    *(_QWORD *)cchCount1 += 3LL;
    v7 = lpString2;
    if ( v20 > 7 )
      v7 = (LPCWCH *)lpString2[0];
    memmove_0((char *)v7 + 2 * v5, L"-t-", 6u);
    *((_WORD *)v7 + v6) = 0;
  }
  *(_OWORD *)&v21.m256i_u64[1] = 0;
  v9 = lpString2;
  if ( v20 > 7 )
    v9 = (LPCWCH *)lpString2[0];
  v21.m256i_i64[0] = (__int64)v9;
  v10 = (__int16 *)std::lower_bound_InputProfileMobileDataHelper::_InputProfileTagsTable_const___InputProfileMobileDataHelper::_InputProfileTagsTable__lambda_ca5082866df3ec02d189ab0c15bc4015___(
                     v8,
                     &word_1800CD3D0,
                     &v21);
  if ( v10 == &word_1800CD3D0 )
    goto LABEL_19;
  v11 = 0;
  v12 = cchCount1[0];
  while ( 1 )
  {
    v13 = (const WCHAR *)lpString2;
    if ( v20 > 7 )
      v13 = lpString2[0];
    if ( CompareStringOrdinal(*(LPCWCH *)v10, v12, v13, v12, 1) != 2 )
      break;
    if ( v10 == (__int16 *)&off_1800CC4A0 )
      goto LABEL_21;
    v11 = 1;
    v10 -= 12;
  }
  if ( !v11 )
    goto LABEL_19;
  v10 += 12;
LABEL_21:
  if ( v10 == &word_1800CD3D0 )
  {
LABEL_19:
    std::wstring::_Tidy_deallocate(lpString2);
    return 2147943568LL;
  }
  else
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v16 = (const WCHAR *)lpString2;
      if ( v20 > 7 )
        v16 = lpString2[0];
      if ( CompareStringOrdinal(*(LPCWCH *)v10, v12, v16, v12, 1) != 2 )
        break;
      std::wstring::wstring(&v21, *(_QWORD *)v10);
      v17 = a2[1];
      if ( v17 == a2[2] )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a2, v17, &v21);
      }
      else
      {
        *(_OWORD *)v17 = 0;
        *(_QWORD *)(v17 + 16) = 0;
        *(_QWORD *)(v17 + 24) = 0;
        *(__m256i *)v17 = v21;
        *(__m128i *)&v21.m256i_u64[2] = si128;
        v21.m256i_i16[0] = 0;
        a2[1] += 32LL;
      }
      std::wstring::_Tidy_deallocate(&v21);
      v10 += 12;
    }
    std::wstring::_Tidy_deallocate(lpString2);
    return 0;
  }
}

```

## disassembly

```asm
0x18009bab4  mov     rax, rsp
0x18009bab7  mov     [rax+18h], rbx
0x18009babb  push    rsi
0x18009babc  push    rdi
0x18009babd  push    r12
0x18009babf  push    r14
0x18009bac1  push    r15
0x18009bac3  sub     rsp, 90h
0x18009baca  movaps  xmmword ptr [rax-38h], xmm6
0x18009bace  mov     rax, cs:__security_cookie
0x18009bad5  xor     rax, rsp
0x18009bad8  mov     [rsp+0B8h+var_40], rax
0x18009badd  mov     rsi, rdx
0x18009bae0  mov     rbx, rcx
0x18009bae3  mov     rdx, [rdx+8]
0x18009bae7  cmp     [rsi], rdx
0x18009baea  jz      short loc_18009BAFB
0x18009baec  mov     rcx, [rsi]
0x18009baef  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18009baf4  mov     rax, [rsi]
0x18009baf7  mov     [rsi+8], rax
0x18009bafb  mov     rdx, rbx
0x18009bafe  lea     rcx, [rsp+0B8h+lpString2]
0x18009bb03  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009bb08  nop
0x18009bb09  mov     rcx, qword ptr [rsp+0B8h+cchCount1]
0x18009bb0e  mov     rax, [rsp+0B8h+var_68]
0x18009bb13  sub     rax, rcx
0x18009bb16  mov     edx, 3
0x18009bb1b  cmp     rax, rdx
0x18009bb1e  jb      short loc_18009BB58
0x18009bb20  lea     rdi, [rcx+3]
0x18009bb24  mov     qword ptr [rsp+0B8h+cchCount1], rdi
0x18009bb29  lea     rbx, [rsp+0B8h+lpString2]
0x18009bb2e  cmp     [rsp+0B8h+var_68], 7
0x18009bb34  cmova   rbx, [rsp+0B8h+lpString2]
0x18009bb3a  lea     rcx, [rbx+rcx*2]; void *
0x18009bb3e  lea     r8d, [rdx+3]; Size
0x18009bb42  lea     rdx, aT; "-t-"
0x18009bb49  call    memmove_0
0x18009bb4e  xor     r14d, r14d
0x18009bb51  mov     [rbx+rdi*2], r14w
0x18009bb56  jmp     short loc_18009BB71
0x18009bb58  mov     qword ptr [rsp+0B8h+bIgnoreCase], rdx; __int64
0x18009bb5d  lea     r9, aT; "-t-"
0x18009bb64  lea     rcx, [rsp+0B8h+lpString2]; Src
0x18009bb69  call    ??$_Reallocate_grow_by@V_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64)
0x18009bb6e  xor     r14d, r14d
0x18009bb71  xorps   xmm0, xmm0
0x18009bb74  movdqu  [rsp+0B8h+var_60+8], xmm0
0x18009bb7a  lea     rax, [rsp+0B8h+lpString2]
0x18009bb7f  cmp     [rsp+0B8h+var_68], 7
0x18009bb85  cmova   rax, [rsp+0B8h+lpString2]
0x18009bb8b  mov     qword ptr [rsp+0B8h+var_60], rax
0x18009bb90  lea     r8, [rsp+0B8h+var_60]
0x18009bb95  lea     r12, word_1800CD3D0
0x18009bb9c  mov     rdx, r12
0x18009bb9f  call    std__lower_bound_InputProfileMobileDataHelper___InputProfileTagsTable_const___InputProfileMobileDataHelper___InputProfileTagsTable__lambda_ca5082866df3ec02d189ab0c15bc4015___
0x18009bba4  mov     rbx, rax
0x18009bba7  cmp     rax, r12
0x18009bbaa  jnz     short loc_18009BBC0
0x18009bbac  lea     rcx, [rsp+0B8h+lpString2]
0x18009bbb1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bbb6  mov     eax, 80070490h
0x18009bbbb  jmp     loc_18009BCF2
0x18009bbc0  mov     dil, r14b
0x18009bbc3  mov     r15d, [rsp+0B8h+cchCount1]
0x18009bbc8  lea     r8, [rsp+0B8h+lpString2]
0x18009bbcd  cmp     [rsp+0B8h+var_68], 7
0x18009bbd3  cmova   r8, [rsp+0B8h+lpString2]; lpString2
0x18009bbd9  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x18009bbe1  mov     r9d, r15d; cchCount2
0x18009bbe4  mov     edx, r15d; cchCount1
0x18009bbe7  mov     rcx, [rbx]; lpString1
0x18009bbea  call    cs:__imp_CompareStringOrdinal
0x18009bbf0  cmp     eax, 2
0x18009bbf3  jnz     short loc_18009BC0A
0x18009bbf5  lea     rax, off_1800CC4A0; "af-t-k0-windows-us"
0x18009bbfc  cmp     rbx, rax
0x18009bbff  jz      short loc_18009BC27
0x18009bc01  mov     dil, 1
0x18009bc04  sub     rbx, 18h
0x18009bc08  jmp     short loc_18009BBC8
0x18009bc0a  test    dil, dil
0x18009bc0d  jnz     short loc_18009BC23
0x18009bc0f  lea     rcx, [rsp+0B8h+lpString2]
0x18009bc14  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bc19  mov     eax, 80070490h
0x18009bc1e  jmp     loc_18009BCF2
0x18009bc23  add     rbx, 18h
0x18009bc27  cmp     rbx, r12
0x18009bc2a  jnz     short loc_18009BC40
0x18009bc2c  lea     rcx, [rsp+0B8h+lpString2]
0x18009bc31  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bc36  mov     eax, 80070490h
0x18009bc3b  jmp     loc_18009BCF2
0x18009bc40  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18009bc48  lea     r8, [rsp+0B8h+lpString2]
0x18009bc4d  cmp     [rsp+0B8h+var_68], 7
0x18009bc53  cmova   r8, [rsp+0B8h+lpString2]; lpString2
0x18009bc59  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x18009bc61  mov     r9d, r15d; cchCount2
0x18009bc64  mov     edx, r15d; cchCount1
0x18009bc67  mov     rcx, [rbx]; lpString1
0x18009bc6a  call    cs:__imp_CompareStringOrdinal
0x18009bc70  cmp     eax, 2
0x18009bc73  jnz     short loc_18009BCE0
0x18009bc75  mov     rdx, [rbx]
0x18009bc78  lea     rcx, [rsp+0B8h+var_60]
0x18009bc7d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009bc82  nop
0x18009bc83  mov     rdx, [rsi+8]
0x18009bc87  cmp     rdx, [rsi+10h]
0x18009bc8b  jz      short loc_18009BCBF
0x18009bc8d  xorps   xmm0, xmm0
0x18009bc90  movups  xmmword ptr [rdx], xmm0
0x18009bc93  mov     [rdx+10h], r14
0x18009bc97  mov     [rdx+18h], r14
0x18009bc9b  movups  xmm0, [rsp+0B8h+var_60]
0x18009bca0  movups  xmmword ptr [rdx], xmm0
0x18009bca3  movups  xmm1, [rsp+0B8h+var_50]
0x18009bca8  movups  xmmword ptr [rdx+10h], xmm1
0x18009bcac  movdqu  [rsp+0B8h+var_50], xmm6
0x18009bcb2  mov     word ptr [rsp+0B8h+var_60], r14w
0x18009bcb8  add     qword ptr [rsi+8], 20h ; ' '
0x18009bcbd  jmp     short loc_18009BCCD
0x18009bcbf  lea     r8, [rsp+0B8h+var_60]
0x18009bcc4  mov     rcx, rsi
0x18009bcc7  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18009bccc  nop
0x18009bccd  lea     rcx, [rsp+0B8h+var_60]
0x18009bcd2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bcd7  add     rbx, 18h
0x18009bcdb  jmp     loc_18009BC48
0x18009bce0  lea     rcx, [rsp+0B8h+lpString2]
0x18009bce5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bcea  xor     eax, eax
0x18009bcec  jmp     short loc_18009BCF2
0x18009bcee  mov     eax, [rsp+0B8h+var_88]
0x18009bcf2  mov     rcx, [rsp+0B8h+var_40]
0x18009bcf7  xor     rcx, rsp; StackCookie
0x18009bcfa  call    __security_check_cookie
0x18009bcff  lea     r11, [rsp+0B8h+var_28]
0x18009bd07  mov     rbx, [r11+40h]
0x18009bd0b  movaps  xmm6, xmmword ptr [r11-10h]
0x18009bd10  mov     rsp, r11
0x18009bd13  pop     r15
0x18009bd15  pop     r14
0x18009bd17  pop     r12
0x18009bd19  pop     rdi
0x18009bd1a  pop     rsi
0x18009bd1b  retn
```

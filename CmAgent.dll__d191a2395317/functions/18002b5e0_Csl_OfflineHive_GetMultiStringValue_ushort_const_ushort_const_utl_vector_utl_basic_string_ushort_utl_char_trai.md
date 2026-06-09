# Csl::OfflineHive::GetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)

- ea: `0x18002b5e0`
- end: `0x18002b80d`
- name: `?GetMultiStringValue@OfflineHive@Csl@@QEBAJPEBG0AEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(int, int, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180029264`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180007b4c`
- `0x180009d48`
- `0x18000adb8`
- `0x18000af30`
- `0x18002b5e0`
- `0x18002b814`

## string_xrefs

- `0x18002b628`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b77b`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b7c7`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::GetMultiStringValue(int a1, int a2, int a3, __int64 a4)
{
  int WideStringValueCommon; // eax
  unsigned int v6; // ebx
  const struct std::nothrow_t *v7; // rdx
  void *v8; // rcx
  char *v9; // r14
  char *v10; // rbx
  __int64 v11; // rax
  char *v12; // rsi
  __int64 v13; // r13
  unsigned __int64 v14; // r8
  __int64 v15; // rdi
  __int64 v16; // rsi
  __m128i v17; // kr00_16
  const struct std::nothrow_t *v18; // rdx
  __int64 v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  unsigned int v22; // [rsp+20h] [rbp-49h]
  int v23; // [rsp+30h] [rbp-39h] BYREF
  void *v24; // [rsp+38h] [rbp-31h] BYREF
  __m128i si128; // [rsp+40h] [rbp-29h] BYREF
  __int64 v26; // [rsp+50h] [rbp-19h]
  void *v27; // [rsp+58h] [rbp-11h] BYREF
  char *v28; // [rsp+60h] [rbp-9h]
  _WORD v29[44]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v24 = 0;
  v23 = 0;
  WideStringValueCommon = Csl::OfflineHive::GetWideStringValueCommon(a1, a2, a3, a4, (__int64)&v24, (__int64)&v23);
  v6 = WideStringValueCommon;
  if ( WideStringValueCommon < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)WideStringValueCommon,
      v22);
    v8 = v24;
    if ( v24 )
      goto LABEL_27;
    return v6;
  }
  v9 = (char *)v24;
  v10 = (char *)v24;
  v11 = v23 & 0xFFFFFFFE;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v26 = -1;
  v12 = (char *)v24 + v11;
  v13 = v11 - 2;
  if ( v24 >= (char *)v24 + v11 )
  {
LABEL_25:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x31E,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)0xD,
           v22);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
    if ( v9 )
    {
      v8 = v9;
LABEL_27:
      operator delete(v8, v7);
    }
    return v6;
  }
  while ( *(_WORD *)v10 || v10 != &v9[v13] )
  {
    v29[0] = 0;
    v27 = v29;
    v14 = -1;
    v28 = (char *)v29;
    do
      ++v14;
    while ( *(_WORD *)&v10[2 * v14] );
    if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (__int64)&v27,
            v10,
            v14) )
    {
      v20 = 787;
      goto LABEL_20;
    }
    v15 = v28 - (_BYTE *)v27;
    if ( !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(
                             &si128,
                             &v27) )
    {
      v20 = 793;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)0x8007000ELL,
        v22);
      if ( v27 != v29 )
        operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
      if ( v9 )
        operator delete(v9, v21);
      return 2147942414LL;
    }
    v10 += 2 * (v15 >> 1) + 2;
    if ( v27 != v29 )
      operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 >= v12 )
      goto LABEL_25;
  }
  v16 = v26;
  v17 = si128;
  v26 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(a4);
  *(__m128i *)a4 = v17;
  *(_QWORD *)(a4 + 16) = v16;
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
  if ( v9 )
    operator delete(v9, v18);
  return 0;
}

```

## disassembly

```asm
0x18002b5e0  push    rbp
0x18002b5e2  push    rbx
0x18002b5e3  push    rsi
0x18002b5e4  push    rdi
0x18002b5e5  push    r12
0x18002b5e7  push    r13
0x18002b5e9  push    r14
0x18002b5eb  push    r15
0x18002b5ed  lea     rbp, [rsp-1Fh]
0x18002b5f2  sub     rsp, 88h
0x18002b5f9  lea     rax, [rbp+57h+var_90]
0x18002b5fd  xor     r12d, r12d
0x18002b600  mov     [rsp+0C0h+var_98], rax
0x18002b605  mov     r15, r9
0x18002b608  lea     rax, [rbp+57h+var_88]
0x18002b60c  mov     [rbp+57h+var_88], r12
0x18002b610  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x18002b615  mov     [rbp+57h+var_90], r12d
0x18002b619  call    ?GetWideStringValueCommon@OfflineHive@Csl@@QEBAJQEBG0KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@AEAK@Z; Csl::OfflineHive::GetWideStringValueCommon(ushort const * const,ushort const * const,ulong,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,ulong &)
0x18002b61e  mov     ebx, eax
0x18002b620  test    eax, eax
0x18002b622  jns     short loc_18002B64E
0x18002b624  mov     rcx, [rbp+5Fh]; this
0x18002b628  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b62f  mov     r9d, eax; char *
0x18002b632  mov     edx, 302h; void *
0x18002b637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b63c  mov     rcx, [rbp+57h+var_88]
0x18002b640  test    rcx, rcx
0x18002b643  jz      loc_18002B7F6
0x18002b649  jmp     loc_18002B7F1
0x18002b64e  mov     r14, [rbp+57h+var_88]
0x18002b652  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002b656  mov     eax, [rbp+57h+var_90]
0x18002b659  mov     rbx, r14
0x18002b65c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002b664  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002b668  movdqu  [rbp+57h+var_80], xmm0
0x18002b66d  mov     [rbp+57h+var_70], rcx
0x18002b671  lea     rsi, [rax+r14]
0x18002b675  lea     r13, [rax-2]
0x18002b679  cmp     r14, rsi
0x18002b67c  jnb     loc_18002B7C3
0x18002b682  cmp     [rbx], r12w
0x18002b686  jnz     short loc_18002B695
0x18002b688  lea     rax, [r14+r13]
0x18002b68c  cmp     rbx, rax
0x18002b68f  jz      loc_18002B71E
0x18002b695  lea     rax, [rbp+57h+var_58]
0x18002b699  mov     [rbp+57h+var_58], r12w
0x18002b69e  mov     [rbp+57h+var_68], rax
0x18002b6a2  mov     r8, rcx
0x18002b6a5  lea     rax, [rbp+57h+var_58]
0x18002b6a9  mov     [rbp+57h+var_60], rax
0x18002b6ad  inc     r8
0x18002b6b0  cmp     [rbx+r8*2], r12w
0x18002b6b5  jnz     short loc_18002B6AD
0x18002b6b7  mov     rdx, rbx
0x18002b6ba  lea     rcx, [rbp+57h+var_68]
0x18002b6be  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002b6c3  test    al, al
0x18002b6c5  jz      loc_18002B772
0x18002b6cb  mov     rdi, [rbp+57h+var_60]
0x18002b6cf  lea     rdx, [rbp+57h+var_68]
0x18002b6d3  sub     rdi, [rbp+57h+var_68]
0x18002b6d7  lea     rcx, [rbp+57h+var_80]
0x18002b6db  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_N$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::emplace_back<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18002b6e0  test    al, al
0x18002b6e2  jz      loc_18002B76B
0x18002b6e8  mov     rcx, [rbp+57h+var_68]; void *
0x18002b6ec  lea     rax, [rbp+57h+var_58]
0x18002b6f0  sar     rdi, 1
0x18002b6f3  lea     rbx, [rbx+rdi*2]
0x18002b6f7  add     rbx, 2
0x18002b6fb  cmp     rcx, rax
0x18002b6fe  jz      short loc_18002B70C
0x18002b700  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b707  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b70c  cmp     rbx, rsi
0x18002b70f  jnb     loc_18002B7C3
0x18002b715  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002b719  jmp     loc_18002B682
0x18002b71e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002b726  mov     rsi, [rbp+57h+var_70]
0x18002b72a  mov     rbx, qword ptr [rbp+57h+var_80]
0x18002b72e  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x18002b732  mov     [rbp+57h+var_70], rcx
0x18002b736  mov     rcx, r15
0x18002b739  movdqu  [rbp+57h+var_80], xmm0
0x18002b73e  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002b743  lea     rcx, [rbp+57h+var_80]
0x18002b747  mov     [r15], rbx
0x18002b74a  mov     [r15+8], rdi
0x18002b74e  mov     [r15+10h], rsi
0x18002b752  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002b757  test    r14, r14
0x18002b75a  jz      short loc_18002B764
0x18002b75c  mov     rcx, r14; void *
0x18002b75f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b764  xor     eax, eax
0x18002b766  jmp     loc_18002B7F8
0x18002b76b  mov     edx, 319h
0x18002b770  jmp     short loc_18002B777
0x18002b772  mov     edx, 313h; void *
0x18002b777  mov     rcx, [rbp+5Fh]; this
0x18002b77b  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b782  mov     r9d, 8007000Eh; char *
0x18002b788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b78d  mov     rcx, [rbp+57h+var_68]; void *
0x18002b791  lea     rax, [rbp+57h+var_58]
0x18002b795  cmp     rcx, rax
0x18002b798  jz      short loc_18002B7A6
0x18002b79a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b7a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b7a6  lea     rcx, [rbp+57h+var_80]
0x18002b7aa  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002b7af  test    r14, r14
0x18002b7b2  jz      short loc_18002B7BC
0x18002b7b4  mov     rcx, r14; void *
0x18002b7b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b7bc  mov     eax, 8007000Eh
0x18002b7c1  jmp     short loc_18002B7F8
0x18002b7c3  mov     rcx, [rbp+5Fh]; this
0x18002b7c7  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b7ce  mov     r9d, 0Dh; char *
0x18002b7d4  mov     edx, 31Eh; void *
0x18002b7d9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b7de  lea     rcx, [rbp+57h+var_80]
0x18002b7e2  mov     ebx, eax
0x18002b7e4  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002b7e9  test    r14, r14
0x18002b7ec  jz      short loc_18002B7F6
0x18002b7ee  mov     rcx, r14; void *
0x18002b7f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b7f6  mov     eax, ebx
0x18002b7f8  add     rsp, 88h
0x18002b7ff  pop     r15
0x18002b801  pop     r14
0x18002b803  pop     r13
0x18002b805  pop     r12
0x18002b807  pop     rdi
0x18002b808  pop     rsi
0x18002b809  pop     rbx
0x18002b80a  pop     rbp
0x18002b80b  retn
```

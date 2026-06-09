# Container::Manager::Image::_anonymous_namespace_::RegisterUserHiveInImage

- ea: `0x180029928`
- end: `0x180029ef2`
- name: `Container::Manager::Image::_anonymous_namespace_::RegisterUserHiveInImage`
- size: `1482`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int8 **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027c74`

## callees

- `0x180002534`
- `0x180002c48`
- `0x1800045e4`
- `0x18000af30`
- `0x18000b004`
- `0x18000bb98`
- `0x18000bc38`
- `0x18000bc6c`
- `0x180028fd8`
- `0x180029928`
- `0x18002ab0c`
- `0x18002ac10`
- `0x18002bafc`
- `0x18002bf64`
- `0x1800361a8`

## string_xrefs

- `0x1800299ad`: `Windows\System32\config\SOFTWARE`
- `0x180029be7`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::RegisterUserHiveInImage(
        __int64 *a1,
        unsigned __int8 **a2,
        unsigned __int8 **a3)
{
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdx
  void *v8; // rcx
  int v9; // eax
  int v10; // edi
  void *v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int Key; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  unsigned __int8 *v20; // r8
  unsigned __int8 *v21; // rdx
  __int64 v22; // rax
  size_t v23; // rbx
  unsigned __int8 *v24; // rdi
  int v25; // ebx
  const struct Path *v26; // rdx
  int v27; // esi
  __int64 v28; // rdx
  unsigned int v29; // [rsp+20h] [rbp-79h]
  unsigned int v30; // [rsp+20h] [rbp-79h]
  unsigned int v31; // [rsp+20h] [rbp-79h]
  const wchar_t *v32; // [rsp+30h] [rbp-69h] BYREF
  __int64 v33; // [rsp+38h] [rbp-61h]
  void *v34[2]; // [rsp+40h] [rbp-59h] BYREF
  _WORD v35[8]; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v36[2]; // [rsp+60h] [rbp-39h] BYREF
  _WORD v37[8]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int8 *v38[2]; // [rsp+80h] [rbp-19h] BYREF
  _WORD v39[8]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int8 *v40[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v41; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  int v43; // [rsp+100h] [rbp+67h] BYREF

  v5 = a1[1] - *a1;
  v6 = *a1;
  v34[0] = v35;
  v34[1] = v35;
  v35[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v34,
                           v6,
                           v5 >> 1) )
  {
    v7 = 892;
    goto LABEL_3;
  }
  v33 = 32;
  v32 = L"Windows\\System32\\config\\SOFTWARE";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v34) )
  {
    v7 = 893;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v29);
    v8 = v34[0];
    if ( v34[0] == v35 )
      return 2147942414LL;
LABEL_72:
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  LOBYTE(v32) = 0;
  v33 = 0;
  v9 = Csl::OfflineHive::Open((Csl::OfflineHive *)&v32, (const struct Path *)v34);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v9,
      v29);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    v11 = v34[0];
    if ( v34[0] == v35 )
      return (unsigned int)v10;
LABEL_9:
    operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v10;
  }
  v37[0] = 0;
  v36[0] = v37;
  v40[1] = (unsigned __int8 *)47;
  v36[1] = v37;
  v40[0] = (unsigned __int8 *)L"Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
  if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v36) )
  {
    v13 = 901;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v29);
    goto LABEL_69;
  }
  v14 = a2[1] - *a2;
  v40[0] = *a2;
  v40[1] = (unsigned __int8 *)(v14 >> 1);
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v36) )
  {
    v13 = 902;
    goto LABEL_13;
  }
  LOBYTE(v43) = 0;
  Key = Csl::OfflineHive::CreateKey((Csl::OfflineHive *)&v32, v36[0], (bool *)&v43);
  v10 = Key;
  if ( Key < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x388,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)Key,
      v29);
    goto LABEL_18;
  }
  v39[0] = 0;
  v38[0] = (unsigned __int8 *)v39;
  v40[1] = (unsigned __int8 *)8;
  v38[1] = (unsigned __int8 *)v39;
  v40[0] = (unsigned __int8 *)L"C:\\Users";
  if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v38) )
  {
    v16 = 910;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v29);
LABEL_67:
    if ( (_WORD *)v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_69:
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    v8 = v34[0];
    if ( v34[0] == v35 )
      return 2147942414LL;
    goto LABEL_72;
  }
  v17 = a3[1] - *a3;
  v40[0] = *a3;
  v40[1] = (unsigned __int8 *)(v17 >> 1);
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v38) )
  {
    v16 = 911;
    goto LABEL_24;
  }
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)&v38[0][2 * v18] );
  v10 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"ProfileImagePath", v38[0], 2 * (int)v18 + 2, 2u);
  if ( v10 < 0 )
  {
    v19 = 915;
    goto LABEL_31;
  }
  v43 = 0;
  v10 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"Flags", (const unsigned __int8 *)&v43, 4u, 4u);
  if ( v10 < 0 )
  {
    v19 = 918;
    goto LABEL_31;
  }
  v43 = 0;
  v10 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"State", (const unsigned __int8 *)&v43, 4u, 4u);
  if ( v10 < 0 )
  {
    v19 = 919;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v10,
      v30);
    if ( (_WORD *)v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_18:
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    v11 = v34[0];
    if ( v34[0] == v35 )
      return (unsigned int)v10;
    goto LABEL_9;
  }
  v20 = a2[1];
  v21 = *a2;
  v22 = (v20 - *a2) >> 1;
  *(__m128i *)v40 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v41 = -1;
  v23 = 2 * v22;
  if ( 2 * v22 )
  {
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(v40, 2 * v22) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)0x8007000ELL,
        v30);
      if ( v40[0] != (unsigned __int8 *)-1LL )
        operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_67;
    }
    memset_0(v40[1], 0, v23);
    v24 = v40[0];
    v21 = *a2;
    v25 = LODWORD(v40[0]) + v23;
    v20 = a2[1];
  }
  else
  {
    v24 = v40[0];
    v25 = -1;
  }
  memcpy_0(v24, v21, 2 * ((v20 - v21) >> 1));
  v27 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"Sid", v24, v25 - (int)v24, 3u);
  if ( v27 < 0 )
  {
    v28 = 929;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v27,
      v31);
    if ( v24 != (unsigned __int8 *)-1LL )
      operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
    if ( (_WORD *)v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    if ( v34[0] != v35 )
      operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v27;
  }
  v27 = Csl::DeletePath((LPCWSTR *)v34, v26);
  if ( v27 < 0 )
  {
    v28 = 932;
    goto LABEL_43;
  }
  v27 = Csl::OfflineHive::Save((Csl::OfflineHive *)&v32, (const struct Path *)v34);
  if ( v27 < 0 )
  {
    v28 = 935;
    goto LABEL_43;
  }
  if ( v24 != (unsigned __int8 *)-1LL )
    operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
  if ( (_WORD *)v38[0] != v39 )
    operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v36[0] != v37 )
    operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
  if ( v34[0] != v35 )
    operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180029928  push    rbp
0x18002992a  push    rbx
0x18002992b  push    rsi
0x18002992c  push    rdi
0x18002992d  push    r14
0x18002992f  push    r15
0x180029931  lea     rbp, [rsp-2Fh]
0x180029936  sub     rsp, 0C8h
0x18002993d  mov     rbx, r8
0x180029940  lea     rax, [rbp+57h+var_A0]
0x180029944  mov     r8, [rcx+8]
0x180029948  mov     rsi, rdx
0x18002994b  sub     r8, [rcx]
0x18002994e  xor     r14d, r14d
0x180029951  mov     rdx, [rcx]
0x180029954  lea     rcx, [rbp+57h+var_B0]
0x180029958  mov     [rbp+57h+var_B0], rax
0x18002995c  lea     rax, [rbp+57h+var_A0]
0x180029960  sar     r8, 1
0x180029963  mov     [rbp+57h+var_A8], rax
0x180029967  mov     [rbp+57h+var_A0], r14w
0x18002996c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180029971  test    al, al
0x180029973  jnz     short loc_1800299AD
0x180029975  mov     edx, 37Ch; void *
0x18002997a  mov     rcx, [rbp+5Fh]; this
0x18002997e  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029985  mov     r9d, 8007000Eh; char *
0x18002998b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029990  mov     rcx, [rbp+57h+var_B0]
0x180029994  lea     rax, [rbp+57h+var_A0]
0x180029998  cmp     rcx, rax
0x18002999b  jz      loc_180029EDC
0x1800299a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800299a8  jmp     loc_180029ED7
0x1800299ad  lea     rax, aWindowsSystem3_2; "Windows\\System32\\config\\SOFTWARE"
0x1800299b4  mov     [rbp+57h+var_B8], 20h ; ' '
0x1800299bc  lea     rdx, [rbp+57h+var_C0]
0x1800299c0  mov     [rbp+57h+var_C0], rax
0x1800299c4  lea     rcx, [rbp+57h+var_B0]; this
0x1800299c8  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800299cd  test    al, al
0x1800299cf  jnz     short loc_1800299D8
0x1800299d1  mov     edx, 37Dh
0x1800299d6  jmp     short loc_18002997A
0x1800299d8  lea     rdx, [rbp+57h+var_B0]; struct Path *
0x1800299dc  mov     byte ptr [rbp+57h+var_C0], r14b
0x1800299e0  lea     rcx, [rbp+57h+var_C0]; this
0x1800299e4  mov     [rbp+57h+var_B8], r14
0x1800299e8  call    ?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z; Csl::OfflineHive::Open(Csl::Path const &)
0x1800299ed  mov     edi, eax
0x1800299ef  test    eax, eax
0x1800299f1  jns     short loc_180029A34
0x1800299f3  mov     rcx, [rbp+5Fh]; this
0x1800299f7  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800299fe  mov     r9d, eax; char *
0x180029a01  mov     edx, 381h; void *
0x180029a06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a0b  lea     rcx, [rbp+57h+var_C0]; this
0x180029a0f  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x180029a14  mov     rcx, [rbp+57h+var_B0]; void *
0x180029a18  lea     rax, [rbp+57h+var_A0]
0x180029a1c  cmp     rcx, rax
0x180029a1f  jz      short loc_180029A2D
0x180029a21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029a28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a2d  mov     eax, edi
0x180029a2f  jmp     loc_180029EE1
0x180029a34  lea     rax, [rbp+57h+var_80]
0x180029a38  mov     [rbp+57h+var_80], r14w
0x180029a3d  mov     [rbp+57h+var_90], rax
0x180029a41  lea     rdx, [rbp+57h+var_50]
0x180029a45  lea     rax, [rbp+57h+var_80]
0x180029a49  mov     [rbp+57h+var_50+8], 2Fh ; '/'
0x180029a51  mov     [rbp+57h+var_88], rax
0x180029a55  lea     rcx, [rbp+57h+var_90]; this
0x180029a59  lea     rax, aMicrosoftWindo; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x180029a60  mov     [rbp+57h+var_50], rax
0x180029a64  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180029a69  test    al, al
0x180029a6b  jnz     short loc_180029A94
0x180029a6d  mov     edx, 385h; void *
0x180029a72  mov     rcx, [rbp+5Fh]; this
0x180029a76  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029a7d  mov     r9d, 8007000Eh; char *
0x180029a83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a88  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029a8f  jmp     loc_180029EA9
0x180029a94  mov     rax, [rsi]
0x180029a97  lea     rdx, [rbp+57h+var_50]
0x180029a9b  mov     rcx, [rsi+8]
0x180029a9f  sub     rcx, rax
0x180029aa2  mov     [rbp+57h+var_50], rax
0x180029aa6  sar     rcx, 1
0x180029aa9  mov     [rbp+57h+var_50+8], rcx
0x180029aad  lea     rcx, [rbp+57h+var_90]; this
0x180029ab1  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180029ab6  test    al, al
0x180029ab8  jnz     short loc_180029AC1
0x180029aba  mov     edx, 386h
0x180029abf  jmp     short loc_180029A72
0x180029ac1  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180029ac5  lea     r8, [rbp+57h+arg_0]; bool *
0x180029ac9  lea     rcx, [rbp+57h+var_C0]; this
0x180029acd  mov     byte ptr [rbp+57h+arg_0], r14b
0x180029ad1  call    ?CreateKey@OfflineHive@Csl@@QEAAJQEBGAEA_N@Z; Csl::OfflineHive::CreateKey(ushort const * const,bool &)
0x180029ad6  mov     edi, eax
0x180029ad8  test    eax, eax
0x180029ada  jns     short loc_180029B32
0x180029adc  mov     rcx, [rbp+5Fh]; this
0x180029ae0  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029ae7  mov     r9d, eax; char *
0x180029aea  mov     edx, 388h; void *
0x180029aef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029af4  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029afb  mov     rcx, [rbp+57h+var_90]; void *
0x180029aff  lea     rax, [rbp+57h+var_80]
0x180029b03  cmp     rcx, rax
0x180029b06  jz      short loc_180029B10
0x180029b08  mov     rdx, rbx; struct std::nothrow_t *
0x180029b0b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029b10  lea     rcx, [rbp+57h+var_C0]; this
0x180029b14  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x180029b19  mov     rcx, [rbp+57h+var_B0]
0x180029b1d  lea     rax, [rbp+57h+var_A0]
0x180029b21  cmp     rcx, rax
0x180029b24  jz      loc_180029A2D
0x180029b2a  mov     rdx, rbx
0x180029b2d  jmp     loc_180029A28
0x180029b32  lea     rax, [rbp+57h+var_60]
0x180029b36  mov     [rbp+57h+var_60], r14w
0x180029b3b  mov     [rbp+57h+var_70], rax
0x180029b3f  lea     rdx, [rbp+57h+var_50]
0x180029b43  lea     rax, [rbp+57h+var_60]
0x180029b47  mov     [rbp+57h+var_50+8], 8
0x180029b4f  mov     [rbp+57h+var_68], rax
0x180029b53  lea     rcx, [rbp+57h+var_70]; this
0x180029b57  lea     rax, aCUsers; "C:\\Users"
0x180029b5e  mov     [rbp+57h+var_50], rax
0x180029b62  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180029b67  test    al, al
0x180029b69  jnz     short loc_180029B92
0x180029b6b  mov     edx, 38Eh; void *
0x180029b70  mov     rcx, [rbp+5Fh]; this
0x180029b74  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029b7b  mov     r9d, 8007000Eh; char *
0x180029b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029b86  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029b8d  jmp     loc_180029E94
0x180029b92  mov     rax, [rbx]
0x180029b95  lea     rdx, [rbp+57h+var_50]
0x180029b99  mov     rcx, [rbx+8]
0x180029b9d  sub     rcx, rax
0x180029ba0  mov     [rbp+57h+var_50], rax
0x180029ba4  sar     rcx, 1
0x180029ba7  mov     [rbp+57h+var_50+8], rcx
0x180029bab  lea     rcx, [rbp+57h+var_70]; this
0x180029baf  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180029bb4  test    al, al
0x180029bb6  jnz     short loc_180029BBF
0x180029bb8  mov     edx, 38Fh
0x180029bbd  jmp     short loc_180029B70
0x180029bbf  mov     r9, [rbp+57h+var_70]; unsigned __int8 *
0x180029bc3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180029bc7  mov     rax, r15
0x180029bca  inc     rax
0x180029bcd  cmp     [r9+rax*2], r14w
0x180029bd2  jnz     short loc_180029BCA
0x180029bd4  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180029bd8  lea     eax, ds:2[rax*2]
0x180029bdf  mov     [rsp+0F0h+var_C8], 2; unsigned int
0x180029be7  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180029bee  lea     rcx, [rbp+57h+var_C0]; this
0x180029bf2  mov     [rsp+0F0h+var_D0], eax; int
0x180029bf6  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x180029bfb  mov     edi, eax
0x180029bfd  test    eax, eax
0x180029bff  jns     short loc_180029C3E
0x180029c01  mov     edx, 393h; void *
0x180029c06  mov     rcx, [rbp+5Fh]; this
0x180029c0a  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029c11  mov     r9d, edi; char *
0x180029c14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029c19  mov     rcx, [rbp+57h+var_70]; void *
0x180029c1d  lea     rax, [rbp+57h+var_60]
0x180029c21  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029c28  cmp     rcx, rax
0x180029c2b  jz      loc_180029AFB
0x180029c31  mov     rdx, rbx; struct std::nothrow_t *
0x180029c34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029c39  jmp     loc_180029AFB
0x180029c3e  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180029c42  lea     r9, [rbp+57h+arg_0]; unsigned __int8 *
0x180029c46  mov     ebx, 4
0x180029c4b  mov     [rbp+57h+arg_0], r14d
0x180029c4f  mov     [rsp+0F0h+var_C8], ebx; unsigned int
0x180029c53  lea     r8, aFlags; "Flags"
0x180029c5a  lea     rcx, [rbp+57h+var_C0]; this
0x180029c5e  mov     [rsp+0F0h+var_D0], ebx; unsigned int
0x180029c62  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x180029c67  mov     edi, eax
0x180029c69  test    eax, eax
0x180029c6b  jns     short loc_180029C74
0x180029c6d  mov     edx, 396h
0x180029c72  jmp     short loc_180029C06
0x180029c74  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180029c78  lea     r9, [rbp+57h+arg_0]; unsigned __int8 *
0x180029c7c  mov     [rsp+0F0h+var_C8], ebx; unsigned int
0x180029c80  lea     r8, aState; "State"
0x180029c87  lea     rcx, [rbp+57h+var_C0]; this
0x180029c8b  mov     [rsp+0F0h+var_D0], ebx; int
0x180029c8f  mov     [rbp+57h+arg_0], r14d
0x180029c93  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x180029c98  mov     edi, eax
0x180029c9a  test    eax, eax
0x180029c9c  jns     short loc_180029CA8
0x180029c9e  mov     edx, 397h
0x180029ca3  jmp     loc_180029C06
0x180029ca8  mov     r8, [rsi+8]
0x180029cac  mov     rdx, [rsi]
0x180029caf  mov     rax, r8
0x180029cb2  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180029cba  sub     rax, rdx
0x180029cbd  sar     rax, 1
0x180029cc0  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x180029cc5  mov     [rbp+57h+var_40], r15
0x180029cc9  lea     rbx, [rax+rax]
0x180029ccd  test    rbx, rbx
0x180029cd0  jnz     short loc_180029CDB
0x180029cd2  mov     rdi, [rbp+57h+var_50]
0x180029cd6  dec     rbx
0x180029cd9  jmp     short loc_180029D0B
0x180029cdb  mov     rdx, rbx
0x180029cde  lea     rcx, [rbp+57h+var_50]
0x180029ce2  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180029ce7  test    al, al
0x180029ce9  jz      loc_180029E61
0x180029cef  mov     rcx, [rbp+57h+var_50+8]; void *
0x180029cf3  mov     r8, rbx; Size
0x180029cf6  xor     edx, edx; Val
0x180029cf8  call    memset_0
0x180029cfd  mov     rdi, [rbp+57h+var_50]
0x180029d01  mov     rdx, [rsi]; Src
0x180029d04  add     rbx, rdi
0x180029d07  mov     r8, [rsi+8]
0x180029d0b  sub     r8, rdx
0x180029d0e  mov     rcx, rdi; void *
0x180029d11  sar     r8, 1
0x180029d14  add     r8, r8; Size
0x180029d17  call    memcpy_0
0x180029d1c  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180029d20  lea     r8, aSid; "Sid"
0x180029d27  sub     ebx, edi
0x180029d29  mov     [rsp+0F0h+var_C8], 3; unsigned int
0x180029d31  mov     r9, rdi; unsigned __int8 *
0x180029d34  mov     [rsp+0F0h+var_D0], ebx; int
0x180029d38  lea     rcx, [rbp+57h+var_C0]; this
0x180029d3c  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x180029d41  mov     esi, eax
0x180029d43  test    eax, eax
0x180029d45  jns     short loc_180029DC5
0x180029d47  mov     edx, 3A1h; void *
0x180029d4c  mov     rcx, [rbp+5Fh]; this
0x180029d50  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029d57  mov     r9d, esi; char *
0x180029d5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d5f  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029d66  cmp     rdi, r15
0x180029d69  jz      short loc_180029D76
0x180029d6b  mov     rdx, rbx; struct std::nothrow_t *
0x180029d6e  mov     rcx, rdi; void *
0x180029d71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029d76  mov     rcx, [rbp+57h+var_70]; void *
0x180029d7a  lea     rax, [rbp+57h+var_60]
0x180029d7e  cmp     rcx, rax
0x180029d81  jz      short loc_180029D8B
0x180029d83  mov     rdx, rbx; struct std::nothrow_t *
0x180029d86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029d8b  mov     rcx, [rbp+57h+var_90]; void *
0x180029d8f  lea     rax, [rbp+57h+var_80]
0x180029d93  cmp     rcx, rax
0x180029d96  jz      short loc_180029DA0
0x180029d98  mov     rdx, rbx; struct std::nothrow_t *
0x180029d9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029da0  lea     rcx, [rbp+57h+var_C0]; this
0x180029da4  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x180029da9  mov     rcx, [rbp+57h+var_B0]; void *
0x180029dad  lea     rax, [rbp+57h+var_A0]
0x180029db1  cmp     rcx, rax
0x180029db4  jz      short loc_180029DBE
0x180029db6  mov     rdx, rbx; struct std::nothrow_t *
0x180029db9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029dbe  mov     eax, esi
0x180029dc0  jmp     loc_180029EE1
0x180029dc5  lea     rcx, [rbp+57h+var_B0]; this
0x180029dc9  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x180029dce  mov     esi, eax
0x180029dd0  test    eax, eax
0x180029dd2  jns     short loc_180029DDE
0x180029dd4  mov     edx, 3A4h
  ... truncated ...
```

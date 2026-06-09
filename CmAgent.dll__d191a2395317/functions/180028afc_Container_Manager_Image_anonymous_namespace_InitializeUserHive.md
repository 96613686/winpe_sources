# Container::Manager::Image::_anonymous_namespace_::InitializeUserHive

- ea: `0x180028afc`
- end: `0x180028fd2`
- name: `Container::Manager::Image::_anonymous_namespace_::InitializeUserHive`
- size: `1238`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180027c74`

## callees

- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x1800045e4`
- `0x180007b2c`
- `0x1800091a0`
- `0x18000adb8`
- `0x18000af30`
- `0x18000bb98`
- `0x18000bc6c`
- `0x180028afc`
- `0x180028fd8`
- `0x18002ab0c`
- `0x18002af0c`
- `0x18002bafc`
- `0x18002bbc8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028dfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ed6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028dfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ed6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028bb6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028c7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028bb6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028c7f`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::InitializeUserHive(_QWORD *a1, __int64 *a2)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r14
  int v8; // eax
  unsigned int LastError; // ebx
  const struct std::nothrow_t *v10; // rdx
  const char *v11; // r9
  unsigned int v12; // r15d
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  const char *v18; // r9
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // r8d
  __int64 v24; // rdx
  int v25; // eax
  const struct Path *v26; // rdx
  unsigned int v27; // r8d
  const unsigned __int16 **i; // rbx
  int v29; // eax
  unsigned int v30; // esi
  __int64 v31; // rdx
  const struct std::nothrow_t *v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  int v37; // [rsp+20h] [rbp-50h] BYREF
  __int64 v38; // [rsp+28h] [rbp-48h]
  __m128i si128; // [rsp+30h] [rbp-40h] BYREF
  __int64 v40; // [rsp+40h] [rbp-30h]
  void *v41[2]; // [rsp+48h] [rbp-28h] BYREF
  _WORD v42[12]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+B0h] [rbp+40h] BYREF

  v4 = ((__int64)(a1[1] - *a1) >> 1) + 70;
  v5 = 2 * v4;
  if ( !is_mul_ok(v4, 2u) )
    v5 = -1;
  v6 = (unsigned __int16 *)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v37);
    return LastError;
  }
  memset_0(v6, 0, v5);
  v8 = StringCchPrintfW(
         v7,
         (unsigned int)v4,
         L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)",
         *a1);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x322,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v8,
      v37);
LABEL_35:
    operator delete(v7, v10);
    return LastError;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &SecurityDescriptor, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x329,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
                  v11);
    goto LABEL_33;
  }
  v12 = ((__int64)(a1[1] - *a1) >> 1) + 77;
  v13 = 2LL * v12;
  if ( !is_mul_ok(v12, 2u) )
    v13 = -1;
  v14 = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v37);
LABEL_33:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_35;
  }
  memset_0(v14, 0, v13);
  v16 = StringCchPrintfW(v15, v12, L"D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)", *a1);
  LastError = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x334,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v16,
      v37);
LABEL_32:
    operator delete(v15, v17);
    goto LABEL_33;
  }
  hMem = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, &hMem, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x33B,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
                  v18);
LABEL_30:
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_32;
  }
  v19 = a2[1] - *a2;
  v20 = *a2;
  v41[0] = v42;
  v41[1] = v42;
  v42[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v41,
                           v20,
                           v19 >> 1) )
  {
    v21 = 832;
LABEL_19:
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v37);
    goto LABEL_28;
  }
  si128.m128i_i64[1] = 10;
  si128.m128i_i64[0] = (__int64)L"NTUSER.DAT";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v41) )
  {
    v21 = 833;
    goto LABEL_19;
  }
  LOBYTE(v37) = 0;
  v38 = 0;
  v22 = Csl::OfflineHive::Open((Csl::OfflineHive *)&v37, (const struct Path *)v41);
  LastError = v22;
  if ( v22 < 0 )
  {
    v24 = 836;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v22,
      v37);
LABEL_27:
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v37);
LABEL_28:
    if ( v41[0] != v42 )
      operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_30;
  }
  v22 = Csl::OfflineHive::SetKeySecurity((Csl::OfflineHive *)&v37, 0, v23, SecurityDescriptor);
  LastError = v22;
  if ( v22 < 0 )
  {
    v24 = 841;
    goto LABEL_22;
  }
  v40 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v25 = Csl::OfflineHive::EnumerateSubkeys(&v37, 0, &si128);
  LastError = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v25,
      v37);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
    goto LABEL_27;
  }
  for ( i = (const unsigned __int16 **)si128.m128i_i64[0]; i != (const unsigned __int16 **)si128.m128i_i64[1]; i += 4 )
  {
    v29 = Csl::OfflineHive::SetKeySecurity((Csl::OfflineHive *)&v37, *i, v27, hMem);
    v30 = v29;
    if ( v29 < 0 )
    {
      v31 = 851;
LABEL_45:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v29,
        v37);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
      Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v37);
      if ( v41[0] != v42 )
        operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( hMem )
        LocalFree(hMem);
      operator delete(v15, v32);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      operator delete(v7, v33);
      return v30;
    }
  }
  v29 = Csl::DeletePath((LPCWSTR *)v41, v26);
  v30 = v29;
  if ( v29 < 0 )
  {
    v31 = 855;
    goto LABEL_45;
  }
  v29 = Csl::OfflineHive::Save((Csl::OfflineHive *)&v37, (const struct Path *)v41);
  v30 = v29;
  if ( v29 < 0 )
  {
    v31 = 858;
    goto LABEL_45;
  }
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v37);
  if ( v41[0] != v42 )
    operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hMem )
    LocalFree(hMem);
  operator delete(v15, v35);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  operator delete(v7, v36);
  return 0;
}

```

## disassembly

```asm
0x180028afc  mov     [rsp-28h+arg_8], rbx
0x180028b01  mov     [rsp-28h+arg_18], rsi
0x180028b06  push    rbp
0x180028b07  push    rdi
0x180028b08  push    r12
0x180028b0a  push    r14
0x180028b0c  push    r15
0x180028b0e  mov     rbp, rsp
0x180028b11  sub     rsp, 70h
0x180028b15  mov     rdi, [rcx+8]
0x180028b19  mov     r12, rdx
0x180028b1c  sub     rdi, [rcx]
0x180028b1f  mov     rsi, rcx
0x180028b22  sar     rdi, 1
0x180028b25  mov     eax, 2
0x180028b2a  add     rdi, 46h ; 'F'
0x180028b2e  mov     edi, edi
0x180028b30  mul     rdi
0x180028b33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028b3a  mov     rbx, rax
0x180028b3d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028b44  cmovb   rbx, rax
0x180028b48  mov     rcx, rbx; unsigned __int64
0x180028b4b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028b50  mov     r14, rax
0x180028b53  test    rax, rax
0x180028b56  jz      loc_180028F99
0x180028b5c  mov     r8, rbx; Size
0x180028b5f  xor     edx, edx; Val
0x180028b61  mov     rcx, rax; void *
0x180028b64  call    memset_0
0x180028b69  mov     r9, [rsi]
0x180028b6c  lea     r8, aDPaiAOiciKaSAO; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x180028b73  mov     edx, edi; unsigned __int64
0x180028b75  mov     rcx, r14; unsigned __int16 *
0x180028b78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028b7d  mov     ebx, eax
0x180028b7f  test    eax, eax
0x180028b81  jns     short loc_180028BA0
0x180028b83  mov     rcx, [rbp+28h]; this
0x180028b87  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028b8e  mov     r9d, eax; char *
0x180028b91  mov     edx, 322h; void *
0x180028b96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b9b  jmp     loc_180028E23
0x180028ba0  xor     r9d, r9d; SecurityDescriptorSize
0x180028ba3  mov     [rbp+SecurityDescriptor], 0
0x180028bab  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180028baf  mov     rcx, r14; StringSecurityDescriptor
0x180028bb2  lea     edx, [r9+1]; StringSDRevision
0x180028bb6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180028bbd  nop     dword ptr [rax+rax+00h]
0x180028bc2  test    eax, eax
0x180028bc4  jnz     short loc_180028BE2
0x180028bc6  mov     rcx, [rbp+28h]; this
0x180028bca  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028bd1  mov     edx, 329h; void *
0x180028bd6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028bdb  mov     ebx, eax
0x180028bdd  jmp     loc_180028E0E
0x180028be2  mov     r15, [rsi+8]
0x180028be6  mov     eax, 2
0x180028beb  sub     r15, [rsi]
0x180028bee  sar     r15, 1
0x180028bf1  add     r15, 4Dh ; 'M'
0x180028bf5  mov     r15d, r15d
0x180028bf8  mul     r15
0x180028bfb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028c02  mov     rbx, rax
0x180028c05  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028c0c  cmovb   rbx, rax
0x180028c10  mov     rcx, rbx; unsigned __int64
0x180028c13  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028c18  mov     rdi, rax
0x180028c1b  test    rax, rax
0x180028c1e  jz      loc_180028F77
0x180028c24  mov     r8, rbx; Size
0x180028c27  xor     edx, edx; Val
0x180028c29  mov     rcx, rax; void *
0x180028c2c  call    memset_0
0x180028c31  mov     r9, [rsi]
0x180028c34  lea     r8, aDAiAOiciidKaSA; "D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY"...
0x180028c3b  mov     edx, r15d; unsigned __int64
0x180028c3e  mov     rcx, rdi; unsigned __int16 *
0x180028c41  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028c46  mov     ebx, eax
0x180028c48  test    eax, eax
0x180028c4a  jns     short loc_180028C69
0x180028c4c  mov     rcx, [rbp+28h]; this
0x180028c50  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028c57  mov     r9d, eax; char *
0x180028c5a  mov     edx, 334h; void *
0x180028c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c64  jmp     loc_180028E06
0x180028c69  xor     r9d, r9d; SecurityDescriptorSize
0x180028c6c  mov     [rbp+hMem], 0
0x180028c74  lea     r8, [rbp+hMem]; SecurityDescriptor
0x180028c78  mov     rcx, rdi; StringSecurityDescriptor
0x180028c7b  lea     edx, [r9+1]; StringSDRevision
0x180028c7f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180028c86  nop     dword ptr [rax+rax+00h]
0x180028c8b  test    eax, eax
0x180028c8d  jnz     short loc_180028CAB
0x180028c8f  mov     rcx, [rbp+28h]; this
0x180028c93  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028c9a  mov     edx, 33Bh; void *
0x180028c9f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028ca4  mov     ebx, eax
0x180028ca6  jmp     loc_180028DF1
0x180028cab  mov     r8, [r12+8]
0x180028cb0  lea     rax, [rbp+var_18]
0x180028cb4  sub     r8, [r12]
0x180028cb8  lea     rcx, [rbp+var_28]
0x180028cbc  mov     rdx, [r12]
0x180028cc0  mov     [rbp+var_28], rax
0x180028cc4  lea     rax, [rbp+var_18]
0x180028cc8  mov     [rbp+var_20], rax
0x180028ccc  xor     eax, eax
0x180028cce  sar     r8, 1
0x180028cd1  mov     [rbp+var_18], ax
0x180028cd5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180028cda  test    al, al
0x180028cdc  jnz     short loc_180028CE5
0x180028cde  mov     edx, 340h
0x180028ce3  jmp     short loc_180028D0E
0x180028ce5  lea     rax, aNtuserDat; "NTUSER.DAT"
0x180028cec  mov     qword ptr [rbp+var_40+8], 0Ah
0x180028cf4  lea     rdx, [rbp+var_40]
0x180028cf8  mov     qword ptr [rbp+var_40], rax
0x180028cfc  lea     rcx, [rbp+var_28]; this
0x180028d00  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180028d05  test    al, al
0x180028d07  jnz     short loc_180028D2B
0x180028d09  mov     edx, 341h; void *
0x180028d0e  mov     rcx, [rbp+28h]; this
0x180028d12  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028d19  mov     ebx, 8007000Eh
0x180028d1e  mov     r9d, ebx; char *
0x180028d21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d26  jmp     loc_180028DD8
0x180028d2b  lea     rdx, [rbp+var_28]; struct Path *
0x180028d2f  mov     byte ptr [rbp+var_50], 0
0x180028d33  lea     rcx, [rbp+var_50]; this
0x180028d37  mov     [rbp+var_48], 0
0x180028d3f  call    ?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z; Csl::OfflineHive::Open(Csl::Path const &)
0x180028d44  mov     ebx, eax
0x180028d46  test    eax, eax
0x180028d48  jns     short loc_180028D64
0x180028d4a  mov     edx, 344h; void *
0x180028d4f  mov     rcx, [rbp+28h]; this
0x180028d53  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028d5a  mov     r9d, eax; char *
0x180028d5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d62  jmp     short loc_180028DCF
0x180028d64  mov     r9, [rbp+SecurityDescriptor]; void *
0x180028d68  lea     rcx, [rbp+var_50]; this
0x180028d6c  xor     edx, edx; unsigned __int16 *
0x180028d6e  call    ?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z; Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)
0x180028d73  mov     ebx, eax
0x180028d75  test    eax, eax
0x180028d77  jns     short loc_180028D80
0x180028d79  mov     edx, 349h
0x180028d7e  jmp     short loc_180028D4F
0x180028d80  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180028d88  lea     r8, [rbp+var_40]
0x180028d8c  xor     edx, edx
0x180028d8e  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x180028d96  lea     rcx, [rbp+var_50]
0x180028d9a  movdqu  [rbp+var_40], xmm0
0x180028d9f  call    ?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z; Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)
0x180028da4  mov     ebx, eax
0x180028da6  test    eax, eax
0x180028da8  jns     loc_180028E30
0x180028dae  mov     rcx, [rbp+28h]; this
0x180028db2  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028db9  mov     r9d, eax; char *
0x180028dbc  mov     edx, 34Dh; void *
0x180028dc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028dc6  lea     rcx, [rbp+var_40]
0x180028dca  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x180028dcf  lea     rcx, [rbp+var_50]; this
0x180028dd3  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x180028dd8  mov     rcx, [rbp+var_28]; void *
0x180028ddc  lea     rax, [rbp+var_18]
0x180028de0  cmp     rcx, rax
0x180028de3  jz      short loc_180028DF1
0x180028de5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028dec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028df1  mov     rcx, [rbp+hMem]; hMem
0x180028df5  test    rcx, rcx
0x180028df8  jz      short loc_180028E06
0x180028dfa  call    cs:__imp_LocalFree
0x180028e01  nop     dword ptr [rax+rax+00h]
0x180028e06  mov     rcx, rdi; void *
0x180028e09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028e0e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180028e12  test    rcx, rcx
0x180028e15  jz      short loc_180028E23
0x180028e17  call    cs:__imp_LocalFree
0x180028e1e  nop     dword ptr [rax+rax+00h]
0x180028e23  mov     rcx, r14; void *
0x180028e26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028e2b  jmp     loc_180028FB6
0x180028e30  mov     rbx, qword ptr [rbp+var_40]
0x180028e34  cmp     rbx, qword ptr [rbp+var_40+8]
0x180028e38  jz      short loc_180028E5D
0x180028e3a  mov     r9, [rbp+hMem]; void *
0x180028e3e  lea     rcx, [rbp+var_50]; this
0x180028e42  mov     rdx, [rbx]; unsigned __int16 *
0x180028e45  call    ?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z; Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)
0x180028e4a  mov     esi, eax
0x180028e4c  test    eax, eax
0x180028e4e  js      short loc_180028E56
0x180028e50  add     rbx, 20h ; ' '
0x180028e54  jmp     short loc_180028E34
0x180028e56  mov     edx, 353h
0x180028e5b  jmp     short loc_180028E8F
0x180028e5d  lea     rcx, [rbp+var_28]; this
0x180028e61  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x180028e66  mov     esi, eax
0x180028e68  test    eax, eax
0x180028e6a  jns     short loc_180028E73
0x180028e6c  mov     edx, 357h
0x180028e71  jmp     short loc_180028E8F
0x180028e73  lea     rdx, [rbp+var_28]; struct Path *
0x180028e77  lea     rcx, [rbp+var_50]; this
0x180028e7b  call    ?Save@OfflineHive@Csl@@QEBAJAEBVPath@2@@Z; Csl::OfflineHive::Save(Csl::Path const &)
0x180028e80  mov     esi, eax
0x180028e82  test    eax, eax
0x180028e84  jns     loc_180028F0E
0x180028e8a  mov     edx, 35Ah; void *
0x180028e8f  mov     rcx, [rbp+28h]; this
0x180028e93  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028e9a  mov     r9d, eax; char *
0x180028e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ea2  lea     rcx, [rbp+var_40]
0x180028ea6  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x180028eab  lea     rcx, [rbp+var_50]; this
0x180028eaf  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x180028eb4  mov     rcx, [rbp+var_28]; void *
0x180028eb8  lea     rax, [rbp+var_18]
0x180028ebc  cmp     rcx, rax
0x180028ebf  jz      short loc_180028ECD
0x180028ec1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028ec8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028ecd  mov     rcx, [rbp+hMem]; hMem
0x180028ed1  test    rcx, rcx
0x180028ed4  jz      short loc_180028EE2
0x180028ed6  call    cs:__imp_LocalFree
0x180028edd  nop     dword ptr [rax+rax+00h]
0x180028ee2  mov     rcx, rdi; void *
0x180028ee5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028eea  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180028eee  test    rcx, rcx
0x180028ef1  jz      short loc_180028EFF
0x180028ef3  call    cs:__imp_LocalFree
0x180028efa  nop     dword ptr [rax+rax+00h]
0x180028eff  mov     rcx, r14; void *
0x180028f02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028f07  mov     eax, esi
0x180028f09  jmp     loc_180028FB8
0x180028f0e  lea     rcx, [rbp+var_40]
0x180028f12  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x180028f17  lea     rcx, [rbp+var_50]; this
0x180028f1b  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x180028f20  mov     rcx, [rbp+var_28]; void *
0x180028f24  lea     rax, [rbp+var_18]
0x180028f28  cmp     rcx, rax
0x180028f2b  jz      short loc_180028F39
0x180028f2d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028f34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028f39  mov     rcx, [rbp+hMem]; hMem
0x180028f3d  test    rcx, rcx
0x180028f40  jz      short loc_180028F4E
0x180028f42  call    cs:__imp_LocalFree
0x180028f49  nop     dword ptr [rax+rax+00h]
0x180028f4e  mov     rcx, rdi; void *
0x180028f51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028f56  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180028f5a  test    rcx, rcx
0x180028f5d  jz      short loc_180028F6B
0x180028f5f  call    cs:__imp_LocalFree
0x180028f66  nop     dword ptr [rax+rax+00h]
0x180028f6b  mov     rcx, r14; void *
0x180028f6e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028f73  xor     eax, eax
0x180028f75  jmp     short loc_180028FB8
0x180028f77  mov     rcx, [rbp+28h]; this
0x180028f7b  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028f82  mov     ebx, 8007000Eh
0x180028f87  mov     edx, 32Fh; void *
0x180028f8c  mov     r9d, ebx; char *
0x180028f8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f94  jmp     loc_180028E0E
0x180028f99  mov     rcx, [rbp+28h]; this
0x180028f9d  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028fa4  mov     ebx, 8007000Eh
0x180028fa9  mov     edx, 31Dh; void *
0x180028fae  mov     r9d, ebx; char *
0x180028fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```

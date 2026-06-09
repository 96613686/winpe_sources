# Csl::CopyRegistryKeyToOfflineHive(Csl::RegistryKey &,Csl::OfflineHive &,Csl::Path const &)

- ea: `0x180198f7c`
- end: `0x1801993af`
- name: `?CopyRegistryKeyToOfflineHive@Csl@@YAJAEAVRegistryKey@1@AEAVOfflineHive@1@AEBVPath@1@@Z`
- size: `1075`
- prototype: `int(Csl *__hidden this, struct Csl::RegistryKey *, struct Csl::OfflineHive *, const struct Path *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801993b8`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x18000da88`
- `0x18000dad8`
- `0x180032714`
- `0x180033104`
- `0x1800343f0`
- `0x180198f7c`
- `0x18019a1d8`
- `0x18019a324`
- `0x18019a404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180198fe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019919b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019924a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180199357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019938c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180198fe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019919b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019924a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180199357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019938c`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180199010`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1801990a4`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180199010`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1801990a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180199299`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180199299`

## string_xrefs

- `0x180199036`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x1801990bf`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x1801992ad`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x180198fc7`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x1801990e7`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18019914b`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x1801991ff`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x1801992d0`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x180199375`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::CopyRegistryKeyToOfflineHive(
        Csl *this,
        struct Csl::RegistryKey *a2,
        const unsigned __int16 **a3,
        const struct Path *a4)
{
  __int64 v4; // rcx
  Csl::OfflineHive *v6; // r12
  int v7; // eax
  unsigned int v8; // ebx
  HKEY v10; // rbx
  unsigned int KeySecurity; // eax
  int v12; // edi
  __int64 v13; // rdx
  DWORD v14; // edi
  void *v15; // rax
  void *v16; // r15
  unsigned int v17; // eax
  unsigned int v18; // r8d
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  int v21; // eax
  int v22; // esi
  const struct std::nothrow_t *v23; // rdx
  __int64 v24; // rcx
  void *v25; // rdi
  void *v26; // rcx
  _BYTE *v27; // r14
  char *v28; // rdi
  char *i; // rsi
  int v30; // eax
  unsigned int v31; // r12d
  const struct std::nothrow_t *v32; // rdx
  __int64 v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  const struct std::nothrow_t *v37; // rdx
  __int64 v38; // rcx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-49h]
  int lpcSubKeysa; // [rsp+20h] [rbp-49h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-49h]
  void *v42[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v43; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbSecurityDescriptor; // [rsp+D0h] [rbp+67h] BYREF
  struct Csl::RegistryKey *v46; // [rsp+D8h] [rbp+6Fh]
  HKEY hKey; // [rsp+E0h] [rbp+77h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+E8h] [rbp+7Fh] BYREF

  v46 = a2;
  v4 = *(_QWORD *)this;
  hKey = 0;
  v6 = a2;
  v7 = Csl::OpenRegistryKey(v4, *a3, 131097, &hKey);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)v7,
      lpcSubKeys);
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  v10 = hKey;
  cbSecurityDescriptor = 0;
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
  v12 = KeySecurity;
  if ( KeySecurity == 122 )
  {
    v12 = -2147024774;
  }
  else if ( KeySecurity )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4CE,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
            (const char *)KeySecurity,
            lpcSubKeys);
  }
  if ( v12 != -2147024774 )
  {
    if ( v12 < 0 )
    {
      v13 = 1272;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v12,
        lpcSubKeys);
    }
LABEL_52:
    if ( v10 )
      RegCloseKey(v10);
    return (unsigned int)v12;
  }
  v14 = cbSecurityDescriptor;
  v15 = operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
  {
    v12 = -2147024882;
    v13 = 1276;
    goto LABEL_51;
  }
  memset_0(v15, 0, v14);
  v17 = RegGetKeySecurity(v10, 4u, v16, &cbSecurityDescriptor);
  v12 = v17;
  if ( v17 == 122 )
  {
    v12 = -2147024774;
  }
  else if ( v17 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4CE,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
            (const char *)v17,
            lpcSubKeys);
  }
  if ( v12 < 0 )
  {
    v19 = 1283;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)v12,
      lpcSubKeys);
    operator delete(v16, v20);
    goto LABEL_52;
  }
  v12 = Csl::OfflineHive::SetKeySecurity(v6, *a3, v18, v16);
  if ( v12 < 0 )
  {
    v19 = 1288;
    goto LABEL_19;
  }
  v43 = -1;
  *(__m128i *)v42 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v21 = Csl::RegistryKey::EnumerateValues(&hKey, v42);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)v21,
      lpcSubKeys);
    v25 = v42[0];
    if ( v42[0] == (void *)-1LL )
    {
LABEL_26:
      operator delete(v16, v23);
      if ( v10 )
        RegCloseKey(v10);
      return (unsigned int)v22;
    }
    utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v24, v42[0], ((char *)v42[1] - (char *)v42[0]) >> 6);
    v26 = v25;
LABEL_25:
    operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_26;
  }
  v27 = v42[0];
  v28 = (char *)v42[1];
  for ( i = (char *)v42[0]; i != v28; i += 64 )
  {
    v30 = Csl::OfflineHive::SetValue(
            v6,
            *a3,
            *(const unsigned __int16 **)i,
            *((const unsigned __int8 **)i + 5),
            *((_DWORD *)i + 12) - (unsigned int)*((_QWORD *)i + 5),
            *((_DWORD *)i + 8));
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x515,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v30,
        lpcSubKeysa);
      if ( v27 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v33, v27, (v28 - v27) >> 6);
        operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
      }
      operator delete(v16, v32);
      if ( v10 )
        RegCloseKey(v10);
      return v31;
    }
    v6 = v46;
  }
  ftLastWriteTime = 0;
  v34 = RegQueryInfoKeyW(v10, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
  if ( v34 )
  {
    v22 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4F6,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
            (const char *)v34,
            lpcSubKeysb);
    if ( v22 < 0 )
    {
      v35 = 1306;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v22,
        lpcSubKeysb);
      if ( v27 == (_BYTE *)-1LL )
        goto LABEL_26;
      utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v36, v27, (v28 - v27) >> 6);
      v26 = v27;
      goto LABEL_25;
    }
  }
  v22 = Csl::OfflineHive::SetKeyLastWriteTime(v6, *a3, &ftLastWriteTime);
  if ( v22 < 0 )
  {
    v35 = 1308;
    goto LABEL_41;
  }
  if ( v27 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v38, v27, (v28 - v27) >> 6);
    operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
  }
  operator delete(v16, v37);
  if ( v10 )
    RegCloseKey(v10);
  return 0;
}

```

## disassembly

```asm
0x180198f7c  mov     [rsp-8+arg_8], rdx
0x180198f81  push    rbp
0x180198f82  push    rbx
0x180198f83  push    rsi
0x180198f84  push    rdi
0x180198f85  push    r12
0x180198f87  push    r13
0x180198f89  push    r14
0x180198f8b  push    r15
0x180198f8d  lea     rbp, [rsp-1Fh]
0x180198f92  sub     rsp, 88h
0x180198f99  mov     rcx, [rcx]
0x180198f9c  lea     r9, [rbp+57h+hKey]
0x180198fa0  mov     r13, r8
0x180198fa3  mov     [rbp+57h+hKey], 0
0x180198fab  mov     r12, rdx
0x180198fae  mov     r8d, 20019h
0x180198fb4  mov     rdx, [r13+0]
0x180198fb8  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180198fbd  mov     ebx, eax
0x180198fbf  test    eax, eax
0x180198fc1  jns     short loc_180198FF7
0x180198fc3  mov     rcx, [rbp+5Fh]; this
0x180198fc7  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198fce  mov     r9d, eax; char *
0x180198fd1  mov     edx, 4EBh; void *
0x180198fd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198fdb  mov     rcx, [rbp+57h+hKey]; hKey
0x180198fdf  test    rcx, rcx
0x180198fe2  jz      short loc_180198FF0
0x180198fe4  call    cs:__imp_RegCloseKey
0x180198feb  nop     dword ptr [rax+rax+00h]
0x180198ff0  mov     eax, ebx
0x180198ff2  jmp     loc_18019939A
0x180198ff7  mov     rbx, [rbp+57h+hKey]
0x180198ffb  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180198fff  xor     r8d, r8d; pSecurityDescriptor
0x180199002  mov     [rbp+57h+cbSecurityDescriptor], 0
0x180199009  mov     rcx, rbx; hKey
0x18019900c  lea     edx, [r8+4]; SecurityInformation
0x180199010  call    cs:__imp_RegGetKeySecurity
0x180199017  nop     dword ptr [rax+rax+00h]
0x18019901c  mov     esi, 80070000h
0x180199021  mov     r14d, 4CEh
0x180199027  mov     edi, eax
0x180199029  cmp     eax, 7Ah ; 'z'
0x18019902c  jz      short loc_18019904C
0x18019902e  test    eax, eax
0x180199030  jz      short loc_180199051
0x180199032  mov     rcx, [rbp+5Fh]; this
0x180199036  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019903d  mov     r9d, eax; char *
0x180199040  mov     edx, r14d; void *
0x180199043  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180199048  mov     edi, eax
0x18019904a  jmp     short loc_180199051
0x18019904c  movzx   edi, ax
0x18019904f  or      edi, esi
0x180199051  cmp     edi, 8007007Ah
0x180199057  jz      short loc_18019906B
0x180199059  test    edi, edi
0x18019905b  jns     loc_180199384
0x180199061  mov     edx, 4F8h
0x180199066  jmp     loc_180199371
0x18019906b  mov     edi, [rbp+57h+cbSecurityDescriptor]
0x18019906e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180199075  mov     ecx, edi; unsigned __int64
0x180199077  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019907c  mov     r15, rax
0x18019907f  test    rax, rax
0x180199082  jz      loc_180199367
0x180199088  mov     r8d, edi; Size
0x18019908b  xor     edx, edx; Val
0x18019908d  mov     rcx, rax; void *
0x180199090  call    memset_0
0x180199095  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180199099  mov     r8, r15; pSecurityDescriptor
0x18019909c  mov     edx, 4; SecurityInformation
0x1801990a1  mov     rcx, rbx; hKey
0x1801990a4  call    cs:__imp_RegGetKeySecurity
0x1801990ab  nop     dword ptr [rax+rax+00h]
0x1801990b0  mov     edi, eax
0x1801990b2  cmp     eax, 7Ah ; 'z'
0x1801990b5  jz      short loc_1801990D5
0x1801990b7  test    eax, eax
0x1801990b9  jz      short loc_1801990DA
0x1801990bb  mov     rcx, [rbp+5Fh]; this
0x1801990bf  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801990c6  mov     r9d, eax; char *
0x1801990c9  mov     edx, r14d; void *
0x1801990cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801990d1  mov     edi, eax
0x1801990d3  jmp     short loc_1801990DA
0x1801990d5  movzx   edi, ax
0x1801990d8  or      edi, esi
0x1801990da  test    edi, edi
0x1801990dc  jns     short loc_180199103
0x1801990de  mov     edx, 503h; void *
0x1801990e3  mov     rcx, [rbp+5Fh]; this
0x1801990e7  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801990ee  mov     r9d, edi; char *
0x1801990f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801990f6  mov     rcx, r15; void *
0x1801990f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801990fe  jmp     loc_180199384
0x180199103  mov     rdx, [r13+0]; unsigned __int16 *
0x180199107  mov     r9, r15; void *
0x18019910a  mov     rcx, r12; this
0x18019910d  call    ?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z; Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)
0x180199112  mov     edi, eax
0x180199114  test    eax, eax
0x180199116  jns     short loc_18019911F
0x180199118  mov     edx, 508h
0x18019911d  jmp     short loc_1801990E3
0x18019911f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180199127  lea     rdx, [rbp+57h+var_60]
0x18019912b  lea     rcx, [rbp+57h+hKey]
0x18019912f  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFFh
0x180199137  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18019913c  call    ?EnumerateValues@RegistryKey@Csl@@QEBAJAEAV?$vector@URegistryValue@Csl@@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@@Z; Csl::RegistryKey::EnumerateValues(utl::vector<Csl::RegistryValue,utl::allocator<Csl::RegistryValue>> &)
0x180199141  mov     esi, eax
0x180199143  test    eax, eax
0x180199145  jns     short loc_1801991AE
0x180199147  mov     rcx, [rbp+5Fh]; this
0x18019914b  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180199152  mov     r9d, eax; char *
0x180199155  mov     edx, 50Ch; void *
0x18019915a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019915f  mov     rdi, [rbp+57h+var_60]
0x180199163  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180199167  jz      short loc_18019918B
0x180199169  mov     r8, [rbp+57h+var_60+8]
0x18019916d  mov     rdx, rdi
0x180199170  sub     r8, rdi
0x180199173  sar     r8, 6
0x180199177  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x18019917c  mov     rcx, rdi; void *
0x18019917f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180199186  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019918b  mov     rcx, r15; void *
0x18019918e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180199193  test    rbx, rbx
0x180199196  jz      short loc_1801991A7
0x180199198  mov     rcx, rbx; hKey
0x18019919b  call    cs:__imp_RegCloseKey
0x1801991a2  nop     dword ptr [rax+rax+00h]
0x1801991a7  mov     eax, esi
0x1801991a9  jmp     loc_18019939A
0x1801991ae  mov     r14, [rbp+57h+var_60]
0x1801991b2  xor     ecx, ecx
0x1801991b4  mov     rdi, [rbp+57h+var_60+8]
0x1801991b8  mov     rsi, r14
0x1801991bb  cmp     rsi, rdi
0x1801991be  jz      loc_18019925E
0x1801991c4  mov     ecx, [rsi+30h]
0x1801991c7  mov     r9, [rsi+28h]; unsigned __int8 *
0x1801991cb  mov     eax, [rsi+20h]
0x1801991ce  sub     ecx, r9d
0x1801991d1  mov     r8, [rsi]; unsigned __int16 *
0x1801991d4  mov     rdx, [r13+0]; unsigned __int16 *
0x1801991d8  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], eax; unsigned int
0x1801991dc  mov     dword ptr [rsp+0C0h+lpcSubKeys], ecx; int
0x1801991e0  mov     rcx, r12; this
0x1801991e3  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x1801991e8  xor     ecx, ecx
0x1801991ea  mov     r12d, eax
0x1801991ed  test    eax, eax
0x1801991ef  js      short loc_1801991FB
0x1801991f1  mov     r12, [rbp+57h+arg_8]
0x1801991f5  add     rsi, 40h ; '@'
0x1801991f9  jmp     short loc_1801991BB
0x1801991fb  mov     rcx, [rbp+5Fh]; this
0x1801991ff  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180199206  mov     r9d, r12d; char *
0x180199209  mov     edx, 515h; void *
0x18019920e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199213  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180199217  jz      short loc_18019923A
0x180199219  sub     rdi, r14
0x18019921c  mov     rdx, r14
0x18019921f  sar     rdi, 6
0x180199223  mov     r8, rdi
0x180199226  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x18019922b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180199232  mov     rcx, r14; void *
0x180199235  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019923a  mov     rcx, r15; void *
0x18019923d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180199242  test    rbx, rbx
0x180199245  jz      short loc_180199256
0x180199247  mov     rcx, rbx; hKey
0x18019924a  call    cs:__imp_RegCloseKey
0x180199251  nop     dword ptr [rax+rax+00h]
0x180199256  mov     eax, r12d
0x180199259  jmp     loc_18019939A
0x18019925e  lea     rax, [rbp+57h+ftLastWriteTime]
0x180199262  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rcx
0x180199266  mov     [rsp+0C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18019926b  xor     r9d, r9d; lpReserved
0x18019926e  mov     [rsp+0C0h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x180199273  xor     r8d, r8d; lpcchClass
0x180199276  mov     [rsp+0C0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x18019927b  xor     edx, edx; lpClass
0x18019927d  mov     [rsp+0C0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x180199282  mov     [rsp+0C0h+lpcValues], rcx; lpcValues
0x180199287  mov     [rsp+0C0h+lpcbMaxClassLen], rcx; lpcbMaxClassLen
0x18019928c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x180199291  mov     [rsp+0C0h+lpcSubKeys], rcx; int
0x180199296  mov     rcx, rbx; hKey
0x180199299  call    cs:__imp_RegQueryInfoKeyW
0x1801992a0  nop     dword ptr [rax+rax+00h]
0x1801992a5  test    eax, eax
0x1801992a7  jz      short loc_180199303
0x1801992a9  mov     rcx, [rbp+5Fh]; this
0x1801992ad  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801992b4  mov     r9d, eax; char *
0x1801992b7  mov     edx, 4F6h; void *
0x1801992bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801992c1  mov     esi, eax
0x1801992c3  test    eax, eax
0x1801992c5  jns     short loc_180199303
0x1801992c7  mov     edx, 51Ah; void *
0x1801992cc  mov     rcx, [rbp+5Fh]; this
0x1801992d0  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801992d7  mov     r9d, esi; char *
0x1801992da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801992df  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1801992e3  jz      loc_18019918B
0x1801992e9  sub     rdi, r14
0x1801992ec  mov     rdx, r14
0x1801992ef  sar     rdi, 6
0x1801992f3  mov     r8, rdi
0x1801992f6  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x1801992fb  mov     rcx, r14
0x1801992fe  jmp     loc_18019917F
0x180199303  mov     rdx, [r13+0]; unsigned __int16 *
0x180199307  lea     r8, [rbp+57h+ftLastWriteTime]; struct _FILETIME *
0x18019930b  mov     rcx, r12; this
0x18019930e  call    ?SetKeyLastWriteTime@OfflineHive@Csl@@QEAAJPEBGAEBU_FILETIME@@@Z; Csl::OfflineHive::SetKeyLastWriteTime(ushort const *,_FILETIME const &)
0x180199313  mov     esi, eax
0x180199315  test    eax, eax
0x180199317  jns     short loc_180199320
0x180199319  mov     edx, 51Ch
0x18019931e  jmp     short loc_1801992CC
0x180199320  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180199324  jz      short loc_180199347
0x180199326  sub     rdi, r14
0x180199329  mov     rdx, r14
0x18019932c  sar     rdi, 6
0x180199330  mov     r8, rdi
0x180199333  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x180199338  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019933f  mov     rcx, r14; void *
0x180199342  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180199347  mov     rcx, r15; void *
0x18019934a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019934f  test    rbx, rbx
0x180199352  jz      short loc_180199363
0x180199354  mov     rcx, rbx; hKey
0x180199357  call    cs:__imp_RegCloseKey
0x18019935e  nop     dword ptr [rax+rax+00h]
0x180199363  xor     eax, eax
0x180199365  jmp     short loc_18019939A
0x180199367  mov     edi, 8007000Eh
0x18019936c  mov     edx, 4FCh; void *
0x180199371  mov     rcx, [rbp+5Fh]; this
0x180199375  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019937c  mov     r9d, edi; char *
0x18019937f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199384  test    rbx, rbx
0x180199387  jz      short loc_180199398
0x180199389  mov     rcx, rbx; hKey
0x18019938c  call    cs:__imp_RegCloseKey
0x180199393  nop     dword ptr [rax+rax+00h]
0x180199398  mov     eax, edi
0x18019939a  add     rsp, 88h
0x1801993a1  pop     r15
0x1801993a3  pop     r14
0x1801993a5  pop     r13
0x1801993a7  pop     r12
0x1801993a9  pop     rdi
0x1801993aa  pop     rsi
0x1801993ab  pop     rbx
0x1801993ac  pop     rbp
0x1801993ad  retn
```

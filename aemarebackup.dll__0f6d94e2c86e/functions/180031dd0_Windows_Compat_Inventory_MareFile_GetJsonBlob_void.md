# Windows::Compat::Inventory::MareFile::GetJsonBlob(void)

- ea: `0x180031dd0`
- end: `0x180032373`
- name: `?GetJsonBlob@MareFile@Inventory@Compat@Windows@@UEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1443`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004ea0`
- `0x18000fb60`
- `0x180011fcc`
- `0x1800134b8`
- `0x18001359c`
- `0x180014a48`
- `0x180019354`
- `0x180027d3c`
- `0x1800283e0`
- `0x18002b4b8`
- `0x18002cd04`
- `0x180031848`
- `0x180031910`
- `0x180031dd0`
- `0x18003237c`
- `0x1800327dc`
- `0x180038470`
- `0x180048f6c`
- `0x18004c020`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800320ae`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800321a7`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800320ae`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800321a7`
- `ole32!CoTaskMemFree` at `0x180031f6a`
- `ole32!CoTaskMemFree` at `0x18003204e`
- `ole32!CoTaskMemFree` at `0x180031f6a`
- `ole32!CoTaskMemFree` at `0x18003204e`

## string_xrefs

- `0x180031e80`: `tipV2Reason::aumidWrittenWithoutLink`
- `0x180031e87`: `tipV2Reason::aumidWrittenWithoutLink`
- `0x180031fb7`: `tipV2Reason::linkWrittenWithoutAumid`
- `0x180031fbe`: `tipV2Reason::linkWrittenWithoutAumid`
- `0x180031f04`: `tipV2Reason::linkFileHasNonzeroFarAttrs`
- `0x180031f0b`: `tipV2Reason::linkFileHasNonzeroFarAttrs`
- `0x180031ed4`: `Empty linkpath for AUMID [%ls]`
- `0x180031ee1`: `Windows::Compat::Inventory::MareFile::GetJsonBlob`
- `0x18003201a`: `Windows::Compat::Inventory::MareFile::GetJsonBlob`
- `0x180032246`: `Windows::Compat::Inventory::MareFile::GetJsonBlob`
- `0x18003200d`: `Link without AUMID [%ls]`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall Windows::Compat::Inventory::MareFile::GetJsonBlob(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r12
  __int64 v5; // rax
  unsigned __int64 v6; // rdi
  const char *v7; // rbx
  char v8; // cl
  const char *v9; // rax
  __int64 *v10; // rax
  const wchar_t *v11; // rax
  const char *v12; // rbx
  char v13; // cl
  const char *v14; // rax
  __int64 *v15; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  _QWORD *v17; // rax
  const char *v18; // rbx
  char v19; // cl
  const char *v20; // rax
  __int64 *v21; // rax
  const wchar_t *v22; // rax
  struct _RTL_CRITICAL_SECTION *v23; // rbx
  unsigned __int64 v24; // r14
  wchar_t *v25; // rdx
  unsigned __int64 v26; // r8
  unsigned __int16 *v27; // rax
  __int16 v28; // ax
  __int128 *v29; // rcx
  _QWORD *v30; // rbx
  __int64 v31; // rax
  bool v32; // cf
  __int64 FarAttribute; // rax
  unsigned __int64 v34; // r8
  unsigned __int16 *v35; // rax
  __int16 v36; // ax
  __int128 *v37; // rcx
  unsigned __int16 *v38; // r14
  int v39; // eax
  __int64 v40; // rax
  _WORD *v41; // rax
  unsigned __int16 **v42; // rdx
  _QWORD *v43; // rbx
  __int64 v44; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v47; // [rsp+40h] [rbp-C0h]
  _QWORD *v48; // [rsp+48h] [rbp-B8h]
  _QWORD v49[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v50; // [rsp+70h] [rbp-90h] BYREF
  __int128 v51; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v52[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v53; // [rsp+A8h] [rbp-58h]
  __int128 Src; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v55; // [rsp+C0h] [rbp-40h]
  _OWORD v56[2]; // [rsp+D0h] [rbp-30h] BYREF
  char *v57[4]; // [rsp+F0h] [rbp-10h] BYREF

  v48 = a2;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v47 = 1;
  v4 = *(_QWORD *)(a1 + 24);
  std::wstring::append(a2, L"{");
  v56[0] = 0;
  v56[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v56[0]) = 0;
  v5 = *(_QWORD *)(a1 + 80);
  v6 = -1;
  if ( *(_QWORD *)(a1 + 48) )
  {
    if ( v5 )
    {
      if ( !*(_QWORD *)(a1 + 24) )
      {
LABEL_22:
        std::wstring::operator=(v56, a1 + 64);
        v17 = Windows::Compat::Inventory::MareDataWriter::EscapeSpecialChars(&Src, (wchar_t *)(a1 + 32));
        Windows::Compat::Inventory::MareJsonElement::AppendNameValuePair<unsigned short const *,std::wstring>(
          a2,
          L"aumid",
          (__int64)v17,
          1);
        goto LABEL_47;
      }
      tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>((volatile signed __int32 **)pv);
      v12 = "tipV2Reason::linkFileHasNonzeroFarAttrs";
      v13 = aTipv2reasonLin_0[0];
      if ( aTipv2reasonLin_0[0] )
      {
        v14 = "tipV2Reason::linkFileHasNonzeroFarAttrs";
        do
        {
          ++v14;
          if ( v13 == 58 )
            v12 = v14;
          v13 = *v14;
        }
        while ( *v14 );
      }
      v15 = tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data((__int64 *)pv);
      tip2::details::shared_data<1,0,1>::set_flag_without_lock(*v15 + 8, 2, v12);
    }
    else
    {
      tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>((volatile signed __int32 **)pv);
      v7 = "tipV2Reason::aumidWrittenWithoutLink";
      v8 = aTipv2reasonAum[0];
      if ( aTipv2reasonAum[0] )
      {
        v9 = "tipV2Reason::aumidWrittenWithoutLink";
        do
        {
          ++v9;
          if ( v8 == 58 )
            v7 = v9;
          v8 = *v9;
        }
        while ( *v9 );
      }
      v10 = tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data((__int64 *)pv);
      tip2::details::shared_data<1,0,1>::set_flag_without_lock(*v10 + 8, 0, v7);
      if ( *(_QWORD *)(a1 + 56) <= 7u )
        v11 = (const wchar_t *)(a1 + 32);
      else
        v11 = *(const wchar_t **)(a1 + 32);
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareFile::GetJsonBlob",
        54,
        "Empty linkpath for AUMID [%ls]",
        v11);
    }
    v16 = (struct _RTL_CRITICAL_SECTION *)pv[0];
    if ( pv[0] && _InterlockedExchangeAdd((volatile signed __int32 *)pv[0] + 84, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(v16);
      CoTaskMemFree(v16);
    }
    goto LABEL_22;
  }
  if ( v5 )
  {
    tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>((volatile signed __int32 **)pv);
    v18 = "tipV2Reason::linkWrittenWithoutAumid";
    v19 = aTipv2reasonLin[0];
    if ( aTipv2reasonLin[0] )
    {
      v20 = "tipV2Reason::linkWrittenWithoutAumid";
      do
      {
        ++v20;
        if ( v19 == 58 )
          v18 = v20;
        v19 = *v20;
      }
      while ( *v20 );
    }
    v21 = tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data((__int64 *)pv);
    tip2::details::shared_data<1,0,1>::set_flag_without_lock(*v21 + 8, 1, v18);
    v22 = (const wchar_t *)(a1 + 64);
    if ( *(_QWORD *)(a1 + 88) > 7u )
      v22 = *(const wchar_t **)v22;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::MareFile::GetJsonBlob", 72, "Link without AUMID [%ls]", v22);
    v23 = (struct _RTL_CRITICAL_SECTION *)pv[0];
    if ( pv[0] && !_InterlockedDecrement((volatile signed __int32 *)pv[0] + 84) )
    {
      tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(v23);
      CoTaskMemFree(v23);
    }
  }
  v24 = 43;
  do
  {
    if ( _bittest64(&v4, v24) )
    {
      v25 = (&off_180119078)[3 * v24];
      v50 = 0;
      v51 = 0;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v50, v25, v26);
      v27 = (unsigned __int16 *)&v50;
      if ( *((_QWORD *)&v51 + 1) > 7u )
        v27 = (unsigned __int16 *)v50;
      v28 = _o_tolower(*v27);
      v29 = &v50;
      if ( *((_QWORD *)&v51 + 1) > 7u )
        v29 = (__int128 *)v50;
      *(_WORD *)v29 = v28;
      File::GetFarAttribute(*(_QWORD *)(a1 + 8), &Src, (unsigned int)v24);
      if ( (_QWORD)v55 )
      {
        pv[0] = v49;
        v30 = Windows::Compat::Inventory::MareDataWriter::EscapeSpecialChars(v49, (wchar_t *)&Src);
        v31 = std::wstring::wstring((__int64)v57, (__int64)&v50);
        Windows::Compat::Inventory::MareJsonElement::AppendNameValuePair<std::wstring,std::wstring>(
          a2,
          v31,
          (__int64)v30,
          1);
      }
      std::wstring::~wstring((char **)&Src);
      std::wstring::~wstring((char **)&v50);
    }
    v32 = v24-- == 1;
  }
  while ( !v32 && v24 != 1 );
  FarAttribute = File::GetFarAttribute(*(_QWORD *)(a1 + 8), v57, 1);
  std::wstring::operator=(v56, FarAttribute);
  std::wstring::~wstring(v57);
LABEL_47:
  v50 = 0;
  v51 = 0;
  v34 = -1;
  do
    ++v34;
  while ( off_180119090[v34] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v50, off_180119090, v34);
  v35 = (unsigned __int16 *)&v50;
  if ( *((_QWORD *)&v51 + 1) > 7u )
    v35 = (unsigned __int16 *)v50;
  v36 = _o_tolower(*v35);
  v37 = &v50;
  if ( *((_QWORD *)&v51 + 1) > 7u )
    v37 = (__int128 *)v50;
  *(_WORD *)v37 = v36;
  std::wstring::wstring(v52, 260, 0);
  v38 = (unsigned __int16 *)v52;
  if ( v53 > 7 )
    v38 = v52[0];
  if ( dword_18011AD60
    || (PiiFilter::Initialize((PiiFilter *)&Windows::Compat::Inventory::MareFile::s_pathUnexpander), dword_18011AD60) )
  {
    v39 = PiiFilterExecute(v38);
    if ( (v39 & 0xC0000000) != 0xC0000000 )
      goto LABEL_60;
  }
  else
  {
    v39 = -1073741595;
  }
  AslLogCallPrintf(1, "Windows::Compat::Inventory::MareFile::GetJsonBlob", 100, "PiiFilter::Execute failed [%#x]", v39);
  v40 = File::GetFarAttribute(*(_QWORD *)(a1 + 8), v57, 1);
  std::wstring::operator=(v52, v40);
  std::wstring::~wstring(v57);
LABEL_60:
  if ( v52[2] )
  {
    pv[0] = v57;
    v42 = v52;
    if ( v53 > 7 )
      v42 = (unsigned __int16 **)v52[0];
    Src = 0;
    v55 = 0;
    do
      ++v6;
    while ( *((_WORD *)v42 + v6) );
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, v42, v6);
    v43 = Windows::Compat::Inventory::MareDataWriter::EscapeSpecialChars(v57, (wchar_t *)&Src);
    v44 = std::wstring::wstring((__int64)v49, (__int64)&v50);
    Windows::Compat::Inventory::MareJsonElement::AppendNameValuePair<std::wstring,std::wstring>(
      a2,
      v44,
      (__int64)v43,
      0);
    std::wstring::~wstring((char **)&Src);
    std::wstring::append(a2, L"}");
  }
  else
  {
    a2[2] = 0;
    if ( a2[3] <= 7u )
      v41 = a2;
    else
      v41 = (_WORD *)*a2;
    *v41 = 0;
  }
  std::wstring::~wstring((char **)v52);
  std::wstring::~wstring((char **)&v50);
  std::wstring::~wstring((char **)v56);
  return a2;
}

```

## disassembly

```asm
0x180031dd0  mov     [rsp-8+arg_10], rbx
0x180031dd5  push    rbp
0x180031dd6  push    rsi
0x180031dd7  push    rdi
0x180031dd8  push    r12
0x180031dda  push    r13
0x180031ddc  push    r14
0x180031dde  push    r15
0x180031de0  lea     rbp, [rsp-20h]
0x180031de5  sub     rsp, 120h
0x180031dec  mov     rax, cs:__security_cookie
0x180031df3  xor     rax, rsp
0x180031df6  mov     [rbp+50h+var_40], rax
0x180031dfa  mov     rsi, rdx
0x180031dfd  mov     r15, rcx
0x180031e00  mov     [rsp+150h+var_108], rdx
0x180031e05  mov     [rsp+150h+var_110], 1
0x180031e0d  xorps   xmm0, xmm0
0x180031e10  movups  xmmword ptr [rdx], xmm0
0x180031e13  xor     r13d, r13d
0x180031e16  mov     [rdx+10h], r13
0x180031e1a  mov     qword ptr [rdx+18h], 7
0x180031e22  mov     [rdx], r13w
0x180031e26  mov     [rsp+150h+var_110], 1
0x180031e2e  mov     r12, [rcx+18h]
0x180031e32  lea     rdx, asc_1800F754C; "{"
0x180031e39  mov     rcx, rsi; Src
0x180031e3c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180031e41  xorps   xmm0, xmm0
0x180031e44  movups  [rbp+50h+var_80], xmm0
0x180031e48  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180031e50  movdqu  [rbp+50h+var_70], xmm1
0x180031e55  mov     word ptr [rbp+50h+var_80], r13w
0x180031e5a  lea     r14, [r15+20h]
0x180031e5e  mov     rax, [r15+50h]
0x180031e62  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031e66  cmp     [r14+10h], r13
0x180031e6a  jz      loc_180031FA3
0x180031e70  test    rax, rax
0x180031e73  jnz     short loc_180031EF4
0x180031e75  lea     rcx, [rsp+150h+pv]
0x180031e7a  call    ??$open@V?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>(void)
0x180031e7f  nop
0x180031e80  lea     rbx, aTipv2reasonAum; "tipV2Reason::aumidWrittenWithoutLink"
0x180031e87  mov     cl, byte ptr cs:aTipv2reasonAum; "tipV2Reason::aumidWrittenWithoutLink"
0x180031e8d  test    cl, cl
0x180031e8f  jz      short loc_180031EA5
0x180031e91  mov     rax, rbx
0x180031e94  inc     rax
0x180031e97  cmp     cl, 3Ah ; ':'
0x180031e9a  jnz     short loc_180031E9F
0x180031e9c  mov     rbx, rax
0x180031e9f  mov     cl, [rax]
0x180031ea1  test    cl, cl
0x180031ea3  jnz     short loc_180031E94
0x180031ea5  lea     rcx, [rsp+150h+pv]
0x180031eaa  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data(void)
0x180031eaf  xor     edx, edx
0x180031eb1  mov     rcx, [rax]
0x180031eb4  add     rcx, 8
0x180031eb8  mov     r8, rbx
0x180031ebb  call    ?set_flag_without_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,1>::set_flag_without_lock(ushort,char const *)
0x180031ec0  cmp     qword ptr [r14+18h], 7
0x180031ec5  jbe     short loc_180031ECC
0x180031ec7  mov     rax, [r14]
0x180031eca  jmp     short loc_180031ECF
0x180031ecc  mov     rax, r14
0x180031ecf  mov     [rsp+150h+var_130], rax
0x180031ed4  lea     r9, aEmptyLinkpathF; "Empty linkpath for AUMID [%ls]"
0x180031edb  mov     r8d, 36h ; '6'
0x180031ee1  lea     rdx, aWindowsCompatI_40; "Windows::Compat::Inventory::MareFile::G"...
0x180031ee8  lea     ecx, [r8-35h]
0x180031eec  call    AslLogCallPrintf
0x180031ef1  nop
0x180031ef2  jmp     short loc_180031F47
0x180031ef4  cmp     [r15+18h], r13
0x180031ef8  jz      short loc_180031F70
0x180031efa  lea     rcx, [rsp+150h+pv]
0x180031eff  call    ??$open@V?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>(void)
0x180031f04  lea     rbx, aTipv2reasonLin_0; "tipV2Reason::linkFileHasNonzeroFarAttrs"
0x180031f0b  mov     cl, byte ptr cs:aTipv2reasonLin_0; "tipV2Reason::linkFileHasNonzeroFarAttrs"
0x180031f11  test    cl, cl
0x180031f13  jz      short loc_180031F29
0x180031f15  mov     rax, rbx
0x180031f18  inc     rax
0x180031f1b  cmp     cl, 3Ah ; ':'
0x180031f1e  jnz     short loc_180031F23
0x180031f20  mov     rbx, rax
0x180031f23  mov     cl, [rax]
0x180031f25  test    cl, cl
0x180031f27  jnz     short loc_180031F18
0x180031f29  lea     rcx, [rsp+150h+pv]
0x180031f2e  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data(void)
0x180031f33  mov     edx, 2
0x180031f38  mov     rcx, [rax]
0x180031f3b  add     rcx, 8
0x180031f3f  mov     r8, rbx
0x180031f42  call    ?set_flag_without_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,1>::set_flag_without_lock(ushort,char const *)
0x180031f47  mov     rbx, [rsp+150h+pv]
0x180031f4c  test    rbx, rbx
0x180031f4f  jz      short loc_180031F70
0x180031f51  mov     eax, edi
0x180031f53  lock xadd [rbx+150h], eax
0x180031f5b  add     eax, edi
0x180031f5d  jnz     short loc_180031F70
0x180031f5f  mov     rcx, rbx
0x180031f62  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x180031f67  mov     rcx, rbx; pv
0x180031f6a  call    cs:__imp_CoTaskMemFree
0x180031f70  lea     rdx, [r15+40h]
0x180031f74  lea     rcx, [rbp+50h+var_80]
0x180031f78  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180031f7d  mov     rdx, r14
0x180031f80  lea     rcx, [rbp+50h+Src]; Src
0x180031f84  call    ?EscapeSpecialChars@MareDataWriter@Inventory@Compat@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Windows::Compat::Inventory::MareDataWriter::EscapeSpecialChars(std::wstring const &)
0x180031f89  mov     r9b, 1
0x180031f8c  mov     r8, rax
0x180031f8f  lea     rdx, aAumid; "aumid"
0x180031f96  mov     rcx, rsi; Src
0x180031f99  call    ??$AppendNameValuePair@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@MareJsonElement@Inventory@Compat@Windows@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGV45@_N@Z; Windows::Compat::Inventory::MareJsonElement::AppendNameValuePair<ushort const *,std::wstring>(std::wstring &,ushort const *,std::wstring,bool)
0x180031f9e  jmp     loc_180032165
0x180031fa3  test    rax, rax
0x180031fa6  jz      loc_180032054
0x180031fac  lea     rcx, [rsp+150h+pv]
0x180031fb1  call    ??$open@V?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>>(void)
0x180031fb6  nop
0x180031fb7  lea     rbx, aTipv2reasonLin; "tipV2Reason::linkWrittenWithoutAumid"
0x180031fbe  mov     cl, byte ptr cs:aTipv2reasonLin; "tipV2Reason::linkWrittenWithoutAumid"
0x180031fc4  test    cl, cl
0x180031fc6  jz      short loc_180031FDC
0x180031fc8  mov     rax, rbx
0x180031fcb  inc     rax
0x180031fce  cmp     cl, 3Ah ; ':'
0x180031fd1  jnz     short loc_180031FD6
0x180031fd3  mov     rbx, rax
0x180031fd6  mov     cl, [rax]
0x180031fd8  test    cl, cl
0x180031fda  jnz     short loc_180031FCB
0x180031fdc  lea     rcx, [rsp+150h+pv]
0x180031fe1  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data(void)
0x180031fe6  mov     edx, 1
0x180031feb  mov     rcx, [rax]
0x180031fee  add     rcx, 8
0x180031ff2  mov     r8, rbx
0x180031ff5  call    ?set_flag_without_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,1>::set_flag_without_lock(ushort,char const *)
0x180031ffa  lea     rax, [r15+40h]
0x180031ffe  cmp     qword ptr [rax+18h], 7
0x180032003  jbe     short loc_180032008
0x180032005  mov     rax, [rax]
0x180032008  mov     [rsp+150h+var_130], rax
0x18003200d  lea     r9, aLinkWithoutAum; "Link without AUMID [%ls]"
0x180032014  mov     r8d, 48h ; 'H'
0x18003201a  lea     rdx, aWindowsCompatI_40; "Windows::Compat::Inventory::MareFile::G"...
0x180032021  lea     ecx, [r8-47h]
0x180032025  call    AslLogCallPrintf
0x18003202a  nop
0x18003202b  mov     rbx, [rsp+150h+pv]
0x180032030  test    rbx, rbx
0x180032033  jz      short loc_180032054
0x180032035  mov     eax, edi
0x180032037  lock xadd [rbx+150h], eax
0x18003203f  add     eax, edi
0x180032041  jnz     short loc_180032054
0x180032043  mov     rcx, rbx
0x180032046  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x18003204b  mov     rcx, rbx; pv
0x18003204e  call    cs:__imp_CoTaskMemFree
0x180032054  mov     r14d, 2Bh ; '+'
0x18003205a  bt      r12, r14
0x18003205e  jnb     loc_18003212E
0x180032064  lea     rax, [r14+r14*2]
0x180032068  lea     rdx, off_180119078; "Name"
0x18003206f  mov     rdx, [rdx+rax*8]
0x180032073  xorps   xmm0, xmm0
0x180032076  movups  [rsp+150h+var_E0], xmm0
0x18003207b  xorps   xmm1, xmm1
0x18003207e  movdqu  [rbp+50h+var_D0], xmm1
0x180032083  mov     r8, rdi
0x180032086  inc     r8
0x180032089  cmp     [rdx+r8*2], r13w
0x18003208e  jnz     short loc_180032086
0x180032090  lea     rcx, [rsp+150h+var_E0]
0x180032095  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003209a  nop
0x18003209b  lea     rax, [rsp+150h+var_E0]
0x1800320a0  cmp     qword ptr [rbp+50h+var_D0+8], 7
0x1800320a5  cmova   rax, qword ptr [rsp+150h+var_E0]
0x1800320ab  movzx   ecx, word ptr [rax]
0x1800320ae  call    cs:__imp__o_tolower
0x1800320b4  lea     rcx, [rsp+150h+var_E0]
0x1800320b9  cmp     qword ptr [rbp+50h+var_D0+8], 7
0x1800320be  cmova   rcx, qword ptr [rsp+150h+var_E0]
0x1800320c4  mov     [rcx], ax
0x1800320c7  mov     r8d, r14d
0x1800320ca  lea     rdx, [rbp+50h+Src]
0x1800320ce  mov     rcx, [r15+8]
0x1800320d2  call    ?GetFarAttribute@File@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FILEATTRID@@@Z; File::GetFarAttribute(FILEATTRID)
0x1800320d7  nop
0x1800320d8  cmp     qword ptr [rbp+50h+var_90], r13
0x1800320dc  jz      short loc_18003211A
0x1800320de  lea     rax, [rsp+150h+var_100]
0x1800320e3  mov     [rsp+150h+pv], rax
0x1800320e8  lea     rdx, [rbp+50h+Src]
0x1800320ec  lea     rcx, [rsp+150h+var_100]; Src
0x1800320f1  call    ?EscapeSpecialChars@MareDataWriter@Inventory@Compat@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Windows::Compat::Inventory::MareDataWriter::EscapeSpecialChars(std::wstring const &)
0x1800320f6  mov     rbx, rax
0x1800320f9  lea     rdx, [rsp+150h+var_E0]
0x1800320fe  lea     rcx, [rbp+50h+var_60]
0x180032102  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180032107  nop
0x180032108  mov     r9b, 1
0x18003210b  mov     r8, rbx
0x18003210e  mov     rdx, rax
0x180032111  mov     rcx, rsi; Src
0x180032114  call    ??$AppendNameValuePair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@MareJsonElement@Inventory@Compat@Windows@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@1_N@Z; Windows::Compat::Inventory::MareJsonElement::AppendNameValuePair<std::wstring,std::wstring>(std::wstring &,std::wstring,std::wstring,bool)
0x180032119  nop
0x18003211a  lea     rcx, [rbp+50h+Src]
0x18003211e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032123  nop
0x180032124  lea     rcx, [rsp+150h+var_E0]
0x180032129  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003212e  dec     r14
0x180032131  cmp     r14, 1
0x180032135  ja      loc_18003205A
0x18003213b  mov     r8d, 1
0x180032141  lea     rdx, [rbp+50h+var_60]
0x180032145  mov     rcx, [r15+8]
0x180032149  call    ?GetFarAttribute@File@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FILEATTRID@@@Z; File::GetFarAttribute(FILEATTRID)
0x18003214e  nop
0x18003214f  mov     rdx, rax
0x180032152  lea     rcx, [rbp+50h+var_80]
0x180032156  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003215b  nop
0x18003215c  lea     rcx, [rbp+50h+var_60]
0x180032160  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032165  mov     rdx, cs:off_180119090; "Path"
0x18003216c  xorps   xmm0, xmm0
0x18003216f  movups  [rsp+150h+var_E0], xmm0
0x180032174  xorps   xmm1, xmm1
0x180032177  movdqu  [rbp+50h+var_D0], xmm1
0x18003217c  mov     r8, rdi
0x18003217f  inc     r8
0x180032182  cmp     [rdx+r8*2], r13w
0x180032187  jnz     short loc_18003217F
0x180032189  lea     rcx, [rsp+150h+var_E0]
0x18003218e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180032193  nop
0x180032194  lea     rax, [rsp+150h+var_E0]
0x180032199  cmp     qword ptr [rbp+50h+var_D0+8], 7
0x18003219e  cmova   rax, qword ptr [rsp+150h+var_E0]
0x1800321a4  movzx   ecx, word ptr [rax]
0x1800321a7  call    cs:__imp__o_tolower
0x1800321ad  lea     rcx, [rsp+150h+var_E0]
0x1800321b2  cmp     qword ptr [rbp+50h+var_D0+8], 7
0x1800321b7  cmova   rcx, qword ptr [rsp+150h+var_E0]
0x1800321bd  mov     [rcx], ax
0x1800321c0  xor     r8d, r8d
0x1800321c3  mov     edx, 104h
0x1800321c8  lea     rcx, [rbp+50h+var_C0]
0x1800321cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800321d1  nop
0x1800321d2  lea     rbx, [rbp+50h+var_80]
0x1800321d6  cmp     qword ptr [rbp+50h+var_70+8], 7
0x1800321db  cmova   rbx, qword ptr [rbp+50h+var_80]
0x1800321e0  lea     r14, [rbp+50h+var_C0]
0x1800321e4  cmp     [rbp+50h+var_A8], 7
0x1800321e9  cmova   r14, [rbp+50h+var_C0]
0x1800321ee  cmp     cs:dword_18011AD60, r13d
0x1800321f5  jnz     short loc_180032213
0x1800321f7  lea     rcx, ?s_pathUnexpander@MareFile@Inventory@Compat@Windows@@0VPiiFilter@@A; this
0x1800321fe  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x180032203  cmp     cs:dword_18011AD60, r13d
0x18003220a  jnz     short loc_180032213
0x18003220c  mov     eax, 0C00000E5h
0x180032211  jmp     short loc_180032235
0x180032213  mov     r9, rbx
0x180032216  mov     r8, cs:?s_pathUnexpander@MareFile@Inventory@Compat@Windows@@0VPiiFilter@@A; PiiFilter Windows::Compat::Inventory::MareFile::s_pathUnexpander
0x18003221d  mov     rcx, r14; unsigned __int16 *
0x180032220  call    PiiFilterExecute
0x180032225  mov     r9d, eax
0x180032228  mov     ecx, 0C0000000h
0x18003222d  and     r9d, ecx
0x180032230  cmp     r9d, ecx
0x180032233  jnz     short loc_180032280
0x180032235  mov     dword ptr [rsp+150h+var_130], eax
0x180032239  lea     r9, aPiifilterExecu; "PiiFilter::Execute failed [%#x]"
0x180032240  mov     r8d, 64h ; 'd'
0x180032246  lea     rdx, aWindowsCompatI_40; "Windows::Compat::Inventory::MareFile::G"...
0x18003224d  lea     ecx, [r8-63h]
0x180032251  call    AslLogCallPrintf
0x180032256  mov     r8d, 1
0x18003225c  lea     rdx, [rbp+50h+var_60]
0x180032260  mov     rcx, [r15+8]
0x180032264  call    ?GetFarAttribute@File@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FILEATTRID@@@Z; File::GetFarAttribute(FILEATTRID)
0x180032269  nop
0x18003226a  mov     rdx, rax
0x18003226d  lea     rcx, [rbp+50h+var_C0]
0x180032271  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180032276  nop
0x180032277  lea     rcx, [rbp+50h+var_60]
  ... truncated ...
```

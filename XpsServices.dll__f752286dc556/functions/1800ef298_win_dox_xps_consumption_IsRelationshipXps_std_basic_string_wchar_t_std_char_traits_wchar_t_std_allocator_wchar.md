# win_dox::xps_consumption::IsRelationshipXps(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800ef298`
- end: `0x1800ef65a`
- name: `?IsRelationshipXps@xps_consumption@win_dox@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `962`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eea78`
- `0x1800eec38`
- `0x1800eeefc`
- `0x1800ef0bc`
- `0x180194850`

## callees

- `0x1800be73c`
- `0x1800ef298`
- `0x18010f260`

## string_xrefs

- `0x1800ef361`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail`
- `0x1800ef2c2`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/core-properties`
- `0x1800ef2e6`: `http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/signature`
- `0x1800ef310`: `http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/certificate`
- `0x1800ef33a`: `http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/origin`
- `0x1800ef4af`: `http://schemas.microsoft.com/xps/2005/06/signature-definitions`
- `0x1800ef614`: `http://schemas.openxps.org/oxps/v1.0/signature-definitions`
- `0x1800ef38b`: `http://schemas.microsoft.com/xps/2005/06/discard-control`
- `0x1800ef503`: `http://schemas.openxps.org/oxps/v1.0/discard-control`
- `0x1800ef488`: `http://schemas.microsoft.com/xps/2005/06/documentstructure`
- `0x1800ef5f1`: `http://schemas.openxps.org/oxps/v1.0/documentstructure`
- `0x1800ef3b7`: `http://schemas.microsoft.com/xps/2005/06/printticket`
- `0x1800ef52a`: `http://schemas.openxps.org/oxps/v1.0/printticket`
- `0x1800ef40e`: `http://schemas.microsoft.com/xps/2005/06/required-resource`
- `0x1800ef57b`: `http://schemas.openxps.org/oxps/v1.0/required-resource`
- `0x1800ef43a`: `http://schemas.microsoft.com/xps/2005/06/restricted-font`
- `0x1800ef5a7`: `http://schemas.openxps.org/oxps/v1.0/restricted-font`
- `0x1800ef3e4`: `http://schemas.microsoft.com/xps/2005/06/fixedrepresentation`
- `0x1800ef554`: `http://schemas.openxps.org/oxps/v1.0/fixedrepresentation`
- `0x1800ef4d9`: `http://schemas.microsoft.com/xps/2005/06/storyfragments`
- `0x1800ef63a`: `http://schemas.openxps.org/oxps/v1.0/storyfragments`
- `0x1800ef5ce`: `http://schemas.openxps.org/oxps/v1.0/required-resource`
- `0x1800ef461`: `http://schemas.microsoft.com/xps/2005/06/required-resource`

## pseudocode

```c
char __fastcall win_dox::xps_consumption::IsRelationshipXps(_QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  _QWORD *v8; // rcx
  _QWORD *v9; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  _QWORD *v14; // rcx
  _QWORD *v15; // rcx
  _QWORD *v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  _QWORD *v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  char result; // al

  v1 = a1;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  if ( v1[2] == 85
    && !wmemcmp(
          (const wchar_t *)a1,
          L"http://schemas.openxmlformats.org/package/2006/relationships/metadata/core-properties",
          0x55u) )
  {
    return 1;
  }
  v2 = v1;
  if ( v1[3] > 7u )
    v2 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v2,
                          v1[2],
                          L"http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/signature",
                          88) )
    return 1;
  v3 = v1;
  if ( v1[3] > 7u )
    v3 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v3,
                          v1[2],
                          L"http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/certificate",
                          90) )
    return 1;
  v4 = v1;
  if ( v1[3] > 7u )
    v4 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v4,
                          v1[2],
                          L"http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/origin",
                          85) )
    return 1;
  v5 = v1;
  if ( v1[3] > 7u )
    v5 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v5,
                          v1[2],
                          L"http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail",
                          79) )
    return 1;
  v6 = v1;
  if ( v1[3] > 7u )
    v6 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v6,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/discard-control",
                          56) )
    return 1;
  v7 = v1;
  if ( v1[3] > 7u )
    v7 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v7,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/printticket",
                          52) )
    return 1;
  v8 = v1;
  if ( v1[3] > 7u )
    v8 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v8,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/fixedrepresentation",
                          60) )
    return 1;
  v9 = v1;
  if ( v1[3] > 7u )
    v9 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v9,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/required-resource",
                          58) )
    return 1;
  v10 = v1;
  if ( v1[3] > 7u )
    v10 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v10,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/restricted-font",
                          56) )
    return 1;
  v11 = v1;
  if ( v1[3] > 7u )
    v11 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v11,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/required-resource",
                          58) )
    return 1;
  v12 = v1;
  if ( v1[3] > 7u )
    v12 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v12,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/documentstructure",
                          58) )
    return 1;
  v13 = v1;
  if ( v1[3] > 7u )
    v13 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v13,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/signature-definitions",
                          62) )
    return 1;
  v14 = v1;
  if ( v1[3] > 7u )
    v14 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v14,
                          v1[2],
                          L"http://schemas.microsoft.com/xps/2005/06/storyfragments",
                          55) )
    return 1;
  v15 = v1;
  if ( v1[3] > 7u )
    v15 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v15,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/discard-control",
                          52) )
    return 1;
  v16 = v1;
  if ( v1[3] > 7u )
    v16 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v16,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/printticket",
                          48) )
    return 1;
  v17 = v1;
  if ( v1[3] > 7u )
    v17 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v17,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/fixedrepresentation",
                          56) )
    return 1;
  v18 = v1;
  if ( v1[3] > 7u )
    v18 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v18,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/required-resource",
                          54) )
    return 1;
  v19 = v1;
  if ( v1[3] > 7u )
    v19 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v19,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/restricted-font",
                          52) )
    return 1;
  v20 = v1;
  if ( v1[3] > 7u )
    v20 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v20,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/required-resource",
                          54) )
    return 1;
  v21 = v1;
  if ( v1[3] > 7u )
    v21 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v21,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/documentstructure",
                          54) )
    return 1;
  v22 = v1;
  if ( v1[3] > 7u )
    v22 = (_QWORD *)*v1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v22,
                          v1[2],
                          L"http://schemas.openxps.org/oxps/v1.0/signature-definitions",
                          58) )
    return 1;
  v23 = v1[2];
  if ( v1[3] > 7u )
    v1 = (_QWORD *)*v1;
  result = std::_Traits_equal<std::char_traits<wchar_t>>(
             v1,
             v23,
             L"http://schemas.openxps.org/oxps/v1.0/storyfragments",
             51);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800ef298  push    rbx
0x1800ef29a  push    rbp
0x1800ef29b  push    rsi
0x1800ef29c  push    rdi
0x1800ef29d  push    r14
0x1800ef29f  sub     rsp, 20h
0x1800ef2a3  mov     edi, 7
0x1800ef2a8  mov     rbx, rcx
0x1800ef2ab  cmp     [rcx+18h], rdi
0x1800ef2af  jbe     short loc_1800EF2B4
0x1800ef2b1  mov     rcx, [rcx]; S1
0x1800ef2b4  mov     esi, 55h ; 'U'
0x1800ef2b9  cmp     [rbx+10h], rsi
0x1800ef2bd  jnz     short loc_1800EF2D6
0x1800ef2bf  mov     r8d, esi; N
0x1800ef2c2  lea     rdx, ?gc_CoreProperties@PackageWide@RelationshipTypes@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800ef2c9  call    wmemcmp
0x1800ef2ce  test    eax, eax
0x1800ef2d0  jz      loc_1800EF64D
0x1800ef2d6  mov     rcx, rbx
0x1800ef2d9  cmp     [rbx+18h], rdi
0x1800ef2dd  jbe     short loc_1800EF2E2
0x1800ef2df  mov     rcx, [rbx]
0x1800ef2e2  mov     rdx, [rbx+10h]
0x1800ef2e6  lea     r8, ?gc_DigitalSignature@PackageWide@RelationshipTypes@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800ef2ed  mov     r9d, 58h ; 'X'
0x1800ef2f3  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef2f8  test    al, al
0x1800ef2fa  jnz     loc_1800EF64D
0x1800ef300  mov     rcx, rbx
0x1800ef303  cmp     [rbx+18h], rdi
0x1800ef307  jbe     short loc_1800EF30C
0x1800ef309  mov     rcx, [rbx]
0x1800ef30c  mov     rdx, [rbx+10h]
0x1800ef310  lea     r8, ?gc_DigitalSignatureCertificate@PackageWide@RelationshipTypes@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800ef317  mov     r9d, 5Ah ; 'Z'
0x1800ef31d  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef322  test    al, al
0x1800ef324  jnz     loc_1800EF64D
0x1800ef32a  mov     rcx, rbx
0x1800ef32d  cmp     [rbx+18h], rdi
0x1800ef331  jbe     short loc_1800EF336
0x1800ef333  mov     rcx, [rbx]
0x1800ef336  mov     rdx, [rbx+10h]
0x1800ef33a  lea     r8, ?gc_DigitalSignatureOrigin@PackageWide@RelationshipTypes@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800ef341  mov     r9, rsi
0x1800ef344  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef349  test    al, al
0x1800ef34b  jnz     loc_1800EF64D
0x1800ef351  mov     rcx, rbx
0x1800ef354  cmp     [rbx+18h], rdi
0x1800ef358  jbe     short loc_1800EF35D
0x1800ef35a  mov     rcx, [rbx]
0x1800ef35d  mov     rdx, [rbx+10h]
0x1800ef361  lea     r8, ?gc_Thumbnail@PackageWide@RelationshipTypes@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800ef368  mov     r9d, 4Fh ; 'O'
0x1800ef36e  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef373  test    al, al
0x1800ef375  jnz     loc_1800EF64D
0x1800ef37b  mov     rcx, rbx
0x1800ef37e  cmp     [rbx+18h], rdi
0x1800ef382  jbe     short loc_1800EF387
0x1800ef384  mov     rcx, [rbx]
0x1800ef387  mov     rdx, [rbx+10h]
0x1800ef38b  lea     r8, ?gc_DiscardControl@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef392  mov     esi, 38h ; '8'
0x1800ef397  mov     r9d, esi
0x1800ef39a  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef39f  test    al, al
0x1800ef3a1  jnz     loc_1800EF64D
0x1800ef3a7  mov     rcx, rbx
0x1800ef3aa  cmp     [rbx+18h], rdi
0x1800ef3ae  jbe     short loc_1800EF3B3
0x1800ef3b0  mov     rcx, [rbx]
0x1800ef3b3  mov     rdx, [rbx+10h]
0x1800ef3b7  lea     r8, ?gc_PrintTicket@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef3be  mov     r14d, 34h ; '4'
0x1800ef3c4  mov     r9d, r14d
0x1800ef3c7  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef3cc  test    al, al
0x1800ef3ce  jnz     loc_1800EF64D
0x1800ef3d4  mov     rcx, rbx
0x1800ef3d7  cmp     [rbx+18h], rdi
0x1800ef3db  jbe     short loc_1800EF3E0
0x1800ef3dd  mov     rcx, [rbx]
0x1800ef3e0  mov     rdx, [rbx+10h]
0x1800ef3e4  lea     r8, ?gc_ReachPackageStartPart@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef3eb  mov     r9d, 3Ch ; '<'
0x1800ef3f1  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef3f6  test    al, al
0x1800ef3f8  jnz     loc_1800EF64D
0x1800ef3fe  mov     rcx, rbx
0x1800ef401  cmp     [rbx+18h], rdi
0x1800ef405  jbe     short loc_1800EF40A
0x1800ef407  mov     rcx, [rbx]
0x1800ef40a  mov     rdx, [rbx+10h]
0x1800ef40e  lea     r8, ?gc_RequiredResource@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef415  mov     ebp, 3Ah ; ':'
0x1800ef41a  mov     r9d, ebp
0x1800ef41d  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef422  test    al, al
0x1800ef424  jnz     loc_1800EF64D
0x1800ef42a  mov     rcx, rbx
0x1800ef42d  cmp     [rbx+18h], rdi
0x1800ef431  jbe     short loc_1800EF436
0x1800ef433  mov     rcx, [rbx]
0x1800ef436  mov     rdx, [rbx+10h]
0x1800ef43a  lea     r8, ?gc_RestrictedFont@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef441  mov     r9, rsi
0x1800ef444  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef449  test    al, al
0x1800ef44b  jnz     loc_1800EF64D
0x1800ef451  mov     rcx, rbx
0x1800ef454  cmp     [rbx+18h], rdi
0x1800ef458  jbe     short loc_1800EF45D
0x1800ef45a  mov     rcx, [rbx]
0x1800ef45d  mov     rdx, [rbx+10h]
0x1800ef461  lea     r8, ?gc_ResourceDictionary@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef468  mov     r9, rbp
0x1800ef46b  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef470  test    al, al
0x1800ef472  jnz     loc_1800EF64D
0x1800ef478  mov     rcx, rbx
0x1800ef47b  cmp     [rbx+18h], rdi
0x1800ef47f  jbe     short loc_1800EF484
0x1800ef481  mov     rcx, [rbx]
0x1800ef484  mov     rdx, [rbx+10h]
0x1800ef488  lea     r8, ?gc_DocumentStructure@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef48f  mov     r9, rbp
0x1800ef492  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef497  test    al, al
0x1800ef499  jnz     loc_1800EF64D
0x1800ef49f  mov     rcx, rbx
0x1800ef4a2  cmp     [rbx+18h], rdi
0x1800ef4a6  jbe     short loc_1800EF4AB
0x1800ef4a8  mov     rcx, [rbx]
0x1800ef4ab  mov     rdx, [rbx+10h]
0x1800ef4af  lea     r8, ?gc_SignatureDefinitions@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef4b6  mov     r9d, 3Eh ; '>'
0x1800ef4bc  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef4c1  test    al, al
0x1800ef4c3  jnz     loc_1800EF64D
0x1800ef4c9  mov     rcx, rbx
0x1800ef4cc  cmp     [rbx+18h], rdi
0x1800ef4d0  jbe     short loc_1800EF4D5
0x1800ef4d2  mov     rcx, [rbx]
0x1800ef4d5  mov     rdx, [rbx+10h]
0x1800ef4d9  lea     r8, ?gc_StoryFragments@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800ef4e0  mov     r9d, 37h ; '7'
0x1800ef4e6  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef4eb  test    al, al
0x1800ef4ed  jnz     loc_1800EF64D
0x1800ef4f3  mov     rcx, rbx
0x1800ef4f6  cmp     [rbx+18h], rdi
0x1800ef4fa  jbe     short loc_1800EF4FF
0x1800ef4fc  mov     rcx, [rbx]
0x1800ef4ff  mov     rdx, [rbx+10h]
0x1800ef503  lea     r8, ?gc_DiscardControl@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/di"...
0x1800ef50a  mov     r9, r14
0x1800ef50d  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef512  test    al, al
0x1800ef514  jnz     loc_1800EF64D
0x1800ef51a  mov     rcx, rbx
0x1800ef51d  cmp     [rbx+18h], rdi
0x1800ef521  jbe     short loc_1800EF526
0x1800ef523  mov     rcx, [rbx]
0x1800ef526  mov     rdx, [rbx+10h]
0x1800ef52a  lea     r8, ?gc_PrintTicket@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/pr"...
0x1800ef531  mov     r9d, 30h ; '0'
0x1800ef537  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef53c  test    al, al
0x1800ef53e  jnz     loc_1800EF64D
0x1800ef544  mov     rcx, rbx
0x1800ef547  cmp     [rbx+18h], rdi
0x1800ef54b  jbe     short loc_1800EF550
0x1800ef54d  mov     rcx, [rbx]
0x1800ef550  mov     rdx, [rbx+10h]
0x1800ef554  lea     r8, ?gc_ReachPackageStartPart@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/fi"...
0x1800ef55b  mov     r9, rsi
0x1800ef55e  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef563  test    al, al
0x1800ef565  jnz     loc_1800EF64D
0x1800ef56b  mov     rcx, rbx
0x1800ef56e  cmp     [rbx+18h], rdi
0x1800ef572  jbe     short loc_1800EF577
0x1800ef574  mov     rcx, [rbx]
0x1800ef577  mov     rdx, [rbx+10h]
0x1800ef57b  lea     r8, ?gc_RequiredResource@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/re"...
0x1800ef582  mov     esi, 36h ; '6'
0x1800ef587  mov     r9d, esi
0x1800ef58a  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef58f  test    al, al
0x1800ef591  jnz     loc_1800EF64D
0x1800ef597  mov     rcx, rbx
0x1800ef59a  cmp     [rbx+18h], rdi
0x1800ef59e  jbe     short loc_1800EF5A3
0x1800ef5a0  mov     rcx, [rbx]
0x1800ef5a3  mov     rdx, [rbx+10h]
0x1800ef5a7  lea     r8, ?gc_RestrictedFont@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/re"...
0x1800ef5ae  mov     r9, r14
0x1800ef5b1  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef5b6  test    al, al
0x1800ef5b8  jnz     loc_1800EF64D
0x1800ef5be  mov     rcx, rbx
0x1800ef5c1  cmp     [rbx+18h], rdi
0x1800ef5c5  jbe     short loc_1800EF5CA
0x1800ef5c7  mov     rcx, [rbx]
0x1800ef5ca  mov     rdx, [rbx+10h]
0x1800ef5ce  lea     r8, ?gc_ResourceDictionary@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/re"...
0x1800ef5d5  mov     r9, rsi
0x1800ef5d8  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef5dd  test    al, al
0x1800ef5df  jnz     short loc_1800EF64D
0x1800ef5e1  mov     rcx, rbx
0x1800ef5e4  cmp     [rbx+18h], rdi
0x1800ef5e8  jbe     short loc_1800EF5ED
0x1800ef5ea  mov     rcx, [rbx]
0x1800ef5ed  mov     rdx, [rbx+10h]
0x1800ef5f1  lea     r8, ?gc_DocumentStructure@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/do"...
0x1800ef5f8  mov     r9, rsi
0x1800ef5fb  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef600  test    al, al
0x1800ef602  jnz     short loc_1800EF64D
0x1800ef604  mov     rcx, rbx
0x1800ef607  cmp     [rbx+18h], rdi
0x1800ef60b  jbe     short loc_1800EF610
0x1800ef60d  mov     rcx, [rbx]
0x1800ef610  mov     rdx, [rbx+10h]
0x1800ef614  lea     r8, ?gc_SignatureDefinitions@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/si"...
0x1800ef61b  mov     r9, rbp
0x1800ef61e  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef623  test    al, al
0x1800ef625  jnz     short loc_1800EF64D
0x1800ef627  mov     rdx, [rbx+10h]
0x1800ef62b  cmp     [rbx+18h], rdi
0x1800ef62f  jbe     short loc_1800EF634
0x1800ef631  mov     rbx, [rbx]
0x1800ef634  mov     r9d, 33h ; '3'
0x1800ef63a  lea     r8, ?gc_StoryFragments@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/st"...
0x1800ef641  mov     rcx, rbx
0x1800ef644  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ef649  test    al, al
0x1800ef64b  jz      short loc_1800EF64F
0x1800ef64d  mov     al, 1
0x1800ef64f  add     rsp, 20h
0x1800ef653  pop     r14
0x1800ef655  pop     rdi
0x1800ef656  pop     rsi
0x1800ef657  pop     rbp
0x1800ef658  pop     rbx
0x1800ef659  retn
```

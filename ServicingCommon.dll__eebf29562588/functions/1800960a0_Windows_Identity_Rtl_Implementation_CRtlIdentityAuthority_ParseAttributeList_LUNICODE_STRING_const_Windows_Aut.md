# Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList(_LUNICODE_STRING const *,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>> *,Windows::WCP::Implementation::CAllocationPool &)

- ea: `0x1800960a0`
- end: `0x1800969b7`
- name: `?ParseAttributeList@CRtlIdentityAuthority@Implementation@Rtl@Identity@Windows@@AEAAJPEBU_LUNICODE_STRING@@PEAV?$Auto@U?$Vector@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@@5@AEAVCAllocationPool@2WCP@5@@Z`
- size: `2327`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180093450`
- `0x1800937a0`

## callees

- `0x180002564`
- `0x18001f554`
- `0x18001f5d4`
- `0x18001fd10`
- `0x1800293a0`
- `0x1800661b0`
- `0x180067060`
- `0x180093d30`
- `0x180095cf4`
- `0x1800960a0`

## string_xrefs

- `0x18009630f`: `((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::EndOfStream))`
- `0x18009687f`: `((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::EndOfStream))`
- `0x1800964bf`: `((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Equals))`
- `0x18009682d`: `Pool.Allocate(&TempName)`
- `0x180096856`: `Pool.Allocate(&TempString)`
- `0x1800967f8`: `Pool.Allocate(&TempValue)`

## pseudocode

```c
__int64 __fastcall Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4)
{
  char v4; // r13
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 *v8; // r15
  __int64 v9; // r8
  const char **v10; // rdx
  int NextLexeme; // eax
  const char **v12; // rdx
  __int64 v13; // r8
  __int128 v14; // xmm6
  __int64 v15; // r14
  __int128 v16; // xmm0
  __int64 *v17; // r12
  __int64 v18; // rdi
  __int64 *v19; // rsi
  __int128 v20; // xmm0
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // rax
  __int64 v26; // rcx
  __int128 v27; // xmm0
  __int64 v28; // rax
  __int64 v29; // rcx
  __int128 v30; // xmm1
  __int64 v31; // rax
  __int128 v32; // xmm0
  __int128 v33; // xmm0
  char v34; // al
  __int64 v35; // xmm1_8
  __int64 v36; // xmm2_8
  __int128 v37; // xmm3
  __int128 v38; // xmm0
  __int64 v39; // r14
  int v40; // r15d
  __int128 v41; // xmm1
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 *v44; // r15
  __int64 v45; // r8
  __int64 *v46; // rdx
  __int64 v47; // xmm1_8
  __int128 v48; // xmm3
  __int64 v49; // xmm2_8
  __int64 v50; // rcx
  __int64 *v51; // r8
  bool v52; // zf
  __int64 v53; // rax
  __int64 v54; // rcx
  __int128 v55; // xmm0
  const char *v56; // rax
  const char *v57; // rax
  __int64 *v59; // [rsp+48h] [rbp-C0h] BYREF
  int v60; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v61[3]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v62; // [rsp+70h] [rbp-98h] BYREF
  const char *v63; // [rsp+78h] [rbp-90h] BYREF
  const char *v64; // [rsp+80h] [rbp-88h]
  __int64 v65; // [rsp+88h] [rbp-80h]
  const char *v66; // [rsp+90h] [rbp-78h]
  int v67; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v68[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v69[24]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v70[24]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-20h]
  __int128 v72; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v73; // [rsp+100h] [rbp-8h]
  const char *v74; // [rsp+108h] [rbp+0h]
  __int64 *v75; // [rsp+110h] [rbp+8h]
  __int128 v76; // [rsp+118h] [rbp+10h] BYREF
  __int64 v77; // [rsp+128h] [rbp+20h]
  const char *v78; // [rsp+130h] [rbp+28h]
  _QWORD v79[4]; // [rsp+138h] [rbp+30h] BYREF
  _QWORD v80[4]; // [rsp+158h] [rbp+50h] BYREF
  _QWORD v81[4]; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v82[4]; // [rsp+198h] [rbp+90h] BYREF
  _QWORD v83[4]; // [rsp+1B8h] [rbp+B0h] BYREF
  _QWORD v84[4]; // [rsp+1D8h] [rbp+D0h] BYREF
  int v85; // [rsp+1F8h] [rbp+F0h]
  __int128 v86; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v87; // [rsp+210h] [rbp+108h]
  int v88; // [rsp+218h] [rbp+110h]
  __int128 v89; // [rsp+220h] [rbp+118h] BYREF
  __int64 v90; // [rsp+230h] [rbp+128h]
  _DWORD v91[4]; // [rsp+238h] [rbp+130h] BYREF
  int v92; // [rsp+248h] [rbp+140h] BYREF
  __int128 v93; // [rsp+250h] [rbp+148h] BYREF
  __int64 v94; // [rsp+260h] [rbp+158h]
  char v95; // [rsp+268h] [rbp+160h]
  int *v96; // [rsp+270h] [rbp+168h]
  int v97; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v98; // [rsp+2B0h] [rbp+1A8h]
  __int64 v99; // [rsp+2B8h] [rbp+1B0h]

  v4 = 0;
  v98 = a2[2];
  v5 = *a2 + v98;
  v90 = 0;
  v6 = 0;
  v87 = 0;
  v94 = 0;
  v8 = a3;
  v99 = v5;
  v96 = &v97;
  v71 = a4;
  v75 = a3;
  v91[0] = 0;
  v62 = 0;
  v59 = 0;
  memset(v70, 0, sizeof(v70));
  v88 = 0;
  memset(v69, 0, sizeof(v69));
  v85 = 0;
  v89 = 0;
  v97 = -1;
  v86 = 0;
  v92 = 0;
  v93 = 0;
  v95 = 0;
  v60 = 0;
  memset(v61, 0, sizeof(v61));
  v67 = 0;
  memset(v68, 0, sizeof(v68));
  if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(a4, &v62, a3) )
  {
    v77 = 699;
    *(_QWORD *)&v76 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v10 = (const char **)&v76;
    *((_QWORD *)&v76 + 1) = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v78 = "Pool.Allocate(&NameAttributeValueBuffer)";
    goto LABEL_3;
  }
  if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(a4, &v59, v9) )
  {
    v73 = 700;
    *(_QWORD *)&v72 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v10 = (const char **)&v72;
    *((_QWORD *)&v72 + 1) = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v74 = "Pool.Allocate(&TypeNameAttributeValueBuffer)";
    goto LABEL_3;
  }
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v60);
  if ( NextLexeme < 0 )
    goto LABEL_65;
  if ( v60 != 1 )
  {
    v79[2] = 707;
    v79[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v12 = (const char **)v79;
    v13 = 3221225485LL;
    v79[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v79[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::String";
    goto LABEL_64;
  }
  v14 = *(_OWORD *)&v61[1];
  v15 = v61[0];
  v16 = *(_OWORD *)&v68[8];
  *(_OWORD *)&v68[8] = *(_OWORD *)&v61[1];
  v61[0] = *(_QWORD *)v68;
  *(_OWORD *)&v61[1] = v16;
  *(_QWORD *)v68 = v15;
  v67 = 1;
  v60 = 0;
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v60);
  if ( NextLexeme < 0 )
    goto LABEL_65;
  if ( ((v60 - 2) & 0xFFFFFFFD) != 0 )
  {
    v80[2] = 718;
    v80[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v12 = (const char **)v80;
    v13 = 3221225485LL;
    v80[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v80[3] = "((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityP"
             "arser::CLexeme::EndOfStream))";
    goto LABEL_64;
  }
  v17 = v59;
  v18 = 0;
  if ( v60 == 4 )
  {
    v19 = v62;
    v20 = *(_OWORD *)(v62 + 1);
    v21 = *v62;
    *v62 = v15;
    *(_OWORD *)&v68[8] = v20;
    *(_QWORD *)v68 = v21;
    *(_OWORD *)(v19 + 1) = v14;
    goto LABEL_14;
  }
  if ( v60 != 2 )
    goto LABEL_68;
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v60);
  if ( NextLexeme < 0 )
    goto LABEL_65;
  if ( v60 != 1 )
  {
    v81[2] = 730;
    v81[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v12 = (const char **)v81;
    v81[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v81[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::String";
    goto LABEL_63;
  }
  v27 = *(_OWORD *)(v17 + 1);
  v28 = *v17;
  v19 = v62;
  *v17 = v15;
  *(_OWORD *)(v17 + 1) = v14;
  *(_QWORD *)v68 = v28;
  v29 = *v19;
  v30 = *(_OWORD *)(v19 + 1);
  v31 = v61[0];
  *(_OWORD *)&v68[8] = v27;
  v61[0] = v29;
  v32 = *(_OWORD *)&v61[1];
  *v19 = v31;
  *(_OWORD *)&v61[1] = v30;
  *(_OWORD *)(v19 + 1) = v32;
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v60);
  if ( NextLexeme < 0 )
    goto LABEL_65;
  switch ( v60 )
  {
    case 4:
      v4 = 1;
      goto LABEL_14;
    case 2:
      v34 = 0;
      v4 = 1;
      break;
    case 3:
      v33 = *(_OWORD *)v19;
      v34 = 1;
      v35 = v19[2];
      v36 = *(_QWORD *)&v70[16];
      *(_OWORD *)v19 = 0;
      v19[2] = v36;
      v37 = *(_OWORD *)v19;
      *(_OWORD *)v70 = v33;
      v38 = *(_OWORD *)v17;
      *(_QWORD *)&v70[16] = v35;
      *(_OWORD *)v19 = v38;
      v19[2] = v17[2];
      *(_OWORD *)v17 = v37;
      v17[2] = v36;
      break;
    default:
      v82[2] = 754;
      v82[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v12 = (const char **)v82;
      v82[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v82[3] = "((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == Identit"
               "yParser::CLexeme::Equals))";
      goto LABEL_63;
  }
  v39 = *(_QWORD *)v69;
  if ( !v34 )
    goto LABEL_48;
  while ( 1 )
  {
    v40 = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
            (IdentityParser::CLexicalAnalyzer *)&v92,
            (struct IdentityParser::CLexeme *)&v60);
    if ( v40 < 0 )
    {
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v68);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v61);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v93);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v86);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v89);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v69);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v70);
      return (unsigned int)v40;
    }
    if ( v60 != 1 )
    {
      v84[2] = 786;
      v84[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v12 = (const char **)v84;
      v84[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v84[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::String";
      goto LABEL_63;
    }
    v41 = *(_OWORD *)&v69[8];
    v42 = v39;
    v39 = v61[0];
    *(_QWORD *)v69 = v61[0];
    v61[0] = v42;
    *(_OWORD *)&v69[8] = *(_OWORD *)&v61[1];
    *(_OWORD *)&v61[1] = v41;
    NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                   (IdentityParser::CLexicalAnalyzer *)&v92,
                   (struct IdentityParser::CLexeme *)&v60);
    if ( NextLexeme < 0 )
      goto LABEL_65;
    if ( ((v60 - 2) & 0xFFFFFFFD) != 0 )
      break;
    v77 = 0;
    v73 = 0;
    v76 = 0;
    v72 = 0;
    NextLexeme = RtlSplitLUnicodeString(2, (unsigned int)v70, 0, 0, 58, (__int64)&v76, (__int64)&v72);
    if ( NextLexeme < 0 )
      goto LABEL_65;
    if ( (_QWORD)v72 )
    {
      v59 = 0;
      if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v71, &v59, v43) )
      {
        v65 = 814;
        v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
        v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
        v57 = "Pool.Allocate(&TempString)";
LABEL_58:
        v66 = v57;
        v10 = &v63;
LABEL_3:
        NextLexeme = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
                       v91,
                       v10);
        goto LABEL_65;
      }
      v44 = v59;
      NextLexeme = RtlDuplicateLUnicodeString(&v76, v59);
      if ( NextLexeme < 0 )
        goto LABEL_65;
    }
    else
    {
      v44 = 0;
      v72 = v76;
      v73 = v77;
    }
    v62 = 0;
    if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v71, &v62, v43) )
    {
      v65 = 824;
      v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v57 = "Pool.Allocate(&TempName)";
      goto LABEL_58;
    }
    NextLexeme = RtlDuplicateLUnicodeString(&v72, v62);
    if ( NextLexeme < 0 )
      goto LABEL_65;
    if ( v39 )
    {
      v59 = 0;
      if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v71, &v59, v45) )
      {
        v65 = 840;
        v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
        v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
        v57 = "Pool.Allocate(&TempValue)";
        goto LABEL_58;
      }
      v46 = v59;
      v47 = *(_QWORD *)&v69[16];
      v48 = *(_OWORD *)v59;
      v49 = v59[2];
      *(_OWORD *)v59 = *(_OWORD *)v69;
      *(_OWORD *)v69 = v48;
      v39 = v48;
      v46[2] = v47;
      *(_QWORD *)&v69[16] = v49;
    }
    else
    {
      v46 = g_LUNICODE_STRING_neutral;
    }
    v50 = 3 * v18;
    v51 = v62;
    ++v18;
    v52 = v60 == 4;
    v53 = *v75;
    *(_QWORD *)(v53 + 8 * v50) = v44;
    *(_QWORD *)(v53 + 8 * v50 + 8) = v51;
    *(_QWORD *)(v53 + 8 * v50 + 16) = v46;
    if ( v52 )
    {
      v8 = v75;
LABEL_14:
      if ( v19[2] )
      {
        v22 = *v8;
        v23 = 3 * v18;
        v24 = v18 + 1;
        *(_QWORD *)(v22 + 8 * v23) = 0;
        *(_QWORD *)(v22 + 8 * v23 + 8) = g_LUNICODE_STRING_Name;
        *(_QWORD *)(v22 + 8 * v23 + 16) = v19;
        if ( !v4 )
        {
LABEL_18:
          v8[1] = v24;
          goto LABEL_66;
        }
        if ( v17[2] )
        {
          v25 = *v8;
          v26 = 3 * v24++;
          *(_QWORD *)(v25 + 8 * v26) = 0;
          *(_QWORD *)(v25 + 8 * v26 + 8) = g_LUNICODE_STRING_TypeName;
          *(_QWORD *)(v25 + 8 * v26 + 16) = v17;
          goto LABEL_18;
        }
      }
LABEL_68:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1800969B6LL);
    }
LABEL_48:
    NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                   (IdentityParser::CLexicalAnalyzer *)&v92,
                   (struct IdentityParser::CLexeme *)&v67);
    if ( NextLexeme < 0 )
      goto LABEL_65;
    if ( v67 != 1 )
    {
      v65 = 773;
      v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v56 = "PreviousLexeme.m_LexemeType == IdentityParser::CLexeme::String";
      goto LABEL_56;
    }
    NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                   (IdentityParser::CLexicalAnalyzer *)&v92,
                   (struct IdentityParser::CLexeme *)&v60);
    if ( NextLexeme < 0 )
      goto LABEL_65;
    if ( v60 != 3 )
    {
      v83[2] = 777;
      v83[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v12 = (const char **)v83;
      v83[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v83[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Equals";
      goto LABEL_63;
    }
    v54 = *(_QWORD *)v70;
    v55 = *(_OWORD *)&v68[8];
    *(_OWORD *)&v68[8] = *(_OWORD *)&v70[8];
    *(_QWORD *)v70 = *(_QWORD *)v68;
    *(_OWORD *)&v70[8] = v55;
    *(_QWORD *)v68 = v54;
  }
  v65 = 794;
  v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
  v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
  v56 = "((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser"
        "::CLexeme::EndOfStream))";
LABEL_56:
  v66 = v56;
  v12 = &v63;
LABEL_63:
  v13 = 3222601753LL;
LABEL_64:
  NextLexeme = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 v91,
                 v12,
                 v13);
LABEL_65:
  v6 = NextLexeme;
LABEL_66:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v68);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v61);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v93);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v86);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v89);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v69);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v70);
  return v6;
}

```

## disassembly

```asm
0x1800960a0  mov     rax, rsp
0x1800960a3  mov     [rax+8], rbx
0x1800960a7  push    rbp
0x1800960a8  push    rsi
0x1800960a9  push    rdi
0x1800960aa  push    r12
0x1800960ac  push    r13
0x1800960ae  push    r14
0x1800960b0  push    r15
0x1800960b2  lea     rbp, [rax-218h]
0x1800960b9  sub     rsp, 2E0h
0x1800960c0  movaps  xmmword ptr [rax-48h], xmm6
0x1800960c4  movaps  xmmword ptr [rax-58h], xmm7
0x1800960c8  mov     rax, cs:__security_cookie
0x1800960cf  xor     rax, rsp
0x1800960d2  mov     [rbp+210h+var_58], rax
0x1800960d9  mov     rcx, [rdx+10h]
0x1800960dd  xor     r13d, r13d
0x1800960e0  xor     eax, eax
0x1800960e2  mov     [rbp+210h+var_68], rcx
0x1800960e9  add     rcx, [rdx]
0x1800960ec  xorps   xmm0, xmm0
0x1800960ef  mov     [rbp+210h+var_238], rax
0x1800960f3  lea     rdx, [rsp+310h+var_2A8]
0x1800960f8  mov     [rbp+210h+var_250], rax
0x1800960fc  xorps   xmm7, xmm7
0x1800960ff  mov     [rbp+210h+var_E8], rax
0x180096106  mov     ebx, r13d
0x180096109  mov     [rbp+210h+var_108], rax
0x180096110  mov     rsi, r9
0x180096113  mov     [rbp+210h+var_B8], rax
0x18009611a  mov     r15, r8
0x18009611d  lea     rax, [rbp+210h+var_70]
0x180096124  mov     [rbp+210h+var_60], rcx
0x18009612b  mov     [rbp+210h+var_A8], rax
0x180096132  mov     rcx, r9
0x180096135  xor     eax, eax
0x180096137  mov     [rbp+210h+var_230], r9
0x18009613b  mov     [rsp+310h+var_2B0], rax
0x180096140  mov     [rbp+210h+var_268], rax
0x180096144  mov     [rbp+210h+var_208], r8
0x180096148  mov     [rbp+210h+var_E0], ebx
0x18009614e  mov     [rsp+310h+var_2A8], r13
0x180096153  mov     [rsp+310h+var_2D0], r13
0x180096158  movups  [rbp+210h+var_248], xmm7
0x18009615c  mov     [rbp+210h+var_100], r13d
0x180096163  movups  [rbp+210h+var_260], xmm0
0x180096167  mov     [rbp+210h+var_120], r13d
0x18009616e  movups  [rbp+210h+var_F8], xmm0
0x180096175  mov     [rbp+210h+var_70], 0FFFFFFFFh
0x18009617f  movups  [rbp+210h+var_118], xmm0
0x180096186  mov     [rbp+210h+var_D0], r13d
0x18009618d  movups  [rbp+210h+var_C8], xmm0
0x180096194  mov     [rbp+210h+var_B0], r13b
0x18009619b  mov     dword ptr [rsp+310h+var_2C8], r13d
0x1800961a0  movups  [rsp+310h+var_2C8+8], xmm0
0x1800961a5  mov     [rbp+210h+var_280], r13d
0x1800961a9  movups  [rbp+210h+var_278], xmm0
0x1800961ad  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x1800961b2  test    rax, rax
0x1800961b5  jnz     short loc_1800961F5
0x1800961b7  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x1800961be  mov     [rbp+210h+var_1F0], 2BBh
0x1800961c6  mov     qword ptr [rbp+210h+var_200], rax
0x1800961ca  lea     rdx, [rbp+210h+var_200]
0x1800961ce  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x1800961d5  mov     qword ptr [rbp+210h+var_200+8], rax
0x1800961d9  lea     rax, aPoolAllocateNa; "Pool.Allocate(&NameAttributeValueBuffer"...
0x1800961e0  mov     [rbp+210h+var_1E8], rax
0x1800961e4  lea     rcx, [rbp+210h+var_E0]
0x1800961eb  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800961f0  jmp     loc_1800968D9
0x1800961f5  lea     rdx, [rsp+310h+var_2D0]
0x1800961fa  mov     rcx, rsi
0x1800961fd  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x180096202  test    rax, rax
0x180096205  jnz     short loc_180096236
0x180096207  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x18009620e  mov     [rbp+210h+var_218], 2BCh
0x180096216  mov     qword ptr [rbp+210h+var_228], rax
0x18009621a  lea     rdx, [rbp+210h+var_228]
0x18009621e  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x180096225  mov     qword ptr [rbp+210h+var_228+8], rax
0x180096229  lea     rax, aPoolAllocateTy; "Pool.Allocate(&TypeNameAttributeValueBu"...
0x180096230  mov     [rbp+210h+var_210], rax
0x180096234  jmp     short loc_1800961E4
0x180096236  lea     rdx, [rsp+310h+var_2C8]; struct IdentityParser::CLexeme *
0x18009623b  lea     rcx, [rbp+210h+var_D0]; this
0x180096242  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x180096247  test    eax, eax
0x180096249  js      loc_1800968D9
0x18009624f  cmp     dword ptr [rsp+310h+var_2C8], 1
0x180096254  jz      short loc_18009628E
0x180096256  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x18009625d  mov     [rbp+210h+var_1D0], 2C3h
0x180096265  mov     [rbp+210h+var_1E0], rax
0x180096269  lea     rdx, [rbp+210h+var_1E0]
0x18009626d  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x180096274  mov     r8d, 0C000000Dh
0x18009627a  mov     [rbp+210h+var_1D8], rax
0x18009627e  lea     rax, aCurrentlexemeM_1; "CurrentLexeme.m_LexemeType == IdentityP"...
0x180096285  mov     [rbp+210h+var_1C8], rax
0x180096289  jmp     loc_1800968CD
0x18009628e  movups  xmm6, xmmword ptr [rsp+310h+var_2B8]
0x180096293  mov     r14, qword ptr [rsp+310h+var_2C8+8]
0x180096298  lea     rdx, [rsp+310h+var_2C8]; struct IdentityParser::CLexeme *
0x18009629d  movups  xmm0, [rbp+210h+var_278+8]
0x1800962a1  mov     rax, qword ptr [rbp+210h+var_278]
0x1800962a5  lea     rcx, [rbp+210h+var_D0]; this
0x1800962ac  movdqu  [rbp+210h+var_278+8], xmm6
0x1800962b1  mov     qword ptr [rsp+310h+var_2C8+8], rax
0x1800962b6  movdqu  xmmword ptr [rsp+310h+var_2B8], xmm0
0x1800962bc  mov     qword ptr [rbp+210h+var_278], r14
0x1800962c0  mov     [rbp+210h+var_280], 1
0x1800962c7  mov     dword ptr [rsp+310h+var_2C8], r13d
0x1800962cc  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x1800962d1  test    eax, eax
0x1800962d3  js      loc_1800968D9
0x1800962d9  mov     ecx, dword ptr [rsp+310h+var_2C8]
0x1800962dd  lea     eax, [rcx-2]
0x1800962e0  test    eax, 0FFFFFFFDh
0x1800962e5  jz      short loc_18009631F
0x1800962e7  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x1800962ee  mov     [rbp+210h+var_1B0], 2CEh
0x1800962f6  mov     [rbp+210h+var_1C0], rax
0x1800962fa  lea     rdx, [rbp+210h+var_1C0]
0x1800962fe  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x180096305  mov     r8d, 0C000000Dh
0x18009630b  mov     [rbp+210h+var_1B8], rax
0x18009630f  lea     rax, aCurrentlexemeM; "((CurrentLexeme.m_LexemeType == Identit"...
0x180096316  mov     [rbp+210h+var_1A8], rax
0x18009631a  jmp     loc_1800968CD
0x18009631f  mov     r12, [rsp+310h+var_2D0]
0x180096324  mov     rdi, r13
0x180096327  cmp     ecx, 4
0x18009632a  jnz     loc_1800963B1
0x180096330  mov     rsi, [rsp+310h+var_2A8]
0x180096335  movups  xmm0, xmmword ptr [rsi+8]
0x180096339  mov     rax, [rsi]
0x18009633c  mov     [rsi], r14
0x18009633f  movdqu  [rbp+210h+var_278+8], xmm0
0x180096344  mov     qword ptr [rbp+210h+var_278], rax
0x180096348  movdqu  xmmword ptr [rsi+8], xmm6
0x18009634d  xor     r8d, r8d
0x180096350  cmp     [rsi+10h], r8
0x180096354  jz      loc_1800969AC
0x18009635a  mov     rax, [r15]
0x18009635d  lea     rcx, [rdi+rdi*2]
0x180096361  lea     rdx, g_LUNICODE_STRING_Name
0x180096368  inc     rdi
0x18009636b  mov     [rax+rcx*8], r8
0x18009636f  mov     [rax+rcx*8+8], rdx
0x180096374  mov     [rax+rcx*8+10h], rsi
0x180096379  test    r13b, r13b
0x18009637c  jz      short loc_1800963A8
0x18009637e  cmp     [r12+10h], r8
0x180096383  jz      loc_1800969AC
0x180096389  mov     rax, [r15]
0x18009638c  lea     rcx, [rdi+rdi*2]
0x180096390  lea     rdx, g_LUNICODE_STRING_TypeName
0x180096397  inc     rdi
0x18009639a  mov     [rax+rcx*8], r8
0x18009639e  mov     [rax+rcx*8+8], rdx
0x1800963a3  mov     [rax+rcx*8+10h], r12
0x1800963a8  mov     [r15+8], rdi
0x1800963ac  jmp     loc_1800968DB
0x1800963b1  cmp     ecx, 2
0x1800963b4  jnz     loc_1800969AC
0x1800963ba  lea     rdx, [rsp+310h+var_2C8]; struct IdentityParser::CLexeme *
0x1800963bf  lea     rcx, [rbp+210h+var_D0]; this
0x1800963c6  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x1800963cb  test    eax, eax
0x1800963cd  js      loc_1800968D9
0x1800963d3  cmp     dword ptr [rsp+310h+var_2C8], 1
0x1800963d8  jz      short loc_180096412
0x1800963da  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x1800963e1  mov     [rbp+210h+var_190], 2DAh
0x1800963ec  mov     [rbp+210h+var_1A0], rax
0x1800963f0  lea     rdx, [rbp+210h+var_1A0]
0x1800963f4  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x1800963fb  mov     [rbp+210h+var_198], rax
0x1800963ff  lea     rax, aCurrentlexemeM_1; "CurrentLexeme.m_LexemeType == IdentityP"...
0x180096406  mov     [rbp+210h+var_188], rax
0x18009640d  jmp     loc_1800968C7
0x180096412  movups  xmm0, xmmword ptr [r12+8]
0x180096418  mov     rax, [r12]
0x18009641c  lea     rdx, [rsp+310h+var_2C8]; struct IdentityParser::CLexeme *
0x180096421  mov     rsi, [rsp+310h+var_2A8]
0x180096426  mov     [r12], r14
0x18009642a  movdqu  xmmword ptr [r12+8], xmm6
0x180096431  mov     qword ptr [rbp+210h+var_278], rax
0x180096435  mov     rcx, [rsi]
0x180096438  movups  xmm1, xmmword ptr [rsi+8]
0x18009643c  mov     rax, qword ptr [rsp+310h+var_2C8+8]
0x180096441  movdqu  [rbp+210h+var_278+8], xmm0
0x180096446  mov     qword ptr [rsp+310h+var_2C8+8], rcx
0x18009644b  lea     rcx, [rbp+210h+var_D0]; this
0x180096452  movups  xmm0, xmmword ptr [rsp+310h+var_2B8]
0x180096457  mov     [rsi], rax
0x18009645a  movdqu  xmmword ptr [rsp+310h+var_2B8], xmm1
0x180096460  movdqu  xmmword ptr [rsi+8], xmm0
0x180096465  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x18009646a  test    eax, eax
0x18009646c  js      loc_1800968D9
0x180096472  mov     eax, dword ptr [rsp+310h+var_2C8]
0x180096476  cmp     eax, 4
0x180096479  jnz     short loc_180096483
0x18009647b  mov     r13b, 1
0x18009647e  jmp     loc_18009634D
0x180096483  cmp     eax, 2
0x180096486  jz      loc_180096517
0x18009648c  cmp     eax, 3
0x18009648f  jz      short loc_1800964D2
0x180096491  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180096498  mov     [rbp+210h+var_170], 2F2h
0x1800964a3  mov     [rbp+210h+var_180], rax
0x1800964aa  lea     rdx, [rbp+210h+var_180]
0x1800964b1  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x1800964b8  mov     [rbp+210h+var_178], rax
0x1800964bf  lea     rax, aCurrentlexemeM_0; "((CurrentLexeme.m_LexemeType == Identit"...
0x1800964c6  mov     [rbp+210h+var_168], rax
0x1800964cd  jmp     loc_1800968C7
0x1800964d2  movups  xmm0, xmmword ptr [rsi]
0x1800964d5  mov     al, 1
0x1800964d7  movsd   xmm1, qword ptr [rsi+10h]
0x1800964dc  movsd   xmm2, [rbp+210h+var_238]
0x1800964e1  movups  xmmword ptr [rsi], xmm7
0x1800964e4  movsd   qword ptr [rsi+10h], xmm2
0x1800964e9  movups  xmm3, xmmword ptr [rsi]
0x1800964ec  movups  [rbp+210h+var_248], xmm0
0x1800964f0  movups  xmm0, xmmword ptr [r12]
0x1800964f5  movsd   [rbp+210h+var_238], xmm1
0x1800964fa  movups  xmmword ptr [rsi], xmm0
0x1800964fd  movsd   xmm1, qword ptr [r12+10h]
0x180096504  movsd   qword ptr [rsi+10h], xmm1
0x180096509  movups  xmmword ptr [r12], xmm3
0x18009650e  movsd   qword ptr [r12+10h], xmm2
0x180096515  jmp     short loc_18009651D
0x180096517  mov     al, r13b
0x18009651a  mov     r13b, 1
0x18009651d  mov     r14, qword ptr [rbp+210h+var_260]
0x180096521  test    al, al
0x180096523  jz      loc_1800966F0
0x180096529  lea     rdx, [rsp+310h+var_2C8]; struct IdentityParser::CLexeme *
0x18009652e  lea     rcx, [rbp+210h+var_D0]; this
0x180096535  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x18009653a  mov     r15d, eax
0x18009653d  test    eax, eax
0x18009653f  js      loc_18009695B
0x180096545  cmp     dword ptr [rsp+310h+var_2C8], 1
0x18009654a  jnz     loc_18009688B
0x180096550  movups  xmm1, [rbp+210h+var_260+8]
0x180096554  mov     rax, r14
0x180096557  mov     r14, qword ptr [rsp+310h+var_2C8+8]
0x18009655c  movups  xmm0, xmmword ptr [rsp+310h+var_2B8]
0x180096561  lea     rdx, [rsp+310h+var_2C8]; struct IdentityParser::CLexeme *
0x180096566  mov     qword ptr [rbp+210h+var_260], r14
0x18009656a  lea     rcx, [rbp+210h+var_D0]; this
0x180096571  mov     qword ptr [rsp+310h+var_2C8+8], rax
0x180096576  movdqu  [rbp+210h+var_260+8], xmm0
0x18009657b  movdqu  xmmword ptr [rsp+310h+var_2B8], xmm1
0x180096581  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x180096586  test    eax, eax
0x180096588  js      loc_1800968D9
0x18009658e  mov     eax, dword ptr [rsp+310h+var_2C8]
0x180096592  add     eax, 0FFFFFFFEh
0x180096595  test    eax, 0FFFFFFFDh
0x18009659a  jnz     loc_18009685F
0x1800965a0  xor     eax, eax
0x1800965a2  lea     rdx, [rbp+210h+var_248]
0x1800965a6  mov     [rbp+210h+var_1F0], rax
0x1800965aa  xor     r9d, r9d
0x1800965ad  mov     [rbp+210h+var_218], rax
0x1800965b1  xorps   xmm0, xmm0
0x1800965b4  lea     rax, [rbp+210h+var_228]
0x1800965b8  xorps   xmm1, xmm1
0x1800965bb  mov     [rsp+310h+var_2E0], rax
0x1800965c0  xor     r8d, r8d
0x1800965c3  lea     rax, [rbp+210h+var_200]
0x1800965c7  mov     [rsp+310h+var_2E8], rax
0x1800965cc  lea     ecx, [r9+2]
0x1800965d0  mov     [rsp+310h+var_2F0], 3Ah ; ':'
0x1800965d9  movups  [rbp+210h+var_200], xmm0
0x1800965dd  movups  [rbp+210h+var_228], xmm1
0x1800965e1  call    RtlSplitLUnicodeString
0x1800965e6  test    eax, eax
0x1800965e8  js      loc_1800968D9
0x1800965ee  cmp     qword ptr [rbp+210h+var_228], rbx
0x1800965f2  jnz     short loc_18009660B
0x1800965f4  movups  xmm0, [rbp+210h+var_200]
0x1800965f8  xor     r15d, r15d
0x1800965fb  movsd   xmm1, [rbp+210h+var_1F0]
0x180096600  movups  [rbp+210h+var_228], xmm0
0x180096604  movsd   [rbp+210h+var_218], xmm1
0x180096609  jmp     short loc_180096640
0x18009660b  mov     rcx, [rbp+210h+var_230]
0x18009660f  lea     rdx, [rsp+310h+var_2D0]
0x180096614  mov     [rsp+310h+var_2D0], rbx
0x180096619  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x18009661e  test    rax, rax
  ... truncated ...
```

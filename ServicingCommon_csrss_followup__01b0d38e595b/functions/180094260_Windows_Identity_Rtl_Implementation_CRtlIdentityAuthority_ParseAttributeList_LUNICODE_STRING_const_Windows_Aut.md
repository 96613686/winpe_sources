# Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList(_LUNICODE_STRING const *,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>> *,Windows::WCP::Implementation::CAllocationPool &)

- ea: `0x180094260`
- end: `0x180094b29`
- name: `?ParseAttributeList@CRtlIdentityAuthority@Implementation@Rtl@Identity@Windows@@AEAAJPEBU_LUNICODE_STRING@@PEAV?$Auto@U?$Vector@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@@5@AEAVCAllocationPool@2WCP@5@@Z`
- size: `2249`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180091dd0`
- `0x180092120`

## callees

- `0x180004a8c`
- `0x18001f840`
- `0x1800217cc`
- `0x18002d2b0`
- `0x180066860`
- `0x180067710`
- `0x1800926b0`
- `0x180093ea8`
- `0x180094260`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180094b1c`
- `ntdll!RtlRaiseStatus` at `0x180094b1c`

## string_xrefs

- `0x180094619`: `((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Equals))`
- `0x1800944c7`: `((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::EndOfStream))`
- `0x1800949d9`: `((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::EndOfStream))`
- `0x1800949b1`: `Pool.Allocate(&TempString)`
- `0x180094989`: `Pool.Allocate(&TempName)`
- `0x180094955`: `Pool.Allocate(&TempValue)`

## pseudocode

```c
__int64 __fastcall Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // r13
  __int64 *v7; // r12
  __int64 v8; // r8
  const char **v9; // rdx
  int NextLexeme; // eax
  const char **v11; // rdx
  __int64 v12; // r8
  __int128 v13; // xmm6
  __int64 v14; // r14
  __int128 v15; // xmm0
  __int64 *v16; // r15
  __int64 v17; // rdi
  char v18; // dl
  __int64 *v19; // rsi
  __int128 v20; // xmm0
  __int64 v21; // rax
  __int128 v22; // xmm0
  __int64 v23; // rax
  __int64 v24; // rcx
  __int128 v25; // xmm1
  __int64 v26; // rax
  __int128 v27; // xmm0
  int v28; // r14d
  __int128 v29; // xmm0
  char v30; // r8
  __int64 v31; // xmm1_8
  __int64 v32; // xmm2_8
  __int128 v33; // xmm3
  __int128 v34; // xmm0
  __int64 v35; // r12
  __int64 v36; // rcx
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 *v41; // r13
  __int64 v42; // r8
  __int64 *v43; // rdx
  __int64 v44; // xmm1_8
  __int128 v45; // xmm3
  __int64 v46; // xmm2_8
  __int64 v47; // rcx
  __int64 *v48; // r9
  __int64 v49; // rax
  const char *v50; // rax
  const char *v51; // rax
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rdi
  __int64 v56; // rax
  __int64 v57; // rcx
  char v58; // [rsp+48h] [rbp-C0h]
  __int64 *v59; // [rsp+50h] [rbp-B8h] BYREF
  __int64 *v60; // [rsp+58h] [rbp-B0h] BYREF
  int v61; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v62[3]; // [rsp+68h] [rbp-A0h] BYREF
  const char *v63; // [rsp+80h] [rbp-88h] BYREF
  const char *v64; // [rsp+88h] [rbp-80h]
  __int64 v65; // [rsp+90h] [rbp-78h]
  const char *v66; // [rsp+98h] [rbp-70h]
  int v67; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v68[24]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v69; // [rsp+C0h] [rbp-48h]
  _BYTE v70[24]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v71[24]; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v72; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v73; // [rsp+108h] [rbp+0h]
  const char *v74; // [rsp+110h] [rbp+8h]
  __int64 *v75; // [rsp+118h] [rbp+10h]
  __int128 v76; // [rsp+120h] [rbp+18h] BYREF
  __int64 v77; // [rsp+130h] [rbp+28h]
  const char *v78; // [rsp+138h] [rbp+30h]
  _QWORD v79[4]; // [rsp+140h] [rbp+38h] BYREF
  _QWORD v80[4]; // [rsp+160h] [rbp+58h] BYREF
  _QWORD v81[4]; // [rsp+180h] [rbp+78h] BYREF
  _QWORD v82[4]; // [rsp+1A0h] [rbp+98h] BYREF
  _QWORD v83[4]; // [rsp+1C0h] [rbp+B8h] BYREF
  _QWORD v84[4]; // [rsp+1E0h] [rbp+D8h] BYREF
  int v85; // [rsp+200h] [rbp+F8h]
  __int128 v86; // [rsp+208h] [rbp+100h] BYREF
  __int64 v87; // [rsp+218h] [rbp+110h]
  int v88; // [rsp+220h] [rbp+118h]
  __int128 v89; // [rsp+228h] [rbp+120h] BYREF
  __int64 v90; // [rsp+238h] [rbp+130h]
  int v91; // [rsp+240h] [rbp+138h] BYREF
  int v92; // [rsp+248h] [rbp+140h] BYREF
  __int128 v93; // [rsp+250h] [rbp+148h] BYREF
  __int64 v94; // [rsp+260h] [rbp+158h]
  char v95; // [rsp+268h] [rbp+160h]
  int *v96; // [rsp+270h] [rbp+168h]
  int v97; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v98; // [rsp+2B0h] [rbp+1A8h]
  __int64 v99; // [rsp+2B8h] [rbp+1B0h]

  v98 = a2[2];
  v4 = *a2 + v98;
  v90 = 0;
  v5 = 0;
  v87 = 0;
  v6 = a4;
  v94 = 0;
  v7 = a3;
  v99 = v4;
  v96 = &v97;
  v69 = a4;
  v75 = a3;
  v91 = 0;
  v60 = 0;
  v59 = 0;
  memset(v71, 0, sizeof(v71));
  v88 = 0;
  memset(v70, 0, sizeof(v70));
  v85 = 0;
  v89 = 0;
  v97 = -1;
  v86 = 0;
  v92 = 0;
  v93 = 0;
  v95 = 0;
  v61 = 0;
  memset(v62, 0, sizeof(v62));
  v67 = 0;
  memset(v68, 0, sizeof(v68));
  if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(a4, &v60, a3) )
  {
    v77 = 699;
    *(_QWORD *)&v76 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v9 = (const char **)&v76;
    *((_QWORD *)&v76 + 1) = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v78 = "Pool.Allocate(&NameAttributeValueBuffer)";
LABEL_3:
    NextLexeme = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
                   &v91,
                   v9);
    goto LABEL_61;
  }
  if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v6, &v59, v8) )
  {
    v73 = 700;
    *(_QWORD *)&v72 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v9 = (const char **)&v72;
    *((_QWORD *)&v72 + 1) = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v74 = "Pool.Allocate(&TypeNameAttributeValueBuffer)";
    goto LABEL_3;
  }
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v61);
  if ( NextLexeme < 0 )
    goto LABEL_61;
  if ( v61 != 1 )
  {
    v79[2] = 707;
    v79[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v11 = (const char **)v79;
    v12 = 3221225485LL;
    v79[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v79[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::String";
    goto LABEL_60;
  }
  v13 = *(_OWORD *)&v62[1];
  v14 = v62[0];
  v15 = *(_OWORD *)&v68[8];
  *(_OWORD *)&v68[8] = *(_OWORD *)&v62[1];
  v62[0] = *(_QWORD *)v68;
  *(_OWORD *)&v62[1] = v15;
  *(_QWORD *)v68 = v14;
  v67 = 1;
  v61 = 0;
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v61);
  if ( NextLexeme < 0 )
    goto LABEL_61;
  if ( ((v61 - 2) & 0xFFFFFFFD) != 0 )
  {
    v80[2] = 718;
    v80[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v11 = (const char **)v80;
    v12 = 3221225485LL;
    v80[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v80[3] = "((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityP"
             "arser::CLexeme::EndOfStream))";
    goto LABEL_60;
  }
  v16 = v59;
  v17 = 0;
  if ( v61 == 4 )
  {
    v18 = 0;
    v19 = v60;
    v20 = *(_OWORD *)(v60 + 1);
    v21 = *v60;
    *v60 = v14;
    *(_OWORD *)&v68[8] = v20;
    *(_QWORD *)v68 = v21;
    *(_OWORD *)(v19 + 1) = v13;
    goto LABEL_64;
  }
  if ( v61 != 2 )
    goto LABEL_69;
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v61);
  if ( NextLexeme < 0 )
    goto LABEL_61;
  if ( v61 != 1 )
  {
    v81[2] = 730;
    v81[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
    v11 = (const char **)v81;
    v81[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
    v81[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::String";
    goto LABEL_59;
  }
  v22 = *(_OWORD *)(v16 + 1);
  v23 = *v16;
  v19 = v60;
  *v16 = v14;
  *(_OWORD *)(v16 + 1) = v13;
  *(_QWORD *)v68 = v23;
  v24 = *v19;
  v25 = *(_OWORD *)(v19 + 1);
  v26 = v62[0];
  *(_OWORD *)&v68[8] = v22;
  v62[0] = v24;
  v27 = *(_OWORD *)&v62[1];
  *v19 = v26;
  *(_OWORD *)&v62[1] = v25;
  *(_OWORD *)(v19 + 1) = v27;
  NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                 (IdentityParser::CLexicalAnalyzer *)&v92,
                 (struct IdentityParser::CLexeme *)&v61);
  if ( NextLexeme < 0 )
    goto LABEL_61;
  v28 = v61;
  switch ( v61 )
  {
    case 4:
      v18 = 1;
      goto LABEL_64;
    case 2:
      v30 = 0;
      v58 = 1;
      break;
    case 3:
      v29 = *(_OWORD *)v19;
      v30 = 1;
      v31 = v19[2];
      v32 = *(_QWORD *)&v71[16];
      *(_OWORD *)v19 = 0;
      v58 = 0;
      v19[2] = v32;
      v33 = *(_OWORD *)v19;
      *(_OWORD *)v71 = v29;
      v34 = *(_OWORD *)v16;
      *(_QWORD *)&v71[16] = v31;
      *(_OWORD *)v19 = v34;
      v19[2] = v16[2];
      *(_OWORD *)v16 = v33;
      v16[2] = v32;
      break;
    default:
      v82[2] = 754;
      v82[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v11 = (const char **)v82;
      v82[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v82[3] = "((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == Identit"
               "yParser::CLexeme::Equals))";
      goto LABEL_59;
  }
  v35 = *(_QWORD *)v70;
  while ( 1 )
  {
    if ( v28 == 4 )
    {
      v18 = v58;
      v7 = v75;
LABEL_64:
      if ( v19[2] )
      {
        v53 = *v7;
        v54 = 3 * v17;
        v55 = v17 + 1;
        *(_QWORD *)(v53 + 8 * v54) = 0;
        *(_QWORD *)(v53 + 8 * v54 + 8) = g_LUNICODE_STRING_Name;
        *(_QWORD *)(v53 + 8 * v54 + 16) = v19;
        if ( !v18 )
        {
LABEL_68:
          v7[1] = v55;
          goto LABEL_62;
        }
        if ( v16[2] )
        {
          v56 = *v7;
          v57 = 3 * v55++;
          *(_QWORD *)(v56 + 8 * v57) = 0;
          *(_QWORD *)(v56 + 8 * v57 + 8) = g_LUNICODE_STRING_TypeName;
          *(_QWORD *)(v56 + 8 * v57 + 16) = v16;
          goto LABEL_68;
        }
      }
LABEL_69:
      RtlRaiseStatus(-1073741595);
    }
    if ( !v30 )
    {
      NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                     (IdentityParser::CLexicalAnalyzer *)&v92,
                     (struct IdentityParser::CLexeme *)&v67);
      if ( NextLexeme < 0 )
        goto LABEL_61;
      if ( v67 != 1 )
      {
        v65 = 773;
        v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
        v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
        v50 = "PreviousLexeme.m_LexemeType == IdentityParser::CLexeme::String";
        goto LABEL_52;
      }
      NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                     (IdentityParser::CLexicalAnalyzer *)&v92,
                     (struct IdentityParser::CLexeme *)&v61);
      if ( NextLexeme < 0 )
        goto LABEL_61;
      if ( v61 != 3 )
      {
        v83[2] = 777;
        v83[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
        v11 = (const char **)v83;
        v83[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
        v83[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Equals";
        goto LABEL_59;
      }
      v36 = *(_QWORD *)v71;
      v37 = *(_OWORD *)&v68[8];
      *(_OWORD *)&v68[8] = *(_OWORD *)&v71[8];
      *(_QWORD *)v71 = *(_QWORD *)v68;
      *(_OWORD *)&v71[8] = v37;
      *(_QWORD *)v68 = v36;
    }
    NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                   (IdentityParser::CLexicalAnalyzer *)&v92,
                   (struct IdentityParser::CLexeme *)&v61);
    if ( NextLexeme < 0 )
      goto LABEL_61;
    if ( v61 != 1 )
    {
      v84[2] = 786;
      v84[0] = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v11 = (const char **)v84;
      v84[1] = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v84[3] = "CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::String";
      goto LABEL_59;
    }
    v38 = *(_OWORD *)&v70[8];
    v39 = v35;
    v35 = v62[0];
    *(_QWORD *)v70 = v62[0];
    v62[0] = v39;
    *(_OWORD *)&v70[8] = *(_OWORD *)&v62[1];
    *(_OWORD *)&v62[1] = v38;
    NextLexeme = IdentityParser::CLexicalAnalyzer::GetNextLexeme(
                   (IdentityParser::CLexicalAnalyzer *)&v92,
                   (struct IdentityParser::CLexeme *)&v61);
    if ( NextLexeme < 0 )
      goto LABEL_61;
    v28 = v61;
    if ( ((v61 - 2) & 0xFFFFFFFD) != 0 )
      break;
    v77 = 0;
    v73 = 0;
    v76 = 0;
    v72 = 0;
    NextLexeme = RtlSplitLUnicodeString(2, (unsigned int)v71, 0, 0, 58, (__int64)&v76, (__int64)&v72);
    if ( NextLexeme < 0 )
      goto LABEL_61;
    if ( (_QWORD)v72 )
    {
      v59 = 0;
      if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v6, &v59, v40) )
      {
        v65 = 814;
        v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
        v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
        v51 = "Pool.Allocate(&TempString)";
        goto LABEL_54;
      }
      v41 = v59;
      NextLexeme = RtlDuplicateLUnicodeString(&v76, v59);
      if ( NextLexeme < 0 )
        goto LABEL_61;
    }
    else
    {
      v41 = 0;
      v72 = v76;
      v73 = v77;
    }
    v60 = 0;
    if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v69, &v60, v40) )
    {
      v65 = 824;
      v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
      v51 = "Pool.Allocate(&TempName)";
      goto LABEL_54;
    }
    NextLexeme = RtlDuplicateLUnicodeString(&v72, v60);
    if ( NextLexeme < 0 )
      goto LABEL_61;
    if ( v35 )
    {
      v59 = 0;
      if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v69, &v59, v42) )
      {
        v65 = 840;
        v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
        v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
        v51 = "Pool.Allocate(&TempValue)";
LABEL_54:
        v66 = v51;
        v9 = &v63;
        goto LABEL_3;
      }
      v43 = v59;
      v44 = *(_QWORD *)&v70[16];
      v45 = *(_OWORD *)v59;
      v46 = v59[2];
      *(_OWORD *)v59 = *(_OWORD *)v70;
      *(_OWORD *)v70 = v45;
      v35 = v45;
      v43[2] = v44;
      *(_QWORD *)&v70[16] = v46;
    }
    else
    {
      v43 = g_LUNICODE_STRING_neutral;
    }
    v47 = 3 * v17;
    v48 = v60;
    v30 = 0;
    ++v17;
    v49 = *v75;
    *(_QWORD *)(v49 + 8 * v47) = v41;
    v6 = v69;
    *(_QWORD *)(v49 + 8 * v47 + 8) = v48;
    *(_QWORD *)(v49 + 8 * v47 + 16) = v43;
  }
  v65 = 794;
  v63 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
  v64 = "Windows::Identity::Rtl::Implementation::CRtlIdentityAuthority::ParseAttributeList";
  v50 = "((CurrentLexeme.m_LexemeType == IdentityParser::CLexeme::Comma) || (CurrentLexeme.m_LexemeType == IdentityParser"
        "::CLexeme::EndOfStream))";
LABEL_52:
  v66 = v50;
  v11 = &v63;
LABEL_59:
  v12 = 3222601753LL;
LABEL_60:
  NextLexeme = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v91,
                 v11,
                 v12);
LABEL_61:
  v5 = NextLexeme;
LABEL_62:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v68);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v62);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v93);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v86);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v89);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v70);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v71);
  return v5;
}

```

## disassembly

```asm
0x180094260  mov     rax, rsp
0x180094263  mov     [rax+8], rbx
0x180094267  push    rbp
0x180094268  push    rsi
0x180094269  push    rdi
0x18009426a  push    r12
0x18009426c  push    r13
0x18009426e  push    r14
0x180094270  push    r15
0x180094272  lea     rbp, [rax-218h]
0x180094279  sub     rsp, 2E0h
0x180094280  movaps  xmmword ptr [rax-48h], xmm6
0x180094284  movaps  xmmword ptr [rax-58h], xmm7
0x180094288  mov     rax, cs:__security_cookie
0x18009428f  xor     rax, rsp
0x180094292  mov     [rbp+210h+var_58], rax
0x180094299  mov     rcx, [rdx+10h]
0x18009429d  xor     esi, esi
0x18009429f  xor     eax, eax
0x1800942a1  mov     [rbp+210h+var_68], rcx
0x1800942a8  add     rcx, [rdx]
0x1800942ab  xorps   xmm0, xmm0
0x1800942ae  mov     [rbp+210h+var_228], rax
0x1800942b2  lea     rdx, [rsp+310h+var_2C0]
0x1800942b7  mov     [rbp+210h+var_240], rax
0x1800942bb  xorps   xmm7, xmm7
0x1800942be  mov     [rbp+210h+var_E0], rax
0x1800942c5  mov     ebx, esi
0x1800942c7  mov     [rbp+210h+var_100], rax
0x1800942ce  mov     r13, r9
0x1800942d1  mov     [rbp+210h+var_B8], rax
0x1800942d8  mov     r12, r8
0x1800942db  lea     rax, [rbp+210h+var_70]
0x1800942e2  mov     [rbp+210h+var_60], rcx
0x1800942e9  mov     [rbp+210h+var_A8], rax
0x1800942f0  mov     rcx, r9
0x1800942f3  xor     eax, eax
0x1800942f5  mov     [rbp+210h+var_258], r9
0x1800942f9  mov     [rsp+310h+var_2A0], rax
0x1800942fe  mov     [rbp+210h+var_260], rax
0x180094302  mov     [rbp+210h+var_200], r8
0x180094306  mov     [rbp+210h+var_D8], ebx
0x18009430c  mov     [rsp+310h+var_2C0], rsi
0x180094311  mov     [rsp+310h+var_2C8], rsi
0x180094316  movups  [rbp+210h+var_238], xmm7
0x18009431a  mov     [rbp+210h+var_F8], esi
0x180094320  movups  [rbp+210h+var_250], xmm0
0x180094324  mov     [rbp+210h+var_118], esi
0x18009432a  movups  [rbp+210h+var_F0], xmm0
0x180094331  mov     [rbp+210h+var_70], 0FFFFFFFFh
0x18009433b  movups  [rbp+210h+var_110], xmm0
0x180094342  mov     [rbp+210h+var_D0], esi
0x180094348  movups  [rbp+210h+var_C8], xmm0
0x18009434f  mov     [rbp+210h+var_B0], sil
0x180094356  mov     dword ptr [rsp+310h+var_2B8], esi
0x18009435a  movups  [rsp+310h+var_2B8+8], xmm0
0x18009435f  mov     [rbp+210h+var_278], esi
0x180094362  movups  [rbp+210h+var_270], xmm0
0x180094366  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x18009436b  test    rax, rax
0x18009436e  jnz     short loc_1800943AE
0x180094370  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180094377  mov     [rbp+210h+var_1E8], 2BBh
0x18009437f  mov     qword ptr [rbp+210h+var_1F8], rax
0x180094383  lea     rdx, [rbp+210h+var_1F8]
0x180094387  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x18009438e  mov     qword ptr [rbp+210h+var_1F8+8], rax
0x180094392  lea     rax, aPoolAllocateNa; "Pool.Allocate(&NameAttributeValueBuffer"...
0x180094399  mov     [rbp+210h+var_1E0], rax
0x18009439d  lea     rcx, [rbp+210h+var_D8]
0x1800943a4  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800943a9  jmp     loc_180094A33
0x1800943ae  lea     rdx, [rsp+310h+var_2C8]
0x1800943b3  mov     rcx, r13
0x1800943b6  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x1800943bb  test    rax, rax
0x1800943be  jnz     short loc_1800943EF
0x1800943c0  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x1800943c7  mov     [rbp+210h+var_210], 2BCh
0x1800943cf  mov     qword ptr [rbp+210h+var_220], rax
0x1800943d3  lea     rdx, [rbp+210h+var_220]
0x1800943d7  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x1800943de  mov     qword ptr [rbp+210h+var_220+8], rax
0x1800943e2  lea     rax, aPoolAllocateTy; "Pool.Allocate(&TypeNameAttributeValueBu"...
0x1800943e9  mov     [rbp+210h+var_208], rax
0x1800943ed  jmp     short loc_18009439D
0x1800943ef  lea     rdx, [rsp+310h+var_2B8]; struct IdentityParser::CLexeme *
0x1800943f4  lea     rcx, [rbp+210h+var_D0]; this
0x1800943fb  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x180094400  test    eax, eax
0x180094402  js      loc_180094A33
0x180094408  cmp     dword ptr [rsp+310h+var_2B8], 1
0x18009440d  jz      short loc_180094447
0x18009440f  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180094416  mov     [rbp+210h+var_1C8], 2C3h
0x18009441e  mov     [rbp+210h+var_1D8], rax
0x180094422  lea     rdx, [rbp+210h+var_1D8]
0x180094426  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x18009442d  mov     r8d, 0C000000Dh
0x180094433  mov     [rbp+210h+var_1D0], rax
0x180094437  lea     rax, aCurrentlexemeM_1; "CurrentLexeme.m_LexemeType == IdentityP"...
0x18009443e  mov     [rbp+210h+var_1C0], rax
0x180094442  jmp     loc_180094A27
0x180094447  movups  xmm6, xmmword ptr [rsp+310h+var_2A8]
0x18009444c  mov     r14, qword ptr [rsp+310h+var_2B8+8]
0x180094451  lea     rdx, [rsp+310h+var_2B8]; struct IdentityParser::CLexeme *
0x180094456  movups  xmm0, [rbp+210h+var_270+8]
0x18009445a  mov     rax, qword ptr [rbp+210h+var_270]
0x18009445e  lea     rcx, [rbp+210h+var_D0]; this
0x180094465  movdqu  [rbp+210h+var_270+8], xmm6
0x18009446a  mov     qword ptr [rsp+310h+var_2B8+8], rax
0x18009446f  movdqu  xmmword ptr [rsp+310h+var_2A8], xmm0
0x180094475  mov     qword ptr [rbp+210h+var_270], r14
0x180094479  mov     [rbp+210h+var_278], 1
0x180094480  mov     dword ptr [rsp+310h+var_2B8], esi
0x180094484  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x180094489  test    eax, eax
0x18009448b  js      loc_180094A33
0x180094491  mov     ecx, dword ptr [rsp+310h+var_2B8]
0x180094495  lea     eax, [rcx-2]
0x180094498  test    eax, 0FFFFFFFDh
0x18009449d  jz      short loc_1800944D7
0x18009449f  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x1800944a6  mov     [rbp+210h+var_1A8], 2CEh
0x1800944ae  mov     [rbp+210h+var_1B8], rax
0x1800944b2  lea     rdx, [rbp+210h+var_1B8]
0x1800944b6  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x1800944bd  mov     r8d, 0C000000Dh
0x1800944c3  mov     [rbp+210h+var_1B0], rax
0x1800944c7  lea     rax, aCurrentlexemeM; "((CurrentLexeme.m_LexemeType == Identit"...
0x1800944ce  mov     [rbp+210h+var_1A0], rax
0x1800944d2  jmp     loc_180094A27
0x1800944d7  mov     r15, [rsp+310h+var_2C8]
0x1800944dc  mov     rdi, rsi
0x1800944df  cmp     ecx, 4
0x1800944e2  jnz     short loc_180094509
0x1800944e4  mov     dl, sil
0x1800944e7  mov     rsi, [rsp+310h+var_2C0]
0x1800944ec  movups  xmm0, xmmword ptr [rsi+8]
0x1800944f0  mov     rax, [rsi]
0x1800944f3  mov     [rsi], r14
0x1800944f6  movdqu  [rbp+210h+var_270+8], xmm0
0x1800944fb  mov     qword ptr [rbp+210h+var_270], rax
0x1800944ff  movdqu  xmmword ptr [rsi+8], xmm6
0x180094504  jmp     loc_180094ABD
0x180094509  cmp     ecx, 2
0x18009450c  jnz     loc_180094B17
0x180094512  lea     rdx, [rsp+310h+var_2B8]; struct IdentityParser::CLexeme *
0x180094517  lea     rcx, [rbp+210h+var_D0]; this
0x18009451e  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x180094523  test    eax, eax
0x180094525  js      loc_180094A33
0x18009452b  cmp     dword ptr [rsp+310h+var_2B8], 1
0x180094530  jz      short loc_18009456D
0x180094532  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180094539  mov     [rbp+210h+var_188], 2DAh
0x180094544  mov     [rbp+210h+var_198], rax
0x180094548  lea     rdx, [rbp+210h+var_198]
0x18009454c  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x180094553  mov     [rbp+210h+var_190], rax
0x18009455a  lea     rax, aCurrentlexemeM_1; "CurrentLexeme.m_LexemeType == IdentityP"...
0x180094561  mov     [rbp+210h+var_180], rax
0x180094568  jmp     loc_180094A21
0x18009456d  movups  xmm0, xmmword ptr [r15+8]
0x180094572  mov     rax, [r15]
0x180094575  lea     rdx, [rsp+310h+var_2B8]; struct IdentityParser::CLexeme *
0x18009457a  mov     rsi, [rsp+310h+var_2C0]
0x18009457f  mov     [r15], r14
0x180094582  movdqu  xmmword ptr [r15+8], xmm6
0x180094588  mov     qword ptr [rbp+210h+var_270], rax
0x18009458c  mov     rcx, [rsi]
0x18009458f  movups  xmm1, xmmword ptr [rsi+8]
0x180094593  mov     rax, qword ptr [rsp+310h+var_2B8+8]
0x180094598  movdqu  [rbp+210h+var_270+8], xmm0
0x18009459d  mov     qword ptr [rsp+310h+var_2B8+8], rcx
0x1800945a2  lea     rcx, [rbp+210h+var_D0]; this
0x1800945a9  movups  xmm0, xmmword ptr [rsp+310h+var_2A8]
0x1800945ae  mov     [rsi], rax
0x1800945b1  movdqu  xmmword ptr [rsp+310h+var_2A8], xmm1
0x1800945b7  movdqu  xmmword ptr [rsi+8], xmm0
0x1800945bc  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x1800945c1  test    eax, eax
0x1800945c3  js      loc_180094A33
0x1800945c9  mov     r14d, dword ptr [rsp+310h+var_2B8]
0x1800945ce  cmp     r14d, 4
0x1800945d2  jnz     short loc_1800945DB
0x1800945d4  mov     dl, 1
0x1800945d6  jmp     loc_180094ABD
0x1800945db  cmp     r14d, 2
0x1800945df  jz      loc_180094674
0x1800945e5  cmp     r14d, 3
0x1800945e9  jz      short loc_18009462C
0x1800945eb  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x1800945f2  mov     [rbp+210h+var_168], 2F2h
0x1800945fd  mov     [rbp+210h+var_178], rax
0x180094604  lea     rdx, [rbp+210h+var_178]
0x18009460b  lea     rax, aWindowsIdentit_17; "Windows::Identity::Rtl::Implementation:"...
0x180094612  mov     [rbp+210h+var_170], rax
0x180094619  lea     rax, aCurrentlexemeM_0; "((CurrentLexeme.m_LexemeType == Identit"...
0x180094620  mov     [rbp+210h+var_160], rax
0x180094627  jmp     loc_180094A21
0x18009462c  movups  xmm0, xmmword ptr [rsi]
0x18009462f  xor     al, al
0x180094631  mov     r8b, 1
0x180094634  movsd   xmm1, qword ptr [rsi+10h]
0x180094639  movsd   xmm2, [rbp+210h+var_228]
0x18009463e  movups  xmmword ptr [rsi], xmm7
0x180094641  mov     byte ptr [rsp+310h+var_2D0], al
0x180094645  movsd   qword ptr [rsi+10h], xmm2
0x18009464a  movups  xmm3, xmmword ptr [rsi]
0x18009464d  movups  [rbp+210h+var_238], xmm0
0x180094651  movups  xmm0, xmmword ptr [r15]
0x180094655  movsd   [rbp+210h+var_228], xmm1
0x18009465a  movups  xmmword ptr [rsi], xmm0
0x18009465d  movsd   xmm1, qword ptr [r15+10h]
0x180094663  movsd   qword ptr [rsi+10h], xmm1
0x180094668  movups  xmmword ptr [r15], xmm3
0x18009466c  movsd   qword ptr [r15+10h], xmm2
0x180094672  jmp     short loc_18009467C
0x180094674  xor     r8b, r8b
0x180094677  mov     byte ptr [rsp+310h+var_2D0], 1
0x18009467c  mov     r12, qword ptr [rbp+210h+var_250]
0x180094680  cmp     r14d, 4
0x180094684  jz      loc_180094AB5
0x18009468a  test    r8b, r8b
0x18009468d  jnz     short loc_1800946F7
0x18009468f  lea     rdx, [rbp+210h+var_278]; struct IdentityParser::CLexeme *
0x180094693  lea     rcx, [rbp+210h+var_D0]; this
0x18009469a  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x18009469f  test    eax, eax
0x1800946a1  js      loc_180094A33
0x1800946a7  cmp     [rbp+210h+var_278], 1
0x1800946ab  jnz     loc_180094902
0x1800946b1  lea     rdx, [rsp+310h+var_2B8]; struct IdentityParser::CLexeme *
0x1800946b6  lea     rcx, [rbp+210h+var_D0]; this
0x1800946bd  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x1800946c2  test    eax, eax
0x1800946c4  js      loc_180094A33
0x1800946ca  cmp     dword ptr [rsp+310h+var_2B8], 3
0x1800946cf  jnz     loc_1800948C1
0x1800946d5  movups  xmm1, [rbp+210h+var_238+8]
0x1800946d9  mov     rcx, qword ptr [rbp+210h+var_238]
0x1800946dd  movups  xmm0, [rbp+210h+var_270+8]
0x1800946e1  mov     rax, qword ptr [rbp+210h+var_270]
0x1800946e5  movdqu  [rbp+210h+var_270+8], xmm1
0x1800946ea  mov     qword ptr [rbp+210h+var_238], rax
0x1800946ee  movdqu  [rbp+210h+var_238+8], xmm0
0x1800946f3  mov     qword ptr [rbp+210h+var_270], rcx
0x1800946f7  lea     rdx, [rsp+310h+var_2B8]; struct IdentityParser::CLexeme *
0x1800946fc  lea     rcx, [rbp+210h+var_D0]; this
0x180094703  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x180094708  test    eax, eax
0x18009470a  js      loc_180094A33
0x180094710  cmp     dword ptr [rsp+310h+var_2B8], 1
0x180094715  jnz     loc_1800949E5
0x18009471b  movups  xmm1, [rbp+210h+var_250+8]
0x18009471f  mov     rax, r12
0x180094722  mov     r12, qword ptr [rsp+310h+var_2B8+8]
0x180094727  movups  xmm0, xmmword ptr [rsp+310h+var_2A8]
0x18009472c  lea     rdx, [rsp+310h+var_2B8]; struct IdentityParser::CLexeme *
0x180094731  mov     qword ptr [rbp+210h+var_250], r12
0x180094735  lea     rcx, [rbp+210h+var_D0]; this
0x18009473c  mov     qword ptr [rsp+310h+var_2B8+8], rax
0x180094741  movdqu  [rbp+210h+var_250+8], xmm0
0x180094746  movdqu  xmmword ptr [rsp+310h+var_2A8], xmm1
0x18009474c  call    ?GetNextLexeme@CLexicalAnalyzer@IdentityParser@@QEAAJPEAVCLexeme@2@@Z; IdentityParser::CLexicalAnalyzer::GetNextLexeme(IdentityParser::CLexeme *)
0x180094751  test    eax, eax
0x180094753  js      loc_180094A33
0x180094759  mov     r14d, dword ptr [rsp+310h+var_2B8]
0x18009475e  lea     eax, [r14-2]
0x180094762  test    eax, 0FFFFFFFDh
0x180094767  jnz     loc_1800949BA
0x18009476d  xor     eax, eax
0x18009476f  lea     rdx, [rbp+210h+var_238]
0x180094773  mov     [rbp+210h+var_1E8], rax
0x180094777  xor     r9d, r9d
0x18009477a  mov     [rbp+210h+var_210], rax
0x18009477e  xorps   xmm0, xmm0
0x180094781  lea     rax, [rbp+210h+var_220]
0x180094785  xorps   xmm1, xmm1
0x180094788  mov     [rsp+310h+var_2E0], rax
0x18009478d  xor     r8d, r8d
0x180094790  lea     rax, [rbp+210h+var_1F8]
0x180094794  mov     [rsp+310h+var_2E8], rax
0x180094799  lea     ecx, [r9+2]
0x18009479d  mov     [rsp+310h+var_2F0], 3Ah ; ':'
0x1800947a6  movups  [rbp+210h+var_1F8], xmm0
0x1800947aa  movups  [rbp+210h+var_220], xmm1
0x1800947ae  call    RtlSplitLUnicodeString
0x1800947b3  test    eax, eax
0x1800947b5  js      loc_180094A33
0x1800947bb  cmp     qword ptr [rbp+210h+var_220], rbx
0x1800947bf  jnz     short loc_1800947D8
0x1800947c1  movups  xmm0, [rbp+210h+var_1F8]
0x1800947c5  xor     r13d, r13d
0x1800947c8  movsd   xmm1, [rbp+210h+var_1E8]
0x1800947cd  movups  [rbp+210h+var_220], xmm0
0x1800947d1  movsd   [rbp+210h+var_210], xmm1
0x1800947d6  jmp     short loc_18009480C
0x1800947d8  lea     rdx, [rsp+310h+var_2C8]
  ... truncated ...
```

# ActionListParser::ParseInstallPackage(XmlParserGenerator::ParserState *,ActionListParser::InstallPackage * *)

- ea: `0x18005d3b8`
- end: `0x18005e10b`
- name: `?ParseInstallPackage@ActionListParser@@YAJPEAUParserState@XmlParserGenerator@@PEAPEAUInstallPackage@1@@Z`
- size: `3411`
- prototype: `__int64 __fastcall(ActionListParser *__hidden this, struct XmlParserGenerator::ParserState *, struct ActionListParser::InstallPackage **)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180057e08`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x1800497c0`
- `0x180057154`
- `0x180057d18`
- `0x180059af4`
- `0x18005d3b8`
- `0x18005e114`
- `0x18005e49c`
- `0x1800629d4`
- `0x1800630c4`
- `0x1800633dc`
- `0x180186df4`
- `0x18018d23c`
- `0x18018d3f8`
- `0x18018d4d0`
- `0x18018d614`
- `0x18018d69c`
- `0x18018d9d8`
- `0x18018da08`
- `0x18018db1c`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005d5a5`
- `ntdll!RtlRaiseStatus` at `0x18005e046`
- `ntdll!RtlRaiseStatus` at `0x18005d5a5`
- `ntdll!RtlRaiseStatus` at `0x18005e046`

## string_xrefs

- `0x18005d619`: `FilePath`
- `0x18005d57d`: `*ppObject = State->m_pAllocator->Allocate<InstallPackage>()`
- `0x18005d632`: `SourcePath`
- `0x18005d64b`: `ExpressPackagePath`
- `0x18005d5e6`: `InstalledSize`
- `0x18005df18`: `Token`
- `0x18005d65e`: `ExpressMetadataContainerPath`
- `0x18005d568`: `ActionListParser::ParseInstallPackage`
- `0x18005d80c`: `LicensePath`
- `0x18005df02`: `InstallPayload`

## pseudocode

```c
__int64 __fastcall ActionListParser::ParseInstallPackage(
        ActionListParser *this,
        struct XmlParserGenerator::ParserState *a2,
        struct ActionListParser::InstallPackage **a3)
{
  ActionListParser *v4; // rdi
  __int64 v5; // rdx
  __int64 result; // rax
  __int64 v7; // rax
  char v8; // si
  struct XmlParserGenerator::ParserState *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // r12d
  NTSTATUS v13; // eax
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // rsi
  __int64 v16; // xmm1_8
  __int128 v17; // xmm0
  __int64 v18; // rdx
  __int64 v19; // rcx
  char v20; // r15
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rsi
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rsi
  __int64 v27; // r9
  unsigned __int64 v28; // rsi
  unsigned __int64 v29; // rsi
  unsigned __int64 v30; // rsi
  unsigned __int64 v31; // rsi
  unsigned __int64 v32; // rsi
  unsigned __int64 v33; // rsi
  unsigned __int64 v34; // rsi
  struct XmlParserGenerator::ParserState *v35; // rdx
  int v36; // eax
  struct XmlParserGenerator::ParserState *v37; // rsi
  struct XmlParserGenerator::ParserState *v38; // r15
  struct XmlParserGenerator::ParserState *v39; // rdx
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rax
  unsigned __int64 *v42; // [rsp+28h] [rbp-D8h]
  char v43; // [rsp+30h] [rbp-D0h] BYREF
  char v44; // [rsp+31h] [rbp-CFh] BYREF
  char v45; // [rsp+32h] [rbp-CEh]
  unsigned __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v47; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  int v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-60h]
  const char *v58; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v59[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  const char *v62; // [rsp+D0h] [rbp-30h]
  __int128 v63; // [rsp+D8h] [rbp-28h]
  __int64 v64; // [rsp+E8h] [rbp-18h]
  __int64 v65; // [rsp+F0h] [rbp-10h]
  const char *v66; // [rsp+F8h] [rbp-8h]
  __int128 v67; // [rsp+100h] [rbp+0h]
  __int64 v68; // [rsp+110h] [rbp+10h]
  __int64 v69; // [rsp+118h] [rbp+18h]
  const char *v70; // [rsp+120h] [rbp+20h]
  unsigned __int64 v71[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v72; // [rsp+140h] [rbp+40h]
  __int64 v73; // [rsp+148h] [rbp+48h]
  const char *v74; // [rsp+150h] [rbp+50h]
  __int128 v75; // [rsp+158h] [rbp+58h]
  __int64 v76; // [rsp+168h] [rbp+68h]
  __int64 v77; // [rsp+170h] [rbp+70h]
  const char *v78; // [rsp+178h] [rbp+78h]
  __int128 v79; // [rsp+180h] [rbp+80h]
  __int64 v80; // [rsp+190h] [rbp+90h]
  __int64 v81; // [rsp+198h] [rbp+98h]
  const char *v82; // [rsp+1A0h] [rbp+A0h]
  __int128 v83; // [rsp+1A8h] [rbp+A8h]
  __int64 v84; // [rsp+1B8h] [rbp+B8h]
  __int64 v85; // [rsp+1C0h] [rbp+C0h]
  const char *v86; // [rsp+1C8h] [rbp+C8h]
  __int128 v87; // [rsp+1D0h] [rbp+D0h]
  __int64 v88; // [rsp+1E0h] [rbp+E0h]
  __int64 v89; // [rsp+1E8h] [rbp+E8h]
  const char *v90; // [rsp+1F0h] [rbp+F0h]
  __int128 v91; // [rsp+1F8h] [rbp+F8h]
  __int64 v92; // [rsp+208h] [rbp+108h]
  __int64 v93; // [rsp+210h] [rbp+110h]
  const char *v94; // [rsp+218h] [rbp+118h]
  __int128 v95; // [rsp+220h] [rbp+120h]
  __int64 v96; // [rsp+230h] [rbp+130h]
  __int64 v97; // [rsp+238h] [rbp+138h]
  const char *v98; // [rsp+240h] [rbp+140h]
  __int128 v99; // [rsp+248h] [rbp+148h]
  __int64 v100; // [rsp+258h] [rbp+158h]
  __int64 v101; // [rsp+260h] [rbp+160h]
  const char *v102; // [rsp+268h] [rbp+168h]
  __int128 v103; // [rsp+270h] [rbp+170h]
  __int64 v104; // [rsp+280h] [rbp+180h]
  __int64 v105; // [rsp+288h] [rbp+188h]
  const char *v106; // [rsp+290h] [rbp+190h]
  __int128 v107; // [rsp+298h] [rbp+198h]
  __int64 v108; // [rsp+2A8h] [rbp+1A8h]
  __int64 v109; // [rsp+2B0h] [rbp+1B0h]
  const char *v110; // [rsp+2B8h] [rbp+1B8h]
  __int128 v111; // [rsp+2C0h] [rbp+1C0h]
  __int64 v112; // [rsp+2D0h] [rbp+1D0h]
  __int64 v113; // [rsp+2D8h] [rbp+1D8h]
  const char *v114; // [rsp+2E0h] [rbp+1E0h]
  __int128 v115; // [rsp+2E8h] [rbp+1E8h]
  __int64 v116; // [rsp+2F8h] [rbp+1F8h]
  __int64 v117; // [rsp+300h] [rbp+200h]
  const char *v118; // [rsp+308h] [rbp+208h]
  __int128 v119; // [rsp+310h] [rbp+210h]
  __int64 v120; // [rsp+320h] [rbp+220h]
  __int64 v121; // [rsp+328h] [rbp+228h]
  const char *v122; // [rsp+330h] [rbp+230h]
  __int128 v123; // [rsp+338h] [rbp+238h]
  __int64 v124; // [rsp+348h] [rbp+248h]
  __int64 v125; // [rsp+350h] [rbp+250h]
  const char *v126; // [rsp+358h] [rbp+258h]
  __int128 v127; // [rsp+360h] [rbp+260h]
  __int64 v128; // [rsp+370h] [rbp+270h]
  __int64 v129; // [rsp+378h] [rbp+278h]
  const char *v130; // [rsp+380h] [rbp+280h]
  __int128 v131; // [rsp+388h] [rbp+288h]
  __int64 v132; // [rsp+398h] [rbp+298h]
  __int64 v133; // [rsp+3A0h] [rbp+2A0h]
  const char *v134; // [rsp+3A8h] [rbp+2A8h]
  __int128 v135; // [rsp+3B0h] [rbp+2B0h]
  __int64 v136; // [rsp+3C0h] [rbp+2C0h]
  __int64 v137; // [rsp+3C8h] [rbp+2C8h]
  const char *v138; // [rsp+3D0h] [rbp+2D0h]
  __int128 v139; // [rsp+3E0h] [rbp+2E0h]
  char v140; // [rsp+3F0h] [rbp+2F0h]

  v4 = this;
  if ( *((_DWORD *)this + 2282) != 3 )
    goto LABEL_2;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 1173) + 8LL))(
         *((_QWORD *)this + 1173),
         320,
         8);
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 0;
    *(_QWORD *)(v7 + 32) = 0;
    *(_OWORD *)(v7 + 40) = 0;
    *(_QWORD *)(v7 + 56) = 0;
    *(_OWORD *)(v7 + 64) = 0;
    *(_QWORD *)(v7 + 80) = 0;
    *(_OWORD *)(v7 + 88) = 0;
    *(_QWORD *)(v7 + 104) = 0;
    *(_OWORD *)(v7 + 112) = 0;
    *(_QWORD *)(v7 + 128) = 0;
    *(_QWORD *)(v7 + 168) = "MainOS";
    *(_DWORD *)(v7 + 136) = 0;
    *(_QWORD *)(v7 + 140) = 5;
    *(_QWORD *)(v7 + 152) = 6;
    *(_QWORD *)(v7 + 160) = 7;
    *(_OWORD *)(v7 + 176) = 0;
    *(_QWORD *)(v7 + 192) = 0;
    *(_OWORD *)(v7 + 200) = 0;
    *(_QWORD *)(v7 + 216) = 0;
    *(_QWORD *)(v7 + 224) = 5;
    *(_OWORD *)(v7 + 232) = 0;
    *(_QWORD *)(v7 + 248) = 0;
    *(_QWORD *)(v7 + 256) = 0;
    *(_QWORD *)(v7 + 264) = 0;
    *(_QWORD *)(v7 + 272) = 0;
    *(_QWORD *)(v7 + 280) = 0;
    *(_QWORD *)(v7 + 288) = 0;
    *(_QWORD *)(v7 + 296) = 0;
    *(_QWORD *)(v7 + 304) = 0;
    *(_DWORD *)(v7 + 312) = 0;
    *(_WORD *)(v7 + 316) = 0;
    *(_BYTE *)(v7 + 318) = 0;
  }
  else
  {
    v7 = 0;
  }
  *(_QWORD *)a2 = v7;
  if ( !v7 )
  {
    v57 = 3148;
    *(_QWORD *)&v56 = "onecore\\base\\servicing\\actionlist\\lib\\loadactionlist\\objfre\\amd64\\actionlistparser.cpp";
    *((_QWORD *)&v56 + 1) = "ActionListParser::ParseInstallPackage";
    v58 = "*ppObject = State->m_pAllocator->Allocate<InstallPackage>()";
    RtlReportErrorOrigination(&v56, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
    return 3221225495LL;
  }
  if ( *((_DWORD *)v4 + 2282) != 3 )
    RtlRaiseStatus(-1073741595);
  v8 = *((_BYTE *)v4 + 9268);
  v9 = (struct XmlParserGenerator::ParserState *)*((unsigned int *)v4 + 2316);
  v140 = 0;
  v72 = 7;
  v74 = "Keyform";
  v78 = "InstalledSize";
  LODWORD(a3) = 10;
  v100 = 6;
  v101 = 7;
  v82 = "StagedSize";
  v104 = 6;
  v86 = "FilePath";
  v105 = 7;
  v90 = "SourcePath";
  v45 = v8;
  v94 = "ExpressPackagePath";
  v98 = "ExpressMetadataContainerPath";
  v102 = "Action";
  v106 = "Reason";
  v110 = "PayloadType";
  v114 = "Partition";
  v118 = "BinaryPartition";
  v122 = "FeatureId";
  v49 = (int)v9;
  v139 = 0;
  v73 = 8;
  *(_OWORD *)v71 = *(_OWORD *)&off_1801C4200;
  v76 = 13;
  v75 = *(_OWORD *)&off_1801C4200;
  v77 = 14;
  v79 = *(_OWORD *)&off_1801C4200;
  v80 = 10;
  v81 = 11;
  v83 = *(_OWORD *)&off_1801C4200;
  v84 = 8;
  v85 = 9;
  v87 = *(_OWORD *)&off_1801C4200;
  v88 = 10;
  v89 = 11;
  v91 = *(_OWORD *)&off_1801C4200;
  v92 = 18;
  v93 = 19;
  v95 = *(_OWORD *)&off_1801C4200;
  v96 = 28;
  v97 = 29;
  v99 = *(_OWORD *)&off_1801C4200;
  v108 = 11;
  v103 = *(_OWORD *)&off_1801C4200;
  v109 = 12;
  v107 = *(_OWORD *)&off_1801C4200;
  v112 = 9;
  v111 = *(_OWORD *)&off_1801C4200;
  v113 = 10;
  v115 = *(_OWORD *)&off_1801C4200;
  v116 = 15;
  v117 = 16;
  v119 = *(_OWORD *)&off_1801C4200;
  v120 = 9;
  v121 = 10;
  v123 = *(_OWORD *)&off_1801C4200;
  v124 = 12;
  v126 = "CapabilityId";
  v130 = "Type";
  v134 = "RebootRequired";
  v138 = "LicensePath";
  v10 = *((_QWORD *)v4 + 1177);
  v137 = 12;
  v11 = *((_QWORD *)v4 + 1176);
  v125 = 13;
  v128 = 4;
  v129 = 5;
  v132 = 14;
  v133 = 15;
  v136 = 11;
  v127 = *(_OWORD *)&off_1801C4200;
  v131 = *(_OWORD *)&off_1801C4200;
  v135 = *(_OWORD *)&off_1801C4200;
  if ( v11 != v10 )
  {
    do
      v10 -= 8;
    while ( v11 != v10 );
    *((_QWORD *)v4 + 1177) = v10;
  }
  v12 = 0;
  if ( (_DWORD)v9 )
  {
    while ( 1 )
    {
      v46 = 0;
      v13 = RtlIndexIntoGrowingList((ActionListParser *)((char *)v4 + 3456), v12);
      if ( v13 < 0 )
        RtlRaiseStatus(v13);
      v14 = v46;
      if ( *(_BYTE *)(v46 + 104) || *(_BYTE *)(v46 + 105) )
        goto LABEL_81;
      v53 = *(_QWORD *)(v46 + 32);
      v54 = v53;
      v55 = *(_QWORD *)(v46 + 24);
      v50 = *(_QWORD *)(v46 + 8);
      v51 = v50;
      v52 = *(_QWORD *)v46;
      v46 = 0;
      result = XmlParserGenerator::MatchNamespaceAndNameAgainstList(
                 (XmlParserGenerator *)&v53,
                 (const struct _LUTF8_STRING *)&v50,
                 (const struct _LUTF8_STRING *)0x11,
                 (unsigned __int64)v71,
                 (const struct XmlParserGenerator::NamespaceNamePair *const)&v46,
                 v42);
      if ( (int)result < 0 )
        return result;
      v15 = v46;
      if ( v46 >= 0x11 )
      {
        if ( (*((_BYTE *)v4 + 9400) & 2) == 0 )
        {
          v5 = 3221225636LL;
          goto LABEL_116;
        }
        goto LABEL_80;
      }
      this = v4;
      if ( *((_BYTE *)&v139 + v46) )
      {
        v5 = 3221225636LL;
        goto LABEL_3;
      }
      v16 = *(_QWORD *)(v14 + 64);
      *((_BYTE *)&v139 + v46) = 1;
      v47 = 0;
      v17 = *(_OWORD *)(v14 + 48);
      v48 = 0;
      v44 = 0;
      v56 = v17;
      v57 = v16;
      result = XmlParserGenerator::ParserState::Utf8ExtentToExpandedString(v4, &v56, &v47, &v44);
      if ( (int)result < 0 )
        return result;
      v43 = 0;
      v20 = 0;
      if ( v15 > 8 )
      {
        v28 = v15 - 9;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              v31 = v30 - 1;
              if ( v31 )
              {
                v32 = v31 - 1;
                if ( v32 )
                {
                  v33 = v32 - 1;
                  if ( v33 )
                  {
                    v34 = v33 - 1;
                    if ( v34 )
                    {
                      if ( v34 != 1 )
                        goto LABEL_77;
                      v42 = (unsigned __int64 *)&v43;
                      result = XmlParserGenerator::ParserState::ParseString(
                                 &v43,
                                 *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                                 *((_QWORD *)v4 + 1173),
                                 &v47,
                                 *(_QWORD *)a2 + 232LL);
                      if ( (int)result < 0 )
                        return result;
                      *(_BYTE *)(*(_QWORD *)a2 + 318LL) = 1;
                    }
                    else
                    {
                      result = ActionListParser::ParseRebootRequiredType(v19, v18, &v47, *(_QWORD *)a2 + 228LL, &v43);
                      if ( (int)result < 0 )
                        return result;
                      *(_BYTE *)(*(_QWORD *)a2 + 317LL) = 1;
                    }
                  }
                  else
                  {
                    result = ActionListParser::ParseReasonType(v19, v18, &v47, *(_QWORD *)a2 + 224LL, &v43);
                    if ( (int)result < 0 )
                      return result;
                    *(_BYTE *)(*(_QWORD *)a2 + 316LL) = 1;
                  }
                }
                else
                {
                  v42 = (unsigned __int64 *)&v43;
                  result = XmlParserGenerator::ParserState::ParseString(
                             &v43,
                             *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                             *((_QWORD *)v4 + 1173),
                             &v47,
                             *(_QWORD *)a2 + 200LL);
                  if ( (int)result < 0 )
                    return result;
                  *(_BYTE *)(*(_QWORD *)a2 + 315LL) = 1;
                }
              }
              else
              {
                v42 = (unsigned __int64 *)&v43;
                result = XmlParserGenerator::ParserState::ParseString(
                           &v43,
                           *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                           *((_QWORD *)v4 + 1173),
                           &v47,
                           *(_QWORD *)a2 + 176LL);
                if ( (int)result < 0 )
                  return result;
                *(_BYTE *)(*(_QWORD *)a2 + 314LL) = 1;
              }
            }
            else
            {
              result = XmlParserGenerator::ParseBool(v19, v18, &v47, *(_QWORD *)a2 + 304LL, &v43);
              if ( (int)result < 0 )
                return result;
              *(_BYTE *)(*(_QWORD *)a2 + 313LL) = 1;
            }
          }
          else
          {
            v42 = (unsigned __int64 *)&v43;
            result = XmlParserGenerator::ParserState::ParseString(
                       &v43,
                       *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                       *((_QWORD *)v4 + 1173),
                       &v47,
                       *(_QWORD *)a2 + 152LL);
            if ( (int)result < 0 )
              return result;
            *(_BYTE *)(*(_QWORD *)a2 + 312LL) = 1;
          }
        }
        else
        {
          result = CompositionDatabaseParser::ParsePackageUpdateType(v19, v18, &v47, *(_QWORD *)a2 + 144LL, &v43);
          if ( (int)result < 0 )
            return result;
          *(_BYTE *)(*(_QWORD *)a2 + 311LL) = 1;
        }
      }
      else if ( v15 == 8 )
      {
        result = ActionListParser::ParseReasonType(v19, v18, &v47, *(_QWORD *)a2 + 140LL, &v43);
        if ( (int)result < 0 )
          return result;
        *(_BYTE *)(*(_QWORD *)a2 + 310LL) = 1;
      }
      else
      {
        if ( !v15 )
        {
          v42 = (unsigned __int64 *)&v43;
          result = XmlParserGenerator::ParserState::ParseString(
                     &v43,
                     *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                     *((_QWORD *)v4 + 1173),
                     &v47,
                     *(_QWORD *)a2);
          goto LABEL_47;
        }
        v21 = v15 - 1;
        if ( !v21 )
        {
          v27 = *(_QWORD *)a2 + 24LL;
LABEL_44:
          result = XmlParserGenerator::ParseInt_unsigned___int64_(v19, v18, (unsigned int)&v47, v27, (__int64)&v43);
LABEL_47:
          if ( (int)result < 0 )
            return result;
          v20 = 1;
          goto LABEL_75;
        }
        v22 = v21 - 1;
        if ( !v22 )
        {
          v27 = *(_QWORD *)a2 + 32LL;
          goto LABEL_44;
        }
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                if ( v26 != 1 )
                  goto LABEL_77;
                result = ActionListParser::ParseActionType(v19, v18, &v47, *(_QWORD *)a2 + 136LL, &v43);
                if ( (int)result < 0 )
                  return result;
                *(_BYTE *)(*(_QWORD *)a2 + 309LL) = 1;
              }
              else
              {
                v42 = (unsigned __int64 *)&v43;
                result = XmlParserGenerator::ParserState::ParseString(
                           &v43,
                           *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                           *((_QWORD *)v4 + 1173),
                           &v47,
                           *(_QWORD *)a2 + 112LL);
                if ( (int)result < 0 )
                  return result;
                *(_BYTE *)(*(_QWORD *)a2 + 308LL) = 1;
              }
            }
            else
            {
              v42 = (unsigned __int64 *)&v43;
              result = XmlParserGenerator::ParserState::ParseString(
                         &v43,
                         *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                         *((_QWORD *)v4 + 1173),
                         &v47,
                         *(_QWORD *)a2 + 88LL);
              if ( (int)result < 0 )
                return result;
              *(_BYTE *)(*(_QWORD *)a2 + 307LL) = 1;
            }
          }
          else
          {
            v42 = (unsigned __int64 *)&v43;
            result = XmlParserGenerator::ParserState::ParseString(
                       &v43,
                       *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                       *((_QWORD *)v4 + 1173),
                       &v47,
                       *(_QWORD *)a2 + 64LL);
            if ( (int)result < 0 )
              return result;
            *(_BYTE *)(*(_QWORD *)a2 + 306LL) = 1;
          }
        }
        else
        {
          v42 = (unsigned __int64 *)&v43;
          result = XmlParserGenerator::ParserState::ParseString(
                     &v43,
                     *((_DWORD *)v4 + 2350) | (unsigned int)(v44 != 0),
                     *((_QWORD *)v4 + 1173),
                     &v47,
                     *(_QWORD *)a2 + 40LL);
          if ( (int)result < 0 )
            return result;
          *(_BYTE *)(*(_QWORD *)a2 + 305LL) = 1;
        }
      }
LABEL_75:
      if ( !v43 )
      {
        if ( v20 )
          goto LABEL_78;
LABEL_77:
        if ( (*((_BYTE *)v4 + 9400) & 2) == 0 )
        {
LABEL_78:
          v5 = 3221225657LL;
          goto LABEL_116;
        }
LABEL_80:
        result = XmlParserGenerator::ParserState::ValidateDuplicateUnknownAttributes(
                   v4,
                   (const struct _LUTF8_STRING *)&v53,
                   (const struct _LUTF8_STRING *)&v50);
        if ( (int)result < 0 )
          return result;
      }
LABEL_81:
      if ( ++v12 == v49 )
      {
        v8 = v45;
        break;
      }
    }
  }
  if ( !(_BYTE)v139 || !BYTE1(v139) || !BYTE2(v139) )
  {
    v5 = 3221226021LL;
LABEL_116:
    this = v4;
    goto LABEL_3;
  }
  result = XmlParserGenerator::MoveToNextSemanticNode(v4, v9, (bool)a3);
  if ( (int)result < 0 )
    return result;
  v60 = 14;
  *(_QWORD *)&v139 = 0;
  DWORD2(v139) = 0;
  v62 = "InstallPayload";
  v66 = "CustomInformation";
  v70 = "Token";
  v61 = 15;
  v64 = 17;
  v65 = 18;
  v68 = 5;
  v69 = 6;
  *(_OWORD *)v59 = *(_OWORD *)&off_1801C41F0;
  v63 = *(_OWORD *)&off_1801C41F0;
  v67 = *(_OWORD *)&off_1801C41F0;
  if ( v8 )
    return 0;
  v36 = *((_DWORD *)v4 + 2282);
  if ( v36 == 3 )
  {
    v37 = (struct XmlParserGenerator::ParserState *)(*(_QWORD *)a2 + 256LL);
    v38 = (struct XmlParserGenerator::ParserState *)(*(_QWORD *)a2 + 280LL);
    do
    {
      v50 = *((_QWORD *)v4 + 1152);
      v51 = v50;
      v52 = *((_QWORD *)v4 + 1151);
      v53 = *((_QWORD *)v4 + 1149);
      v54 = v53;
      v55 = *((_QWORD *)v4 + 1148);
      v46 = 0;
      result = XmlParserGenerator::MatchNamespaceAndNameAgainstList(
                 (XmlParserGenerator *)&v50,
                 (const struct _LUTF8_STRING *)&v53,
                 (const struct _LUTF8_STRING *)3,
                 (unsigned __int64)v59,
                 (const struct XmlParserGenerator::NamespaceNamePair *const)&v46,
                 v42);
      if ( (int)result < 0 )
        return result;
      v40 = v46;
      if ( v46 < 3 )
        ++*((_DWORD *)&v139 + v46);
      this = v4;
      if ( !v40 )
      {
        result = ActionListParser::ParseInstallPayload(v4, v37, a3);
        if ( (int)result < 0 )
          return result;
        v37 = (struct XmlParserGenerator::ParserState *)(*(_QWORD *)v37 + 128LL);
        ++*(_QWORD *)(*(_QWORD *)a2 + 264LL);
        goto LABEL_109;
      }
      v41 = v40 - 1;
      if ( v41 )
      {
        if ( v41 == 1 )
        {
          result = ActionListParser::ParseInstallPackageToken(v4, v38, a3);
          if ( (int)result < 0 )
            return result;
          v38 = (struct XmlParserGenerator::ParserState *)(*(_QWORD *)v38 + 8LL);
          ++*(_QWORD *)(*(_QWORD *)a2 + 288LL);
          goto LABEL_109;
        }
        if ( (*((_BYTE *)v4 + 9400) & 2) == 0 )
        {
          v5 = 3221225508LL;
          goto LABEL_3;
        }
        result = XmlParserGenerator::EatUnknownNodes(v4, v39);
      }
      else
      {
        if ( DWORD1(v139) != 1 )
        {
          v5 = 3221225661LL;
          goto LABEL_3;
        }
        result = ActionListParser::ParseCustomInformation(
                   v4,
                   (struct XmlParserGenerator::ParserState *)(*(_QWORD *)a2 + 272LL),
                   a3);
      }
      if ( (int)result < 0 )
        return result;
LABEL_109:
      v36 = *((_DWORD *)v4 + 2282);
    }
    while ( v36 == 3 );
  }
  this = v4;
  if ( v36 == 4 )
  {
    result = XmlParserGenerator::MoveToNextSemanticNode(v4, v35, (bool)a3);
    if ( (int)result < 0 )
      return result;
    return 0;
  }
LABEL_2:
  v5 = 3221226538LL;
LABEL_3:
  result = XmlParserGenerator::ReportError(this, (const struct XmlParserGenerator::ParserState *)v5, (int)a3);
  if ( (int)result >= 0 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18005E10ALL);
  }
  return result;
}

```

## disassembly

```asm
0x18005d3b8  mov     [rsp-8+arg_10], rbx
0x18005d3bd  push    rbp
0x18005d3be  push    rsi
0x18005d3bf  push    rdi
0x18005d3c0  push    r12
0x18005d3c2  push    r13
0x18005d3c4  push    r14
0x18005d3c6  push    r15
0x18005d3c8  lea     rbp, [rsp-300h]
0x18005d3d0  sub     rsp, 400h
0x18005d3d7  mov     rax, cs:__security_cookie
0x18005d3de  xor     rax, rsp
0x18005d3e1  mov     [rbp+330h+var_38], rax
0x18005d3e8  cmp     dword ptr [rcx+23A8h], 3
0x18005d3ef  mov     r14, rdx
0x18005d3f2  mov     rdi, rcx
0x18005d3f5  jz      short loc_18005D434
0x18005d3f7  mov     edx, 0C000042Ah; struct XmlParserGenerator::ParserState *
0x18005d3fc  call    ?ReportError@XmlParserGenerator@@YAJPEBUParserState@1@J@Z; XmlParserGenerator::ReportError(XmlParserGenerator::ParserState const *,long)
0x18005d401  test    eax, eax
0x18005d403  jns     loc_18005E100
0x18005d409  mov     rcx, [rbp+330h+var_38]
0x18005d410  xor     rcx, rsp; StackCookie
0x18005d413  call    __security_check_cookie
0x18005d418  mov     rbx, [rsp+430h+arg_10]
0x18005d420  add     rsp, 400h
0x18005d427  pop     r15
0x18005d429  pop     r14
0x18005d42b  pop     r13
0x18005d42d  pop     r12
0x18005d42f  pop     rdi
0x18005d430  pop     rsi
0x18005d431  pop     rbp
0x18005d432  retn
0x18005d434  mov     rcx, [rcx+24A8h]
0x18005d43b  mov     r13d, 8
0x18005d441  mov     r8d, r13d
0x18005d444  mov     edx, 140h
0x18005d449  mov     rax, [rcx]
0x18005d44c  mov     rax, [rax+8]
0x18005d450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d455  xor     ebx, ebx
0x18005d457  lea     r15d, [r13-3]
0x18005d45b  lea     r12d, [r13-2]
0x18005d45f  lea     r11d, [r13-1]
0x18005d463  test    rax, rax
0x18005d466  jnz     short loc_18005D46F
0x18005d468  mov     eax, ebx
0x18005d46a  jmp     loc_18005D546
0x18005d46f  xorps   xmm0, xmm0
0x18005d472  xor     ecx, ecx
0x18005d474  movups  xmmword ptr [rax], xmm0
0x18005d477  mov     [rax+10h], rcx
0x18005d47b  mov     [rax+18h], rbx
0x18005d47f  mov     [rax+20h], rbx
0x18005d483  movups  xmmword ptr [rax+28h], xmm0
0x18005d487  mov     [rax+38h], rcx
0x18005d48b  movups  xmmword ptr [rax+40h], xmm0
0x18005d48f  mov     [rax+50h], rcx
0x18005d493  movups  xmmword ptr [rax+58h], xmm0
0x18005d497  mov     [rax+68h], rcx
0x18005d49b  movups  xmmword ptr [rax+70h], xmm0
0x18005d49f  mov     [rax+80h], rcx
0x18005d4a6  lea     rcx, aMainos_0; "MainOS"
0x18005d4ad  mov     [rax+0A8h], rcx
0x18005d4b4  xor     ecx, ecx
0x18005d4b6  mov     [rax+88h], ebx
0x18005d4bc  mov     [rax+8Ch], r15
0x18005d4c3  mov     [rax+98h], r12
0x18005d4ca  mov     [rax+0A0h], r11
0x18005d4d1  movups  xmmword ptr [rax+0B0h], xmm0
0x18005d4d8  mov     [rax+0C0h], rcx
0x18005d4df  movups  xmmword ptr [rax+0C8h], xmm0
0x18005d4e6  mov     [rax+0D8h], rcx
0x18005d4ed  mov     [rax+0E0h], r15
0x18005d4f4  movups  xmmword ptr [rax+0E8h], xmm0
0x18005d4fb  mov     [rax+0F8h], rcx
0x18005d502  mov     [rax+100h], rbx
0x18005d509  mov     [rax+108h], rbx
0x18005d510  mov     [rax+110h], rbx
0x18005d517  mov     [rax+118h], rbx
0x18005d51e  mov     [rax+120h], rbx
0x18005d525  mov     [rax+128h], rbx
0x18005d52c  mov     [rax+130h], rbx
0x18005d533  mov     [rax+138h], ebx
0x18005d539  mov     [rax+13Ch], bx
0x18005d540  mov     [rax+13Eh], bl
0x18005d546  mov     [r14], rax
0x18005d549  test    rax, rax
0x18005d54c  jnz     short loc_18005D597
0x18005d54e  lea     rax, aOnecoreBaseSer_2; "onecore\\base\\servicing\\actionlist\\l"...
0x18005d555  mov     [rbp+330h+var_390], 0C4Ch
0x18005d55d  mov     qword ptr [rbp+330h+var_3A0], rax
0x18005d561  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18005d568  lea     rax, aActionlistpars_26; "ActionListParser::ParseInstallPackage"
0x18005d56f  mov     r8d, 0C0000017h
0x18005d575  mov     qword ptr [rbp+330h+var_3A0+8], rax
0x18005d579  lea     rcx, [rbp+330h+var_3A0]
0x18005d57d  lea     rax, aPpobjectStateM_49; "*ppObject = State->m_pAllocator->Alloca"...
0x18005d584  mov     [rbp+330h+var_388], rax
0x18005d588  call    RtlReportErrorOrigination
0x18005d58d  mov     eax, 0C0000017h
0x18005d592  jmp     loc_18005D409
0x18005d597  cmp     dword ptr [rdi+23A8h], 3
0x18005d59e  jz      short loc_18005D5B2
0x18005d5a0  mov     ecx, 0C00000E5h; Status
0x18005d5a5  call    cs:__imp_RtlRaiseStatus
0x18005d5ac  nop     dword ptr [rax+rax+00h]
0x18005d5b1  int     3; Trap to Debugger
0x18005d5b2  movups  xmm1, xmmword ptr cs:off_1801C4200
0x18005d5b9  mov     sil, [rdi+2434h]
0x18005d5c0  xor     eax, eax
0x18005d5c2  mov     edx, [rdi+2430h]
0x18005d5c8  mov     r9d, 0Dh
0x18005d5ce  mov     [rbp+330h+var_40], al
0x18005d5d4  xorps   xmm0, xmm0
0x18005d5d7  lea     rax, aKeyform_0; "Keyform"
0x18005d5de  mov     [rbp+330h+var_2F0], r11
0x18005d5e2  mov     [rbp+330h+var_2E0], rax
0x18005d5e6  lea     rax, aInstalledsize; "InstalledSize"
0x18005d5ed  mov     [rbp+330h+var_2B8], rax
0x18005d5f1  lea     r8d, [r9-3]
0x18005d5f5  lea     r10d, [r9-2]
0x18005d5f9  mov     [rbp+330h+var_1D8], r12
0x18005d600  lea     rax, aStagedsize; "StagedSize"
0x18005d607  mov     [rbp+330h+var_1D0], r11
0x18005d60e  mov     [rbp+330h+var_290], rax
0x18005d615  lea     ecx, [r9-1]
0x18005d619  lea     rax, aFilepath; "FilePath"
0x18005d620  mov     [rbp+330h+var_1B0], r12
0x18005d627  mov     [rbp+330h+var_268], rax
0x18005d62e  lea     r12d, [r9+2]
0x18005d632  lea     rax, aSourcepath; "SourcePath"
0x18005d639  mov     [rbp+330h+var_1A8], r11
0x18005d640  mov     [rbp+330h+var_240], rax
0x18005d647  lea     r11d, [r9-4]
0x18005d64b  lea     rax, aExpresspackage_1; "ExpressPackagePath"
0x18005d652  mov     [rsp+430h+var_3FE], sil
0x18005d657  mov     [rbp+330h+var_218], rax
0x18005d65e  lea     rax, aExpressmetadat; "ExpressMetadataContainerPath"
0x18005d665  mov     [rbp+330h+var_1F0], rax
0x18005d66c  lea     rax, aAction_0; "Action"
0x18005d673  mov     [rbp+330h+var_1C8], rax
0x18005d67a  lea     rax, aReason_0; "Reason"
0x18005d681  mov     [rbp+330h+var_1A0], rax
0x18005d688  lea     rax, aPayloadtype; "PayloadType"
0x18005d68f  mov     [rbp+330h+var_178], rax
0x18005d696  lea     rax, aPartition; "Partition"
0x18005d69d  mov     [rbp+330h+var_150], rax
0x18005d6a4  lea     rax, aBinarypartitio; "BinaryPartition"
0x18005d6ab  mov     [rbp+330h+var_128], rax
0x18005d6b2  lea     rax, aFeatureid_0; "FeatureId"
0x18005d6b9  mov     [rbp+330h+var_100], rax
0x18005d6c0  mov     [rsp+430h+var_3D8], edx
0x18005d6c4  movups  [rbp+330h+var_50], xmm0
0x18005d6cb  mov     [rbp+330h+var_2E8], r13
0x18005d6cf  movdqu  xmmword ptr [rbp+330h+var_300], xmm1
0x18005d6d4  mov     [rbp+330h+var_2C8], r9
0x18005d6d8  movdqu  [rbp+330h+var_2D8], xmm1
0x18005d6dd  mov     [rbp+330h+var_2C0], 0Eh
0x18005d6e5  movdqu  [rbp+330h+var_2B0], xmm1
0x18005d6ed  mov     [rbp+330h+var_2A0], r8
0x18005d6f4  mov     [rbp+330h+var_298], r10
0x18005d6fb  movdqu  [rbp+330h+var_288], xmm1
0x18005d703  mov     [rbp+330h+var_278], r13
0x18005d70a  mov     [rbp+330h+var_270], 9
0x18005d715  movdqu  [rbp+330h+var_260], xmm1
0x18005d71d  mov     [rbp+330h+var_250], r8
0x18005d724  mov     [rbp+330h+var_248], r10
0x18005d72b  movdqu  [rbp+330h+var_238], xmm1
0x18005d733  mov     [rbp+330h+var_228], 12h
0x18005d73e  mov     [rbp+330h+var_220], 13h
0x18005d749  movdqu  [rbp+330h+var_210], xmm1
0x18005d751  mov     [rbp+330h+var_200], 1Ch
0x18005d75c  mov     [rbp+330h+var_1F8], 1Dh
0x18005d767  movdqu  [rbp+330h+var_1E8], xmm1
0x18005d76f  mov     [rbp+330h+var_188], r10
0x18005d776  movdqu  [rbp+330h+var_1C0], xmm1
0x18005d77e  mov     [rbp+330h+var_180], rcx
0x18005d785  movdqu  [rbp+330h+var_198], xmm1
0x18005d78d  mov     [rbp+330h+var_160], r11
0x18005d794  movdqu  [rbp+330h+var_170], xmm1
0x18005d79c  mov     [rbp+330h+var_158], r8
0x18005d7a3  movdqu  [rbp+330h+var_148], xmm1
0x18005d7ab  mov     [rbp+330h+var_138], r12
0x18005d7b2  mov     [rbp+330h+var_130], 10h
0x18005d7bd  movdqu  [rbp+330h+var_120], xmm1
0x18005d7c5  mov     [rbp+330h+var_110], r11
0x18005d7cc  mov     [rbp+330h+var_108], r8
0x18005d7d3  movdqu  [rbp+330h+var_F8], xmm1
0x18005d7db  lea     rax, aCapabilityid; "CapabilityId"
0x18005d7e2  mov     [rbp+330h+var_E8], rcx
0x18005d7e9  mov     [rbp+330h+var_D8], rax
0x18005d7f0  lea     rax, aType; "Type"
0x18005d7f7  mov     [rbp+330h+var_B0], rax
0x18005d7fe  lea     rax, aRebootrequired; "RebootRequired"
0x18005d805  mov     [rbp+330h+var_88], rax
0x18005d80c  lea     rax, aLicensepath; "LicensePath"
0x18005d813  mov     [rbp+330h+var_60], rax
0x18005d81a  mov     rax, [rdi+24C8h]
0x18005d821  mov     [rbp+330h+var_68], rcx
0x18005d828  mov     rcx, [rdi+24C0h]
0x18005d82f  mov     [rbp+330h+var_E0], r9
0x18005d836  mov     [rbp+330h+var_C0], 4
0x18005d841  mov     [rbp+330h+var_B8], r15
0x18005d848  mov     [rbp+330h+var_98], 0Eh
0x18005d853  mov     [rbp+330h+var_90], r12
0x18005d85a  mov     [rbp+330h+var_70], r10
0x18005d861  movdqu  [rbp+330h+var_D0], xmm1
0x18005d869  movdqu  [rbp+330h+var_A8], xmm1
0x18005d871  movdqu  [rbp+330h+var_80], xmm1
0x18005d879  cmp     rcx, rax
0x18005d87c  jz      short loc_18005D88E
0x18005d87e  add     rax, 0FFFFFFFFFFFFFFF8h
0x18005d882  cmp     rcx, rax
0x18005d885  jnz     short loc_18005D87E
0x18005d887  mov     [rdi+24C8h], rax
0x18005d88e  mov     r12d, ebx
0x18005d891  test    edx, edx
0x18005d893  jz      loc_18005DEB0
0x18005d899  mov     r9b, 1
0x18005d89c  mov     [rsp+430h+var_3F8], rbx
0x18005d8a1  lea     r8, [rsp+430h+var_3F8]
0x18005d8a6  mov     edx, r12d; unsigned int
0x18005d8a9  lea     rcx, [rdi+0D80h]; struct _RTL_GROWING_LIST *
0x18005d8b0  call    RtlIndexIntoGrowingList
0x18005d8b5  test    eax, eax
0x18005d8b7  js      loc_18005E044
0x18005d8bd  mov     r15, [rsp+430h+var_3F8]
0x18005d8c2  cmp     [r15+68h], bl
0x18005d8c6  jnz     loc_18005DE97
0x18005d8cc  cmp     [r15+69h], bl
0x18005d8d0  jnz     loc_18005DE97
0x18005d8d6  mov     rax, [r15+20h]
0x18005d8da  lea     r9, [rbp+330h+var_300]; unsigned __int64
0x18005d8de  mov     [rsp+430h+var_3B8], rax
0x18005d8e3  lea     rdx, [rsp+430h+var_3D0]; struct _LUTF8_STRING *
0x18005d8e8  mov     [rbp+330h+var_3B0], rax
0x18005d8ec  lea     rcx, [rsp+430h+var_3B8]; this
0x18005d8f1  mov     rax, [r15+18h]
0x18005d8f5  mov     r8d, 11h; struct _LUTF8_STRING *
0x18005d8fb  mov     [rbp+330h+var_3A8], rax
0x18005d8ff  mov     rax, [r15+8]
0x18005d903  mov     [rsp+430h+var_3D0], rax
0x18005d908  mov     [rsp+430h+var_3C8], rax
0x18005d90d  mov     rax, [r15]
0x18005d910  mov     [rsp+430h+var_3C0], rax
0x18005d915  lea     rax, [rsp+430h+var_3F8]
0x18005d91a  mov     [rsp+430h+var_410], rax; struct XmlParserGenerator::NamespaceNamePair *
0x18005d91f  mov     [rsp+430h+var_3F8], rbx
0x18005d924  call    ?MatchNamespaceAndNameAgainstList@XmlParserGenerator@@YAJAEBU_LUTF8_STRING@@0_KQEBUNamespaceNamePair@1@PEA_K@Z; XmlParserGenerator::MatchNamespaceAndNameAgainstList(_LUTF8_STRING const &,_LUTF8_STRING const &,unsigned __int64,XmlParserGenerator::NamespaceNamePair const * const,unsigned __int64 *)
0x18005d929  test    eax, eax
0x18005d92b  js      loc_18005D409
0x18005d931  mov     rsi, [rsp+430h+var_3F8]
0x18005d936  cmp     rsi, 11h
0x18005d93a  jnb     loc_18005DE70
0x18005d940  mov     rcx, rdi
0x18005d943  cmp     byte ptr [rbp+rsi+330h+var_50], bl
0x18005d94a  jnz     loc_18005E030
0x18005d950  movsd   xmm1, qword ptr [r15+40h]
0x18005d956  lea     r9, [rsp+430h+var_3FF]
0x18005d95b  xorps   xmm0, xmm0
0x18005d95e  mov     byte ptr [rbp+rsi+330h+var_50], 1
0x18005d966  movups  [rsp+430h+var_3F0], xmm0
0x18005d96b  xor     eax, eax
0x18005d96d  lea     r8, [rsp+430h+var_3F0]
0x18005d972  movups  xmm0, xmmword ptr [r15+30h]
0x18005d977  lea     rdx, [rbp+330h+var_3A0]
0x18005d97b  mov     [rsp+430h+var_3E0], rax
0x18005d980  mov     [rsp+430h+var_3FF], bl
0x18005d984  movaps  [rbp+330h+var_3A0], xmm0
0x18005d988  movsd   [rbp+330h+var_390], xmm1
0x18005d98d  call    ?Utf8ExtentToExpandedString@ParserState@XmlParserGenerator@@QEAAJU_XML_EXTENT@@PEAU_LUTF8_STRING@@PEA_N@Z; XmlParserGenerator::ParserState::Utf8ExtentToExpandedString(_XML_EXTENT,_LUTF8_STRING *,bool *)
0x18005d992  test    eax, eax
0x18005d994  js      loc_18005D409
0x18005d99a  mov     [rsp+430h+var_400], bl
0x18005d99e  mov     r15b, bl
0x18005d9a1  cmp     rsi, r13
0x18005d9a4  ja      loc_18005DC01
0x18005d9aa  jz      loc_18005DBCC
0x18005d9b0  test    rsi, rsi
0x18005d9b3  jz      loc_18005DB8A
0x18005d9b9  sub     rsi, 1
0x18005d9bd  jz      loc_18005DB81
0x18005d9c3  sub     rsi, 1
0x18005d9c7  jz      loc_18005DB64
0x18005d9cd  sub     rsi, 1
0x18005d9d1  jz      loc_18005DB17
0x18005d9d7  sub     rsi, 1
0x18005d9db  jz      loc_18005DACA
0x18005d9e1  sub     rsi, 1
0x18005d9e5  jz      loc_18005DA7D
0x18005d9eb  sub     rsi, 1
0x18005d9ef  jz      short loc_18005DA30
0x18005d9f1  cmp     rsi, 1
0x18005d9f5  jnz     loc_18005DE5D
0x18005d9fb  mov     r9, [r14]
0x18005d9fe  lea     rax, [rsp+430h+var_400]
0x18005da03  add     r9, 88h
0x18005da0a  mov     [rsp+430h+var_410], rax
  ... truncated ...
```

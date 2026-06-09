# LibRaw::GetNormalizedModel(void)

- ea: `0x180073a10`
- end: `0x180075790`
- name: `?GetNormalizedModel@LibRaw@@IEAAXXZ`
- size: `7552`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1800546b0`

## callees

- `0x180005d03`
- `0x180005d0f`
- `0x180005d4b`
- `0x180006150`
- `0x18002c2f0`
- `0x18005bc30`
- `0x180073750`
- `0x180073810`
- `0x180073a10`
- `0x180092f00`
- `0x180094f51`
- `0x180094fbd`
- `0x180094fc9`
- `0x180095071`
- `0x1800951c4`

## string_xrefs

- `0x180073ef2`: `GXR Mount A12`
- `0x180075672`: `LensID="`
- `0x1800756ce`: `LensID="(`

## pseudocode

```c
void __fastcall LibRaw::GetNormalizedModel(LibRaw *this)
{
  int v1; // r12d
  int v3; // r13d
  int v4; // eax
  unsigned int v5; // edx
  int v6; // eax
  char v7; // cl
  _QWORD *v8; // rbx
  _QWORD *v9; // rsi
  char v10; // al
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ecx
  char *v14; // rax
  __int64 v15; // rbx
  const char *v16; // rdx
  unsigned int v17; // ebx
  __int64 v18; // rsi
  __int64 v19; // rax
  char *v20; // rbp
  const char *v21; // rsi
  int i; // ebx
  const char *v23; // rcx
  __int64 v24; // rax
  int v25; // ebx
  const char *v26; // rsi
  __int64 v27; // rax
  int v28; // ebx
  const char *v29; // rsi
  __int64 v30; // rax
  char *v31; // r14
  const char *v32; // rsi
  int v33; // ebx
  const char *v34; // rcx
  __int64 v35; // rax
  char *v36; // rax
  const char *v37; // rsi
  int v38; // ebx
  const char *v39; // rcx
  __int64 v40; // rax
  char *v41; // rbp
  const char *v42; // rsi
  int v43; // ebx
  const char *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  char *v47; // rbp
  const char *v48; // rsi
  int v49; // ebx
  const char *v50; // rcx
  __int64 v51; // rax
  char *v52; // r14
  const char *v53; // rsi
  int v54; // ebx
  const char *v55; // rcx
  __int64 v56; // rax
  const char *v57; // rsi
  int v58; // ebx
  const char *v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rbx
  _QWORD *v63; // rax
  __int64 v64; // rbx
  char *v65; // rbp
  const char *v66; // rsi
  int v67; // ebx
  const char *v68; // rcx
  __int64 v69; // rax
  const char **v70; // rsi
  __int64 v71; // rbp
  size_t v72; // rax
  int v73; // ebx
  const char *v74; // rsi
  const char *v75; // rcx
  __int64 v76; // rax
  int v77; // ebx
  const char *v78; // rsi
  __int64 v79; // rcx
  unsigned int v80; // eax
  int v81; // ecx
  char *v82; // rbx
  int v84; // eax
  __int16 v85; // ax
  char v86; // al
  __int16 v87; // ax
  int v88; // ecx
  __int16 v89; // ax
  __int16 v90; // ax
  __int64 v91; // rax
  const char **v92; // rsi
  size_t v93; // rax
  int v94; // eax
  const char *v95; // rcx
  char v96; // al
  const char *v97; // rbx
  char *v98; // rax
  int v99; // eax
  char *v100; // rax
  __int16 v101; // ax
  __int16 v102; // ax

  v1 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 131) == 66 )
    LibRaw::setMakeFromIndex(this, 0x3Bu);
  v4 = *((_DWORD *)this + 131);
  if ( v4 == 59 )
  {
    if ( *((_WORD *)this + 677) == 33 )
    {
      v5 = 49;
LABEL_16:
      LibRaw::setMakeFromIndex(this, v5);
      goto LABEL_17;
    }
    goto LABEL_26;
  }
  if ( v4 )
  {
    if ( v4 == 24 )
    {
      if ( *((_DWORD *)this + 95919) )
      {
        v5 = 63;
        goto LABEL_16;
      }
      goto LABEL_26;
    }
    if ( v4 != 78 )
    {
      if ( v4 == 11 )
      {
        if ( *((_QWORD *)this + 47673) == 0x5330303539LL )
          goto LABEL_15;
      }
      else if ( v4 == 8
             && (!strncmp_0((const char *)this + 268, "EOS D2000", 9u)
              || !strncmp_0((const char *)this + 268, "EOS D6000", 9u)
              || !strncmp_0((const char *)this + 268, "EOSDCS", 6u)) )
      {
LABEL_28:
        v5 = 29;
        goto LABEL_16;
      }
LABEL_26:
      if ( *((_DWORD *)this + 131) != 51 || strnicmp_0((const char *)this + 268, "Camerz ZDS 14", 0xDu) )
      {
        strcpy_0((char *)this + 396, (const char *)this + 204);
        goto LABEL_17;
      }
      goto LABEL_28;
    }
LABEL_15:
    v5 = 45;
    goto LABEL_16;
  }
  if ( LibRaw::strcasestr((char *)this + 268, "Google") )
  {
    v5 = 22;
    goto LABEL_16;
  }
LABEL_17:
  v6 = *((_DWORD *)this + 131);
  if ( v6 == 3 )
  {
    if ( *((_BYTE *)this + 153376)
      && (!strncmp_0((const char *)this + 268, "iPad", 4u) || !strncmp_0((const char *)this + 268, "iPhone", 6u)) )
    {
      strcpy_0((char *)this + 268, (const char *)this + 153376);
    }
  }
  else if ( v6 == 29 )
  {
    if ( *((_BYTE *)this + 274) == 32
      && (!strncmp_0((const char *)this + 268, "DCS4", 4u) || !strncmp_0((const char *)this + 268, "NC2000", 6u)) )
    {
      *((_BYTE *)this + 274) = 0;
    }
    v7 = *((_BYTE *)this + 274);
    if ( (((v7 - 65) & 0xF3) != 0 || v7 == 69) && !strncmp_0((const char *)this + 268, "NC2000", 6u) )
      *((_BYTE *)this + 274) = 0;
  }
  else if ( v6 == 56 && !strncmp_0((const char *)this + 268, "GXR", 3u) )
  {
    strcpy((char *)this + 1356, "Ricoh GXR");
    if ( !*((_BYTE *)this + 788) && *((_BYTE *)this + 153376) )
    {
      strcpy_0((char *)this + 788, (const char *)this + 153376);
      LibRaw::remove_caseSubstr((char *)this + 788, "Ricoh");
      LibRaw::remove_caseSubstr((char *)this + 788, "Lens");
      LibRaw::removeExcessiveSpaces((char *)this + 788);
    }
    v8 = (_QWORD *)((char *)this + 1200);
    v9 = (_QWORD *)((char *)this + 1200);
    if ( *((_QWORD *)this + 150) == -1 )
    {
      if ( strstr((const char *)this + 788, "50mm") )
      {
        *v8 = 1;
      }
      else if ( strstr((const char *)this + 788, "S10") )
      {
        *v8 = 2;
      }
      else if ( strstr((const char *)this + 788, "P10") )
      {
        *v8 = 3;
      }
      else if ( strstr((const char *)this + 788, "28mm") )
      {
        *v8 = 5;
      }
      else if ( strstr((const char *)this + 788, "A16") )
      {
        v9 = (_QWORD *)((char *)this + 1200);
        *v8 = 6;
      }
    }
    switch ( *v9 )
    {
      case 1LL:
        qmemcpy((char *)this + 268, "GXR A12 50mm", 12);
        v10 = aGxrA1250mm[12];
        goto LABEL_57;
      case 2LL:
        *((_DWORD *)this + 334) = 2818055;
        *(_QWORD *)((char *)this + 268) = 0x30315320525847LL;
        *((_DWORD *)this + 338) = 2293767;
        *((_WORD *)this + 710) = 2;
        break;
      case 3LL:
        *((_DWORD *)this + 334) = 2818054;
        *(_QWORD *)((char *)this + 268) = 0x30315020525847LL;
        *((_DWORD *)this + 338) = 2293766;
        *((_WORD *)this + 710) = 2;
        break;
      case 5LL:
        qmemcpy((char *)this + 268, "GXR A12 28mm", 12);
        v10 = aGxrA1228mm[12];
LABEL_57:
        *((_BYTE *)this + 280) = v10;
        *((_DWORD *)this + 334) = 2818049;
        *((_DWORD *)this + 338) = 2293761;
        *((_WORD *)this + 710) = 1;
        break;
      case 6LL:
        *((_DWORD *)this + 334) = 2818049;
        *(_QWORD *)((char *)this + 268) = 0x36314120525847LL;
        *((_DWORD *)this + 338) = 2293761;
        *((_WORD *)this + 710) = 2;
        break;
      case 8LL:
        strcpy((char *)this + 268, "GXR Mount A12");
        *((_DWORD *)this + 338) = 1114113;
        *v9 = -1;
        break;
      default:
        break;
    }
  }
  strcpy_0((char *)this + 460, (const char *)this + 268);
  v11 = *((_DWORD *)this + 131);
  switch ( v11 )
  {
    case 8:
      v12 = *((_QWORD *)this + 47672);
      if ( !v12 )
      {
        if ( *((_DWORD *)this + 133)
          && strlen_0((const char *)this + 153376) > 6
          && strncmp_0((const char *)this + 153382, "PowerShot", 9u) )
        {
          v17 = 0;
          while ( 1 )
          {
            v18 = 32LL * v17;
            if ( !strcmp_0(&byte_1800CE0D0[v18 + 8], (const char *)this + 153382) )
              break;
            if ( (int)++v17 >= 74 )
              goto LABEL_248;
          }
          v19 = *(_QWORD *)&byte_1800CE0D0[v18];
          *((_QWORD *)this + 47672) = v19;
          *((_QWORD *)this + 168) = v19;
          strcpy_0((char *)this + 460, &byte_1800CE0D0[v18 + 8]);
          v3 = 1;
        }
        goto LABEL_248;
      }
      if ( ((v12 - 2147484960LL) & 0xFFFFFFFFFFFFFFBFuLL) == 0 )
        goto LABEL_248;
      v13 = 0;
      v14 = byte_1800CE0D0;
      while ( v12 != *(_QWORD *)v14 )
      {
        ++v13;
        v14 += 32;
        if ( (__int64)v14 >= (__int64)qword_1800CEA10 )
          goto LABEL_248;
      }
      v15 = 32LL * v13;
      strcpy_0((char *)this + 268, &byte_1800CE0D0[v15 + 8]);
      v16 = &byte_1800CE0D0[v15 + 8];
      goto LABEL_247;
    case 18:
      v20 = qword_180126A98;
      v21 = "@DBP for GX680";
      for ( i = 0; i < 33; ++i )
      {
        v23 = (char *)this + 268;
        v24 = 16LL * i;
        if ( *v21 == 64 )
        {
          v20 = &aDbpForGx680_0[v24 + 1];
          qword_180126A98 = v20;
          if ( !strcmp_0(v23, v20) )
            goto LABEL_248;
        }
        else if ( !strcmp_0(v23, &aDbpForGx680_0[v24]) )
        {
          goto LABEL_87;
        }
        v21 += 16;
      }
      goto LABEL_248;
    case 24:
      LibRaw::parseHassyModel(this);
      goto LABEL_248;
    case 36:
      v25 = 0;
      v26 = "@H20";
      while ( 1 )
      {
        v27 = 16LL * (unsigned int)v25;
        if ( *v26 == 64 )
        {
          qword_180126A98 = &aH20_1[v27 + 1];
        }
        else if ( !strcmp_0((const char *)this + 268, &aH20_1[v27]) )
        {
          LibRaw::setMakeFromIndex(this, 0x32u);
          strcpy_0((char *)this + 460, qword_180126A98);
LABEL_98:
          v28 = 0;
          v29 = "@Aptus-II 5";
          while ( 1 )
          {
            v30 = 16LL * (unsigned int)v28;
            if ( *v29 == 64 )
            {
              qword_180126A98 = &aAptusIi5_0[v30 + 1];
            }
            else if ( !strcmp_0((const char *)this + 268, &aAptusIi5_0[v30]) )
            {
              LibRaw::setMakeFromIndex(this, 0x1Fu);
              goto LABEL_246;
            }
            ++v28;
            v29 += 16;
            if ( v28 >= 10 )
              goto LABEL_248;
          }
        }
        ++v25;
        v26 += 16;
        if ( v25 >= 35 )
          goto LABEL_98;
      }
  }
  if ( v11 != 31 )
  {
    if ( v11 != 40 )
    {
      if ( v11 != 30 )
      {
        if ( v11 == 43 )
        {
          v20 = qword_180126A98;
          v37 = "@COOLPIX 2100";
          v38 = 0;
          while ( 1 )
          {
            v39 = (char *)this + 268;
            v40 = 16LL * v38;
            if ( *v37 == 64 )
            {
              v20 = &aCoolpix2100_0[v40 + 1];
              qword_180126A98 = v20;
              if ( !strcmp_0(v39, v20) )
                goto LABEL_248;
            }
            else if ( !strcmp_0(v39, &aCoolpix2100_0[v40]) )
            {
              goto LABEL_87;
            }
            ++v38;
            v37 += 16;
            if ( v38 >= 42 )
              goto LABEL_248;
          }
        }
        if ( v11 == 45 )
        {
          v41 = qword_180126A98;
          v42 = "@AIR A01";
          v43 = 0;
          while ( 1 )
          {
            v44 = (char *)this + 268;
            v45 = 32LL * v43;
            if ( *v42 == 64 )
            {
              v41 = &aAirA01_0[v45 + 1];
              qword_180126A98 = v41;
              if ( !strcmp_0(v44, v41) )
                goto LABEL_135;
            }
            else if ( !strcmp_0(v44, &aAirA01_0[v45]) )
            {
              strcpy_0((char *)this + 460, v41);
LABEL_135:
              if ( !*((_QWORD *)this + 47673) )
              {
                if ( !strcmp_0((const char *)this + 460, "C-740UZ") )
                {
                  *((_QWORD *)this + 47672) = 0x5358373534LL;
                  *((_QWORD *)this + 47673) = 0x5358373534LL;
                  *((_QWORD *)this + 168) = 0x5358373534LL;
                }
                else if ( !strcmp_0((const char *)this + 460, "C-770UZ") )
                {
                  *((_QWORD *)this + 47672) = 0x5358373732LL;
                  *((_QWORD *)this + 47673) = 0x5358373732LL;
                  *((_QWORD *)this + 168) = 0x5358373732LL;
                }
              }
              goto LABEL_248;
            }
            ++v43;
            v42 += 32;
            if ( v43 >= 75 )
              goto LABEL_135;
          }
        }
        if ( v11 == 47 || v11 == 32 || (v46 = *((_DWORD *)this + 131), v46 == 70) )
        {
          v73 = 0;
          v74 = "@DMC-FX150";
          while ( 1 )
          {
            v75 = (char *)this + 268;
            v76 = 16LL * v73;
            if ( *v74 == 64 )
            {
              qword_180126A98 = &aDmcFx150_0[v76 + 1];
              if ( !strcmp_0(v75, &aDmcFx150_0[v76 + 1]) )
                goto LABEL_248;
            }
            else if ( !strcmp_0(v75, &aDmcFx150_0[v76]) )
            {
              LibRaw::setMakeFromIndex(this, 0x2Fu);
LABEL_246:
              v16 = qword_180126A98;
              goto LABEL_247;
            }
            ++v73;
            v74 += 16;
            if ( v73 >= 128 )
              goto LABEL_248;
          }
        }
        switch ( v46 )
        {
          case '1':
            if ( !*((_QWORD *)this + 47672) )
            {
              if ( !strcmp_0((const char *)this + 268, "Optio S") )
              {
                *((_QWORD *)this + 47672) = 76140;
                *((_QWORD *)this + 168) = 76140;
              }
              else if ( !strcmp_0((const char *)this + 268, "Optio S V1.01") )
              {
                *((_QWORD *)this + 47672) = 76145;
                *((_QWORD *)this + 168) = 76145;
              }
              else if ( !strcmp_0((const char *)this + 268, "Optio S4") )
              {
                *((_QWORD *)this + 47672) = 76245;
                *((_QWORD *)this + 168) = 76245;
              }
              else if ( !strcmp_0((const char *)this + 268, "Optio 750Z") )
              {
                *((_QWORD *)this + 47672) = 76390;
                *((_QWORD *)this + 168) = 76390;
              }
              else if ( !strcmp_0((const char *)this + 268, "Optio 33WR") )
              {
                *((_QWORD *)this + 47672) = 76230;
                *((_QWORD *)this + 168) = 76230;
              }
            }
            v47 = qword_180126A98;
            v48 = "@*istDL2";
            v49 = 0;
            while ( 1 )
            {
              v50 = (char *)this + 268;
              v51 = 16LL * v49;
              if ( *v48 == 64 )
              {
                v47 = &aIstdl2_0[v51 + 1];
                qword_180126A98 = v47;
                if ( !strcmp_0(v50, v47) )
                  goto LABEL_163;
              }
              else if ( !strcmp_0(v50, &aIstdl2_0[v51]) )
              {
                strcpy_0((char *)this + 460, v47);
LABEL_163:
                if ( !strncmp_0((const char *)this + 268, "GR", 2u) )
                {
                  LibRaw::setMakeFromIndex(this, 0x38u);
                  strcpy((char *)this + 204, "Ricoh");
                }
                goto LABEL_248;
              }
              ++v49;
              v48 += 16;
              if ( v49 >= 20 )
                goto LABEL_163;
            }
          case '2':
            v52 = qword_180126A98;
            v53 = "@H20";
            v54 = 0;
            while ( 1 )
            {
              v55 = (char *)this + 268;
              v56 = 16LL * v54;
              if ( *v53 == 64 )
              {
                v52 = &aH20_1[v56 + 1];
                qword_180126A98 = v52;
                if ( !strcmp_0(v55, v52) )
                  goto LABEL_174;
              }
              else if ( !strcmp_0(v55, &aH20_1[v56]) )
              {
                strcpy_0((char *)this + 460, v52);
LABEL_174:
                if ( strstr((const char *)this + 4052, "Achromatic") )
                  *(_QWORD *)((char *)this + 540) = 1;
                goto LABEL_248;
              }
              ++v54;
              v53 += 16;
              if ( v54 >= 35 )
                goto LABEL_174;
            }
          case ';':
            if ( strstr((const char *)this + 268, "WB5500") || strstr((const char *)this + 268, "HZ50W") )
            {
              v16 = (char *)this + 268;
              strcpy((char *)this + 268, "WB5500");
              goto LABEL_247;
            }
            if ( strstr((const char *)this + 268, "WB5000") || strstr((const char *)this + 268, "HZ25W") )
            {
              v16 = (char *)this + 268;
              strcpy((char *)this + 268, "WB5000");
              goto LABEL_247;
            }
            if ( strstr((const char *)this + 268, "WB550") || strstr((const char *)this + 268, "HZ15W") )
            {
              v16 = (char *)this + 268;
              strcpy((char *)this + 268, "WB550");
              goto LABEL_247;
            }
            if ( strstr((const char *)this + 268, "WB500") || strstr((const char *)this + 268, "HZ10W") )
            {
              v16 = (char *)this + 268;
              strcpy((char *)this + 268, "WB500");
              goto LABEL_247;
            }
            v20 = qword_180126A98;
            v57 = "@EX1";
            v58 = 0;
            while ( 1 )
            {
              v59 = (char *)this + 268;
              v60 = (__int64)v58 << 6;
              if ( *v57 == 64 )
              {
                v20 = &aEx1_0[v60 + 1];
                qword_180126A98 = v20;
                if ( !strcmp_0(v59, v20) )
                  goto LABEL_248;
              }
              else if ( !strcmp_0(v59, &aEx1_0[v60]) )
              {
LABEL_87:
                v16 = v20;
                goto LABEL_247;
              }
              ++v58;
              v57 += 64;
              if ( v58 >= 12 )
                goto LABEL_248;
            }
        }
        if ( v46 != 63 )
        {
          if ( v46 != 29 )
            goto LABEL_248;
          LibRaw::remove_caseSubstr((char *)this + 460, "EasyShare");
          LibRaw::remove_caseSubstr((char *)this + 460, "ZOOM");
          LibRaw::removeExcessiveSpaces((char *)this + 460);
          v65 = qword_180126A98;
          v66 = "@DCS Pro 14N";
          v67 = 0;
          while ( 1 )
          {
            v68 = (char *)this + 268;
            v69 = 16LL * v67;
            if ( *v66 == 64 )
            {
              v65 = &aDcsPro14n[v69 + 1];
              qword_180126A98 = v65;
              if ( !strcmp_0(v68, v65) )
                goto LABEL_214;
            }
            else if ( !strcmp_0(v68, &aDcsPro14n[v69]) )
            {
              strcpy_0((char *)this + 460, v65);
LABEL_214:
              if ( strstr((const char *)this + 268, "DC25") )
              {
                strcpy((char *)this + 268, "DC25");
                goto LABEL_222;
              }
              if ( !strcmp_0((const char *)this + 268, "40") )
              {
                strcpy((char *)this + 268, "DC40");
                goto LABEL_222;
              }
              if ( strstr((const char *)this + 268, "DC50") )
              {
                strcpy((char *)this + 268, "DC50");
                goto LABEL_222;
              }
              if ( strstr((const char *)this + 268, "DC120") )
              {
                strcpy((char *)this + 268, "DC120");
LABEL_222:
                strcpy_0((char *)this + 460, (const char *)this + 268);
              }
              v70 = (const char **)off_1800E4DF0;
              v71 = 23;
              do
              {
                v72 = strlen_0(*v70);
                if ( !strncmp_0((const char *)this + 268, *v70, v72) )
                  *(_QWORD *)((char *)this + 540) = 1;
                ++v70;
                --v71;
              }
              while ( v71 );
              goto LABEL_248;
            }
            ++v67;
            v66 += 16;
            if ( v67 >= 24 )
              goto LABEL_214;
          }
        }
        v61 = *((_QWORD *)this + 47672);
        if ( !v61 )
          goto LABEL_248;
        v62 = 0;
        v63 = qword_1800CEA10;
        while ( v61 != *v63 )
        {
          v62 = (unsigned int)(v62 + 1);
          v63 += 4;
          if ( (int)v62 >= 92 )
            goto LABEL_248;
        }
        v64 = 4 * v62;
        if ( !strcmp_0((const char *)this + 204, "Sony") )
          strcpy_0((char *)this + 268, (const char *)&qword_1800CEA10[v64 + 1]);
        v16 = (const char *)&qword_1800CEA10[v64 + 1];
LABEL_247:
        strcpy_0((char *)this + 460, v16);
        goto LABEL_248;
      }
      if ( !strnicmp_0((const char *)this + 268, "DiMAGE", 6u) )
      {
LABEL_237:
        LibRaw::setMakeFromIndex(this, 0x28u);
        *(_QWORD *)((char *)this + 204) = 0x61746C6F6E694DLL;
        goto LABEL_248;
      }
    }
    v77 = 0;
    v78 = "@DG-5D";
    while ( 1 )
    {
      v79 = 24LL * v77;
      if ( *v78 == 64 )
      {
        qword_180126A98 = &aDg5d_0[v79 + 1];
        if ( !strcmp_0((const char *)this + 268, qword_180126A98) )
          goto LABEL_237;
      }
      else if ( !stricmp_0((const char *)this + 268, &aDg5d_0[v79]) )
      {
        LibRaw::setMakeFromIndex(this, 0x28u);
        *(_QWORD *)((char *)this + 204) = 0x61746C6F6E694DLL;
        goto LABEL_246;
      }
      ++v77;
      v78 += 24;
      if ( v77 >= 9 )
        goto LABEL_248;
    }
  }
  v31 = qword_180126A98;
  v32 = "@Aptus-II 5";
  v33 = 0;
  while ( 1 )
  {
    v34 = (char *)this + 268;
    v35 = 16LL * v33;
    if ( *v32 == 64 )
    {
      v31 = &aAptusIi5_0[v35 + 1];
      qword_180126A98 = v31;
      if ( !strcmp_0(v34, v31) )
        goto LABEL_114;
      goto LABEL_111;
    }
    if ( !strcmp_0(v34, &aAptusIi5_0[v35]) )
      break;
LABEL_111:
    ++v33;
    v32 += 16;
    if ( v33 >= 10 )
      goto LABEL_114;
  }
  strcpy_0((char *)this + 460, v31);
LABEL_114:
  v36 = strchr((const char *)this + 460, 40);
  if ( v36 )
    *v36 = 0;
LABEL_248:
  if ( *((_BYTE *)this + 1356) )
  {
    if ( *((_WORD *)this + 677) != 15
      && !strncmp_0((const char *)this + 1356, "Hasselblad ", 0xBu)
      && (v80 = *((unsigned __int8 *)this + 1367), LOBYTE(v80) = v80 - 50, (unsigned __int8)v80 <= 0x11u)
      && (v81 = 131209, _bittest(&v81, v80)) )
    {
      *((_DWORD *)this + 338) = 983052;
    }
    else if ( !strncmp_0((const char *)this + 1356, "XF", 2u) || !strncmp_0((const char *)this + 1356, "645DF", 5u) )
    {
      *((_DWORD *)this + 338) = 1572875;
    }
    else if ( !strncmp_0((const char *)this + 1356, "Sinarcam", 2u) )
    {
      *((_DWORD *)this + 338) = 2686990;
      v82 = (char *)this + 1355;
      while ( *++v82 != 0 )
        ;
      strcpy(v82, " shutter system");
    }
  }
  v84 = *((_DWORD *)this + 131);
  if ( v84 == 29 )
  {
    v85 = *((_WORD *)this + 677);
    if ( (v85 == 42 || !v85) && !strncmp_0((const char *)this + 153312, "PB645", 5u) )
    {
      *((_WORD *)this + 676) = 11;
      v86 = *((_BYTE *)this + 153317);
      switch ( v86 )
      {
        case 'C':
          *((_WORD *)this + 677) = 8;
          strcpy((char *)this + 1356, "Contax 645");
          break;
        case 'H':
          *((_WORD *)this + 677) = 14;
          strcpy((char *)this + 1356, "Hasselblad H1/H2");
          break;
        case 'M':
          *((_WORD *)this + 677) = 24;
          strcpy((char *)this + 1356, "Mamiya 645");
          break;
      }
    }
    else if ( !strnicmp_0((const char *)this + 268, "PIXPRO S-1", 0xAu) )
    {
      *((_WORD *)this + 676) = 8;
    }
    else if ( !strnicmp_0((const char *)this + 268, "PIXPRO ", 7u) )
    {
      *((_WORD *)this + 676) = 6;
    }
  }
  else if ( v84 == 18 && !strncmp_0((const char *)this + 460, "DBP", 3u) )
  {
    strcpy((char *)this + 1356, "Fujifilm GX680");
  }
  if ( !*((_WORD *)this + 676) || (v87 = *((_WORD *)this + 677)) == 0 || v87 == 44 )
  {
    v88 = *((_DWORD *)this + 131);
    switch ( v88 )
    {
      case 8:
        if ( !strncmp_0((const char *)this + 460, "EOS", 3u) )
          break;
LABEL_375:
        *((_WORD *)this + 677) = 43;
        break;
      case 43:
        v89 = 27;
        if ( *((_BYTE *)this + 460) != 68 )
          v89 = 43;
        *((_WORD *)this + 677) = v89;
        break;
      case 47:
        if ( strncmp_0((const char *)this + 460, "DC-S", 4u) )
        {
          if ( !strncmp_0((const char *)this + 460, "DMC-L1", 6u) || !strncmp_0((const char *)this + 460, "DMC-L10", 7u) )
          {
            *((_DWORD *)this + 338) = 524296;
          }
          else if ( !strncmp_0((const char *)this + 462, "-G", 2u) || !strncmp_0((const char *)this + 463, "-G", 2u) )
          {
            *((_DWORD *)this + 338) = 655368;
          }
          else
          {
            *((_WORD *)this + 677) = 43;
            *((_WORD *)this + 710) = 2;
            if ( !strncmp_0((const char *)this + 462, "-LX100", 6u)
              || !strncmp_0((const char *)this + 463, "-LX100", 6u) )
            {
              *((_WORD *)this + 668) = 8;
              *((_WORD *)this + 676) = 8;
            }
            else if ( !strncmp_0((const char *)this + 460, "DMC-CM1", 7u) )
            {
              *((_WORD *)this + 710) = 1;
            }
          }
          break;
        }
LABEL_341:
        *((_DWORD *)this + 338) = 1441794;
        break;
      case 18:
        if ( !strncmp_0((const char *)this + 460, "GFX ", 4u) )
        {
          *((_DWORD *)this + 338) = 720905;
          break;
        }
        if ( !strncmp_0((const char *)this + 460, "X-", 2u)
          && (strncmp_0((const char *)this + 460, "X-S1", 4u) || !strncmp_0((const char *)this + 460, "X-S10", 5u)) )
        {
          *((_DWORD *)this + 338) = 851969;
          break;
        }
        if ( *((_BYTE *)this + 460) == 83 && *((_BYTE *)this + 462) == 80
          || !strnicmp_0((const char *)this + 460, "IS Pro", 6u) )
        {
          *((_DWORD *)this + 338) = 1769473;
          break;
        }
        if ( !strncmp_0((const char *)this + 460, "DBP", 3u) )
        {
          *((_DWORD *)this + 338) = 786453;
          break;
        }
        goto LABEL_375;
      case 59:
        if ( *((_BYTE *)this + 460) != 78 || *((_BYTE *)this + 461) != 88 )
          goto LABEL_375;
        if ( *((_BYTE *)this + 462) == 70 && *((_BYTE *)this + 463) == 49 )
        {
          *((_WORD *)this + 677) = 37;
          *((_WORD *)this + 676) = 5;
        }
        else
        {
          *((_WORD *)this + 677) = 38;
          *((_WORD *)this + 676) = 1;
        }
        break;
      case 29:
        *((_WORD *)this + 677) = 43;
        v92 = (const char **)&off_1800C3020;
        while ( 1 )
        {
          v93 = strlen_0(*v92);
          if ( !strncmp_0((const char *)this + 460, *v92, v93) )
            break;
          ++v1;
          v92 += 2;
          if ( v1 >= 9 )
            goto LABEL_305;
        }
        *((_WORD *)this + 677) = (&off_1800C3020)[2 * (unsigned int)v1 + 1];
        break;
      case 40:
        if ( !strcmp_0((const char *)this + 460, "DG-5D") || !strcmp_0((const char *)this + 460, "DG-7D") )
        {
          *((_DWORD *)this + 338) = 1638401;
          break;
        }
        if ( !strnicmp_0((const char *)this + 460, "DiMAGE", 6u) )
          goto LABEL_375;
        break;
      default:
        if ( ((v88 - 9) & 0xFFFFFFFB) == 0 )
          goto LABEL_375;
        switch ( v88 )
        {
          case 60:
            if ( !strncmp_0((const char *)this + 460, "fp", 2u) )
              goto LABEL_341;
            v94 = strnicmp_0((const char *)this + 460, "SD", 2u);
            v95 = (char *)this + 460;
            if ( v94 )
            {
              if ( strnicmp_0(v95, "DP", 2u) )
                goto LABEL_305;
              *((_WORD *)this + 677) = 43;
              v96 = *((_BYTE *)this + 464);
              if ( v96 == 77 )
              {
                *((_WORD *)this + 676) = 18;
                goto LABEL_305;
              }
            }
            else
            {
              *((_WORD *)this + 677) = 39;
              if ( !strcmp_0(v95, "SD1") || (v96 = *((_BYTE *)this + 464), v96 == 77) )
              {
                *((_WORD *)this + 676) = 18;
                goto LABEL_305;
              }
              if ( *((_BYTE *)this + 471) == 72 )
              {
                *((_WORD *)this + 676) = 19;
                goto LABEL_305;
              }
            }
            if ( v96 == 81 )
              *((_WORD *)this + 676) = 1;
            else
              *((_WORD *)this + 676) = 17;
            break;
          case 30:
            if ( !strncmp_0((const char *)this + 268, "KD-", 3u) )
              goto LABEL_375;
            break;
          case 36:
            if ( !strncmp_0((const char *)this + 460, "ZD", 2u) )
              *((_DWORD *)this + 338) = 1572884;
            break;
          case 63:
            if ( !strncmp_0((const char *)this + 460, "XCD-", 4u) )
            {
              *((_WORD *)this + 677) = 2;
            }
            else if ( !strncmp_0((const char *)this + 460, "DSC-V3", 6u)
                   || !strncmp_0((const char *)this + 460, "DSC-F828", 8u) )
            {
              *((_WORD *)this + 677) = 43;
              *((_WORD *)this + 1700) = 1;
            }
            break;
          default:
            if ( v88 == 54 && !strncmp_0((const char *)this + 460, "x530", 4u)
              || *((_DWORD *)this + 131) == 57 && !strncmp_0((const char *)this + 460, "d530flex", 8u)
              || *((_DWORD *)this + 131) == 49 && !strncmp_0((const char *)this + 460, "Optio", 5u) )
            {
              goto LABEL_375;
            }
            if ( *((_DWORD *)this + 131) == 16 && !strncmp_0((const char *)this + 460, "R-D1", 4u) )
              *((_DWORD *)this + 338) = 1114113;
            break;
        }
        break;
    }
  }
LABEL_305:
  v90 = *((_WORD *)this + 669);
  if ( v90 == 6 )
  {
    if ( *((_QWORD *)this + 150) == 61182 )
    {
      v91 = *((__int16 *)this + 1020);
      if ( (_WORD)v91 )
        *((_QWORD *)this + 150) = v91;
    }
  }
  else if ( !v90 && *((_DWORD *)this + 131) == 59 && *((_BYTE *)this + 788) == 78 && *((_BYTE *)this + 789) == 88 )
  {
    if ( *((_BYTE *)this + 790) == 45 )
      *((_DWORD *)this + 334) = 2424837;
    else
      *((_DWORD *)this + 334) = 2490369;
  }
  if ( *((_QWORD *)this + 150) == -1 )
  {
    v97 = (const char *)*((_QWORD *)this + 79);
    if ( v97 )
    {
      if ( strlen_0(*((const char **)this + 79)) > 9 )
      {
        if ( *((_DWORD *)this + 131) == 8 && v3 && (v98 = strstr(v97, "LensID=\"")) != 0 )
        {
          v99 = atoi_0(v98 + 8);
          *((_QWORD *)this + 150) = v99;
          if ( v99 == 61182 )
          {
            *((_WORD *)this + 677) = 6;
            *((_WORD *)this + 669) = 6;
          }
        }
        else if ( *((_DWORD *)this + 131) == 59 && *((_WORD *)this + 669) == 38 )
        {
          v100 = strstr(*((const char **)this + 79), "LensID=\"(");
          if ( v100 )
            *((_QWORD *)this + 150) = atoi_0(v100 + 9);
        }
      }
    }
  }
  v101 = *((_WORD *)this + 677);
  if ( v101 == 43 )
  {
    v102 = *((_WORD *)this + 676);
    if ( v102 )
      *((_WORD *)this + 668) = v102;
    if ( !*((_WORD *)this + 669) )
      *((_WORD *)this + 669) = 43;
  }
  else if ( v101 && !*((_WORD *)this + 669) )
  {
    if ( *((_QWORD *)this + 150) == -1 )
      *((_WORD *)this + 669) = 44;
    else
      *((_WORD *)this + 669) = v101;
  }
}

```

## disassembly

```asm
0x180073a10  mov     [rsp+arg_0], rbx
0x180073a15  mov     [rsp+arg_8], rbp
0x180073a1a  mov     [rsp+arg_10], rsi
0x180073a1f  push    rdi
0x180073a20  push    r12
0x180073a22  push    r13
0x180073a24  push    r14
0x180073a26  push    r15
0x180073a28  sub     rsp, 20h
0x180073a2c  xor     r12d, r12d
0x180073a2f  mov     rdi, rcx
0x180073a32  cmp     dword ptr [rcx+20Ch], 42h ; 'B'
0x180073a39  mov     r13d, r12d
0x180073a3c  jnz     short loc_180073A48
0x180073a3e  mov     edx, 3Bh ; ';'; unsigned int
0x180073a43  call    ?setMakeFromIndex@LibRaw@@QEAAHI@Z; LibRaw::setMakeFromIndex(uint)
0x180073a48  mov     eax, [rdi+20Ch]
0x180073a4e  mov     ebx, 16h
0x180073a53  mov     esi, 9
0x180073a58  mov     ebp, 6
0x180073a5d  mov     edx, 0Dh
0x180073a62  cmp     eax, 3Bh ; ';'
0x180073a65  jnz     short loc_180073A7C
0x180073a67  cmp     word ptr [rdi+54Ah], 21h ; '!'
0x180073a6f  jnz     loc_180073BBA
0x180073a75  mov     edx, 31h ; '1'
0x180073a7a  jmp     short loc_180073ADF
0x180073a7c  test    eax, eax
0x180073a7e  jnz     short loc_180073A9C
0x180073a80  lea     rcx, [rdi+10Ch]; String1
0x180073a87  lea     rdx, aGoogle; "Google"
0x180073a8e  call    ?strcasestr@LibRaw@@KAPEADPEADPEBD@Z; LibRaw::strcasestr(char *,char const *)
0x180073a93  test    rax, rax
0x180073a96  jz      short loc_180073AE7
0x180073a98  mov     edx, ebx
0x180073a9a  jmp     short loc_180073ADF
0x180073a9c  cmp     eax, 18h
0x180073a9f  jnz     short loc_180073AB5
0x180073aa1  cmp     [rdi+5DABCh], r12d
0x180073aa8  jz      loc_180073BBA
0x180073aae  mov     edx, 3Fh ; '?'
0x180073ab3  jmp     short loc_180073ADF
0x180073ab5  cmp     eax, 4Eh ; 'N'
0x180073ab8  jz      short loc_180073ADA
0x180073aba  cmp     eax, 0Bh
0x180073abd  jnz     loc_180073B62
0x180073ac3  mov     rax, 5330303539h
0x180073acd  cmp     [rdi+5D1C8h], rax
0x180073ad4  jnz     loc_180073BBA
0x180073ada  mov     edx, 2Dh ; '-'; unsigned int
0x180073adf  mov     rcx, rdi; this
0x180073ae2  call    ?setMakeFromIndex@LibRaw@@QEAAHI@Z; LibRaw::setMakeFromIndex(uint)
0x180073ae7  mov     eax, [rdi+20Ch]
0x180073aed  mov     r14d, 1
0x180073af3  mov     r15d, 2
0x180073af9  cmp     eax, 3
0x180073afc  jnz     loc_180073BFF
0x180073b02  cmp     [rdi+25720h], r12b
0x180073b09  jz      loc_180073F32
0x180073b0f  mov     r8d, 4; MaxCount
0x180073b15  lea     rdx, aIpad; "iPad"
0x180073b1c  lea     rcx, [rdi+10Ch]; Str1
0x180073b23  call    strncmp_0
0x180073b28  test    eax, eax
0x180073b2a  jz      short loc_180073B4A
0x180073b2c  mov     r8, rbp; MaxCount
0x180073b2f  lea     rdx, aIphone; "iPhone"
0x180073b36  lea     rcx, [rdi+10Ch]; Str1
0x180073b3d  call    strncmp_0
0x180073b42  test    eax, eax
0x180073b44  jnz     loc_180073F32
0x180073b4a  lea     rdx, [rdi+25720h]; Source
0x180073b51  lea     rcx, [rdi+10Ch]; Destination
0x180073b58  call    strcpy_0
0x180073b5d  jmp     loc_180073F32
0x180073b62  cmp     eax, 8
0x180073b65  jnz     short loc_180073BBA
0x180073b67  mov     r8, rsi; MaxCount
0x180073b6a  lea     rdx, aEosD2000; "EOS D2000"
0x180073b71  lea     rcx, [rdi+10Ch]; Str1
0x180073b78  call    strncmp_0
0x180073b7d  test    eax, eax
0x180073b7f  jz      short loc_180073BDD
0x180073b81  mov     r8, rsi; MaxCount
0x180073b84  lea     rdx, aEosD6000; "EOS D6000"
0x180073b8b  lea     rcx, [rdi+10Ch]; Str1
0x180073b92  call    strncmp_0
0x180073b97  test    eax, eax
0x180073b99  jz      short loc_180073BDD
0x180073b9b  mov     r8, rbp; MaxCount
0x180073b9e  lea     rdx, aEosdcs; "EOSDCS"
0x180073ba5  lea     rcx, [rdi+10Ch]; Str1
0x180073bac  call    strncmp_0
0x180073bb1  test    eax, eax
0x180073bb3  jz      short loc_180073BDD
0x180073bb5  mov     edx, 0Dh
0x180073bba  cmp     dword ptr [rdi+20Ch], 33h ; '3'
0x180073bc1  jnz     short loc_180073BE7
0x180073bc3  mov     r8, rdx; MaxCount
0x180073bc6  lea     rcx, [rdi+10Ch]; String1
0x180073bcd  lea     rdx, aCamerzZds14; "Camerz ZDS 14"
0x180073bd4  call    _strnicmp_0
0x180073bd9  test    eax, eax
0x180073bdb  jnz     short loc_180073BE7
0x180073bdd  mov     edx, 1Dh
0x180073be2  jmp     loc_180073ADF
0x180073be7  lea     rdx, [rdi+0CCh]; Source
0x180073bee  lea     rcx, [rdi+18Ch]; Destination
0x180073bf5  call    strcpy_0
0x180073bfa  jmp     loc_180073AE7
0x180073bff  cmp     eax, 1Dh
0x180073c02  jnz     loc_180073C90
0x180073c08  cmp     byte ptr [rdi+112h], 20h ; ' '
0x180073c0f  jnz     short loc_180073C4F
0x180073c11  mov     r8d, 4; MaxCount
0x180073c17  lea     rdx, aDcs4; "DCS4"
0x180073c1e  lea     rcx, [rdi+10Ch]; Str1
0x180073c25  call    strncmp_0
0x180073c2a  test    eax, eax
0x180073c2c  jz      short loc_180073C48
0x180073c2e  mov     r8, rbp; MaxCount
0x180073c31  lea     rdx, aNc2000; "NC2000"
0x180073c38  lea     rcx, [rdi+10Ch]; Str1
0x180073c3f  call    strncmp_0
0x180073c44  test    eax, eax
0x180073c46  jnz     short loc_180073C4F
0x180073c48  mov     [rdi+112h], r12b
0x180073c4f  movzx   ecx, byte ptr [rdi+112h]
0x180073c56  lea     eax, [rcx-41h]
0x180073c59  test    al, 0F3h
0x180073c5b  jnz     short loc_180073C66
0x180073c5d  cmp     cl, 45h ; 'E'
0x180073c60  jnz     loc_180073F32
0x180073c66  lea     rcx, [rdi+10Ch]; Str1
0x180073c6d  mov     r8, rbp; MaxCount
0x180073c70  lea     rdx, aNc2000; "NC2000"
0x180073c77  call    strncmp_0
0x180073c7c  test    eax, eax
0x180073c7e  jnz     loc_180073F32
0x180073c84  mov     [rdi+112h], r12b
0x180073c8b  jmp     loc_180073F32
0x180073c90  cmp     eax, 38h ; '8'
0x180073c93  jnz     loc_180073F32
0x180073c99  lea     rcx, [rdi+10Ch]; Str1
0x180073ca0  mov     r8d, 3; MaxCount
0x180073ca6  lea     rdx, aGxr; "GXR"
0x180073cad  call    strncmp_0
0x180073cb2  test    eax, eax
0x180073cb4  jnz     loc_180073F32
0x180073cba  movsd   xmm0, qword ptr cs:aRicohGxr; "Ricoh GXR"
0x180073cc2  lea     rbp, [rdi+314h]
0x180073cc9  movsd   qword ptr [rdi+54Ch], xmm0
0x180073cd1  movzx   eax, word ptr cs:aRicohGxr+8; "R"
0x180073cd8  mov     [rdi+554h], ax
0x180073cdf  cmp     [rbp+0], r12b
0x180073ce3  jnz     short loc_180073D1F
0x180073ce5  lea     rdx, [rdi+25720h]; Source
0x180073cec  cmp     [rdx], r12b
0x180073cef  jz      short loc_180073D1F
0x180073cf1  mov     rcx, rbp; Destination
0x180073cf4  call    strcpy_0
0x180073cf9  lea     rdx, aRicoh_0; "Ricoh"
0x180073d00  mov     rcx, rbp; String1
0x180073d03  call    ?remove_caseSubstr@LibRaw@@KAXPEAD0@Z; LibRaw::remove_caseSubstr(char *,char *)
0x180073d08  lea     rdx, aLens; "Lens"
0x180073d0f  mov     rcx, rbp; String1
0x180073d12  call    ?remove_caseSubstr@LibRaw@@KAXPEAD0@Z; LibRaw::remove_caseSubstr(char *,char *)
0x180073d17  mov     rcx, rbp; char *
0x180073d1a  call    ?removeExcessiveSpaces@LibRaw@@KAXPEAD@Z; LibRaw::removeExcessiveSpaces(char *)
0x180073d1f  lea     rbx, [rdi+4B0h]
0x180073d26  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180073d2a  mov     rsi, rbx
0x180073d2d  jnz     short loc_180073D46
0x180073d2f  lea     rdx, a50mm; "50mm"
0x180073d36  mov     rcx, rbp; Str
0x180073d39  call    strstr
0x180073d3e  test    rax, rax
0x180073d41  jz      short loc_180073D6E
0x180073d43  mov     [rbx], r14
0x180073d46  mov     ebp, 6
0x180073d4b  mov     rax, [rsi]
0x180073d4e  dec     rax; switch 8 cases
0x180073d51  cmp     rax, 7
0x180073d55  ja      def_180073D6C; jumptable 0000000180073D6C default case, cases 4,7
0x180073d5b  lea     rcx, __ImageBase
0x180073d62  mov     eax, ds:(jpt_180073D6C - 180000000h)[rcx+rax*4]
0x180073d69  add     rax, rcx
0x180073d6c  jmp     rax; switch jump
0x180073d6e  lea     rdx, aS10; "S10"
0x180073d75  mov     rcx, rbp; Str
0x180073d78  call    strstr
0x180073d7d  test    rax, rax
0x180073d80  jz      short loc_180073D87
0x180073d82  mov     [rbx], r15
0x180073d85  jmp     short loc_180073D46
0x180073d87  lea     rdx, aP10; "P10"
0x180073d8e  mov     rcx, rbp; Str
0x180073d91  call    strstr
0x180073d96  test    rax, rax
0x180073d99  jz      short loc_180073DA4
0x180073d9b  mov     qword ptr [rbx], 3
0x180073da2  jmp     short loc_180073D46
0x180073da4  lea     rdx, a28mm; "28mm"
0x180073dab  mov     rcx, rbp; Str
0x180073dae  call    strstr
0x180073db3  test    rax, rax
0x180073db6  jz      short loc_180073DC1
0x180073db8  mov     qword ptr [rbx], 5
0x180073dbf  jmp     short loc_180073D46
0x180073dc1  lea     rdx, aA16; "A16"
0x180073dc8  mov     rcx, rbp; Str
0x180073dcb  call    strstr
0x180073dd0  test    rax, rax
0x180073dd3  jz      loc_180073D46
0x180073dd9  mov     ebp, 6
0x180073dde  lea     rsi, [rdi+4B0h]
0x180073de5  mov     [rbx], rbp
0x180073de8  jmp     loc_180073D4B
0x180073ded  movsd   xmm0, qword ptr cs:aGxrA1250mm; jumptable 0000000180073D6C case 1
0x180073df5  movsd   qword ptr [rdi+10Ch], xmm0
0x180073dfd  mov     eax, dword ptr cs:aGxrA1250mm+8; "50mm"
0x180073e03  mov     [rdi+114h], eax
0x180073e09  movzx   eax, byte ptr cs:aGxrA1250mm+0Ch; ""
0x180073e10  mov     [rdi+118h], al
0x180073e16  mov     dword ptr [rdi+538h], 2B0001h
0x180073e20  mov     dword ptr [rdi+548h], 230001h
0x180073e2a  mov     [rdi+58Ch], r14w
0x180073e32  jmp     def_180073D6C; jumptable 0000000180073D6C default case, cases 4,7
0x180073e37  mov     rax, 30315320525847h; jumptable 0000000180073D6C case 2
0x180073e41  mov     dword ptr [rdi+538h], 2B0007h
0x180073e4b  mov     [rdi+10Ch], rax
0x180073e52  mov     dword ptr [rdi+548h], 230007h
0x180073e5c  mov     [rdi+58Ch], r15w
0x180073e64  jmp     def_180073D6C; jumptable 0000000180073D6C default case, cases 4,7
0x180073e69  mov     rax, 30315020525847h; jumptable 0000000180073D6C case 3
0x180073e73  mov     dword ptr [rdi+538h], 2B0006h
0x180073e7d  mov     [rdi+10Ch], rax
0x180073e84  mov     dword ptr [rdi+548h], 230006h
0x180073e8e  mov     [rdi+58Ch], r15w
0x180073e96  jmp     def_180073D6C; jumptable 0000000180073D6C default case, cases 4,7
0x180073e9b  movsd   xmm0, qword ptr cs:aGxrA1228mm; jumptable 0000000180073D6C case 5
0x180073ea3  movsd   qword ptr [rdi+10Ch], xmm0
0x180073eab  mov     eax, dword ptr cs:aGxrA1228mm+8; "28mm"
0x180073eb1  mov     [rdi+114h], eax
0x180073eb7  movzx   eax, byte ptr cs:aGxrA1228mm+0Ch; ""
0x180073ebe  jmp     loc_180073E10
0x180073ec3  mov     rax, 36314120525847h; jumptable 0000000180073D6C case 6
0x180073ecd  mov     dword ptr [rdi+538h], 2B0001h
0x180073ed7  mov     [rdi+10Ch], rax
0x180073ede  mov     dword ptr [rdi+548h], 230001h
0x180073ee8  mov     [rdi+58Ch], r15w
0x180073ef0  jmp     short def_180073D6C; jumptable 0000000180073D6C default case, cases 4,7
0x180073ef2  movsd   xmm0, qword ptr cs:aGxrMountA12; jumptable 0000000180073D6C case 8
0x180073efa  movsd   qword ptr [rdi+10Ch], xmm0
0x180073f02  mov     eax, dword ptr cs:aGxrMountA12+8; "t A12"
0x180073f08  mov     [rdi+114h], eax
0x180073f0e  movzx   eax, word ptr cs:aGxrMountA12+0Ch; "2"
0x180073f15  mov     [rdi+118h], ax
0x180073f1c  mov     dword ptr [rdi+548h], 110001h
0x180073f26  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180073f2d  mov     esi, 9; jumptable 0000000180073D6C default case, cases 4,7
0x180073f32  lea     r15, [rdi+10Ch]
0x180073f39  mov     rdx, r15; Source
0x180073f3c  lea     rcx, [rdi+1CCh]; Destination
0x180073f43  call    strcpy_0
0x180073f48  mov     eax, [rdi+20Ch]
0x180073f4e  cmp     eax, 8
0x180073f51  jnz     loc_180074077
0x180073f57  mov     rdx, [rdi+5D1C0h]
0x180073f5e  test    rdx, rdx
0x180073f61  jz      short loc_180073FCB
0x180073f63  mov     rax, 0FFFFFFFF7FFFFAE0h
0x180073f6d  add     rax, rdx
0x180073f70  test    rax, 0FFFFFFFFFFFFFFBFh
0x180073f76  jz      loc_180074C16
0x180073f7c  lea     r14, byte_1800CE0D0
0x180073f83  mov     ecx, r12d
0x180073f86  mov     rax, r14
0x180073f89  lea     r8, qword_1800CEA10
0x180073f90  cmp     rdx, [rax]
0x180073f93  jz      short loc_180073FA5
0x180073f95  inc     ecx
0x180073f97  add     rax, 20h ; ' '
0x180073f9b  cmp     rax, r8
0x180073f9e  jl      short loc_180073F90
0x180073fa0  jmp     loc_180074C16
0x180073fa5  movsxd  rbx, ecx
0x180073fa8  lea     rdx, [r14+8]
0x180073fac  shl     rbx, 5
0x180073fb0  lea     rcx, [rdi+10Ch]; Destination
0x180073fb7  add     rdx, rbx; Source
0x180073fba  call    strcpy_0
0x180073fbf  lea     rdx, [r14+8]
0x180073fc3  add     rdx, rbx
0x180073fc6  jmp     loc_180074C0A
0x180073fcb  cmp     [rdi+214h], r12d
0x180073fd2  jz      loc_180074C16
0x180073fd8  lea     rcx, [rdi+25720h]; Str
0x180073fdf  call    strlen_0
0x180073fe4  cmp     rax, 6
  ... truncated ...
```

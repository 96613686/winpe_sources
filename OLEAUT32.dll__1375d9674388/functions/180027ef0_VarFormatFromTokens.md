# VarFormatFromTokens

- ea: `0x180027ef0`
- end: `0x18002a103`
- name: `VarFormatFromTokens`
- size: `8723`
- prototype: `HRESULT __stdcall(LPVARIANT pvarIn, LPOLESTR pstrFormat, LPBYTE pbTokCur, ULONG dwFlags, BSTR *pbstrOut, LCID lcid)`
- caller_count: `5`
- callee_count: `28`
- tags: `installer_update`

## callers

- `0x180026620`
- `0x180044920`
- `0x180077cd0`
- `0x180077df0`
- `0x180077e60`

## callees

- `0x1800043d4`
- `0x180005790`
- `0x1800057e0`
- `0x180007590`
- `0x1800078c0`
- `0x18000a780`
- `0x180027c44`
- `0x180027ed0`
- `0x180027ef0`
- `0x18002a10c`
- `0x18002a360`
- `0x18002a74c`
- `0x18002a79c`
- `0x18002ac34`
- `0x18002b020`
- `0x18002cf58`
- `0x180032ff8`
- `0x180042770`
- `0x1800491e4`
- `0x18004d900`
- `0x18007773c`
- `0x1800779a8`
- `0x180077a94`
- `0x180077b5c`
- `0x180077c38`
- `0x18009a624`
- `0x18009a630`
- `0x18009b1d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180029ee4`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180029ee4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800284b2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800284b2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180028b1d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180028b1d`

## pseudocode

```c
HRESULT __stdcall VarFormatFromTokens(
        LPVARIANT pvarIn,
        LPOLESTR pstrFormat,
        LPBYTE pbTokCur,
        ULONG dwFlags,
        BSTR *pbstrOut,
        LCID lcid)
{
  int v6; // r10d
  __int64 *v8; // r12
  LPVARIANT p_pvargDest; // rdi
  VARTYPE vt; // ax
  int v11; // esi
  __m128i st; // xmm6
  LCID v13; // r15d
  int v14; // eax
  __int64 v15; // r13
  __int64 v16; // r14
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HRESULT result; // eax
  HRESULT v22; // eax
  HRESULT NumInfo; // ebx
  int v24; // edi
  int v25; // r11d
  unsigned __int16 v26; // r9
  OLECHAR *v27; // rsi
  unsigned __int8 *v28; // rcx
  unsigned int v29; // r8d
  unsigned __int8 *v30; // r15
  unsigned int v31; // ebx
  unsigned __int16 epi16; // r14
  unsigned __int16 v33; // dx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  int v36; // r8d
  BSTR v37; // rax
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  unsigned int v40; // ebx
  unsigned int v41; // ebx
  unsigned __int16 *v42; // rcx
  unsigned __int16 *v43; // rdx
  __int64 Info; // rax
  int DateInfo; // eax
  __int64 v46; // r10
  LPOLESTR *v47; // r9
  int v48; // r14d
  int v49; // eax
  const wchar_t *v50; // rdx
  BSTR bstrVal; // rbx
  UINT v52; // eax
  wchar_t v53; // r15
  const wchar_t *v54; // r13
  wchar_t *v55; // rsi
  wchar_t *v56; // rdi
  const wchar_t *v57; // rbx
  wchar_t *v58; // rax
  wchar_t *v59; // r13
  int v60; // esi
  const wchar_t *i; // rbx
  int v62; // r11d
  char v63; // r10
  int v64; // r9d
  LPOLESTR *v65; // r9
  OLECHAR *v66; // rcx
  __int16 v67; // ax
  __int64 v68; // rcx
  size_t v69; // r8
  OLECHAR *v70; // rbx
  size_t v71; // r8
  OLECHAR *v72; // r9
  void **v73; // rdi
  unsigned int v74; // ebx
  unsigned int v75; // ebx
  unsigned int v76; // ebx
  unsigned int v77; // ebx
  unsigned int v78; // ebx
  unsigned int v79; // ebx
  struct tagDATEINFO *v80; // r14
  int v81; // edi
  signed int v82; // ebx
  int v83; // edi
  signed int v84; // ebx
  int v85; // ecx
  struct IDispatch **ppdispVal; // rcx
  bool v87; // zf
  char *pcVal; // rsi
  signed int v89; // eax
  char v90; // bl
  int v91; // r13d
  __int64 v92; // rbx
  LONGLONG llVal; // xmm0_8
  __int64 v94; // r8
  int v95; // edx
  int v96; // edx
  int v97; // ecx
  int v98; // eax
  int v99; // ecx
  wchar_t *v100; // rcx
  __int64 v101; // rcx
  int v102; // ecx
  signed int v103; // ecx
  unsigned __int16 v104; // ax
  unsigned __int16 v105; // kr00_2
  unsigned __int16 v106; // kr02_2
  OLECHAR *v107; // r8
  unsigned int v108; // ecx
  OLECHAR v109; // cx
  int v110; // ecx
  LPOLESTR *v111; // rcx
  LCID v112; // ecx
  int v113; // eax
  int v114; // edx
  int v115; // r8d
  unsigned int v116; // ecx
  unsigned int v117; // ebx
  unsigned int v118; // ebx
  unsigned int v119; // ebx
  unsigned int v120; // ebx
  __int16 v121; // r11
  __int64 v122; // rdi
  unsigned __int16 v123; // ax
  unsigned int v124; // ebx
  unsigned int v125; // ebx
  int v126; // eax
  int v127; // eax
  int v128; // eax
  unsigned __int16 v129; // kr04_2
  int v130; // edx
  int v131; // r8d
  int WeekOfYear; // eax
  int ImperialEra; // eax
  __int64 v134; // rcx
  int v135; // r8d
  int v136; // edx
  __int16 v137; // ax
  __int16 *v138; // rax
  int v139; // r14d
  int v140; // edi
  struct tagDATEINFO *v141; // rbx
  int v142; // eax
  unsigned int v143; // ecx
  int v144; // eax
  __int16 v145; // ax
  _WORD *v146; // rax
  __int16 v147; // cx
  _BYTE *v148; // rsi
  int v149; // eax
  __int16 *v150; // rdx
  __int16 v151; // ax
  int v152; // ecx
  __int64 v153; // rbx
  __int64 v154; // rax
  int v155; // ebx
  __int64 v156; // r14
  wchar_t v157; // dx
  __int64 v158; // rdx
  OLECHAR *v159; // r10
  OLECHAR v160; // ax
  __int64 v161; // r10
  const struct tagBOOLINF near *const *v162; // r9
  int j; // edx
  __int64 v164; // rcx
  __int16 v165; // r8
  const struct tagBOOLINF near *const *v166; // rax
  __int64 v167; // rcx
  LPOLESTR *v168; // rbx
  size_t v169; // r8
  size_t v170; // r8
  OLECHAR *v171; // rbx
  int v172; // [rsp+38h] [rbp-D0h]
  unsigned __int8 *v173; // [rsp+40h] [rbp-C8h]
  struct tagDATEINFO *v174; // [rsp+48h] [rbp-C0h]
  int v175; // [rsp+50h] [rbp-B8h]
  int v177; // [rsp+58h] [rbp-B0h]
  int v178; // [rsp+5Ch] [rbp-ACh]
  unsigned int v179; // [rsp+60h] [rbp-A8h]
  unsigned __int16 v180; // [rsp+64h] [rbp-A4h]
  LPOLESTR *prgp; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v182; // [rsp+70h] [rbp-98h]
  void *Src; // [rsp+78h] [rbp-90h] BYREF
  int v184; // [rsp+80h] [rbp-88h]
  unsigned int v185; // [rsp+84h] [rbp-84h]
  LPOLESTR *v186; // [rsp+88h] [rbp-80h]
  const wchar_t *v187; // [rsp+90h] [rbp-78h]
  VARIANTARG pvargDest; // [rsp+98h] [rbp-70h] BYREF
  int v189; // [rsp+B0h] [rbp-58h]
  int v190; // [rsp+B4h] [rbp-54h]
  LPBYTE v191; // [rsp+B8h] [rbp-50h]
  UDATE pudateOut; // [rsp+C8h] [rbp-40h] BYREF
  int v193; // [rsp+E8h] [rbp-20h]
  int v194; // [rsp+ECh] [rbp-1Ch]
  __int64 wDayOfYear; // [rsp+F0h] [rbp-18h]
  int v196; // [rsp+F8h] [rbp-10h]
  LPOLESTR v197; // [rsp+100h] [rbp-8h]
  BSTR *v198; // [rsp+108h] [rbp+0h]
  __int64 v199; // [rsp+110h] [rbp+8h]
  OLECHAR strIn[1024]; // [rsp+118h] [rbp+10h] BYREF
  WCHAR DestStr[256]; // [rsp+918h] [rbp+810h] BYREF

  v6 = 0;
  v174 = 0;
  Src = 0;
  v8 = (__int64 *)pbTokCur;
  v186 = 0;
  p_pvargDest = pvarIn;
  prgp = 0;
  v191 = pbTokCur;
  v197 = pstrFormat;
  v198 = pbstrOut;
  if ( !pvarIn || !pbstrOut )
    return -2147024809;
  *pbstrOut = 0;
  vt = pvarIn->vt;
  v11 = pvarIn->vt & 0xBFFF;
  wDayOfYear = 0;
  st = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  memset(&pudateOut, 0, sizeof(pudateOut));
  if ( v11 != 9 )
  {
    v13 = lcid;
LABEL_5:
    if ( v8 && *(_BYTE *)v8 )
    {
LABEL_56:
      NumInfo = GetNumInfo(v13, 0, (struct tagNUMINFO **)&prgp);
      if ( NumInfo < 0 )
        goto LABEL_36;
      DateInfo = GetDateInfo(v13, dwFlags & 0x80000000, (struct CDateInfo **)&Src);
      v6 = 0;
      NumInfo = DateInfo;
      if ( DateInfo < 0 )
        goto LABEL_36;
      v174 = (struct tagDATEINFO *)Src;
      v186 = prgp;
      goto LABEL_9;
    }
    if ( v11 == 8 )
    {
      v14 = FormatVarToNum(&pvargDest, p_pvargDest, v13);
      v6 = 0;
      if ( v14 < 0 )
        goto LABEL_8;
      v11 = pvargDest.vt;
      p_pvargDest = &pvargDest;
    }
    if ( v11 != 11 )
    {
      v8 = qword_1800B4598;
      if ( v11 != 7 )
        v8 = &qword_1800B4500;
      v191 = (LPBYTE)v8;
      goto LABEL_56;
    }
LABEL_8:
    v8 = qword_1800AD510;
    v191 = (LPBYTE)qword_1800AD510;
LABEL_9:
    LODWORD(v15) = 0;
    v187 = 0;
    Src = 0;
    v175 = 0;
    v178 = 0;
    v177 = 0;
    while ( 1 )
    {
      v16 = *((unsigned __int8 *)v8 + 2);
      if ( !*((_BYTE *)v8 + 2) )
        goto LABEL_156;
      v17 = *((unsigned __int8 *)v8 + 1);
      v194 = v17;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              if ( v20 == 1 )
              {
                if ( v11 == 1 )
                  goto LABEL_198;
                if ( v11 == 8 )
                {
                  v73 = (p_pvargDest->vt & 0x4000) != 0
                      ? (void **)p_pvargDest->llVal
                      : (void **)&p_pvargDest->decVal.Lo32;
                  pcVal = (char *)*v73;
                }
                else
                {
                  result = VariantChangeTypeEx(&pvargDest, p_pvargDest, v13, 2u, 8u);
                  if ( result < 0 )
                    return result;
                  pcVal = pvargDest.pcVal;
                }
                Src = pcVal;
                if ( !SysStringLen((BSTR)pcVal) )
                {
LABEL_198:
                  v16 = *((unsigned __int8 *)v8 + 3);
                  if ( !*((_BYTE *)v8 + 3) )
                    return 0;
                  pcVal = 0;
                  Src = 0;
                }
                v89 = SysStringLen((BSTR)pcVal);
                v90 = *((_BYTE *)v8 + v16);
                LODWORD(v15) = v89;
                v24 = *((unsigned __int8 *)v8 + v16 + 3);
                v178 = v24;
                if ( v89 > 255 )
                  LODWORD(v15) = 255;
                if ( (v90 & 3) != 0 && (v90 & 3) != 3 )
                {
                  LCMapStringW(v13, (((v90 & 1) == 0) + 1) << 8, (LPCWSTR)pcVal, v15, DestStr, 256);
                  pcVal = (char *)DestStr;
                  Src = DestStr;
                }
                if ( (int)v15 > v24 && (v90 & 4) != 0 )
                {
                  v91 = v15 - v24;
                  v92 = v91;
                  if ( &strIn[v92] >= DestStr )
                    goto LABEL_156;
                  memcpy_0(strIn, pcVal, 2LL * v91);
                  LODWORD(v15) = v24;
                  Src = &pcVal[v92 * 2];
                }
                v25 = 0;
                v6 = 0;
                goto LABEL_21;
              }
            }
            else
            {
              if ( v11 == 1 )
                return 0;
              while ( 1 )
              {
                result = VariantChangeTypeEx(&pvargDest, p_pvargDest, v13, dwFlags, 7u);
                if ( result >= 0 )
                  break;
                if ( v11 != 8 )
                  return result;
                result = FormatVarToNum(&pvargDest, p_pvargDest, v13);
                v6 = 0;
                if ( result < 0 )
                  goto LABEL_178;
                v11 = pvargDest.vt;
                p_pvargDest = &pvargDest;
              }
              v22 = VarUdateFromDate(pvargDest.dblVal, dwFlags, &pudateOut);
              v6 = 0;
              NumInfo = v22;
              if ( v22 < 0 )
                goto LABEL_36;
              st = (__m128i)pudateOut.st;
              wDayOfYear = pudateOut.wDayOfYear;
            }
            v24 = 0;
LABEL_20:
            v25 = 0;
            goto LABEL_21;
          }
        }
      }
      if ( v11 <= 6 )
        break;
      if ( v11 == 7 )
      {
        if ( (p_pvargDest->vt & 0x4000) != 0 )
          llVal = *p_pvargDest->pllVal;
        else
          llVal = p_pvargDest->llVal;
        pvargDest.llVal = llVal;
LABEL_216:
        pvargDest.vt = 5;
LABEL_217:
        p_pvargDest = &pvargDest;
LABEL_84:
        if ( (_BYTE)v194 == 1 )
        {
          result = VariantChangeTypeEx(&pvargDest, p_pvargDest, v13, 0, 8u);
          if ( result < 0 )
            return result;
          *v198 = pvargDest.bstrVal;
          return 0;
        }
        result = VariantChangeTypeEx(&pvargDest, p_pvargDest, 0x409u, 4u, 8u);
        if ( result < 0 )
          return result;
        bstrVal = pvargDest.bstrVal;
        v52 = SysStringLen(pvargDest.bstrVal);
        v53 = *bstrVal;
        v54 = bstrVal + 1;
        v55 = &bstrVal[v52];
        if ( *bstrVal != 45 )
          v54 = bstrVal;
        v187 = v54;
        v56 = wmemchr(v54, 0x2Eu, v55 - v54);
        v57 = v56 + 1;
        if ( !v56 )
          v57 = v54;
        v58 = wmemchr(v57, 0x45u, v55 - v57);
        v59 = v58;
        if ( v58 )
        {
          v60 = _o__wtoi(v58 + 1);
        }
        else
        {
          v59 = v55;
          v60 = 0;
        }
        v175 = v60;
        if ( v56 )
        {
          v94 = v59 - v57;
          v60 -= v94;
          v175 = v60;
          memmove_0(v56, v57, 2 * v94);
          --v59;
        }
        for ( i = v187; *i == 48; ++i )
          ;
        v187 = i;
        v15 = v59 - i;
        if ( !(_DWORD)v15 )
          goto LABEL_223;
        v62 = 0;
        if ( v53 == 45 )
        {
          if ( !*((_BYTE *)v8 + 3) || *((_BYTE *)v8 + *((unsigned __int8 *)v8 + 3) + 5) == 2 )
            v177 = 1;
          else
            LODWORD(v16) = *((unsigned __int8 *)v8 + 3);
        }
        while ( 2 )
        {
          v63 = *((_BYTE *)v8 + (unsigned int)v16);
          if ( !(_DWORD)v15 )
          {
            v25 = v175;
            v64 = v63 & 2;
            v6 = 0;
            goto LABEL_100;
          }
          if ( (v63 & 1) != 0 )
            v95 = v60 + 2 * *((unsigned __int8 *)v8 + (unsigned int)v16 + 1);
          else
            v95 = v60;
          v96 = -3 * *((unsigned __int8 *)v8 + (unsigned int)v16 + 2) + v95;
          v97 = *((unsigned __int8 *)v8 + (unsigned int)v16 + 4);
          v64 = v63 & 2;
          if ( (v63 & 2) != 0 )
            v98 = v97 + *((unsigned __int8 *)v8 + (unsigned int)v16 + 3);
          else
            v98 = v15 + v97 + v96;
          v99 = 0;
          if ( v98 >= 0 )
            v99 = v98;
          if ( (v63 & 0x20) == 0 && v99 < (int)v15 )
          {
            v100 = (wchar_t *)&i[v99];
            if ( *v100 < 0x35u )
            {
              --v100;
LABEL_243:
              if ( v100 >= i )
                goto LABEL_244;
            }
            else
            {
              while ( v100 != i )
              {
                if ( ++*--v100 != 58 )
                  goto LABEL_243;
              }
              *v100 = 49;
              ++v96;
              do
              {
LABEL_244:
                if ( *v100 != 48 )
                  break;
                --v100;
              }
              while ( v100 >= i );
            }
            v101 = v100 - i;
            v96 += v15 - v101 - 1;
            LODWORD(v15) = v101 + 1;
          }
          v6 = 0;
          if ( v64
            || (v102 = *((unsigned __int8 *)v8 + (unsigned int)v16 + 4), v96 + v102 + (int)v15 > 0)
            || !*((_BYTE *)v8 + (unsigned int)v16 + 3) && !(_BYTE)v102
            || v62 )
          {
            v25 = v96;
            v175 = v96;
LABEL_100:
            v24 = *((unsigned __int8 *)v8 + (unsigned int)v16 + 3);
            v178 = v24;
            if ( v64 && (_DWORD)v15 )
            {
              v25 += v15 - v24;
              v175 = v25;
            }
            else
            {
              if ( v24 < v25 + (int)v15 )
                v24 = v25 + v15;
              v178 = v24;
            }
LABEL_21:
            v26 = _mm_cvtsi128_si32(st);
            v27 = strIn;
            v28 = 0;
            v172 = 0;
            v173 = 0;
            v29 = *((unsigned __int8 *)v8 + (unsigned int)v16);
            v30 = (unsigned __int8 *)v8 + (unsigned int)v16 + 5;
            v185 = v29;
            LODWORD(v182) = 0;
            v184 = 0;
            v190 = 0;
            v189 = 0;
            v179 = 0;
            v199 = (unsigned int)v16;
            v193 = 0;
            v196 = 1023;
            v180 = v26;
            while ( 1 )
            {
              v31 = *v30++;
              epi16 = _mm_extract_epi16(st, 1);
              v33 = _mm_extract_epi16(st, 4);
              while ( 1 )
              {
                if ( v31 > 0x21 )
                {
                  if ( v31 > 0x32 )
                  {
                    if ( v31 <= 0x3A )
                    {
                      switch ( v31 )
                      {
                        case ':':
                          goto LABEL_501;
                        case '3':
                          v66 = v27 + 1;
                          if ( v27 + 1 >= DestStr )
                            goto LABEL_156;
                          v67 = 97;
                          if ( v33 >= 0xCu )
                            v67 = 112;
                          goto LABEL_116;
                        case '4':
                        case '5':
                          v46 = *v30;
                          if ( &v27[v46] >= DestStr )
                            goto LABEL_156;
                          v47 = v186;
                          if ( (v29 & 4) != 0 )
                          {
                            v152 = *((unsigned __int16 *)v186 + 27);
                            v48 = 3;
                            v184 = 3;
                            v190 = v152;
                            if ( (v29 & 0x18) != 0 )
                            {
                              if ( (v29 & 0x10) != 0 )
                              {
                                v48 = *((_DWORD *)v186 + 17);
                              }
                              else
                              {
                                v48 = *((_DWORD *)v186 + 21);
                                v190 = *((unsigned __int16 *)v186 + 32);
                              }
                              v184 = v48;
                            }
                          }
                          else
                          {
                            v48 = v184;
                          }
                          v49 = *((unsigned __int8 *)v8 + v199 + 3);
                          if ( v24 > v49 )
                            LODWORD(v46) = v24 + v46 - v49;
                          while ( 2 )
                          {
                            if ( (int)v46 <= 0 )
                            {
                              ++v30;
                              goto LABEL_51;
                            }
                            if ( (int)v15 <= 0 )
                            {
                              if ( (v29 & 0x102) != 2 && (v29 & 0x300) != 0x200 )
                                goto LABEL_123;
                            }
                            else
                            {
                              if ( v177 )
                              {
                                if ( v27 + 1 >= DestStr )
                                  goto LABEL_156;
                                *v27++ = *((_WORD *)v47 + 30);
                                v177 = 0;
                              }
                              if ( (v29 & 2) != 0 || v25 + (_DWORD)v15 == v24 )
                              {
                                if ( v27 + 1 >= DestStr )
                                  goto LABEL_156;
                                v50 = v187 + 1;
                                *v27++ = *v187;
                                v187 = v50;
                                LODWORD(v15) = v15 - 1;
LABEL_77:
                                v29 |= 0x200u;
                                v185 = v29;
                                if ( (v29 & 4) != 0 && v24 > 1 && v48 > 0 && (v24 % v48 == 1 || v48 == 1) )
                                {
                                  if ( v27 + 1 >= DestStr )
                                    goto LABEL_156;
                                  *v27++ = v190;
                                }
LABEL_78:
                                v47 = v186;
                                LODWORD(v46) = v46 - 1;
                                v178 = --v24;
                                continue;
                              }
                              if ( (v29 & 0x300) == 0 )
                              {
LABEL_123:
                                if ( v31 != 52 )
                                {
                                  if ( (v29 & 0x100) != 0 )
                                    LODWORD(v15) = v15 - 1;
                                  goto LABEL_78;
                                }
                                if ( (v29 & 0x100) != 0 && (int)v15 < 0 )
                                {
                                  v71 = -(int)v15;
                                  if ( &v27[v71] >= DestStr )
                                    goto LABEL_156;
                                  wmemset(v27, 0, v71);
                                  v29 = v185;
                                  LODWORD(v15) = 0;
                                  v27 = v72;
                                }
                              }
                            }
                            break;
                          }
                          if ( v27 + 1 >= DestStr )
                            goto LABEL_156;
                          *v27++ = 48;
                          goto LABEL_77;
                        case '6':
                          if ( (v29 & 0x100) != 0 )
                          {
                            if ( v27 + 1 >= DestStr )
                              goto LABEL_156;
                            *v27++ = 46;
                            goto LABEL_53;
                          }
                          if ( v177 )
                          {
                            if ( v27 + 1 >= DestStr )
                              goto LABEL_156;
                            v65 = v186;
                            v177 = 0;
                            *v27++ = *((_WORD *)v186 + 30);
                          }
                          else
                          {
                            v65 = v186;
                          }
                          if ( &v27[v24 + 1] >= DestStr )
                            goto LABEL_156;
                          if ( v24 > 0 )
                          {
                            v150 = (__int16 *)v187;
                            do
                            {
                              if ( (_DWORD)v15 )
                              {
                                v151 = *v150;
                                LODWORD(v15) = v15 - 1;
                                ++v150;
                              }
                              else
                              {
                                v151 = 48;
                              }
                              *v27 = v151;
                              --v24;
                              ++v27;
                            }
                            while ( v24 > 0 );
                            v6 = v172;
                            v187 = (const wchar_t *)v150;
                            v178 = v24;
                          }
                          v66 = v27 + 1;
                          if ( v27 + 1 >= DestStr )
                            goto LABEL_156;
                          if ( (v29 & 8) != 0 )
                            v67 = *((_WORD *)v65 + 31);
                          else
                            v67 = *((_WORD *)v65 + 26);
                          v185 = v29 & 0xFFFFFEFB | 0x100;
                          goto LABEL_116;
                        case '7':
                        case '8':
                          v146 = v27 + 1;
                          if ( v27 + 1 >= DestStr )
                            goto LABEL_156;
                          v31 += 2;
                          v147 = 69;
                          break;
                        default:
LABEL_501:
                          v146 = v27 + 1;
                          if ( v27 + 1 >= DestStr )
                            goto LABEL_156;
                          v147 = 101;
                          break;
                      }
                      *v27 = v147;
                      if ( v25 >= 0 )
                      {
                        if ( v31 == 57 )
                        {
                          v148 = v146 + 1;
                          if ( v146 + 1 >= DestStr )
                            goto LABEL_156;
                          *v146 = 43;
                        }
                        else
                        {
                          v148 = v146;
                        }
                      }
                      else
                      {
                        v148 = v146 + 1;
                        if ( v146 + 1 >= DestStr )
                          goto LABEL_156;
                        *v146 = 45;
                        v149 = v25;
                        v25 = -v25;
                        if ( v25 < 0 )
                          v25 = v149;
                        v175 = v25;
                      }
                      v153 = *v30;
                      if ( &v148[2 * v153] >= (_BYTE *)DestStr )
                        goto LABEL_156;
                      ++v30;
                      _o__itow_s((unsigned int)v25, v148, ((char *)DestStr - v148) >> 1, 10);
                      v154 = -1;
                      do
                        ++v154;
                      while ( *(_WORD *)&v148[2 * v154] );
                      v155 = v153 - v154;
                      v156 = 2LL * (int)v154;
                      if ( v155 > 0 )
                      {
                        memmove_0(&v148[2 * v155], v148, 2LL * (int)v154);
                        wmemset((wchar_t *)v148, v157, v155);
                        v148 += 2 * v155;
                      }
                      v27 = (OLECHAR *)&v148[v156];
                      goto LABEL_51;
                    }
                    if ( v31 == 59 )
                    {
                      v168 = v186;
                      v169 = *((int *)v186 + 6);
                      if ( &v27[v169] >= DestStr )
                        goto LABEL_156;
                      memcpy_0(v27, v186 + 4, v169 * 2);
                      Info = *((int *)v168 + 6);
                      goto LABEL_50;
                    }
                    if ( v31 != 60 )
                    {
                      switch ( v31 )
                      {
                        case '=':
                          v161 = 1;
                          break;
                        case '>':
                          v161 = 3;
                          break;
                        case '?':
                          v161 = 5;
                          break;
                        default:
                          if ( v31 - 64 > 1 )
                            goto LABEL_53;
                          v158 = *v30;
                          if ( &v27[v158] >= DestStr )
                            goto LABEL_156;
                          ++v30;
                          if ( !(_DWORD)v158 )
                            goto LABEL_52;
                          v159 = (OLECHAR *)Src;
                          do
                          {
                            if ( (int)v15 > 0 && ((int)v15 >= v24 || (v29 & 4) != 0) )
                            {
                              v160 = *v159++;
                              *v27++ = v160;
                              LODWORD(v15) = v15 - 1;
                            }
                            else if ( v31 == 64 )
                            {
                              *v27++ = 32;
                            }
                            LODWORD(v158) = v158 - 1;
                            --v24;
                          }
                          while ( (int)v158 > 0 );
                          v8 = (__int64 *)v191;
                          Src = v159;
                          v178 = v24;
                          goto LABEL_51;
                      }
                      v162 = &rgbiList;
                      for ( j = 0; ; ++j )
                      {
                        if ( j >= 25 )
                          goto LABEL_577;
                        v164 = (__int64)j << 6;
                        v165 = *(_WORD *)((char *)&rgbiList + v164 + 4);
                        if ( v165 )
                        {
                          if ( v165 == ((unsigned __int16)v196 & (unsigned __int16)lcid) )
                            break;
                        }
                        v166 = (const struct tagBOOLINF near *const *)((char *)&rgbiList + v164);
                        if ( lcid == *(_DWORD *)((char *)&rgbiList + v164) )
                          goto LABEL_576;
                      }
                      v166 = (const struct tagBOOLINF near *const *)((char *)&rgbiList + v164);
LABEL_576:
                      v162 = v166;
LABEL_577:
                      v167 = 0;
                      if ( (int)v15 > 0 )
                        v167 = 8;
                      v42 = *(unsigned __int16 **)((char *)&v162[v161] + v167);
                      goto LABEL_48;
                    }
                    v66 = v27 + 1;
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    v67 = *((_WORD *)v186 + 30);
LABEL_116:
                    *v27 = v67;
                    v27 = v66;
                    goto LABEL_52;
                  }
                  if ( v31 == 50 )
                  {
                    if ( v27 + 2 >= DestStr )
                      goto LABEL_156;
                    v145 = 97;
                    if ( v33 >= 0xCu )
                      v145 = 112;
                    *v27 = v145;
                    v27[1] = 109;
                    goto LABEL_466;
                  }
                  if ( v31 <= 0x2A )
                  {
                    switch ( v31 )
                    {
                      case '*':
                        goto LABEL_411;
                      case '"':
                        if ( v33 >= 0xAu )
                          goto LABEL_421;
                        break;
                      case '#':
LABEL_421:
                        if ( v27 + 1 >= DestStr )
                          goto LABEL_156;
                        *v27++ = v33 / 0xAu + 48;
                        v33 = _mm_extract_epi16(st, 4);
                        break;
                      case '$':
                        v43 = v27;
                        goto LABEL_377;
                      case '%':
                        v43 = v27;
                        goto LABEL_373;
                      case '&':
                        if ( (dwFlags & 8) != 0 )
                        {
                          v42 = (unsigned __int16 *)g_rgszHijriMonth2[epi16 - 1];
                          if ( v42 )
                            goto LABEL_48;
                        }
                        v43 = v27;
                        goto LABEL_304;
                      case '\'':
                        if ( (dwFlags & 8) == 0 || (v42 = (unsigned __int16 *)g_rgszHijriMonth2[epi16 - 1]) == 0 )
                          v42 = (unsigned __int16 *)*((_QWORD *)v174 + epi16 + 14);
                        goto LABEL_48;
                      default:
                        if ( v31 - 40 > 1 )
                          goto LABEL_53;
LABEL_411:
                        if ( (unsigned int)IsJapan(lcid) )
                        {
                          pudateOut.wDayOfYear = wDayOfYear;
                          pudateOut.st = (SYSTEMTIME)st;
                          ImperialEra = GetImperialEra(&pudateOut, v174);
                          v189 = ImperialEra;
                          if ( ImperialEra < 0 )
                            goto LABEL_51;
                          v42 = (unsigned __int16 *)*((_QWORD *)v174 + 6 * ImperialEra + v31 + 34);
                        }
                        else if ( (unsigned int)IsTaiwan(lcid) )
                        {
                          if ( *((_DWORD *)v174 + 583) )
                          {
                            if ( v31 <= 0x28 )
                              goto LABEL_51;
                            v134 = v31 - 40;
                            if ( v180 >= 0x778u )
                              v42 = (unsigned __int16 *)*((_QWORD *)v174 + v134 + 76);
                            else
                              v42 = (unsigned __int16 *)*((_QWORD *)v174 + v134 + 72);
                          }
                          else
                          {
                            if ( *v30 )
                              goto LABEL_51;
                            v135 = v30[2];
                            v136 = 0;
                            if ( v30[2] )
                            {
                              while ( v197[v136 + v30[1]] == 32 )
                              {
                                if ( ++v136 >= v135 )
                                  goto LABEL_435;
                              }
                              goto LABEL_51;
                            }
LABEL_435:
                            if ( v136 != v135 )
                            {
LABEL_51:
                              v6 = v172;
                              goto LABEL_52;
                            }
                            v42 = 0;
                            v30 += 3;
                          }
                        }
                        else
                        {
                          if ( (unsigned int)IsKorea(lcid) )
                          {
                            if ( v31 > 0x29 )
                            {
                              v42 = (unsigned __int16 *)&qword_1800B4370;
                              if ( *((_WORD *)v174 + 1171) != 5 )
                                v42 = (unsigned __int16 *)&qword_1800B4368;
                              goto LABEL_48;
                            }
                            goto LABEL_51;
                          }
                          if ( !(unsigned int)IsThai(lcid) )
                            goto LABEL_51;
                          if ( (*((_WORD *)v174 + 1171) != 7 || (dwFlags & 0x100) != 0) && (dwFlags & 0x80u) == 0 )
                          {
                            v42 = (unsigned __int16 *)&psz;
                            goto LABEL_48;
                          }
                          v42 = (unsigned __int16 *)*((_QWORD *)v174 + 79);
                        }
                        if ( v42 )
                          goto LABEL_48;
                        goto LABEL_51;
                    }
                    v107 = v27 + 1;
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    v108 = v33;
                    goto LABEL_271;
                  }
                  if ( v31 != 43 && v31 != 44 )
                  {
                    if ( v31 == 45 )
                    {
                      v66 = v27 + 1;
                      if ( v27 + 1 >= DestStr )
                        goto LABEL_156;
                      if ( v33 >= 0xCu )
                        v138 = (__int16 *)((char *)v174 + 52);
                      else
                        v138 = (__int16 *)((char *)v174 + 28);
                      v67 = *v138;
                      goto LABEL_116;
                    }
                    if ( v31 == 46 )
                      goto LABEL_456;
                    if ( v31 != 47 )
                    {
                      if ( v31 == 48 )
                      {
                        v66 = v27 + 1;
                        if ( v27 + 1 >= DestStr )
                          goto LABEL_156;
                        v67 = 65;
                        if ( v33 >= 0xCu )
                          v67 = 80;
                        goto LABEL_116;
                      }
LABEL_456:
                      if ( v33 >= 0xCu )
                        v42 = (unsigned __int16 *)((char *)v174 + 52);
                      else
                        v42 = (unsigned __int16 *)((char *)v174 + 28);
                      goto LABEL_48;
                    }
                    if ( v27 + 2 >= DestStr )
                      goto LABEL_156;
                    v137 = 65;
                    if ( v33 >= 0xCu )
                      v137 = 80;
                    *v27 = v137;
                    v27[1] = 77;
LABEL_466:
                    v27 += 2;
                    goto LABEL_53;
                  }
                  v139 = v31 - 42;
                  v140 = 4;
                  if ( (unsigned int)IsJapan(lcid) )
                  {
                    v141 = v174;
                    pudateOut.wDayOfYear = wDayOfYear;
                    pudateOut.st = (SYSTEMTIME)st;
                    v142 = GetImperialEra(&pudateOut, v174);
                    v189 = v142;
                    if ( v142 >= 0 )
                    {
                      v143 = v180 - *((__int16 *)v174 + 24 * v142 + 284) + 1;
                      goto LABEL_487;
                    }
                    v144 = v180;
LABEL_481:
                    v179 = v144;
LABEL_489:
                    if ( (unsigned int)IsJapan(lcid)
                      && v189 >= 0
                      && v179 == 1
                      && !*((_DWORD *)v141 + 812)
                      && !*v30
                      && (unsigned int)IsPrefix(&v197[v30[1]], v30[2], *((const unsigned __int16 **)v141 + 132), v141) )
                    {
                      *v27++ = *((_WORD *)v141 + 1160);
                      goto LABEL_51;
                    }
                    v116 = v179;
                    v115 = v139;
                    v114 = v140;
                    goto LABEL_312;
                  }
                  if ( (unsigned int)IsTaiwan(lcid) )
                  {
                    v141 = v174;
                    v144 = v180;
                    if ( !*((_DWORD *)v174 + 583) )
                      goto LABEL_481;
                    v143 = 1912;
                    if ( v180 >= 0x778u )
                    {
                      v144 = v180 - 1911;
                      goto LABEL_481;
                    }
LABEL_485:
                    v143 -= v144;
                  }
                  else
                  {
                    if ( !(unsigned int)IsKorea(lcid) )
                    {
                      v141 = v174;
                      goto LABEL_489;
                    }
                    v143 = v180 + 2333;
                    v87 = v31 == 43;
                    v141 = v174;
                    if ( v87 )
                    {
                      v140 = 2;
                      v139 = 2;
                      v144 = 100 * (v143 / 0x64);
                      goto LABEL_485;
                    }
                    v140 = 5;
                    v139 = 1;
                  }
LABEL_487:
                  v179 = v143;
                  goto LABEL_489;
                }
                if ( v31 == 33 )
                  goto LABEL_261;
                if ( v31 <= 0x10 )
                  break;
                if ( v31 <= 0x19 )
                {
                  if ( v31 != 25 )
                  {
                    v38 = v31 - 17;
                    if ( v38 )
                    {
                      v39 = v38 - 1;
                      if ( v39 )
                      {
                        v40 = v39 - 1;
                        if ( v40 )
                        {
                          v41 = v40 - 1;
                          if ( !v41 )
                          {
                            if ( (dwFlags & 8) != 0 )
                            {
                              v111 = (LPOLESTR *)g_rgszHijriMonth2;
                              goto LABEL_297;
                            }
                            if ( v193 != 1 || (lcid & 0x3FF) == 1 )
                              goto LABEL_592;
                            v112 = *((_DWORD *)v174 + 4);
                            prgp = 0;
                            NumInfo = GetAltMonthNames(v112, &prgp);
                            if ( NumInfo < 0 )
                              goto LABEL_36;
                            v111 = prgp;
                            if ( prgp )
                            {
LABEL_297:
                              v42 = v111[epi16 - 1];
                            }
                            else
                            {
LABEL_592:
                              if ( (unsigned int)IsDBCS(lcid) )
                                v42 = (unsigned __int16 *)((char *)v174 + 64 * (unsigned __int64)epi16 + 1112);
                              else
                                v42 = (unsigned __int16 *)*((_QWORD *)v174 + epi16 + 14);
                            }
LABEL_48:
                            v43 = v27;
LABEL_49:
                            Info = GetInfo(v42, v43, DestStr);
LABEL_50:
                            v27 += Info;
                            goto LABEL_51;
                          }
                          v78 = v41 - 1;
                          if ( v78 )
                          {
                            v79 = v78 - 1;
                            if ( v79 )
                            {
                              if ( v79 - 1 > 1 )
                                goto LABEL_53;
                              v80 = v174;
LABEL_150:
                              v81 = v26;
                              v82 = v26 / 0x64u;
                              if ( (unsigned int)IsThai(lcid)
                                && ((dwFlags & 0x80u) != 0 || *((_WORD *)v80 + 1171) == 7 && (dwFlags & 0x100) == 0) )
                              {
                                v82 = (v81 + 543) / 0x64u;
                                if ( v82 >= 100 )
                                {
                                  if ( v27 + 5 >= DestStr )
                                    goto LABEL_156;
                                  *v27++ = (__int16)v82 / 100 + 48;
                                  v82 %= 100;
                                }
                              }
                              if ( v27 + 4 >= DestStr )
                                goto LABEL_156;
                              v26 = v180;
                              v172 = 0;
                              *v27 = v82 / 10 + 48;
                              v27[1] = v82 % 10 + 48;
                              v27 += 2;
                            }
                            else
                            {
                              v172 = v6;
                              if ( v6 )
                              {
                                v80 = v174;
                                v85 = *((__int16 *)v174 + 1168);
                                if ( v26 < v85 - 99 )
                                  goto LABEL_150;
                                v172 = 0;
                                if ( v26 > v85 )
                                  goto LABEL_150;
                              }
                            }
                            v83 = v26;
                            v84 = v26 % 0x64u;
                            if ( (unsigned int)IsThai(lcid)
                              && ((dwFlags & 0x80u) != 0 || *((_WORD *)v174 + 1171) == 7 && (dwFlags & 0x100) == 0) )
                            {
                              v84 = (v83 + 543) % 0x64u;
                            }
                            if ( v27 + 2 >= DestStr )
                              goto LABEL_156;
                            *v27 = v84 / 10 + 48;
                            v27[1] = v84 % 10 + 48;
                            v27 += 2;
                            goto LABEL_51;
                          }
                          v110 = (unsigned __int16)wDayOfYear;
                          if ( (unsigned __int16)wDayOfYear >= 0x64u )
                          {
                            if ( v27 + 1 >= DestStr )
                              goto LABEL_156;
                            *v27++ = (unsigned __int16)wDayOfYear / 0x64u + 48;
                            v110 %= 0x64u;
LABEL_389:
                            if ( v27 + 1 >= DestStr )
                              goto LABEL_156;
                            *v27++ = v110 / 10 + 48;
                            LOWORD(v110) = v110 % 10;
LABEL_391:
                            if ( v27 + 1 >= DestStr )
                              goto LABEL_156;
                            *v27++ = v110 + 48;
                            goto LABEL_52;
                          }
LABEL_388:
                          if ( v110 >= 10 )
                            goto LABEL_389;
                          goto LABEL_391;
                        }
                        if ( (dwFlags & 8) != 0 )
                        {
                          v42 = (unsigned __int16 *)g_rgszHijriMonth2[epi16 - 1];
                          goto LABEL_48;
                        }
                        v113 = IsDBCS(lcid);
                        v43 = v27;
                        if ( v113 )
                        {
                          v42 = (unsigned __int16 *)((char *)v174 + 8 * epi16 + 1936);
                          goto LABEL_49;
                        }
LABEL_304:
                        v42 = (unsigned __int16 *)*((_QWORD *)v174 + epi16 + 26);
                        goto LABEL_49;
                      }
LABEL_306:
                      if ( v27 + 1 >= DestStr )
                        goto LABEL_156;
                      *v27++ = epi16 / 0xAu + 48;
                    }
                    else if ( epi16 >= 0xAu )
                    {
                      goto LABEL_306;
                    }
                    v107 = v27 + 1;
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    v108 = epi16;
                    goto LABEL_271;
                  }
                  v114 = 2;
                  v115 = 1;
                  v116 = v26 % 0x64u;
LABEL_312:
                  Info = RenderInt(v116, v114, v115, v27, DestStr);
                  goto LABEL_50;
                }
                switch ( v31 )
                {
                  case 0x1Au:
                    v104 = _mm_extract_epi16(st, 5);
                    if ( v104 < 0xAu )
                      goto LABEL_269;
                    goto LABEL_278;
                  case 0x1Bu:
                    v104 = _mm_extract_epi16(st, 5);
LABEL_278:
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    v106 = v104;
                    v104 = _mm_extract_epi16(st, 5);
                    *v27++ = v106 / 0xAu + 48;
                    goto LABEL_269;
                  case 0x1Cu:
                    v104 = _mm_extract_epi16(st, 6);
                    if ( v104 >= 0xAu )
                      goto LABEL_267;
                    goto LABEL_269;
                  case 0x1Du:
                    v104 = _mm_extract_epi16(st, 6);
LABEL_267:
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    v105 = v104;
                    v104 = _mm_extract_epi16(st, 6);
                    *v27++ = v105 / 0xAu + 48;
LABEL_269:
                    v107 = v27 + 1;
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    v108 = v104;
LABEL_271:
                    v103 = v108 % 0xA;
                    goto LABEL_272;
                }
                if ( v31 != 30 && v31 != 31 )
                {
LABEL_261:
                  v103 = v33;
                  if ( v33 <= 0xCu )
                  {
                    if ( !v33 )
                      v103 = 12;
                  }
                  else
                  {
                    v103 = v33 - 12;
                  }
                  if ( v31 == 33 || v103 >= 10 )
                  {
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    *v27++ = v103 / 10 + 48;
                  }
                  v107 = v27 + 1;
                  if ( v27 + 1 < DestStr )
                  {
                    LOWORD(v103) = v103 % 10;
LABEL_272:
                    v109 = v103 + 48;
LABEL_273:
                    *v27 = v109;
LABEL_274:
                    v27 = v107;
LABEL_52:
                    v28 = v173;
                    goto LABEL_53;
                  }
LABEL_156:
                  NumInfo = -2147024809;
                  goto LABEL_36;
                }
                v31 += 4;
              }
              if ( v31 == 16 )
              {
                v130 = *v30;
                if ( !*v30 )
                  v130 = *((__int16 *)v174 + 1169);
                v131 = v30[1];
                v30 += 2;
                if ( !v131 )
                  v131 = *((__int16 *)v174 + 1170);
                pudateOut.wDayOfYear = wDayOfYear;
                pudateOut.st = (SYSTEMTIME)st;
                WeekOfYear = GetWeekOfYear(&pudateOut, v130, v131, lcid, dwFlags);
                v6 = v172;
                v110 = WeekOfYear;
                goto LABEL_388;
              }
              if ( v31 > 8 )
              {
                v74 = v31 - 9;
                if ( v74 )
                {
                  v75 = v74 - 1;
                  if ( v75 )
                  {
                    v76 = v75 - 1;
                    if ( v76 )
                    {
                      v77 = v76 - 1;
                      if ( v77 )
                      {
                        v124 = v77 - 1;
                        if ( v124 )
                        {
                          v125 = v124 - 1;
                          if ( v125 )
                          {
                            if ( v125 != 1 )
                              goto LABEL_53;
                            v126 = *v30;
                            if ( !*v30 )
                              v126 = *((__int16 *)v174 + 1169);
                            v107 = v27 + 1;
                            if ( v27 + 1 >= DestStr )
                              goto LABEL_156;
                            ++v30;
                            v109 = (_mm_extract_epi16(st, 2) - v126 + 8) % 7 + 49;
                            goto LABEL_273;
                          }
                          if ( *((_QWORD *)v174 + 296)
                            || (GetMediumDateFormat((unsigned __int8 **)v174 + 296, lcid),
                                v6 = v172,
                                *((_QWORD *)v174 + 296)) )
                          {
                            v28 = v30;
                            v30 = (unsigned __int8 *)*((_QWORD *)v174 + 296);
                            v173 = v28;
                            goto LABEL_53;
                          }
                        }
                        else if ( *((_QWORD *)v174 + 294)
                               || (GetNlsFormat(0x20u, (unsigned __int8 **)v174 + 294, lcid),
                                   v6 = v172,
                                   *((_QWORD *)v174 + 294)) )
                        {
                          v28 = v30;
                          v30 = (unsigned __int8 *)*((_QWORD *)v174 + 294);
                          v173 = v28;
                          goto LABEL_53;
                        }
                      }
                      else if ( *((_QWORD *)v174 + 293)
                             || (GetNlsFormat(0x1Fu, (unsigned __int8 **)v174 + 293, lcid),
                                 v6 = v172,
                                 *((_QWORD *)v174 + 293)) )
                      {
                        v28 = v30;
                        v30 = (unsigned __int8 *)*((_QWORD *)v174 + 293);
                        v173 = v28;
                        goto LABEL_53;
                      }
                      goto LABEL_158;
                    }
                    v127 = IsDBCS(lcid);
                    v43 = v27;
                    if ( v127 )
                    {
                      v42 = (unsigned __int16 *)((char *)v174 + 32 * (unsigned int)_mm_extract_epi16(st, 2) + 2040);
                      goto LABEL_49;
                    }
LABEL_373:
                    v42 = (unsigned __int16 *)*((_QWORD *)v174 + (unsigned int)_mm_extract_epi16(st, 2) + 57);
                    goto LABEL_49;
                  }
                  v128 = IsDBCS(lcid);
                  v43 = v27;
                  if ( v128 )
                  {
                    v42 = (unsigned __int16 *)((char *)v174 + 8 * (unsigned int)_mm_extract_epi16(st, 2) + 2264);
                    goto LABEL_49;
                  }
LABEL_377:
                  v42 = (unsigned __int16 *)*((_QWORD *)v174 + (unsigned int)_mm_extract_epi16(st, 2) + 64);
                  goto LABEL_49;
                }
                v123 = _mm_extract_epi16(st, 3);
LABEL_379:
                if ( v27 + 1 >= DestStr )
                  goto LABEL_156;
                v129 = v123;
                v123 = _mm_extract_epi16(st, 3);
                *v27++ = v129 / 0xAu + 48;
LABEL_381:
                if ( v27 + 1 >= DestStr )
                  goto LABEL_156;
                v193 = 1;
                *v27++ = v123 % 0xAu + 48;
                goto LABEL_52;
              }
              if ( v31 == 8 )
              {
                v123 = _mm_extract_epi16(st, 3);
                if ( v123 >= 0xAu )
                  goto LABEL_379;
                goto LABEL_381;
              }
              if ( !v31 )
              {
                if ( v177 )
                {
                  if ( v27 + 1 >= DestStr )
                    goto LABEL_156;
                  v177 = 0;
                  *v27++ = *((_WORD *)v186 + 30);
                }
                v68 = *v30;
                v69 = v30[1];
                v70 = &v27[v69];
                if ( &v27[v69] >= DestStr )
                  goto LABEL_156;
                if ( v197 )
                {
                  v30 += 2;
                  memcpy_0(v27, &v197[v68], v69 * 2);
                  v27 = v70;
                  goto LABEL_51;
                }
                return -2147024809;
              }
              v34 = v31 - 1;
              if ( !v34 )
              {
                v122 = 2LL * *v30;
                if ( &v27[(unsigned __int64)v122 / 2] >= DestStr )
                  goto LABEL_156;
                memcpy_0(v27, v30 + 1, 2LL * *v30);
                v27 = (OLECHAR *)((char *)v27 + v122);
                v30 += v122 + 1;
                goto LABEL_51;
              }
              v35 = v34 - 1;
              if ( v35 )
              {
                v117 = v35 - 1;
                if ( !v117 )
                {
                  v42 = (unsigned __int16 *)((char *)v174 + 92);
                  goto LABEL_48;
                }
                v118 = v117 - 1;
                if ( !v118 )
                {
                  v42 = (unsigned __int16 *)((char *)v174 + 76);
                  goto LABEL_48;
                }
                v119 = v118 - 1;
                if ( v119 )
                {
                  v120 = v119 - 1;
                  if ( !v120 )
                  {
                    v107 = v27 + 1;
                    if ( v27 + 1 >= DestStr )
                      goto LABEL_156;
                    *v27 = (epi16 - 1) / 3 + 49;
                    goto LABEL_274;
                  }
                  if ( v120 != 1 )
                    goto LABEL_53;
                  if ( *((_QWORD *)v174 + 295)
                    || (GetNlsFormat(0x1003u, (unsigned __int8 **)v174 + 295, lcid), v6 = v172, *((_QWORD *)v174 + 295)) )
                  {
                    v28 = v30;
                    v30 = (unsigned __int8 *)*((_QWORD *)v174 + 295);
                    v173 = v28;
                    goto LABEL_53;
                  }
LABEL_158:
                  NumInfo = -2147024882;
                  goto LABEL_36;
                }
                if ( epi16 != 12 || (v121 = _mm_extract_epi16(st, 3), v121 != 30) || v26 != 1899 )
                {
                  if ( *((_QWORD *)v174 + 293)
                    || (GetNlsFormat(0x1Fu, (unsigned __int8 **)v174 + 293, lcid),
                        v33 = _mm_extract_epi16(st, 4),
                        *((_QWORD *)v174 + 293)) )
                  {
                    v28 = v30;
                    v30 = (unsigned __int8 *)*((_QWORD *)v174 + 293);
                    v6 = 1;
                    v172 = 1;
                    v173 = v28;
                    if ( v33 || (unsigned __int16)_mm_extract_epi16(st, 5) || (unsigned __int16)_mm_extract_epi16(st, 6) )
                      LODWORD(v182) = 1;
                    goto LABEL_53;
                  }
                  goto LABEL_158;
                }
                v36 = v182;
LABEL_336:
                if ( v36 )
                {
                  if ( v27 + 1 >= DestStr )
                    goto LABEL_156;
                  *v27++ = 32;
                }
                if ( !v33
                  && !(unsigned __int16)_mm_extract_epi16(st, 5)
                  && !(unsigned __int16)_mm_extract_epi16(st, 6)
                  && (epi16 != 12 || v121 != 30 || v26 != 1899) )
                {
                  LODWORD(v182) = 0;
                  goto LABEL_53;
                }
                if ( *((_QWORD *)v174 + 295)
                  || (GetNlsFormat(0x1003u, (unsigned __int8 **)v174 + 295, lcid),
                      v28 = v173,
                      v6 = v172,
                      v36 = v182,
                      *((_QWORD *)v174 + 295)) )
                {
                  LODWORD(v182) = 0;
                  if ( !v36 )
                    v28 = v30;
                  v30 = (unsigned __int8 *)*((_QWORD *)v174 + 295);
                  v173 = v28;
                  goto LABEL_53;
                }
                goto LABEL_158;
              }
              v36 = v182;
              if ( (_DWORD)v182 )
              {
                v121 = _mm_extract_epi16(st, 3);
                goto LABEL_336;
              }
              if ( !v28 )
              {
                if ( (_BYTE)v194 == 4 && (_DWORD)v15 )
                {
                  v170 = (int)v15;
                  v171 = &v27[v170];
                  if ( &v27[v170] < DestStr )
                  {
                    memcpy_0(v27, Src, v170 * 2);
                    v27 = v171;
                    goto LABEL_35;
                  }
                  goto LABEL_156;
                }
LABEL_35:
                v37 = SysAllocStringLen(strIn, v27 - strIn);
                *v198 = v37;
                NumInfo = v37 == 0 ? 0x8007000E : 0;
LABEL_36:
                VariantClear(&pvargDest);
                return NumInfo;
              }
              v30 = v28;
              v28 = 0;
              v173 = 0;
LABEL_53:
              if ( v27 + 10 >= DestStr )
                goto LABEL_156;
              v24 = v178;
              v29 = v185;
              v26 = v180;
              v25 = v175;
            }
          }
LABEL_223:
          v16 = *((unsigned __int8 *)v8 + 4);
          v62 = 1;
          if ( !*((_BYTE *)v8 + 4) || *((_BYTE *)v8 + v16 + 5) == 2 )
            LODWORD(v16) = *((unsigned __int8 *)v8 + 2);
          v177 = 0;
          continue;
        }
      }
      if ( v11 != 8 )
      {
        if ( v11 == 11 || v11 == 14 || v11 == 17 )
          goto LABEL_84;
        v87 = v11 == 20;
LABEL_189:
        if ( v87 )
          goto LABEL_84;
      }
      result = FormatVarToNum(&pvargDest, p_pvargDest, v13);
      v6 = 0;
      if ( result >= 0 )
      {
        if ( pvargDest.vt != 7 )
          goto LABEL_217;
        goto LABEL_216;
      }
LABEL_178:
      if ( (dwFlags & 0x20) != 0 )
        return result;
      v8 = qword_1800AD510;
      v191 = (LPBYTE)qword_1800AD510;
    }
    switch ( v11 )
    {
      case 6:
        goto LABEL_84;
      case 0:
        return 0;
      case 1:
        LODWORD(v16) = *((unsigned __int8 *)v8 + 5);
        if ( *((_BYTE *)v8 + 5) )
        {
          v24 = 0;
          LODWORD(v15) = 0;
          goto LABEL_20;
        }
        return 0;
      case 2:
      case 3:
      case 4:
        goto LABEL_84;
    }
    v87 = v11 == 5;
    goto LABEL_189;
  }
  if ( (vt & 0x4000) != 0 )
  {
    if ( !pvarIn->llVal )
      return -2147352571;
    ppdispVal = pvarIn->ppdispVal;
  }
  else
  {
    ppdispVal = &pvarIn->pdispVal;
  }
  v13 = lcid;
  result = ExtractValueProperty(*ppdispVal, lcid, &pvargDest);
  if ( result > -1 )
  {
    v11 = pvargDest.vt;
    p_pvargDest = &pvargDest;
    v6 = 0;
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x180027ef0  mov     rax, rsp
0x180027ef3  push    rbp
0x180027ef4  push    rbx
0x180027ef5  push    rsi
0x180027ef6  push    rdi
0x180027ef7  push    r12
0x180027ef9  push    r13
0x180027efb  push    r14
0x180027efd  push    r15
0x180027eff  lea     rbp, [rax-0A78h]
0x180027f06  sub     rsp, 0B38h
0x180027f0d  movaps  xmmword ptr [rax-58h], xmm6
0x180027f11  mov     rax, cs:__security_cookie
0x180027f18  xor     rax, rsp
0x180027f1b  mov     [rbp+0A70h+var_60], rax
0x180027f22  mov     rax, [rbp+0A70h+pbstrOut]
0x180027f29  xor     r10d, r10d
0x180027f2c  mov     [rsp+0B70h+dwFlags], r9d
0x180027f31  mov     ebx, r10d
0x180027f34  mov     [rsp+0B70h+var_B30], rbx
0x180027f39  mov     r14d, r9d
0x180027f3c  mov     [rsp+0B70h+Src], rbx
0x180027f41  mov     r12, r8
0x180027f44  mov     [rbp+0A70h+var_AF0], rbx
0x180027f48  mov     rdi, rcx
0x180027f4b  mov     [rsp+0B70h+prgp], rbx
0x180027f50  mov     [rbp+0A70h+var_AC0], r8
0x180027f54  mov     [rbp+0A70h+var_A78], rdx
0x180027f58  mov     [rbp+0A70h+var_A70], rax
0x180027f5c  test    rcx, rcx
0x180027f5f  jz      loc_18002A0F9
0x180027f65  test    rax, rax
0x180027f68  jz      loc_18002A0F9
0x180027f6e  xor     ecx, ecx
0x180027f70  mov     [rax], r10
0x180027f73  movzx   eax, word ptr [rdi]
0x180027f76  xorps   xmm0, xmm0
0x180027f79  mov     esi, eax
0x180027f7b  mov     qword ptr [rbp+0A70h+pvargDest+10h], rcx
0x180027f7f  btr     esi, 0Eh
0x180027f83  mov     [rbp+0A70h+var_A88], rcx
0x180027f87  mov     [rbp+0A70h+pudateOut.wDayOfYear], cx
0x180027f8b  xorps   xmm6, xmm6
0x180027f8e  movups  xmmword ptr [rbp+0A70h+pvargDest], xmm0
0x180027f92  movups  xmmword ptr [rbp+0A70h+pudateOut.st.wYear], xmm6
0x180027f96  cmp     esi, 9
0x180027f99  jz      loc_180028928
0x180027f9f  mov     r15d, [rbp+0A70h+lcid]
0x180027fa6  mov     ecx, 7
0x180027fab  test    r12, r12
0x180027fae  jnz     loc_180028284
0x180027fb4  cmp     esi, 8
0x180027fb7  jnz     loc_180028985
0x180027fbd  mov     r8d, r15d; unsigned int
0x180027fc0  lea     rcx, [rbp+0A70h+pvargDest]; pvar
0x180027fc4  mov     rdx, rdi; struct tagVARIANT *
0x180027fc7  call    ?FormatVarToNum@@YAJPEAUtagVARIANT@@0K@Z; FormatVarToNum(tagVARIANT *,tagVARIANT *,ulong)
0x180027fcc  xor     r10d, r10d
0x180027fcf  test    eax, eax
0x180027fd1  jns     loc_180028978
0x180027fd7  lea     r12, qword_1800AD510
0x180027fde  mov     [rbp+0A70h+var_AC0], r12
0x180027fe2  mov     ebx, [rsp+0B70h+dwFlags]
0x180027fe6  mov     r13d, r10d
0x180027fe9  mov     [rbp+0A70h+var_AE8], r10
0x180027fed  mov     [rsp+0B70h+Src], r10
0x180027ff2  mov     [rsp+0B70h+var_B28], r10d
0x180027ff7  mov     [rsp+0B70h+var_B1C], r10d
0x180027ffc  mov     [rsp+0B70h+var_B20], r10d
0x180028001  mov     edx, 1
0x180028006  movzx   r14d, byte ptr [r12+2]
0x18002800c  test    r14d, r14d
0x18002800f  jz      loc_1800288AD
0x180028015  movzx   eax, byte ptr [r12+1]
0x18002801b  mov     [rbp+0A70h+var_A8C], eax
0x18002801e  test    eax, eax
0x180028020  jz      loc_1800283DF
0x180028026  sub     eax, edx
0x180028028  jz      loc_1800283DF
0x18002802e  sub     eax, edx
0x180028030  jz      loc_1800283DF
0x180028036  sub     eax, edx
0x180028038  jnz     loc_1800286CA
0x18002803e  cmp     esi, edx
0x180028040  jz      loc_18002878C
0x180028046  movzx   r9d, bx; wFlags
0x18002804a  mov     [rsp+0B70h+vt], 7; vt
0x180028051  mov     r8d, r15d; lcid
0x180028054  lea     rcx, [rbp+0A70h+pvargDest]; pvargDest
0x180028058  mov     rdx, rdi; pvarSrc
0x18002805b  call    VariantChangeTypeEx
0x180028060  test    eax, eax
0x180028062  js      loc_1800289AB
0x180028068  movsd   xmm0, qword ptr [rbp+0A70h+pvargDest+8]; dateIn
0x18002806d  lea     r8, [rbp+0A70h+pudateOut]; pudateOut
0x180028071  mov     edx, ebx; dwFlags
0x180028073  call    VarUdateFromDate
0x180028078  xor     r10d, r10d
0x18002807b  mov     ebx, eax
0x18002807d  test    eax, eax
0x18002807f  js      loc_180028197
0x180028085  movzx   eax, [rbp+0A70h+pudateOut.wDayOfYear]
0x180028089  movups  xmm6, xmmword ptr [rbp+0A70h+pudateOut.st.wYear]
0x18002808d  mov     [rbp+0A70h+var_A88], rax
0x180028091  mov     edi, r13d
0x180028094  mov     r11d, edi
0x180028097  xor     edx, edx
0x180028099  mov     eax, r14d
0x18002809c  movd    r9d, xmm6
0x1800280a1  lea     rsi, [rbp+0A70h+strIn]
0x1800280a5  mov     rcx, r10
0x1800280a8  mov     dword ptr [rsp+0B70h+var_B40], r10d
0x1800280ad  mov     [rsp+0B70h+var_B38], rcx
0x1800280b2  movzx   r8d, byte ptr [rax+r12]
0x1800280b7  lea     r15, [rax+5]
0x1800280bb  add     r15, r12
0x1800280be  mov     [rsp+0B70h+var_AF4], r8d
0x1800280c3  mov     dword ptr [rsp+0B70h+var_B08], edx
0x1800280c7  mov     [rsp+0B70h+var_AF8], edx
0x1800280cb  mov     [rbp+0A70h+var_AC4], edx
0x1800280ce  mov     [rbp+0A70h+var_AC8], edx
0x1800280d1  mov     [rsp+0B70h+var_B18], edx
0x1800280d5  mov     [rbp+0A70h+var_A68], rax
0x1800280d9  mov     [rbp+0A70h+var_A90], edx
0x1800280dc  mov     [rbp+0A70h+var_A80], 3FFh
0x1800280e3  mov     [rsp+0B70h+var_B18+4], r9d
0x1800280e8  movzx   ebx, byte ptr [r15]
0x1800280ec  inc     r15
0x1800280ef  pextrw  r14d, xmm6, 1
0x1800280f5  pextrw  edx, xmm6, 4
0x1800280fa  cmp     ebx, 21h ; '!'
0x1800280fd  ja      loc_1800282E2
0x180028103  jz      loc_180028D8B
0x180028109  cmp     ebx, 10h
0x18002810c  ja      loc_1800281CD
0x180028112  jz      loc_180029624
0x180028118  mov     r11d, 8
0x18002811e  cmp     ebx, r11d
0x180028121  ja      loc_1800286FF
0x180028127  jz      loc_180029409
0x18002812d  xor     edi, edi
0x18002812f  test    ebx, ebx
0x180028131  jz      loc_1800285E5
0x180028137  sub     ebx, 1
0x18002813a  jz      loc_1800293A3
0x180028140  sub     ebx, 1
0x180028143  jnz     loc_180029187
0x180028149  mov     r8d, dword ptr [rsp+0B70h+var_B08]
0x18002814e  test    r8d, r8d
0x180028151  jnz     loc_1800292DB
0x180028157  xor     r14d, r14d
0x18002815a  test    rcx, rcx
0x18002815d  jnz     loc_180028756
0x180028163  cmp     byte ptr [rbp+0A70h+var_A8C], 4
0x180028167  jz      loc_18002A0C0
0x18002816d  lea     rax, [rbp+0A70h+strIn]
0x180028171  sub     rsi, rax
0x180028174  lea     rcx, [rbp+0A70h+strIn]; strIn
0x180028178  sar     rsi, 1
0x18002817b  mov     edx, esi; ui
0x18002817d  call    SysAllocStringLen
0x180028182  mov     rcx, [rbp+0A70h+var_A70]
0x180028186  mov     ebx, 8007000Eh
0x18002818b  mov     [rcx], rax
0x18002818e  neg     rax
0x180028191  sbb     ecx, ecx
0x180028193  not     ecx
0x180028195  and     ebx, ecx
0x180028197  lea     rcx, [rbp+0A70h+pvargDest]; pvarg
0x18002819b  call    VariantClear
0x1800281a0  mov     eax, ebx
0x1800281a2  mov     rcx, [rbp+0A70h+var_60]
0x1800281a9  xor     rcx, rsp; StackCookie
0x1800281ac  call    __security_check_cookie
0x1800281b1  movaps  xmm6, [rsp+0B70h+var_58+8]
0x1800281b9  add     rsp, 0B38h
0x1800281c0  pop     r15
0x1800281c2  pop     r14
0x1800281c4  pop     r13
0x1800281c6  pop     r12
0x1800281c8  pop     rdi
0x1800281c9  pop     rsi
0x1800281ca  pop     rbx
0x1800281cb  pop     rbp
0x1800281cc  retn
0x1800281cd  cmp     ebx, 19h
0x1800281d0  ja      loc_180028D5A
0x1800281d6  jz      loc_180029147
0x1800281dc  mov     eax, r10d
0x1800281df  sub     ebx, 11h
0x1800281e2  jz      loc_1800290E7
0x1800281e8  sub     ebx, 1
0x1800281eb  jz      loc_1800290F8
0x1800281f1  sub     ebx, 1
0x1800281f4  jz      loc_180029079
0x1800281fa  sub     ebx, 1
0x1800281fd  jnz     loc_180028793
0x180028203  test    byte ptr [rsp+0B70h+dwFlags], 8
0x180028208  jnz     loc_180029005
0x18002820e  mov     rdi, [rsp+0B70h+var_B30]
0x180028213  lea     ecx, [rbx+1]
0x180028216  cmp     [rbp+0A70h+var_A90], ecx
0x180028219  jz      loc_18002900E
0x18002821f  mov     ecx, [rbp+0A70h+lcid]
0x180028225  call    IsDBCS
0x18002822a  test    eax, eax
0x18002822c  jnz     loc_180029062
0x180028232  movzx   eax, r14w
0x180028236  mov     rcx, [rdi+rax*8+70h]; Src
0x18002823b  mov     rdx, rsi; unsigned __int16 *
0x18002823e  lea     r8, [rbp+0A70h+DestStr]; unsigned __int16 *
0x180028245  call    ?GetInfo@@YA_JPEAG00@Z; GetInfo(ushort *,ushort *,ushort *)
0x18002824a  lea     rsi, [rsi+rax*2]
0x18002824e  mov     r10d, dword ptr [rsp+0B70h+var_B40]
0x180028253  mov     rcx, [rsp+0B70h+var_B38]
0x180028258  lea     rax, [rsi+14h]
0x18002825c  lea     rdx, [rbp+0A70h+DestStr]
0x180028263  cmp     rax, rdx
0x180028266  jnb     loc_1800288AD
0x18002826c  mov     edi, [rsp+0B70h+var_B1C]
0x180028270  mov     r8d, [rsp+0B70h+var_AF4]
0x180028275  mov     r9d, [rsp+0B70h+var_B18+4]
0x18002827a  mov     r11d, [rsp+0B70h+var_B28]
0x18002827f  jmp     loc_1800280E8
0x180028284  cmp     [r12], r10b
0x180028288  jz      loc_180027FB4
0x18002828e  lea     r8, [rsp+0B70h+prgp]; struct tagNUMINFO **
0x180028293  xor     edx, edx; unsigned int
0x180028295  mov     ecx, r15d; unsigned int
0x180028298  call    ?GetNumInfo@@YAJKKPEAPEAUtagNUMINFO@@@Z; GetNumInfo(ulong,ulong,tagNUMINFO * *)
0x18002829d  mov     ebx, eax
0x18002829f  test    eax, eax
0x1800282a1  js      loc_180028197
0x1800282a7  mov     edx, r14d
0x1800282aa  lea     r8, [rsp+0B70h+Src]
0x1800282af  and     edx, 80000000h
0x1800282b5  mov     ecx, r15d
0x1800282b8  call    GetDateInfo
0x1800282bd  xor     r10d, r10d
0x1800282c0  mov     ebx, eax
0x1800282c2  test    eax, eax
0x1800282c4  js      loc_180028197
0x1800282ca  mov     rax, [rsp+0B70h+Src]
0x1800282cf  mov     [rsp+0B70h+var_B30], rax
0x1800282d4  mov     rax, [rsp+0B70h+prgp]
0x1800282d9  mov     [rbp+0A70h+var_AF0], rax
0x1800282dd  jmp     loc_180027FE2
0x1800282e2  cmp     ebx, 32h ; '2'
0x1800282e5  jbe     loc_180029740
0x1800282eb  mov     eax, 3Ah ; ':'
0x1800282f0  cmp     ebx, eax
0x1800282f2  ja      loc_180029F2E
0x1800282f8  jz      loc_180029C8E
0x1800282fe  mov     eax, ebx
0x180028300  sub     eax, 33h ; '3'
0x180028303  jz      loc_180029E5C
0x180028309  sub     eax, 1
0x18002830c  jz      short loc_180028317
0x18002830e  sub     eax, 1
0x180028311  jnz     loc_180028561
0x180028317  movzx   r10d, byte ptr [r15]
0x18002831b  lea     rax, [rbp+0A70h+DestStr]
0x180028322  lea     rcx, [rsi+r10*2]
0x180028326  cmp     rcx, rax
0x180028329  jnb     loc_1800288AD
0x18002832f  mov     r9, [rbp+0A70h+var_AF0]
0x180028333  test    r8b, 4
0x180028337  jnz     loc_180029D87
0x18002833d  mov     r14d, [rsp+0B70h+var_AF8]
0x180028342  mov     rax, [rbp+0A70h+var_A68]
0x180028346  movzx   eax, byte ptr [rax+r12+3]
0x18002834c  cmp     edi, eax
0x18002834e  jle     short loc_180028356
0x180028350  sub     r10d, eax
0x180028353  add     r10d, edi
0x180028356  xor     edx, edx; C
0x180028358  test    r10d, r10d
0x18002835b  jle     loc_18002854E
0x180028361  test    r13d, r13d
0x180028364  jle     loc_180028639
0x18002836a  cmp     [rsp+0B70h+var_B20], edx
0x18002836e  jnz     loc_180029DCE
0x180028374  test    r8b, 2
0x180028378  jnz     short loc_180028386
0x18002837a  lea     eax, [r11+r13]
0x18002837e  cmp     eax, edi
0x180028380  jnz     loc_180029DF6
0x180028386  lea     rcx, [rsi+2]
0x18002838a  lea     rax, [rbp+0A70h+DestStr]
0x180028391  cmp     rcx, rax
0x180028394  jnb     loc_1800288AD
0x18002839a  mov     rdx, [rbp+0A70h+var_AE8]
0x18002839e  movzx   eax, word ptr [rdx]
0x1800283a1  add     rdx, 2
0x1800283a5  mov     [rsi], ax
0x1800283a8  mov     rsi, rcx
0x1800283ab  mov     ecx, 1
0x1800283b0  mov     [rbp+0A70h+var_AE8], rdx
0x1800283b4  sub     r13d, ecx
0x1800283b7  bts     r8d, 9
  ... truncated ...
```

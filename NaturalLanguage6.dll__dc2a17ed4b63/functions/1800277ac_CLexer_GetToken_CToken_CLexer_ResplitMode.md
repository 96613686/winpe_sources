# CLexer::GetToken(CToken &,CLexer::ResplitMode)

- ea: `0x1800277ac`
- end: `0x180028cfb`
- name: `?GetToken@CLexer@@QEAA?AW4ResplitMode@1@AEAVCToken@@W421@@Z`
- size: `5455`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: ``

## callers

- `0x18002924c`

## callees

- `0x180008d38`
- `0x180008d70`
- `0x180009690`
- `0x1800277ac`
- `0x180028d04`
- `0x180028d3c`
- `0x180028e0c`
- `0x180028e40`
- `0x180028e7c`
- `0x180029594`
- `0x180029a04`
- `0x180029d64`
- `0x180029e94`
- `0x180029ecc`
- `0x180029f50`
- `0x180029f9c`
- `0x18002a01c`
- `0x18002a0d0`
- `0x180033f40`
- `0x1800361f4`
- `0x180036260`
- `0x180036578`
- `0x180036bd8`
- `0x180036e30`
- `0x18003712c`
- `0x180037154`
- `0x180037180`
- `0x180037400`
- `0x180037528`
- `0x180037684`
- `0x180075cec`
- `0x180075d44`
- `0x180075f50`
- `0x180075fa4`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall CLexer::GetToken(_QWORD *a1, __int64 a2, int a3)
{
  __int64 v3; // r14
  int v4; // r15d
  const unsigned __int16 *v6; // rbx
  __int64 v9; // r8
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  int v12; // edi
  unsigned int v13; // r15d
  int v14; // r10d
  int v15; // r10d
  int v16; // ebp
  char v17; // r10
  char v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rax
  char v21; // dl
  int v22; // r10d
  __int64 v23; // rcx
  const struct SSItem *v24; // rbx
  const struct SSItem *v25; // rax
  __int64 v26; // r15
  unsigned int SubstringWithLookaheadBreak; // r10d
  __int64 v28; // r8
  unsigned __int16 v29; // cx
  unsigned __int16 v30; // cx
  unsigned int v31; // ebx
  __int64 v32; // r15
  unsigned int v33; // eax
  unsigned int v34; // edi
  unsigned __int16 v35; // cx
  int v36; // eax
  unsigned __int16 v37; // cx
  int v38; // eax
  unsigned __int16 v39; // cx
  int v40; // r15d
  const struct SSItem *v41; // rbx
  const struct SSItem *v42; // rax
  unsigned int v43; // eax
  unsigned __int16 v44; // cx
  unsigned int v45; // edi
  int v46; // edx
  unsigned int v47; // ebx
  unsigned int v48; // r8d
  int v49; // r9d
  unsigned __int16 v50; // r15
  unsigned int v51; // eax
  int v52; // edi
  int IsCharSpaceW; // eax
  unsigned __int16 v54; // cx
  unsigned __int16 v55; // cx
  int v56; // ecx
  unsigned __int16 v57; // cx
  unsigned __int16 v58; // cx
  unsigned __int16 v59; // cx
  unsigned __int16 v60; // cx
  __int64 v61; // rcx
  int v62; // edi
  int v63; // r12d
  int v64; // r10d
  __int64 v65; // rbx
  CLexer *v66; // rcx
  unsigned __int16 v67; // r15
  __int64 v68; // rcx
  __int64 v69; // rdx
  CLexer *v70; // rcx
  unsigned __int16 v71; // cx
  const struct SSItem *v72; // rbx
  const struct SSItem *v73; // rax
  unsigned int v74; // eax
  int v75; // eax
  int v76; // r10d
  unsigned int v77; // ebx
  unsigned int v78; // r9d
  __int64 v79; // r8
  __int64 v80; // rbx
  unsigned int v81; // edi
  const unsigned __int16 *v82; // rbx
  const struct SSItem *v83; // rax
  unsigned int v84; // edx
  __int64 v85; // r9
  __int64 i; // r8
  __int64 v87; // rdx
  int v88; // r8d
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // r8
  int IsCharDigitW; // eax
  int v94; // ecx
  int v95; // eax
  __int64 v96; // rdx
  unsigned __int16 v97; // cx
  __int64 v98; // r8
  unsigned int v99; // ebx
  int v100; // eax
  CLexer *v101; // rcx
  __int64 v102; // rdi
  CLexer *v103; // rcx
  __int64 v104; // r9
  int v105; // r10d
  unsigned __int16 v106; // cx
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // rcx
  const struct SSItem *v111; // rax
  unsigned int v112; // eax
  const struct SSItem *v113; // rax
  unsigned __int16 v114; // cx
  char v115; // r8
  int v116; // r9d
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // r8
  int v120; // r9d
  int v121; // r10d
  __int64 v122; // rdx
  __int64 v123; // r8
  bool v124; // zf
  __int64 v125; // rdx
  __int64 v126; // r8
  int v127; // r8d
  unsigned int v128; // r9d
  unsigned int v129; // eax
  unsigned int v130; // edi
  const unsigned __int16 *v131; // rbx
  const struct SSItem *v132; // rax
  unsigned __int16 v133; // cx
  int v134; // eax
  int v135; // r8d
  unsigned __int16 v136; // cx
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  int IsCharAlphaW; // eax
  __int64 v141; // r8
  __int64 v142; // r9
  __int64 v143; // rdx
  __int64 v144; // rax
  unsigned int v145; // r11d
  int v146; // ebx
  const struct SSItem *v147; // rbx
  const struct SSItem *v148; // rax
  unsigned int v149; // edi
  unsigned int v150; // eax
  BOOL v151; // r8d
  char v152; // cl
  unsigned __int16 v153; // cx
  int v154; // eax
  __int64 v155; // r8
  unsigned int v156; // edx
  __int64 v157; // r9
  int v159; // [rsp+20h] [rbp-78h]
  int v160; // [rsp+28h] [rbp-70h]
  unsigned int v161; // [rsp+30h] [rbp-68h]
  unsigned int v162; // [rsp+34h] [rbp-64h]
  unsigned int v163; // [rsp+38h] [rbp-60h]
  char v164; // [rsp+3Ch] [rbp-5Ch]
  char v165; // [rsp+3Dh] [rbp-5Bh]
  int v166; // [rsp+40h] [rbp-58h]
  unsigned int v167; // [rsp+44h] [rbp-54h]
  unsigned int v168; // [rsp+48h] [rbp-50h]
  unsigned int v169; // [rsp+4Ch] [rbp-4Ch]
  unsigned int v170; // [rsp+50h] [rbp-48h]
  int v171; // [rsp+58h] [rbp-40h]
  unsigned int v172; // [rsp+A0h] [rbp+8h] BYREF
  int v173; // [rsp+B0h] [rbp+18h]
  bool v174; // [rsp+B8h] [rbp+20h] BYREF

  v173 = a3;
  v3 = *((unsigned int *)a1 + 3);
  v4 = *((_DWORD *)a1 + 2);
  v6 = (const unsigned __int16 *)*a1;
  v167 = 0;
  *((_DWORD *)a1 + 4) = v3;
  if ( (_DWORD)v3 == v4 )
  {
    v9 = 17;
    v159 = 0;
LABEL_3:
    v10 = v6;
    goto LABEL_411;
  }
  v11 = &v6[v3];
  v12 = *v11;
  if ( !(_WORD)v12 )
  {
    v9 = 15;
    v159 = 1;
    goto LABEL_3;
  }
  if ( (unsigned int)v3 >= 0x7D00 )
  {
    CToken::Set(a2, v6, 15, (unsigned int)v3, 0, 0);
    *(_DWORD *)(a2 + 24) = 1;
    goto LABEL_412;
  }
  v13 = v4 - v3;
  if ( (unsigned int)CLexer::FIsSurrogatePair((CLexer *)a1, v11, v13) )
  {
    CToken::Set(a2, v6, 3, (unsigned int)v3, 2, v14);
    *((_DWORD *)a1 + 4) += 2;
    goto LABEL_412;
  }
  if ( (unsigned int)FIsEop(v12) )
  {
    v16 = 1;
    CToken::Set(a2, v6, 16, (unsigned int)v3, 1, v15);
    if ( ++*((_DWORD *)a1 + 4) >= *((_DWORD *)a1 + 2) )
      goto LABEL_412;
    if ( (_WORD)v12 == 10 || (v18 = v17, (_WORD)v12 == 141) )
      v18 = 1;
    v19 = *((unsigned int *)a1 + 4);
    v20 = *a1;
    if ( *(_WORD *)(*a1 + 2 * v19) == 10 || (v21 = v17, *(_WORD *)(v20 + 2 * v19) == 141) )
      v21 = 1;
    if ( ((_WORD)v12 != 13 || !v21) && (!v18 || *(_WORD *)(v20 + 2 * v19) != 13) )
      goto LABEL_412;
    *(_DWORD *)(a2 + 16) = 2;
LABEL_403:
    *((_DWORD *)a1 + 4) += v16;
    goto LABEL_412;
  }
  v172 = v13;
  if ( (unsigned int)FIsSmiley(v6, v3, &v172) )
  {
    CToken::Set(a2, v6, 18, (unsigned int)v3, v172, 0);
LABEL_25:
    *((_DWORD *)a1 + 4) += v22;
    goto LABEL_412;
  }
  v16 = 1;
  if ( !(unsigned int)CMN_IsCharAlphaNumericW((unsigned __int16)v12)
    && !(unsigned int)CMN_IsCharSpaceW((unsigned __int16)v12)
    && !(unsigned int)FIsQuote(v12)
    && v13 > 1 )
  {
    if ( (a3 & 8) == 0
      || (v23 = v6[(unsigned int)(v3 - 1)], (_WORD)v23 != 95) && !(unsigned int)CMN_IsCharAlphaNumericW(v23) )
    {
      v24 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 80LL))(a1[16]);
      v25 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 88LL))(a1[16]);
      v3 = *((unsigned int *)a1 + 4);
      v26 = *a1;
      SubstringWithLookaheadBreak = FindSubstringWithLookaheadBreak(
                                      (const unsigned __int16 *)(*a1 + 2 * v3),
                                      *((_DWORD *)a1 + 2) - v3,
                                      1u,
                                      v25,
                                      v24);
      if ( SubstringWithLookaheadBreak )
      {
        CToken::Set(a2, v26, 3, (unsigned int)v3, SubstringWithLookaheadBreak, 65);
        goto LABEL_25;
      }
    }
  }
  if ( (_WORD)v12 == 8230 )
  {
    v28 = 8;
LABEL_37:
    v160 = 0;
LABEL_38:
    CToken::Set(a2, *a1, v28, (unsigned int)v3, v16, v160);
    goto LABEL_403;
  }
  if ( (unsigned int)FIsRegularExclamationOrQuestionMark(v12) )
  {
    v28 = 12;
    goto LABEL_37;
  }
  if ( (unsigned int)FIsFullStop(v29) )
  {
    v28 = 19;
    goto LABEL_37;
  }
  if ( (unsigned int)FIsGap(v30) )
  {
    v31 = v3 + 1;
    *((_DWORD *)a1 + 4) = v3 + 1;
    if ( (unsigned int)(v3 + 1) >= *((_DWORD *)a1 + 2) )
    {
      v34 = v3 + 1;
    }
    else
    {
      v32 = *a1;
      v33 = v3 + 1;
      do
      {
        v34 = v33;
        if ( !(unsigned int)FIsGap(*(_WORD *)(v32 + 2LL * v33)) )
          break;
        v33 = ++v31;
        *((_DWORD *)a1 + 4) = v31;
        v34 = v31;
      }
      while ( v31 < *((_DWORD *)a1 + 2) );
    }
    v159 = v34 - v3;
    v9 = 1;
    goto LABEL_410;
  }
  if ( (unsigned __int16)(v12 + 6144) <= 1u )
  {
    v156 = v3 + 1;
    *((_DWORD *)a1 + 4) = v3 + 1;
    if ( (unsigned int)(v3 + 1) < *((_DWORD *)a1 + 2) )
    {
      v157 = *a1;
      do
      {
        if ( (unsigned __int16)(*(_WORD *)(v157 + 2LL * v156) + 6144) > 1u )
          break;
        *((_DWORD *)a1 + 4) = ++v156;
      }
      while ( v156 < *((_DWORD *)a1 + 2) );
    }
    v159 = v156 - v3;
    v9 = 2;
    goto LABEL_410;
  }
  if ( *((_DWORD *)a1 + 34) )
  {
    if ( (unsigned int)FIsGroupBegin(v12) )
    {
      v36 = FIsQuote(v35);
      v28 = 10;
      v160 = v36 != 0 ? 32 : 16;
      goto LABEL_38;
    }
    if ( (unsigned int)FIsGroupEnd(v35) )
    {
      v38 = FIsQuote(v37);
      v28 = 11;
      v160 = v38 != 0 ? 32 : 16;
      goto LABEL_38;
    }
  }
  if ( (unsigned int)FIsApostrophe(v12) )
  {
    v40 = 4;
    if ( !a3 )
    {
      v41 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 80LL))(a1[16]);
      v42 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 88LL))(a1[16]);
      v3 = *((unsigned int *)a1 + 4);
      v43 = FindSubstringWithLookaheadBreak(
              (const unsigned __int16 *)(*a1 + 2 * v3),
              *((_DWORD *)a1 + 2) - v3,
              1u,
              v42,
              v41);
      if ( v43 )
      {
        v40 = 69;
        v16 = v43;
      }
    }
    v160 = v40;
    v28 = (unsigned int)FIsQuote(v12) != 0 ? 13 : 31;
    goto LABEL_38;
  }
  if ( (unsigned int)FIsQuote(v39) || (((_WORD)v12 - 171) & 0xFFEF) == 0 )
  {
    v28 = 13;
    goto LABEL_37;
  }
  if ( !(unsigned int)FIsPeriod(v12) )
  {
    if ( (unsigned int)FIsMiscPunctuation(v44) )
    {
      v28 = 14;
      goto LABEL_37;
    }
    if ( (unsigned int)FIsSymbol(v54) )
    {
      v56 = 128;
      if ( (_WORD)v12 != 167 )
        v56 = 0;
      v28 = 27;
      v160 = v56;
      goto LABEL_38;
    }
    if ( (unsigned int)FIsMathSymbol(v55) )
    {
      v28 = 29;
      goto LABEL_37;
    }
    if ( (unsigned int)FIsBulletSymbol(v57) )
    {
      v28 = 28;
      goto LABEL_37;
    }
    if ( (unsigned int)FIsCurrencySymbol(v58) )
    {
      v28 = 30;
      goto LABEL_37;
    }
    if ( (unsigned int)FIsBreakingHyphen(v59) )
    {
      v28 = 32;
      goto LABEL_37;
    }
    if ( (unsigned int)FIsBeginPunctuation(v60) )
    {
      v28 = 26;
      goto LABEL_37;
    }
    if ( !(unsigned int)CMN_IsCharAlphaNumericW(v61) )
    {
      if ( (unsigned int)FIsRegularExclamationOrQuestionMark(v12)
        || (v154 = FIsFullStop(v153)) != 0
        || v12 == 8228
        || v12 == 8229
        || v12 == 8253
        || v12 == 65294 )
      {
        v154 = 1;
      }
      v155 = 12;
      if ( !v154 )
        v155 = 15;
      CToken::Set(a2, *a1, v155, (unsigned int)v3, 1, 0);
      goto LABEL_403;
    }
    v62 = 0;
    v63 = 0;
    v162 = v3;
    v169 = 0;
    v174 = 0;
    if ( (v173 & 2) != 0
      || (LOBYTE(v161) = 1, !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 96LL))(a1[16])) )
    {
      LOBYTE(v161) = 0;
    }
    v163 = v3;
    v170 = v3;
    v166 = 0;
    v64 = -1;
    v171 = 0;
    LOBYTE(v172) = 0;
    v164 = 0;
    v165 = 0;
    v168 = 5;
    while ( 1 )
    {
      if ( v62 < 0 )
        goto LABEL_353;
      v65 = *((unsigned int *)a1 + 4);
      v66 = (CLexer *)(2 * v65);
      if ( (unsigned int)v65 < *((_DWORD *)a1 + 2) )
        v67 = *(_WORD *)((char *)v66 + *a1);
      else
        v67 = 0;
      if ( (unsigned int)CLexer::FIsSurrogatePair(
                           v66,
                           (const unsigned __int16 *)((char *)v66 + *a1),
                           *((_DWORD *)a1 + 2) - (int)v65)
        || (unsigned int)FIsFullStop(v67) )
      {
        goto LABEL_352;
      }
      if ( (unsigned int)CMN_IsCharAlphaNumericW(v68)
        || v67 == 95
        || !(unsigned int)FIsBreakingCharacter(v67)
        && v67 != 45
        && !(unsigned int)FIsApostrophe((unsigned __int16)v70)
        && !(unsigned int)FIsPeriod((unsigned __int16)v70)
        && v67 != 33 )
      {
        break;
      }
      if ( !v164
        && (unsigned int)v65 < *((_DWORD *)a1 + 2)
        && ((unsigned int)FIsApostrophe(v67) || !(unsigned int)FIsQuote(v71)) )
      {
        v164 = 1;
        v72 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 80LL))(a1[16]);
        v73 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 88LL))(a1[16]);
        v74 = FindSubstringWithLookaheadBreak(
                (const unsigned __int16 *)(*a1 + 2LL * v162),
                *((_DWORD *)a1 + 2) - v162,
                *((_DWORD *)a1 + 4) - v162 + 1,
                v73,
                v72);
        if ( v74 )
        {
          v63 |= 0x41u;
          *((_DWORD *)a1 + 4) = v162 + v74;
LABEL_351:
          v64 = -1;
LABEL_352:
          v62 = v64;
LABEL_353:
          v141 = *((unsigned int *)a1 + 4);
          v142 = *a1;
          if ( (unsigned int)v3 < v162 )
            v62 = v64;
          if ( *(_WORD *)(v142 + 2LL * (unsigned int)(v141 - 1)) == 95 )
          {
            do
            {
              v143 = (unsigned int)(v141 - 1);
              v144 = (unsigned int)(v141 - 2);
              *((_DWORD *)a1 + 4) = v143;
              v141 = v143;
            }
            while ( *(_WORD *)(v142 + 2 * v144) == 95 );
          }
          else
          {
            v143 = (unsigned int)v141;
          }
          switch ( v62 )
          {
            case -6:
              v167 = 1;
              v168 = 4;
              break;
            case -5:
              v168 = 6;
              break;
            case -3:
              v168 = 7;
              break;
            default:
              if ( v62 != -2 )
              {
                if ( v62 == v64 )
                {
                  v145 = v163;
                  v146 = v173;
                  v168 = 3;
                  if ( v163 <= (unsigned int)v3 || v163 >= (unsigned int)v143 )
                  {
                    v151 = 0;
                    v149 = v143;
                  }
                  else if ( v173 )
                  {
                    v149 = v163;
                    v63 = v166;
                    v151 = 0;
                    *((_DWORD *)a1 + 4) = v163;
                    if ( v171 )
                      v168 = v171;
                  }
                  else
                  {
                    if ( (v63 & 0x40) != 0 )
                    {
                      v150 = 0;
                      v149 = v143;
                    }
                    else
                    {
                      v147 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[16] + 80LL))(
                                                      a1[16],
                                                      v143,
                                                      v141);
                      v148 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 88LL))(a1[16]);
                      v149 = *((_DWORD *)a1 + 4);
                      v150 = FindSubstringWithLookaheadBreak(
                               (const unsigned __int16 *)(*a1 + 2 * v3),
                               v149 - v3,
                               v149 - v3,
                               v148,
                               v147);
                      v145 = v163;
                      v146 = v173;
                      if ( v150 )
                        v63 |= 0x40u;
                    }
                    v151 = v150 == 0;
                    v167 = v151;
                  }
                  if ( (v63 & 4) == 0 )
                    goto LABEL_391;
                  v152 = v161;
                  LODWORD(v143) = v170;
                  if ( v151 && v170 < v145 )
                    v152 = v172;
                  if ( v152 )
                    goto LABEL_391;
                  if ( !v146 )
                  {
                    v167 = v151 | 2;
                    goto LABEL_391;
                  }
                  if ( v170 >= v149 )
                    LODWORD(v143) = v149;
                  else
                    *((_DWORD *)a1 + 4) = v170;
                  v63 = 1;
                }
                else
                {
                  v168 = 0;
                }
              }
              break;
          }
          v149 = v143;
LABEL_391:
          CToken::Set(a2, *a1, v168, (unsigned int)v3, v149 - v3, v63);
          if ( v165 )
            *(_DWORD *)(a2 + 24) = 1;
          goto LABEL_412;
        }
      }
      if ( v67 == 45 || (unsigned int)FIsApostrophe(v67) )
        break;
      v75 = FIsPeriod((unsigned __int16)v70);
      v76 = v173;
      if ( v75 )
        goto LABEL_147;
      if ( v173 )
        goto LABEL_351;
      v77 = v163;
      v78 = v162;
      v79 = v161;
      if ( v163 == v162 )
      {
        v77 = *((_DWORD *)a1 + 4);
        v163 = v77;
        v166 = v63;
        LOBYTE(v172) = v161;
      }
LABEL_148:
      if ( v62 > 60 )
      {
        switch ( v62 )
        {
          case '=':
            if ( !(unsigned int)CMN_IsCharDigitW(v67, v69, v79) )
            {
              v134 = FIsPeriod(v67);
              v135 = *((_DWORD *)a1 + 4);
              if ( v134 && (unsigned int)FIsPeriod(*(_WORD *)(*a1 + 2LL * (unsigned int)(v135 - 1))) )
              {
                v100 = v135 + 1;
              }
              else
              {
                v100 = v135 - 1;
                v62 = 66;
              }
              goto LABEL_337;
            }
LABEL_332:
            ++*((_DWORD *)a1 + 4);
            v62 = 60;
            goto LABEL_338;
          case 'B':
            if ( (unsigned int)CMN_IsCharAlphaW(v67, v69, v79) || v67 == 95 )
              goto LABEL_278;
            if ( !(unsigned int)FIsApostrophe(v67) )
            {
              if ( !(unsigned int)FIsPeriod(v133) )
                goto LABEL_274;
              ++*((_DWORD *)a1 + 4);
              v62 = -6;
              goto LABEL_338;
            }
LABEL_190:
            if ( !v173 )
            {
              if ( v77 == v162 )
              {
                v163 = *((_DWORD *)a1 + 4);
                LOBYTE(v172) = v161;
                v166 = v63;
              }
              goto LABEL_193;
            }
            goto LABEL_311;
          case 'F':
            v62 = 71;
            v100 = *((_DWORD *)a1 + 4) + 1;
            v169 = v100;
            goto LABEL_337;
        }
        if ( v62 != 71 )
        {
          if ( v62 != 80 )
            goto LABEL_338;
          if ( (_BYTE)v79 )
          {
            if ( (unsigned int)FIsApostrophe(*(_WORD *)(*a1 + 2LL * (unsigned int)(*((_DWORD *)a1 + 4) - 1))) )
            {
              *((_DWORD *)a1 + 4) = v127;
              if ( v170 == v127 )
              {
                v63 &= ~4u;
                v170 = v128;
              }
            }
          }
          goto LABEL_311;
        }
        if ( (unsigned int)CMN_IsCharAlphaW(v67, v69, v79) )
        {
          if ( *((_DWORD *)a1 + 29) || !(unsigned int)CMN_IsCharUpperW(v67) )
          {
            if ( !*((_DWORD *)a1 + 30) && (unsigned int)CMN_IsCharLowerW(v67) )
              *((_DWORD *)a1 + 30) = 1;
          }
          else
          {
            *((_DWORD *)a1 + 29) = 1;
          }
          goto LABEL_293;
        }
        if ( v67 == 41 )
        {
          v129 = v169;
          v130 = *((_DWORD *)a1 + 4);
          if ( v130 > v169 )
          {
            v131 = (const unsigned __int16 *)(*a1 + 2LL * v169);
            v132 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 80LL))(a1[16]);
            if ( (int)FindString(v131, v130 - v169, v132) >= 0 )
            {
              ++*((_DWORD *)a1 + 4);
              goto LABEL_311;
            }
            goto LABEL_323;
          }
        }
        else
        {
LABEL_323:
          v129 = v169;
        }
        v100 = v129 - 1;
        v62 = -1;
        goto LABEL_337;
      }
      switch ( v62 )
      {
        case 60:
          if ( !(unsigned int)CMN_IsCharDigitW(v67, v69, v79) )
          {
            if ( (unsigned int)FIsPeriod(v67) )
            {
              if ( v173 )
                goto LABEL_311;
            }
            else if ( (unsigned __int16)(v67 - 44) > 1u && v67 != 58 )
            {
              v62 = 66;
              goto LABEL_338;
            }
            if ( v77 == v162 )
            {
              v163 = *((_DWORD *)a1 + 4);
              LOBYTE(v172) = v161;
              v166 = v63;
            }
            ++*((_DWORD *)a1 + 4);
            v62 = 61;
            goto LABEL_338;
          }
LABEL_293:
          ++*((_DWORD *)a1 + 4);
          goto LABEL_338;
        case 0:
          if ( !(unsigned int)CMN_IsCharDigitW(v67, v69, v79) )
          {
            if ( (unsigned int)CMN_IsCharAlphaW(v67, v125, v126) )
            {
              v63 |= 1u;
              if ( !*((_DWORD *)a1 + 29) && (unsigned int)CMN_IsCharUpperW(v67) )
                goto LABEL_286;
              v124 = *((_DWORD *)a1 + 30) == 0;
LABEL_288:
              if ( v124 && (unsigned int)CMN_IsCharLowerW(v67) )
                *((_DWORD *)a1 + 30) = 1;
            }
LABEL_291:
            ++*((_DWORD *)a1 + 4);
            v62 = 10;
            goto LABEL_338;
          }
          v63 |= 2u;
          goto LABEL_332;
        case 10:
          if ( (unsigned int)FIsPeriod(v67) )
          {
            if ( v77 == v116 )
            {
              v163 = *((_DWORD *)a1 + 4);
              v166 = v63;
              LOBYTE(v172) = v115;
            }
            goto LABEL_214;
          }
          if ( !(unsigned int)FIsApostrophe(v114) )
          {
            if ( (unsigned int)CMN_IsCharDigitW(v118, v117, v119) )
            {
              v63 |= 2u;
              goto LABEL_291;
            }
            if ( v67 == 173 )
              goto LABEL_277;
            if ( (unsigned int)CMN_IsCharAlphaNumericW(v67) )
            {
              if ( v67 != 0xE800 )
              {
                if ( v67 == 0xE801 )
                  goto LABEL_272;
LABEL_277:
                if ( (unsigned int)CMN_IsCharAlphaW(v67, v122, v123) )
                {
LABEL_278:
                  v63 |= 1u;
                  if ( *((_DWORD *)a1 + 29) || !(unsigned int)CMN_IsCharUpperW(v67) )
                  {
                    v124 = *((_DWORD *)a1 + 30) == 0;
                    goto LABEL_288;
                  }
LABEL_286:
                  *((_DWORD *)a1 + 29) = 1;
                }
                goto LABEL_291;
              }
            }
            else
            {
LABEL_272:
              if ( v67 == 95 || (unsigned __int16)(v67 - 8208) <= 1u )
                goto LABEL_277;
            }
LABEL_274:
            v62 = -1;
            if ( v67 == 40 )
              v62 = 70;
            goto LABEL_338;
          }
          if ( (_BYTE)v161 )
          {
            v63 |= 4u;
            v62 = 40;
            v170 = *((_DWORD *)a1 + 4);
            *((_DWORD *)a1 + 4) = v170 + 1;
LABEL_341:
            if ( !(unsigned int)FIsApostrophe(v67) && !(unsigned int)FIsPeriod(v136) )
            {
              IsCharAlphaW = CMN_IsCharAlphaW(v138, v137, v139);
              if ( IsCharAlphaW || (IsCharAlphaW = 95, v67 == 95) )
              {
                LOBYTE(IsCharAlphaW) = 1;
                v161 = IsCharAlphaW;
              }
              else
              {
                LOBYTE(v161) = 0;
              }
            }
LABEL_347:
            v64 = -1;
            break;
          }
          if ( v121 )
            goto LABEL_197;
          if ( v77 == v120 )
          {
            v163 = *((_DWORD *)a1 + 4);
            v166 = v63;
            LOBYTE(v172) = 0;
          }
          v63 |= 4u;
          v170 = *((_DWORD *)a1 + 4);
          *((_DWORD *)a1 + 4) = v170 + 1;
          v64 = -1;
          v62 = 40;
          break;
        case 20:
          if ( (unsigned int)CMN_IsCharAlphaNumericW(v67) )
          {
            if ( (unsigned __int16)(v67 + 6144) > 1u )
              goto LABEL_231;
          }
          else if ( v67 == 45 )
          {
            if ( (v173 & 4) == 0
              && CLexer::FIsAbbreviation(
                   (CLexer *)a1,
                   (const unsigned __int16 *)(*a1 + 2LL * v162),
                   *((_DWORD *)a1 + 4) - v162,
                   &v174) )
            {
              if ( v174 )
                v63 |= 8u;
              v163 = *((_DWORD *)a1 + 4);
              v171 = 5;
              v166 = v63;
            }
            goto LABEL_237;
          }
          if ( (unsigned int)FIsApostrophe(v67) )
          {
            if ( v173 )
              goto LABEL_311;
            if ( v77 == v162 )
            {
              v163 = *((_DWORD *)a1 + 4);
              LOBYTE(v172) = v161;
              v166 = v63;
            }
            v63 |= 4u;
            v170 = *((_DWORD *)a1 + 4);
            v100 = v170 + 1;
LABEL_199:
            v62 = 40;
          }
          else
          {
            if ( !(unsigned int)CMN_IsCharSpaceW(v110)
              || (v63 & 4) != 0
              || (v173 & 2) != 0
              || (v111 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 32LL))(a1[16]),
                  (v112 = FindSubstringWithLookaheadBreak(
                            (const unsigned __int16 *)(*a1 + 2LL * v162),
                            *((_DWORD *)a1 + 2) - v162,
                            *((_DWORD *)a1 + 4) - v162 + 1,
                            v111,
                            0)) == 0)
              && (v113 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 64LL))(a1[16]),
                  (v112 = FindSubstringWithLookaheadBreak(
                            (const unsigned __int16 *)(*a1 + 2LL * v162),
                            *((_DWORD *)a1 + 2) - v162,
                            *((_DWORD *)a1 + 4) - v162 + 1,
                            v113,
                            0)) == 0) )
            {
LABEL_209:
              v62 = 50;
              goto LABEL_338;
            }
            v100 = v162 + v112;
            v62 = -2;
          }
LABEL_337:
          *((_DWORD *)a1 + 4) = v100;
          goto LABEL_338;
        case 30:
          if ( (unsigned int)FIsPeriod(v67) )
          {
LABEL_214:
            ++*((_DWORD *)a1 + 4);
            v62 = 20;
            goto LABEL_338;
          }
          if ( (unsigned int)FIsApostrophe(v106) )
          {
            if ( (v63 & 4) != 0 )
            {
              v170 = *((_DWORD *)a1 + 4);
              v100 = v170 + 1;
              goto LABEL_199;
            }
LABEL_311:
            v62 = -1;
            goto LABEL_338;
          }
          if ( (unsigned int)CMN_IsCharDigitW(v108, v107, v109) )
          {
            v63 |= 2u;
            goto LABEL_237;
          }
          if ( v67 != 173 )
          {
            if ( !(unsigned int)CMN_IsCharAlphaNumericW(v67) )
              goto LABEL_224;
            if ( v67 == 0xE800 )
              goto LABEL_311;
            if ( v67 == 0xE801 )
            {
LABEL_224:
              if ( v67 != 95 )
              {
                if ( v67 != 45 )
                {
                  if ( v67 == 40 )
                  {
LABEL_211:
                    v62 = 70;
                    goto LABEL_338;
                  }
                  goto LABEL_311;
                }
                if ( v173 )
                  goto LABEL_311;
                if ( v77 == v162 )
                {
                  v163 = *((_DWORD *)a1 + 4);
                  LOBYTE(v172) = v161;
                  v166 = v63;
                }
LABEL_237:
                ++*((_DWORD *)a1 + 4);
                v62 = 30;
                goto LABEL_338;
              }
            }
          }
LABEL_231:
          if ( *((_DWORD *)a1 + 29) || !(unsigned int)CMN_IsCharUpperW(v67) )
          {
            if ( !*((_DWORD *)a1 + 30) && (unsigned int)CMN_IsCharLowerW(v67) )
              *((_DWORD *)a1 + 30) = 1;
          }
          else
          {
            *((_DWORD *)a1 + 29) = 1;
          }
          goto LABEL_237;
        case 40:
          if ( (unsigned int)CLexer::FIsValidPostAposChar(v70, v67) )
          {
            if ( (unsigned int)CMN_IsCharAlphaW(v67, v89, v90) )
            {
              v63 |= 1u;
              if ( *((_DWORD *)a1 + 29) || !(unsigned int)CMN_IsCharUpperW(v67) )
              {
                if ( !*((_DWORD *)a1 + 30) && (unsigned int)CMN_IsCharLowerW(v67) )
                  *((_DWORD *)a1 + 30) = 1;
              }
              else
              {
                *((_DWORD *)a1 + 29) = 1;
              }
            }
            IsCharDigitW = CMN_IsCharDigitW(v67, v91, v92);
            v94 = v63 | 2;
            if ( !IsCharDigitW )
              v94 = v63;
            v63 = v94;
LABEL_193:
            ++*((_DWORD *)a1 + 4);
            v62 = 40;
            goto LABEL_338;
          }
          if ( v67 == 45 )
            goto LABEL_190;
          v95 = FIsApostrophe(v67);
          v99 = *((_DWORD *)a1 + 4);
          if ( v95 )
          {
            if ( (unsigned int)CMN_IsCharAlphaW(*(unsigned __int16 *)(*a1 + 2LL * (v99 - 1)), v96, v98) )
            {
              v100 = v99 + 1;
              goto LABEL_199;
            }
            LOBYTE(v161) = 0;
LABEL_197:
            v64 = -1;
            v62 = -1;
            break;
          }
          if ( (unsigned int)FIsPeriod(v97) )
          {
            if ( v99 < *((_DWORD *)a1 + 2) )
            {
              v102 = *a1;
              if ( (unsigned int)CLexer::FIsValidPostAposChar(v101, *(_WORD *)(*a1 + 2LL * (v99 - 1))) )
              {
                if ( (unsigned int)CLexer::FIsValidPostAposChar(v103, *(_WORD *)(v102 + 2LL * (v99 + 1))) )
                {
                  v62 = 10;
                  LOBYTE(v161) = 0;
                  v162 = v170 + 1;
                  *((_DWORD *)a1 + 4) = v170 + 1;
                  goto LABEL_347;
                }
              }
            }
            v62 = (_BYTE)v161 != 0 ? 80 : -1;
            goto LABEL_338;
          }
          if ( (unsigned int)FIsRightSingleQuote(*(_WORD *)(*a1 + 2LL * (v99 - 1)))
            && (unsigned int)FIsPeriod(*(_WORD *)(v104 + 2LL * (v99 - 2))) )
          {
            *((_DWORD *)a1 + 4) = v105;
            goto LABEL_209;
          }
          if ( v67 == 40 )
            goto LABEL_211;
          v64 = -1;
          v62 = (_BYTE)v161 != 0 ? 80 : -1;
          break;
        case 50:
          if ( (v76 & 4) == 0 )
          {
            v80 = v78;
            if ( CLexer::FIsTitle(
                   (CLexer *)a1,
                   (const unsigned __int16 *)(*a1 + 2LL * v78),
                   *((_DWORD *)a1 + 4) - v78,
                   0) )
            {
              goto LABEL_158;
            }
            if ( CLexer::FIsAbbreviation(
                   (CLexer *)a1,
                   (const unsigned __int16 *)(*a1 + 2 * v80),
                   *((_DWORD *)a1 + 4) - v162,
                   &v174) )
            {
              v62 = -2;
              if ( v174 )
                v63 |= 8u;
              goto LABEL_338;
            }
            if ( CLexer::FIsTitle(
                   (CLexer *)a1,
                   (const unsigned __int16 *)(*a1 + 2 * v80),
                   *((_DWORD *)a1 + 4) - v162,
                   1) )
            {
LABEL_158:
              v62 = -3;
              goto LABEL_338;
            }
            v81 = *((_DWORD *)a1 + 4) - v162;
            v82 = (const unsigned __int16 *)(*a1 + 2 * v80);
            v83 = (const struct SSItem *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1[16] + 40LL))(a1[16]);
            if ( (int)FindString(v82, v81, v83) >= 0 )
            {
              v62 = -5;
              goto LABEL_338;
            }
            v76 = v173;
          }
          v62 = -1;
          if ( v76 || v163 <= v162 )
            goto LABEL_177;
          if ( (unsigned int)FIsBreakingHyphen(*(_WORD *)(*a1 + 2LL * v163)) )
          {
            LODWORD(i) = v84;
          }
          else
          {
            for ( i = (unsigned int)(*((_DWORD *)a1 + 4) - 1);
                  (unsigned int)i > v84 && !(unsigned int)FIsBreakingHyphen(*(_WORD *)(v85 + 2 * i));
                  i = (unsigned int)(i - 1) )
            {
              ;
            }
          }
          if ( !(unsigned int)FIsBreakingHyphen(*(_WORD *)(v85 + 2LL * (unsigned int)i))
            || !CLexer::FIsAbbreviation(
                  (CLexer *)a1,
                  (const unsigned __int16 *)(*a1 + 2LL + 2 * v87),
                  *((_DWORD *)a1 + 4) + ~v88,
                  0) )
          {
LABEL_177:
            --*((_DWORD *)a1 + 4);
          }
LABEL_338:
          if ( (_BYTE)v161 && ((unsigned int)v62 <= 0x4F || v62 >= 90) )
            goto LABEL_341;
          goto LABEL_347;
        default:
          goto LABEL_338;
      }
      if ( *((_DWORD *)a1 + 4) >= 0x7D00u )
      {
        v165 = 1;
        v62 = -1;
      }
    }
    v76 = v173;
LABEL_147:
    v77 = v163;
    v79 = v161;
    v78 = v162;
    goto LABEL_148;
  }
  v45 = v3 + 1;
  v46 = 1;
  *((_DWORD *)a1 + 4) = v3 + 1;
  v47 = v3 + 1;
  while ( 2 )
  {
    v48 = 3;
    while ( 2 )
    {
      v49 = 4;
      while ( 1 )
      {
        v50 = v47 < *((_DWORD *)a1 + 2) ? *(_WORD *)(*a1 + 2LL * v47) : 0;
        if ( v46 == 1 )
          break;
        switch ( v46 )
        {
          case 2:
            if ( v47 - (unsigned int)v3 < v48 )
            {
              if ( (unsigned int)FIsPeriod(v50) )
                goto LABEL_94;
            }
            else
            {
              v45 = v47;
            }
LABEL_90:
            v46 = -1;
            break;
          case 3:
            if ( (unsigned int)FIsPeriod(v50) )
            {
              v46 = v49;
LABEL_94:
              *((_DWORD *)a1 + 4) = ++v47;
              break;
            }
            goto LABEL_90;
          case 4:
            v51 = (v47 - (unsigned int)v3) >> 1;
            if ( v51 == 2 || v51 == v49 )
            {
              v45 = v47;
            }
            else if ( v51 == 6 )
            {
              v45 = v47;
              goto LABEL_79;
            }
            IsCharSpaceW = CMN_IsCharSpaceW(v50);
            v48 = 3;
            if ( IsCharSpaceW )
            {
              ++v47;
              v46 = 3;
              *((_DWORD *)a1 + 4) = v47;
            }
            else
            {
              v46 = -1;
            }
            v49 = 4;
            break;
        }
        if ( v46 <= 0 )
          goto LABEL_79;
      }
      if ( (unsigned int)CMN_IsCharSpaceW(v50) )
      {
        ++v47;
        v48 = 3;
        *((_DWORD *)a1 + 4) = v47;
        v46 = 3;
        continue;
      }
      break;
    }
    if ( (unsigned int)FIsPeriod(v50) )
    {
      ++v47;
      v46 = 2;
      *((_DWORD *)a1 + 4) = v47;
      continue;
    }
    break;
  }
LABEL_79:
  *((_DWORD *)a1 + 4) = v45;
  v52 = v45 - v3;
  if ( v52 == 1 )
    v9 = 12;
  else
    v9 = (unsigned int)(v52 != 3) + 8;
  v159 = v52;
LABEL_410:
  v10 = (const unsigned __int16 *)*a1;
LABEL_411:
  CToken::Set(a2, v10, v9, (unsigned int)v3, v159, 0);
LABEL_412:
  CToken::operator=((__int64)(a1 + 3), a2);
  return v167;
}

```

## disassembly

```asm
0x1800277ac  mov     rax, rsp
0x1800277af  mov     [rax+10h], rbx
0x1800277b3  mov     [rax+18h], r8d
0x1800277b7  push    rbp
0x1800277b8  push    rsi
0x1800277b9  push    rdi
0x1800277ba  push    r12
0x1800277bc  push    r13
0x1800277be  push    r14
0x1800277c0  push    r15
0x1800277c2  sub     rsp, 60h
0x1800277c6  mov     r14d, [rcx+0Ch]
0x1800277ca  xor     r10d, r10d
0x1800277cd  mov     r15d, [rcx+8]
0x1800277d1  mov     r12d, r8d
0x1800277d4  mov     rbx, [rcx]
0x1800277d7  mov     r13, rdx
0x1800277da  mov     [rsp+98h+var_54], r10d
0x1800277df  mov     rsi, rcx
0x1800277e2  mov     [rcx+10h], r14d
0x1800277e6  cmp     r14d, r15d
0x1800277e9  jnz     short loc_1800277FF
0x1800277eb  mov     [rax-70h], r10d
0x1800277ef  lea     r8d, [r10+11h]
0x1800277f3  mov     [rax-78h], r10d
0x1800277f7  mov     rdx, rbx
0x1800277fa  jmp     loc_180028CC8
0x1800277ff  lea     rdx, [rbx+r14*2]; unsigned __int16 *
0x180027803  movzx   edi, word ptr [rdx]
0x180027806  cmp     r10w, di
0x18002780a  jnz     short loc_180027821
0x18002780c  mov     [rsp+98h+var_70], r10d
0x180027811  mov     r8d, 0Fh
0x180027817  mov     dword ptr [rsp+98h+var_78], 1
0x18002781f  jmp     short loc_1800277F7
0x180027821  cmp     r14d, 7D00h
0x180027828  jb      short loc_180027855
0x18002782a  mov     [rsp+98h+var_70], r10d
0x18002782f  mov     r9d, r14d
0x180027832  mov     r8d, 0Fh
0x180027838  mov     dword ptr [rsp+98h+var_78], r10d
0x18002783d  mov     rdx, rbx
0x180027840  mov     rcx, r13
0x180027843  call    ?Set@CToken@@QEAAAEAV1@PEBGW4eTokenTypes@@IIW4TokenTypeFlags@@@Z; CToken::Set(ushort const *,eTokenTypes,uint,uint,TokenTypeFlags)
0x180027848  mov     dword ptr [r13+18h], 1
0x180027850  jmp     loc_180028CD3
0x180027855  sub     r15d, r14d
0x180027858  mov     r8d, r15d; int
0x18002785b  call    ?FIsSurrogatePair@CLexer@@QEAAHPEBGH@Z; CLexer::FIsSurrogatePair(ushort const *,int)
0x180027860  test    eax, eax
0x180027862  jz      short loc_18002788E
0x180027864  mov     [rsp+98h+var_70], r10d
0x180027869  mov     r9d, r14d
0x18002786c  mov     r8d, 3
0x180027872  mov     dword ptr [rsp+98h+var_78], 2
0x18002787a  mov     rdx, rbx
0x18002787d  mov     rcx, r13
0x180027880  call    ?Set@CToken@@QEAAAEAV1@PEBGW4eTokenTypes@@IIW4TokenTypeFlags@@@Z; CToken::Set(ushort const *,eTokenTypes,uint,uint,TokenTypeFlags)
0x180027885  add     dword ptr [rsi+10h], 2
0x180027889  jmp     loc_180028CD3
0x18002788e  movzx   ecx, di; unsigned __int16
0x180027891  call    ?FIsEop@@YAHG@Z; FIsEop(ushort)
0x180027896  test    eax, eax
0x180027898  jz      loc_180027931
0x18002789e  mov     ebp, 1
0x1800278a3  mov     [rsp+98h+var_70], r10d
0x1800278a8  mov     r9d, r14d
0x1800278ab  mov     dword ptr [rsp+98h+var_78], ebp
0x1800278af  mov     rdx, rbx
0x1800278b2  mov     rcx, r13
0x1800278b5  lea     r8d, [rbp+0Fh]
0x1800278b9  call    ?Set@CToken@@QEAAAEAV1@PEBGW4eTokenTypes@@IIW4TokenTypeFlags@@@Z; CToken::Set(ushort const *,eTokenTypes,uint,uint,TokenTypeFlags)
0x1800278be  add     [rsi+10h], ebp
0x1800278c1  mov     eax, [rsi+10h]
0x1800278c4  cmp     eax, [rsi+8]
0x1800278c7  jnb     loc_180028CD3
0x1800278cd  lea     edx, [rbp+9]
0x1800278d0  mov     r8d, 8Dh
0x1800278d6  cmp     di, dx
0x1800278d9  jz      short loc_1800278E4
0x1800278db  mov     r9b, r10b
0x1800278de  cmp     di, r8w
0x1800278e2  jnz     short loc_1800278E7
0x1800278e4  mov     r9b, bpl
0x1800278e7  mov     rcx, rax
0x1800278ea  mov     rax, [rsi]
0x1800278ed  cmp     [rax+rcx*2], dx
0x1800278f1  jz      short loc_1800278FD
0x1800278f3  mov     dl, r10b
0x1800278f6  cmp     [rax+rcx*2], r8w
0x1800278fb  jnz     short loc_180027900
0x1800278fd  mov     dl, bpl
0x180027900  mov     r8d, 0Dh
0x180027906  cmp     di, r8w
0x18002790a  jnz     short loc_180027910
0x18002790c  test    dl, dl
0x18002790e  jnz     short loc_180027924
0x180027910  test    r9b, r9b
0x180027913  jz      loc_180028CD3
0x180027919  cmp     [rax+rcx*2], r8w
0x18002791e  jnz     loc_180028CD3
0x180027924  mov     dword ptr [r13+10h], 2
0x18002792c  jmp     loc_180028C6E
0x180027931  lea     r8, [rsp+98h+arg_0]; unsigned int *
0x180027939  mov     [rsp+98h+arg_0], r15d
0x180027941  mov     edx, r14d; unsigned int
0x180027944  mov     rcx, rbx; unsigned __int16 *
0x180027947  call    ?FIsSmiley@@YAHPEBGIPEAI@Z; FIsSmiley(ushort const *,uint,uint *)
0x18002794c  test    eax, eax
0x18002794e  jz      short loc_180027982
0x180027950  mov     r10d, [rsp+98h+arg_0]
0x180027958  mov     r8d, 12h
0x18002795e  mov     [rsp+98h+var_70], 0
0x180027966  mov     rdx, rbx
0x180027969  mov     r9d, r14d
0x18002796c  mov     dword ptr [rsp+98h+var_78], r10d
0x180027971  mov     rcx, r13
0x180027974  call    ?Set@CToken@@QEAAAEAV1@PEBGW4eTokenTypes@@IIW4TokenTypeFlags@@@Z; CToken::Set(ushort const *,eTokenTypes,uint,uint,TokenTypeFlags)
0x180027979  add     [rsi+10h], r10d
0x18002797d  jmp     loc_180028CD3
0x180027982  movzx   ecx, di
0x180027985  call    CMN_IsCharAlphaNumericW
0x18002798a  mov     ebp, 1
0x18002798f  test    eax, eax
0x180027991  jnz     loc_180027A46
0x180027997  movzx   ecx, di
0x18002799a  call    CMN_IsCharSpaceW
0x18002799f  test    eax, eax
0x1800279a1  jnz     loc_180027A46
0x1800279a7  movzx   ecx, di; unsigned __int16
0x1800279aa  call    ?FIsQuote@@YAHG@Z; FIsQuote(ushort)
0x1800279af  test    eax, eax
0x1800279b1  jnz     loc_180027A46
0x1800279b7  cmp     r15d, ebp
0x1800279ba  jbe     loc_180027A46
0x1800279c0  test    r12b, 8
0x1800279c4  jz      short loc_1800279DF
0x1800279c6  lea     eax, [r14-1]
0x1800279ca  movzx   ecx, word ptr [rbx+rax*2]
0x1800279ce  lea     eax, [rbp+5Eh]
0x1800279d1  cmp     ax, cx
0x1800279d4  jz      short loc_180027A46
0x1800279d6  call    CMN_IsCharAlphaNumericW
0x1800279db  test    eax, eax
0x1800279dd  jnz     short loc_180027A46
0x1800279df  mov     rcx, [rsi+80h]
0x1800279e6  mov     rax, [rcx]
0x1800279e9  mov     rax, [rax+50h]
0x1800279ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279f2  mov     rcx, [rsi+80h]
0x1800279f9  mov     rbx, rax
0x1800279fc  mov     rdx, [rcx]
0x1800279ff  mov     rax, [rdx+58h]
0x180027a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a08  mov     r14d, [rsi+10h]
0x180027a0c  mov     r9, rax; struct SSItem *
0x180027a0f  mov     edx, [rsi+8]
0x180027a12  mov     r8d, ebp; unsigned int
0x180027a15  mov     r15, [rsi]
0x180027a18  sub     edx, r14d; unsigned int
0x180027a1b  mov     [rsp+98h+var_78], rbx; struct SSItem *
0x180027a20  lea     rcx, [r15+r14*2]; unsigned __int16 *
0x180027a24  call    ?FindSubstringWithLookaheadBreak@@YAIPEBGIIPEBUSSItem@@1@Z; FindSubstringWithLookaheadBreak(ushort const *,uint,uint,SSItem const *,SSItem const *)
0x180027a29  mov     r10d, eax
0x180027a2c  test    eax, eax
0x180027a2e  jz      short loc_180027A46
0x180027a30  mov     [rsp+98h+var_70], 41h ; 'A'
0x180027a38  mov     r8d, 3
0x180027a3e  mov     rdx, r15
0x180027a41  jmp     loc_180027969
0x180027a46  mov     eax, 2026h
0x180027a4b  cmp     ax, di
0x180027a4e  jnz     short loc_180027A70
0x180027a50  mov     r8d, 8
0x180027a56  mov     [rsp+98h+var_70], 0
0x180027a5e  mov     rdx, [rsi]
0x180027a61  mov     r9d, r14d
0x180027a64  mov     dword ptr [rsp+98h+var_78], ebp
0x180027a68  mov     rcx, r13
0x180027a6b  jmp     loc_180028C69
0x180027a70  movzx   ecx, di; unsigned __int16
0x180027a73  call    ?FIsRegularExclamationOrQuestionMark@@YAHG@Z; FIsRegularExclamationOrQuestionMark(ushort)
0x180027a78  test    eax, eax
0x180027a7a  jz      short loc_180027A84
0x180027a7c  mov     r8d, 0Ch
0x180027a82  jmp     short loc_180027A56
0x180027a84  call    ?FIsFullStop@@YAHG@Z; FIsFullStop(ushort)
0x180027a89  test    eax, eax
0x180027a8b  jz      short loc_180027A95
0x180027a8d  mov     r8d, 13h
0x180027a93  jmp     short loc_180027A56
0x180027a95  call    ?FIsGap@@YAHG@Z; FIsGap(ushort)
0x180027a9a  test    eax, eax
0x180027a9c  jz      short loc_180027AEA
0x180027a9e  lea     ebx, [r14+1]
0x180027aa2  mov     [rsi+10h], ebx
0x180027aa5  cmp     ebx, [rsi+8]
0x180027aa8  jnb     short loc_180027AD1
0x180027aaa  mov     r15, [rsi]
0x180027aad  mov     eax, ebx
0x180027aaf  mov     ecx, eax
0x180027ab1  mov     edi, eax
0x180027ab3  movzx   ecx, word ptr [r15+rcx*2]; unsigned __int16
0x180027ab8  call    ?FIsGap@@YAHG@Z; FIsGap(ushort)
0x180027abd  test    eax, eax
0x180027abf  jz      short loc_180027AD3
0x180027ac1  inc     ebx
0x180027ac3  mov     eax, ebx
0x180027ac5  mov     [rsi+10h], ebx
0x180027ac8  mov     edi, ebx
0x180027aca  cmp     ebx, [rsi+8]
0x180027acd  jb      short loc_180027AAF
0x180027acf  jmp     short loc_180027AD3
0x180027ad1  mov     edi, ebx
0x180027ad3  sub     edi, r14d
0x180027ad6  mov     [rsp+98h+var_70], 0
0x180027ade  mov     dword ptr [rsp+98h+var_78], edi
0x180027ae2  mov     r8d, ebp
0x180027ae5  jmp     loc_180028CC5
0x180027aea  mov     ecx, 1800h
0x180027aef  lea     eax, [rcx+rdi]
0x180027af2  cmp     ax, bp
0x180027af5  jbe     loc_180028C7E
0x180027afb  cmp     dword ptr [rsi+88h], 0
0x180027b02  jz      short loc_180027B55
0x180027b04  movzx   ecx, di; unsigned __int16
0x180027b07  call    ?FIsGroupBegin@@YAHG@Z; FIsGroupBegin(ushort)
0x180027b0c  test    eax, eax
0x180027b0e  jz      short loc_180027B2E
0x180027b10  call    ?FIsQuote@@YAHG@Z; FIsQuote(ushort)
0x180027b15  neg     eax
0x180027b17  mov     r8d, 0Ah
0x180027b1d  sbb     ecx, ecx
0x180027b1f  and     ecx, 10h
0x180027b22  add     ecx, 10h
0x180027b25  mov     [rsp+98h+var_70], ecx
0x180027b29  jmp     loc_180027A5E
0x180027b2e  call    ?FIsGroupEnd@@YAHG@Z; FIsGroupEnd(ushort)
0x180027b33  test    eax, eax
0x180027b35  jz      short loc_180027B55
0x180027b37  call    ?FIsQuote@@YAHG@Z; FIsQuote(ushort)
0x180027b3c  neg     eax
0x180027b3e  mov     r8d, 0Bh
0x180027b44  sbb     ecx, ecx
0x180027b46  and     ecx, 10h
0x180027b49  add     ecx, 10h
0x180027b4c  mov     [rsp+98h+var_70], ecx
0x180027b50  jmp     loc_180027A5E
0x180027b55  movzx   ecx, di; unsigned __int16
0x180027b58  call    ?FIsApostrophe@@YAHG@Z; FIsApostrophe(ushort)
0x180027b5d  test    eax, eax
0x180027b5f  jz      short loc_180027BE0
0x180027b61  mov     r15d, 4
0x180027b67  test    r12d, r12d
0x180027b6a  jnz     short loc_180027BC1
0x180027b6c  mov     rcx, [rsi+80h]
0x180027b73  mov     rax, [rcx]
0x180027b76  mov     rax, [rax+50h]
0x180027b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b7f  mov     rcx, [rsi+80h]
0x180027b86  mov     rbx, rax
0x180027b89  mov     rdx, [rcx]
0x180027b8c  mov     rax, [rdx+58h]
0x180027b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b95  mov     r14d, [rsi+10h]
0x180027b99  mov     r9, rax; struct SSItem *
0x180027b9c  mov     edx, [rsi+8]
0x180027b9f  mov     r8d, ebp; unsigned int
0x180027ba2  mov     rcx, [rsi]
0x180027ba5  sub     edx, r14d; unsigned int
0x180027ba8  mov     [rsp+98h+var_78], rbx; struct SSItem *
0x180027bad  lea     rcx, [rcx+r14*2]; unsigned __int16 *
0x180027bb1  call    ?FindSubstringWithLookaheadBreak@@YAIPEBGIIPEBUSSItem@@1@Z; FindSubstringWithLookaheadBreak(ushort const *,uint,uint,SSItem const *,SSItem const *)
0x180027bb6  test    eax, eax
0x180027bb8  jz      short loc_180027BC1
0x180027bba  lea     r15d, [r12+45h]
0x180027bbf  mov     ebp, eax
0x180027bc1  movzx   ecx, di; unsigned __int16
0x180027bc4  call    ?FIsQuote@@YAHG@Z; FIsQuote(ushort)
0x180027bc9  neg     eax
0x180027bcb  mov     [rsp+98h+var_70], r15d
0x180027bd0  sbb     r8d, r8d
0x180027bd3  and     r8d, 0FFFFFFEEh
0x180027bd7  add     r8d, 1Fh
0x180027bdb  jmp     loc_180027A5E
0x180027be0  call    ?FIsQuote@@YAHG@Z; FIsQuote(ushort)
0x180027be5  test    eax, eax
0x180027be7  jnz     loc_180028C73
0x180027bed  mov     ecx, 0ABh
0x180027bf2  movzx   eax, di
0x180027bf5  sub     ax, cx
0x180027bf8  mov     ecx, 0FFEFh
0x180027bfd  test    cx, ax
0x180027c00  jz      loc_180028C73
0x180027c06  movzx   ecx, di; unsigned __int16
0x180027c09  call    ?FIsPeriod@@YAHG@Z; FIsPeriod(ushort)
0x180027c0e  test    eax, eax
0x180027c10  jz      loc_180027D54
0x180027c16  lea     edi, [r14+1]
0x180027c1a  mov     edx, ebp
  ... truncated ...
```

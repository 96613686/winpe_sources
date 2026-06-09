# T42CreateBaseFont

- ea: `0x18003d7e4`
- end: `0x18003edab`
- name: `T42CreateBaseFont`
- size: `5575`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180036b00`
- `0x18003eef0`

## callees

- `0x180001ee0`
- `0x1800055e0`
- `0x18003858c`
- `0x180038750`
- `0x180038968`
- `0x180038b18`
- `0x18003a950`
- `0x18003ad04`
- `0x18003aef4`
- `0x18003b10c`
- `0x18003b9a8`
- `0x18003bb84`
- `0x18003c0d8`
- `0x18003c1a4`
- `0x18003c260`
- `0x18003c348`
- `0x18003d7e4`
- `0x18003f258`
- `0x18004306c`
- `0x180043430`
- `0x18004350c`
- `0x1800454ac`
- `0x18005d010`

## string_xrefs

- `0x18003e50f`: `/%s /%s [/%s%s] composefont pop`
- `0x18003e614`: `/%s%s] composefont pop`
- `0x18003e4c4`: `/%s /%s [/%s] composefont pop`
- `0x18003e98f`: `/%s /%s [/%s%s /%s%s] composefont pop`
- `0x18003ea50`: `/%s /%s [/%s%s /%s%s] composefont pop`
- `0x18003ebc2`: `/%s%s /%s%s /%s%s] composefont pop`

## pseudocode

```c
__int64 __fastcall T42CreateBaseFont(__int64 a1, __int64 a2, __int64 a3, double a4, const char *a5)
{
  int *v6; // r14
  __int64 v8; // rdx
  unsigned __int16 MinSfnt; // bx
  __int64 v10; // rcx
  unsigned __int8 (__fastcall *v11)(__int64, __int64); // rax
  __int64 v12; // rsi
  __int64 v13; // r9
  char *v14; // r13
  int NumGlyphs; // eax
  __int64 v16; // rdx
  unsigned int TableSize; // eax
  unsigned int v18; // r15d
  unsigned int v19; // r12d
  int v20; // edx
  unsigned int v21; // ebx
  __int64 v22; // rax
  unsigned int v23; // r15d
  __int64 v24; // r12
  __int64 v25; // r9
  __int64 (__fastcall *v26)(_QWORD, _QWORD, _QWORD); // rax
  unsigned int v27; // eax
  unsigned int v28; // r13d
  __int64 v29; // rax
  __int64 v30; // r15
  unsigned int v31; // eax
  __int64 v32; // r9
  int v33; // eax
  __int64 v34; // r8
  int v35; // r9d
  int v36; // eax
  __int64 v37; // r10
  _BYTE *v38; // rcx
  __int64 v39; // rax
  int v40; // ebx
  unsigned int v41; // ecx
  int v42; // eax
  unsigned int v43; // ecx
  __int64 v44; // rcx
  unsigned int v45; // r15d
  __int64 v46; // rax
  unsigned __int16 v47; // ax
  int v48; // edx
  int v49; // eax
  int v50; // r8d
  int v51; // ecx
  int v52; // ecx
  char v53; // cl
  char *v54; // rax
  unsigned int v55; // eax
  const char *v56; // r8
  __int64 v57; // r9
  char *v58; // rdx
  unsigned __int16 v59; // ax
  __int16 v60; // ax
  unsigned __int16 TableDirectoryOffset; // ax
  __int64 v62; // r9
  unsigned __int16 v63; // ax
  int v64; // ecx
  __int64 v65; // r13
  __int64 v66; // rax
  __int64 v67; // r15
  unsigned int OS2FSType; // eax
  __int64 v69; // r13
  int v70; // r15d
  _DWORD *v71; // r13
  __int64 v72; // r9
  __int64 v73; // r8
  unsigned __int16 v74; // ax
  char *v75; // rdx
  const char *v76; // r13
  const char *v77; // r15
  __int64 v78; // r9
  __int64 v79; // r8
  unsigned __int16 v80; // ax
  __int64 v81; // r9
  unsigned __int16 v82; // ax
  __int64 v83; // rcx
  __int64 v84; // rax
  unsigned int v85; // r13d
  char *v86; // r15
  __int64 v87; // r13
  __int64 (__fastcall *v88)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  int v89; // eax
  unsigned int v90; // ebx
  __int64 v91; // rax
  unsigned __int16 RotatedGIDs; // ax
  unsigned int v93; // r13d
  const char *v94; // r13
  __int64 v95; // r9
  __int64 v96; // r8
  unsigned __int16 v97; // ax
  __int64 v98; // r9
  unsigned __int16 v99; // ax
  const char *v100; // r15
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 v106; // [rsp+20h] [rbp-E0h]
  double v107; // [rsp+28h] [rbp-D8h]
  __int64 v108; // [rsp+30h] [rbp-D0h]
  int v109; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v110[4]; // [rsp+54h] [rbp-ACh] BYREF
  int v111; // [rsp+58h] [rbp-A8h] BYREF
  int v112; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v113; // [rsp+60h] [rbp-A0h] BYREF
  int v114; // [rsp+64h] [rbp-9Ch] BYREF
  int v115; // [rsp+68h] [rbp-98h] BYREF
  int v116[2]; // [rsp+70h] [rbp-90h]
  int v117; // [rsp+78h] [rbp-88h] BYREF
  int v118; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v119; // [rsp+80h] [rbp-80h]
  const char *v120; // [rsp+88h] [rbp-78h]
  char pszDest[256]; // [rsp+A0h] [rbp-60h] BYREF

  v120 = a5;
  v6 = *(int **)(*(_QWORD *)(a1 + 48) + 8LL);
  if ( !v6 )
    return 2;
  v8 = *(_QWORD *)(a1 + 40);
  MinSfnt = 13;
  v119 = v8;
  v10 = *(_QWORD *)(v8 + 160);
  v11 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(v10 + 8);
  if ( v11 )
  {
    v12 = *(_QWORD *)(v8 + 168);
    if ( v11(v10, 3) )
    {
      if ( (unsigned int)(*(_DWORD *)(a1 + 4) - 13) > 1
        || (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 160LL) + 8LL))(
             *(_QWORD *)(*(_QWORD *)(a1 + 40) + 160LL),
             4) )
      {
        v109 = 0;
        MinSfnt = 0;
        v113 = 0;
        v14 = 0;
        *(_QWORD *)v116 = 0;
        if ( *(_DWORD *)(a1 + 8) != 2 )
        {
          MinSfnt = GetMinSfnt(a1, 0);
          if ( MinSfnt )
            goto LABEL_18;
          MinSfnt = FillInHeadTable(a1);
          if ( MinSfnt )
            goto LABEL_18;
          NumGlyphs = GetNumGlyphs(a1);
          v16 = *((_QWORD *)v6 + 52);
          v6[3] = NumGlyphs;
          TableSize = GetTableSize(a1, v16, 1633906540);
          v18 = TableSize;
          if ( !TableSize )
            goto LABEL_17;
          v19 = TableSize;
          v20 = v6[3];
          v21 = 4 * v20 + 4;
          if ( !*((_WORD *)v6 + 245) )
            v21 = 2 * v20 + 2;
          if ( v21 > TableSize )
            v19 = v21;
          v22 = UFLNewPtr(*(_QWORD *)(a1 + 32), v19);
          *((_QWORD *)v6 + 54) = v22;
          if ( !v22 )
          {
            MinSfnt = 6;
            goto LABEL_83;
          }
          if ( !(unsigned int)GetFontTable(a1, 1633906540, v22, v19) )
          {
LABEL_17:
            MinSfnt = 14;
LABEL_18:
            v23 = 0;
            goto LABEL_19;
          }
          if ( v21 > v18 )
          {
            v33 = GetTableSize(a1, *((_QWORD *)v6 + 52), 1719233639);
            v34 = *((_QWORD *)v6 + 54);
            v35 = v33;
            v36 = v6[3] - 1;
            if ( *((_WORD *)v6 + 245) )
            {
              v37 = (unsigned int)(4 * v36);
              if ( v35
                 - ((*(unsigned __int8 *)(v37 + v34 + 2)
                   + (((*(unsigned __int8 *)(v37 + v34) << 8) + *(unsigned __int8 *)(v37 + v34 + 1)) << 8)) << 8)
                 - (unsigned int)*(unsigned __int8 *)(v37 + v34 + 3) < 0x1001 )
              {
                v38 = (_BYTE *)(v37 + v34);
                *(_BYTE *)(v37 + v34 + 4) = HIBYTE(v35);
                v38[5] = BYTE2(v35);
                v38[6] = BYTE1(v35);
                v38[7] = v35;
              }
            }
            else
            {
              v39 = (unsigned int)(2 * v36);
              if ( v35 + -256 * *(unsigned __int8 *)(v39 + v34) - (unsigned int)*(unsigned __int8 *)(v39 + v34 + 1) < 0x1001 )
              {
                *(_BYTE *)((unsigned int)v39 + v34 + 3) = v35;
                *(_BYTE *)((unsigned int)v39 + v34 + 2) = BYTE1(v35);
              }
            }
          }
          v40 = *v6;
          v41 = v40 + GetTableSize(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL) + 408LL), 1719233639);
          v42 = 640;
          v43 = (5 * (v41 / 0x3FFE)) >> 2;
          if ( v43 > 0x280 )
            v42 = v43;
          v44 = *(_QWORD *)(a1 + 32);
          v45 = v42 + 1;
          v113 = v42 + 1;
          v46 = UFLNewPtr(v44, (unsigned int)(4 * (v42 + 1)));
          *((_QWORD *)v6 + 53) = v46;
          if ( !v46 )
          {
            MinSfnt = 6;
            goto LABEL_18;
          }
          v47 = CalculateStringLength(a1, v6, v45);
          if ( v47 )
          {
            MinSfnt = v47;
            goto LABEL_18;
          }
          if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
          {
            MinSfnt = 0;
          }
          else
          {
            v48 = *((__int16 *)v6 + 229);
            if ( !*((_WORD *)v6 + 229) )
              goto LABEL_17;
            v49 = *((__int16 *)v6 + 241);
            if ( v49 <= 0 )
            {
              if ( v49 < 0 )
                --v49;
            }
            else
            {
              ++v49;
            }
            v50 = *((__int16 *)v6 + 240);
            if ( v50 <= 0 )
            {
              if ( v50 < 0 )
                --v50;
            }
            else
            {
              ++v50;
            }
            v51 = *((__int16 *)v6 + 239);
            if ( v51 <= 0 )
              v52 = v51 + (v51 < 0);
            else
              v52 = v51 - 1;
            LODWORD(v108) = (v49 << 8) / v48;
            LODWORD(v107) = (v50 << 8) / v48;
            LODWORD(v106) = (v52 << 8) / v48;
            UFLsprintfEx(pszDest, 256, "%f %f %f %f", a4, *(double *)&v106, v107, *(double *)&v108);
            MinSfnt = StrmPutStringEOL(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 168LL), pszDest);
            if ( MinSfnt )
              goto LABEL_18;
          }
          if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
          {
            if ( a256Array012551[0] )
            {
              LOBYTE(v13) = 1;
              MinSfnt = StrmPutBytes(v12, " 256 array 0 1 255 {1 index exch /.notdef put} for ", 51, v13);
              if ( MinSfnt )
                goto LABEL_18;
            }
            else
            {
              MinSfnt = 0;
            }
          }
          if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
          {
            if ( (unsigned int)(*(_DWORD *)(a1 + 4) - 13) <= 1 )
              StringCchPrintfA(pszDest, 0x100u, "/%s%s", (const char *)v6 + 150, gcidSuffix[0]);
            else
              StringCchPrintfA(pszDest, 0x100u, " /%s", *(const char **)(a1 + 56));
            MinSfnt = StrmPutStringEOL(v12, pszDest);
            if ( MinSfnt )
              goto LABEL_18;
          }
        }
        if ( (unsigned int)(*(_DWORD *)(a1 + 4) - 13) <= 3 )
        {
          LOWORD(v107) = *((_WORD *)v6 + 28);
          *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) = *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) & 0xFF7F
                                                  | ((*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)(a1 + 40) + 88LL))(
                                                       *(_QWORD *)(a1 + 16),
                                                       2020896118,
                                                       0,
                                                       0,
                                                       0,
                                                       LODWORD(v107)) != 0
                                                   ? 0x80
                                                   : 0);
          if ( *((_WORD *)v6 + 32) )
          {
            v53 = 0;
            v23 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 4LL);
            v109 = v23;
            if ( v23 > 0x7F00 && (!*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0) )
              v53 = 1;
            if ( ((*(_DWORD *)(a1 + 4) - 13) & 0xFFFFFFFD) != 0 )
            {
              v54 = aWincharsetffff;
              v14 = aWincharsetffff_0;
            }
            else
            {
              v14 = aWincharsetffff_1;
              v54 = aWincharsetffff_2;
            }
            if ( !v53 )
              v14 = v54;
          }
          else
          {
            v23 = *((unsigned __int16 *)v6 + 73);
            v14 = (char *)v6 + 66;
            v109 = v23;
          }
          *(_QWORD *)v116 = v14;
LABEL_19:
          v24 = -1;
          if ( *(_DWORD *)(a1 + 8) == 2 )
            goto LABEL_169;
          if ( MinSfnt
            || (unsigned int)(*(_DWORD *)(a1 + 4) - 13) > 3
            || *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
          {
            if ( (!*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0) && !MinSfnt )
            {
              v58 = "Type42DictBegin";
              goto LABEL_107;
            }
          }
          else
          {
            StringCchPrintfA(pszDest, 0x100u, "(%s) (%s) %d", v14 + 36, v14 + 56, *((__int16 *)v14 + 38));
            MinSfnt = StrmPutStringEOL(v12, pszDest);
            v25 = 32512;
            if ( v23 < 0x7F00 )
              v25 = v23;
            StringCchPrintfA(pszDest, 0x100u, "%lu", v25);
            if ( !MinSfnt )
              MinSfnt = StrmPutStringEOL(v12, pszDest);
            v26 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v119 + 96);
            if ( v26 && (v27 = v26(*(_QWORD *)(a1 + 16), 0, 0), (v28 = v27) != 0) )
            {
              v29 = UFLNewPtr(*(_QWORD *)(a1 + 32), v27);
              v30 = v29;
              if ( v29 )
              {
                v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(v119 + 96))(*(_QWORD *)(a1 + 16), v29, v28);
                if ( !MinSfnt )
                {
                  LOBYTE(v32) = 1;
                  StrmPutBytes(v12, v30, v31, v32);
                }
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                  v30 - 8,
                  *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
              }
            }
            else
            {
              v55 = v23 - 1;
              if ( *((_WORD *)v6 + 74) )
                v56 = "%lu IDStrNull";
              else
                v56 = "%lu IDStr";
              v57 = 32512;
              if ( v55 < 0x7F00 )
                v57 = v55;
              StringCchPrintfA(pszDest, 0x100u, v56, v57);
              if ( !MinSfnt )
                MinSfnt = StrmPutStringEOL(v12, pszDest);
            }
            if ( *(char *)(*(_QWORD *)(a1 + 48) + 68LL) >= 0 )
            {
              v111 = 0;
              v115 = 0;
              v112 = 0;
              v117 = 0;
              v114 = 0;
              v118 = 0;
              v110[0] = 0;
              GetMetrics2FromTTF(
                a1,
                0,
                (unsigned int)&v111,
                (unsigned int)&v115,
                (__int64)&v112,
                (__int64)&v117,
                (__int64)&v114,
                (__int64)v110,
                1,
                (__int64)&v118);
              StringCchPrintfA(
                pszDest,
                0x100u,
                "{5{pop}repeat 0 -1 %ld %ld div %ld %ld div}bind",
                v112,
                v111,
                v117,
                v111);
            }
            else
            {
              StringCchPrintfA(pszDest, 0x100u, "{pop 4 index add}bind");
            }
            if ( !MinSfnt )
              MinSfnt = StrmPutStringEOL(v12, pszDest);
            StringCchPrintfA(pszDest, 0x100u, "CIDT42Begin");
            if ( !MinSfnt )
            {
              v58 = pszDest;
LABEL_107:
              MinSfnt = StrmPutStringEOL(v12, v58);
            }
          }
          if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
          {
            if ( MinSfnt )
              goto LABEL_159;
            LOBYTE(v13) = 1;
            v59 = StrmPutBytes(v12, "[", 1, v13);
            if ( v59 )
              goto LABEL_158;
            if ( *(_BYTE *)(v12 + 16) )
              v60 = PSSendSfntsAsciiHex(a1);
            else
              v60 = PSSendSfntsBinary(a1);
            *((_WORD *)v6 + 248) = v60;
            MinSfnt = GenerateGlyphStorageExt(a1, v113);
            if ( MinSfnt )
            {
LABEL_159:
              if ( (unsigned int)(*(_DWORD *)(a1 + 4) - 13) <= 3 )
              {
                if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
                {
                  if ( MinSfnt )
                    goto LABEL_253;
                  StringCchPrintfA(pszDest, 0x100u, "CIDT42End");
                  v75 = pszDest;
                  goto LABEL_164;
                }
              }
              else if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
              {
                if ( MinSfnt )
                  goto LABEL_253;
                v75 = "Type42DictEnd";
LABEL_164:
                MinSfnt = StrmPutStringEOL(v12, v75);
              }
LABEL_169:
              if ( !MinSfnt && (unsigned int)(*(_DWORD *)(a1 + 4) - 13) <= 1 )
              {
                v76 = *(const char **)v116;
                StringCchPrintfA(pszDest, 0x100u, "CMAP-%s", *(const char **)v116);
                MinSfnt = StrmPutStringEOL(v12, pszDest);
                if ( *(_DWORD *)(a1 + 4) == 13 )
                {
                  if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
                  {
                    v77 = v120;
                    StringCchPrintfA(pszDest, 0x100u, "%%%%IncludeResource: CIDFont %s", v120);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s] composefont pop",
                      *(const char **)(a1 + 56),
                      v76,
                      v77);
                  }
                  else if ( (unsigned int)v109 > 0x7F00 )
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "%lu dup 1 sub %lu IDStr2 /%s%s /%s%s T42CIDCP32K",
                      v109 - 32512,
                      32512,
                      (const char *)v6 + 150,
                      "CID32K",
                      (const char *)v6 + 150,
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        v79 = -1;
                        do
                          ++v79;
                        while ( pszDest[v79] );
                        LOBYTE(v78) = 1;
                        v80 = StrmPutBytes(v12, pszDest, v79, v78);
                      }
                      else
                      {
                        v80 = 0;
                      }
                      MinSfnt = v80;
                    }
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s ",
                      *(const char **)(a1 + 56),
                      v76,
                      (const char *)v6 + 150,
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        do
                          ++v24;
                        while ( pszDest[v24] );
                        LOBYTE(v81) = 1;
                        v82 = StrmPutBytes(v12, pszDest, (unsigned int)v24, v81);
                      }
                      else
                      {
                        v82 = 0;
                      }
                      MinSfnt = v82;
                    }
                    StringCchPrintfA(pszDest, 0x100u, "/%s%s] composefont pop", (char *)v6 + 150, "CID32K");
                  }
                  else
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s] composefont pop",
                      *(const char **)(a1 + 56),
                      v76,
                      (const char *)v6 + 150,
                      gcidSuffix[0]);
                  }
                  goto LABEL_258;
                }
                v83 = -1;
                do
                  ++v83;
                while ( v76[v83] );
                v84 = -1;
                do
                  ++v84;
                while ( *((_BYTE *)v6 + v84 + 150) );
                v85 = v83 + v84 + 1;
                v86 = (char *)UFLNewPtr(*(_QWORD *)(a1 + 32), v85);
                if ( v86 )
                {
                  StringCchPrintfA(v86, v85, "%s%s", *(const char **)v116, (const char *)v6 + 150);
                  if ( !MinSfnt )
                  {
                    v87 = *(_QWORD *)(a1 + 40);
                    *((_WORD *)v6 + 249) = 0;
                    v88 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(v87 + 112);
                    if ( v88 )
                    {
                      v89 = v88(*(_QWORD *)(a1 + 16), 0, 0, 0);
                      v90 = v89;
                      if ( v89 > 0 )
                      {
                        v91 = UFLNewPtr(*(_QWORD *)(a1 + 32), (unsigned int)(4 * v89 + 4));
                        *((_QWORD *)v6 + 63) = v91;
                        if ( v91 )
                        {
                          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(v87 + 112))(
                            *(_QWORD *)(a1 + 16),
                            v91,
                            v90,
                            0);
                          *((_WORD *)v6 + 249) = v90;
LABEL_205:
                          v93 = v109;
                          MinSfnt = T42SendCMapWinCharSetFFFF_V(
                                      a1,
                                      *((_QWORD *)v6 + 63),
                                      *((unsigned __int16 *)v6 + 249),
                                      v116[0],
                                      (__int64)v86,
                                      v109,
                                      v12,
                                      pszDest);
                          goto LABEL_209;
                        }
                        goto LABEL_207;
                      }
                      if ( !v89 )
                        goto LABEL_205;
                    }
                    RotatedGIDs = DefaultGetRotatedGIDs(a1, v6, v87 + 48);
                    if ( !RotatedGIDs )
                      goto LABEL_205;
                    MinSfnt = RotatedGIDs;
                  }
LABEL_208:
                  v93 = v109;
LABEL_209:
                  if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
                  {
                    v94 = v120;
                    StringCchPrintfA(pszDest, 0x100u, "%%%%IncludeResource: CIDFont %s", v120);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    v109 = 0;
                    v114 = 0;
                    v112 = 0;
                    v111 = 0;
                    v115 = 0;
                    v113 = 0;
                    v110[0] = 0;
                    StringCchPrintfA(pszDest, 0x100u, "/%s%s ", v94, gcidSuffix[0]);
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        v96 = -1;
                        do
                          ++v96;
                        while ( pszDest[v96] );
                        LOBYTE(v95) = 1;
                        v97 = StrmPutBytes(v12, pszDest, v96, v95);
                      }
                      else
                      {
                        v97 = 0;
                      }
                      MinSfnt = v97;
                    }
                    GetMetrics2FromTTF(
                      a1,
                      0,
                      (unsigned int)&v109,
                      (unsigned int)&v114,
                      (__int64)&v112,
                      (__int64)&v111,
                      (__int64)&v115,
                      (__int64)v110,
                      1,
                      (__int64)&v113);
                    if ( *(char *)(*(_QWORD *)(a1 + 48) + 68LL) >= 0 )
                    {
                      StringCchPrintfA(
                        pszDest,
                        0x100u,
                        "{5{pop}repeat 0 -1 %ld %ld div %ld %ld div}bind",
                        v112,
                        v109,
                        v111,
                        v109);
                    }
                    else if ( v111 == v113 )
                    {
                      StringCchPrintfA(pszDest, 0x100u, "true");
                    }
                    else
                    {
                      StringCchPrintfA(pszDest, 0x100u, "%ld %ld sub %ld div", v111, v113, v109);
                    }
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        do
                          ++v24;
                        while ( pszDest[v24] );
                        LOBYTE(v98) = 1;
                        v99 = StrmPutBytes(v12, pszDest, (unsigned int)v24, v98);
                      }
                      else
                      {
                        v99 = 0;
                      }
                      MinSfnt = v99;
                    }
                    StringCchPrintfA(pszDest, 0x100u, " /%s hfDef42CID", v94);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(pszDest, 0x100u, "/%s%s /%s hfDefRT42CID", *(const char **)(a1 + 56), "CIDR", v94);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s /%s%s] composefont pop",
                      *(const char **)(a1 + 56),
                      v86,
                      v94,
                      gcidSuffix[0],
                      *(const char **)(a1 + 56),
                      "CIDR");
                  }
                  else if ( v93 > 0x7F00 )
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "%lu dup 1 sub %lu IDStr2 /%s%s /%s%s T42CIDCP32K",
                      v93 - 32512,
                      32512,
                      (const char *)v6 + 150,
                      "CID32K",
                      (const char *)v6 + 150,
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s T42CIDCPR",
                      (const char *)v6 + 150,
                      "CIDR",
                      (const char *)v6 + 150,
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s T42CIDCPR",
                      (const char *)v6 + 150,
                      "CID32KR",
                      (const char *)v6 + 150,
                      "CID32K");
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s ",
                      *(const char **)(a1 + 56),
                      v86,
                      (const char *)v6 + 150,
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s /%s%s] composefont pop",
                      (char *)v6 + 150,
                      "CIDR",
                      (char *)v6 + 150,
                      "CID32K",
                      (char *)v6 + 150,
                      "CID32KR");
                  }
                  else
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s T42CIDCPR",
                      (const char *)v6 + 150,
                      "CIDR",
                      (const char *)v6 + 150,
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s /%s%s] composefont pop",
                      *(_QWORD *)(a1 + 56),
                      v86,
                      (char *)v6 + 150,
                      gcidSuffix[0],
                      (char *)v6 + 150,
                      "CIDR");
                  }
                  if ( !MinSfnt )
                    MinSfnt = StrmPutStringEOL(v12, pszDest);
                  if ( v86 )
                    (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v86 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  goto LABEL_260;
                }
LABEL_207:
                MinSfnt = 6;
                goto LABEL_208;
              }
LABEL_253:
              if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
              {
LABEL_260:
                v101 = *((_QWORD *)v6 + 52);
                if ( v101 )
                {
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                    v101 - 8,
                    *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  *((_QWORD *)v6 + 52) = 0;
                }
                if ( MinSfnt )
                {
                  v102 = *((_QWORD *)v6 + 51);
                  if ( v102 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v102 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  v103 = *((_QWORD *)v6 + 53);
                  *((_QWORD *)v6 + 51) = 0;
                  if ( v103 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v103 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  v104 = *((_QWORD *)v6 + 54);
                  *((_QWORD *)v6 + 53) = 0;
                  if ( v104 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v104 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  v105 = *((_QWORD *)v6 + 63);
                  *((_QWORD *)v6 + 54) = 0;
                  if ( v105 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v105 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  *((_QWORD *)v6 + 63) = 0;
                }
                else
                {
                  *(_DWORD *)(a1 + 8) = 4 - (*(_DWORD *)(a1 + 8) != 2);
                }
                return MinSfnt;
              }
              v100 = v120;
              StringCchPrintfA(pszDest, 0x100u, "\n%%%%IncludeResource: font %s", v120);
              if ( !MinSfnt )
                MinSfnt = StrmPutStringEOL(v12, pszDest);
              StringCchPrintfA(pszDest, 0x100u, "/%s true /%s hfRedefFont", *(_QWORD *)(a1 + 56), v100);
LABEL_258:
              if ( !MinSfnt )
                MinSfnt = StrmPutStringEOL(v12, pszDest);
              goto LABEL_260;
            }
            MinSfnt = StrmPutStringEOL(v12, "]def ");
          }
          if ( MinSfnt )
            goto LABEL_159;
          if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
            goto LABEL_276;
          TableDirectoryOffset = GetTableDirectoryOffset(v6, 1633906540);
          MinSfnt = StrmPutInt(v12, TableDirectoryOffset);
          if ( MinSfnt )
            goto LABEL_159;
          LOBYTE(v62) = 1;
          v59 = StrmPutBytes(v12, " ", 1, v62);
          if ( v59 )
            goto LABEL_158;
          v63 = GetTableDirectoryOffset(v6, 1719233639);
          MinSfnt = StrmPutInt(v12, v63);
          if ( !MinSfnt )
          {
            MinSfnt = StrmPutStringEOL(v12, " ");
            if ( !MinSfnt )
            {
              MinSfnt = StrmPutStringEOL(v12, "PrepFor2015");
              if ( !MinSfnt )
              {
LABEL_276:
                if ( *(_QWORD *)(a1 + 160) && (v64 = *(_DWORD *)(a1 + 28), (v64 & 8) != 0)
                  || (MinSfnt = StrmPutStringEOL(v12, "AddFontInfoBegin"),
                      v64 = *(_DWORD *)(a1 + 28) | 1,
                      *(_DWORD *)(a1 + 28) = v64,
                      !MinSfnt) )
                {
                  if ( *(_QWORD *)(a1 + 160) && (v64 & 8) != 0
                    || (StringCchPrintfA(pszDest, 0x100u, "AddFontInfo"),
                        MinSfnt = StrmPutStringEOL(v12, pszDest),
                        v64 = *(_DWORD *)(a1 + 28) | 2,
                        *(_DWORD *)(a1 + 28) = v64,
                        !MinSfnt) )
                  {
                    if ( (v65 = v119, !*(_QWORD *)(v119 + 128))
                      || *(_QWORD *)(a1 + 160) && (v64 & 8) != 0
                      || (v66 = UFLNewPtr(*(_QWORD *)(a1 + 32), 1000), (v67 = v66) == 0)
                      || ((*(void (__fastcall **)(_QWORD, __int64, __int64))(v65 + 128))(
                            *(_QWORD *)(a1 + 16),
                            v66,
                            1000),
                          MinSfnt = StrmPutStringEOL(v12, v67),
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                            v67 - 8,
                            *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL)),
                          !MinSfnt) )
                    {
                      if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
                        goto LABEL_277;
                      OS2FSType = GetOS2FSType(a1);
                      if ( OS2FSType == -1 )
                        OS2FSType = 4;
                      StringCchPrintfA(pszDest, 0x100u, "/FSType %ld def", OS2FSType);
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                      if ( !MinSfnt )
                      {
LABEL_277:
                        if ( (*(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0
                           || (MinSfnt = StrmPutStringEOL(v12, "AddFontInfoEnd")) == 0)
                          && (!*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0) )
                        {
                          v69 = *(_QWORD *)(a1 + 48);
                          v70 = *(_DWORD *)(v69 + 16);
                          if ( v70 )
                          {
                            v71 = *(_DWORD **)(v69 + 24);
                            LOBYTE(v13) = 1;
                            MinSfnt = StrmPutBytes(v12, "[", 1, v13);
                            do
                            {
                              StringCchPrintfA(pszDest, 0x100u, "16#%x ", *v71);
                              if ( !MinSfnt )
                              {
                                if ( pszDest[0] )
                                {
                                  v73 = -1;
                                  do
                                    ++v73;
                                  while ( pszDest[v73] );
                                  LOBYTE(v72) = 1;
                                  v74 = StrmPutBytes(v12, pszDest, v73, v72);
                                }
                                else
                                {
                                  v74 = 0;
                                }
                                MinSfnt = v74;
                              }
                              ++v71;
                              --v70;
                            }
                            while ( v70 );
                            StringCchPrintfA(pszDest, 0x100u, "] AddXUID");
                            if ( !MinSfnt )
                            {
                              v59 = StrmPutStringEOL(v12, pszDest);
LABEL_158:
                              MinSfnt = v59;
                              goto LABEL_159;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          goto LABEL_159;
        }
LABEL_83:
        v23 = 0;
        goto LABEL_19;
      }
    }
  }
  return MinSfnt;
}

```

## disassembly

```asm
0x18003d7e4  push    rbp
0x18003d7e6  push    rbx
0x18003d7e7  push    rsi
0x18003d7e8  push    rdi
0x18003d7e9  push    r12
0x18003d7eb  push    r13
0x18003d7ed  push    r14
0x18003d7ef  push    r15
0x18003d7f1  lea     rbp, [rsp-0B8h]
0x18003d7f9  sub     rsp, 1B8h
0x18003d800  mov     rax, cs:__security_cookie
0x18003d807  xor     rax, rsp
0x18003d80a  mov     [rbp+0F0h+var_50], rax
0x18003d811  mov     rax, [rbp+0F0h+arg_20]
0x18003d818  xor     r12d, r12d
0x18003d81b  mov     [rbp+0F0h+var_168], rax
0x18003d81f  mov     rdi, rcx
0x18003d822  mov     rax, [rcx+30h]
0x18003d826  mov     r14, [rax+8]
0x18003d82a  test    r14, r14
0x18003d82d  jnz     short loc_18003D838
0x18003d82f  lea     eax, [r14+2]
0x18003d833  jmp     loc_18003ED88
0x18003d838  mov     rdx, [rcx+28h]
0x18003d83c  mov     ebx, 0Dh
0x18003d841  mov     [rbp+0F0h+var_170], rdx
0x18003d845  mov     rcx, [rdx+0A0h]
0x18003d84c  mov     rax, [rcx+8]
0x18003d850  test    rax, rax
0x18003d853  jz      loc_18003ED85
0x18003d859  mov     rsi, [rdx+0A8h]
0x18003d860  lea     edx, [rbx-0Ah]
0x18003d863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d868  test    al, al
0x18003d86a  jz      loc_18003ED85
0x18003d870  mov     eax, [rdi+4]
0x18003d873  sub     eax, ebx
0x18003d875  cmp     eax, 1
0x18003d878  ja      short loc_18003D899
0x18003d87a  mov     rax, [rdi+28h]
0x18003d87e  lea     edx, [rbx-9]
0x18003d881  mov     rcx, [rax+0A0h]
0x18003d888  mov     rax, [rcx+8]
0x18003d88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d891  test    al, al
0x18003d893  jz      loc_18003ED85
0x18003d899  mov     eax, 2
0x18003d89e  mov     [rsp+1F0h+var_1A0], r12d
0x18003d8a3  mov     ebx, r12d
0x18003d8a6  mov     [rsp+1F0h+var_190], r12d
0x18003d8ab  mov     r13, r12
0x18003d8ae  mov     qword ptr [rsp+1F0h+var_180], r12
0x18003d8b3  cmp     [rdi+8], eax
0x18003d8b6  jz      loc_18003DDB2
0x18003d8bc  xor     edx, edx
0x18003d8be  mov     rcx, rdi
0x18003d8c1  call    GetMinSfnt
0x18003d8c6  movzx   ebx, ax
0x18003d8c9  cmp     r12w, ax
0x18003d8cd  jnz     loc_18003D975
0x18003d8d3  mov     rcx, rdi
0x18003d8d6  call    FillInHeadTable
0x18003d8db  movzx   ebx, ax
0x18003d8de  cmp     r12w, ax
0x18003d8e2  jnz     loc_18003D975
0x18003d8e8  mov     rcx, rdi
0x18003d8eb  call    GetNumGlyphs
0x18003d8f0  mov     rdx, [r14+1A0h]
0x18003d8f7  mov     r8d, 61636F6Ch
0x18003d8fd  mov     rcx, rdi
0x18003d900  mov     [r14+0Ch], eax
0x18003d904  call    GetTableSize
0x18003d909  mov     r15d, eax
0x18003d90c  test    eax, eax
0x18003d90e  jz      short loc_18003D970
0x18003d910  cmp     [r14+1EAh], r12w
0x18003d918  mov     r12d, eax
0x18003d91b  mov     edx, [r14+0Ch]
0x18003d91f  lea     ecx, ds:2[rdx*2]
0x18003d926  lea     ebx, ds:4[rdx*4]
0x18003d92d  cmovz   ebx, ecx
0x18003d930  mov     rcx, [rdi+20h]
0x18003d934  cmp     ebx, eax
0x18003d936  cmova   r12d, ebx
0x18003d93a  mov     edx, r12d
0x18003d93d  call    UFLNewPtr
0x18003d942  mov     [r14+1B0h], rax
0x18003d949  test    rax, rax
0x18003d94c  jz      loc_18003DE73
0x18003d952  mov     r9d, r12d
0x18003d955  mov     r8, rax
0x18003d958  mov     edx, 61636F6Ch
0x18003d95d  mov     rcx, rdi
0x18003d960  call    GetFontTable
0x18003d965  xor     r12d, r12d
0x18003d968  test    eax, eax
0x18003d96a  jnz     loc_18003DAB8
0x18003d970  mov     ebx, 0Eh
0x18003d975  mov     r15d, r12d
0x18003d978  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003d97c  cmp     dword ptr [rdi+8], 2
0x18003d980  jz      loc_18003E428
0x18003d986  xor     eax, eax
0x18003d988  cmp     ax, bx
0x18003d98b  jnz     loc_18003E00A
0x18003d991  mov     eax, [rdi+4]
0x18003d994  sub     eax, 0Dh
0x18003d997  cmp     eax, 3
0x18003d99a  ja      loc_18003E00A
0x18003d9a0  cmp     qword ptr [rdi+0A0h], 0
0x18003d9a8  jz      short loc_18003D9B4
0x18003d9aa  test    byte ptr [rdi+1Ch], 8
0x18003d9ae  jnz     loc_18003E00A
0x18003d9b4  movsx   eax, word ptr [r13+4Ch]
0x18003d9b9  lea     rcx, [r13+38h]
0x18003d9bd  lea     r9, [r13+24h]
0x18003d9c1  mov     [rsp+1F0h+var_1C8], eax
0x18003d9c5  mov     [rsp+1F0h+var_1D0], rcx
0x18003d9ca  lea     r8, aSSD; "(%s) (%s) %d"
0x18003d9d1  mov     r13d, 100h
0x18003d9d7  lea     rcx, [rbp+0F0h+pszDest]; pszDest
0x18003d9db  mov     edx, r13d; cchDest
0x18003d9de  call    StringCchPrintfA
0x18003d9e3  lea     rdx, [rbp+0F0h+pszDest]
0x18003d9e7  mov     rcx, rsi
0x18003d9ea  call    StrmPutStringEOL
0x18003d9ef  movzx   ebx, ax
0x18003d9f2  lea     r8, aLu_0; "%lu"
0x18003d9f9  mov     eax, 7F00h
0x18003d9fe  lea     rcx, [rbp+0F0h+pszDest]; pszDest
0x18003da02  cmp     r15d, eax
0x18003da05  mov     r9d, eax
0x18003da08  mov     edx, r13d; cchDest
0x18003da0b  cmovb   r9d, r15d
0x18003da0f  call    StringCchPrintfA
0x18003da14  xor     r13d, r13d
0x18003da17  cmp     r13w, bx
0x18003da1b  jnz     short loc_18003DA2C
0x18003da1d  lea     rdx, [rbp+0F0h+pszDest]
0x18003da21  mov     rcx, rsi
0x18003da24  call    StrmPutStringEOL
0x18003da29  movzx   ebx, ax
0x18003da2c  mov     rax, [rbp+0F0h+var_170]
0x18003da30  mov     rax, [rax+60h]
0x18003da34  test    rax, rax
0x18003da37  jz      loc_18003DEB4
0x18003da3d  mov     rcx, [rdi+10h]
0x18003da41  xor     r8d, r8d
0x18003da44  xor     edx, edx
0x18003da46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da4b  mov     r13d, eax
0x18003da4e  test    eax, eax
0x18003da50  jz      loc_18003DEB1
0x18003da56  mov     rcx, [rdi+20h]
0x18003da5a  mov     edx, eax
0x18003da5c  call    UFLNewPtr
0x18003da61  mov     r15, rax
0x18003da64  test    rax, rax
0x18003da67  jz      loc_18003DF11
0x18003da6d  mov     rcx, [rdi+10h]
0x18003da71  mov     rdx, rax
0x18003da74  mov     rax, [rbp+0F0h+var_170]
0x18003da78  mov     r8d, r13d
0x18003da7b  mov     rax, [rax+60h]
0x18003da7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da84  xor     r13d, r13d
0x18003da87  cmp     r13w, bx
0x18003da8b  jnz     short loc_18003DA9E
0x18003da8d  mov     r9b, 1
0x18003da90  mov     r8d, eax
0x18003da93  mov     rdx, r15
0x18003da96  mov     rcx, rsi
0x18003da99  call    StrmPutBytes
0x18003da9e  mov     rax, [rdi+20h]
0x18003daa2  lea     rcx, [r15-8]
0x18003daa6  mov     rdx, [rax+20h]
0x18003daaa  mov     rax, [rax+8]
0x18003daae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dab3  jmp     loc_18003DF14
0x18003dab8  cmp     ebx, r15d
0x18003dabb  jbe     loc_18003DB87
0x18003dac1  mov     rdx, [r14+1A0h]
0x18003dac8  mov     r8d, 66796C67h
0x18003dace  mov     rcx, rdi
0x18003dad1  call    GetTableSize
0x18003dad6  mov     r8, [r14+1B0h]
0x18003dadd  mov     r9d, eax
0x18003dae0  mov     eax, [r14+0Ch]
0x18003dae4  dec     eax
0x18003dae6  cmp     [r14+1EAh], r12w
0x18003daee  jz      short loc_18003DB54
0x18003daf0  lea     ecx, ds:0[rax*4]
0x18003daf7  movzx   edx, byte ptr [rcx+r8+1]
0x18003dafd  mov     r10d, ecx
0x18003db00  movzx   ecx, byte ptr [rcx+r8]
0x18003db05  shl     ecx, 8
0x18003db08  add     edx, ecx
0x18003db0a  mov     ecx, r9d
0x18003db0d  movzx   eax, byte ptr [r10+r8+2]
0x18003db13  shl     edx, 8
0x18003db16  add     edx, eax
0x18003db18  movzx   eax, byte ptr [r10+r8+3]
0x18003db1e  shl     edx, 8
0x18003db21  sub     ecx, edx
0x18003db23  sub     ecx, eax
0x18003db25  cmp     ecx, 1001h
0x18003db2b  jnb     short loc_18003DB87
0x18003db2d  lea     rcx, [r10+r8]
0x18003db31  mov     eax, r9d
0x18003db34  shr     eax, 18h
0x18003db37  mov     [r10+r8+4], al
0x18003db3c  mov     eax, r9d
0x18003db3f  shr     eax, 10h
0x18003db42  mov     [rcx+5], al
0x18003db45  mov     eax, r9d
0x18003db48  shr     eax, 8
0x18003db4b  mov     [rcx+6], al
0x18003db4e  mov     [rcx+7], r9b
0x18003db52  jmp     short loc_18003DB87
0x18003db54  add     eax, eax
0x18003db56  mov     r10d, eax
0x18003db59  movzx   ecx, byte ptr [rax+r8+1]
0x18003db5f  movzx   eax, byte ptr [rax+r8]
0x18003db64  imul    edx, eax, 0FFFFFF00h
0x18003db6a  sub     edx, ecx
0x18003db6c  add     edx, r9d
0x18003db6f  cmp     edx, 1001h
0x18003db75  jnb     short loc_18003DB87
0x18003db77  mov     eax, r9d
0x18003db7a  mov     [r10+r8+3], r9b
0x18003db7f  shr     eax, 8
0x18003db82  mov     [r10+r8+2], al
0x18003db87  mov     rax, [rdi+30h]
0x18003db8b  mov     r8d, 66796C67h
0x18003db91  mov     ebx, [r14]
0x18003db94  mov     rcx, rdi
0x18003db97  mov     rdx, [rax+8]
0x18003db9b  mov     rdx, [rdx+198h]
0x18003dba2  call    GetTableSize
0x18003dba7  lea     ecx, [rbx+rax]
0x18003dbaa  mov     eax, 80041h
0x18003dbaf  mul     ecx
0x18003dbb1  mov     eax, 280h
0x18003dbb6  sub     ecx, edx
0x18003dbb8  shr     ecx, 1
0x18003dbba  add     ecx, edx
0x18003dbbc  shr     ecx, 0Dh
0x18003dbbf  lea     ecx, [rcx+rcx*4]
0x18003dbc2  shr     ecx, 2
0x18003dbc5  cmp     ecx, eax
0x18003dbc7  cmova   eax, ecx
0x18003dbca  mov     rcx, [rdi+20h]
0x18003dbce  lea     r15d, [rax+1]
0x18003dbd2  lea     edx, ds:0[r15*4]
0x18003dbda  mov     [rsp+1F0h+var_190], r15d
0x18003dbdf  call    UFLNewPtr
0x18003dbe4  mov     [r14+1A8h], rax
0x18003dbeb  test    rax, rax
0x18003dbee  jz      loc_18003DE69
0x18003dbf4  mov     r8d, r15d
0x18003dbf7  mov     rdx, r14
0x18003dbfa  mov     rcx, rdi
0x18003dbfd  call    CalculateStringLength
0x18003dc02  cmp     r12w, ax
0x18003dc06  jnz     loc_18003DE61
0x18003dc0c  cmp     [rdi+0A0h], r12
0x18003dc13  jz      short loc_18003DC23
0x18003dc15  test    byte ptr [rdi+1Ch], 8
0x18003dc19  jz      short loc_18003DC23
0x18003dc1b  movzx   ebx, ax
0x18003dc1e  jmp     loc_18003DD03
0x18003dc23  movsx   edx, word ptr [r14+1CAh]
0x18003dc2b  cmp     r12w, dx
0x18003dc2f  jz      loc_18003D970
0x18003dc35  movsx   eax, word ptr [r14+1E2h]
0x18003dc3d  test    eax, eax
0x18003dc3f  jle     short loc_18003DC45
0x18003dc41  inc     eax
0x18003dc43  jmp     short loc_18003DC49
0x18003dc45  jns     short loc_18003DC49
0x18003dc47  dec     eax
0x18003dc49  movsx   r8d, word ptr [r14+1E0h]
0x18003dc51  test    r8d, r8d
0x18003dc54  jle     short loc_18003DC5B
0x18003dc56  inc     r8d
0x18003dc59  jmp     short loc_18003DC60
0x18003dc5b  jns     short loc_18003DC60
0x18003dc5d  dec     r8d
0x18003dc60  movsx   ecx, word ptr [r14+1DEh]
0x18003dc68  test    ecx, ecx
0x18003dc6a  jle     short loc_18003DC70
0x18003dc6c  dec     ecx
0x18003dc6e  jmp     short loc_18003DC74
0x18003dc70  jns     short loc_18003DC74
0x18003dc72  inc     ecx
0x18003dc74  movsx   r11d, word ptr [r14+1DCh]
0x18003dc7c  test    r11d, r11d
0x18003dc7f  jle     short loc_18003DC86
0x18003dc81  dec     r11d
0x18003dc84  jmp     short loc_18003DC8B
  ... truncated ...
```

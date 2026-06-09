# T42CreateBaseFont

- ea: `0x18003f09c`
- end: `0x180040664`
- name: `T42CreateBaseFont`
- size: `5576`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, double, const char *)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180038370`
- `0x1800407a0`

## callees

- `0x180001f20`
- `0x180005670`
- `0x180039e10`
- `0x180039fd4`
- `0x18003a1f4`
- `0x18003a3a8`
- `0x18003c1f8`
- `0x18003c5ac`
- `0x18003c79c`
- `0x18003c9b4`
- `0x18003d258`
- `0x18003d434`
- `0x18003d98c`
- `0x18003da58`
- `0x18003db18`
- `0x18003dc00`
- `0x18003f09c`
- `0x180040b0c`
- `0x18004496c`
- `0x180044d30`
- `0x180044e0c`
- `0x180046dcc`
- `0x18005f010`

## string_xrefs

- `0x18003fdc7`: `/%s /%s [/%s%s] composefont pop`
- `0x18003fecc`: `/%s%s] composefont pop`
- `0x18003fd7c`: `/%s /%s [/%s] composefont pop`
- `0x180040247`: `/%s /%s [/%s%s /%s%s] composefont pop`
- `0x180040308`: `/%s /%s [/%s%s /%s%s] composefont pop`
- `0x18004047a`: `/%s%s /%s%s /%s%s] composefont pop`

## pseudocode

```c
__int64 __fastcall T42CreateBaseFont(__int64 a1, __int64 a2, __int64 a3, double a4, const char *a5)
{
  __int64 v6; // r14
  __int64 v8; // rdx
  unsigned __int16 MinSfnt; // bx
  __int64 v10; // rcx
  unsigned __int8 (__fastcall *v11)(__int64, __int64); // rax
  __int64 v12; // rsi
  char *v13; // r13
  int NumGlyphs; // eax
  __int64 v15; // rdx
  unsigned int TableSize; // eax
  unsigned int v17; // r15d
  unsigned int v18; // r12d
  int v19; // edx
  unsigned int v20; // ebx
  _DWORD *v21; // rax
  unsigned int v22; // r15d
  __int64 v23; // r12
  __int64 v24; // r9
  __int64 (__fastcall *v25)(_QWORD, _QWORD, _QWORD); // rax
  unsigned int v26; // eax
  unsigned int v27; // r13d
  _DWORD *v28; // rax
  __int64 v29; // r15
  int v30; // eax
  int v31; // eax
  __int64 v32; // r8
  int v33; // r9d
  int v34; // eax
  __int64 v35; // r10
  _BYTE *v36; // rcx
  __int64 v37; // rax
  int v38; // ebx
  unsigned int v39; // ecx
  int v40; // eax
  unsigned int v41; // ecx
  __int64 v42; // rcx
  int v43; // r15d
  _DWORD *v44; // rax
  unsigned __int16 v45; // ax
  int v46; // edx
  int v47; // eax
  int v48; // r8d
  int v49; // ecx
  int v50; // ecx
  char v51; // cl
  char *v52; // rax
  unsigned int v53; // eax
  const char *v54; // r8
  __int64 v55; // r9
  char *v56; // rdx
  unsigned __int16 v57; // ax
  __int16 v58; // ax
  unsigned __int16 TableDirectoryOffset; // ax
  unsigned __int16 v60; // ax
  int v61; // ecx
  __int64 v62; // r13
  _DWORD *v63; // rax
  _BYTE *v64; // r15
  unsigned int OS2FSType; // eax
  __int64 v66; // r13
  int v67; // r15d
  _DWORD *v68; // r13
  __int64 v69; // r8
  unsigned __int16 v70; // ax
  char *v71; // rdx
  const char *v72; // r13
  const char *v73; // r15
  __int64 v74; // r8
  unsigned __int16 v75; // ax
  unsigned __int16 v76; // ax
  __int64 v77; // rcx
  __int64 v78; // rax
  unsigned int v79; // r13d
  char *v80; // r15
  __int64 v81; // r13
  __int64 (__fastcall *v82)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  int v83; // eax
  unsigned int v84; // ebx
  _DWORD *v85; // rax
  unsigned __int16 RotatedGIDs; // ax
  unsigned int v87; // r13d
  const char *v88; // r13
  __int64 v89; // r8
  unsigned __int16 v90; // ax
  unsigned __int16 v91; // ax
  const char *v92; // r15
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // [rsp+20h] [rbp-E0h]
  double v99; // [rsp+28h] [rbp-D8h]
  __int64 v100; // [rsp+30h] [rbp-D0h]
  int v101; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v102[4]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v103; // [rsp+58h] [rbp-A8h] BYREF
  int v104; // [rsp+5Ch] [rbp-A4h] BYREF
  int v105; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v106; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v107; // [rsp+68h] [rbp-98h] BYREF
  int v108[2]; // [rsp+70h] [rbp-90h]
  unsigned int v109; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v110; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v111; // [rsp+80h] [rbp-80h]
  const char *v112; // [rsp+88h] [rbp-78h]
  char pszDest[256]; // [rsp+A0h] [rbp-60h] BYREF

  v112 = a5;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
  if ( !v6 )
    return 2;
  v8 = *(_QWORD *)(a1 + 40);
  MinSfnt = 13;
  v111 = v8;
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
        v101 = 0;
        MinSfnt = 0;
        v105 = 0;
        v13 = 0;
        *(_QWORD *)v108 = 0;
        if ( *(_DWORD *)(a1 + 8) != 2 )
        {
          MinSfnt = GetMinSfnt(a1, 0);
          if ( MinSfnt )
            goto LABEL_18;
          MinSfnt = FillInHeadTable(a1);
          if ( MinSfnt )
            goto LABEL_18;
          NumGlyphs = GetNumGlyphs((_QWORD *)a1);
          v15 = *(_QWORD *)(v6 + 416);
          *(_DWORD *)(v6 + 12) = NumGlyphs;
          TableSize = GetTableSize((_QWORD *)a1, v15, 0x61636F6Cu);
          v17 = TableSize;
          if ( !TableSize )
            goto LABEL_17;
          v18 = TableSize;
          v19 = *(_DWORD *)(v6 + 12);
          v20 = 4 * v19 + 4;
          if ( !*(_WORD *)(v6 + 490) )
            v20 = 2 * v19 + 2;
          if ( v20 > TableSize )
            v18 = v20;
          v21 = UFLNewPtr(*(_QWORD *)(a1 + 32), v18);
          *(_QWORD *)(v6 + 432) = v21;
          if ( !v21 )
          {
            MinSfnt = 6;
            goto LABEL_83;
          }
          if ( !(unsigned int)GetFontTable((_QWORD *)a1, 1633906540, (__int64)v21, v18) )
          {
LABEL_17:
            MinSfnt = 14;
LABEL_18:
            v22 = 0;
            goto LABEL_19;
          }
          if ( v20 > v17 )
          {
            v31 = GetTableSize((_QWORD *)a1, *(_QWORD *)(v6 + 416), 0x66796C67u);
            v32 = *(_QWORD *)(v6 + 432);
            v33 = v31;
            v34 = *(_DWORD *)(v6 + 12) - 1;
            if ( *(_WORD *)(v6 + 490) )
            {
              v35 = (unsigned int)(4 * v34);
              if ( v33
                 - ((*(unsigned __int8 *)(v35 + v32 + 2)
                   + (((*(unsigned __int8 *)(v35 + v32) << 8) + *(unsigned __int8 *)(v35 + v32 + 1)) << 8)) << 8)
                 - (unsigned int)*(unsigned __int8 *)(v35 + v32 + 3) < 0x1001 )
              {
                v36 = (_BYTE *)(v35 + v32);
                *(_BYTE *)(v35 + v32 + 4) = HIBYTE(v33);
                v36[5] = BYTE2(v33);
                v36[6] = BYTE1(v33);
                v36[7] = v33;
              }
            }
            else
            {
              v37 = (unsigned int)(2 * v34);
              if ( v33 + -256 * *(unsigned __int8 *)(v37 + v32) - (unsigned int)*(unsigned __int8 *)(v37 + v32 + 1) < 0x1001 )
              {
                *(_BYTE *)((unsigned int)v37 + v32 + 3) = v33;
                *(_BYTE *)((unsigned int)v37 + v32 + 2) = BYTE1(v33);
              }
            }
          }
          v38 = *(_DWORD *)v6;
          v39 = v38
              + GetTableSize((_QWORD *)a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL) + 408LL), 0x66796C67u);
          v40 = 640;
          v41 = (5 * (v39 / 0x3FFE)) >> 2;
          if ( v41 > 0x280 )
            v40 = v41;
          v42 = *(_QWORD *)(a1 + 32);
          v43 = v40 + 1;
          v105 = v40 + 1;
          v44 = UFLNewPtr(v42, 4 * (v40 + 1));
          *(_QWORD *)(v6 + 424) = v44;
          if ( !v44 )
          {
            MinSfnt = 6;
            goto LABEL_18;
          }
          v45 = CalculateStringLength(a1, v6, v43);
          if ( v45 )
          {
            MinSfnt = v45;
            goto LABEL_18;
          }
          if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
          {
            MinSfnt = 0;
          }
          else
          {
            v46 = *(__int16 *)(v6 + 458);
            if ( !*(_WORD *)(v6 + 458) )
              goto LABEL_17;
            v47 = *(__int16 *)(v6 + 482);
            if ( v47 <= 0 )
            {
              if ( v47 < 0 )
                --v47;
            }
            else
            {
              ++v47;
            }
            v48 = *(__int16 *)(v6 + 480);
            if ( v48 <= 0 )
            {
              if ( v48 < 0 )
                --v48;
            }
            else
            {
              ++v48;
            }
            v49 = *(__int16 *)(v6 + 478);
            if ( v49 <= 0 )
              v50 = v49 + (v49 < 0);
            else
              v50 = v49 - 1;
            LODWORD(v100) = (v47 << 8) / v46;
            LODWORD(v99) = (v48 << 8) / v46;
            LODWORD(v98) = (v50 << 8) / v46;
            UFLsprintfEx((__int64)pszDest, 256, "%f %f %f %f", a4, *(double *)&v98, v99, *(double *)&v100);
            MinSfnt = StrmPutStringEOL(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 168LL), pszDest);
            if ( MinSfnt )
              goto LABEL_18;
          }
          if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
          {
            if ( a256Array012551[0] )
            {
              MinSfnt = StrmPutBytes(v12, (__int64)" 256 array 0 1 255 {1 index exch /.notdef put} for ", 51, 1);
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
              StringCchPrintfA(pszDest, 0x100u, "/%s%s", (const char *)(v6 + 150), gcidSuffix[0]);
            else
              StringCchPrintfA(pszDest, 0x100u, " /%s", *(const char **)(a1 + 56));
            MinSfnt = StrmPutStringEOL(v12, pszDest);
            if ( MinSfnt )
              goto LABEL_18;
          }
        }
        if ( (unsigned int)(*(_DWORD *)(a1 + 4) - 13) <= 3 )
        {
          LOWORD(v99) = *(_WORD *)(v6 + 56);
          *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) = *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) & 0xFF7F
                                                  | ((*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)(a1 + 40) + 88LL))(
                                                       *(_QWORD *)(a1 + 16),
                                                       2020896118,
                                                       0,
                                                       0,
                                                       0,
                                                       LODWORD(v99)) != 0
                                                   ? 0x80
                                                   : 0);
          if ( *(_WORD *)(v6 + 64) )
          {
            v51 = 0;
            v22 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 4LL);
            v101 = v22;
            if ( v22 > 0x7F00 && (!*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0) )
              v51 = 1;
            if ( ((*(_DWORD *)(a1 + 4) - 13) & 0xFFFFFFFD) != 0 )
            {
              v52 = aWincharsetffff;
              v13 = aWincharsetffff_0;
            }
            else
            {
              v13 = aWincharsetffff_1;
              v52 = aWincharsetffff_2;
            }
            if ( !v51 )
              v13 = v52;
          }
          else
          {
            v22 = *(unsigned __int16 *)(v6 + 146);
            v13 = (char *)(v6 + 66);
            v101 = v22;
          }
          *(_QWORD *)v108 = v13;
LABEL_19:
          v23 = -1;
          if ( *(_DWORD *)(a1 + 8) == 2 )
            goto LABEL_169;
          if ( MinSfnt
            || (unsigned int)(*(_DWORD *)(a1 + 4) - 13) > 3
            || *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
          {
            if ( (!*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0) && !MinSfnt )
            {
              v56 = "Type42DictBegin";
              goto LABEL_107;
            }
          }
          else
          {
            StringCchPrintfA(pszDest, 0x100u, "(%s) (%s) %d", v13 + 36, v13 + 56, *((__int16 *)v13 + 38));
            MinSfnt = StrmPutStringEOL(v12, pszDest);
            v24 = 32512;
            if ( v22 < 0x7F00 )
              v24 = v22;
            StringCchPrintfA(pszDest, 0x100u, "%lu", v24);
            if ( !MinSfnt )
              MinSfnt = StrmPutStringEOL(v12, pszDest);
            v25 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v111 + 96);
            if ( v25 && (v26 = v25(*(_QWORD *)(a1 + 16), 0, 0), (v27 = v26) != 0) )
            {
              v28 = UFLNewPtr(*(_QWORD *)(a1 + 32), v26);
              v29 = (__int64)v28;
              if ( v28 )
              {
                v30 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD))(v111 + 96))(*(_QWORD *)(a1 + 16), v28, v27);
                if ( !MinSfnt )
                  StrmPutBytes(v12, v29, v30, 1);
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                  v29 - 8,
                  *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
              }
            }
            else
            {
              v53 = v22 - 1;
              if ( *(_WORD *)(v6 + 148) )
                v54 = "%lu IDStrNull";
              else
                v54 = "%lu IDStr";
              v55 = 32512;
              if ( v53 < 0x7F00 )
                v55 = v53;
              StringCchPrintfA(pszDest, 0x100u, v54, v55);
              if ( !MinSfnt )
                MinSfnt = StrmPutStringEOL(v12, pszDest);
            }
            if ( *(char *)(*(_QWORD *)(a1 + 48) + 68LL) >= 0 )
            {
              v103 = 0;
              v107 = 0;
              v104 = 0;
              v109 = 0;
              v106 = 0;
              v110 = 0;
              v102[0] = 0;
              GetMetrics2FromTTF(a1, 0, &v103, &v107, &v104, &v109, &v106, v102, 1, &v110);
              StringCchPrintfA(
                pszDest,
                0x100u,
                "{5{pop}repeat 0 -1 %ld %ld div %ld %ld div}bind",
                v104,
                v103,
                v109,
                v103);
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
              v56 = pszDest;
LABEL_107:
              MinSfnt = StrmPutStringEOL(v12, v56);
            }
          }
          if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
          {
            if ( MinSfnt )
              goto LABEL_159;
            v57 = StrmPutBytes(v12, (__int64)"[", 1, 1);
            if ( v57 )
              goto LABEL_158;
            if ( *(_BYTE *)(v12 + 16) )
              v58 = PSSendSfntsAsciiHex(a1);
            else
              v58 = PSSendSfntsBinary(a1);
            *(_WORD *)(v6 + 496) = v58;
            MinSfnt = GenerateGlyphStorageExt(a1, v105);
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
                  v71 = pszDest;
                  goto LABEL_164;
                }
              }
              else if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
              {
                if ( MinSfnt )
                  goto LABEL_253;
                v71 = "Type42DictEnd";
LABEL_164:
                MinSfnt = StrmPutStringEOL(v12, v71);
              }
LABEL_169:
              if ( !MinSfnt && (unsigned int)(*(_DWORD *)(a1 + 4) - 13) <= 1 )
              {
                v72 = *(const char **)v108;
                StringCchPrintfA(pszDest, 0x100u, "CMAP-%s", *(const char **)v108);
                MinSfnt = StrmPutStringEOL(v12, pszDest);
                if ( *(_DWORD *)(a1 + 4) == 13 )
                {
                  if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
                  {
                    v73 = v112;
                    StringCchPrintfA(pszDest, 0x100u, "%%%%IncludeResource: CIDFont %s", v112);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s] composefont pop",
                      *(const char **)(a1 + 56),
                      v72,
                      v73);
                  }
                  else if ( (unsigned int)v101 > 0x7F00 )
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "%lu dup 1 sub %lu IDStr2 /%s%s /%s%s T42CIDCP32K",
                      v101 - 32512,
                      32512,
                      (const char *)(v6 + 150),
                      "CID32K",
                      (const char *)(v6 + 150),
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        v74 = -1;
                        do
                          ++v74;
                        while ( pszDest[v74] );
                        v75 = StrmPutBytes(v12, (__int64)pszDest, v74, 1);
                      }
                      else
                      {
                        v75 = 0;
                      }
                      MinSfnt = v75;
                    }
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s ",
                      *(const char **)(a1 + 56),
                      v72,
                      (const char *)(v6 + 150),
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        do
                          ++v23;
                        while ( pszDest[v23] );
                        v76 = StrmPutBytes(v12, (__int64)pszDest, v23, 1);
                      }
                      else
                      {
                        v76 = 0;
                      }
                      MinSfnt = v76;
                    }
                    StringCchPrintfA(pszDest, 0x100u, "/%s%s] composefont pop", v6 + 150, "CID32K");
                  }
                  else
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s] composefont pop",
                      *(const char **)(a1 + 56),
                      v72,
                      (const char *)(v6 + 150),
                      gcidSuffix[0]);
                  }
                  goto LABEL_258;
                }
                v77 = -1;
                do
                  ++v77;
                while ( v72[v77] );
                v78 = -1;
                do
                  ++v78;
                while ( *(_BYTE *)(v6 + v78 + 150) );
                v79 = v77 + v78 + 1;
                v80 = (char *)UFLNewPtr(*(_QWORD *)(a1 + 32), v79);
                if ( v80 )
                {
                  StringCchPrintfA(v80, v79, "%s%s", *(const char **)v108, (const char *)(v6 + 150));
                  if ( !MinSfnt )
                  {
                    v81 = *(_QWORD *)(a1 + 40);
                    *(_WORD *)(v6 + 498) = 0;
                    v82 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(v81 + 112);
                    if ( v82 )
                    {
                      v83 = v82(*(_QWORD *)(a1 + 16), 0, 0, 0);
                      v84 = v83;
                      if ( v83 > 0 )
                      {
                        v85 = UFLNewPtr(*(_QWORD *)(a1 + 32), 4 * v83 + 4);
                        *(_QWORD *)(v6 + 504) = v85;
                        if ( v85 )
                        {
                          (*(void (__fastcall **)(_QWORD, _DWORD *, _QWORD, _QWORD))(v81 + 112))(
                            *(_QWORD *)(a1 + 16),
                            v85,
                            v84,
                            0);
                          *(_WORD *)(v6 + 498) = v84;
LABEL_205:
                          v87 = v101;
                          MinSfnt = T42SendCMapWinCharSetFFFF_V(
                                      a1,
                                      *(unsigned __int16 **)(v6 + 504),
                                      *(_WORD *)(v6 + 498),
                                      *(const char **)v108,
                                      v80,
                                      v101,
                                      v12,
                                      pszDest);
                          goto LABEL_209;
                        }
                        goto LABEL_207;
                      }
                      if ( !v83 )
                        goto LABEL_205;
                    }
                    RotatedGIDs = DefaultGetRotatedGIDs((_QWORD *)a1, v6, v81 + 48);
                    if ( !RotatedGIDs )
                      goto LABEL_205;
                    MinSfnt = RotatedGIDs;
                  }
LABEL_208:
                  v87 = v101;
LABEL_209:
                  if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
                  {
                    v88 = v112;
                    StringCchPrintfA(pszDest, 0x100u, "%%%%IncludeResource: CIDFont %s", v112);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    v101 = 0;
                    v106 = 0;
                    v104 = 0;
                    v103 = 0;
                    v107 = 0;
                    v105 = 0;
                    v102[0] = 0;
                    StringCchPrintfA(pszDest, 0x100u, "/%s%s ", v88, gcidSuffix[0]);
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        v89 = -1;
                        do
                          ++v89;
                        while ( pszDest[v89] );
                        v90 = StrmPutBytes(v12, (__int64)pszDest, v89, 1);
                      }
                      else
                      {
                        v90 = 0;
                      }
                      MinSfnt = v90;
                    }
                    GetMetrics2FromTTF(
                      a1,
                      0,
                      (unsigned int *)&v101,
                      &v106,
                      &v104,
                      &v103,
                      &v107,
                      v102,
                      1,
                      (unsigned int *)&v105);
                    if ( *(char *)(*(_QWORD *)(a1 + 48) + 68LL) >= 0 )
                    {
                      StringCchPrintfA(
                        pszDest,
                        0x100u,
                        "{5{pop}repeat 0 -1 %ld %ld div %ld %ld div}bind",
                        v104,
                        v101,
                        v103,
                        v101);
                    }
                    else if ( v103 == v105 )
                    {
                      StringCchPrintfA(pszDest, 0x100u, "true");
                    }
                    else
                    {
                      StringCchPrintfA(pszDest, 0x100u, "%ld %ld sub %ld div", v103, v105, v101);
                    }
                    if ( !MinSfnt )
                    {
                      if ( pszDest[0] )
                      {
                        do
                          ++v23;
                        while ( pszDest[v23] );
                        v91 = StrmPutBytes(v12, (__int64)pszDest, v23, 1);
                      }
                      else
                      {
                        v91 = 0;
                      }
                      MinSfnt = v91;
                    }
                    StringCchPrintfA(pszDest, 0x100u, " /%s hfDef42CID", v88);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(pszDest, 0x100u, "/%s%s /%s hfDefRT42CID", *(const char **)(a1 + 56), "CIDR", v88);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s /%s%s] composefont pop",
                      *(const char **)(a1 + 56),
                      v80,
                      v88,
                      gcidSuffix[0],
                      *(const char **)(a1 + 56),
                      "CIDR");
                  }
                  else if ( v87 > 0x7F00 )
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "%lu dup 1 sub %lu IDStr2 /%s%s /%s%s T42CIDCP32K",
                      v87 - 32512,
                      32512,
                      (const char *)(v6 + 150),
                      "CID32K",
                      (const char *)(v6 + 150),
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s T42CIDCPR",
                      (const char *)(v6 + 150),
                      "CIDR",
                      (const char *)(v6 + 150),
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s T42CIDCPR",
                      (const char *)(v6 + 150),
                      "CID32KR",
                      (const char *)(v6 + 150),
                      "CID32K");
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s ",
                      *(const char **)(a1 + 56),
                      v80,
                      (const char *)(v6 + 150),
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s /%s%s] composefont pop",
                      v6 + 150,
                      "CIDR",
                      v6 + 150,
                      "CID32K",
                      v6 + 150,
                      "CID32KR");
                  }
                  else
                  {
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s%s /%s%s T42CIDCPR",
                      (const char *)(v6 + 150),
                      "CIDR",
                      (const char *)(v6 + 150),
                      gcidSuffix[0]);
                    if ( !MinSfnt )
                      MinSfnt = StrmPutStringEOL(v12, pszDest);
                    StringCchPrintfA(
                      pszDest,
                      0x100u,
                      "/%s /%s [/%s%s /%s%s] composefont pop",
                      *(_QWORD *)(a1 + 56),
                      v80,
                      v6 + 150,
                      gcidSuffix[0],
                      v6 + 150,
                      "CIDR");
                  }
                  if ( !MinSfnt )
                    MinSfnt = StrmPutStringEOL(v12, pszDest);
                  if ( v80 )
                    (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v80 - 8,
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
                v93 = *(_QWORD *)(v6 + 416);
                if ( v93 )
                {
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                    v93 - 8,
                    *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  *(_QWORD *)(v6 + 416) = 0;
                }
                if ( MinSfnt )
                {
                  v94 = *(_QWORD *)(v6 + 408);
                  if ( v94 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v94 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  v95 = *(_QWORD *)(v6 + 424);
                  *(_QWORD *)(v6 + 408) = 0;
                  if ( v95 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v95 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  v96 = *(_QWORD *)(v6 + 432);
                  *(_QWORD *)(v6 + 424) = 0;
                  if ( v96 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v96 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  v97 = *(_QWORD *)(v6 + 504);
                  *(_QWORD *)(v6 + 432) = 0;
                  if ( v97 )
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                      v97 - 8,
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
                  *(_QWORD *)(v6 + 504) = 0;
                }
                else
                {
                  *(_DWORD *)(a1 + 8) = 4 - (*(_DWORD *)(a1 + 8) != 2);
                }
                return MinSfnt;
              }
              v92 = v112;
              StringCchPrintfA(pszDest, 0x100u, "\n%%%%IncludeResource: font %s", v112);
              if ( !MinSfnt )
                MinSfnt = StrmPutStringEOL(v12, pszDest);
              StringCchPrintfA(pszDest, 0x100u, "/%s true /%s hfRedefFont", *(_QWORD *)(a1 + 56), v92);
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
          v57 = StrmPutBytes(v12, (__int64)" ", 1, 1);
          if ( v57 )
            goto LABEL_158;
          v60 = GetTableDirectoryOffset(v6, 1719233639);
          MinSfnt = StrmPutInt(v12, v60);
          if ( !MinSfnt )
          {
            MinSfnt = StrmPutStringEOL(v12, " ");
            if ( !MinSfnt )
            {
              MinSfnt = StrmPutStringEOL(v12, "PrepFor2015");
              if ( !MinSfnt )
              {
LABEL_276:
                if ( *(_QWORD *)(a1 + 160) && (v61 = *(_DWORD *)(a1 + 28), (v61 & 8) != 0)
                  || (MinSfnt = StrmPutStringEOL(v12, "AddFontInfoBegin"),
                      v61 = *(_DWORD *)(a1 + 28) | 1,
                      *(_DWORD *)(a1 + 28) = v61,
                      !MinSfnt) )
                {
                  if ( *(_QWORD *)(a1 + 160) && (v61 & 8) != 0
                    || (StringCchPrintfA(pszDest, 0x100u, "AddFontInfo"),
                        MinSfnt = StrmPutStringEOL(v12, pszDest),
                        v61 = *(_DWORD *)(a1 + 28) | 2,
                        *(_DWORD *)(a1 + 28) = v61,
                        !MinSfnt) )
                  {
                    if ( (v62 = v111, !*(_QWORD *)(v111 + 128))
                      || *(_QWORD *)(a1 + 160) && (v61 & 8) != 0
                      || (v63 = UFLNewPtr(*(_QWORD *)(a1 + 32), 0x3E8u), (v64 = v63) == 0)
                      || ((*(void (__fastcall **)(_QWORD, _DWORD *, __int64))(v62 + 128))(
                            *(_QWORD *)(a1 + 16),
                            v63,
                            1000),
                          MinSfnt = StrmPutStringEOL(v12, v64),
                          (*(void (__fastcall **)(_BYTE *, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
                            v64 - 8,
                            *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL)),
                          !MinSfnt) )
                    {
                      if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
                        goto LABEL_277;
                      OS2FSType = GetOS2FSType((_QWORD *)a1);
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
                          v66 = *(_QWORD *)(a1 + 48);
                          v67 = *(_DWORD *)(v66 + 16);
                          if ( v67 )
                          {
                            v68 = *(_DWORD **)(v66 + 24);
                            MinSfnt = StrmPutBytes(v12, (__int64)"[", 1, 1);
                            do
                            {
                              StringCchPrintfA(pszDest, 0x100u, "16#%x ", *v68);
                              if ( !MinSfnt )
                              {
                                if ( pszDest[0] )
                                {
                                  v69 = -1;
                                  do
                                    ++v69;
                                  while ( pszDest[v69] );
                                  v70 = StrmPutBytes(v12, (__int64)pszDest, v69, 1);
                                }
                                else
                                {
                                  v70 = 0;
                                }
                                MinSfnt = v70;
                              }
                              ++v68;
                              --v67;
                            }
                            while ( v67 );
                            StringCchPrintfA(pszDest, 0x100u, "] AddXUID");
                            if ( !MinSfnt )
                            {
                              v57 = StrmPutStringEOL(v12, pszDest);
LABEL_158:
                              MinSfnt = v57;
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
        v22 = 0;
        goto LABEL_19;
      }
    }
  }
  return MinSfnt;
}

```

## disassembly

```asm
0x18003f09c  push    rbp
0x18003f09e  push    rbx
0x18003f09f  push    rsi
0x18003f0a0  push    rdi
0x18003f0a1  push    r12
0x18003f0a3  push    r13
0x18003f0a5  push    r14
0x18003f0a7  push    r15
0x18003f0a9  lea     rbp, [rsp-0B8h]
0x18003f0b1  sub     rsp, 1B8h
0x18003f0b8  mov     rax, cs:__security_cookie
0x18003f0bf  xor     rax, rsp
0x18003f0c2  mov     [rbp+0F0h+var_50], rax
0x18003f0c9  mov     rax, [rbp+0F0h+arg_20]
0x18003f0d0  xor     r12d, r12d
0x18003f0d3  mov     [rbp+0F0h+var_168], rax
0x18003f0d7  mov     rdi, rcx
0x18003f0da  mov     rax, [rcx+30h]
0x18003f0de  mov     r14, [rax+8]
0x18003f0e2  test    r14, r14
0x18003f0e5  jnz     short loc_18003F0F0
0x18003f0e7  lea     eax, [r14+2]
0x18003f0eb  jmp     loc_180040640
0x18003f0f0  mov     rdx, [rcx+28h]
0x18003f0f4  mov     ebx, 0Dh
0x18003f0f9  mov     [rbp+0F0h+var_170], rdx
0x18003f0fd  mov     rcx, [rdx+0A0h]
0x18003f104  mov     rax, [rcx+8]
0x18003f108  test    rax, rax
0x18003f10b  jz      loc_18004063D
0x18003f111  mov     rsi, [rdx+0A8h]
0x18003f118  lea     edx, [rbx-0Ah]
0x18003f11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f120  test    al, al
0x18003f122  jz      loc_18004063D
0x18003f128  mov     eax, [rdi+4]
0x18003f12b  sub     eax, ebx
0x18003f12d  cmp     eax, 1
0x18003f130  ja      short loc_18003F151
0x18003f132  mov     rax, [rdi+28h]
0x18003f136  lea     edx, [rbx-9]
0x18003f139  mov     rcx, [rax+0A0h]
0x18003f140  mov     rax, [rcx+8]
0x18003f144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f149  test    al, al
0x18003f14b  jz      loc_18004063D
0x18003f151  mov     eax, 2
0x18003f156  mov     [rsp+1F0h+var_1A0], r12d
0x18003f15b  mov     ebx, r12d
0x18003f15e  mov     [rsp+1F0h+var_190], r12d
0x18003f163  mov     r13, r12
0x18003f166  mov     qword ptr [rsp+1F0h+var_180], r12
0x18003f16b  cmp     [rdi+8], eax
0x18003f16e  jz      loc_18003F66A
0x18003f174  xor     edx, edx
0x18003f176  mov     rcx, rdi
0x18003f179  call    GetMinSfnt
0x18003f17e  movzx   ebx, ax
0x18003f181  cmp     r12w, ax
0x18003f185  jnz     loc_18003F22D
0x18003f18b  mov     rcx, rdi
0x18003f18e  call    FillInHeadTable
0x18003f193  movzx   ebx, ax
0x18003f196  cmp     r12w, ax
0x18003f19a  jnz     loc_18003F22D
0x18003f1a0  mov     rcx, rdi
0x18003f1a3  call    GetNumGlyphs
0x18003f1a8  mov     rdx, [r14+1A0h]
0x18003f1af  mov     r8d, 61636F6Ch
0x18003f1b5  mov     rcx, rdi
0x18003f1b8  mov     [r14+0Ch], eax
0x18003f1bc  call    GetTableSize
0x18003f1c1  mov     r15d, eax
0x18003f1c4  test    eax, eax
0x18003f1c6  jz      short loc_18003F228
0x18003f1c8  cmp     [r14+1EAh], r12w
0x18003f1d0  mov     r12d, eax
0x18003f1d3  mov     edx, [r14+0Ch]
0x18003f1d7  lea     ecx, ds:2[rdx*2]
0x18003f1de  lea     ebx, ds:4[rdx*4]
0x18003f1e5  cmovz   ebx, ecx
0x18003f1e8  mov     rcx, [rdi+20h]
0x18003f1ec  cmp     ebx, eax
0x18003f1ee  cmova   r12d, ebx
0x18003f1f2  mov     edx, r12d
0x18003f1f5  call    UFLNewPtr
0x18003f1fa  mov     [r14+1B0h], rax
0x18003f201  test    rax, rax
0x18003f204  jz      loc_18003F72B
0x18003f20a  mov     r9d, r12d
0x18003f20d  mov     r8, rax
0x18003f210  mov     edx, 61636F6Ch
0x18003f215  mov     rcx, rdi
0x18003f218  call    GetFontTable
0x18003f21d  xor     r12d, r12d
0x18003f220  test    eax, eax
0x18003f222  jnz     loc_18003F370
0x18003f228  mov     ebx, 0Eh
0x18003f22d  mov     r15d, r12d
0x18003f230  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003f234  cmp     dword ptr [rdi+8], 2
0x18003f238  jz      loc_18003FCE0
0x18003f23e  xor     eax, eax
0x18003f240  cmp     ax, bx
0x18003f243  jnz     loc_18003F8C2
0x18003f249  mov     eax, [rdi+4]
0x18003f24c  sub     eax, 0Dh
0x18003f24f  cmp     eax, 3
0x18003f252  ja      loc_18003F8C2
0x18003f258  cmp     qword ptr [rdi+0A0h], 0
0x18003f260  jz      short loc_18003F26C
0x18003f262  test    byte ptr [rdi+1Ch], 8
0x18003f266  jnz     loc_18003F8C2
0x18003f26c  movsx   eax, word ptr [r13+4Ch]
0x18003f271  lea     rcx, [r13+38h]
0x18003f275  lea     r9, [r13+24h]
0x18003f279  mov     [rsp+1F0h+var_1C8], eax
0x18003f27d  mov     [rsp+1F0h+var_1D0], rcx
0x18003f282  lea     r8, aSSD; "(%s) (%s) %d"
0x18003f289  mov     r13d, 100h
0x18003f28f  lea     rcx, [rbp+0F0h+pszDest]; pszDest
0x18003f293  mov     edx, r13d; cchDest
0x18003f296  call    StringCchPrintfA
0x18003f29b  lea     rdx, [rbp+0F0h+pszDest]
0x18003f29f  mov     rcx, rsi
0x18003f2a2  call    StrmPutStringEOL
0x18003f2a7  movzx   ebx, ax
0x18003f2aa  lea     r8, aLu_0; "%lu"
0x18003f2b1  mov     eax, 7F00h
0x18003f2b6  lea     rcx, [rbp+0F0h+pszDest]; pszDest
0x18003f2ba  cmp     r15d, eax
0x18003f2bd  mov     r9d, eax
0x18003f2c0  mov     edx, r13d; cchDest
0x18003f2c3  cmovb   r9d, r15d
0x18003f2c7  call    StringCchPrintfA
0x18003f2cc  xor     r13d, r13d
0x18003f2cf  cmp     r13w, bx
0x18003f2d3  jnz     short loc_18003F2E4
0x18003f2d5  lea     rdx, [rbp+0F0h+pszDest]
0x18003f2d9  mov     rcx, rsi
0x18003f2dc  call    StrmPutStringEOL
0x18003f2e1  movzx   ebx, ax
0x18003f2e4  mov     rax, [rbp+0F0h+var_170]
0x18003f2e8  mov     rax, [rax+60h]
0x18003f2ec  test    rax, rax
0x18003f2ef  jz      loc_18003F76C
0x18003f2f5  mov     rcx, [rdi+10h]
0x18003f2f9  xor     r8d, r8d
0x18003f2fc  xor     edx, edx
0x18003f2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f303  mov     r13d, eax
0x18003f306  test    eax, eax
0x18003f308  jz      loc_18003F769
0x18003f30e  mov     rcx, [rdi+20h]
0x18003f312  mov     edx, eax
0x18003f314  call    UFLNewPtr
0x18003f319  mov     r15, rax
0x18003f31c  test    rax, rax
0x18003f31f  jz      loc_18003F7C9
0x18003f325  mov     rcx, [rdi+10h]
0x18003f329  mov     rdx, rax
0x18003f32c  mov     rax, [rbp+0F0h+var_170]
0x18003f330  mov     r8d, r13d
0x18003f333  mov     rax, [rax+60h]
0x18003f337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f33c  xor     r13d, r13d
0x18003f33f  cmp     r13w, bx
0x18003f343  jnz     short loc_18003F356
0x18003f345  mov     r9b, 1
0x18003f348  mov     r8d, eax
0x18003f34b  mov     rdx, r15
0x18003f34e  mov     rcx, rsi
0x18003f351  call    StrmPutBytes
0x18003f356  mov     rax, [rdi+20h]
0x18003f35a  lea     rcx, [r15-8]
0x18003f35e  mov     rdx, [rax+20h]
0x18003f362  mov     rax, [rax+8]
0x18003f366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f36b  jmp     loc_18003F7CC
0x18003f370  cmp     ebx, r15d
0x18003f373  jbe     loc_18003F43F
0x18003f379  mov     rdx, [r14+1A0h]
0x18003f380  mov     r8d, 66796C67h
0x18003f386  mov     rcx, rdi
0x18003f389  call    GetTableSize
0x18003f38e  mov     r8, [r14+1B0h]
0x18003f395  mov     r9d, eax
0x18003f398  mov     eax, [r14+0Ch]
0x18003f39c  dec     eax
0x18003f39e  cmp     [r14+1EAh], r12w
0x18003f3a6  jz      short loc_18003F40C
0x18003f3a8  lea     ecx, ds:0[rax*4]
0x18003f3af  movzx   edx, byte ptr [rcx+r8+1]
0x18003f3b5  mov     r10d, ecx
0x18003f3b8  movzx   ecx, byte ptr [rcx+r8]
0x18003f3bd  shl     ecx, 8
0x18003f3c0  add     edx, ecx
0x18003f3c2  mov     ecx, r9d
0x18003f3c5  movzx   eax, byte ptr [r10+r8+2]
0x18003f3cb  shl     edx, 8
0x18003f3ce  add     edx, eax
0x18003f3d0  movzx   eax, byte ptr [r10+r8+3]
0x18003f3d6  shl     edx, 8
0x18003f3d9  sub     ecx, edx
0x18003f3db  sub     ecx, eax
0x18003f3dd  cmp     ecx, 1001h
0x18003f3e3  jnb     short loc_18003F43F
0x18003f3e5  lea     rcx, [r10+r8]
0x18003f3e9  mov     eax, r9d
0x18003f3ec  shr     eax, 18h
0x18003f3ef  mov     [r10+r8+4], al
0x18003f3f4  mov     eax, r9d
0x18003f3f7  shr     eax, 10h
0x18003f3fa  mov     [rcx+5], al
0x18003f3fd  mov     eax, r9d
0x18003f400  shr     eax, 8
0x18003f403  mov     [rcx+6], al
0x18003f406  mov     [rcx+7], r9b
0x18003f40a  jmp     short loc_18003F43F
0x18003f40c  add     eax, eax
0x18003f40e  mov     r10d, eax
0x18003f411  movzx   ecx, byte ptr [rax+r8+1]
0x18003f417  movzx   eax, byte ptr [rax+r8]
0x18003f41c  imul    edx, eax, 0FFFFFF00h
0x18003f422  sub     edx, ecx
0x18003f424  add     edx, r9d
0x18003f427  cmp     edx, 1001h
0x18003f42d  jnb     short loc_18003F43F
0x18003f42f  mov     eax, r9d
0x18003f432  mov     [r10+r8+3], r9b
0x18003f437  shr     eax, 8
0x18003f43a  mov     [r10+r8+2], al
0x18003f43f  mov     rax, [rdi+30h]
0x18003f443  mov     r8d, 66796C67h
0x18003f449  mov     ebx, [r14]
0x18003f44c  mov     rcx, rdi
0x18003f44f  mov     rdx, [rax+8]
0x18003f453  mov     rdx, [rdx+198h]
0x18003f45a  call    GetTableSize
0x18003f45f  lea     ecx, [rbx+rax]
0x18003f462  mov     eax, 80041h
0x18003f467  mul     ecx
0x18003f469  mov     eax, 280h
0x18003f46e  sub     ecx, edx
0x18003f470  shr     ecx, 1
0x18003f472  add     ecx, edx
0x18003f474  shr     ecx, 0Dh
0x18003f477  lea     ecx, [rcx+rcx*4]
0x18003f47a  shr     ecx, 2
0x18003f47d  cmp     ecx, eax
0x18003f47f  cmova   eax, ecx
0x18003f482  mov     rcx, [rdi+20h]
0x18003f486  lea     r15d, [rax+1]
0x18003f48a  lea     edx, ds:0[r15*4]
0x18003f492  mov     [rsp+1F0h+var_190], r15d
0x18003f497  call    UFLNewPtr
0x18003f49c  mov     [r14+1A8h], rax
0x18003f4a3  test    rax, rax
0x18003f4a6  jz      loc_18003F721
0x18003f4ac  mov     r8d, r15d
0x18003f4af  mov     rdx, r14
0x18003f4b2  mov     rcx, rdi
0x18003f4b5  call    CalculateStringLength
0x18003f4ba  cmp     r12w, ax
0x18003f4be  jnz     loc_18003F719
0x18003f4c4  cmp     [rdi+0A0h], r12
0x18003f4cb  jz      short loc_18003F4DB
0x18003f4cd  test    byte ptr [rdi+1Ch], 8
0x18003f4d1  jz      short loc_18003F4DB
0x18003f4d3  movzx   ebx, ax
0x18003f4d6  jmp     loc_18003F5BB
0x18003f4db  movsx   edx, word ptr [r14+1CAh]
0x18003f4e3  cmp     r12w, dx
0x18003f4e7  jz      loc_18003F228
0x18003f4ed  movsx   eax, word ptr [r14+1E2h]
0x18003f4f5  test    eax, eax
0x18003f4f7  jle     short loc_18003F4FD
0x18003f4f9  inc     eax
0x18003f4fb  jmp     short loc_18003F501
0x18003f4fd  jns     short loc_18003F501
0x18003f4ff  dec     eax
0x18003f501  movsx   r8d, word ptr [r14+1E0h]
0x18003f509  test    r8d, r8d
0x18003f50c  jle     short loc_18003F513
0x18003f50e  inc     r8d
0x18003f511  jmp     short loc_18003F518
0x18003f513  jns     short loc_18003F518
0x18003f515  dec     r8d
0x18003f518  movsx   ecx, word ptr [r14+1DEh]
0x18003f520  test    ecx, ecx
0x18003f522  jle     short loc_18003F528
0x18003f524  dec     ecx
0x18003f526  jmp     short loc_18003F52C
0x18003f528  jns     short loc_18003F52C
0x18003f52a  inc     ecx
0x18003f52c  movsx   r11d, word ptr [r14+1DCh]
0x18003f534  test    r11d, r11d
0x18003f537  jle     short loc_18003F53E
0x18003f539  dec     r11d
0x18003f53c  jmp     short loc_18003F543
  ... truncated ...
```

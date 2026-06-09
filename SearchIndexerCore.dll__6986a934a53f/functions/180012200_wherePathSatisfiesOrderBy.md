# wherePathSatisfiesOrderBy

- ea: `0x180012200`
- end: `0x180012fcb`
- name: `wherePathSatisfiesOrderBy`
- size: `3531`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18004eae8`

## callees

- `0x18000a710`
- `0x18000e13c`
- `0x180010100`
- `0x1800117a0`
- `0x180011948`
- `0x180011a10`
- `0x180011bcc`
- `0x180012200`
- `0x180012fd4`
- `0x180013210`
- `0x180014650`
- `0x180018be0`
- `0x18001e4a0`
- `0x180052d60`
- `0x180078968`
- `0x1800789c0`

## pseudocode

```c
char __fastcall wherePathSatisfiesOrderBy(
        __int64 **a1,
        unsigned __int64 a2,
        __int64 a3,
        __int16 a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 *a7)
{
  __int64 *v7; // rbx
  __int16 v8; // bp
  __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 **v11; // r11
  __int16 v12; // r10
  _BYTE *v13; // r8
  __int64 v14; // r9
  unsigned __int64 v15; // r14
  __int64 v16; // r12
  __int64 v17; // r15
  int v18; // r13d
  unsigned __int64 v19; // rax
  unsigned __int16 v20; // r10
  int v21; // ecx
  bool v22; // zf
  unsigned int v23; // ecx
  unsigned int j; // esi
  _BYTE *v25; // r15
  __int64 v26; // rdi
  int v27; // eax
  __int64 v28; // r11
  unsigned __int16 v29; // cx
  char v30; // r13
  int v31; // eax
  int v32; // edi
  char v33; // r12
  int v34; // esi
  unsigned int n; // r15d
  char v36; // bl
  _BYTE *v37; // r13
  unsigned __int8 v38; // al
  __int64 v40; // rcx
  unsigned __int16 v41; // ax
  __int64 v42; // rcx
  unsigned int v43; // ebx
  int i; // ecx
  __int64 v45; // rdx
  int m; // r9d
  __int64 v47; // rdi
  __int64 v48; // rsi
  unsigned __int8 *v49; // rbx
  int *v50; // r10
  int v51; // r11d
  __int64 *v52; // r10
  _BYTE *v53; // r8
  unsigned __int8 *kk; // r9
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rdx
  _QWORD *v58; // rbx
  unsigned __int8 *nn; // r9
  __int64 v60; // rax
  unsigned __int8 v61; // al
  unsigned int v62; // eax
  _DWORD *v63; // r10
  __int64 v64; // r11
  __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  __int16 v68; // dx
  const char *v69; // rdi
  __int64 v70; // rsi
  int *v71; // r10
  int v72; // r11d
  __int64 *v73; // r10
  _BYTE *v74; // r8
  const char *mm; // r9
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 CollSeq; // rax
  unsigned int v80; // eax
  _DWORD *v81; // r10
  __int64 v82; // r11
  __int64 ii; // r8
  int v84; // eax
  bool v85; // zf
  int v86; // eax
  __int64 v87; // rdx
  __int64 *v88; // r14
  __int64 v89; // rbp
  char *v90; // rax
  char v91; // al
  int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // r8
  _DWORD *v95; // rcx
  int i1; // edx
  __int64 v97; // rax
  int v98; // eax
  __int64 v99; // rbp
  __int16 v100; // cx
  __int64 k; // r14
  __int64 v102; // rcx
  __int16 v103; // ax
  __int64 v104; // rcx
  _QWORD *v105; // rdi
  _QWORD *v106; // rax
  int v107; // eax
  _BYTE *jj; // rax
  unsigned __int8 v109; // [rsp+20h] [rbp-158h]
  int v111; // [rsp+24h] [rbp-154h]
  unsigned __int8 v112; // [rsp+28h] [rbp-150h]
  char v113; // [rsp+29h] [rbp-14Fh]
  unsigned int v114; // [rsp+2Ch] [rbp-14Ch]
  unsigned __int16 v115; // [rsp+30h] [rbp-148h]
  __int64 v116; // [rsp+38h] [rbp-140h]
  unsigned __int64 v117; // [rsp+40h] [rbp-138h]
  _BYTE *v118; // [rsp+48h] [rbp-130h]
  char v120; // [rsp+58h] [rbp-120h]
  int v121; // [rsp+5Ch] [rbp-11Ch]
  __int16 v122; // [rsp+60h] [rbp-118h]
  int v123; // [rsp+64h] [rbp-114h]
  int v124; // [rsp+68h] [rbp-110h]
  int v125; // [rsp+6Ch] [rbp-10Ch]
  unsigned __int16 v126; // [rsp+70h] [rbp-108h]
  __int64 v127; // [rsp+78h] [rbp-100h]
  __int64 v128; // [rsp+80h] [rbp-F8h]
  __int64 v129; // [rsp+88h] [rbp-F0h]
  __int16 v130; // [rsp+90h] [rbp-E8h]
  int v131; // [rsp+94h] [rbp-E4h]
  unsigned __int64 v133; // [rsp+B8h] [rbp-C0h]
  _QWORD v134[4]; // [rsp+C0h] [rbp-B8h] BYREF
  int v135; // [rsp+E0h] [rbp-98h]
  int v136; // [rsp+E4h] [rbp-94h]
  __int16 v137; // [rsp+E8h] [rbp-90h]
  char v138; // [rsp+EAh] [rbp-8Eh]
  unsigned int v139; // [rsp+ECh] [rbp-8Ch]
  __int16 v140; // [rsp+118h] [rbp-60h]

  LODWORD(v7) = a5;
  v8 = a4;
  v9 = a6;
  v10 = a3;
  v11 = a1;
  v118 = (_BYTE *)a2;
  if ( a5 && (*(_BYTE *)(**a1 + 96) & 0x40) != 0 )
    return 0;
  v122 = *(_WORD *)a2;
  v12 = *(_WORD *)a2;
  if ( *(unsigned __int16 *)a2 > 0x3Fu )
    return 0;
  v13 = (_BYTE *)a2;
  v14 = 0;
  v121 = *(unsigned __int16 *)a2;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v117 = 0;
  v18 = v121;
  v127 = 0;
  v128 = 0;
  LOBYTE(a2) = 1;
  v19 = (1LL << v12) - 1;
  v111 = a2;
  v133 = v19;
  v20 = ((v8 & 0x803) != 0) + 386;
  v115 = v20;
  v21 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v123 = v21;
      if ( !(_BYTE)a2 )
      {
        v22 = v15 == v19;
LABEL_54:
        if ( v22 )
          return v122;
        if ( (_BYTE)a2 )
          return -1;
        for ( i = v18 - 1; i > 0; --i )
        {
          if ( i >= 64 )
            v45 = 0;
          else
            v45 = (1LL << i) - 1;
          if ( (v15 & v45) == v45 )
            return i;
        }
        return 0;
      }
      v22 = v15 == v19;
      if ( v15 >= v19 )
        goto LABEL_54;
      if ( v21 > (unsigned __int16)v7 )
        return -1;
      if ( v21 > 0 )
      {
        v17 |= *(_QWORD *)(v14 + 8);
        v128 = v17;
      }
      if ( v21 >= (unsigned __int16)v7 )
      {
        v14 = v9;
        v116 = v9;
        break;
      }
      v14 = *(_QWORD *)(*(_QWORD *)(v10 + 24) + 8LL * v21);
      v116 = v14;
      if ( (v8 & 0x800) == 0 )
        break;
      v19 = v133;
      ++v21;
    }
    if ( (*(_DWORD *)(v14 + 56) & 0x400) != 0 )
      break;
    v130 = v8 & 0x80;
    if ( (v8 & 0x80) != 0 )
      *(_WORD *)(v14 + 30) = 0;
    v23 = HIDWORD(v11[1][13 * *(unsigned __int8 *)(v14 + 16) + 9]);
    v114 = v23;
    if ( v18 )
    {
      for ( j = 0; (int)j < v18; ++j )
      {
        if ( !_bittest64((const __int64 *)&v15, j) )
        {
          v25 = &v13[32 * j];
          v26 = *((_QWORD *)v25 + 1);
          if ( v26 )
          {
            while ( 1 )
            {
              v98 = *(_DWORD *)(v26 + 4);
              if ( (v98 & 0x82000) == 0 )
                break;
              if ( (v98 & 0x80000) != 0 )
              {
                v26 = *(_QWORD *)(*(_QWORD *)(v26 + 32) + 8LL);
              }
              else
              {
                if ( *(_BYTE *)v26 != 113 )
                  break;
                v26 = *(_QWORD *)(v26 + 16);
              }
              if ( !v26 )
                goto LABEL_18;
            }
            if ( ((*(_BYTE *)v26 + 89) & 0xFD) == 0 && *(_DWORD *)(v26 + 44) == v23 )
            {
              v7 = (__int64 *)(v11 + 14);
              v99 = 0;
              memset_0(v134, 0, 0x70u);
              v100 = *(_WORD *)(v26 + 48);
              v136 = v115;
              v139 = v114;
              v134[0] = v7;
              v134[1] = v7;
              v134[3] = 0;
              v137 = 256;
              v134[2] = 0;
              v135 = 0;
              v138 = 1;
              if ( v100 != -2 )
              {
                v140 = v100;
                goto LABEL_228;
              }
              for ( k = 0; k; k = whereScanNext(v134) )
              {
                v102 = *(_QWORD *)(k + 40);
                if ( (~v128 & v102) == 0 )
                {
                  if ( !v102 && (*(_BYTE *)(k + 20) & 0x82) != 0 )
                    goto LABEL_240;
                  if ( !v99 )
                    v99 = k;
                }
LABEL_228:
                ;
              }
              k = v99;
              if ( !v99 )
              {
LABEL_231:
                v14 = v116;
LABEL_232:
                v15 = v117;
                v11 = a1;
                v23 = v114;
                v13 = v118;
                continue;
              }
LABEL_240:
              v103 = *(_WORD *)(k + 20);
              if ( v103 == 1 )
              {
                v14 = v116;
                if ( !*(_WORD *)(v116 + 60) )
                  goto LABEL_232;
                v104 = 0;
                while ( k != *(_QWORD *)(*(_QWORD *)(v116 + 72) + 8 * v104) )
                {
                  v104 = (unsigned int)(v104 + 1);
                  if ( (int)v104 >= *(unsigned __int16 *)(v116 + 60) )
                    goto LABEL_232;
                }
              }
              else if ( (v103 & 0x82) != 0 && *(__int16 *)(v26 + 48) >= 0 )
              {
                v7 = *a1;
                v105 = (_QWORD *)sqlite3ExprNNCollSeq(*a1, *((_QWORD *)v25 + 1));
                v106 = (_QWORD *)sqlite3ExprCompareCollSeq(v7, *(_QWORD *)k);
                if ( !v106 )
                  goto LABEL_231;
                v107 = sqlite3StrICmp(*v105, *v106);
                v14 = v116;
                if ( v107 )
                  goto LABEL_232;
              }
              else
              {
                v14 = v116;
              }
              v15 = v117;
              v11 = a1;
              _bittestandset64((__int64 *)&v15, j);
              v23 = v114;
              v13 = v118;
              v117 = v15;
            }
          }
        }
LABEL_18:
        ;
      }
      LODWORD(a2) = v111;
      v8 = a4;
      v20 = v115;
      v16 = v127;
    }
    v27 = *(_DWORD *)(v14 + 56);
    if ( (v27 & 0x1000) != 0 )
      goto LABEL_73;
    if ( (v27 & 0x100) != 0 )
    {
      LODWORD(v7) = v111;
      v28 = 0;
      v129 = 0;
      v29 = 1;
      v126 = 0;
    }
    else
    {
      v28 = *(_QWORD *)(v14 + 32);
      v129 = v28;
      if ( !v28 || (*(_BYTE *)(v28 + 100) & 4) != 0 )
        return 0;
      LODWORD(a2) = *(unsigned __int16 *)(v28 + 94);
      v29 = *(_WORD *)(v28 + 96);
      v126 = *(_WORD *)(v28 + 94);
      LOBYTE(v7) = *(_BYTE *)(v28 + 98) && (v27 & 0x8000) == 0;
      v111 = (int)v7;
    }
    v30 = 0;
    v31 = v29;
    v120 = 0;
    v32 = 0;
    v131 = v29;
    v113 = 0;
    v112 = 0;
    while ( 1 )
    {
LABEL_28:
      v125 = v32;
      if ( v32 >= v31 )
        goto LABEL_48;
      LODWORD(a2) = *(unsigned __int16 *)(v14 + 24);
      v33 = 1;
      if ( v32 >= (int)a2 || v32 < *(unsigned __int16 *)(v14 + 62) )
        break;
      v13 = *(_BYTE **)(v14 + 72);
      v40 = *(_QWORD *)&v13[8 * v32];
      v41 = *(_WORD *)(v40 + 20);
      if ( (v41 & v20) == 0 )
      {
        if ( (v41 & 1) != 0 )
        {
          for ( m = v32 + 1; m < (int)a2; ++m )
          {
            if ( **(_QWORD **)&v13[8 * m] == *(_QWORD *)v40 )
            {
              v33 = 0;
              goto LABEL_30;
            }
          }
        }
        break;
      }
      if ( (v41 & 0x180) == 0 )
        goto LABEL_67;
      v31 = v131;
      LOBYTE(v7) = 0;
      v111 = (int)v7;
      ++v32;
    }
LABEL_30:
    if ( v28 )
    {
      v34 = *(__int16 *)(*(_QWORD *)(v28 + 8) + 2LL * v32);
      v109 = *(_BYTE *)(v32 + *(_QWORD *)(v28 + 56)) & 1;
      if ( v34 == *(__int16 *)(*(_QWORD *)(v28 + 24) + 52LL) )
        v34 = -1;
    }
    else
    {
      v34 = -1;
      v109 = 0;
    }
    v124 = v34;
    if ( (_BYTE)v7 )
    {
      if ( v34 < 0 )
      {
        LODWORD(v7) = (unsigned __int8)v7;
        if ( v34 == -2 )
          LODWORD(v7) = 0;
        v111 = (int)v7;
      }
      else if ( v32 >= (int)a2 )
      {
        LODWORD(a2) = 3 * v34;
        if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v28 + 24) + 8LL) + 24LL * v34 + 8) & 0xF) == 0 )
          LOBYTE(v111) = 0;
      }
    }
    for ( n = 0; v33 && (int)n < v121; ++n )
    {
      if ( _bittest64((const __int64 *)&v15, n) )
        continue;
      v36 = n;
      v37 = &v118[32 * n];
      a2 = *((_QWORD *)v37 + 1);
      if ( !a2 )
        continue;
      while ( 1 )
      {
        v86 = *(_DWORD *)(a2 + 4);
        if ( (v86 & 0x82000) == 0 )
          break;
        if ( (v86 & 0x80000) != 0 )
        {
          a2 = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 8LL);
        }
        else
        {
          if ( *(_BYTE *)a2 != 113 )
            break;
          a2 = *(_QWORD *)(a2 + 16);
        }
        if ( !a2 )
          goto LABEL_43;
      }
      v8 = a4;
      if ( (a4 & 0xC0) == 0 )
        v33 = 0;
      if ( v34 < -1 )
      {
        for ( ii = *(_QWORD *)(32LL * v32 + *(_QWORD *)(v28 + 80) + 8); ii; ii = *(_QWORD *)(ii + 16) )
        {
          if ( (*(_DWORD *)(ii + 4) & 0x2000) == 0 )
            break;
        }
        do
        {
          if ( (*(_DWORD *)(a2 + 4) & 0x2000) == 0 )
            break;
          a2 = *(_QWORD *)(a2 + 16);
        }
        while ( a2 );
        v84 = sqlite3ExprCompare(0, a2, ii, v114);
        v28 = v129;
        v85 = v84 == 0;
LABEL_185:
        if ( !v85 )
          continue;
        if ( v34 != -1 )
        {
          v58 = 0;
          v87 = *((_QWORD *)v37 + 1);
          v88 = *a1;
          v89 = **a1;
          while ( 1 )
          {
            if ( !v87 )
              goto LABEL_124;
            v90 = (char *)(*(_BYTE *)v87 == 0xB0 ? v87 + 2 : v87);
            v91 = *v90;
            if ( v91 == -87 )
              break;
            if ( v91 == -89 )
              goto LABEL_145;
            if ( v91 == 36 )
              goto LABEL_211;
            if ( v91 == 77 )
            {
LABEL_145:
              v65 = *(__int16 *)(v87 + 48);
              if ( (v65 & 0x8000u) == 0LL )
              {
                v66 = 3 * v65;
                v67 = *(_QWORD *)(*(_QWORD *)(v87 + 64) + 8LL);
                v68 = *(_WORD *)(v67 + 8 * v66 + 18);
                if ( (v68 & 0x200) == 0 )
                  goto LABEL_147;
                for ( jj = *(_BYTE **)(v67 + 8 * v66); *jj; ++jj )
                  ;
                if ( (v68 & 4) != 0 )
                {
                  do
                    ++jj;
                  while ( *jj );
                }
                v49 = jj + 1;
                if ( jj == (_BYTE *)-1LL )
                {
LABEL_147:
                  v58 = *(_QWORD **)(v89 + 16);
                }
                else
                {
                  v50 = (int *)(v89 + 624);
                  if ( *(_QWORD *)(v89 + 640) )
                  {
                    v62 = strHash(jj + 1);
                    v50 = (int *)(v64 + 16LL * (v62 % *v63));
                    v51 = *v50;
                  }
                  else
                  {
                    v51 = *(_DWORD *)(v89 + 628);
                  }
                  v52 = (__int64 *)*((_QWORD *)v50 + 1);
LABEL_114:
                  if ( v51 )
                  {
                    v53 = (_BYTE *)v52[3];
                    for ( kk = v49; ; ++kk )
                    {
                      v55 = (unsigned __int8)*v53;
                      v56 = *kk;
                      if ( (_DWORD)v55 == (_DWORD)v56 )
                      {
                        if ( !*v53 )
                          goto LABEL_120;
                      }
                      else if ( *((unsigned __int8 *)qword_1800B4ED0 + v55) != *((unsigned __int8 *)qword_1800B4ED0 + v56) )
                      {
                        v52 = (__int64 *)*v52;
                        --v51;
                        goto LABEL_114;
                      }
                      ++v53;
                    }
                  }
                  v52 = qword_1800D0DC0;
LABEL_120:
                  v57 = v52[2];
                  if ( v57 )
                    v58 = (_QWORD *)(v57 + 40 * (*(unsigned __int8 *)(v89 + 100) - 1LL));
                  else
                    v58 = 0;
                }
                goto LABEL_122;
              }
              goto LABEL_124;
            }
            if ( v91 == -83 )
            {
LABEL_211:
              v87 = *(_QWORD *)(v87 + 16);
            }
            else if ( v91 == -79 )
            {
              v87 = *(_QWORD *)(*(_QWORD *)(v87 + 32) + 8LL);
            }
            else
            {
              if ( v91 == 113 )
              {
                v69 = *(const char **)(v87 + 8);
                v70 = *(unsigned __int8 *)(v89 + 100);
                if ( v69 )
                {
                  v71 = (int *)(v89 + 624);
                  if ( *(_QWORD *)(v89 + 640) )
                  {
                    v80 = strHash(v69);
                    v71 = (int *)(v82 + 16LL * (v80 % *v81));
                    v72 = *v71;
                  }
                  else
                  {
                    v72 = *(_DWORD *)(v89 + 628);
                  }
                  v73 = (__int64 *)*((_QWORD *)v71 + 1);
LABEL_152:
                  if ( v72 )
                  {
                    v74 = (_BYTE *)v73[3];
                    for ( mm = v69; ; ++mm )
                    {
                      v76 = (unsigned __int8)*v74;
                      v77 = *(unsigned __int8 *)mm;
                      if ( (_DWORD)v76 == (_DWORD)v77 )
                      {
                        if ( !*v74 )
                          goto LABEL_158;
                      }
                      else if ( *((unsigned __int8 *)qword_1800B4ED0 + v76) != *((unsigned __int8 *)qword_1800B4ED0 + v77) )
                      {
                        v73 = (__int64 *)*v73;
                        --v72;
                        goto LABEL_152;
                      }
                      ++v74;
                    }
                  }
                  v73 = qword_1800D0DC0;
LABEL_158:
                  v78 = v73[2];
                  if ( v78 )
                    v58 = (_QWORD *)(v78 + 40 * (v70 - 1));
                  else
                    v58 = 0;
                }
                else
                {
                  v58 = *(_QWORD **)(v89 + 16);
                }
                if ( !v58 || !v58[3] )
                {
                  callCollNeeded(v89, (unsigned int)v70, v69);
                  CollSeq = sqlite3FindCollSeq(v89, (unsigned __int8)v70, v69, 0);
                  v58 = (_QWORD *)CollSeq;
                  if ( !CollSeq )
                    goto LABEL_163;
                  if ( !*(_QWORD *)(CollSeq + 24) && (unsigned int)synthCollSeq(v89, CollSeq) )
                  {
                    v58 = 0;
LABEL_163:
                    sqlite3ErrorMsg(v88, "no such collation sequence: %s", v69);
                    *((_DWORD *)v88 + 6) = 257;
                  }
                }
                v32 = v125;
                v34 = v124;
LABEL_122:
                if ( !v58 || !v58[3] && !sqlite3GetCollSeq(v88, *(unsigned __int8 *)(*v88 + 100), v58, *v58) )
                {
LABEL_125:
                  v58 = *(_QWORD **)(*v88 + 16);
                  goto LABEL_126;
                }
LABEL_124:
                if ( !v58 )
                  goto LABEL_125;
LABEL_126:
                v28 = v129;
                v13 = (_BYTE *)*v58;
                for ( nn = *(unsigned __int8 **)(*(_QWORD *)(v129 + 64) + 8LL * v32); ; ++nn )
                {
                  a2 = (unsigned __int8)*v13;
                  v60 = *nn;
                  if ( (_DWORD)a2 == (_DWORD)v60 )
                  {
                    if ( !*v13 )
                    {
                      v36 = n;
                      v15 = v117;
                      v8 = a4;
                      goto LABEL_133;
                    }
                  }
                  else if ( *((unsigned __int8 *)qword_1800B4ED0 + a2) != *((unsigned __int8 *)qword_1800B4ED0 + v60) )
                  {
                    v15 = v117;
                    goto LABEL_43;
                  }
                  ++v13;
                }
              }
LABEL_198:
              v92 = *(_DWORD *)(v87 + 4);
              if ( (v92 & 0x200) == 0 )
                goto LABEL_124;
              v93 = *(_QWORD *)(v87 + 16);
              if ( v93 && (*(_DWORD *)(v93 + 4) & 0x200) != 0 )
              {
                v87 = *(_QWORD *)(v87 + 16);
              }
              else
              {
                v94 = *(_QWORD *)(v87 + 24);
                if ( (v92 & 0x1000) == 0 )
                {
                  v95 = *(_DWORD **)(v87 + 32);
                  if ( v95 )
                  {
                    if ( !*(_BYTE *)(v89 + 103) )
                    {
                      for ( i1 = 0; i1 < *v95; ++i1 )
                      {
                        v97 = 8LL * i1;
                        if ( (*(_DWORD *)(*(_QWORD *)&v95[v97 + 2] + 4LL) & 0x200) != 0 )
                        {
                          v94 = *(_QWORD *)&v95[v97 + 2];
                          break;
                        }
                      }
                    }
                  }
                }
                v87 = v94;
              }
            }
          }
          if ( *(_QWORD *)(v87 + 64) )
            goto LABEL_145;
          goto LABEL_198;
        }
LABEL_133:
        v14 = v116;
        if ( v130 )
          *(_WORD *)(v116 + 30) = v32 + 1;
        if ( (v8 & 0x40) == 0 )
        {
          v61 = v37[24] & 1;
          if ( v113 )
          {
            if ( (v112 ^ v109) != v61 )
              goto LABEL_45;
          }
          else
          {
            v112 = v109 ^ v61;
            if ( v109 != v61 )
            {
              LODWORD(a2) = (_DWORD)a7;
              v42 = *a7;
              _bittestandset64(&v42, v123);
              *a7 = v42;
            }
            v113 = 1;
          }
        }
        if ( (v37[24] & 2) != 0 )
        {
          if ( v32 != *(unsigned __int16 *)(v116 + 24) )
            goto LABEL_45;
          *(_DWORD *)(v116 + 56) |= 0x80000u;
        }
        v20 = v115;
        v30 = v120;
        if ( v34 == -1 )
          v30 = 1;
        v15 |= 1LL << v36;
        LODWORD(v7) = v111;
        v117 = v15;
        v120 = v30;
LABEL_67:
        v31 = v131;
        ++v32;
        goto LABEL_28;
      }
      if ( ((*(_BYTE *)a2 + 89) & 0xFD) == 0 && *(_DWORD *)(a2 + 44) == v114 )
      {
        v85 = *(__int16 *)(a2 + 48) == v34;
        goto LABEL_185;
      }
LABEL_43:
      ;
    }
    v8 = a4;
    v14 = v116;
LABEL_45:
    if ( v32 && v32 >= v126 )
    {
      v30 = v120;
LABEL_48:
      v38 = v111;
    }
    else
    {
      v30 = v120;
      v38 = 0;
    }
    if ( v30 )
    {
      LOBYTE(a2) = 1;
      v111 = a2;
    }
    else
    {
      v117 = v15;
      LODWORD(a2) = v38;
      v111 = v38;
      if ( !v38 )
      {
        v18 = v121;
        v16 = v127;
        goto LABEL_52;
      }
    }
    v16 = v127;
    v18 = v121;
LABEL_73:
    v16 |= *(_QWORD *)(v14 + 8);
    v43 = 0;
    v127 = v16;
    if ( v18 )
    {
      do
      {
        if ( !_bittest64((const __int64 *)&v15, v43) )
        {
          v47 = *(_QWORD *)&v118[32 * v43 + 8];
          v48 = sqlite3WhereExprUsage(a1 + 75, v47, v13);
          if ( (v48 || (unsigned int)exprIsConst(0, v47, 1)) && (~v16 & v48) == 0 )
            _bittestandset64((__int64 *)&v15, v43);
        }
        ++v43;
      }
      while ( (int)v43 < v18 );
      v14 = v116;
      LODWORD(a2) = v111;
      v8 = a4;
      v117 = v15;
    }
LABEL_52:
    v13 = v118;
    v21 = v123 + 1;
    v11 = a1;
    v20 = v115;
    LODWORD(v7) = a5;
    v9 = a6;
    v10 = a3;
    v17 = v128;
    v19 = v133;
  }
  if ( *(_BYTE *)(v14 + 32) && (v8 & 0x280) != 0x80 )
    return v122;
  return -1;
}

```

## disassembly

```asm
0x180012200  mov     [rsp+arg_18], rbx
0x180012205  push    rbp
0x180012206  push    rsi
0x180012207  push    rdi
0x180012208  push    r12
0x18001220a  push    r13
0x18001220c  push    r14
0x18001220e  push    r15
0x180012210  sub     rsp, 140h
0x180012217  mov     rax, cs:__security_cookie
0x18001221e  xor     rax, rsp
0x180012221  mov     [rsp+178h+var_48], rax
0x180012229  movzx   ebx, [rsp+178h+arg_20]
0x180012231  movzx   ebp, r9w
0x180012235  mov     rdi, [rsp+178h+arg_28]
0x18001223d  mov     rsi, r8
0x180012240  mov     rax, [rsp+178h+arg_30]
0x180012248  mov     r11, rcx
0x18001224b  mov     [rsp+178h+var_156], r9w
0x180012251  mov     [rsp+178h+var_D8], r8
0x180012259  mov     [rsp+178h+var_130], rdx
0x18001225e  mov     [rsp+178h+var_128], rcx
0x180012263  mov     [rsp+178h+var_E0], rdi
0x18001226b  mov     [rsp+178h+var_C8], rax
0x180012273  test    bx, bx
0x180012276  jnz     loc_180012751
0x18001227c  movzx   r10d, word ptr [rdx]
0x180012280  mov     [rsp+178h+var_118], r10w
0x180012286  cmp     r10d, 3Fh ; '?'
0x18001228a  ja      loc_180012717
0x180012290  mov     r8, [rsp+178h+var_130]
0x180012295  mov     ecx, r10d
0x180012298  xor     r9d, r9d
0x18001229b  mov     [rsp+178h+var_11C], r10d
0x1800122a0  xor     r14d, r14d
0x1800122a3  xor     r12d, r12d
0x1800122a6  xor     r15d, r15d
0x1800122a9  mov     [rsp+178h+var_138], r14
0x1800122ae  mov     r13d, r10d
0x1800122b1  mov     [rsp+178h+var_100], r12
0x1800122b6  mov     r10d, r9d
0x1800122b9  mov     [rsp+178h+var_F8], r15
0x1800122c1  mov     eax, 1
0x1800122c6  mov     dl, 1
0x1800122c8  shl     rax, cl
0x1800122cb  mov     ecx, 803h
0x1800122d0  dec     rax
0x1800122d3  mov     [rsp+178h+var_154], edx
0x1800122d7  test    cx, bp
0x1800122da  mov     [rsp+178h+var_C0], rax
0x1800122e2  setnz   r10b
0x1800122e6  add     r10w, 182h
0x1800122ec  mov     dword ptr [rsp+178h+var_148], r10d
0x1800122f1  xor     ecx, ecx
0x1800122f3  mov     [rsp+178h+var_114], ecx
0x1800122f7  test    dl, dl
0x1800122f9  jz      loc_180012573
0x1800122ff  cmp     r14, rax
0x180012302  jnb     loc_180012576
0x180012308  movzx   eax, bx
0x18001230b  cmp     ecx, eax
0x18001230d  jg      loc_180012781
0x180012313  test    ecx, ecx
0x180012315  jg      loc_180012661
0x18001231b  cmp     ecx, eax
0x18001231d  jl      loc_1800127DC
0x180012323  mov     r9, rdi
0x180012326  mov     [rsp+178h+var_140], rdi
0x18001232b  test    dword ptr [r9+38h], 400h
0x180012333  jnz     loc_180012776
0x180012339  movzx   eax, bp
0x18001233c  mov     ecx, 80h
0x180012341  and     ax, cx
0x180012344  mov     [rsp+178h+var_E8], ax
0x18001234c  jnz     loc_180012672
0x180012352  movzx   eax, byte ptr [r9+10h]
0x180012357  imul    rcx, rax, 68h ; 'h'
0x18001235b  mov     rax, [r11+8]
0x18001235f  mov     ecx, [rcx+rax+4Ch]
0x180012363  mov     [rsp+178h+var_14C], ecx
0x180012367  test    r13d, r13d
0x18001236a  jz      short loc_1800123AA
0x18001236c  xor     esi, esi
0x18001236e  mov     eax, esi
0x180012370  bt      r14, rax
0x180012374  jb      short loc_180012390
0x180012376  mov     r15d, esi
0x180012379  shl     r15, 5
0x18001237d  add     r15, r8
0x180012380  mov     r12d, esi
0x180012383  mov     rdi, [r15+8]
0x180012387  test    rdi, rdi
0x18001238a  jnz     loc_180012D80
0x180012390  inc     esi
0x180012392  cmp     esi, r13d
0x180012395  jl      short loc_18001236E
0x180012397  mov     edx, [rsp+178h+var_154]
0x18001239b  movzx   ebp, [rsp+178h+var_156]
0x1800123a0  mov     r10d, dword ptr [rsp+178h+var_148]
0x1800123a5  mov     r12, [rsp+178h+var_100]
0x1800123aa  mov     eax, [r9+38h]
0x1800123ae  bt      eax, 0Ch
0x1800123b2  jb      loc_1800126BD
0x1800123b8  bt      eax, 8
0x1800123bc  jb      loc_18001268F
0x1800123c2  mov     r11, [r9+20h]
0x1800123c6  mov     [rsp+178h+var_F0], r11
0x1800123ce  test    r11, r11
0x1800123d1  jz      loc_180012717
0x1800123d7  test    byte ptr [r11+64h], 4
0x1800123dc  jnz     loc_180012717
0x1800123e2  cmp     byte ptr [r11+62h], 0
0x1800123e7  movzx   edx, word ptr [r11+5Eh]
0x1800123ec  movzx   ecx, word ptr [r11+60h]
0x1800123f1  mov     dword ptr [rsp+178h+var_108], edx
0x1800123f5  jnz     loc_18001267E
0x1800123fb  xor     bl, bl
0x1800123fd  mov     [rsp+178h+var_154], ebx
0x180012401  xor     r13b, r13b
0x180012404  movzx   eax, cx
0x180012407  mov     [rsp+178h+var_120], r13d
0x18001240c  xor     edi, edi
0x18001240e  mov     [rsp+178h+var_E4], eax
0x180012415  mov     [rsp+178h+var_14F], 0
0x18001241a  mov     [rsp+178h+var_150], 0
0x18001241f  mov     [rsp+178h+var_10C], edi
0x180012423  cmp     edi, eax
0x180012425  jge     loc_180012506
0x18001242b  movzx   edx, word ptr [r9+18h]
0x180012430  mov     r12b, 1
0x180012433  cmp     edi, edx
0x180012435  jl      loc_1800125AC
0x18001243b  test    r11, r11
0x18001243e  jz      loc_1800126FC
0x180012444  mov     rax, [r11+8]
0x180012448  movsxd  rcx, edi
0x18001244b  movsx   esi, word ptr [rax+rcx*2]
0x18001244f  mov     rax, [r11+38h]
0x180012453  movzx   ebp, byte ptr [rcx+rax]
0x180012457  mov     rax, [r11+18h]
0x18001245b  and     bpl, 1
0x18001245f  mov     [rsp+178h+var_158], bpl
0x180012464  movsx   ecx, word ptr [rax+34h]
0x180012468  mov     eax, 0FFFFFFFFh
0x18001246d  cmp     esi, ecx
0x18001246f  cmovz   esi, eax
0x180012472  mov     [rsp+178h+var_110], esi
0x180012476  test    bl, bl
0x180012478  jz      short loc_1800124A1
0x18001247a  test    esi, esi
0x18001247c  js      loc_180012762
0x180012482  cmp     edi, edx
0x180012484  jl      short loc_1800124A1
0x180012486  movsxd  rax, esi
0x180012489  lea     rdx, [rax+rax*2]
0x18001248d  mov     rax, [r11+18h]
0x180012491  mov     rcx, [rax+8]
0x180012495  test    byte ptr [rcx+rdx*8+8], 0Fh
0x18001249a  jnz     short loc_1800124A1
0x18001249c  mov     byte ptr [rsp+178h+var_154], 0
0x1800124a1  xor     r15d, r15d
0x1800124a4  test    r12b, r12b
0x1800124a7  jz      short loc_1800124E2
0x1800124a9  cmp     r15d, [rsp+178h+var_11C]
0x1800124ae  jge     short loc_1800124E2
0x1800124b0  mov     eax, r15d
0x1800124b3  bt      r14, rax
0x1800124b7  jb      short loc_1800124DD
0x1800124b9  movsxd  rbx, r15d
0x1800124bc  mov     r13, rbx
0x1800124bf  mov     [rsp+178h+var_D0], rbx
0x1800124c7  shl     r13, 5
0x1800124cb  add     r13, [rsp+178h+var_130]
0x1800124d0  mov     rdx, [r13+8]
0x1800124d4  test    rdx, rdx
0x1800124d7  jnz     loc_180012C10
0x1800124dd  inc     r15d
0x1800124e0  jmp     short loc_1800124A4
0x1800124e2  movzx   ebp, [rsp+178h+var_156]
0x1800124e7  mov     r9, [rsp+178h+var_140]
0x1800124ec  test    edi, edi
0x1800124ee  jz      loc_180012745
0x1800124f4  movzx   eax, [rsp+178h+var_108]
0x1800124f9  cmp     edi, eax
0x1800124fb  jl      loc_180012745
0x180012501  mov     r13d, [rsp+178h+var_120]
0x180012506  mov     eax, [rsp+178h+var_154]
0x18001250a  test    r13b, r13b
0x18001250d  jnz     loc_1800126AD
0x180012513  mov     [rsp+178h+var_138], r14
0x180012518  movzx   edx, al
0x18001251b  mov     [rsp+178h+var_154], edx
0x18001251f  test    al, al
0x180012521  jnz     loc_1800126B3
0x180012527  mov     r13d, [rsp+178h+var_11C]
0x18001252c  mov     r12, [rsp+178h+var_100]
0x180012531  mov     ecx, [rsp+178h+var_114]
0x180012535  mov     r8, [rsp+178h+var_130]
0x18001253a  inc     ecx
0x18001253c  mov     r11, [rsp+178h+var_128]
0x180012541  mov     r10d, dword ptr [rsp+178h+var_148]
0x180012546  movzx   ebx, [rsp+178h+arg_20]
0x18001254e  mov     rdi, [rsp+178h+var_E0]
0x180012556  mov     rsi, [rsp+178h+var_D8]
0x18001255e  mov     r15, [rsp+178h+var_F8]
0x180012566  mov     rax, [rsp+178h+var_C0]
0x18001256e  jmp     loc_1800122F3
0x180012573  cmp     r14, rax
0x180012576  jnz     loc_18001270B
0x18001257c  movzx   eax, byte ptr [rsp+178h+var_118]
0x180012581  mov     rcx, [rsp+178h+var_48]
0x180012589  xor     rcx, rsp; StackCookie
0x18001258c  call    __security_check_cookie
0x180012591  mov     rbx, [rsp+178h+arg_18]
0x180012599  add     rsp, 140h
0x1800125a0  pop     r15
0x1800125a2  pop     r14
0x1800125a4  pop     r13
0x1800125a6  pop     r12
0x1800125a8  pop     rdi
0x1800125a9  pop     rsi
0x1800125aa  pop     rbp
0x1800125ab  retn
0x1800125ac  movzx   eax, word ptr [r9+3Eh]
0x1800125b1  cmp     edi, eax
0x1800125b3  jl      loc_18001243B
0x1800125b9  mov     r8, [r9+48h]
0x1800125bd  movsxd  rax, edi
0x1800125c0  mov     rcx, [r8+rax*8]
0x1800125c4  movzx   eax, word ptr [rcx+14h]
0x1800125c8  test    r10w, ax
0x1800125cc  jz      loc_180012788
0x1800125d2  mov     ecx, 180h
0x1800125d7  test    cx, ax
0x1800125da  jz      short loc_180012653
0x1800125dc  mov     eax, [rsp+178h+var_E4]
0x1800125e3  xor     bl, bl
0x1800125e5  mov     [rsp+178h+var_154], ebx
0x1800125e9  inc     edi
0x1800125eb  jmp     loc_18001241F
0x1800125f0  movzx   r10d, al
0x1800125f4  xor     r10b, [rsp+178h+var_158]
0x1800125f9  mov     [rsp+178h+var_150], r10b
0x1800125fe  jz      short loc_180012617
0x180012600  mov     rdx, [rsp+178h+var_C8]
0x180012608  movsxd  rax, [rsp+178h+var_114]
0x18001260d  mov     rcx, [rdx]
0x180012610  bts     rcx, rax
0x180012614  mov     [rdx], rcx
0x180012617  mov     [rsp+178h+var_14F], 1
0x18001261c  test    byte ptr [r13+18h], 2
0x180012621  jnz     loc_1800127BA
0x180012627  mov     r13d, [rsp+178h+var_120]
0x18001262c  cmp     esi, 0FFFFFFFFh
0x18001262f  mov     r10d, dword ptr [rsp+178h+var_148]
0x180012634  mov     eax, 1
0x180012639  movzx   r13d, r13b
0x18001263d  cmovz   r13d, eax
0x180012641  bts     r14, rbx
0x180012645  mov     ebx, [rsp+178h+var_154]
0x180012649  mov     [rsp+178h+var_138], r14
0x18001264e  mov     [rsp+178h+var_120], r13d
0x180012653  mov     eax, [rsp+178h+var_E4]
0x18001265a  inc     edi
0x18001265c  jmp     loc_18001241F
0x180012661  or      r15, [r9+8]
0x180012665  mov     [rsp+178h+var_F8], r15
0x18001266d  jmp     loc_18001231B
0x180012672  xor     eax, eax
0x180012674  mov     [r9+1Eh], ax
0x180012679  jmp     loc_180012352
0x18001267e  bt      eax, 0Fh
0x180012682  jb      loc_1800123FB
0x180012688  mov     bl, 1
0x18001268a  jmp     loc_1800123FD
0x18001268f  mov     ebx, [rsp+178h+var_154]
0x180012693  xor     r11d, r11d
0x180012696  mov     [rsp+178h+var_F0], r11
0x18001269e  mov     ecx, 1
0x1800126a3  mov     dword ptr [rsp+178h+var_108], r11d
0x1800126a8  jmp     loc_180012401
0x1800126ad  mov     dl, 1
0x1800126af  mov     [rsp+178h+var_154], edx
0x1800126b3  mov     r12, [rsp+178h+var_100]
0x1800126b8  mov     r13d, [rsp+178h+var_11C]
0x1800126bd  or      r12, [r9+8]
0x1800126c1  xor     ebx, ebx
0x1800126c3  mov     [rsp+178h+var_100], r12
0x1800126c8  test    r13d, r13d
0x1800126cb  jz      loc_180012531
0x1800126d1  mov     eax, ebx
0x1800126d3  bt      r14, rax
0x1800126d7  jnb     loc_18001280A
0x1800126dd  inc     ebx
0x1800126df  cmp     ebx, r13d
0x1800126e2  jl      short loc_1800126D1
0x1800126e4  mov     r9, [rsp+178h+var_140]
0x1800126e9  mov     edx, [rsp+178h+var_154]
0x1800126ed  movzx   ebp, [rsp+178h+var_156]
0x1800126f2  mov     [rsp+178h+var_138], r14
  ... truncated ...
```

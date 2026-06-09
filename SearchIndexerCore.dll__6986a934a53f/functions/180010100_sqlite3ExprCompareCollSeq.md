# sqlite3ExprCompareCollSeq

- ea: `0x180010100`
- end: `0x180010c63`
- name: `sqlite3ExprCompareCollSeq`
- size: `2915`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000fcd4`
- `0x180012200`
- `0x180012fd4`
- `0x180064df4`
- `0x18006b8d8`
- `0x180076c80`
- `0x18009ee70`
- `0x1800a480c`

## callees

- `0x180010100`
- `0x180010c70`
- `0x1800117a0`
- `0x180011948`
- `0x180011a10`
- `0x180011bcc`
- `0x180014650`
- `0x180052840`
- `0x180052d60`

## pseudocode

```c
__int64 __fastcall sqlite3ExprCompareCollSeq(_DWORD *a1, __int64 a2)
{
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // rbp
  _QWORD *v6; // rbx
  char *v7; // rax
  char v8; // al
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  __int64 v13; // r14
  char *v14; // rax
  char v15; // al
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  _DWORD *v19; // rcx
  __int64 *v20; // r11
  __int64 v21; // rdx
  __int64 *v23; // r11
  __int64 v24; // rdx
  __int64 v25; // rbp
  char *v26; // rax
  char v27; // al
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  _DWORD *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int16 v35; // ax
  __int64 *v36; // r12
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int16 v40; // r8
  const char *v41; // rdi
  __int64 v42; // rsi
  int *v43; // r10
  int v44; // r11d
  __int64 *v45; // r12
  _BYTE *v46; // rdx
  const char *i; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 CollSeq; // rax
  const char *v52; // rsi
  __int64 v53; // rbp
  int *v54; // r10
  int v55; // ebx
  __int64 *v56; // r11
  _BYTE *v57; // r8
  const char *n; // r9
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int16 v66; // ax
  const char *v67; // rdi
  __int64 v68; // rsi
  int *v69; // r10
  int v70; // ebx
  __int64 *v71; // r11
  _BYTE *v72; // rdx
  const char *mm; // r8
  __int64 v74; // r9
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  unsigned int v78; // eax
  _DWORD *v79; // r10
  __int64 v80; // r11
  unsigned int v81; // eax
  _DWORD *v82; // r10
  __int64 v83; // r11
  unsigned int v84; // eax
  _DWORD *v85; // r10
  __int64 v86; // r11
  int j; // r8d
  __int64 v88; // rax
  int ii; // r8d
  __int64 v90; // rax
  int nn; // r8d
  __int64 v92; // rax
  unsigned __int8 *v93; // rbx
  int *v94; // r10
  int v95; // r11d
  _BYTE *v96; // r8
  unsigned __int8 *m; // rax
  __int64 v98; // r9
  __int64 v99; // rcx
  unsigned int v100; // eax
  _DWORD *v101; // r10
  __int64 v102; // r11
  unsigned __int8 *v103; // rbx
  int *v104; // r10
  int v105; // esi
  _BYTE *v106; // r8
  unsigned __int8 *kk; // r9
  __int64 v108; // rdx
  __int64 v109; // rax
  unsigned int v110; // eax
  _DWORD *v111; // r10
  __int64 v112; // r11
  unsigned __int8 *v113; // rbx
  int *v114; // r10
  int v115; // edi
  _BYTE *v116; // rdx
  unsigned __int8 *i2; // r8
  __int64 v118; // r9
  __int64 v119; // rax
  unsigned int v120; // eax
  _DWORD *v121; // r10
  __int64 v122; // r11
  _BYTE *k; // r8
  _BYTE *jj; // rax
  _BYTE *i1; // r8

  v3 = *(_QWORD *)(a2 + 16);
  if ( (*(_DWORD *)(a2 + 4) & 0x400) != 0 )
    return sqlite3BinaryCompareCollSeq(a1, *(_QWORD *)(a2 + 24), v3);
  if ( (*(_DWORD *)(v3 + 4) & 0x200) != 0 )
    return sqlite3ExprCollSeq(a1, v3);
  v4 = *(_QWORD *)(a2 + 24);
  if ( v4 && (*(_DWORD *)(v4 + 4) & 0x200) != 0 )
  {
    v5 = *(_QWORD *)a1;
    v6 = 0;
    while ( 1 )
    {
      if ( !v4 )
        return (__int64)v6;
      v7 = (char *)(*(_BYTE *)v4 == 0xB0 ? v4 + 2 : v4);
      v8 = *v7;
      if ( v8 == -87 )
        break;
      switch ( v8 )
      {
        case -89:
          goto LABEL_70;
        case 36:
          goto LABEL_158;
        case 77:
          goto LABEL_70;
        case -83:
LABEL_158:
          v4 = *(_QWORD *)(v4 + 16);
          break;
        case -79:
          v4 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 8LL);
          break;
        case 113:
          v41 = *(const char **)(v4 + 8);
          v42 = *(unsigned __int8 *)(v5 + 100);
          if ( v41 )
          {
            v43 = (int *)(v5 + 624);
            if ( *(_QWORD *)(v5 + 640) )
            {
              v78 = strHash(v41);
              v43 = (int *)(v80 + 16LL * (v78 % *v79));
              v44 = *v43;
            }
            else
            {
              v44 = *(_DWORD *)(v5 + 628);
            }
            v45 = (__int64 *)*((_QWORD *)v43 + 1);
LABEL_88:
            if ( v44 )
            {
              v46 = (_BYTE *)v45[3];
              for ( i = v41; ; ++i )
              {
                v48 = (unsigned __int8)*v46;
                v49 = *(unsigned __int8 *)i;
                if ( (_DWORD)v48 == (_DWORD)v49 )
                {
                  if ( !*v46 )
                    goto LABEL_94;
                }
                else if ( *((unsigned __int8 *)qword_1800B4ED0 + v48) != *((unsigned __int8 *)qword_1800B4ED0 + v49) )
                {
                  v45 = (__int64 *)*v45;
                  --v44;
                  goto LABEL_88;
                }
                ++v46;
              }
            }
            v45 = qword_1800D0DC0;
LABEL_94:
            v50 = v45[2];
            if ( v50 )
              v6 = (_QWORD *)(v50 + 40 * (v42 - 1));
          }
          else
          {
            v6 = *(_QWORD **)(v5 + 16);
          }
          if ( !v6 || !v6[3] )
          {
            callCollNeeded(v5, (unsigned int)v42, v41);
            CollSeq = sqlite3FindCollSeq(v5, (unsigned __int8)v42, v41, 0);
            v6 = (_QWORD *)CollSeq;
            if ( !CollSeq )
              goto LABEL_99;
            if ( !*(_QWORD *)(CollSeq + 24) && (unsigned int)synthCollSeq(v5, CollSeq) )
            {
              v6 = 0;
LABEL_99:
              sqlite3ErrorMsg(a1, "no such collation sequence: %s", v41);
              a1[6] = 257;
            }
          }
LABEL_76:
          if ( v6 && !v6[3] && !sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*(_QWORD *)a1 + 100LL), v6, *v6) )
            return 0;
          return (__int64)v6;
        default:
LABEL_16:
          v9 = *(_DWORD *)(v4 + 4);
          if ( (v9 & 0x200) == 0 )
            return (__int64)v6;
          v10 = *(_QWORD *)(v4 + 16);
          if ( v10 && (*(_DWORD *)(v10 + 4) & 0x200) != 0 )
          {
            v4 = *(_QWORD *)(v4 + 16);
          }
          else
          {
            v11 = *(_QWORD *)(v4 + 24);
            if ( (v9 & 0x1000) == 0 )
            {
              v12 = *(_DWORD **)(v4 + 32);
              if ( v12 )
              {
                if ( !*(_BYTE *)(v5 + 103) )
                {
                  for ( j = 0; j < *v12; ++j )
                  {
                    v88 = 8LL * j;
                    if ( (*(_DWORD *)(*(_QWORD *)&v12[v88 + 2] + 4LL) & 0x200) != 0 )
                    {
                      v11 = *(_QWORD *)&v12[v88 + 2];
                      break;
                    }
                  }
                }
              }
            }
            v4 = v11;
          }
          break;
      }
    }
    if ( *(_QWORD *)(v4 + 64) )
    {
LABEL_70:
      v32 = *(__int16 *)(v4 + 48);
      if ( (v32 & 0x8000u) != 0LL )
        return (__int64)v6;
      v33 = 3 * v32;
      v34 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 8LL);
      v35 = *(_WORD *)(v34 + 24 * v32 + 18);
      if ( (v35 & 0x200) == 0 )
        goto LABEL_72;
      for ( k = *(_BYTE **)(v34 + 8 * v33); *k; ++k )
        ;
      if ( (v35 & 4) != 0 )
      {
        do
          ++k;
        while ( *k );
      }
      v93 = k + 1;
      if ( k == (_BYTE *)-1LL )
      {
LABEL_72:
        v6 = *(_QWORD **)(v5 + 16);
      }
      else
      {
        v94 = (int *)(v5 + 624);
        if ( *(_QWORD *)(v5 + 640) )
        {
          v100 = strHash(k + 1);
          v94 = (int *)(v102 + 16LL * (v100 % *v101));
          v95 = *v94;
        }
        else
        {
          v95 = *(_DWORD *)(v5 + 628);
        }
        v36 = (__int64 *)*((_QWORD *)v94 + 1);
LABEL_197:
        if ( v95 )
        {
          v96 = (_BYTE *)v36[3];
          for ( m = v93; ; ++m )
          {
            v98 = (unsigned __int8)*v96;
            v99 = *m;
            if ( (_DWORD)v98 == (_DWORD)v99 )
            {
              if ( !*v96 )
                goto LABEL_74;
            }
            else if ( *((unsigned __int8 *)qword_1800B4ED0 + v98) != *((unsigned __int8 *)qword_1800B4ED0 + v99) )
            {
              v36 = (__int64 *)*v36;
              --v95;
              goto LABEL_197;
            }
            ++v96;
          }
        }
        v36 = qword_1800D0DC0;
LABEL_74:
        v37 = v36[2];
        if ( v37 )
          v6 = (_QWORD *)(v37 + 40 * (*(unsigned __int8 *)(v5 + 100) - 1LL));
        else
          v6 = 0;
      }
      goto LABEL_76;
    }
    goto LABEL_16;
  }
  v6 = 0;
  v13 = *(_QWORD *)a1;
  while ( 1 )
  {
    if ( !v3 )
      goto LABEL_51;
    v14 = (char *)(*(_BYTE *)v3 == 0xB0 ? v3 + 2 : v3);
    v15 = *v14;
    if ( v15 == -87 )
      break;
    switch ( v15 )
    {
      case -89:
        goto LABEL_81;
      case 36:
        goto LABEL_159;
      case 77:
        goto LABEL_81;
      case -83:
LABEL_159:
        v3 = *(_QWORD *)(v3 + 16);
        break;
      case -79:
        v3 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 8LL);
        break;
      case 113:
        v52 = *(const char **)(v3 + 8);
        v53 = *(unsigned __int8 *)(v13 + 100);
        if ( v52 )
        {
          v54 = (int *)(v13 + 624);
          if ( *(_QWORD *)(v13 + 640) )
          {
            v81 = strHash(*(_QWORD *)(v3 + 8));
            v54 = (int *)(v83 + 16LL * (v81 % *v82));
            v55 = *v54;
          }
          else
          {
            v55 = *(_DWORD *)(v13 + 628);
          }
          v56 = (__int64 *)*((_QWORD *)v54 + 1);
LABEL_106:
          if ( v55 )
          {
            v57 = (_BYTE *)v56[3];
            for ( n = v52; ; ++n )
            {
              v59 = (unsigned __int8)*v57;
              v60 = *(unsigned __int8 *)n;
              if ( (_DWORD)v59 == (_DWORD)v60 )
              {
                if ( !*v57 )
                  goto LABEL_112;
              }
              else if ( *((unsigned __int8 *)qword_1800B4ED0 + v59) != *((unsigned __int8 *)qword_1800B4ED0 + v60) )
              {
                v56 = (__int64 *)*v56;
                --v55;
                goto LABEL_106;
              }
              ++v57;
            }
          }
          v56 = qword_1800D0DC0;
LABEL_112:
          v61 = v56[2];
          if ( v61 )
            v6 = (_QWORD *)(v61 + 40 * (v53 - 1));
          else
            v6 = 0;
        }
        else
        {
          v6 = *(_QWORD **)(v13 + 16);
        }
        if ( !v6 || !v6[3] )
        {
          callCollNeeded(v13, (unsigned int)v53, v52);
          v62 = sqlite3FindCollSeq(v13, (unsigned __int8)v53, v52, 0);
          v6 = (_QWORD *)v62;
          if ( v62 )
          {
            if ( *(_QWORD *)(v62 + 24) || !(unsigned int)synthCollSeq(v13, v62) )
              goto LABEL_49;
            v6 = 0;
          }
          sqlite3ErrorMsg(a1, "no such collation sequence: %s", v52);
          a1[6] = 257;
        }
LABEL_49:
        if ( v6 && (v6[3] || sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*(_QWORD *)a1 + 100LL), v6, *v6)) )
          goto LABEL_51;
        goto LABEL_52;
      default:
LABEL_33:
        v16 = *(_DWORD *)(v3 + 4);
        if ( (v16 & 0x200) == 0 )
          goto LABEL_51;
        v17 = *(_QWORD *)(v3 + 16);
        if ( v17 && (*(_DWORD *)(v17 + 4) & 0x200) != 0 )
        {
          v3 = *(_QWORD *)(v3 + 16);
        }
        else
        {
          v18 = *(_QWORD *)(v3 + 24);
          if ( (v16 & 0x1000) == 0 )
          {
            v19 = *(_DWORD **)(v3 + 32);
            if ( v19 )
            {
              if ( !*(_BYTE *)(v13 + 103) )
              {
                for ( ii = 0; ii < *v19; ++ii )
                {
                  v90 = 8LL * ii;
                  if ( (*(_DWORD *)(*(_QWORD *)&v19[v90 + 2] + 4LL) & 0x200) != 0 )
                  {
                    v18 = *(_QWORD *)&v19[v90 + 2];
                    break;
                  }
                }
              }
            }
          }
          v3 = v18;
        }
        break;
    }
  }
  if ( !*(_QWORD *)(v3 + 64) )
    goto LABEL_33;
LABEL_81:
  v38 = *(__int16 *)(v3 + 48);
  if ( (v38 & 0x8000u) == 0LL )
  {
    v39 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 8LL);
    v40 = *(_WORD *)(v39 + 24 * v38 + 18);
    if ( (v40 & 0x200) == 0 )
      goto LABEL_83;
    for ( jj = *(_BYTE **)(v39 + 24 * v38); *jj; ++jj )
      ;
    if ( (v40 & 4) != 0 )
    {
      do
        ++jj;
      while ( *jj );
    }
    v103 = jj + 1;
    if ( jj == (_BYTE *)-1LL )
    {
LABEL_83:
      v6 = *(_QWORD **)(v13 + 16);
    }
    else
    {
      v104 = (int *)(v13 + 624);
      if ( *(_QWORD *)(v13 + 640) )
      {
        v110 = strHash(jj + 1);
        v104 = (int *)(v112 + 16LL * (v110 % *v111));
        v105 = *v104;
      }
      else
      {
        v105 = *(_DWORD *)(v13 + 628);
      }
      v23 = (__int64 *)*((_QWORD *)v104 + 1);
LABEL_209:
      if ( v105 )
      {
        v106 = (_BYTE *)v23[3];
        for ( kk = v103; ; ++kk )
        {
          v108 = (unsigned __int8)*v106;
          v109 = *kk;
          if ( (_DWORD)v108 == (_DWORD)v109 )
          {
            if ( !*v106 )
              goto LABEL_47;
          }
          else if ( *((unsigned __int8 *)qword_1800B4ED0 + v108) != *((unsigned __int8 *)qword_1800B4ED0 + v109) )
          {
            v23 = (__int64 *)*v23;
            --v105;
            goto LABEL_209;
          }
          ++v106;
        }
      }
      v23 = qword_1800D0DC0;
LABEL_47:
      v24 = v23[2];
      if ( v24 )
        v6 = (_QWORD *)(v24 + 40 * (*(unsigned __int8 *)(v13 + 100) - 1LL));
      else
        v6 = 0;
    }
    goto LABEL_49;
  }
LABEL_51:
  if ( !v6 )
  {
LABEL_52:
    v25 = *(_QWORD *)a1;
    v6 = 0;
    while ( 1 )
    {
      if ( !v4 )
        return (__int64)v6;
      v26 = (char *)(*(_BYTE *)v4 == 0xB0 ? v4 + 2 : v4);
      v27 = *v26;
      if ( v27 == -87 )
        break;
      switch ( v27 )
      {
        case -89:
          goto LABEL_121;
        case 36:
          goto LABEL_164;
        case 77:
          goto LABEL_121;
        case -83:
LABEL_164:
          v4 = *(_QWORD *)(v4 + 16);
          break;
        case -79:
          v4 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 8LL);
          break;
        case 113:
          v67 = *(const char **)(v4 + 8);
          v68 = *(unsigned __int8 *)(v25 + 100);
          if ( v67 )
          {
            v69 = (int *)(v25 + 624);
            if ( *(_QWORD *)(v25 + 640) )
            {
              v84 = strHash(v67);
              v69 = (int *)(v86 + 16LL * (v84 % *v85));
              v70 = *v69;
            }
            else
            {
              v70 = *(_DWORD *)(v25 + 628);
            }
            v71 = (__int64 *)*((_QWORD *)v69 + 1);
LABEL_128:
            if ( v70 )
            {
              v72 = (_BYTE *)v71[3];
              for ( mm = v67; ; ++mm )
              {
                v74 = (unsigned __int8)*v72;
                v75 = *(unsigned __int8 *)mm;
                if ( (_DWORD)v74 == (_DWORD)v75 )
                {
                  if ( !*v72 )
                    goto LABEL_134;
                }
                else if ( *((unsigned __int8 *)qword_1800B4ED0 + v74) != *((unsigned __int8 *)qword_1800B4ED0 + v75) )
                {
                  v71 = (__int64 *)*v71;
                  --v70;
                  goto LABEL_128;
                }
                ++v72;
              }
            }
            v71 = qword_1800D0DC0;
LABEL_134:
            v76 = v71[2];
            if ( v76 )
              v6 = (_QWORD *)(v76 + 40 * (v68 - 1));
            else
              v6 = 0;
          }
          else
          {
            v6 = *(_QWORD **)(v25 + 16);
          }
          if ( !v6 || !v6[3] )
          {
            callCollNeeded(v25, (unsigned int)v68, v67);
            v77 = sqlite3FindCollSeq(v25, (unsigned __int8)v68, v67, 0);
            v6 = (_QWORD *)v77;
            if ( !v77 )
              goto LABEL_139;
            if ( !*(_QWORD *)(v77 + 24) && (unsigned int)synthCollSeq(v25, v77) )
            {
              v6 = 0;
LABEL_139:
              sqlite3ErrorMsg(a1, "no such collation sequence: %s", v67);
              a1[6] = 257;
            }
          }
LABEL_42:
          if ( v6 && !v6[3] && !sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*(_QWORD *)a1 + 100LL), v6, *v6) )
            return 0;
          return (__int64)v6;
        default:
LABEL_63:
          v28 = *(_DWORD *)(v4 + 4);
          if ( (v28 & 0x200) == 0 )
            return (__int64)v6;
          v29 = *(_QWORD *)(v4 + 16);
          if ( v29 && (*(_DWORD *)(v29 + 4) & 0x200) != 0 )
          {
            v4 = *(_QWORD *)(v4 + 16);
          }
          else
          {
            v30 = *(_QWORD *)(v4 + 24);
            if ( (v28 & 0x1000) == 0 )
            {
              v31 = *(_DWORD **)(v4 + 32);
              if ( v31 )
              {
                if ( !*(_BYTE *)(v25 + 103) )
                {
                  for ( nn = 0; nn < *v31; ++nn )
                  {
                    v92 = 8LL * nn;
                    if ( (*(_DWORD *)(*(_QWORD *)&v31[v92 + 2] + 4LL) & 0x200) != 0 )
                    {
                      v30 = *(_QWORD *)&v31[v92 + 2];
                      break;
                    }
                  }
                }
              }
            }
            v4 = v30;
          }
          break;
      }
    }
    if ( *(_QWORD *)(v4 + 64) )
    {
LABEL_121:
      v63 = *(__int16 *)(v4 + 48);
      if ( (v63 & 0x8000u) != 0LL )
        return (__int64)v6;
      v64 = 3 * v63;
      v65 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 8LL);
      v66 = *(_WORD *)(v65 + 24 * v63 + 18);
      if ( (v66 & 0x200) == 0 )
        goto LABEL_123;
      for ( i1 = *(_BYTE **)(v65 + 8 * v64); *i1; ++i1 )
        ;
      if ( (v66 & 4) != 0 )
      {
        do
          ++i1;
        while ( *i1 );
      }
      v113 = i1 + 1;
      if ( i1 == (_BYTE *)-1LL )
      {
LABEL_123:
        v6 = *(_QWORD **)(v25 + 16);
      }
      else
      {
        v114 = (int *)(v25 + 624);
        if ( *(_QWORD *)(v25 + 640) )
        {
          v120 = strHash(i1 + 1);
          v114 = (int *)(v122 + 16LL * (v120 % *v121));
          v115 = *v114;
        }
        else
        {
          v115 = *(_DWORD *)(v25 + 628);
        }
        v20 = (__int64 *)*((_QWORD *)v114 + 1);
LABEL_221:
        if ( v115 )
        {
          v116 = (_BYTE *)v20[3];
          for ( i2 = v113; ; ++i2 )
          {
            v118 = (unsigned __int8)*v116;
            v119 = *i2;
            if ( (_DWORD)v118 == (_DWORD)v119 )
            {
              if ( !*v116 )
                goto LABEL_40;
            }
            else if ( *((unsigned __int8 *)qword_1800B4ED0 + v118) != *((unsigned __int8 *)qword_1800B4ED0 + v119) )
            {
              v20 = (__int64 *)*v20;
              --v115;
              goto LABEL_221;
            }
            ++v116;
          }
        }
        v20 = qword_1800D0DC0;
LABEL_40:
        v21 = v20[2];
        if ( v21 )
          v6 = (_QWORD *)(v21 + 40 * (*(unsigned __int8 *)(v25 + 100) - 1LL));
        else
          v6 = 0;
      }
      goto LABEL_42;
    }
    goto LABEL_63;
  }
  return (__int64)v6;
}

```

## disassembly

```asm
0x180010100  push    r13
0x180010102  sub     rsp, 40h
0x180010106  test    dword ptr [rdx+4], 400h
0x18001010d  mov     r13, rcx
0x180010110  mov     r8, [rdx+10h]
0x180010114  jnz     loc_1800108F5
0x18001011a  mov     r10d, 200h
0x180010120  mov     [rsp+48h+arg_0], rbx
0x180010125  test    [r8+4], r10d
0x180010129  jnz     loc_18001081F
0x18001012f  mov     [rsp+48h+arg_8], rbp
0x180010134  mov     [rsp+48h+arg_10], rsi
0x180010139  mov     [rsp+48h+var_10], rdi
0x18001013e  mov     rdi, [rdx+18h]
0x180010142  mov     [rsp+48h+var_18], r12
0x180010147  mov     [rsp+48h+var_28], r15
0x18001014c  test    rdi, rdi
0x18001014f  jz      loc_1800101F1
0x180010155  test    [rdi+4], r10d
0x180010159  jz      loc_1800101F1
0x18001015f  mov     rbp, [rcx]
0x180010162  xor     ebx, ebx
0x180010164  test    rdi, rdi
0x180010167  jz      loc_1800102BF
0x18001016d  cmp     byte ptr [rdi], 0B0h
0x180010170  jz      loc_180010859
0x180010176  mov     rax, rdi
0x180010179  movzx   eax, byte ptr [rax]
0x18001017c  cmp     al, 0A9h
0x18001017e  jz      loc_1800103CD
0x180010184  cmp     al, 0A7h
0x180010186  jz      loc_1800103D7
0x18001018c  cmp     al, 24h ; '$'
0x18001018e  jz      loc_1800108BE
0x180010194  cmp     al, 4Dh ; 'M'
0x180010196  jz      loc_1800103D7
0x18001019c  cmp     al, 0ADh
0x18001019e  jz      loc_1800108BE
0x1800101a4  cmp     al, 0B1h
0x1800101a6  jz      loc_180010832
0x1800101ac  cmp     al, 71h ; 'q'
0x1800101ae  jz      loc_1800104AF
0x1800101b4  mov     eax, [rdi+4]
0x1800101b7  test    r10d, eax
0x1800101ba  jz      loc_1800102BF
0x1800101c0  mov     rcx, [rdi+10h]
0x1800101c4  test    rcx, rcx
0x1800101c7  jnz     loc_180010930
0x1800101cd  mov     rdx, [rdi+18h]
0x1800101d1  bt      eax, 0Ch
0x1800101d5  jb      short loc_1800101E9
0x1800101d7  mov     rcx, [rdi+20h]
0x1800101db  test    rcx, rcx
0x1800101de  jz      short loc_1800101E9
0x1800101e0  cmp     [rbp+67h], bl
0x1800101e3  jz      loc_18001090D
0x1800101e9  mov     rdi, rdx
0x1800101ec  jmp     loc_180010164
0x1800101f1  mov     [rsp+48h+var_20], r14
0x1800101f6  xor     ebx, ebx
0x1800101f8  mov     r14, [rcx]
0x1800101fb  test    r8, r8
0x1800101fe  jz      loc_1800102E7
0x180010204  cmp     byte ptr [r8], 0B0h
0x180010208  jz      loc_180010862
0x18001020e  mov     rax, r8
0x180010211  movzx   eax, byte ptr [rax]
0x180010214  cmp     al, 0A9h
0x180010216  jz      loc_180010464
0x18001021c  cmp     al, 0A7h
0x18001021e  jz      loc_18001046E
0x180010224  cmp     al, 24h ; '$'
0x180010226  jz      loc_1800108C7
0x18001022c  cmp     al, 4Dh ; 'M'
0x18001022e  jz      loc_18001046E
0x180010234  cmp     al, 0ADh
0x180010236  jz      loc_1800108C7
0x18001023c  cmp     al, 0B1h
0x18001023e  jz      loc_18001083F
0x180010244  cmp     al, 71h ; 'q'
0x180010246  jz      loc_1800105A3
0x18001024c  mov     eax, [r8+4]
0x180010250  test    r10d, eax
0x180010253  jz      loc_1800102E7
0x180010259  mov     rcx, [r8+10h]
0x18001025d  test    rcx, rcx
0x180010260  jnz     loc_18001096D
0x180010266  mov     rdx, [r8+18h]
0x18001026a  bt      eax, 0Ch
0x18001026e  jb      short loc_180010283
0x180010270  mov     rcx, [r8+20h]
0x180010274  test    rcx, rcx
0x180010277  jz      short loc_180010283
0x180010279  cmp     [r14+67h], bl
0x18001027d  jz      loc_18001094A
0x180010283  mov     r8, rdx
0x180010286  jmp     loc_1800101FB
0x18001028b  mov     r11, r12
0x18001028e  mov     rdx, [r11+10h]
0x180010292  test    rdx, rdx
0x180010295  jz      loc_180010C5C
0x18001029b  movzx   ebx, byte ptr [rbp+64h]
0x18001029f  dec     rbx
0x1800102a2  lea     rbx, [rbx+rbx*4]
0x1800102a6  lea     rbx, [rdx+rbx*8]
0x1800102aa  test    rbx, rbx
0x1800102ad  jz      short loc_1800102BA
0x1800102af  cmp     qword ptr [rbx+18h], 0
0x1800102b4  jz      loc_1800109E8
0x1800102ba  mov     r14, [rsp+48h+var_20]
0x1800102bf  mov     r12, [rsp+48h+var_18]
0x1800102c4  mov     rax, rbx
0x1800102c7  mov     rbx, [rsp+48h+arg_0]
0x1800102cc  mov     rdi, [rsp+48h+var_10]
0x1800102d1  mov     rsi, [rsp+48h+arg_10]
0x1800102d6  mov     rbp, [rsp+48h+arg_8]
0x1800102db  mov     r15, [rsp+48h+var_28]
0x1800102e0  add     rsp, 40h
0x1800102e4  pop     r13
0x1800102e6  retn
0x1800102e7  lea     r15, qword_1800B4ED0
0x1800102ee  lea     r12, qword_1800D0DC0
0x1800102f5  jmp     short loc_180010327
0x1800102f7  mov     r11, r12
0x1800102fa  mov     rdx, [r11+10h]
0x1800102fe  test    rdx, rdx
0x180010301  jz      loc_180010C28
0x180010307  movzx   ebx, byte ptr [r14+64h]
0x18001030c  dec     rbx
0x18001030f  lea     rbx, [rbx+rbx*4]
0x180010313  lea     rbx, [rdx+rbx*8]
0x180010317  test    rbx, rbx
0x18001031a  jz      short loc_18001032C
0x18001031c  cmp     qword ptr [rbx+18h], 0
0x180010321  jz      loc_1800109C4
0x180010327  test    rbx, rbx
0x18001032a  jnz     short loc_1800102BA
0x18001032c  mov     rbp, [r13+0]
0x180010330  xor     ebx, ebx
0x180010332  mov     r10d, 200h
0x180010338  nop     dword ptr [rax+rax+00000000h]
0x180010340  test    rdi, rdi
0x180010343  jz      loc_1800102BA
0x180010349  cmp     byte ptr [rdi], 0B0h
0x18001034c  jz      loc_1800108B5
0x180010352  mov     rax, rdi
0x180010355  movzx   eax, byte ptr [rax]
0x180010358  cmp     al, 0A9h
0x18001035a  jz      loc_18001069E
0x180010360  cmp     al, 0A7h
0x180010362  jz      loc_1800106A8
0x180010368  cmp     al, 24h ; '$'
0x18001036a  jz      loc_180010904
0x180010370  cmp     al, 4Dh ; 'M'
0x180010372  jz      loc_1800106A8
0x180010378  cmp     al, 0ADh
0x18001037a  jz      loc_180010904
0x180010380  cmp     al, 0B1h
0x180010382  jz      loc_18001084C
0x180010388  cmp     al, 71h ; 'q'
0x18001038a  jz      loc_1800106DA
0x180010390  mov     eax, [rdi+4]
0x180010393  test    r10d, eax
0x180010396  jz      loc_1800102BA
0x18001039c  mov     rcx, [rdi+10h]
0x1800103a0  test    rcx, rcx
0x1800103a3  jnz     loc_1800109AA
0x1800103a9  mov     rdx, [rdi+18h]
0x1800103ad  bt      eax, 0Ch
0x1800103b1  jb      short loc_1800103C5
0x1800103b3  mov     rcx, [rdi+20h]
0x1800103b7  test    rcx, rcx
0x1800103ba  jz      short loc_1800103C5
0x1800103bc  cmp     [rbp+67h], bl
0x1800103bf  jz      loc_180010987
0x1800103c5  mov     rdi, rdx
0x1800103c8  jmp     loc_180010340
0x1800103cd  cmp     [rdi+40h], rbx
0x1800103d1  jz      loc_1800101B4
0x1800103d7  movsx   rax, word ptr [rdi+30h]
0x1800103dc  test    ax, ax
0x1800103df  js      loc_1800102BF
0x1800103e5  lea     rdx, [rax+rax*2]
0x1800103e9  mov     rax, [rdi+40h]
0x1800103ed  mov     rcx, [rax+8]
0x1800103f1  movzx   eax, word ptr [rcx+rdx*8+12h]
0x1800103f6  test    r10w, ax
0x1800103fa  jnz     loc_180010BCF
0x180010400  mov     rbx, [rbp+10h]
0x180010404  jmp     short loc_18001042A
0x180010406  lea     r12, qword_1800D0DC0
0x18001040d  mov     rdx, [r12+10h]
0x180010412  test    rdx, rdx
0x180010415  jz      loc_180010BF5
0x18001041b  movzx   ebx, byte ptr [rbp+64h]
0x18001041f  dec     rbx
0x180010422  lea     rbx, [rbx+rbx*4]
0x180010426  lea     rbx, [rdx+rbx*8]
0x18001042a  test    rbx, rbx
0x18001042d  jz      loc_1800102BF
0x180010433  cmp     qword ptr [rbx+18h], 0
0x180010438  jnz     loc_1800102BF
0x18001043e  mov     rdx, [r13+0]
0x180010442  mov     r8, rbx
0x180010445  mov     r9, [rbx]
0x180010448  mov     rcx, r13
0x18001044b  movzx   edx, byte ptr [rdx+64h]
0x18001044f  call    sqlite3GetCollSeq
0x180010454  test    rax, rax
0x180010457  jnz     loc_1800102BF
0x18001045d  xor     ebx, ebx
0x18001045f  jmp     loc_1800102BF
0x180010464  cmp     [r8+40h], rbx
0x180010468  jz      loc_18001024C
0x18001046e  movsx   rax, word ptr [r8+30h]
0x180010473  test    ax, ax
0x180010476  js      loc_1800102E7
0x18001047c  lea     rdx, [rax+rax*2]
0x180010480  mov     rax, [r8+40h]
0x180010484  lea     r15, qword_1800B4ED0
0x18001048b  lea     r12, qword_1800D0DC0
0x180010492  mov     rcx, [rax+8]
0x180010496  movzx   r8d, word ptr [rcx+rdx*8+12h]
0x18001049c  test    r10w, r8w
0x1800104a0  jnz     loc_180010C03
0x1800104a6  mov     rbx, [r14+10h]
0x1800104aa  jmp     loc_180010317
0x1800104af  mov     rdi, [rdi+8]
0x1800104b3  movzx   esi, byte ptr [rbp+64h]
0x1800104b7  test    rdi, rdi
0x1800104ba  jz      loc_180010A0E
0x1800104c0  lea     r10, [rbp+270h]
0x1800104c7  mov     r11, [r10+10h]
0x1800104cb  test    r11, r11
0x1800104ce  jnz     loc_1800107C2
0x1800104d4  mov     r11d, [r10+4]
0x1800104d8  mov     r12, [r10+8]
0x1800104dc  lea     r15, qword_1800B4ED0
0x1800104e3  test    r11d, r11d
0x1800104e6  jz      short loc_18001050E
0x1800104e8  mov     rdx, [r12+18h]
0x1800104ed  mov     r8, rdi
0x1800104f0  movzx   r9d, byte ptr [rdx]
0x1800104f4  movzx   eax, byte ptr [r8]
0x1800104f8  cmp     r9d, eax
0x1800104fb  jnz     loc_180010585
0x180010501  test    r9d, r9d
0x180010504  jz      short loc_180010515
0x180010506  inc     rdx
0x180010509  inc     r8
0x18001050c  jmp     short loc_1800104F0
0x18001050e  lea     r12, qword_1800D0DC0
0x180010515  mov     rdx, [r12+10h]
0x18001051a  test    rdx, rdx
0x18001051d  jz      short loc_18001052B
0x18001051f  lea     rbx, [rsi-1]
0x180010523  lea     rbx, [rbx+rbx*4]
0x180010527  lea     rbx, [rdx+rbx*8]
0x18001052b  test    rbx, rbx
0x18001052e  jz      short loc_18001053B
0x180010530  cmp     qword ptr [rbx+18h], 0
0x180010535  jnz     loc_18001042A
0x18001053b  mov     edx, esi
0x18001053d  mov     r8, rdi
0x180010540  mov     rcx, rbp
0x180010543  call    callCollNeeded
0x180010548  xor     r9d, r9d
0x18001054b  mov     r8, rdi
0x18001054e  movzx   edx, sil
0x180010552  mov     rcx, rbp
0x180010555  call    sqlite3FindCollSeq
0x18001055a  mov     rbx, rax
0x18001055d  test    rax, rax
0x180010560  jnz     loc_18001086B
0x180010566  mov     r8, rdi
0x180010569  lea     rdx, aNoSuchCollatio; "no such collation sequence: %s"
0x180010570  mov     rcx, r13
0x180010573  call    sqlite3ErrorMsg
0x180010578  mov     dword ptr [r13+18h], 101h
0x180010580  jmp     loc_18001042A
0x180010585  movzx   ecx, byte ptr [rax+r15]
0x18001058a  movzx   eax, byte ptr [r9+r15]
0x18001058f  cmp     eax, ecx
0x180010591  jz      loc_180010506
0x180010597  mov     r12, [r12]
0x18001059b  dec     r11d
0x18001059e  jmp     loc_1800104E3
0x1800105a3  mov     rsi, [r8+8]
0x1800105a7  lea     r15, qword_1800B4ED0
0x1800105ae  movzx   ebp, byte ptr [r14+64h]
0x1800105b3  lea     r12, qword_1800D0DC0
0x1800105ba  test    rsi, rsi
0x1800105bd  jz      loc_180010A17
0x1800105c3  lea     r10, [r14+270h]
0x1800105ca  mov     r11, [r10+10h]
0x1800105ce  test    r11, r11
0x1800105d1  jnz     loc_1800107E1
0x1800105d7  mov     ebx, [r10+4]
0x1800105db  mov     r11, [r10+8]
0x1800105df  nop
  ... truncated ...
```

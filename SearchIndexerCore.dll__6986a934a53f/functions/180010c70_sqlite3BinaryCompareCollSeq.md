# sqlite3BinaryCompareCollSeq

- ea: `0x180010c70`
- end: `0x180011794`
- name: `sqlite3BinaryCompareCollSeq`
- size: `2852`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000f4a0`
- `0x18000f9f4`
- `0x18000fb00`
- `0x180010100`
- `0x18006e274`
- `0x18007490c`
- `0x180090b7c`

## callees

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
__int64 __fastcall sqlite3BinaryCompareCollSeq(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v6; // rbp
  _QWORD *v7; // rbx
  char *v8; // rax
  char v9; // al
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  __int64 v14; // r14
  char *v15; // rax
  char v16; // al
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdx
  _DWORD *v20; // rcx
  __int64 *v21; // r11
  __int64 v22; // rdx
  __int64 *v24; // r11
  __int64 v25; // rdx
  __int64 v26; // rbp
  char *v27; // rax
  char v28; // al
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rdx
  _DWORD *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int16 v36; // ax
  __int64 *v37; // r12
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int16 v41; // r8
  const char *v42; // rdi
  __int64 v43; // rsi
  int *v44; // r10
  int v45; // r11d
  __int64 *v46; // r12
  _BYTE *v47; // rdx
  const char *i; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 CollSeq; // rax
  const char *v53; // rsi
  __int64 v54; // rbp
  int *v55; // r10
  int v56; // ebx
  __int64 *v57; // r11
  _BYTE *v58; // r8
  const char *n; // r9
  __int64 v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int16 v67; // ax
  const char *v68; // rdi
  __int64 v69; // rsi
  int *v70; // r10
  int v71; // ebx
  __int64 *v72; // r11
  _BYTE *v73; // rdx
  const char *mm; // r8
  __int64 v75; // r9
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rax
  unsigned int v79; // eax
  _DWORD *v80; // r10
  __int64 v81; // r11
  unsigned int v82; // eax
  _DWORD *v83; // r10
  __int64 v84; // r11
  unsigned int v85; // eax
  _DWORD *v86; // r10
  __int64 v87; // r11
  int j; // r8d
  __int64 v89; // rax
  int ii; // r8d
  __int64 v91; // rax
  int nn; // r8d
  __int64 v93; // rax
  unsigned __int8 *v94; // rbx
  int *v95; // r10
  int v96; // r11d
  _BYTE *v97; // r8
  unsigned __int8 *m; // rax
  __int64 v99; // r9
  __int64 v100; // rcx
  unsigned int v101; // eax
  _DWORD *v102; // r10
  __int64 v103; // r11
  unsigned __int8 *v104; // rbx
  int *v105; // r10
  int v106; // esi
  _BYTE *v107; // r8
  unsigned __int8 *kk; // r9
  __int64 v109; // rdx
  __int64 v110; // rax
  unsigned int v111; // eax
  _DWORD *v112; // r10
  __int64 v113; // r11
  unsigned __int8 *v114; // rbx
  int *v115; // r10
  int v116; // edi
  _BYTE *v117; // rdx
  unsigned __int8 *i2; // r8
  __int64 v119; // r9
  __int64 v120; // rax
  unsigned int v121; // eax
  _DWORD *v122; // r10
  __int64 v123; // r11
  _BYTE *k; // r8
  _BYTE *jj; // rax
  _BYTE *i1; // r8

  v4 = a2;
  if ( (*(_DWORD *)(a2 + 4) & 0x200) != 0 )
    return sqlite3ExprCollSeq(a1, a2);
  if ( a3 && (*(_DWORD *)(a3 + 4) & 0x200) != 0 )
  {
    v6 = *(_QWORD *)a1;
    v7 = 0;
    while ( 1 )
    {
      if ( !a3 )
        return (__int64)v7;
      v8 = (char *)(*(_BYTE *)a3 == 0xB0 ? a3 + 2 : a3);
      v9 = *v8;
      if ( v9 == -87 )
        break;
      switch ( v9 )
      {
        case -89:
          goto LABEL_69;
        case 36:
          goto LABEL_157;
        case 77:
          goto LABEL_69;
        case -83:
LABEL_157:
          a3 = *(_QWORD *)(a3 + 16);
          break;
        case -79:
          a3 = *(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL);
          break;
        case 113:
          v42 = *(const char **)(a3 + 8);
          v43 = *(unsigned __int8 *)(v6 + 100);
          if ( v42 )
          {
            v44 = (int *)(v6 + 624);
            if ( *(_QWORD *)(v6 + 640) )
            {
              v79 = strHash(v42);
              v44 = (int *)(v81 + 16LL * (v79 % *v80));
              v45 = *v44;
            }
            else
            {
              v45 = *(_DWORD *)(v6 + 628);
            }
            v46 = (__int64 *)*((_QWORD *)v44 + 1);
LABEL_87:
            if ( v45 )
            {
              v47 = (_BYTE *)v46[3];
              for ( i = v42; ; ++i )
              {
                v49 = (unsigned __int8)*v47;
                v50 = *(unsigned __int8 *)i;
                if ( (_DWORD)v49 == (_DWORD)v50 )
                {
                  if ( !*v47 )
                    goto LABEL_93;
                }
                else if ( *((unsigned __int8 *)qword_1800B4ED0 + v49) != *((unsigned __int8 *)qword_1800B4ED0 + v50) )
                {
                  v46 = (__int64 *)*v46;
                  --v45;
                  goto LABEL_87;
                }
                ++v47;
              }
            }
            v46 = qword_1800D0DC0;
LABEL_93:
            v51 = v46[2];
            if ( v51 )
              v7 = (_QWORD *)(v51 + 40 * (v43 - 1));
          }
          else
          {
            v7 = *(_QWORD **)(v6 + 16);
          }
          if ( !v7 || !v7[3] )
          {
            callCollNeeded(v6, (unsigned int)v43, v42);
            CollSeq = sqlite3FindCollSeq(v6, (unsigned __int8)v43, v42, 0);
            v7 = (_QWORD *)CollSeq;
            if ( !CollSeq )
              goto LABEL_98;
            if ( !*(_QWORD *)(CollSeq + 24) && (unsigned int)synthCollSeq(v6, CollSeq) )
            {
              v7 = 0;
LABEL_98:
              sqlite3ErrorMsg(a1, "no such collation sequence: %s", v42);
              a1[6] = 257;
            }
          }
LABEL_75:
          if ( v7 && !v7[3] && !sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*(_QWORD *)a1 + 100LL), v7, *v7) )
            return 0;
          return (__int64)v7;
        default:
LABEL_15:
          v10 = *(_DWORD *)(a3 + 4);
          if ( (v10 & 0x200) == 0 )
            return (__int64)v7;
          v11 = *(_QWORD *)(a3 + 16);
          if ( v11 && (*(_DWORD *)(v11 + 4) & 0x200) != 0 )
          {
            a3 = *(_QWORD *)(a3 + 16);
          }
          else
          {
            v12 = *(_QWORD *)(a3 + 24);
            if ( (v10 & 0x1000) == 0 )
            {
              v13 = *(_DWORD **)(a3 + 32);
              if ( v13 )
              {
                if ( !*(_BYTE *)(v6 + 103) )
                {
                  for ( j = 0; j < *v13; ++j )
                  {
                    v89 = 8LL * j;
                    if ( (*(_DWORD *)(*(_QWORD *)&v13[v89 + 2] + 4LL) & 0x200) != 0 )
                    {
                      v12 = *(_QWORD *)&v13[v89 + 2];
                      break;
                    }
                  }
                }
              }
            }
            a3 = v12;
          }
          break;
      }
    }
    if ( *(_QWORD *)(a3 + 64) )
    {
LABEL_69:
      v33 = *(__int16 *)(a3 + 48);
      if ( (v33 & 0x8000u) != 0LL )
        return (__int64)v7;
      v34 = 3 * v33;
      v35 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 8LL);
      v36 = *(_WORD *)(v35 + 24 * v33 + 18);
      if ( (v36 & 0x200) == 0 )
        goto LABEL_71;
      for ( k = *(_BYTE **)(v35 + 8 * v34); *k; ++k )
        ;
      if ( (v36 & 4) != 0 )
      {
        do
          ++k;
        while ( *k );
      }
      v94 = k + 1;
      if ( k == (_BYTE *)-1LL )
      {
LABEL_71:
        v7 = *(_QWORD **)(v6 + 16);
      }
      else
      {
        v95 = (int *)(v6 + 624);
        if ( *(_QWORD *)(v6 + 640) )
        {
          v101 = strHash(k + 1);
          v95 = (int *)(v103 + 16LL * (v101 % *v102));
          v96 = *v95;
        }
        else
        {
          v96 = *(_DWORD *)(v6 + 628);
        }
        v37 = (__int64 *)*((_QWORD *)v95 + 1);
LABEL_195:
        if ( v96 )
        {
          v97 = (_BYTE *)v37[3];
          for ( m = v94; ; ++m )
          {
            v99 = (unsigned __int8)*v97;
            v100 = *m;
            if ( (_DWORD)v99 == (_DWORD)v100 )
            {
              if ( !*v97 )
                goto LABEL_73;
            }
            else if ( *((unsigned __int8 *)qword_1800B4ED0 + v99) != *((unsigned __int8 *)qword_1800B4ED0 + v100) )
            {
              v37 = (__int64 *)*v37;
              --v96;
              goto LABEL_195;
            }
            ++v97;
          }
        }
        v37 = qword_1800D0DC0;
LABEL_73:
        v38 = v37[2];
        if ( v38 )
          v7 = (_QWORD *)(v38 + 40 * (*(unsigned __int8 *)(v6 + 100) - 1LL));
        else
          v7 = 0;
      }
      goto LABEL_75;
    }
    goto LABEL_15;
  }
  v7 = 0;
  v14 = *(_QWORD *)a1;
  while ( 1 )
  {
    if ( !v4 )
      goto LABEL_50;
    v15 = (char *)(*(_BYTE *)v4 == 0xB0 ? v4 + 2 : v4);
    v16 = *v15;
    if ( v16 == -87 )
      break;
    switch ( v16 )
    {
      case -89:
        goto LABEL_80;
      case 36:
        goto LABEL_158;
      case 77:
        goto LABEL_80;
      case -83:
LABEL_158:
        v4 = *(_QWORD *)(v4 + 16);
        break;
      case -79:
        v4 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 8LL);
        break;
      case 113:
        v53 = *(const char **)(v4 + 8);
        v54 = *(unsigned __int8 *)(v14 + 100);
        if ( v53 )
        {
          v55 = (int *)(v14 + 624);
          if ( *(_QWORD *)(v14 + 640) )
          {
            v82 = strHash(*(_QWORD *)(v4 + 8));
            v55 = (int *)(v84 + 16LL * (v82 % *v83));
            v56 = *v55;
          }
          else
          {
            v56 = *(_DWORD *)(v14 + 628);
          }
          v57 = (__int64 *)*((_QWORD *)v55 + 1);
LABEL_105:
          if ( v56 )
          {
            v58 = (_BYTE *)v57[3];
            for ( n = v53; ; ++n )
            {
              v60 = (unsigned __int8)*v58;
              v61 = *(unsigned __int8 *)n;
              if ( (_DWORD)v60 == (_DWORD)v61 )
              {
                if ( !*v58 )
                  goto LABEL_111;
              }
              else if ( *((unsigned __int8 *)qword_1800B4ED0 + v60) != *((unsigned __int8 *)qword_1800B4ED0 + v61) )
              {
                v57 = (__int64 *)*v57;
                --v56;
                goto LABEL_105;
              }
              ++v58;
            }
          }
          v57 = qword_1800D0DC0;
LABEL_111:
          v62 = v57[2];
          if ( v62 )
            v7 = (_QWORD *)(v62 + 40 * (v54 - 1));
          else
            v7 = 0;
        }
        else
        {
          v7 = *(_QWORD **)(v14 + 16);
        }
        if ( !v7 || !v7[3] )
        {
          callCollNeeded(v14, (unsigned int)v54, v53);
          v63 = sqlite3FindCollSeq(v14, (unsigned __int8)v54, v53, 0);
          v7 = (_QWORD *)v63;
          if ( v63 )
          {
            if ( *(_QWORD *)(v63 + 24) || !(unsigned int)synthCollSeq(v14, v63) )
              goto LABEL_48;
            v7 = 0;
          }
          sqlite3ErrorMsg(a1, "no such collation sequence: %s", v53);
          a1[6] = 257;
        }
LABEL_48:
        if ( v7 && (v7[3] || sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*(_QWORD *)a1 + 100LL), v7, *v7)) )
          goto LABEL_50;
        goto LABEL_51;
      default:
LABEL_32:
        v17 = *(_DWORD *)(v4 + 4);
        if ( (v17 & 0x200) == 0 )
          goto LABEL_50;
        v18 = *(_QWORD *)(v4 + 16);
        if ( v18 && (*(_DWORD *)(v18 + 4) & 0x200) != 0 )
        {
          v4 = *(_QWORD *)(v4 + 16);
        }
        else
        {
          v19 = *(_QWORD *)(v4 + 24);
          if ( (v17 & 0x1000) == 0 )
          {
            v20 = *(_DWORD **)(v4 + 32);
            if ( v20 )
            {
              if ( !*(_BYTE *)(v14 + 103) )
              {
                for ( ii = 0; ii < *v20; ++ii )
                {
                  v91 = 8LL * ii;
                  if ( (*(_DWORD *)(*(_QWORD *)&v20[v91 + 2] + 4LL) & 0x200) != 0 )
                  {
                    v19 = *(_QWORD *)&v20[v91 + 2];
                    break;
                  }
                }
              }
            }
          }
          v4 = v19;
        }
        break;
    }
  }
  if ( !*(_QWORD *)(v4 + 64) )
    goto LABEL_32;
LABEL_80:
  v39 = *(__int16 *)(v4 + 48);
  if ( (v39 & 0x8000u) == 0LL )
  {
    v40 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 8LL);
    v41 = *(_WORD *)(v40 + 24 * v39 + 18);
    if ( (v41 & 0x200) == 0 )
      goto LABEL_82;
    for ( jj = *(_BYTE **)(v40 + 24 * v39); *jj; ++jj )
      ;
    if ( (v41 & 4) != 0 )
    {
      do
        ++jj;
      while ( *jj );
    }
    v104 = jj + 1;
    if ( jj == (_BYTE *)-1LL )
    {
LABEL_82:
      v7 = *(_QWORD **)(v14 + 16);
    }
    else
    {
      v105 = (int *)(v14 + 624);
      if ( *(_QWORD *)(v14 + 640) )
      {
        v111 = strHash(jj + 1);
        v105 = (int *)(v113 + 16LL * (v111 % *v112));
        v106 = *v105;
      }
      else
      {
        v106 = *(_DWORD *)(v14 + 628);
      }
      v24 = (__int64 *)*((_QWORD *)v105 + 1);
LABEL_207:
      if ( v106 )
      {
        v107 = (_BYTE *)v24[3];
        for ( kk = v104; ; ++kk )
        {
          v109 = (unsigned __int8)*v107;
          v110 = *kk;
          if ( (_DWORD)v109 == (_DWORD)v110 )
          {
            if ( !*v107 )
              goto LABEL_46;
          }
          else if ( *((unsigned __int8 *)qword_1800B4ED0 + v109) != *((unsigned __int8 *)qword_1800B4ED0 + v110) )
          {
            v24 = (__int64 *)*v24;
            --v106;
            goto LABEL_207;
          }
          ++v107;
        }
      }
      v24 = qword_1800D0DC0;
LABEL_46:
      v25 = v24[2];
      if ( v25 )
        v7 = (_QWORD *)(v25 + 40 * (*(unsigned __int8 *)(v14 + 100) - 1LL));
      else
        v7 = 0;
    }
    goto LABEL_48;
  }
LABEL_50:
  if ( !v7 )
  {
LABEL_51:
    v26 = *(_QWORD *)a1;
    v7 = 0;
    while ( 1 )
    {
      if ( !a3 )
        return (__int64)v7;
      v27 = (char *)(*(_BYTE *)a3 == 0xB0 ? a3 + 2 : a3);
      v28 = *v27;
      if ( v28 == -87 )
        break;
      switch ( v28 )
      {
        case -89:
          goto LABEL_120;
        case 36:
          goto LABEL_162;
        case 77:
          goto LABEL_120;
        case -83:
LABEL_162:
          a3 = *(_QWORD *)(a3 + 16);
          break;
        case -79:
          a3 = *(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL);
          break;
        case 113:
          v68 = *(const char **)(a3 + 8);
          v69 = *(unsigned __int8 *)(v26 + 100);
          if ( v68 )
          {
            v70 = (int *)(v26 + 624);
            if ( *(_QWORD *)(v26 + 640) )
            {
              v85 = strHash(v68);
              v70 = (int *)(v87 + 16LL * (v85 % *v86));
              v71 = *v70;
            }
            else
            {
              v71 = *(_DWORD *)(v26 + 628);
            }
            v72 = (__int64 *)*((_QWORD *)v70 + 1);
LABEL_127:
            if ( v71 )
            {
              v73 = (_BYTE *)v72[3];
              for ( mm = v68; ; ++mm )
              {
                v75 = (unsigned __int8)*v73;
                v76 = *(unsigned __int8 *)mm;
                if ( (_DWORD)v75 == (_DWORD)v76 )
                {
                  if ( !*v73 )
                    goto LABEL_133;
                }
                else if ( *((unsigned __int8 *)qword_1800B4ED0 + v75) != *((unsigned __int8 *)qword_1800B4ED0 + v76) )
                {
                  v72 = (__int64 *)*v72;
                  --v71;
                  goto LABEL_127;
                }
                ++v73;
              }
            }
            v72 = qword_1800D0DC0;
LABEL_133:
            v77 = v72[2];
            if ( v77 )
              v7 = (_QWORD *)(v77 + 40 * (v69 - 1));
            else
              v7 = 0;
          }
          else
          {
            v7 = *(_QWORD **)(v26 + 16);
          }
          if ( !v7 || !v7[3] )
          {
            callCollNeeded(v26, (unsigned int)v69, v68);
            v78 = sqlite3FindCollSeq(v26, (unsigned __int8)v69, v68, 0);
            v7 = (_QWORD *)v78;
            if ( !v78 )
              goto LABEL_138;
            if ( !*(_QWORD *)(v78 + 24) && (unsigned int)synthCollSeq(v26, v78) )
            {
              v7 = 0;
LABEL_138:
              sqlite3ErrorMsg(a1, "no such collation sequence: %s", v68);
              a1[6] = 257;
            }
          }
LABEL_41:
          if ( v7 && !v7[3] && !sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*(_QWORD *)a1 + 100LL), v7, *v7) )
            return 0;
          return (__int64)v7;
        default:
LABEL_62:
          v29 = *(_DWORD *)(a3 + 4);
          if ( (v29 & 0x200) == 0 )
            return (__int64)v7;
          v30 = *(_QWORD *)(a3 + 16);
          if ( v30 && (*(_DWORD *)(v30 + 4) & 0x200) != 0 )
          {
            a3 = *(_QWORD *)(a3 + 16);
          }
          else
          {
            v31 = *(_QWORD *)(a3 + 24);
            if ( (v29 & 0x1000) == 0 )
            {
              v32 = *(_DWORD **)(a3 + 32);
              if ( v32 )
              {
                if ( !*(_BYTE *)(v26 + 103) )
                {
                  for ( nn = 0; nn < *v32; ++nn )
                  {
                    v93 = 8LL * nn;
                    if ( (*(_DWORD *)(*(_QWORD *)&v32[v93 + 2] + 4LL) & 0x200) != 0 )
                    {
                      v31 = *(_QWORD *)&v32[v93 + 2];
                      break;
                    }
                  }
                }
              }
            }
            a3 = v31;
          }
          break;
      }
    }
    if ( *(_QWORD *)(a3 + 64) )
    {
LABEL_120:
      v64 = *(__int16 *)(a3 + 48);
      if ( (v64 & 0x8000u) != 0LL )
        return (__int64)v7;
      v65 = 3 * v64;
      v66 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 8LL);
      v67 = *(_WORD *)(v66 + 24 * v64 + 18);
      if ( (v67 & 0x200) == 0 )
        goto LABEL_122;
      for ( i1 = *(_BYTE **)(v66 + 8 * v65); *i1; ++i1 )
        ;
      if ( (v67 & 4) != 0 )
      {
        do
          ++i1;
        while ( *i1 );
      }
      v114 = i1 + 1;
      if ( i1 == (_BYTE *)-1LL )
      {
LABEL_122:
        v7 = *(_QWORD **)(v26 + 16);
      }
      else
      {
        v115 = (int *)(v26 + 624);
        if ( *(_QWORD *)(v26 + 640) )
        {
          v121 = strHash(i1 + 1);
          v115 = (int *)(v123 + 16LL * (v121 % *v122));
          v116 = *v115;
        }
        else
        {
          v116 = *(_DWORD *)(v26 + 628);
        }
        v21 = (__int64 *)*((_QWORD *)v115 + 1);
LABEL_219:
        if ( v116 )
        {
          v117 = (_BYTE *)v21[3];
          for ( i2 = v114; ; ++i2 )
          {
            v119 = (unsigned __int8)*v117;
            v120 = *i2;
            if ( (_DWORD)v119 == (_DWORD)v120 )
            {
              if ( !*v117 )
                goto LABEL_39;
            }
            else if ( *((unsigned __int8 *)qword_1800B4ED0 + v119) != *((unsigned __int8 *)qword_1800B4ED0 + v120) )
            {
              v21 = (__int64 *)*v21;
              --v116;
              goto LABEL_219;
            }
            ++v117;
          }
        }
        v21 = qword_1800D0DC0;
LABEL_39:
        v22 = v21[2];
        if ( v22 )
          v7 = (_QWORD *)(v22 + 40 * (*(unsigned __int8 *)(v26 + 100) - 1LL));
        else
          v7 = 0;
      }
      goto LABEL_41;
    }
    goto LABEL_62;
  }
  return (__int64)v7;
}

```

## disassembly

```asm
0x180010c70  push    rdi
0x180010c72  push    r13
0x180010c74  sub     rsp, 38h
0x180010c78  mov     r10d, 200h
0x180010c7e  mov     rdi, r8
0x180010c81  mov     r8, rdx
0x180010c84  mov     r13, rcx
0x180010c87  test    [rdx+4], r10d
0x180010c8b  jnz     loc_18001136F
0x180010c91  mov     [rsp+48h+arg_0], rbx
0x180010c96  mov     [rsp+48h+arg_8], rbp
0x180010c9b  mov     [rsp+48h+arg_10], rsi
0x180010ca0  mov     [rsp+48h+var_18], r12
0x180010ca5  mov     [rsp+48h+var_28], r15
0x180010caa  test    rdi, rdi
0x180010cad  jz      loc_180010D4F
0x180010cb3  test    [rdi+4], r10d
0x180010cb7  jz      loc_180010D4F
0x180010cbd  mov     rbp, [rcx]
0x180010cc0  xor     ebx, ebx
0x180010cc2  test    rdi, rdi
0x180010cc5  jz      loc_180010E1D
0x180010ccb  cmp     byte ptr [rdi], 0B0h
0x180010cce  jz      loc_1800113A2
0x180010cd4  mov     rax, rdi
0x180010cd7  movzx   eax, byte ptr [rax]
0x180010cda  cmp     al, 0A9h
0x180010cdc  jz      loc_180010F1B
0x180010ce2  cmp     al, 0A7h
0x180010ce4  jz      loc_180010F25
0x180010cea  cmp     al, 24h ; '$'
0x180010cec  jz      loc_180011407
0x180010cf2  cmp     al, 4Dh ; 'M'
0x180010cf4  jz      loc_180010F25
0x180010cfa  cmp     al, 0ADh
0x180010cfc  jz      loc_180011407
0x180010d02  cmp     al, 0B1h
0x180010d04  jz      loc_18001137B
0x180010d0a  cmp     al, 71h ; 'q'
0x180010d0c  jz      loc_180010FFD
0x180010d12  mov     eax, [rdi+4]
0x180010d15  test    r10d, eax
0x180010d18  jz      loc_180010E1D
0x180010d1e  mov     rcx, [rdi+10h]
0x180010d22  test    rcx, rcx
0x180010d25  jnz     loc_18001146A
0x180010d2b  mov     rdx, [rdi+18h]
0x180010d2f  bt      eax, 0Ch
0x180010d33  jb      short loc_180010D47
0x180010d35  mov     rcx, [rdi+20h]
0x180010d39  test    rcx, rcx
0x180010d3c  jz      short loc_180010D47
0x180010d3e  cmp     [rbp+67h], bl
0x180010d41  jz      loc_180011447
0x180010d47  mov     rdi, rdx
0x180010d4a  jmp     loc_180010CC2
0x180010d4f  mov     [rsp+48h+var_20], r14
0x180010d54  xor     ebx, ebx
0x180010d56  mov     r14, [rcx]
0x180010d59  test    r8, r8
0x180010d5c  jz      loc_180010E41
0x180010d62  cmp     byte ptr [r8], 0B0h
0x180010d66  jz      loc_1800113AB
0x180010d6c  mov     rax, r8
0x180010d6f  movzx   eax, byte ptr [rax]
0x180010d72  cmp     al, 0A9h
0x180010d74  jz      loc_180010FB2
0x180010d7a  cmp     al, 0A7h
0x180010d7c  jz      loc_180010FBC
0x180010d82  cmp     al, 24h ; '$'
0x180010d84  jz      loc_180011410
0x180010d8a  cmp     al, 4Dh ; 'M'
0x180010d8c  jz      loc_180010FBC
0x180010d92  cmp     al, 0ADh
0x180010d94  jz      loc_180011410
0x180010d9a  cmp     al, 0B1h
0x180010d9c  jz      loc_180011388
0x180010da2  cmp     al, 71h ; 'q'
0x180010da4  jz      loc_1800110F3
0x180010daa  mov     eax, [r8+4]
0x180010dae  test    r10d, eax
0x180010db1  jz      loc_180010E41
0x180010db7  mov     rcx, [r8+10h]
0x180010dbb  test    rcx, rcx
0x180010dbe  jnz     loc_1800114A7
0x180010dc4  mov     rdx, [r8+18h]
0x180010dc8  bt      eax, 0Ch
0x180010dcc  jb      short loc_180010DE1
0x180010dce  mov     rcx, [r8+20h]
0x180010dd2  test    rcx, rcx
0x180010dd5  jz      short loc_180010DE1
0x180010dd7  cmp     [r14+67h], bl
0x180010ddb  jz      loc_180011484
0x180010de1  mov     r8, rdx
0x180010de4  jmp     loc_180010D59
0x180010de9  mov     r11, r12
0x180010dec  mov     rdx, [r11+10h]
0x180010df0  test    rdx, rdx
0x180010df3  jz      loc_18001178D
0x180010df9  movzx   ebx, byte ptr [rbp+64h]
0x180010dfd  dec     rbx
0x180010e00  lea     rbx, [rbx+rbx*4]
0x180010e04  lea     rbx, [rdx+rbx*8]
0x180010e08  test    rbx, rbx
0x180010e0b  jz      short loc_180010E18
0x180010e0d  cmp     qword ptr [rbx+18h], 0
0x180010e12  jz      loc_180011522
0x180010e18  mov     r14, [rsp+48h+var_20]
0x180010e1d  mov     r12, [rsp+48h+var_18]
0x180010e22  mov     rax, rbx
0x180010e25  mov     rbx, [rsp+48h+arg_0]
0x180010e2a  mov     rsi, [rsp+48h+arg_10]
0x180010e2f  mov     rbp, [rsp+48h+arg_8]
0x180010e34  mov     r15, [rsp+48h+var_28]
0x180010e39  add     rsp, 38h
0x180010e3d  pop     r13
0x180010e3f  pop     rdi
0x180010e40  retn
0x180010e41  lea     r15, qword_1800B4ED0
0x180010e48  lea     r12, qword_1800D0DC0
0x180010e4f  jmp     short loc_180010E81
0x180010e51  mov     r11, r12
0x180010e54  mov     rdx, [r11+10h]
0x180010e58  test    rdx, rdx
0x180010e5b  jz      loc_180011759
0x180010e61  movzx   ebx, byte ptr [r14+64h]
0x180010e66  dec     rbx
0x180010e69  lea     rbx, [rbx+rbx*4]
0x180010e6d  lea     rbx, [rdx+rbx*8]
0x180010e71  test    rbx, rbx
0x180010e74  jz      short loc_180010E86
0x180010e76  cmp     qword ptr [rbx+18h], 0
0x180010e7b  jz      loc_1800114FE
0x180010e81  test    rbx, rbx
0x180010e84  jnz     short loc_180010E18
0x180010e86  mov     rbp, [r13+0]
0x180010e8a  xor     ebx, ebx
0x180010e8c  mov     r10d, 200h
0x180010e92  test    rdi, rdi
0x180010e95  jz      short loc_180010E18
0x180010e97  cmp     byte ptr [rdi], 0B0h
0x180010e9a  jz      loc_1800113FE
0x180010ea0  mov     rax, rdi
0x180010ea3  movzx   eax, byte ptr [rax]
0x180010ea6  cmp     al, 0A9h
0x180010ea8  jz      loc_1800111EE
0x180010eae  cmp     al, 0A7h
0x180010eb0  jz      loc_1800111F8
0x180010eb6  cmp     al, 24h ; '$'
0x180010eb8  jz      loc_18001143E
0x180010ebe  cmp     al, 4Dh ; 'M'
0x180010ec0  jz      loc_1800111F8
0x180010ec6  cmp     al, 0ADh
0x180010ec8  jz      loc_18001143E
0x180010ece  cmp     al, 0B1h
0x180010ed0  jz      loc_180011395
0x180010ed6  cmp     al, 71h ; 'q'
0x180010ed8  jz      loc_18001122A
0x180010ede  mov     eax, [rdi+4]
0x180010ee1  test    r10d, eax
0x180010ee4  jz      loc_180010E18
0x180010eea  mov     rcx, [rdi+10h]
0x180010eee  test    rcx, rcx
0x180010ef1  jnz     loc_1800114E4
0x180010ef7  mov     rdx, [rdi+18h]
0x180010efb  bt      eax, 0Ch
0x180010eff  jb      short loc_180010F13
0x180010f01  mov     rcx, [rdi+20h]
0x180010f05  test    rcx, rcx
0x180010f08  jz      short loc_180010F13
0x180010f0a  cmp     [rbp+67h], bl
0x180010f0d  jz      loc_1800114C1
0x180010f13  mov     rdi, rdx
0x180010f16  jmp     loc_180010E92
0x180010f1b  cmp     [rdi+40h], rbx
0x180010f1f  jz      loc_180010D12
0x180010f25  movsx   rax, word ptr [rdi+30h]
0x180010f2a  test    ax, ax
0x180010f2d  js      loc_180010E1D
0x180010f33  lea     rdx, [rax+rax*2]
0x180010f37  mov     rax, [rdi+40h]
0x180010f3b  mov     rcx, [rax+8]
0x180010f3f  movzx   eax, word ptr [rcx+rdx*8+12h]
0x180010f44  test    r10w, ax
0x180010f48  jnz     loc_180011700
0x180010f4e  mov     rbx, [rbp+10h]
0x180010f52  jmp     short loc_180010F78
0x180010f54  lea     r12, qword_1800D0DC0
0x180010f5b  mov     rdx, [r12+10h]
0x180010f60  test    rdx, rdx
0x180010f63  jz      loc_180011726
0x180010f69  movzx   ebx, byte ptr [rbp+64h]
0x180010f6d  dec     rbx
0x180010f70  lea     rbx, [rbx+rbx*4]
0x180010f74  lea     rbx, [rdx+rbx*8]
0x180010f78  test    rbx, rbx
0x180010f7b  jz      loc_180010E1D
0x180010f81  cmp     qword ptr [rbx+18h], 0
0x180010f86  jnz     loc_180010E1D
0x180010f8c  mov     rdx, [r13+0]
0x180010f90  mov     r8, rbx
0x180010f93  mov     r9, [rbx]
0x180010f96  mov     rcx, r13
0x180010f99  movzx   edx, byte ptr [rdx+64h]
0x180010f9d  call    sqlite3GetCollSeq
0x180010fa2  test    rax, rax
0x180010fa5  jnz     loc_180010E1D
0x180010fab  xor     ebx, ebx
0x180010fad  jmp     loc_180010E1D
0x180010fb2  cmp     [r8+40h], rbx
0x180010fb6  jz      loc_180010DAA
0x180010fbc  movsx   rax, word ptr [r8+30h]
0x180010fc1  test    ax, ax
0x180010fc4  js      loc_180010E41
0x180010fca  lea     rdx, [rax+rax*2]
0x180010fce  mov     rax, [r8+40h]
0x180010fd2  lea     r15, qword_1800B4ED0
0x180010fd9  lea     r12, qword_1800D0DC0
0x180010fe0  mov     rcx, [rax+8]
0x180010fe4  movzx   r8d, word ptr [rcx+rdx*8+12h]
0x180010fea  test    r10w, r8w
0x180010fee  jnz     loc_180011734
0x180010ff4  mov     rbx, [r14+10h]
0x180010ff8  jmp     loc_180010E71
0x180010ffd  mov     rdi, [rdi+8]
0x180011001  movzx   esi, byte ptr [rbp+64h]
0x180011005  test    rdi, rdi
0x180011008  jz      loc_180011548
0x18001100e  lea     r10, [rbp+270h]
0x180011015  mov     r11, [r10+10h]
0x180011019  test    r11, r11
0x18001101c  jnz     loc_180011312
0x180011022  mov     r11d, [r10+4]
0x180011026  mov     r12, [r10+8]
0x18001102a  lea     r15, qword_1800B4ED0
0x180011031  test    r11d, r11d
0x180011034  jz      short loc_18001105E
0x180011036  mov     rdx, [r12+18h]
0x18001103b  mov     r8, rdi
0x18001103e  xchg    ax, ax
0x180011040  movzx   r9d, byte ptr [rdx]
0x180011044  movzx   eax, byte ptr [r8]
0x180011048  cmp     r9d, eax
0x18001104b  jnz     loc_1800110D5
0x180011051  test    r9d, r9d
0x180011054  jz      short loc_180011065
0x180011056  inc     rdx
0x180011059  inc     r8
0x18001105c  jmp     short loc_180011040
0x18001105e  lea     r12, qword_1800D0DC0
0x180011065  mov     rdx, [r12+10h]
0x18001106a  test    rdx, rdx
0x18001106d  jz      short loc_18001107B
0x18001106f  lea     rbx, [rsi-1]
0x180011073  lea     rbx, [rbx+rbx*4]
0x180011077  lea     rbx, [rdx+rbx*8]
0x18001107b  test    rbx, rbx
0x18001107e  jz      short loc_18001108B
0x180011080  cmp     qword ptr [rbx+18h], 0
0x180011085  jnz     loc_180010F78
0x18001108b  mov     edx, esi
0x18001108d  mov     r8, rdi
0x180011090  mov     rcx, rbp
0x180011093  call    callCollNeeded
0x180011098  xor     r9d, r9d
0x18001109b  mov     r8, rdi
0x18001109e  movzx   edx, sil
0x1800110a2  mov     rcx, rbp
0x1800110a5  call    sqlite3FindCollSeq
0x1800110aa  mov     rbx, rax
0x1800110ad  test    rax, rax
0x1800110b0  jnz     loc_1800113B4
0x1800110b6  mov     r8, rdi
0x1800110b9  lea     rdx, aNoSuchCollatio; "no such collation sequence: %s"
0x1800110c0  mov     rcx, r13
0x1800110c3  call    sqlite3ErrorMsg
0x1800110c8  mov     dword ptr [r13+18h], 101h
0x1800110d0  jmp     loc_180010F78
0x1800110d5  movzx   ecx, byte ptr [rax+r15]
0x1800110da  movzx   eax, byte ptr [r9+r15]
0x1800110df  cmp     eax, ecx
0x1800110e1  jz      loc_180011056
0x1800110e7  mov     r12, [r12]
0x1800110eb  dec     r11d
0x1800110ee  jmp     loc_180011031
0x1800110f3  mov     rsi, [r8+8]
0x1800110f7  lea     r15, qword_1800B4ED0
0x1800110fe  movzx   ebp, byte ptr [r14+64h]
0x180011103  lea     r12, qword_1800D0DC0
0x18001110a  test    rsi, rsi
0x18001110d  jz      loc_180011551
0x180011113  lea     r10, [r14+270h]
0x18001111a  mov     r11, [r10+10h]
0x18001111e  test    r11, r11
0x180011121  jnz     loc_180011331
0x180011127  mov     ebx, [r10+4]
0x18001112b  mov     r11, [r10+8]
0x18001112f  nop
0x180011130  test    ebx, ebx
0x180011132  jz      short loc_18001115C
  ... truncated ...
```

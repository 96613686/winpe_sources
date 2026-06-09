# MStringCommon(ushort const *,ushort const *,CBuffer &)

- ea: `0x18000aa80`
- end: `0x18000bcea`
- name: `?MStringCommon@@YAKPEBG0AEAVCBuffer@@@Z`
- size: `4714`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct CBuffer *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009480`

## callees

- `0x18000aa80`
- `0x18000bcf0`
- `0x18000bd10`
- `0x180013b20`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18001c7a8`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000abde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000afab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b64f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000abde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000afab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b64f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MStringCommon(const unsigned __int16 *a1, const unsigned __int16 *a2, struct CBuffer *a3)
{
  unsigned int v3; // r15d
  unsigned int v4; // r12d
  int v5; // ebx
  char *v6; // r13
  const unsigned __int16 *i; // rsi
  __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  char *v10; // r14
  unsigned int j; // eax
  unsigned int v12; // r14d
  unsigned int v13; // esi
  __int64 k; // rdi
  const WCHAR *v15; // rdx
  __int64 v16; // r15
  const WCHAR *v17; // rcx
  int v18; // eax
  __int64 v19; // r13
  _QWORD *v20; // rcx
  __int64 v21; // r12
  unsigned __int64 v22; // rdx
  _QWORD *v23; // r14
  __int64 v24; // rax
  unsigned int v25; // r9d
  _QWORD *m; // r8
  unsigned __int64 v27; // rdx
  _QWORD *v28; // r14
  __int64 v29; // rax
  _QWORD *n; // r8
  int v31; // ebx
  unsigned int ii; // edx
  __int64 v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // ebx
  void *v36; // rax
  unsigned int v37; // ecx
  unsigned int v38; // edi
  _WORD *v39; // rbx
  __int64 v40; // rax
  unsigned int v41; // r14d
  unsigned int v42; // esi
  unsigned __int64 v43; // rdx
  void *v44; // rdi
  unsigned int v45; // ebx
  unsigned __int64 v46; // rdx
  void *v47; // rdi
  void *v48; // rdx
  unsigned int v49; // r13d
  int v50; // ebx
  char *v51; // r12
  const unsigned __int16 *jj; // rsi
  __int64 v53; // rdi
  unsigned __int64 v54; // rdx
  char *v55; // r14
  unsigned int kk; // eax
  unsigned int v57; // r14d
  unsigned int v58; // esi
  __int64 mm; // rdi
  const WCHAR *v60; // rdx
  __int64 v61; // r14
  const WCHAR *v62; // rcx
  int v63; // eax
  unsigned __int64 v64; // rdx
  char *v65; // r15
  __int64 nn; // rax
  unsigned __int64 v67; // rdx
  char *v68; // r14
  __int64 i1; // rax
  int v70; // ebx
  unsigned __int64 i2; // rdx
  __int64 v72; // rcx
  __int64 v73; // rax
  unsigned int v74; // ebx
  char *v75; // rax
  char *v76; // rsi
  unsigned int v77; // ecx
  unsigned int v78; // edi
  _WORD *v79; // rbx
  __int64 v80; // rax
  unsigned int v81; // r14d
  unsigned int v82; // esi
  unsigned __int64 v83; // rdx
  char *v84; // rdi
  unsigned int v85; // ebx
  int v86; // r15d
  char *v87; // rdi
  unsigned int v88; // r14d
  const unsigned __int16 *v89; // rbx
  const unsigned __int16 *v90; // rcx
  void *v91; // r12
  const WCHAR *String; // rdi
  unsigned __int64 v93; // rdx
  const WCHAR *v94; // r15
  struct CBuffer *v95; // r15
  unsigned int v96; // eax
  unsigned int v97; // ebx
  unsigned int v98; // ecx
  void *v99; // rdi
  void *v100; // rcx
  void *v101; // rax
  void *v102; // r12
  unsigned __int64 v103; // rdx
  char *v104; // rax
  unsigned __int64 v105; // rdx
  unsigned int v106; // ecx
  unsigned int v107; // r15d
  unsigned int v108; // ebx
  __int64 v109; // r8
  unsigned int v110; // ecx
  unsigned int v111; // r15d
  unsigned int v112; // ebx
  __int64 v113; // r8
  void *v114; // rax
  void *v115; // rsi
  unsigned __int64 v116; // rdx
  char *v117; // rax
  unsigned __int64 v118; // rdx
  _DWORD *v119; // rax
  unsigned __int64 v120; // rdx
  char *v121; // rax
  struct CBuffer *v122; // rsi
  unsigned int v123; // eax
  unsigned int v124; // ebx
  unsigned int v125; // ecx
  unsigned __int64 v126; // rdx
  void *v127; // rdi
  void *v128; // rcx
  void *v130; // rax
  void *v131; // rdi
  unsigned __int64 v132; // rdx
  int v133; // eax
  __int64 v134; // rax
  unsigned int v135; // ebx
  struct CBuffer *v136; // r13
  unsigned int v137; // eax
  unsigned int v138; // esi
  unsigned int v139; // ecx
  unsigned __int64 v140; // rdx
  void *v141; // r12
  void *v142; // rcx
  const unsigned __int16 *v143; // rax
  void *v144; // rax
  void *v145; // r12
  unsigned __int64 v146; // rdx
  void *v147; // rax
  void *v148; // rdi
  unsigned __int64 v149; // rdx
  __int64 v150; // r8
  __int64 v151; // r8
  void **v152; // [rsp+20h] [rbp-49h] BYREF
  int v153; // [rsp+28h] [rbp-41h]
  unsigned int v154; // [rsp+2Ch] [rbp-3Dh]
  void *v155; // [rsp+30h] [rbp-39h]
  void *Src; // [rsp+38h] [rbp-31h]
  void *v157; // [rsp+40h] [rbp-29h]
  const int *v158; // [rsp+48h] [rbp-21h]
  char *v159; // [rsp+50h] [rbp-19h]
  __int64 v160; // [rsp+58h] [rbp-11h]
  const int *v161; // [rsp+60h] [rbp-9h]
  _DWORD *v162; // [rsp+68h] [rbp-1h]
  __int64 v163; // [rsp+70h] [rbp+7h]
  __int64 v164; // [rsp+78h] [rbp+Fh]
  char *v165; // [rsp+80h] [rbp+17h]
  struct CBuffer *pExceptionObject; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v168; // [rsp+E8h] [rbp+7Fh]

  pExceptionObject = a3;
  v161 = &CBuffer::`vftable';
  v3 = 0;
  Src = 0;
  v162 = 0;
  v163 = 0;
  v158 = &CBuffer::`vftable';
  v157 = 0;
  v159 = 0;
  v160 = 0;
  *((_DWORD *)a3 + 4) = 0;
  v152 = &CDynamicArray<unsigned short const>::`vftable';
  v4 = 0;
  v154 = 0;
  v5 = 0;
  v153 = 0;
  v6 = 0;
  v155 = 0;
  for ( i = FirstString(a1); i; i = NextString(i) )
  {
    v8 = v4;
    if ( v4 >= v5 )
    {
      if ( !v5 )
        v5 = 4;
      for ( ; (int)v4 >= v5; v5 *= 2 )
        ;
      v10 = (char *)operator new[](saturated_mul(v5, 8u));
      if ( !v10 )
      {
        LODWORD(pExceptionObject) = 14;
        throw (ulong *)&pExceptionObject;
      }
      for ( j = 0; j < v4; ++j )
      {
        v150 = 8LL * j;
        v9 = *(_QWORD *)&v6[v150];
        *(_QWORD *)&v10[v150] = v9;
      }
      if ( v6 )
        operator delete(v6, v9);
      v6 = v10;
      v155 = v10;
      v153 = v5;
    }
    ++v4;
    v154 = v8 + 1;
    *(_QWORD *)&v6[8 * v8] = i;
  }
  v12 = v4;
  v168 = v4;
  if ( v4 )
  {
    v13 = 0;
    LODWORD(v164) = 0;
    do
    {
      for ( k = v12 - 1; v13 < (unsigned int)k; v3 = 0 )
      {
        if ( v4 <= (unsigned int)k )
          v15 = 0;
        else
          v15 = *(const WCHAR **)&v6[8 * (int)k];
        v16 = (unsigned int)(k - 1);
        if ( v4 <= (unsigned int)v16 )
          v17 = 0;
        else
          v17 = *(const WCHAR **)&v6[8 * (int)v16];
        v18 = lstrcmpiW(v17, v15);
        if ( v18 <= 0 )
        {
          if ( !v18 )
          {
            v106 = k;
            v107 = v168;
            v12 = v168 - 1;
            if ( (unsigned int)k < v168 - 1 )
            {
              while ( 1 )
              {
                v108 = v106 + 1;
                v109 = v4 <= v106 + 1 ? 0LL : *((_QWORD *)v155 + (int)v108);
                CDynamicArray<unsigned short const>::Set(&v152, v106, v109);
                v106 = v108;
                if ( v108 >= v12 )
                  break;
                v4 = v154;
              }
              v13 = v164;
            }
            CDynamicArray<unsigned short const>::Set(&v152, v107 - 1, 0);
            v168 = v12;
            v5 = v153;
            v6 = (char *)v155;
            v4 = v154;
            goto LABEL_46;
          }
        }
        else
        {
          if ( v4 <= (unsigned int)v16 )
            v19 = 0;
          else
            v19 = *(_QWORD *)&v6[8 * (int)v16];
          v20 = v155;
          if ( v4 <= (unsigned int)k )
            v21 = 0;
          else
            v21 = *((_QWORD *)v155 + (int)k);
          if ( (unsigned int)v16 < v5 )
          {
            v25 = v154;
          }
          else
          {
            if ( !v5 )
              v5 = 4;
            for ( ; (int)v16 >= v5; v5 *= 2 )
              ;
            v23 = operator new[](saturated_mul(v5, 8u));
            if ( !v23 )
            {
              LODWORD(pExceptionObject) = 14;
              throw (ulong *)&pExceptionObject;
            }
            v24 = 0;
            v25 = v154;
            for ( m = v155; (unsigned int)v24 < v25; v24 = (unsigned int)(v24 + 1) )
            {
              v22 = 8 * v24;
              v23[v24] = m[v24];
            }
            if ( m )
            {
              operator delete(m, v22);
              v25 = v154;
            }
            v20 = v23;
            v155 = v23;
            v153 = v5;
          }
          if ( (unsigned int)v16 >= v25 )
          {
            if ( (unsigned int)v16 > v25 )
            {
              memset_0(&v20[v25], 0, 8LL * ((unsigned int)v16 - v25));
              v20 = v155;
            }
            v154 = k;
          }
          v20[v16] = v21;
          if ( (unsigned int)k < v5 )
          {
            v4 = v154;
          }
          else
          {
            if ( !v5 )
              v5 = 4;
            for ( ; (int)k >= v5; v5 *= 2 )
              ;
            v28 = operator new[](saturated_mul(v5, 8u));
            if ( !v28 )
            {
              LODWORD(pExceptionObject) = 14;
              throw (ulong *)&pExceptionObject;
            }
            v29 = 0;
            v4 = v154;
            for ( n = v155; (unsigned int)v29 < v4; v29 = (unsigned int)(v29 + 1) )
            {
              v27 = 8 * v29;
              v28[v29] = n[v29];
            }
            if ( n )
              operator delete(n, v27);
            v20 = v28;
            v155 = v28;
            v153 = v5;
          }
          if ( (unsigned int)k >= v4 )
          {
            if ( (unsigned int)k > v4 )
            {
              memset_0(&v20[v4], 0, 8LL * ((unsigned int)k - v4));
              v20 = v155;
            }
            v4 = k + 1;
            v154 = k + 1;
          }
          v20[k] = v19;
          v6 = (char *)v155;
        }
        v12 = v168;
LABEL_46:
        k = (unsigned int)(k - 1);
      }
      LODWORD(v164) = ++v13;
    }
    while ( v13 < v12 );
    v31 = 0;
    for ( ii = 0; ii < v12; ++ii )
    {
      if ( v4 <= ii )
        v33 = 0;
      else
        v33 = *(_QWORD *)&v6[8 * ii];
      v34 = -1;
      do
        ++v34;
      while ( *(_WORD *)(v33 + 2 * v34) );
      v31 += v34 + 1;
    }
    v35 = 2 * v31 + 4;
    if ( v35 )
    {
      v36 = operator new[](v35);
      Src = v36;
      if ( !v36 )
      {
        LODWORD(pExceptionObject) = 14;
        throw (ulong *)&pExceptionObject;
      }
      v162 = v36;
      v37 = v35;
      HIDWORD(v163) = v35;
    }
    else
    {
      v37 = HIDWORD(v163);
    }
    v38 = 0;
    LODWORD(v163) = 0;
    if ( v12 )
    {
      while ( 1 )
      {
        if ( v4 <= v3 )
          v39 = 0;
        else
          v39 = *(_WORD **)&v6[8 * v3];
        v40 = -1;
        do
          ++v40;
        while ( v39[v40] );
        v41 = 2 * v40 + 2;
        if ( 2 * (_DWORD)v40 != -2 )
        {
          v42 = v38 + v41;
          if ( v38 )
          {
            if ( v37 < v42 )
            {
              v101 = operator new[](v42);
              v102 = v101;
              if ( !v101 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              memcpy_0(v101, Src, v38);
              operator delete(Src, v103);
              Src = v102;
              v162 = v102;
              HIDWORD(v163) = v38 + v41;
              v4 = v154;
            }
          }
          else
          {
            if ( v37 < v42 )
            {
              v44 = operator new[](v42);
              if ( !v44 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              if ( Src )
                operator delete(Src, v43);
              Src = v44;
              v162 = v44;
              HIDWORD(v163) = v42;
            }
            v38 = 0;
          }
          memcpy_0((char *)Src + v38, v39, v41);
          v38 += v41;
          LODWORD(v163) = v38;
        }
        if ( ++v3 >= v168 )
          break;
        v37 = HIDWORD(v163);
      }
    }
    v45 = v38 + 2;
    if ( v38 )
    {
      if ( HIDWORD(v163) < v45 )
      {
        v114 = operator new[](v45);
        v115 = v114;
        if ( !v114 )
        {
          LODWORD(pExceptionObject) = 14;
          throw (ulong *)&pExceptionObject;
        }
        memcpy_0(v114, Src, v38);
        operator delete(Src, v116);
        Src = v115;
        v162 = v115;
        HIDWORD(v163) = v38 + 2;
      }
      v3 = 0;
    }
    else
    {
      if ( HIDWORD(v163) < v45 )
      {
        v47 = operator new[](v45);
        if ( !v47 )
        {
          LODWORD(pExceptionObject) = 14;
          throw (ulong *)&pExceptionObject;
        }
        if ( Src )
          operator delete(Src, v46);
        Src = v47;
        v162 = v47;
        HIDWORD(v163) = v45;
      }
      v3 = 0;
      v38 = 0;
    }
    v48 = Src;
    *(_WORD *)((char *)Src + v38) = 0;
    LODWORD(v163) = v38 + 2;
    if ( v6 )
      operator delete(v6, (unsigned __int64)v48);
  }
  else
  {
    v119 = operator new[](4u);
    Src = v119;
    if ( !v119 )
    {
      LODWORD(pExceptionObject) = 14;
      throw (ulong *)&pExceptionObject;
    }
    v162 = v119;
    HIDWORD(v163) = 4;
    *v119 = 0;
    LODWORD(v163) = 4;
    if ( v6 )
      operator delete(v6, v120);
  }
  v152 = &CDynamicArray<unsigned short const>::`vftable';
  v49 = 0;
  v154 = 0;
  v50 = 0;
  v153 = 0;
  v51 = 0;
  v155 = 0;
  for ( jj = FirstString(a2); jj; jj = NextString(jj) )
  {
    v53 = v49;
    if ( v49 >= v50 )
    {
      if ( !v50 )
        v50 = 4;
      for ( ; (int)v49 >= v50; v50 *= 2 )
        ;
      v55 = (char *)operator new[](saturated_mul(v50, 8u));
      if ( !v55 )
      {
        LODWORD(pExceptionObject) = 14;
        throw (ulong *)&pExceptionObject;
      }
      for ( kk = 0; kk < v49; ++kk )
      {
        v151 = 8LL * kk;
        v54 = *(_QWORD *)&v51[v151];
        *(_QWORD *)&v55[v151] = v54;
      }
      if ( v51 )
        operator delete(v51, v54);
      v51 = v55;
      v155 = v55;
      v153 = v50;
    }
    ++v49;
    v154 = v53 + 1;
    *(_QWORD *)&v51[8 * v53] = jj;
  }
  v57 = v49;
  v168 = v49;
  if ( v49 )
  {
    v58 = 0;
    do
    {
      for ( mm = v57 - 1; v58 < (unsigned int)mm; v3 = 0 )
      {
        if ( v49 <= (unsigned int)mm )
          v60 = 0;
        else
          v60 = *(const WCHAR **)&v51[8 * (int)mm];
        v61 = (unsigned int)(mm - 1);
        if ( v49 <= (unsigned int)v61 )
          v62 = 0;
        else
          v62 = *(const WCHAR **)&v51[8 * (int)v61];
        v63 = lstrcmpiW(v62, v60);
        if ( v63 <= 0 )
        {
          if ( !v63 )
          {
            v110 = mm;
            v111 = v168;
            v57 = v168 - 1;
            if ( (unsigned int)mm < v168 - 1 )
            {
              while ( 1 )
              {
                v112 = v110 + 1;
                v113 = v49 <= v110 + 1 ? 0LL : *(_QWORD *)&v51[8 * v112];
                CDynamicArray<unsigned short const>::Set(&v152, v110, v113);
                v110 = v112;
                if ( v112 >= v57 )
                  break;
                v51 = (char *)v155;
                v49 = v154;
              }
            }
            CDynamicArray<unsigned short const>::Set(&v152, v111 - 1, 0);
            v168 = v57;
            v51 = (char *)v155;
            v49 = v154;
            v50 = v153;
            goto LABEL_127;
          }
        }
        else
        {
          if ( v49 <= (unsigned int)v61 )
            v165 = 0;
          else
            v165 = *(char **)&v51[8 * (int)v61];
          if ( v49 <= (unsigned int)mm )
            v164 = 0;
          else
            v164 = *(_QWORD *)&v51[8 * (int)mm];
          if ( (unsigned int)v61 >= v50 )
          {
            if ( !v50 )
              v50 = 4;
            for ( ; (int)v61 >= v50; v50 *= 2 )
              ;
            v65 = (char *)operator new[](saturated_mul(v50, 8u));
            if ( !v65 )
            {
              LODWORD(pExceptionObject) = 14;
              throw (ulong *)&pExceptionObject;
            }
            for ( nn = 0; (unsigned int)nn < v49; nn = (unsigned int)(nn + 1) )
            {
              v64 = 8 * nn;
              *(_QWORD *)&v65[8 * nn] = *(_QWORD *)&v51[8 * nn];
            }
            if ( v51 )
              operator delete(v51, v64);
            v51 = v65;
            v155 = v65;
            v153 = v50;
          }
          if ( (unsigned int)v61 >= v49 )
          {
            if ( (unsigned int)v61 > v49 )
              memset_0(&v51[8 * v49], 0, 8LL * ((unsigned int)v61 - v49));
            v49 = mm;
            v154 = mm;
          }
          *(_QWORD *)&v51[8 * v61] = v164;
          if ( (unsigned int)mm >= v50 )
          {
            if ( !v50 )
              v50 = 4;
            for ( ; (int)mm >= v50; v50 *= 2 )
              ;
            v68 = (char *)operator new[](saturated_mul(v50, 8u));
            if ( !v68 )
            {
              LODWORD(pExceptionObject) = 14;
              throw (ulong *)&pExceptionObject;
            }
            for ( i1 = 0; (unsigned int)i1 < v49; i1 = (unsigned int)(i1 + 1) )
            {
              v67 = 8 * i1;
              *(_QWORD *)&v68[8 * i1] = *(_QWORD *)&v51[8 * i1];
            }
            if ( v51 )
              operator delete(v51, v67);
            v51 = v68;
            v155 = v68;
            v153 = v50;
          }
          if ( (unsigned int)mm >= v49 )
          {
            if ( (unsigned int)mm > v49 )
              memset_0(&v51[8 * v49], 0, 8LL * ((unsigned int)mm - v49));
            v49 = mm + 1;
            v154 = mm + 1;
          }
          *(_QWORD *)&v51[8 * mm] = v165;
        }
        v57 = v168;
LABEL_127:
        mm = (unsigned int)(mm - 1);
      }
      ++v58;
    }
    while ( v58 < v57 );
    v70 = 0;
    for ( i2 = 0; (unsigned int)i2 < v57; i2 = (unsigned int)(i2 + 1) )
    {
      if ( v49 <= (unsigned int)i2 )
        v72 = 0;
      else
        v72 = *(_QWORD *)&v51[8 * (int)i2];
      v73 = -1;
      do
        ++v73;
      while ( *(_WORD *)(v72 + 2 * v73) );
      v70 += v73 + 1;
    }
    v74 = 2 * v70 + 4;
    if ( v74 )
    {
      v75 = (char *)operator new[](v74);
      v76 = v75;
      v157 = v75;
      if ( !v75 )
      {
        LODWORD(pExceptionObject) = 14;
        throw (ulong *)&pExceptionObject;
      }
      v159 = v75;
      v77 = v74;
      HIDWORD(v160) = v74;
    }
    else
    {
      v76 = (char *)v157;
      v77 = HIDWORD(v160);
    }
    v78 = 0;
    LODWORD(v160) = 0;
    if ( v57 )
    {
      while ( 1 )
      {
        if ( v49 <= v3 )
          v79 = 0;
        else
          v79 = *(_WORD **)&v51[8 * v3];
        v80 = -1;
        do
          ++v80;
        while ( v79[v80] );
        v81 = 2 * v80 + 2;
        if ( 2 * (_DWORD)v80 != -2 )
        {
          v82 = v78 + v81;
          if ( v78 )
          {
            if ( v77 < v82 )
            {
              v104 = (char *)operator new[](v82);
              v165 = v104;
              if ( !v104 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              memcpy_0(v104, v157, v78);
              operator delete(v157, v105);
              v157 = v165;
              v159 = v165;
              HIDWORD(v160) = v78 + v81;
            }
          }
          else
          {
            if ( v77 < v82 )
            {
              v84 = (char *)operator new[](v82);
              if ( !v84 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              if ( v157 )
                operator delete(v157, v83);
              v157 = v84;
              v159 = v84;
              HIDWORD(v160) = v82;
            }
            v78 = 0;
          }
          v76 = (char *)v157;
          memcpy_0((char *)v157 + v78, v79, v81);
          v78 += v81;
          LODWORD(v160) = v78;
        }
        if ( ++v3 >= v168 )
          break;
        v77 = HIDWORD(v160);
      }
    }
    v85 = v78 + 2;
    v86 = HIDWORD(v160);
    if ( v78 )
    {
      if ( HIDWORD(v160) < v85 )
      {
        v117 = (char *)operator new[](v85);
        v76 = v117;
        if ( !v117 )
        {
          LODWORD(pExceptionObject) = 14;
          throw (ulong *)&pExceptionObject;
        }
        memcpy_0(v117, v157, v78);
        operator delete(v157, v118);
        v157 = v76;
        v159 = v76;
        v86 = v78 + 2;
        HIDWORD(v160) = v78 + 2;
      }
    }
    else
    {
      if ( HIDWORD(v160) < v85 )
      {
        v87 = (char *)operator new[](v85);
        if ( !v87 )
        {
          LODWORD(pExceptionObject) = 14;
          throw (ulong *)&pExceptionObject;
        }
        if ( v76 )
          operator delete(v76, i2);
        v76 = v87;
        v157 = v87;
        v159 = v87;
        HIDWORD(v160) = v85;
        v86 = v85;
      }
      v78 = 0;
    }
    *(_WORD *)&v76[v78] = 0;
    LODWORD(v160) = v78 + 2;
  }
  else
  {
    v121 = (char *)operator new[](4u);
    v76 = v121;
    v157 = v121;
    if ( !v121 )
    {
      LODWORD(pExceptionObject) = 14;
      throw (ulong *)&pExceptionObject;
    }
    v159 = v121;
    v86 = 4;
    HIDWORD(v160) = 4;
    *(_DWORD *)v121 = 0;
    LODWORD(v160) = 4;
  }
  if ( v51 )
    operator delete(v51, i2);
  v88 = 0;
  v89 = &WideCharStr;
  v90 = &WideCharStr;
  v91 = Src;
  if ( HIDWORD(v163) )
    v90 = (const unsigned __int16 *)Src;
  String = FirstString(v90);
  if ( v86 )
    v89 = (const unsigned __int16 *)v76;
  v94 = FirstString(v89);
  if ( !String )
    goto LABEL_169;
  do
  {
    if ( !v94 )
      break;
    v133 = lstrcmpiW(String, v94);
    if ( v133 < 0 )
    {
      String = NextString(String);
    }
    else
    {
      if ( v133 > 0 )
      {
        v143 = NextString(v94);
      }
      else
      {
        v134 = -1;
        do
          ++v134;
        while ( String[v134] );
        v135 = 2 * v134 + 2;
        if ( 2 * (_DWORD)v134 != -2 )
        {
          v136 = pExceptionObject;
          v137 = *((_DWORD *)pExceptionObject + 4);
          v138 = v137 + v135;
          v139 = *((_DWORD *)pExceptionObject + 5);
          if ( v137 )
          {
            if ( v139 < v138 )
            {
              v144 = operator new[](v138);
              v145 = v144;
              if ( !v144 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              memcpy_0(v144, *((const void **)v136 + 1), *((unsigned int *)v136 + 4));
              operator delete(*((void **)v136 + 1), v146);
              *((_QWORD *)v136 + 1) = v145;
              *((_DWORD *)v136 + 5) = v138;
              v137 = *((_DWORD *)v136 + 4);
            }
          }
          else
          {
            if ( v139 < v138 )
            {
              v141 = operator new[](v138);
              if ( !v141 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              v142 = (void *)*((_QWORD *)v136 + 1);
              if ( v142 )
                operator delete(v142, v140);
              *((_QWORD *)v136 + 1) = v141;
              *((_DWORD *)v136 + 5) = v138;
            }
            *((_DWORD *)v136 + 4) = 0;
            v137 = 0;
          }
          memcpy_0((void *)(*((_QWORD *)v136 + 1) + v137), String, v135);
          *((_DWORD *)v136 + 4) += v135;
        }
        String = NextString(String);
        v143 = NextString(v94);
        ++v88;
      }
      v94 = v143;
    }
  }
  while ( String );
  if ( !v88 )
  {
    v76 = (char *)v157;
    v91 = Src;
LABEL_169:
    v95 = pExceptionObject;
    v96 = *((_DWORD *)pExceptionObject + 4);
    v97 = v96 + 4;
    v98 = *((_DWORD *)pExceptionObject + 5);
    if ( v96 )
    {
      if ( v98 < v97 )
      {
        v147 = operator new[](v97);
        v148 = v147;
        if ( !v147 )
        {
          LODWORD(pExceptionObject) = 14;
          throw (ulong *)&pExceptionObject;
        }
        memcpy_0(v147, *((const void **)v95 + 1), *((unsigned int *)v95 + 4));
        operator delete(*((void **)v95 + 1), v149);
        *((_QWORD *)v95 + 1) = v148;
        *((_DWORD *)v95 + 5) = v97;
        v96 = *((_DWORD *)v95 + 4);
      }
    }
    else
    {
      if ( v98 < v97 )
      {
        v99 = operator new[](v97);
        if ( !v99 )
        {
          LODWORD(pExceptionObject) = 14;
          throw (ulong *)&pExceptionObject;
        }
        v100 = (void *)*((_QWORD *)v95 + 1);
        if ( v100 )
          operator delete(v100, v93);
        *((_QWORD *)v95 + 1) = v99;
        *((_DWORD *)v95 + 5) = v97;
      }
      *((_DWORD *)v95 + 4) = 0;
      v96 = 0;
    }
    *(_DWORD *)(v96 + *((_QWORD *)v95 + 1)) = 0;
    *((_DWORD *)v95 + 4) += 4;
    goto LABEL_226;
  }
  v122 = pExceptionObject;
  v123 = *((_DWORD *)pExceptionObject + 4);
  v124 = v123 + 2;
  v125 = *((_DWORD *)pExceptionObject + 5);
  if ( v123 )
  {
    if ( v125 < v124 )
    {
      v130 = operator new[](v124);
      v131 = v130;
      if ( !v130 )
      {
        LODWORD(pExceptionObject) = 14;
        throw (ulong *)&pExceptionObject;
      }
      memcpy_0(v130, *((const void **)v122 + 1), *((unsigned int *)v122 + 4));
      operator delete(*((void **)v122 + 1), v132);
      *((_QWORD *)v122 + 1) = v131;
      *((_DWORD *)v122 + 5) = v124;
      v123 = *((_DWORD *)v122 + 4);
    }
  }
  else
  {
    if ( v125 < v124 )
    {
      v127 = operator new[](v124);
      if ( !v127 )
      {
        LODWORD(pExceptionObject) = 14;
        throw (ulong *)&pExceptionObject;
      }
      v128 = (void *)*((_QWORD *)v122 + 1);
      if ( v128 )
        operator delete(v128, v126);
      *((_QWORD *)v122 + 1) = v127;
      *((_DWORD *)v122 + 5) = v124;
    }
    *((_DWORD *)v122 + 4) = 0;
    v123 = 0;
  }
  v93 = v123;
  *(_WORD *)(v123 + *((_QWORD *)v122 + 1)) = 0;
  *((_DWORD *)v122 + 4) += 2;
  v76 = (char *)v157;
  v91 = Src;
LABEL_226:
  if ( v76 )
    operator delete(v76, v93);
  if ( v91 )
    operator delete(v91, v93);
  return v88;
}

```

## disassembly

```asm
0x18000aa80  mov     [rsp-8+arg_0], rbx
0x18000aa85  mov     [rsp-8+pExceptionObject], r8
0x18000aa8a  mov     [rsp-8+arg_8], rdx
0x18000aa8f  push    rbp
0x18000aa90  push    rsi
0x18000aa91  push    rdi
0x18000aa92  push    r12
0x18000aa94  push    r13
0x18000aa96  push    r14
0x18000aa98  push    r15
0x18000aa9a  lea     rbp, [rsp-27h]
0x18000aa9f  sub     rsp, 90h
0x18000aaa6  lea     rdx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000aaad  mov     [rbp+57h+var_60], rdx
0x18000aab1  xor     r15d, r15d
0x18000aab4  mov     eax, r15d
0x18000aab7  mov     [rbp+57h+Src], rax
0x18000aabb  mov     [rbp+57h+var_58], rax
0x18000aabf  mov     [rbp+57h+var_50], r15
0x18000aac3  mov     [rbp+57h+var_78], rdx
0x18000aac7  mov     [rbp+57h+var_80], rax
0x18000aacb  mov     [rbp+57h+var_70], rax
0x18000aacf  mov     [rbp+57h+var_68], r15
0x18000aad3  mov     [r8+10h], r15d
0x18000aad7  lea     rax, ??_7?$CDynamicArray@$$CBG@@6B@; const CDynamicArray<ushort const>::`vftable'
0x18000aade  mov     [rbp+57h+var_A0], rax
0x18000aae2  mov     r12d, r15d
0x18000aae5  mov     [rbp+57h+var_94], r15d
0x18000aae9  mov     ebx, r15d
0x18000aaec  mov     [rbp+57h+var_98], ebx
0x18000aaef  mov     r13d, r15d
0x18000aaf2  mov     [rbp+57h+var_90], r15
0x18000aaf6  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000aafb  mov     rsi, rax
0x18000aafe  mov     eax, 4
0x18000ab03  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000ab0a  test    rsi, rsi
0x18000ab0d  jz      short loc_18000AB8C
0x18000ab0f  mov     edi, r12d
0x18000ab12  cmp     r12d, ebx
0x18000ab15  jb      short loc_18000AB66
0x18000ab17  test    ebx, ebx
0x18000ab19  cmovz   ebx, eax
0x18000ab1c  cmp     edi, ebx
0x18000ab1e  jge     loc_18000B7A0
0x18000ab24  movsxd  rcx, ebx
0x18000ab27  mov     eax, 8
0x18000ab2c  mul     rcx
0x18000ab2f  cmovb   rax, r8
0x18000ab33  mov     rcx, rax; unsigned __int64
0x18000ab36  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ab3b  mov     r14, rax
0x18000ab3e  test    rax, rax
0x18000ab41  jz      loc_18000B833
0x18000ab47  mov     eax, r15d
0x18000ab4a  test    r12d, r12d
0x18000ab4d  jnz     loc_18000B7FC
0x18000ab53  test    r13, r13
0x18000ab56  jnz     loc_18000B81A
0x18000ab5c  mov     r13, r14
0x18000ab5f  mov     [rbp+57h+var_90], r14
0x18000ab63  mov     [rbp+57h+var_98], ebx
0x18000ab66  lea     r12d, [rdi+1]
0x18000ab6a  mov     [rbp+57h+var_94], r12d
0x18000ab6e  mov     [r13+rdi*8+0], rsi
0x18000ab73  mov     rcx, rsi; unsigned __int16 *
0x18000ab76  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18000ab7b  mov     rsi, rax
0x18000ab7e  test    rax, rax
0x18000ab81  mov     eax, 4
0x18000ab86  jnz     loc_18000B827
0x18000ab8c  mov     r14d, r12d
0x18000ab8f  mov     [rbp+57h+arg_18], r12d
0x18000ab93  test    r12d, r12d
0x18000ab96  jz      loc_18000B4D4
0x18000ab9c  mov     esi, r15d
0x18000ab9f  mov     dword ptr [rbp+57h+var_48], r15d
0x18000aba3  test    r12d, r12d
0x18000aba6  jz      loc_18000AD24
0x18000abac  lea     edi, [r14-1]
0x18000abb0  cmp     esi, edi
0x18000abb2  jnb     loc_18000AD16
0x18000abb8  cmp     r12d, edi
0x18000abbb  jbe     loc_18000B863
0x18000abc1  movsxd  rax, edi
0x18000abc4  mov     rdx, [r13+rax*8+0]; lpString2
0x18000abc9  lea     r15d, [rdi-1]
0x18000abcd  movsxd  r14, r15d
0x18000abd0  cmp     r12d, r15d
0x18000abd3  jbe     loc_18000B86B
0x18000abd9  mov     rcx, [r13+r14*8+0]; lpString1
0x18000abde  call    cs:__imp_lstrcmpiW
0x18000abe4  test    eax, eax
0x18000abe6  jle     loc_18000B39C
0x18000abec  cmp     r12d, r15d
0x18000abef  jbe     loc_18000B872
0x18000abf5  mov     r13, [r13+r14*8+0]
0x18000abfa  mov     rcx, [rbp+57h+var_90]
0x18000abfe  cmp     r12d, edi
0x18000ac01  jbe     loc_18000B87A
0x18000ac07  movsxd  rax, edi
0x18000ac0a  mov     r12, [rcx+rax*8]
0x18000ac0e  cmp     r15d, ebx
0x18000ac11  jb      loc_18000B8AF
0x18000ac17  test    ebx, ebx
0x18000ac19  mov     eax, 4
0x18000ac1e  cmovz   ebx, eax
0x18000ac21  cmp     r15d, ebx
0x18000ac24  jge     loc_18000B7C0
0x18000ac2a  movsxd  rcx, ebx
0x18000ac2d  mov     eax, 8
0x18000ac32  mul     rcx
0x18000ac35  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ac3c  cmovb   rax, rcx
0x18000ac40  mov     rcx, rax; unsigned __int64
0x18000ac43  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ac48  mov     r14, rax
0x18000ac4b  test    rax, rax
0x18000ac4e  jz      loc_18000B971
0x18000ac54  xor     eax, eax
0x18000ac56  mov     r9d, [rbp+57h+var_94]
0x18000ac5a  mov     r8, [rbp+57h+var_90]
0x18000ac5e  test    r9d, r9d
0x18000ac61  jnz     loc_18000B882
0x18000ac67  test    r8, r8
0x18000ac6a  jnz     loc_18000B89E
0x18000ac70  mov     rcx, r14
0x18000ac73  mov     [rbp+57h+var_90], rcx
0x18000ac77  mov     [rbp+57h+var_98], ebx
0x18000ac7a  cmp     r15d, r9d
0x18000ac7d  jnb     loc_18000B402
0x18000ac83  mov     [rcx+r15*8], r12
0x18000ac87  cmp     edi, ebx
0x18000ac89  jb      loc_18000B902
0x18000ac8f  test    ebx, ebx
0x18000ac91  mov     eax, 4
0x18000ac96  cmovz   ebx, eax
0x18000ac99  cmp     edi, ebx
0x18000ac9b  jge     loc_18000B7D0
0x18000aca1  movsxd  rcx, ebx
0x18000aca4  mov     eax, 8
0x18000aca9  mul     rcx
0x18000acac  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000acb3  cmovb   rax, rcx
0x18000acb7  mov     rcx, rax; unsigned __int64
0x18000acba  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000acbf  mov     r14, rax
0x18000acc2  test    rax, rax
0x18000acc5  jz      loc_18000B989
0x18000accb  xor     eax, eax
0x18000accd  mov     r12d, [rbp+57h+var_94]
0x18000acd1  mov     r8, [rbp+57h+var_90]
0x18000acd5  test    r12d, r12d
0x18000acd8  jnz     loc_18000B8D9
0x18000acde  test    r8, r8
0x18000ace1  jnz     loc_18000B8F5
0x18000ace7  mov     rcx, r14
0x18000acea  mov     [rbp+57h+var_90], rcx
0x18000acee  mov     [rbp+57h+var_98], ebx
0x18000acf1  cmp     edi, r12d
0x18000acf4  jnb     loc_18000B410
0x18000acfa  mov     [rcx+rdi*8], r13
0x18000acfe  mov     r13, [rbp+57h+var_90]
0x18000ad02  mov     r14d, [rbp+57h+arg_18]
0x18000ad06  dec     edi
0x18000ad08  cmp     esi, edi
0x18000ad0a  mov     r15d, 0
0x18000ad10  jb      loc_18000ABB8
0x18000ad16  inc     esi
0x18000ad18  mov     dword ptr [rbp+57h+var_48], esi
0x18000ad1b  cmp     esi, r14d
0x18000ad1e  jb      loc_18000ABAC
0x18000ad24  mov     ebx, r15d
0x18000ad27  mov     edx, r15d
0x18000ad2a  test    r14d, r14d
0x18000ad2d  jz      short loc_18000AD65
0x18000ad2f  nop
0x18000ad30  cmp     r12d, edx
0x18000ad33  jbe     loc_18000B9A1
0x18000ad39  movsxd  rax, edx
0x18000ad3c  mov     rcx, [r13+rax*8+0]
0x18000ad41  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ad48  nop     dword ptr [rax+rax+00000000h]
0x18000ad50  inc     rax
0x18000ad53  cmp     word ptr [rcx+rax*2], 0
0x18000ad58  jnz     short loc_18000AD50
0x18000ad5a  inc     ebx
0x18000ad5c  add     ebx, eax
0x18000ad5e  inc     edx
0x18000ad60  cmp     edx, r14d
0x18000ad63  jb      short loc_18000AD30
0x18000ad65  lea     ebx, ds:4[rbx*2]
0x18000ad6c  test    ebx, ebx
0x18000ad6e  jz      loc_18000B548
0x18000ad74  mov     ecx, ebx; unsigned __int64
0x18000ad76  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ad7b  mov     [rbp+57h+Src], rax
0x18000ad7f  test    rax, rax
0x18000ad82  jz      loc_18000B9A9
0x18000ad88  mov     [rbp+57h+var_58], rax
0x18000ad8c  mov     ecx, ebx
0x18000ad8e  mov     dword ptr [rbp+57h+var_50+4], ebx
0x18000ad91  mov     edi, r15d
0x18000ad94  mov     dword ptr [rbp+57h+var_50], r15d
0x18000ad98  test    r14d, r14d
0x18000ad9b  jz      loc_18000AE44
0x18000ada1  cmp     r12d, r15d
0x18000ada4  jbe     loc_18000B9C1
0x18000adaa  movsxd  rax, r15d
0x18000adad  mov     rbx, [r13+rax*8+0]
0x18000adb2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000adb9  nop     dword ptr [rax+00000000h]
0x18000adc0  lea     rax, [rax+1]
0x18000adc4  cmp     word ptr [rbx+rax*2], 0
0x18000adc9  jnz     short loc_18000ADC0
0x18000adcb  lea     r14d, ds:2[rax*2]
0x18000add3  test    r14d, r14d
0x18000add6  jz      short loc_18000AE33
0x18000add8  lea     esi, [rdi+r14]
0x18000addc  test    edi, edi
0x18000adde  jnz     loc_18000B30A
0x18000ade4  cmp     ecx, esi
0x18000ade6  jnb     short loc_18000AE1A
0x18000ade8  mov     ecx, esi; unsigned __int64
0x18000adea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000adef  mov     rdi, rax
0x18000adf2  test    rax, rax
0x18000adf5  jz      loc_18000B9E0
0x18000adfb  mov     rax, [rbp+57h+Src]
0x18000adff  test    rax, rax
0x18000ae02  jz      short loc_18000AE0C
0x18000ae04  mov     rcx, rax; void *
0x18000ae07  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ae0c  mov     rcx, rdi
0x18000ae0f  mov     [rbp+57h+Src], rcx
0x18000ae13  mov     [rbp+57h+var_58], rcx
0x18000ae17  mov     dword ptr [rbp+57h+var_50+4], esi
0x18000ae1a  xor     edi, edi
0x18000ae1c  mov     r8d, r14d; Size
0x18000ae1f  mov     ecx, edi
0x18000ae21  add     rcx, [rbp+57h+Src]; void *
0x18000ae25  mov     rdx, rbx; Src
0x18000ae28  call    memcpy_0
0x18000ae2d  add     edi, r14d
0x18000ae30  mov     dword ptr [rbp+57h+var_50], edi
0x18000ae33  inc     r15d
0x18000ae36  cmp     r15d, [rbp+57h+arg_18]
0x18000ae3a  jnb     short loc_18000AE44
0x18000ae3c  mov     ecx, dword ptr [rbp+57h+var_50+4]
0x18000ae3f  jmp     loc_18000ADA1
0x18000ae44  lea     ebx, [rdi+2]
0x18000ae47  test    edi, edi
0x18000ae49  jnz     loc_18000B447
0x18000ae4f  cmp     dword ptr [rbp+57h+var_50+4], ebx
0x18000ae52  jnb     short loc_18000AE86
0x18000ae54  mov     ecx, ebx; unsigned __int64
0x18000ae56  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ae5b  mov     rdi, rax
0x18000ae5e  test    rax, rax
0x18000ae61  jz      loc_18000BA10
0x18000ae67  mov     rax, [rbp+57h+Src]
0x18000ae6b  test    rax, rax
0x18000ae6e  jz      short loc_18000AE78
0x18000ae70  mov     rcx, rax; void *
0x18000ae73  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ae78  mov     rax, rdi
0x18000ae7b  mov     [rbp+57h+Src], rax
0x18000ae7f  mov     [rbp+57h+var_58], rax
0x18000ae83  mov     dword ptr [rbp+57h+var_50+4], ebx
0x18000ae86  xor     r15d, r15d
0x18000ae89  mov     edi, r15d
0x18000ae8c  mov     ecx, edi
0x18000ae8e  mov     rdx, [rbp+57h+Src]; unsigned __int64
0x18000ae92  mov     [rcx+rdx], r15w
0x18000ae97  add     edi, 2
0x18000ae9a  mov     dword ptr [rbp+57h+var_50], edi
0x18000ae9d  test    r13, r13
0x18000aea0  jz      short loc_18000AEAA
0x18000aea2  mov     rcx, r13; void *
0x18000aea5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aeaa  mov     r14d, 4
0x18000aeb0  lea     rax, ??_7?$CDynamicArray@$$CBG@@6B@; const CDynamicArray<ushort const>::`vftable'
0x18000aeb7  mov     [rbp+57h+var_A0], rax
0x18000aebb  mov     r13d, r15d
0x18000aebe  mov     [rbp+57h+var_94], r15d
0x18000aec2  mov     ebx, r15d
0x18000aec5  mov     [rbp+57h+var_98], ebx
0x18000aec8  mov     r12, r15
0x18000aecb  mov     [rbp+57h+var_90], r15
0x18000aecf  mov     rcx, [rbp+57h+arg_8]; unsigned __int16 *
0x18000aed3  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000aed8  mov     rsi, rax
0x18000aedb  test    rax, rax
0x18000aede  jz      short loc_18000AF5F
0x18000aee0  mov     edi, r13d
0x18000aee3  cmp     r13d, ebx
0x18000aee6  jb      short loc_18000AF3F
0x18000aee8  test    ebx, ebx
0x18000aeea  cmovz   ebx, r14d
0x18000aeee  cmp     edi, ebx
  ... truncated ...
```

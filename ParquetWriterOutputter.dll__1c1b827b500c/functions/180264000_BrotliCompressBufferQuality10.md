# BrotliCompressBufferQuality10

- ea: `0x180264000`
- end: `0x18026504d`
- name: `BrotliCompressBufferQuality10`
- size: `4173`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x180265110`

## callees

- `0x180264000`
- `0x180265a00`
- `0x180267d30`
- `0x180268010`
- `0x1802680b0`
- `0x1802681c0`
- `0x1802681e0`
- `0x180268200`
- `0x180268220`
- `0x180268260`
- `0x180268530`
- `0x180268550`
- `0x1802685b0`
- `0x180268610`
- `0x180268670`
- `0x180268710`
- `0x1802687c0`
- `0x180268830`
- `0x180268890`
- `0x180268c90`
- `0x180269a90`
- `0x180269ac0`
- `0x180269ad0`
- `0x180276630`
- `0x180276690`
- `0x180277490`
- `0x180278e10`
- `0x180278e50`
- `0x18027ec50`
- `0x18027faa0`
- `0x1802820e0`
- `0x180283030`
- `0x1802917f0`
- `0x18030c3f0`
- `0x18032ab90`
- `0x180357d70`

## pseudocode

```c
__int64 __fastcall BrotliCompressBufferQuality10(
        int a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        void *a5)
{
  unsigned int v6; // esi
  __int64 v7; // r13
  _WORD *v8; // r15
  __m128i si128; // xmm6
  unsigned __int64 v10; // rbx
  char v11; // al
  unsigned __int64 v12; // r14
  int v13; // r8d
  int v14; // eax
  int v15; // ecx
  __int64 v16; // r8
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // eax
  __int64 v20; // r12
  __int64 v21; // rax
  int v22; // edi
  _WORD *v23; // r8
  unsigned __int64 v24; // rbx
  size_t Size; // rsi
  unsigned __int64 v26; // r15
  __int64 v27; // rax
  unsigned __int64 v28; // rsi
  __int64 v29; // r9
  unsigned __int64 v30; // rdi
  __int64 v31; // rax
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // rax
  __int64 v34; // rax
  unsigned __int64 v35; // rdi
  unsigned int v36; // eax
  unsigned __int64 v37; // r8
  __int64 v38; // r11
  __int64 v39; // r13
  __int64 v40; // rdx
  unsigned __int64 v41; // r9
  __int64 v42; // rdx
  unsigned __int64 v43; // r10
  __int64 v44; // rbx
  __int64 v45; // r14
  unsigned __int64 v46; // rsi
  unsigned __int64 v47; // rdi
  __int64 v48; // rdx
  unsigned __int64 v49; // r11
  _DWORD *v50; // rcx
  unsigned __int64 v51; // r10
  unsigned __int64 v52; // r9
  unsigned __int64 v53; // r8
  unsigned __int64 v54; // r8
  __int64 v55; // rax
  unsigned int v56; // eax
  __int64 v57; // r14
  int v58; // eax
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rcx
  unsigned __int64 v63; // rsi
  unsigned __int64 v64; // r14
  unsigned __int64 v65; // rbx
  __int64 v66; // rax
  void *v67; // rdi
  void *v68; // rax
  unsigned __int64 v69; // rdx
  __int64 v70; // rbx
  __int16 v71; // cx
  unsigned __int64 k; // rax
  __int16 v73; // ax
  unsigned __int64 j; // rdx
  __int16 v75; // ax
  __int64 v76; // r15
  __int64 v77; // r14
  unsigned __int8 *v78; // rbx
  unsigned __int64 v79; // rsi
  __int64 v80; // r8
  __int64 v81; // r9
  int v82; // r8d
  int IsMostlyUTF8; // eax
  int v84; // esi
  __int64 v85; // r8
  __int64 v86; // r9
  int v87; // r8d
  size_t v88; // rsi
  int v89; // r8d
  size_t v90; // rdi
  char *v91; // rsi
  int v93; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v94; // [rsp+80h] [rbp-80h] BYREF
  char v95; // [rsp+81h] [rbp-7Fh]
  char v96; // [rsp+82h] [rbp-7Eh]
  char v97[5]; // [rsp+83h] [rbp-7Dh] BYREF
  __int64 v98; // [rsp+88h] [rbp-78h] BYREF
  __int64 v99; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h]
  int v101[6]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v102; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v103; // [rsp+C0h] [rbp-40h]
  __int64 v104; // [rsp+C8h] [rbp-38h]
  __int64 v105; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v106; // [rsp+D8h] [rbp-28h] BYREF
  size_t v107; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v108; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v109; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v110; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v111; // [rsp+100h] [rbp+0h]
  unsigned __int64 v112; // [rsp+108h] [rbp+8h]
  unsigned __int64 v113; // [rsp+110h] [rbp+10h]
  unsigned __int64 v114; // [rsp+118h] [rbp+18h]
  __int64 v115; // [rsp+120h] [rbp+20h]
  unsigned __int64 v116; // [rsp+128h] [rbp+28h]
  void *v117; // [rsp+130h] [rbp+30h]
  __int64 v118; // [rsp+138h] [rbp+38h]
  unsigned __int64 v119; // [rsp+140h] [rbp+40h]
  unsigned __int64 v120; // [rsp+148h] [rbp+48h]
  unsigned __int64 i; // [rsp+150h] [rbp+50h]
  unsigned __int64 v122; // [rsp+158h] [rbp+58h]
  __int64 v123; // [rsp+160h] [rbp+60h]
  unsigned __int64 v124; // [rsp+168h] [rbp+68h]
  unsigned __int64 v125; // [rsp+170h] [rbp+70h]
  __int64 Dictionary; // [rsp+178h] [rbp+78h]
  unsigned __int64 v127; // [rsp+180h] [rbp+80h]
  unsigned __int64 v128; // [rsp+188h] [rbp+88h]
  _WORD *v129; // [rsp+190h] [rbp+90h]
  unsigned __int64 v130; // [rsp+198h] [rbp+98h]
  unsigned __int64 *v131; // [rsp+1A0h] [rbp+A0h]
  __int64 v132; // [rsp+1A8h] [rbp+A8h]
  __int64 v133[6]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v134[48]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v135[48]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v136; // [rsp+240h] [rbp+140h]
  __int64 v137; // [rsp+248h] [rbp+148h]
  __int64 v138; // [rsp+250h] [rbp+150h]
  __int64 v139; // [rsp+258h] [rbp+158h]
  __int64 v140; // [rsp+260h] [rbp+160h]
  __int64 v141; // [rsp+268h] [rbp+168h]
  __int64 v142; // [rsp+270h] [rbp+170h]
  __int64 v143; // [rsp+278h] [rbp+178h]
  __int64 v144; // [rsp+280h] [rbp+180h]
  __int64 v145; // [rsp+288h] [rbp+188h]
  __int64 v146; // [rsp+290h] [rbp+190h] BYREF
  int v147; // [rsp+298h] [rbp+198h]
  int v148; // [rsp+29Ch] [rbp+19Ch]
  unsigned __int64 v149; // [rsp+2A0h] [rbp+1A0h]
  __int128 v150; // [rsp+2ACh] [rbp+1ACh]
  int v151; // [rsp+2BCh] [rbp+1BCh]
  __m128i v152; // [rsp+2C0h] [rbp+1C0h] BYREF

  v6 = 1;
  v117 = a5;
  v7 = a3;
  v131 = a4;
  v8 = (_WORD *)a2;
  v130 = *a4;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v104 = a3;
  v119 = a2;
  v10 = 1LL << a1;
  v118 = 1;
  v115 = (1LL << a1) - 16;
  v152 = si128;
  if ( a2 < 1LL << a1 )
    v10 = a2;
  v111 = 0;
  Dictionary = BrotliGetDictionary();
  v11 = a1 + 1;
  if ( a1 + 1 > 24 )
    v11 = 24;
  v12 = 0;
  v99 = 0;
  v132 = 1LL << v11;
  v128 = (unsigned __int64)(1LL << v11) >> 3;
  v95 = 0;
  v96 = 0;
  BrotliEncoderInitParams(&v146);
  v14 = 10;
  HIDWORD(v146) = 10;
  if ( a1 >= 10 )
  {
    v14 = a1;
    if ( a1 > v13 )
      v14 = v13;
  }
  v15 = v148;
  v147 = v14;
  if ( v148 )
  {
    if ( v148 < 16 )
      v15 = 16;
    if ( v15 > v13 )
      v15 = v13;
  }
  else
  {
    v15 = 16;
    if ( v14 > 16 )
    {
      v15 = v14;
      if ( v14 > 18 )
        v15 = 18;
    }
  }
  v148 = v15;
  v122 = 1LL << v15;
  BrotliInitMemoryManager(v101, 0, 0, 0);
  EncodeWindowBits((unsigned int)a1, v97, &v94);
  v16 = HIDWORD(v146);
  v17 = 40;
  if ( SHIDWORD(v146) <= 9 )
  {
    if ( HIDWORD(v146) == 4 )
    {
      if ( v149 >= 0x100000 )
      {
        v18 = 54;
        LODWORD(v150) = 54;
        goto LABEL_37;
      }
LABEL_23:
      v18 = HIDWORD(v146);
      LODWORD(v150) = HIDWORD(v146);
      goto LABEL_37;
    }
    if ( SHIDWORD(v146) < 5 )
      goto LABEL_23;
    if ( v147 <= 16 )
    {
      if ( SHIDWORD(v146) >= 7 )
      {
        v18 = (SHIDWORD(v146) >= 9) + 41;
        LODWORD(v150) = v18;
      }
      else
      {
        v18 = 40;
        LODWORD(v150) = 40;
      }
      goto LABEL_37;
    }
    if ( v149 < 0x100000 || v147 < 19 )
    {
      v18 = 5;
      DWORD2(v150) = HIDWORD(v146) - 1;
      LODWORD(v150) = 5;
      DWORD1(v150) = (SHIDWORD(v146) >= 7) + 14;
      if ( SHIDWORD(v146) < 7 )
      {
        v19 = 4;
        goto LABEL_36;
      }
    }
    else
    {
      v18 = 6;
      *(_QWORD *)&v150 = 0xF00000006LL;
      DWORD2(v150) = HIDWORD(v146) - 1;
      HIDWORD(v150) = 5;
      if ( SHIDWORD(v146) < 7 )
      {
        v19 = 4;
LABEL_36:
        v151 = v19;
        goto LABEL_37;
      }
    }
    v19 = 16;
    v16 = 10;
    if ( SHIDWORD(v146) < 9 )
      v19 = 10;
    goto LABEL_36;
  }
  v18 = 10;
  LODWORD(v150) = 10;
LABEL_37:
  switch ( v18 )
  {
    case 2:
      v17 = 262188;
      goto LABEL_39;
    case 3:
      v17 = 262192;
      goto LABEL_39;
    case 4:
    case 40:
    case 41:
      v17 = 524344;
      goto LABEL_39;
    case 5:
      v17 = (1LL << SBYTE4(v150)) * (4 * (1LL << SBYTE8(v150)) + 2) + 64;
      goto LABEL_50;
    case 6:
      v17 = (1LL << SBYTE4(v150)) * (4 * (1LL << SBYTE8(v150)) + 2) + 80;
      goto LABEL_50;
    case 10:
      v21 = v10;
      if ( v10 >= 1LL << v147 )
        v21 = 1LL << v147;
      v17 = 8 * v21 + 524344;
LABEL_50:
      if ( v17 )
        goto LABEL_39;
      v20 = 0;
      break;
    case 42:
      v17 = 1311792;
      goto LABEL_39;
    case 54:
      v17 = 4194360;
      goto LABEL_39;
    default:
LABEL_39:
      v20 = BrotliAllocate(v101, v17, v16, (unsigned int)v147);
      break;
  }
  *(_OWORD *)v20 = v150;
  *(_DWORD *)(v20 + 16) = v151;
  switch ( *(_DWORD *)v20 )
  {
    case 5:
      InitializeH5(v20, &v146);
      break;
    case 6:
      InitializeH6(v20, &v146);
      break;
    case 0xA:
      InitializeH10(v20, &v146);
      break;
    case 0x28:
    case 0x29:
      InitializeH41(v20, &v146);
      break;
    case 0x2A:
      InitializeH42(v20, &v146);
      break;
    default:
      break;
  }
  *(_DWORD *)(v20 + 20) = 0;
  switch ( *(_DWORD *)v20 )
  {
    case 2:
      PrepareH2(v20, 1, v10, v7);
      break;
    case 3:
      PrepareH3(v20, 1, v10, v7);
      break;
    case 4:
      PrepareH4(v20, 1, v10, v7);
      break;
    case 5:
      PrepareH5(v20, 1, v10, v7);
      break;
    case 6:
      PrepareH6(v20, 1, v10, v7);
      break;
    case 0xA:
      PrepareH10(v20, 1, v10, v7);
      break;
    case 0x28:
    case 0x29:
      PrepareH41(v20, 1, v10, v7);
      break;
    case 0x2A:
      PrepareH42(v20, 1, v10, v7);
      break;
    case 0x36:
      PrepareH54(v20, 1, v10, v7);
      break;
    default:
      break;
  }
  v22 = 0;
  v116 = v94;
  v94 = v97[0];
  *(_QWORD *)(v20 + 24) = 0;
  *(_QWORD *)(v20 + 32) = 0;
  *(_DWORD *)(v20 + 20) = 1;
  do
  {
    if ( v12 >= (unsigned __int64)v8 )
      break;
    v23 = (_WORD *)(v12 + v132);
    Src = 0;
    v110 = 0;
    v24 = 0;
    v107 = 0;
    if ( (unsigned __int64)v8 < v12 + v132 )
      v23 = v8;
    v103 = 0;
    v129 = v23;
    v113 = 0;
    Size = 0;
    v109 = v12;
    v26 = v12;
    v127 = ((unsigned __int64)v23 - v12) / 0xC + 16;
    v27 = 0;
    v106 = 0;
    if ( v12 < (unsigned __int64)v23 )
    {
      v28 = HashTypeLengthH10() - 1;
      for ( i = v28; ; v28 = i )
      {
        v30 = v122;
        if ( (unsigned __int64)v23 - v26 < v122 )
          v30 = (unsigned __int64)v23 - v26;
        v114 = v30;
        if ( v30 == -1 )
          v31 = 0;
        else
          v31 = BrotliAllocate(v101, 16 * (v30 + 1), v23, v29);
        v105 = v31;
        BrotliInitZopfliNodes(v31, v30 + 1);
        if ( v30 >= v28 && v26 >= 0x80 )
        {
          v32 = v26 - 127;
          v33 = v26 - 127 + v30;
          v108 = v26 - 127;
          if ( v26 < v33 )
            v33 = v26;
          v125 = v33;
          if ( v32 < v33 )
          {
            do
            {
              v34 = v26 - v32;
              if ( v26 - v32 < 0xF )
                v34 = 15;
              v35 = *(_QWORD *)(v20 + 40) - v34;
              v124 = v35;
              v123 = v7 + (v32 & 0x7FFFFFFFFFFFFFFFLL);
              v36 = HashBytesH10(v123);
              v39 = 64;
              v41 = 0;
              v42 = 2 * (v37 & v40);
              v112 = 0;
              v43 = 0;
              v102 = v42;
              v44 = *(unsigned int *)(v20 + 4LL * v36 + 48);
              v120 = 0;
              *(_DWORD *)(v20 + 4LL * v36 + 48) = v37;
              v45 = v42 + 1;
              v46 = v37 - v44;
              if ( v37 != v44 )
              {
                while ( v46 <= v35 && v39 )
                {
                  v47 = v43;
                  if ( v41 < v43 )
                    v47 = v41;
                  v48 = 0;
                  v49 = v47 + v38;
                  v50 = (_DWORD *)(v104 + v47 + v44);
                  v51 = v104 + v44 + 128;
                  v52 = v104 + v44 + 124;
                  if ( (unsigned __int64)v50 <= v52 )
                  {
                    v53 = v49 - (_QWORD)v50;
                    do
                    {
                      if ( *v50 != *(_DWORD *)((char *)v50 + v53) )
                        break;
                      ++v50;
                      v48 += 4;
                    }
                    while ( (unsigned __int64)v50 <= v52 );
                  }
                  for ( ; (unsigned __int64)v50 < v51; ++v48 )
                  {
                    if ( *(_BYTE *)(v48 + v49) != *(_BYTE *)v50 )
                      break;
                    v50 = (_DWORD *)((char *)v50 + 1);
                  }
                  v54 = v48 + v47;
                  if ( v48 + v47 >= 0x80 )
                  {
                    v37 = v108;
                    *(_DWORD *)(v20 + 4 * v102 + 524344) = *(_DWORD *)(v20 + 8 * (v44 & *(_QWORD *)(v20 + 40)) + 524344);
                    v58 = *(_DWORD *)(v20 + 8 * (v44 & *(_QWORD *)(v20 + 40)) + 524348);
                    goto LABEL_107;
                  }
                  v38 = v123;
                  if ( *(_BYTE *)(v123 + v54) <= *(_BYTE *)(v54 + v44 + v104) )
                  {
                    v42 = v102;
                    v43 = v54;
                    v41 = v112;
                    *(_DWORD *)(v20 + 4 * v45 + 524344) = v44;
                    v57 = v44 & *(_QWORD *)(v20 + 40);
                    v120 = v54;
                    v45 = 2 * v57;
                    v56 = *(_DWORD *)(v20 + 4 * v45 + 524344);
                  }
                  else
                  {
                    v41 = v48 + v47;
                    v43 = v120;
                    v112 = v48 + v47;
                    *(_DWORD *)(v20 + 4 * v102 + 524344) = v44;
                    v55 = v44 & *(_QWORD *)(v20 + 40);
                    v42 = 2 * v55 + 1;
                    v56 = *(_DWORD *)(v20 + 8 * v55 + 524348);
                    v102 = v42;
                  }
                  v37 = v108;
                  --v39;
                  v35 = v124;
                  v44 = v56;
                  v46 = v108 - v56;
                  if ( v108 == v56 )
                    goto LABEL_106;
                }
                v42 = v102;
              }
LABEL_106:
              *(_DWORD *)(v20 + 4 * v42 + 524344) = *(_DWORD *)(v20 + 524336);
              v58 = *(_DWORD *)(v20 + 524336);
LABEL_107:
              v7 = v104;
              v32 = v37 + 1;
              v26 = v109;
              *(_DWORD *)(v20 + 4 * v45 + 524344) = v58;
              v108 = v32;
            }
            while ( v32 < v125 );
            v30 = v114;
          }
        }
        v59 = BrotliZopfliComputeShortestPath(
                (unsigned int)v101,
                Dictionary,
                v30,
                v26,
                v7,
                0x7FFFFFFFFFFFFFFFLL,
                (__int64)&v146,
                v115,
                (__int64)&v152,
                v20,
                v105);
        v62 = v103;
        v63 = v59 + v103;
        v64 = v59 + v103 + 1;
        v65 = v64;
        if ( v127 > v64 )
          v65 = v127;
        if ( v113 == v65 )
        {
          v68 = Src;
        }
        else
        {
          if ( v65 )
          {
            v66 = BrotliAllocate(v101, 16 * v65, v60, v61);
            v62 = v103;
            v67 = (void *)v66;
          }
          else
          {
            v67 = 0;
          }
          v113 = v65;
          if ( Src )
          {
            memmove(v67, Src, 16 * v62);
            Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
          }
          v62 = v103;
          v68 = v67;
          v30 = v114;
          Src = v68;
        }
        BrotliZopfliCreateCommands(
          v30,
          v26,
          v115,
          v105,
          (__int64)&v152,
          (__int64)&v110,
          (__int64)v68 + 16 * v62,
          (__int64)&v106);
        v24 = v63;
        v26 += v30;
        Size = v30 + v107;
        v103 = v24;
        v107 += v30;
        v109 = v26;
        Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
        v27 = v106;
        if ( v106 > v128 )
          break;
        if ( v24 > v128 )
          break;
        v23 = v129;
        if ( v26 >= (unsigned __int64)v129 )
          break;
      }
      v69 = v110;
      v22 = 0;
      if ( v110 )
      {
        v23 = Src;
        v70 = 2 * v24;
        *((_DWORD *)Src + 2 * v70) = v110;
        *(_QWORD *)&v23[4 * v70 + 2] = 0x4000000;
        v23[4 * v70 + 7] = 16;
        if ( v69 >= 6 )
        {
          if ( v69 >= 0x82 )
          {
            if ( v69 >= 0x842 )
            {
              if ( v69 >= 0x1842 )
              {
                v75 = 23;
                if ( v69 < 0x5842 )
                  v75 = 22;
                LOWORD(v69) = v75;
              }
              else
              {
                LOWORD(v69) = 21;
              }
            }
            else
            {
              v73 = 0;
              for ( j = (v69 - 66) >> 1; j; j >>= 1 )
                ++v73;
              LOWORD(v69) = v73 + 10;
            }
          }
          else
          {
            v69 -= 2LL;
            v71 = 0;
            for ( k = v69 >> 1; k; k >>= 1 )
              ++v71;
            LOWORD(v69) = 2 * v71 + (v69 >> ((unsigned __int8)v71 - 1));
          }
        }
        v23[4 * v70 + 6] = (8 * (v69 & 7))
                         | (32 * (6 * ((unsigned __int16)v69 >> 3) + 2)
                          + ((5377344 >> (6 * ((unsigned __int16)v69 >> 3))) & 0xC0))
                         | 2;
        v24 = v64;
        v27 = v110 + v106;
        v106 += v110;
        v103 = v64;
      }
      v12 = v99;
    }
    v76 = Size + v12;
    v77 = (unsigned __int8)v116;
    v98 = (unsigned __int8)v116;
    LOBYTE(v22) = v76 == v119;
    if ( Size )
    {
      if ( (unsigned int)ShouldCompress(v7, -1, v99, Size, v27, v24) )
      {
        BrotliInitBlockSplit(v133);
        BrotliInitBlockSplit(v134);
        BrotliInitBlockSplit(v135);
        v136 = 0;
        v137 = 0;
        v138 = 0;
        v139 = 0;
        v140 = 0;
        v141 = 0;
        v142 = 0;
        v143 = 0;
        v144 = 0;
        v145 = 0;
        IsMostlyUTF8 = BrotliIsMostlyUTF8(v7, v99, -1, Size, *(__int64 *)&DOUBLE_0_75);
        v84 = 2;
        if ( !IsMostlyUTF8 )
          v84 = 3;
        BrotliBuildMetaBlock(
          (int)v101,
          v7,
          v99,
          0x7FFFFFFFFFFFFFFFLL,
          (__int64)&v146,
          v95,
          v96,
          (__int64)Src,
          v24,
          v84,
          (__int64)v133);
        BrotliOptimizeHistograms(0, 0, v133);
        if ( 2 * v107 == -502 )
          v78 = 0;
        else
          v78 = (unsigned __int8 *)BrotliAllocate(v101, 2 * v107 + 502, v85, v86);
        v87 = v99;
        *v78 = v94;
        v93 = v84;
        v88 = v107;
        BrotliStoreMetaBlock(
          (unsigned int)v101,
          v7,
          v87,
          v107,
          0x7FFFFFFFFFFFFFFFLL,
          v95,
          v96,
          v22,
          0,
          0,
          v93,
          (__int64)Src,
          v103,
          (__int64)v133,
          (__int64)&v98,
          (__int64)v78);
        if ( v88 + 4 < (unsigned __int64)v98 >> 3 )
        {
          v89 = v99;
          v152 = si128;
          *v78 = v94;
          v98 = v77;
          BrotliStoreUncompressedMetaBlock(v22, v7, v89, -1, v88, (__int64)&v98, (__int64)v78);
        }
        BrotliDestroyBlockSplit((Concurrency::details::RealizedChore *)v101);
        BrotliDestroyBlockSplit((Concurrency::details::RealizedChore *)v101);
        BrotliDestroyBlockSplit((Concurrency::details::RealizedChore *)v101);
        Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
        v136 = 0;
        Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
        v138 = 0;
        Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
        v140 = 0;
        Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
        v142 = 0;
        Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
        v144 = 0;
      }
      else
      {
        v152 = si128;
        v78 = Size == -16 ? 0LL : (unsigned __int8 *)BrotliAllocate(v101, Size + 16, v80, v81);
        v82 = v99;
        *v78 = v94;
        BrotliStoreUncompressedMetaBlock(v22, v7, v82, -1, Size, (__int64)&v98, (__int64)v78);
      }
      v79 = v98;
    }
    else
    {
      v78 = (unsigned __int8 *)BrotliAllocate(v101, 16, v23, 16);
      *v78 = v94;
      *(_QWORD *)&v78[(unsigned __int64)v98 >> 3] = v78[(unsigned __int64)v98 >> 3]
                                                  | (unsigned __int64)(3LL << (v98 & 7));
      v79 = (v98 + 9) & 0xFFFFFFF8LL;
      v98 = v79;
    }
    si128 = v152;
    v90 = v79 >> 3;
    LOBYTE(v79) = v79 & 7;
    v116 = v79;
    v12 = v76;
    v99 = v76;
    v94 = v78[v90];
    v95 = *(_BYTE *)(v76 + v7 - 1);
    v96 = *(_BYTE *)(v76 + v7 - 2);
    v111 += v90;
    if ( v111 > v130 )
    {
      v22 = 0;
      v6 = 0;
      v118 = 0;
    }
    else
    {
      v91 = (char *)v117;
      memmove(v117, v78, v90);
      v117 = &v91[v90];
      v22 = 0;
      v6 = v118;
    }
    Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
    Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
    v8 = (_WORD *)v119;
  }
  while ( v6 );
  *v131 = v111;
  Concurrency::details::RealizedChore::Invoke((Concurrency::details::RealizedChore *)v101);
  return v6;
}

```

## disassembly

```asm
0x180264000  push    rbp
0x180264002  push    rbx
0x180264003  push    rsi
0x180264004  push    rdi
0x180264005  push    r12
0x180264007  push    r13
0x180264009  push    r14
0x18026400b  push    r15
0x18026400d  lea     rbp, [rsp-1F8h]
0x180264015  sub     rsp, 2F8h
0x18026401c  movaps  [rsp+330h+var_50], xmm6
0x180264024  mov     rax, cs:__security_cookie
0x18026402b  xor     rax, rsp
0x18026402e  mov     [rbp+230h+var_60], rax
0x180264035  movdqa  xmm0, cs:__xmm@000000100000000f0000000b00000004
0x18026403d  mov     edi, ecx
0x18026403f  mov     rax, [rbp+230h+arg_20]
0x180264046  mov     esi, 1
0x18026404b  mov     [rbp+230h+var_200], rax
0x18026404f  mov     r13, r8
0x180264052  mov     eax, esi
0x180264054  mov     [rbp+230h+var_190], r9
0x18026405b  shl     rax, cl
0x18026405e  mov     r15, rdx
0x180264061  mov     rcx, [r9]
0x180264064  sub     rax, 10h
0x180264068  mov     [rbp+230h+var_198], rcx
0x18026406f  movdqa  xmm6, xmm0
0x180264073  xor     ecx, ecx
0x180264075  mov     [rbp+230h+var_268], r8
0x180264079  mov     [rbp+230h+var_1F0], rdx
0x18026407d  lea     rbx, [rax+10h]
0x180264081  mov     [rbp+230h+var_1F8], rsi
0x180264085  cmp     rdx, rbx
0x180264088  mov     [rbp+230h+var_210], rax
0x18026408c  movdqa  [rbp+230h+var_70], xmm0
0x180264094  cmovb   rbx, rdx
0x180264098  mov     [rbp+230h+var_230], rcx
0x18026409c  call    BrotliGetDictionary
0x1802640a1  mov     [rbp+230h+var_1B8], rax
0x1802640a5  mov     r8d, 18h
0x1802640ab  lea     eax, [rdi+1]
0x1802640ae  mov     edx, esi
0x1802640b0  cmp     eax, r8d
0x1802640b3  cmovg   eax, r8d
0x1802640b7  xor     r14d, r14d
0x1802640ba  movzx   ecx, al
0x1802640bd  mov     [rbp+230h+var_2A0], r14
0x1802640c1  shl     rdx, cl
0x1802640c4  lea     rcx, [rbp+230h+var_A0]
0x1802640cb  mov     rax, rdx
0x1802640ce  mov     [rbp+230h+var_188], rdx
0x1802640d5  shr     rax, 3
0x1802640d9  mov     [rbp+230h+var_1A8], rax
0x1802640e0  mov     [rbp+230h+var_2AF], r14b
0x1802640e4  mov     [rbp+230h+var_2AE], r14b
0x1802640e8  call    BrotliEncoderInitParams
0x1802640ed  mov     eax, 0Ah
0x1802640f2  mov     dword ptr [rbp+230h+var_A0+4], eax
0x1802640f8  cmp     edi, eax
0x1802640fa  jl      short loc_180264105
0x1802640fc  cmp     edi, r8d
0x1802640ff  mov     eax, edi
0x180264101  cmovg   eax, r8d
0x180264105  mov     ecx, [rbp+230h+var_94]
0x18026410b  mov     r12d, 10h
0x180264111  mov     [rbp+230h+var_98], eax
0x180264117  test    ecx, ecx
0x180264119  jnz     short loc_180264131
0x18026411b  mov     ecx, r12d
0x18026411e  cmp     eax, r12d
0x180264121  jle     short loc_18026413F
0x180264123  mov     edx, 12h
0x180264128  mov     ecx, eax
0x18026412a  cmp     eax, edx
0x18026412c  cmovg   ecx, edx
0x18026412f  jmp     short loc_18026413F
0x180264131  cmp     ecx, r12d
0x180264134  cmovl   ecx, r12d
0x180264138  cmp     ecx, r8d
0x18026413b  cmovg   ecx, r8d
0x18026413f  mov     [rbp+230h+var_94], ecx
0x180264145  mov     rax, rsi
0x180264148  shl     rax, cl
0x18026414b  xor     r9d, r9d
0x18026414e  lea     rcx, [rbp+230h+var_290]
0x180264152  mov     [rbp+230h+var_1D8], rax
0x180264156  xor     r8d, r8d
0x180264159  xor     edx, edx
0x18026415b  call    BrotliInitMemoryManager
0x180264160  lea     r8, [rbp+230h+var_2B0]
0x180264164  mov     ecx, edi
0x180264166  lea     rdx, [rbp+230h+var_2AD]
0x18026416a  call    EncodeWindowBits
0x18026416f  mov     r8d, dword ptr [rbp+230h+var_A0+4]
0x180264176  mov     edx, 28h ; '('
0x18026417b  mov     r9d, [rbp+230h+var_98]
0x180264182  lea     r10d, [rdx-19h]
0x180264186  cmp     r8d, 9
0x18026418a  jle     short loc_18026419C
0x18026418c  mov     ecx, 0Ah
0x180264191  mov     dword ptr [rbp+230h+var_84], ecx
0x180264197  jmp     loc_180264290
0x18026419c  cmp     r8d, 4
0x1802641a0  jnz     short loc_1802641BF
0x1802641a2  cmp     [rbp+230h+var_90], 100000h
0x1802641ad  jb      short loc_1802641C5
0x1802641af  mov     ecx, 36h ; '6'
0x1802641b4  mov     dword ptr [rbp+230h+var_84], ecx
0x1802641ba  jmp     loc_180264290
0x1802641bf  cmp     r8d, 5
0x1802641c3  jge     short loc_1802641D3
0x1802641c5  mov     ecx, r8d
0x1802641c8  mov     dword ptr [rbp+230h+var_84], ecx
0x1802641ce  jmp     loc_180264290
0x1802641d3  cmp     r9d, 10h
0x1802641d7  jg      short loc_180264203
0x1802641d9  cmp     r8d, 7
0x1802641dd  jge     short loc_1802641EC
0x1802641df  mov     ecx, edx
0x1802641e1  mov     dword ptr [rbp+230h+var_84], edx
0x1802641e7  jmp     loc_180264290
0x1802641ec  xor     ecx, ecx
0x1802641ee  cmp     r8d, 9
0x1802641f2  setnl   cl
0x1802641f5  add     ecx, 29h ; ')'
0x1802641f8  mov     dword ptr [rbp+230h+var_84], ecx
0x1802641fe  jmp     loc_180264290
0x180264203  cmp     [rbp+230h+var_90], 100000h
0x18026420e  jb      short loc_180264247
0x180264210  cmp     r9d, 13h
0x180264214  jl      short loc_180264247
0x180264216  mov     dword ptr [rbp+230h+var_84+4], r10d
0x18026421d  mov     ecx, 6
0x180264222  mov     dword ptr [rbp+230h+var_84], ecx
0x180264228  lea     eax, [r8-1]
0x18026422c  mov     dword ptr [rbp+230h+var_84+8], eax
0x180264232  mov     dword ptr [rbp+230h+var_84+0Ch], 5
0x18026423c  cmp     r8d, 7
0x180264240  jge     short loc_180264279
0x180264242  lea     eax, [rcx-2]
0x180264245  jmp     short loc_18026428A
0x180264247  lea     eax, [r8-1]
0x18026424b  mov     ecx, 5
0x180264250  mov     dword ptr [rbp+230h+var_84+8], eax
0x180264256  xor     eax, eax
0x180264258  cmp     r8d, 7
0x18026425c  mov     dword ptr [rbp+230h+var_84], ecx
0x180264262  setnl   al
0x180264265  add     eax, 0Eh
0x180264268  mov     dword ptr [rbp+230h+var_84+4], eax
0x18026426e  cmp     r8d, 7
0x180264272  jge     short loc_180264279
0x180264274  lea     eax, [rcx-1]
0x180264277  jmp     short loc_18026428A
0x180264279  cmp     r8d, 9
0x18026427d  mov     eax, r12d
0x180264280  mov     r8d, 0Ah
0x180264286  cmovl   eax, r8d
0x18026428a  mov     [rbp+230h+var_74], eax
0x180264290  add     ecx, 0FFFFFFFEh; switch 53 cases
0x180264293  lea     rdi, cs:180000000h
0x18026429a  cmp     ecx, 34h
0x18026429d  ja      short def_1802642B4; jumptable 00000001802642B4 default case, cases 7-9,11-39,43-53
0x18026429f  movsxd  rax, ecx
0x1802642a2  movzx   eax, ds:(byte_180264F5C - 180000000h)[rdi+rax]
0x1802642aa  mov     ecx, ds:(jpt_1802642B4 - 180000000h)[rdi+rax*4]
0x1802642b1  add     rcx, rdi
0x1802642b4  jmp     rcx; switch jump
0x1802642b6  mov     edx, 4002Ch; jumptable 00000001802642B4 case 2
0x1802642bb  lea     rcx, [rbp+230h+var_290]; jumptable 00000001802642B4 default case, cases 7-9,11-39,43-53
0x1802642bf  call    BrotliAllocate
0x1802642c4  mov     r12, rax
0x1802642c7  movups  xmm0, [rbp+230h+var_84]
0x1802642ce  movups  xmmword ptr [r12], xmm0
0x1802642d3  mov     eax, [rbp+230h+var_74]
0x1802642d9  mov     [r12+10h], eax
0x1802642de  mov     eax, [r12]
0x1802642e2  add     eax, 0FFFFFFFEh; switch 53 cases
0x1802642e5  cmp     eax, 34h
0x1802642e8  ja      def_180264302; jumptable 0000000180264302 default case, cases 2-4,7-9,11-39,43-54
0x1802642ee  cdqe
0x1802642f0  movzx   eax, ds:(byte_180264FB4 - 180000000h)[rdi+rax]
0x1802642f8  mov     ecx, ds:(jpt_180264302 - 180000000h)[rdi+rax*4]
0x1802642ff  add     rcx, rdi
0x180264302  jmp     rcx; switch jump
0x180264304  mov     edx, 40030h; jumptable 00000001802642B4 case 3
0x180264309  jmp     short def_1802642B4; jumptable 00000001802642B4 default case, cases 7-9,11-39,43-53
0x18026430b  mov     edx, 80038h; jumptable 00000001802642B4 cases 4,40,41
0x180264310  jmp     short def_1802642B4; jumptable 00000001802642B4 default case, cases 7-9,11-39,43-53
0x180264312  mov     ecx, dword ptr [rbp+230h+var_84+8]; jumptable 00000001802642B4 case 5
0x180264318  mov     rax, rsi
0x18026431b  shl     rax, cl
0x18026431e  mov     ecx, dword ptr [rbp+230h+var_84+4]
0x180264324  lea     rdx, ds:2[rax*4]
0x18026432c  mov     rax, rsi
0x18026432f  shl     rax, cl
0x180264332  imul    rdx, rax
0x180264336  add     rdx, 40h ; '@'
0x18026433a  jmp     short loc_180264395
0x18026433c  mov     ecx, dword ptr [rbp+230h+var_84+8]; jumptable 00000001802642B4 case 6
0x180264342  mov     rax, rsi
0x180264345  shl     rax, cl
0x180264348  mov     ecx, dword ptr [rbp+230h+var_84+4]
0x18026434e  lea     rdx, ds:2[rax*4]
0x180264356  mov     rax, rsi
0x180264359  shl     rax, cl
0x18026435c  imul    rdx, rax
0x180264360  add     rdx, 50h ; 'P'
0x180264364  jmp     short loc_180264395
0x180264366  mov     edx, 140430h; jumptable 00000001802642B4 case 42
0x18026436b  jmp     def_1802642B4; jumptable 00000001802642B4 default case, cases 7-9,11-39,43-53
0x180264370  mov     edx, 400038h; jumptable 00000001802642B4 case 54
0x180264375  jmp     def_1802642B4; jumptable 00000001802642B4 default case, cases 7-9,11-39,43-53
0x18026437a  mov     ecx, r9d; jumptable 00000001802642B4 case 10
0x18026437d  mov     rdx, rsi
0x180264380  shl     rdx, cl
0x180264383  mov     rax, rbx
0x180264386  cmp     rbx, rdx
0x180264389  cmovnb  rax, rdx
0x18026438d  lea     rdx, ds:80038h[rax*8]
0x180264395  test    rdx, rdx
0x180264398  jnz     def_1802642B4; jumptable 00000001802642B4 default case, cases 7-9,11-39,43-53
0x18026439e  xor     r12d, r12d
0x1802643a1  jmp     loc_1802642C7
0x1802643a6  lea     rdx, [rbp+230h+var_A0]; jumptable 0000000180264302 case 5
0x1802643ad  mov     rcx, r12
0x1802643b0  call    InitializeH5
0x1802643b5  jmp     short def_180264302; jumptable 0000000180264302 default case, cases 2-4,7-9,11-39,43-54
0x1802643b7  lea     rdx, [rbp+230h+var_A0]; jumptable 0000000180264302 case 6
0x1802643be  mov     rcx, r12
0x1802643c1  call    InitializeH6
0x1802643c6  jmp     short def_180264302; jumptable 0000000180264302 default case, cases 2-4,7-9,11-39,43-54
0x1802643c8  lea     rdx, [rbp+230h+var_A0]; jumptable 0000000180264302 case 40
0x1802643cf  mov     rcx, r12
0x1802643d2  call    InitializeH41
0x1802643d7  jmp     short def_180264302; jumptable 0000000180264302 default case, cases 2-4,7-9,11-39,43-54
0x1802643d9  lea     rdx, [rbp+230h+var_A0]; jumptable 0000000180264302 case 41
0x1802643e0  mov     rcx, r12
0x1802643e3  call    InitializeH41
0x1802643e8  jmp     short def_180264302; jumptable 0000000180264302 default case, cases 2-4,7-9,11-39,43-54
0x1802643ea  lea     rdx, [rbp+230h+var_A0]; jumptable 0000000180264302 case 42
0x1802643f1  mov     rcx, r12
0x1802643f4  call    InitializeH42
0x1802643f9  jmp     short def_180264302; jumptable 0000000180264302 default case, cases 2-4,7-9,11-39,43-54
0x1802643fb  lea     rdx, [rbp+230h+var_A0]; jumptable 0000000180264302 case 10
0x180264402  mov     rcx, r12
0x180264405  call    InitializeH10
0x18026440a  mov     [r12+14h], r14d; jumptable 0000000180264302 default case, cases 2-4,7-9,11-39,43-54
0x18026440f  mov     eax, [r12]
0x180264413  add     eax, 0FFFFFFFEh; switch 53 cases
0x180264416  cmp     eax, 34h
0x180264419  ja      def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
0x18026441f  cdqe
0x180264421  movzx   eax, ds:(byte_180265018 - 180000000h)[rdi+rax]
0x180264429  mov     ecx, ds:(jpt_180264433 - 180000000h)[rdi+rax*4]
0x180264430  add     rcx, rdi
0x180264433  jmp     rcx; switch jump
0x180264435  mov     r9, r13; jumptable 0000000180264433 case 2
0x180264438  mov     r8, rbx
0x18026443b  mov     edx, esi
0x18026443d  mov     rcx, r12
0x180264440  call    PrepareH2
0x180264445  jmp     def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
0x18026444a  mov     r9, r13; jumptable 0000000180264433 case 3
0x18026444d  mov     r8, rbx
0x180264450  mov     edx, esi
0x180264452  mov     rcx, r12
0x180264455  call    PrepareH3
0x18026445a  jmp     def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
0x18026445f  mov     r9, r13; jumptable 0000000180264433 case 4
0x180264462  mov     r8, rbx
0x180264465  mov     edx, esi
0x180264467  mov     rcx, r12
0x18026446a  call    PrepareH4
0x18026446f  jmp     short def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
0x180264471  mov     r9, r13; jumptable 0000000180264433 case 5
0x180264474  mov     r8, rbx
0x180264477  mov     edx, esi
0x180264479  mov     rcx, r12
0x18026447c  call    PrepareH5
0x180264481  jmp     short def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
0x180264483  mov     r9, r13; jumptable 0000000180264433 case 6
0x180264486  mov     r8, rbx
0x180264489  mov     edx, esi
0x18026448b  mov     rcx, r12
0x18026448e  call    PrepareH6
0x180264493  jmp     short def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
0x180264495  mov     r9, r13; jumptable 0000000180264433 case 40
0x180264498  mov     r8, rbx
0x18026449b  mov     edx, esi
0x18026449d  mov     rcx, r12
0x1802644a0  call    PrepareH41
0x1802644a5  jmp     short def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
0x1802644a7  mov     r9, r13; jumptable 0000000180264433 case 41
0x1802644aa  mov     r8, rbx
0x1802644ad  mov     edx, esi
0x1802644af  mov     rcx, r12
0x1802644b2  call    PrepareH41
0x1802644b7  jmp     short def_180264433; jumptable 0000000180264433 default case, cases 7-9,11-39,43-53
  ... truncated ...
```

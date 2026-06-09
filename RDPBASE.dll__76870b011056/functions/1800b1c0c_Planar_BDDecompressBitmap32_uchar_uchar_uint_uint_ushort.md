# Planar::BDDecompressBitmap32(uchar *,uchar *,uint,uint,ushort)

- ea: `0x1800b1c0c`
- end: `0x1800b39da`
- name: `?BDDecompressBitmap32@Planar@@YAJPEAE0IIG@Z`
- size: `7630`
- prototype: `__int64 __usercall@<rax>(Planar *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b48b0`

## callees

- `0x1800b1c0c`
- `0x1800c678c`
- `0x1800c67f8`
- `0x1800c68c8`
- `0x1800c692c`

## string_xrefs

- `0x1800b1c86`: `Decompress reads one byte end of buffer`
- `0x1800b23e0`: `Decompress reads one byte end of buffer`
- `0x1800b2407`: `Decompress reads one byte end of buffer`
- `0x1800b2531`: `Decompress reads one byte end of buffer`
- `0x1800b2556`: `Decompress reads one byte end of buffer`
- `0x1800b261d`: `Decompress reads one byte end of buffer`
- `0x1800b2644`: `Decompress reads one byte end of buffer`
- `0x1800b27b7`: `Decompress reads one byte end of buffer`
- `0x1800b27e6`: `Decompress reads one byte end of buffer`
- `0x1800b2827`: `Decompress reads one byte end of buffer`
- `0x1800b29a1`: `Decompress reads one byte end of buffer`
- `0x1800b29c8`: `Decompress reads one byte end of buffer`
- `0x1800b2a08`: `Decompress reads one byte end of buffer`
- `0x1800b2ab4`: `Decompress reads one byte end of buffer`
- `0x1800b2fb9`: `Decompress reads one byte end of buffer`
- `0x1800b35ed`: `Decompress reads one byte end of buffer`
- `0x1800b3614`: `Decompress reads one byte end of buffer`
- `0x1800b1dd8`: `Decompress reads off end of buffer`
- `0x1800b20cc`: `Decompress reads off end of buffer`
- `0x1800b23b4`: `Decompress reads off end of buffer`
- `0x1800b242c`: `Decompress reads off end of buffer`
- `0x1800b2506`: `Decompress reads off end of buffer`
- `0x1800b2587`: `Decompress reads off end of buffer`
- `0x1800b25f1`: `Decompress reads off end of buffer`
- `0x1800b2669`: `Decompress reads off end of buffer`
- `0x1800b284b`: `Decompress reads off end of buffer`
- `0x1800b2885`: `Decompress reads off end of buffer`
- `0x1800b290f`: `Decompress reads off end of buffer`
- `0x1800b2a2e`: `Decompress reads off end of buffer`
- `0x1800b2a68`: `Decompress reads off end of buffer`
- `0x1800b2af2`: `Decompress reads off end of buffer`
- `0x1800b2ffa`: `Decompress reads off end of buffer`
- `0x1800b35c1`: `Decompress reads off end of buffer`
- `0x1800b3682`: `Decompress reads off end of buffer`
- `0x1800b372f`: `Decompress reads off end of buffer`
- `0x1800b1d7b`: `Decompress write off end of buffer`
- `0x1800b1d9e`: `Decompress write off end of buffer`
- `0x1800b1e0b`: `Decompress write off end of buffer`
- `0x1800b201d`: `Decompress write off end of buffer`
- `0x1800b20ff`: `Decompress write off end of buffer`
- `0x1800b2337`: `Decompress write off end of buffer`
- `0x1800b245b`: `Decompress write off end of buffer`
- `0x1800b25a1`: `Decompress write off end of buffer`
- `0x1800b2698`: `Decompress write off end of buffer`
- `0x1800b28d2`: `Decompress write off end of buffer`
- `0x1800b2b1f`: `Decompress write off end of buffer`
- `0x1800b2dba`: `Decompress write off end of buffer`
- `0x1800b302d`: `Decompress write off end of buffer`
- `0x1800b335b`: `Decompress write off end of buffer`
- `0x1800b364d`: `Decompress write off end of buffer`
- `0x1800b36f9`: `Decompress write off end of buffer`
- `0x1800b37a1`: `Decompress write off end of buffer`
- `0x1800b37ee`: `Decompress write off end of buffer`

## pseudocode

```c
__int64 __fastcall Planar::BDDecompressBitmap32(
        Planar *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int16 a5)
{
  unsigned int v5; // esi
  unsigned int v6; // ebp
  unsigned __int8 *v7; // r14
  int v8; // eax
  int v9; // r12d
  unsigned __int8 *v10; // rdi
  unsigned __int8 *v11; // rbx
  unsigned __int8 *v12; // r13
  int v13; // r15d
  char v14; // al
  char v15; // cl
  unsigned __int8 *v16; // r15
  int v17; // ecx
  __int64 v18; // rcx
  unsigned __int8 v19; // r9
  unsigned __int16 v20; // dx
  int v21; // edx
  __int64 v22; // rcx
  unsigned __int8 v23; // r9
  __int16 v24; // ax
  __int64 v25; // rcx
  unsigned __int8 v26; // r9
  __int16 v27; // ax
  __int64 v28; // rcx
  unsigned __int8 v29; // r9
  unsigned __int8 *v30; // rbx
  _BYTE *v31; // rdx
  unsigned __int8 *v32; // rcx
  unsigned __int8 v33; // r9
  unsigned int v34; // r8d
  unsigned int v35; // eax
  unsigned __int8 *v36; // r15
  int v37; // ecx
  int v38; // edx
  __int64 v39; // rcx
  unsigned __int8 v40; // r9
  __int16 v41; // ax
  __int64 v42; // rcx
  unsigned __int8 v43; // r9
  __int64 v44; // rcx
  unsigned __int8 v45; // r9
  __int16 v46; // ax
  __int64 v47; // rcx
  unsigned __int8 v48; // r9
  unsigned __int8 *v49; // r11
  __int64 v50; // rcx
  unsigned __int8 v51; // r9
  unsigned __int8 *v52; // rcx
  _QWORD *v53; // rax
  int v54; // r15d
  unsigned __int8 *v55; // rdi
  unsigned __int8 v56; // r15
  int v57; // r12d
  int v58; // ecx
  int v59; // ecx
  int v60; // eax
  char v61; // al
  int v62; // r15d
  unsigned int v63; // r12d
  int v64; // r15d
  unsigned __int8 *v65; // rdi
  unsigned __int8 v66; // r15
  int v67; // r12d
  int v68; // ecx
  int v69; // ecx
  int v70; // edx
  char v71; // r12
  int v72; // r12d
  char v73; // r12
  unsigned __int8 *v74; // r15
  int v75; // ecx
  __int16 v76; // dx
  unsigned __int8 v77; // eax^2
  char v78; // r12
  int v79; // r12d
  unsigned int v80; // r12d
  char v81; // r12
  char v82; // r15
  int v83; // ecx
  _BYTE *v84; // r10
  _BYTE *v85; // rbx
  int v86; // edx
  int v87; // edx
  int v88; // edx
  int v89; // edx
  _BYTE *v90; // r8
  int v91; // edx
  _BYTE *v92; // rbx
  int v93; // edx
  _BYTE *v94; // r8
  unsigned int v95; // edx
  unsigned int v96; // r9d
  unsigned int v97; // ecx
  unsigned __int8 v98; // al
  unsigned __int8 v99; // r8
  unsigned __int8 v100; // r10
  unsigned __int8 *v101; // rax
  unsigned __int8 v102; // r11
  __int16 v103; // kr00_2
  unsigned __int8 v104; // r8
  unsigned __int8 v105; // r10
  unsigned __int8 v106; // r11
  unsigned __int8 v107; // r8
  unsigned __int8 v108; // r10
  unsigned __int8 v109; // r11
  unsigned __int8 v110; // r8
  unsigned __int8 v111; // r10
  unsigned __int8 v112; // r11
  unsigned __int8 v113; // r8
  unsigned __int8 v114; // r10
  unsigned __int8 v115; // r11
  char v116; // al
  char v117; // r8
  char v118; // r10
  char v119; // r10
  char v120; // r15
  int v121; // r8d
  unsigned __int8 *v122; // r8
  int v123; // ecx
  unsigned int v124; // r12d
  _BYTE *v125; // r10
  unsigned __int8 *v126; // r8
  int v127; // edx
  unsigned int v128; // r10d
  int v129; // edx
  unsigned int v130; // r10d
  int v131; // edx
  unsigned int v132; // r10d
  int v133; // edx
  unsigned int v134; // r10d
  int v135; // edx
  unsigned int v136; // r10d
  int v137; // edx
  int v138; // edx
  int v139; // r8d
  unsigned int v140; // ecx
  unsigned int v141; // edx
  unsigned __int8 *v142; // r11
  unsigned __int8 v143; // al
  unsigned __int8 v144; // r9
  unsigned __int8 v145; // r10
  unsigned int v146; // eax
  bool v147; // zf
  _BYTE *v148; // rax
  unsigned __int8 *v149; // r9
  char v150; // r10
  char v151; // r11
  char v152; // r12
  unsigned __int8 v153; // al
  unsigned __int8 v154; // r10
  unsigned __int8 v155; // r11
  unsigned __int8 v156; // al
  unsigned __int8 v157; // r10
  unsigned __int8 v158; // r11
  unsigned __int8 v159; // al
  unsigned __int8 v160; // r10
  unsigned __int8 v161; // r11
  unsigned __int8 v162; // al
  unsigned __int8 v163; // r10
  unsigned __int8 v164; // r11
  unsigned __int8 v165; // al
  unsigned __int8 v166; // r10
  unsigned __int8 v167; // r11
  unsigned __int8 v168; // al
  int v169; // r15d
  char v170; // r15
  unsigned __int8 *v171; // r12
  int v172; // ecx
  unsigned __int8 *v173; // r12
  unsigned __int16 v174; // cx
  unsigned __int8 v176; // [rsp+30h] [rbp-58h]
  unsigned __int8 v177; // [rsp+31h] [rbp-57h]
  unsigned __int8 v178; // [rsp+32h] [rbp-56h]
  unsigned __int8 v179; // [rsp+33h] [rbp-55h]
  int v180; // [rsp+34h] [rbp-54h]
  int v181; // [rsp+38h] [rbp-50h]
  unsigned __int8 v182; // [rsp+90h] [rbp+8h]
  unsigned __int8 v183; // [rsp+90h] [rbp+8h]
  char v185; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v186; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v187; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v188; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v189; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v190; // [rsp+A8h] [rbp+20h]
  unsigned __int8 v191; // [rsp+A8h] [rbp+20h]
  unsigned int v192; // [rsp+A8h] [rbp+20h]

  v5 = 0;
  v6 = -1;
  v7 = (unsigned __int8 *)this + (unsigned int)a3;
  v8 = (int)a2;
  v181 = 0;
  v9 = 1;
  v10 = (unsigned __int8 *)this;
  v180 = 1;
  v11 = a2;
  v12 = &a2[a4];
  while ( v10 < v7 )
  {
    if ( v9 && (int)v11 - v8 >= (unsigned int)a5 )
    {
      v9 = 0;
      v180 = 0;
      v181 = 0;
    }
    if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
      return (unsigned int)-1626586815;
    v13 = *v10;
    v14 = *v10 & 0xE0;
    if ( !v14 )
    {
      if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586802;
      v170 = *v10++;
      v169 = v170 & 0x1F;
      if ( !v169 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586802;
        v169 = *v10++ + 32;
      }
      goto LABEL_248;
    }
    if ( (_BYTE)v13 == 0xF0 )
    {
      if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586798;
      v169 = *(unsigned __int16 *)(v10 + 1);
      v10 += 3;
LABEL_248:
      if ( !v9 )
      {
        if ( v181 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586788;
          v171 = &v11[-a5];
          if ( !(unsigned int)CheckReadNBytes2Ended(v171, a2, v12, 4u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586787;
          v172 = v6 ^ (v171[3] | (v171[2] << 8) | ((v171[1] | (*v171 << 8)) << 16));
          v11[3] = v6 ^ v171[3];
          v11[2] = BYTE1(v172);
          v11[1] = BYTE2(v172);
          *v11 = HIBYTE(v172);
          v11 += 4;
          --v169;
        }
        if ( (unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(4 * v169), L"Decompress write off end of buffer") )
        {
          while ( 1 )
          {
            if ( !v169 )
            {
              v9 = v180;
              goto LABEL_265;
            }
            v173 = &v11[-a5];
            if ( !(unsigned int)CheckReadNBytes2Ended(v173, a2, v12, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586775;
            --v169;
            v174 = _byteswap_ushort(*((_WORD *)v173 + 1));
            *(_WORD *)v11 = *(_WORD *)v173;
            v11[3] = v174;
            v11[2] = HIBYTE(v174);
            v11 += 4;
          }
        }
        else
        {
          return (unsigned int)-1626586779;
        }
      }
      if ( v181 )
      {
        if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
          return (unsigned int)-1626586766;
        v11[3] = v6;
        v11[2] = BYTE1(v6);
        v11[1] = BYTE2(v6);
        *v11 = HIBYTE(v6);
        v11 += 4;
        --v169;
      }
      if ( !(unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(4 * v169), L"Decompress write off end of buffer") )
        return (unsigned int)-1626586761;
      for ( ; v169; --v169 )
      {
        *(_DWORD *)v11 = 0;
        v11 += 4;
      }
LABEL_265:
      v181 = 1;
LABEL_266:
      v8 = (int)a2;
    }
    else
    {
      v181 = 0;
      v15 = v13 & 0xF0;
      v185 = v13 & 0xF0;
      if ( v14 == 64 || v15 == -48 )
      {
        if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
        {
LABEL_121:
          if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586727;
          v80 = *(unsigned __int16 *)(v10 + 1);
          v10 += 3;
          goto LABEL_123;
        }
        if ( v14 == 64 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586719;
          v78 = *v10++;
          v79 = v78 & 0x1F;
          if ( v79 )
            goto LABEL_116;
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586719;
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586715;
          v81 = *v10++;
          v79 = v81 & 0xF;
          if ( v79 )
          {
LABEL_116:
            v80 = 8 * v79;
            goto LABEL_123;
          }
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586715;
        }
        v80 = *v10++ + 1;
LABEL_123:
        if ( v185 == -48 || (_BYTE)v13 == 0xF7 )
        {
          if ( (unsigned int)CheckReadNBytes(v10, v7, 4u, L"Decompress reads off end of buffer") )
          {
            v6 = v10[3] | (v10[2] << 8) | ((v10[1] | (*v10 << 8)) << 16);
            v10 += 4;
            goto LABEL_127;
          }
          return (unsigned int)-1626586708;
        }
LABEL_127:
        while ( v80 > 8 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586691;
          v82 = *v10;
          if ( v180 )
          {
            if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586679;
            v97 = v6 >> 8;
            v95 = HIWORD(v6);
            if ( (v82 & 1) != 0 )
            {
              *v11 = HIBYTE(v6);
              v98 = BYTE2(v6);
              v99 = BYTE1(v6);
              v100 = v6;
            }
            else
            {
              v98 = 0;
              *v11 = 0;
              v99 = 0;
              v100 = 0;
            }
            v11[3] = v100;
            v11[2] = v99;
            v11[1] = v98;
            v101 = v11 + 4;
            if ( (v82 & 2) != 0 )
            {
              v102 = BYTE2(v6);
              v103 = v6;
              v188 = HIBYTE(v6);
            }
            else
            {
              v102 = 0;
              v188 = 0;
              v103 = 0;
            }
            v11[4] = v188;
            v11[7] = v103;
            v11[6] = HIBYTE(v103);
            v11[5] = v102;
            if ( (v82 & 4) != 0 )
            {
              v11[8] = HIBYTE(v6);
              v104 = BYTE2(v6);
              v105 = BYTE1(v6);
              v106 = v6;
            }
            else
            {
              v104 = 0;
              v11[8] = 0;
              v105 = 0;
              v106 = 0;
            }
            v11[11] = v106;
            v11[10] = v105;
            v11[9] = v104;
            if ( (v82 & 8) != 0 )
            {
              v11[12] = HIBYTE(v6);
              v107 = BYTE2(v6);
              v108 = BYTE1(v6);
              v109 = v6;
            }
            else
            {
              v107 = 0;
              v11[12] = 0;
              v108 = 0;
              v109 = 0;
            }
            v11[15] = v109;
            v11[14] = v108;
            v11[13] = v107;
            if ( (v82 & 0x10) != 0 )
            {
              v11[16] = HIBYTE(v6);
              v110 = BYTE2(v6);
              v111 = BYTE1(v6);
              v112 = v6;
            }
            else
            {
              v110 = 0;
              v11[16] = 0;
              v111 = 0;
              v112 = 0;
            }
            v11[19] = v112;
            v11[18] = v111;
            v11[17] = v110;
            if ( (v82 & 0x20) != 0 )
            {
              v11[20] = HIBYTE(v6);
              v113 = BYTE2(v6);
              v114 = BYTE1(v6);
              v115 = v6;
            }
            else
            {
              v113 = 0;
              v11[20] = 0;
              v114 = 0;
              v115 = 0;
            }
            v11[23] = v115;
            v92 = v11 + 24;
            v101[18] = v114;
            v101[17] = v113;
            if ( (v82 & 0x40) != 0 )
            {
              *v92 = HIBYTE(v6);
              v116 = BYTE2(v6);
              v117 = BYTE1(v6);
              v118 = v6;
            }
            else
            {
              v116 = 0;
              *v92 = 0;
              v117 = 0;
              v118 = 0;
            }
            v92[3] = v118;
            v92[2] = v117;
            v94 = v92 + 4;
            v92[1] = v116;
            if ( v82 >= 0 )
            {
              LOBYTE(v95) = 0;
              *v94 = 0;
              LOBYTE(v97) = 0;
              v119 = 0;
            }
            else
            {
              *v94 = HIBYTE(v6);
              v119 = v6;
            }
            v5 = 0;
            LOBYTE(v96) = v95;
            LOBYTE(v95) = v119;
          }
          else
          {
            if ( !(unsigned int)CheckReadNBytes2Ended(&v11[-a5], a2, v12, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586687;
            if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586683;
            v83 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
            if ( (v82 & 1) != 0 )
              v83 ^= v6;
            *v11 = HIBYTE(v83);
            v84 = v11 + 4;
            v11[3] = v83;
            v11[2] = BYTE1(v83);
            v11[1] = BYTE2(v83);
            v85 = v11 + 4;
            v86 = (unsigned __int8)v85[-a5 + 3]
                | ((unsigned __int8)v85[-a5 + 2] << 8)
                | (((unsigned __int8)v85[-a5 + 1] | ((unsigned __int8)v85[-a5] << 8)) << 16);
            if ( (v82 & 2) != 0 )
              v86 ^= v6;
            *v85 = HIBYTE(v86);
            v84[3] = v86;
            v84[2] = BYTE1(v86);
            v84[1] = BYTE2(v86);
            v87 = (unsigned __int8)v85[-a5 + 7]
                | ((unsigned __int8)v85[-a5 + 6] << 8)
                | ((((unsigned __int8)v85[-a5 + 4] << 8) | (unsigned __int8)v85[-a5 + 5]) << 16);
            if ( (v82 & 4) != 0 )
              v87 ^= v6;
            v85[4] = HIBYTE(v87);
            v85[7] = v87;
            v85[6] = BYTE1(v87);
            v85[5] = BYTE2(v87);
            v88 = (unsigned __int8)v85[-a5 + 11]
                | ((unsigned __int8)v85[-a5 + 10] << 8)
                | (((unsigned __int8)v85[-a5 + 9] | ((unsigned __int8)v85[-a5 + 8] << 8)) << 16);
            if ( (v82 & 8) != 0 )
              v88 ^= v6;
            v85[8] = HIBYTE(v88);
            v85[11] = v88;
            v85[10] = BYTE1(v88);
            v85[9] = BYTE2(v88);
            v89 = (unsigned __int8)v85[-a5 + 15]
                | ((unsigned __int8)v85[-a5 + 14] << 8)
                | ((((unsigned __int8)v85[-a5 + 12] << 8) | (unsigned __int8)v85[-a5 + 13]) << 16);
            if ( (v82 & 0x10) != 0 )
              v89 ^= v6;
            v85[12] = HIBYTE(v89);
            v85[15] = v89;
            v85[14] = BYTE1(v89);
            v85[13] = BYTE2(v89);
            v90 = v85 + 16;
            v91 = (unsigned __int8)v85[-a5 + 19]
                | ((unsigned __int8)v85[-a5 + 18] << 8)
                | (((unsigned __int8)v85[-a5 + 17] | ((unsigned __int8)v85[-a5 + 16] << 8)) << 16);
            if ( (v82 & 0x20) != 0 )
              v91 ^= v6;
            v92 = v85 + 20;
            *v90 = HIBYTE(v91);
            v90[3] = v91;
            v90[2] = BYTE1(v91);
            v90[1] = BYTE2(v91);
            v93 = (unsigned __int8)v92[-a5 + 3]
                | ((unsigned __int8)v92[-a5 + 2] << 8)
                | (((unsigned __int8)v92[-a5 + 1] | ((unsigned __int8)v92[-a5] << 8)) << 16);
            if ( (v82 & 0x40) != 0 )
              v93 ^= v6;
            v94 = v92 + 4;
            *v92 = HIBYTE(v93);
            v92[3] = v93;
            v92[2] = BYTE1(v93);
            v92[1] = BYTE2(v93);
            v95 = (unsigned __int8)v92[-a5 + 7]
                | ((unsigned __int8)v92[-a5 + 6] << 8)
                | ((((unsigned __int8)v92[-a5 + 4] << 8) | (unsigned __int8)v92[-a5 + 5]) << 16);
            if ( v82 < 0 )
              v95 ^= v6;
            v96 = HIWORD(v95);
            v97 = v95 >> 8;
            *v94 = HIBYTE(v95);
          }
          v94[3] = v95;
          ++v10;
          v80 -= 8;
          v11 = v92 + 8;
          v94[2] = v97;
          v94[1] = v96;
        }
        if ( !v80 )
          goto LABEL_2;
        if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586673;
        v120 = *v10++;
        if ( v180 )
        {
          v139 = 8;
          if ( v80 < 8 )
            v139 = v80;
          if ( !(unsigned int)CheckWriteNBytes(
                                v11,
                                v12,
                                (unsigned int)(4 * v139),
                                L"Decompress write off end of buffer") )
            return (unsigned int)-1626586661;
          v140 = v6 >> 8;
          v141 = HIWORD(v6);
          v142 = v11;
          if ( (v120 & 1) != 0 )
          {
            *v11 = HIBYTE(v6);
            v143 = BYTE2(v6);
            v144 = BYTE1(v6);
            v145 = v6;
          }
          else
          {
            v143 = 0;
            *v11 = 0;
            v144 = 0;
            v145 = 0;
          }
          v11[3] = v145;
          v11[2] = v144;
          v11[1] = v143;
          v146 = v80 - 1;
          v9 = v180;
          v11 += 4;
          v192 = v146;
          v147 = v146 == 0;
          v8 = (int)a2;
          if ( !v147 )
          {
            v148 = v142 + 4;
            v149 = v142 + 4;
            if ( (v120 & 2) != 0 )
            {
              v150 = BYTE2(v6);
              v189 = HIBYTE(v6);
              v151 = BYTE1(v6);
              v152 = v6;
            }
            else
            {
              v150 = 0;
              v151 = 0;
              v152 = 0;
              v189 = 0;
            }
            *v11 = v189;
            v11 += 4;
            v5 = 0;
            v148[3] = v152;
            v148[2] = v151;
            v148[1] = v150;
            v8 = (int)a2;
            if ( v192 == 1 )
              goto LABEL_3;
            if ( (v120 & 4) != 0 )
            {
              *v11 = HIBYTE(v6);
              v153 = BYTE2(v6);
              v154 = BYTE1(v6);
              v155 = v6;
            }
            else
            {
              v153 = 0;
              *v11 = 0;
              v154 = 0;
              v155 = 0;
            }
            v149[7] = v155;
            v149[6] = v154;
            v149[5] = v153;
            v11 = v149 + 8;
            v8 = (int)a2;
            if ( v192 == 2 )
              goto LABEL_3;
            if ( (v120 & 8) != 0 )
            {
              *v11 = HIBYTE(v6);
              v156 = BYTE2(v6);
              v157 = BYTE1(v6);
              v158 = v6;
            }
            else
            {
              v156 = 0;
              *v11 = 0;
              v157 = 0;
              v158 = 0;
            }
            v149[11] = v158;
            v149[10] = v157;
            v149[9] = v156;
            v11 = v149 + 12;
            v8 = (int)a2;
            if ( v192 == 3 )
              goto LABEL_3;
            if ( (v120 & 0x10) != 0 )
            {
              *v11 = HIBYTE(v6);
              v159 = BYTE2(v6);
              v160 = BYTE1(v6);
              v161 = v6;
            }
            else
            {
              v159 = 0;
              *v11 = 0;
              v160 = 0;
              v161 = 0;
            }
            v149[15] = v161;
            v149[14] = v160;
            v149[13] = v159;
            v11 = v149 + 16;
            v8 = (int)a2;
            if ( v192 == 4 )
              goto LABEL_3;
            if ( (v120 & 0x20) != 0 )
            {
              *v11 = HIBYTE(v6);
              v162 = BYTE2(v6);
              v163 = BYTE1(v6);
              v164 = v6;
            }
            else
            {
              v162 = 0;
              *v11 = 0;
              v163 = 0;
              v164 = 0;
            }
            v149[19] = v164;
            v149[18] = v163;
            v149[17] = v162;
            v11 = v149 + 20;
            v8 = (int)a2;
            if ( v192 == 5 )
              goto LABEL_3;
            if ( (v120 & 0x40) != 0 )
            {
              v149[20] = HIBYTE(v6);
              v165 = BYTE2(v6);
              v166 = BYTE1(v6);
              v167 = v6;
            }
            else
            {
              v165 = 0;
              v149[20] = 0;
              v166 = 0;
              v167 = 0;
            }
            v149[23] = v167;
            v11 = v149 + 24;
            v149[22] = v166;
            v149[21] = v165;
            v9 = v180;
            v8 = (int)a2;
            if ( v192 != 6 )
            {
              if ( v120 >= 0 )
              {
                LOBYTE(v141) = 0;
                *v11 = 0;
                LOBYTE(v140) = 0;
                v168 = 0;
              }
              else
              {
                *v11 = HIBYTE(v6);
                v168 = v6;
              }
              v149[27] = v168;
              v149[26] = v140;
              v149[25] = v141;
              v11 = v149 + 28;
              goto LABEL_266;
            }
          }
        }
        else
        {
          if ( !(unsigned int)CheckReadNBytes2Ended(&v11[-a5], a2, v12, 4u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586669;
          v121 = 8;
          if ( v80 < 8 )
            v121 = v80;
          if ( !(unsigned int)CheckWriteNBytes(
                                v11,
                                v12,
                                (unsigned int)(4 * v121),
                                L"Decompress write off end of buffer") )
            return (unsigned int)-1626586665;
          v122 = v11;
          v123 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
          if ( (v120 & 1) != 0 )
            v123 ^= v6;
          *v11 = HIBYTE(v123);
          v11[3] = v123;
          v11[2] = BYTE1(v123);
          v11[1] = BYTE2(v123);
          v11 += 4;
          v8 = (int)a2;
          v124 = v80 - 1;
          if ( v124 )
          {
            v125 = v122 + 4;
            v126 = v122 + 4;
            v127 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
            if ( (v120 & 2) != 0 )
              v127 ^= v6;
            *v11 = HIBYTE(v127);
            v11 += 4;
            v125[3] = v127;
            v125[2] = BYTE1(v127);
            v125[1] = BYTE2(v127);
            v128 = v124 - 1;
            v8 = (int)a2;
            v9 = 0;
            if ( v128 )
            {
              v129 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | (((v11[-a5] << 8) | v11[-a5 + 1]) << 16);
              if ( (v120 & 4) != 0 )
                v129 ^= v6;
              *v11 = HIBYTE(v129);
              v126[7] = v129;
              v126[6] = BYTE1(v129);
              v126[5] = BYTE2(v129);
              v11 = v126 + 8;
              v8 = (int)a2;
              v130 = v128 - 1;
              if ( v130 )
              {
                v131 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
                if ( (v120 & 8) != 0 )
                  v131 ^= v6;
                *v11 = HIBYTE(v131);
                v126[11] = v131;
                v126[10] = BYTE1(v131);
                v126[9] = BYTE2(v131);
                v11 = v126 + 12;
                v8 = (int)a2;
                v132 = v130 - 1;
                if ( v132 )
                {
                  v133 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | (((v11[-a5] << 8) | v11[-a5 + 1]) << 16);
                  if ( (v120 & 0x10) != 0 )
                    v133 ^= v6;
                  *v11 = HIBYTE(v133);
                  v126[15] = v133;
                  v126[14] = BYTE1(v133);
                  v126[13] = BYTE2(v133);
                  v11 = v126 + 16;
                  v8 = (int)a2;
                  v134 = v132 - 1;
                  if ( v134 )
                  {
                    v135 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
                    if ( (v120 & 0x20) != 0 )
                      v135 ^= v6;
                    *v11 = HIBYTE(v135);
                    v126[19] = v135;
                    v126[18] = BYTE1(v135);
                    v126[17] = BYTE2(v135);
                    v11 = v126 + 20;
                    v8 = (int)a2;
                    v136 = v134 - 1;
                    if ( v136 )
                    {
                      v137 = v126[-a5 + 23] | (v126[-a5 + 22] << 8) | ((v126[-a5 + 21] | (v126[-a5 + 20] << 8)) << 16);
                      if ( (v120 & 0x40) != 0 )
                        v137 ^= v6;
                      v11 = v126 + 24;
                      v126[20] = HIBYTE(v137);
                      v126[23] = v137;
                      v126[22] = BYTE1(v137);
                      v126[21] = BYTE2(v137);
                      v8 = (int)a2;
                      if ( v136 != 1 )
                      {
                        v138 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
                        if ( v120 < 0 )
                          v138 ^= v6;
                        *v11 = HIBYTE(v138);
                        v126[27] = v138;
                        v126[26] = BYTE1(v138);
                        v126[25] = BYTE2(v138);
                        v11 = v126 + 28;
                        goto LABEL_266;
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
LABEL_3:
            v9 = v180;
          }
        }
      }
      else
      {
        if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
          goto LABEL_121;
        if ( v14 == 32 || v15 == -64 )
        {
          if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
          {
LABEL_96:
            if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586643;
            v72 = *(unsigned __int16 *)(v10 + 1);
            v10 += 3;
          }
          else if ( v14 == 32 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586635;
            v71 = *v10++;
            v72 = v71 & 0x1F;
            if ( !v72 )
            {
              if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586635;
              v72 = *v10 + 32;
              goto LABEL_91;
            }
          }
          else
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586631;
            v73 = *v10++;
            v72 = v73 & 0xF;
            if ( !v72 )
            {
              if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586631;
              v72 = *v10 + 16;
LABEL_91:
              ++v10;
            }
          }
          if ( v185 == -64 || (_BYTE)v13 == 0xF6 )
          {
            if ( !(unsigned int)CheckReadNBytes(v10, v7, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586621;
            v6 = v10[3] | (v10[2] << 8) | ((v10[1] | (*v10 << 8)) << 16);
            v10 += 4;
          }
          if ( !(unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(4 * v72), L"Decompress write off end of buffer") )
            return (unsigned int)-1626586611;
          while ( v72 )
          {
            if ( v180 )
            {
              HIBYTE(v76) = BYTE1(v6);
              LOBYTE(v75) = v6;
              *v11 = HIBYTE(v6);
              v77 = BYTE2(v6);
            }
            else
            {
              v74 = &v11[-a5];
              if ( !(unsigned int)CheckReadNBytes2Ended(v74, a2, v12, 4u, L"Decompress reads off end of buffer") )
                return (unsigned int)-1626586606;
              v75 = v6 ^ (v74[3] | (v74[2] << 8) | ((v74[1] | (*v74 << 8)) << 16));
              v76 = v6 ^ _byteswap_ushort(*((_WORD *)v74 + 1));
              *v11 = HIBYTE(v75);
              v77 = BYTE2(v75);
            }
            v11[3] = v75;
            --v72;
            v11[2] = HIBYTE(v76);
            v11[1] = v77;
            v11 += 4;
          }
          goto LABEL_2;
        }
        if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
          goto LABEL_96;
        if ( v15 == -32 )
        {
          if ( (_BYTE)v13 != 0xF8 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586578;
            v66 = *v10;
            v65 = v10 + 1;
            v64 = v66 & 0xF;
            if ( !v64 )
            {
              if ( !(unsigned int)CheckReadOneByte(v65, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586578;
              v64 = *v65++ + 16;
            }
            goto LABEL_79;
          }
LABEL_73:
          if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586584;
          v64 = *(unsigned __int16 *)(v10 + 1);
          v65 = v10 + 3;
LABEL_79:
          if ( !(unsigned int)CheckReadNBytes(v65, v7, 8u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586574;
          v67 = *v65;
          v187 = v65[1];
          v191 = v65[2];
          v183 = v65[3];
          v176 = v65[4];
          v177 = v65[5];
          v178 = v65[6];
          v179 = v65[7];
          if ( !(unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(8 * v64), L"Decompress write off end of buffer") )
            return (unsigned int)-1626586568;
          v68 = v67;
          v10 = v65 + 8;
          v9 = v180;
          v69 = v183 | (v191 << 8) | ((v187 | (v68 << 8)) << 16);
          v70 = v179 | (v178 << 8) | ((v177 | (v176 << 8)) << 16);
          v8 = (int)a2;
          if ( v64 )
          {
            do
            {
              v11[3] = v69;
              v11[2] = BYTE1(v69);
              v11[1] = BYTE2(v69);
              *v11 = HIBYTE(v69);
              v11[7] = v179;
              v11[6] = v178;
              v11[5] = BYTE2(v70);
              v11[4] = HIBYTE(v70);
              v11 += 8;
              --v64;
            }
            while ( v64 );
            goto LABEL_2;
          }
        }
        else
        {
          if ( (_BYTE)v13 == 0xF8 )
            goto LABEL_73;
          if ( v14 == (char)0x80 )
          {
            if ( (_BYTE)v13 != 0xF4 )
            {
              if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586542;
              v61 = *v10++;
              v60 = v61 & 0x1F;
              if ( !v60 )
              {
                if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                  return (unsigned int)-1626586542;
                v60 = *v10++ + 32;
              }
              goto LABEL_67;
            }
LABEL_61:
            if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586548;
            v60 = *(unsigned __int16 *)(v10 + 1);
            v10 += 3;
LABEL_67:
            v62 = 4 * v60;
            v63 = 4 * v60;
            if ( !(unsigned int)CheckReadNBytes(v10, v7, (unsigned int)(4 * v60), L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586534;
            if ( !(unsigned int)CheckWriteNBytes(v11, v12, v63, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586533;
            v8 = (int)a2;
            v9 = v180;
            if ( v62 )
            {
              do
              {
                --v62;
                *v11++ = *v10++;
              }
              while ( v62 > 0 );
              goto LABEL_266;
            }
          }
          else
          {
            if ( (_BYTE)v13 == 0xF4 )
              goto LABEL_61;
            if ( v14 == 96 )
            {
              if ( (_BYTE)v13 != 0xF3 )
              {
                if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                  return (unsigned int)-1626586510;
                v56 = *v10;
                v55 = v10 + 1;
                v54 = v56 & 0x1F;
                if ( !v54 )
                {
                  if ( !(unsigned int)CheckReadOneByte(v55, v7, L"Decompress reads one byte end of buffer") )
                    return (unsigned int)-1626586510;
                  v54 = *v55++ + 32;
                }
                goto LABEL_55;
              }
            }
            else if ( (_BYTE)v13 != 0xF3 )
            {
              switch ( v13 )
              {
                case 249:
                  if ( v9 )
                  {
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586458;
                    v11[3] = v6;
                    v11[2] = BYTE1(v6);
                    v11[1] = BYTE2(v6);
                    *v11 = HIBYTE(v6);
                    v11[4] = HIBYTE(v6);
                    v53 = v11 + 24;
                    v11[7] = v6;
                    v11[6] = BYTE1(v6);
                    v11[5] = BYTE2(v6);
                    *((_QWORD *)v11 + 1) = 0;
                    *((_QWORD *)v11 + 2) = 0;
                    v11 += 32;
                    *v53 = 0;
                  }
                  else
                  {
                    v36 = &v11[-a5];
                    if ( !(unsigned int)CheckReadNBytes2Ended(v36, a2, v12, 4u, L"Decompress reads off end of buffer") )
                      return (unsigned int)-1626586466;
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586462;
                    v37 = v6 ^ (v36[3] | (v36[2] << 8) | ((v36[1] | (*v36 << 8)) << 16));
                    v11[3] = v6 ^ v36[3];
                    v11[2] = BYTE1(v37);
                    v11[1] = BYTE2(v37);
                    *v11 = HIBYTE(v37);
                    v38 = v6 ^ (v11[-a5 + 7] | (v11[-a5 + 6] << 8) | ((v11[-a5 + 5] | (v11[-a5 + 4] << 8)) << 16));
                    v39 = (__int64)&v11[-a5 + 8];
                    v11[7] = v6 ^ v11[-a5 + 7];
                    v11[6] = BYTE1(v38);
                    v11[5] = BYTE2(v38);
                    v11[4] = HIBYTE(v38);
                    v40 = *(_BYTE *)v39;
                    LOWORD(v38) = *(unsigned __int8 *)(v39 + 2) << 8;
                    v41 = *(unsigned __int8 *)(v39 + 3);
                    v11[9] = _byteswap_ushort(*(_WORD *)v39);
                    v11[8] = v40;
                    v42 = (__int64)&v11[-a5 + 12];
                    LOWORD(v38) = v41 | v38;
                    v11[11] = v38;
                    v11[10] = BYTE1(v38);
                    v43 = *(_BYTE *)v42;
                    LOWORD(v38) = _byteswap_ushort(*(_WORD *)(v42 + 2));
                    v11[13] = *(_BYTE *)(v42 + 1);
                    v11[12] = v43;
                    v11[15] = v38;
                    v11[14] = BYTE1(v38);
                    v44 = (__int64)&v11[-a5 + 16];
                    v45 = *(_BYTE *)v44;
                    LOWORD(v38) = *(unsigned __int8 *)(v44 + 2) << 8;
                    v46 = *(unsigned __int8 *)(v44 + 3);
                    v11[17] = _byteswap_ushort(*(_WORD *)v44);
                    v11[16] = v45;
                    v47 = (__int64)&v11[-a5 + 20];
                    LOWORD(v38) = v46 | v38;
                    v11[19] = v38;
                    v11[18] = BYTE1(v38);
                    v48 = *(_BYTE *)v47;
                    LOWORD(v38) = _byteswap_ushort(*(_WORD *)(v47 + 2));
                    v11[21] = *(_BYTE *)(v47 + 1);
                    v11[20] = v48;
                    v11[23] = v38;
                    v11[22] = BYTE1(v38);
                    v49 = v11 + 24;
                    v50 = (__int64)&v11[-a5 + 24];
                    v11 += 32;
                    v51 = *(_BYTE *)v50;
                    LOWORD(v38) = _byteswap_ushort(*(_WORD *)(v50 + 2));
                    v49[1] = *(_BYTE *)(v50 + 1);
                    *v49 = v51;
                    v52 = &v49[-a5 + 4];
                    v49[3] = v38;
                    v49[2] = BYTE1(v38);
                    LOWORD(v38) = _byteswap_ushort(*((_WORD *)v52 + 1));
                    *((_WORD *)v49 + 2) = *(_WORD *)v52;
                    v49[7] = v38;
                    v49[6] = BYTE1(v38);
                  }
                  break;
                case 250:
                  if ( v9 )
                  {
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586443;
                    v11[3] = v6;
                    v11[2] = BYTE1(v6);
                    v33 = 0;
                    *v11 = HIBYTE(v6);
                    v11[1] = BYTE2(v6);
                    *((_DWORD *)v11 + 1) = 0;
                    v11[8] = HIBYTE(v6);
                    v11[10] = BYTE1(v6);
                    v11[11] = v6;
                    v11[9] = BYTE2(v6);
                    *(_QWORD *)(v11 + 12) = 0;
                    *((_DWORD *)v11 + 5) = 0;
                    v30 = v11 + 24;
                    *(_DWORD *)v30 = 0;
                    v31 = v30 + 4;
                    LOBYTE(v35) = 0;
                    v30[4] = 0;
                    LOBYTE(v34) = 0;
                  }
                  else
                  {
                    v16 = &v11[-a5];
                    if ( !(unsigned int)CheckReadNBytes2Ended(v16, a2, v12, 4u, L"Decompress reads off end of buffer") )
                      return (unsigned int)-1626586451;
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586447;
                    v17 = v6 ^ (v16[3] | (v16[2] << 8) | ((v16[1] | (*v16 << 8)) << 16));
                    v11[3] = v6 ^ v16[3];
                    v11[2] = BYTE1(v17);
                    v11[1] = BYTE2(v17);
                    *v11 = HIBYTE(v17);
                    v18 = (__int64)&v11[-a5 + 4];
                    v19 = *(_BYTE *)v18;
                    v20 = _byteswap_ushort(*(_WORD *)(v18 + 2));
                    v11[5] = *(_BYTE *)(v18 + 1);
                    v11[4] = v19;
                    v11[7] = v20;
                    v11[6] = HIBYTE(v20);
                    v21 = v6 ^ (v11[-a5 + 11] | (v11[-a5 + 10] << 8) | ((v11[-a5 + 9] | (v11[-a5 + 8] << 8)) << 16));
                    v22 = (__int64)&v11[-a5 + 12];
                    v11[11] = v6 ^ v11[-a5 + 11];
                    v11[10] = BYTE1(v21);
                    v11[9] = BYTE2(v21);
                    v11[8] = HIBYTE(v21);
                    v23 = *(_BYTE *)v22;
                    LOWORD(v21) = *(unsigned __int8 *)(v22 + 2) << 8;
                    v24 = *(unsigned __int8 *)(v22 + 3);
                    v11[13] = _byteswap_ushort(*(_WORD *)v22);
                    v11[12] = v23;
                    LOWORD(v21) = v24 | v21;
                    v11[15] = v21;
                    v11[14] = BYTE1(v21);
                    v25 = (__int64)&v11[-a5 + 16];
                    v26 = *(_BYTE *)v25;
                    LOWORD(v21) = *(unsigned __int8 *)(v25 + 2) << 8;
                    v27 = *(unsigned __int8 *)(v25 + 3);
                    v11[17] = _byteswap_ushort(*(_WORD *)v25);
                    v11[16] = v26;
                    v28 = (__int64)&v11[-a5 + 20];
                    LOWORD(v21) = v27 | v21;
                    v11[19] = v21;
                    v11[18] = BYTE1(v21);
                    v29 = *(_BYTE *)v28;
                    LOWORD(v21) = _byteswap_ushort(*(_WORD *)(v28 + 2));
                    v11[21] = *(_BYTE *)(v28 + 1);
                    v11[20] = v29;
                    v11[23] = v21;
                    v11[22] = BYTE1(v21);
                    v30 = v11 + 24;
                    LOWORD(v21) = _byteswap_ushort(*(_WORD *)&v30[-a5 + 2]);
                    *(_WORD *)v30 = *(_WORD *)&v30[-a5];
                    v30[3] = v21;
                    v30[2] = BYTE1(v21);
                    v31 = v30 + 4;
                    v32 = &v30[-a5 + 4];
                    v33 = v32[1];
                    v34 = v32[3] | (v32[2] << 8);
                    v30[4] = *v32;
                    v35 = v34 >> 8;
                  }
                  v31[3] = v34;
                  v31[2] = v35;
                  v31[1] = v33;
                  v11 = v30 + 8;
                  break;
                case 253:
                  if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586479;
                  *(_DWORD *)v11 = -1;
LABEL_31:
                  v11 += 4;
                  break;
                case 254:
                  if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586485;
                  *(_DWORD *)v11 = 0;
                  goto LABEL_31;
              }
              ++v10;
LABEL_2:
              v8 = (int)a2;
              goto LABEL_3;
            }
            if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586516;
            v54 = *(unsigned __int16 *)(v10 + 1);
            v55 = v10 + 3;
LABEL_55:
            if ( !(unsigned int)CheckReadNBytes(v55, v7, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586506;
            v57 = *v55;
            v186 = v55[1];
            v190 = v55[2];
            v182 = v55[3];
            if ( !(unsigned int)CheckWriteNBytes(
                                  v11,
                                  v12,
                                  (unsigned int)(4 * v54),
                                  L"Decompress write off end of buffer") )
              return (unsigned int)-1626586502;
            v58 = v57;
            v9 = v180;
            v10 = v55 + 4;
            v59 = v182 | (v190 << 8) | ((v186 | (v58 << 8)) << 16);
            v8 = (int)a2;
            if ( v54 )
            {
              do
              {
                v11[3] = v59;
                v11[2] = BYTE1(v59);
                v11[1] = BYTE2(v59);
                *v11 = HIBYTE(v59);
                v11 += 4;
                --v54;
              }
              while ( v54 );
              goto LABEL_266;
            }
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800b1c0c  mov     [rsp+arg_8], rdx
0x1800b1c11  push    rbx
0x1800b1c12  push    rbp
0x1800b1c13  push    rsi
0x1800b1c14  push    rdi
0x1800b1c15  push    r12
0x1800b1c17  push    r13
0x1800b1c19  push    r14
0x1800b1c1b  push    r15
0x1800b1c1d  sub     rsp, 48h
0x1800b1c21  xor     esi, esi
0x1800b1c23  mov     r14d, r8d
0x1800b1c26  or      ebp, 0FFFFFFFFh
0x1800b1c29  mov     r13d, r9d
0x1800b1c2c  add     r14, rcx
0x1800b1c2f  mov     [rsp+88h+var_4C], esi
0x1800b1c33  mov     rax, rdx
0x1800b1c36  mov     [rsp+88h+var_50], esi
0x1800b1c3a  lea     r12d, [rsi+1]
0x1800b1c3e  mov     rdi, rcx
0x1800b1c41  mov     [rsp+88h+var_54], r12d
0x1800b1c46  mov     rbx, rdx
0x1800b1c49  add     r13, rdx
0x1800b1c4c  jmp     short loc_1800B1C5B
0x1800b1c4e  mov     rax, [rsp+88h+arg_8]
0x1800b1c56  mov     r12d, [rsp+88h+var_54]
0x1800b1c5b  cmp     rdi, r14
0x1800b1c5e  jnb     loc_1800B39C7
0x1800b1c64  test    r12d, r12d
0x1800b1c67  jz      short loc_1800B1C86
0x1800b1c69  mov     ecx, ebx
0x1800b1c6b  sub     ecx, eax
0x1800b1c6d  movzx   eax, word ptr [rsp+88h+arg_20]
0x1800b1c75  cmp     ecx, eax
0x1800b1c77  jb      short loc_1800B1C86
0x1800b1c79  xor     r12d, r12d
0x1800b1c7c  mov     [rsp+88h+var_54], r12d
0x1800b1c81  mov     [rsp+88h+var_50], r12d
0x1800b1c86  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x1800b1c8d  mov     rdx, r14; unsigned __int8 *
0x1800b1c90  mov     rcx, rdi; unsigned __int8 *
0x1800b1c93  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x1800b1c98  test    eax, eax
0x1800b1c9a  jz      loc_1800B39C2
0x1800b1ca0  movzx   r15d, byte ptr [rdi]
0x1800b1ca4  mov     al, r15b
0x1800b1ca7  and     al, 0E0h
0x1800b1ca9  jz      loc_1800B35ED
0x1800b1caf  cmp     r15b, 0F0h
0x1800b1cb3  jz      loc_1800B35C1
0x1800b1cb9  mov     cl, r15b
0x1800b1cbc  mov     [rsp+88h+var_50], 0
0x1800b1cc4  and     cl, 0F0h
0x1800b1cc7  mov     [rsp+88h+arg_10], cl
0x1800b1cce  cmp     al, 40h ; '@'
0x1800b1cd0  jz      loc_1800B298D
0x1800b1cd6  cmp     cl, 0D0h
0x1800b1cd9  jz      loc_1800B298D
0x1800b1cdf  cmp     r15b, 0F2h
0x1800b1ce3  jz      loc_1800B2A2E
0x1800b1ce9  cmp     r15b, 0F7h
0x1800b1ced  jz      loc_1800B2A2E
0x1800b1cf3  cmp     al, 20h ; ' '
0x1800b1cf5  jz      loc_1800B27A3
0x1800b1cfb  cmp     cl, 0C0h
0x1800b1cfe  jz      loc_1800B27A3
0x1800b1d04  cmp     r15b, 0F1h
0x1800b1d08  jz      loc_1800B284B
0x1800b1d0e  cmp     r15b, 0F6h
0x1800b1d12  jz      loc_1800B284B
0x1800b1d18  cmp     cl, 0E0h
0x1800b1d1b  jz      loc_1800B25EB
0x1800b1d21  cmp     r15b, 0F8h
0x1800b1d25  jz      loc_1800B25F1
0x1800b1d2b  cmp     al, 80h
0x1800b1d2d  jz      loc_1800B2500
0x1800b1d33  cmp     r15b, 0F4h
0x1800b1d37  jz      loc_1800B2506
0x1800b1d3d  cmp     al, 60h ; '`'
0x1800b1d3f  jz      loc_1800B23AE
0x1800b1d45  cmp     r15b, 0F3h
0x1800b1d49  jz      loc_1800B23B4
0x1800b1d4f  mov     ecx, r15d
0x1800b1d52  sub     ecx, 0F9h
0x1800b1d58  jz      loc_1800B20BA
0x1800b1d5e  sub     ecx, 1
0x1800b1d61  jz      short loc_1800B1DC6
0x1800b1d63  sub     ecx, 3
0x1800b1d66  jz      short loc_1800B1D9E
0x1800b1d68  cmp     ecx, 1
0x1800b1d6b  jnz     loc_1800B23A6
0x1800b1d71  lea     r8d, [rcx+3]; unsigned __int64
0x1800b1d75  mov     rdx, r13; unsigned __int8 *
0x1800b1d78  mov     rcx, rbx; unsigned __int8 *
0x1800b1d7b  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x1800b1d82  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x1800b1d87  test    eax, eax
0x1800b1d89  jz      loc_1800B3836
0x1800b1d8f  mov     dword ptr [rbx], 0
0x1800b1d95  add     rbx, 4
0x1800b1d99  jmp     loc_1800B23A6
0x1800b1d9e  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x1800b1da5  mov     r8d, 4; unsigned __int64
0x1800b1dab  mov     rdx, r13; unsigned __int8 *
0x1800b1dae  mov     rcx, rbx; unsigned __int8 *
0x1800b1db1  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x1800b1db6  test    eax, eax
0x1800b1db8  jz      loc_1800B3840
0x1800b1dbe  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800b1dc4  jmp     short loc_1800B1D95
0x1800b1dc6  test    r12d, r12d
0x1800b1dc9  jnz     loc_1800B201D
0x1800b1dcf  movzx   r12d, word ptr [rsp+88h+arg_20]
0x1800b1dd8  lea     rax, aDecompressRead; "Decompress reads off end of buffer"
0x1800b1ddf  mov     rdx, [rsp+88h+arg_8]; unsigned __int8 *
0x1800b1de7  mov     r15, rbx
0x1800b1dea  sub     r15, r12
0x1800b1ded  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x1800b1df2  mov     rcx, r15; unsigned __int8 *
0x1800b1df5  mov     r9d, 4; unsigned __int64
0x1800b1dfb  mov     r8, r13; unsigned __int8 *
0x1800b1dfe  call    ?CheckReadNBytes2Ended@@YAHPEAE00_KPEBG@Z; CheckReadNBytes2Ended(uchar *,uchar *,uchar *,unsigned __int64,ushort const *)
0x1800b1e03  test    eax, eax
0x1800b1e05  jz      loc_1800B3854
0x1800b1e0b  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x1800b1e12  mov     r8d, 20h ; ' '; unsigned __int64
0x1800b1e18  mov     rdx, r13; unsigned __int8 *
0x1800b1e1b  mov     rcx, rbx; unsigned __int8 *
0x1800b1e1e  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x1800b1e23  test    eax, eax
0x1800b1e25  jz      loc_1800B384A
0x1800b1e2b  movzx   ecx, byte ptr [r15]
0x1800b1e2f  movzx   eax, byte ptr [r15+1]
0x1800b1e34  shl     ecx, 8
0x1800b1e37  or      ecx, eax
0x1800b1e39  movzx   eax, byte ptr [r15+2]
0x1800b1e3e  shl     eax, 8
0x1800b1e41  shl     ecx, 10h
0x1800b1e44  or      ecx, eax
0x1800b1e46  movzx   eax, byte ptr [r15+3]
0x1800b1e4b  or      ecx, eax
0x1800b1e4d  xor     ecx, ebp
0x1800b1e4f  mov     [rbx+3], cl
0x1800b1e52  mov     eax, ecx
0x1800b1e54  shr     eax, 8
0x1800b1e57  mov     [rbx+2], al
0x1800b1e5a  mov     eax, ecx
0x1800b1e5c  shr     eax, 10h
0x1800b1e5f  mov     [rbx+1], al
0x1800b1e62  shr     ecx, 18h
0x1800b1e65  mov     [rbx], cl
0x1800b1e67  lea     rcx, [rbx+4]
0x1800b1e6b  sub     rcx, r12
0x1800b1e6e  movzx   r9d, byte ptr [rcx]
0x1800b1e72  movzx   eax, byte ptr [rcx+1]
0x1800b1e76  mov     r8d, r9d
0x1800b1e79  movzx   edx, byte ptr [rcx+2]
0x1800b1e7d  shl     edx, 8
0x1800b1e80  shl     r8d, 8
0x1800b1e84  or      r8d, eax
0x1800b1e87  movzx   eax, byte ptr [rcx+3]
0x1800b1e8b  or      edx, eax
0x1800b1e8d  mov     [rbx+5], r8b
0x1800b1e91  mov     [rbx+4], r9b
0x1800b1e95  lea     rcx, [rbx+8]
0x1800b1e99  sub     rcx, r12
0x1800b1e9c  mov     eax, r8d
0x1800b1e9f  shl     eax, 10h
0x1800b1ea2  or      edx, eax
0x1800b1ea4  mov     [rbx+7], dl
0x1800b1ea7  shr     edx, 8
0x1800b1eaa  mov     [rbx+6], dl
0x1800b1ead  movzx   eax, byte ptr [rcx+1]
0x1800b1eb1  movzx   edx, byte ptr [rcx]
0x1800b1eb4  shl     edx, 8
0x1800b1eb7  or      edx, eax
0x1800b1eb9  movzx   eax, byte ptr [rcx+2]
0x1800b1ebd  shl     eax, 8
0x1800b1ec0  shl     edx, 10h
0x1800b1ec3  or      edx, eax
0x1800b1ec5  movzx   eax, byte ptr [rcx+3]
0x1800b1ec9  or      edx, eax
0x1800b1ecb  lea     rcx, [rbx+0Ch]
0x1800b1ecf  xor     edx, ebp
0x1800b1ed1  sub     rcx, r12
0x1800b1ed4  mov     [rbx+0Bh], dl
0x1800b1ed7  mov     eax, edx
0x1800b1ed9  shr     eax, 8
0x1800b1edc  mov     [rbx+0Ah], al
0x1800b1edf  mov     eax, edx
0x1800b1ee1  shr     eax, 10h
0x1800b1ee4  mov     [rbx+9], al
0x1800b1ee7  shr     edx, 18h
0x1800b1eea  mov     [rbx+8], dl
0x1800b1eed  movzx   r9d, byte ptr [rcx]
0x1800b1ef1  movzx   r8d, byte ptr [rcx+1]
0x1800b1ef6  mov     eax, r9d
0x1800b1ef9  movzx   edx, byte ptr [rcx+2]
0x1800b1efd  shl     eax, 8
0x1800b1f00  or      r8d, eax
0x1800b1f03  shl     edx, 8
0x1800b1f06  movzx   eax, byte ptr [rcx+3]
0x1800b1f0a  lea     rcx, [rbx+10h]
0x1800b1f0e  or      edx, eax
0x1800b1f10  mov     [rbx+0Dh], r8b
0x1800b1f14  mov     eax, r8d
0x1800b1f17  mov     [rbx+0Ch], r9b
0x1800b1f1b  shl     eax, 10h
0x1800b1f1e  or      edx, eax
0x1800b1f20  mov     [rbx+0Fh], dl
0x1800b1f23  shr     edx, 8
0x1800b1f26  mov     [rbx+0Eh], dl
0x1800b1f29  sub     rcx, r12
0x1800b1f2c  movzx   r9d, byte ptr [rcx]
0x1800b1f30  movzx   edx, byte ptr [rcx+2]
0x1800b1f34  mov     eax, r9d
0x1800b1f37  movzx   r8d, byte ptr [rcx+1]
0x1800b1f3c  shl     eax, 8
0x1800b1f3f  or      r8d, eax
0x1800b1f42  shl     edx, 8
0x1800b1f45  movzx   eax, byte ptr [rcx+3]
0x1800b1f49  lea     rcx, [rbx+14h]
0x1800b1f4d  or      edx, eax
0x1800b1f4f  mov     [rbx+11h], r8b
0x1800b1f53  mov     [rbx+10h], r9b
0x1800b1f57  mov     eax, r8d
0x1800b1f5a  shl     eax, 10h
0x1800b1f5d  sub     rcx, r12
0x1800b1f60  or      edx, eax
0x1800b1f62  mov     [rbx+13h], dl
0x1800b1f65  shr     edx, 8
0x1800b1f68  mov     [rbx+12h], dl
0x1800b1f6b  movzx   r9d, byte ptr [rcx]
0x1800b1f6f  movzx   edx, byte ptr [rcx+2]
0x1800b1f73  mov     eax, r9d
0x1800b1f76  movzx   r8d, byte ptr [rcx+1]
0x1800b1f7b  shl     eax, 8
0x1800b1f7e  or      r8d, eax
0x1800b1f81  shl     edx, 8
0x1800b1f84  movzx   eax, byte ptr [rcx+3]
0x1800b1f88  or      edx, eax
0x1800b1f8a  mov     [rbx+15h], r8b
0x1800b1f8e  mov     [rbx+14h], r9b
0x1800b1f92  mov     eax, r8d
0x1800b1f95  shl     eax, 10h
0x1800b1f98  or      edx, eax
0x1800b1f9a  mov     [rbx+17h], dl
0x1800b1f9d  shr     edx, 8
0x1800b1fa0  mov     [rbx+16h], dl
0x1800b1fa3  add     rbx, 18h
0x1800b1fa7  mov     rcx, rbx
0x1800b1faa  sub     rcx, r12
0x1800b1fad  movzx   eax, byte ptr [rcx+1]
0x1800b1fb1  movzx   r9d, byte ptr [rcx]
0x1800b1fb5  movzx   edx, byte ptr [rcx+2]
0x1800b1fb9  mov     r8d, r9d
0x1800b1fbc  shl     r8d, 8
0x1800b1fc0  or      r8d, eax
0x1800b1fc3  shl     edx, 8
0x1800b1fc6  movzx   eax, byte ptr [rcx+3]
0x1800b1fca  or      edx, eax
0x1800b1fcc  mov     [rbx+1], r8b
0x1800b1fd0  mov     eax, r8d
0x1800b1fd3  mov     [rbx], r9b
0x1800b1fd6  shl     eax, 10h
0x1800b1fd9  or      edx, eax
0x1800b1fdb  mov     [rbx+3], dl
0x1800b1fde  shr     edx, 8
0x1800b1fe1  mov     [rbx+2], dl
0x1800b1fe4  lea     rdx, [rbx+4]
0x1800b1fe8  mov     rcx, rdx
0x1800b1feb  sub     rcx, r12
0x1800b1fee  movzx   eax, byte ptr [rcx+3]
0x1800b1ff2  movzx   r8d, byte ptr [rcx+2]
0x1800b1ff7  mov     r9b, [rcx+1]
0x1800b1ffb  shl     r8d, 8
0x1800b1fff  or      r8d, eax
0x1800b2002  mov     al, [rcx]
0x1800b2004  mov     [rdx], al
0x1800b2006  lea     rax, [rbx+8]
0x1800b200a  mov     [rsp+88h+arg_0], rax
0x1800b2012  mov     eax, r8d
0x1800b2015  shr     eax, 8
0x1800b2018  jmp     loc_1800B20A0
0x1800b201d  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x1800b2024  mov     r8d, 20h ; ' '; unsigned __int64
0x1800b202a  mov     rdx, r13; unsigned __int8 *
0x1800b202d  mov     rcx, rbx; unsigned __int8 *
0x1800b2030  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x1800b2035  test    eax, eax
0x1800b2037  jz      loc_1800B385E
0x1800b203d  mov     [rbx+3], bpl
0x1800b2041  mov     edx, ebp
0x1800b2043  shr     edx, 8
0x1800b2046  mov     eax, ebp
0x1800b2048  mov     [rbx+2], dl
0x1800b204b  mov     ecx, ebp
0x1800b204d  shr     eax, 18h
0x1800b2050  xor     r9b, r9b
0x1800b2053  mov     [rbx], al
  ... truncated ...
```

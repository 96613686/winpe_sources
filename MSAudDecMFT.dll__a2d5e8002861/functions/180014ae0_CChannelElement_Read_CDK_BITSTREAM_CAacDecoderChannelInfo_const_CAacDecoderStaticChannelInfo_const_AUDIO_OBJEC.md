# CChannelElement_Read(CDK_BITSTREAM *,CAacDecoderChannelInfo * * const,CAacDecoderStaticChannelInfo * * const,AUDIO_OBJECT_TYPE,SamplingRateInfo *,uint,uint,uint,uchar,signed char,TRANSPORTDEC *)

- ea: `0x180014ae0`
- end: `0x180016821`
- name: `?CChannelElement_Read@@YA?AW4AAC_DECODER_ERROR@@PEAUCDK_BITSTREAM@@QEAPEAUCAacDecoderChannelInfo@@QEAPEAUCAacDecoderStaticChannelInfo@@W4AUDIO_OBJECT_TYPE@@PEAUSamplingRateInfo@@IIIECPEAUTRANSPORTDEC@@@Z`
- size: `7489`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `27`
- tags: ``

## callers

- `0x18000c510`

## callees

- `0x1800110c0`
- `0x18001308c`
- `0x1800130d8`
- `0x180013550`
- `0x180014058`
- `0x180014078`
- `0x180014280`
- `0x180014550`
- `0x180014ae0`
- `0x180016880`
- `0x1800175b0`
- `0x1800176d0`
- `0x180017cc0`
- `0x180017d2c`
- `0x180017db8`
- `0x1800285e0`
- `0x18002b66c`
- `0x18002be3c`
- `0x18003c1f0`
- `0x180044774`
- `0x18004756c`
- `0x180047c58`
- `0x180048474`
- `0x18004af04`
- `0x18004dcfc`
- `0x18004dd14`
- `0x18007b580`

## pseudocode

```c
__int64 __fastcall CChannelElement_Read(
        unsigned int *a1,
        _QWORD *a2,
        __int64 a3,
        int a4,
        struct SamplingRateInfo *a5,
        unsigned int a6,
        __int16 a7,
        int a8,
        unsigned __int8 a9,
        char a10,
        struct TRANSPORTDEC *a11)
{
  unsigned __int8 v11; // bp
  __int64 (**v14)[2]; // r15
  int v15; // r13d
  __int64 v16; // rbx
  unsigned int v17; // r14d
  int v18; // r12d
  _QWORD *v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // r8
  __int64 v22; // r9
  _QWORD *v23; // r11
  __int64 *v24; // rcx
  int v25; // ebx
  int v26; // esi
  int v27; // ecx
  int SectionData; // r13d
  __int64 v29; // rax
  struct CAacDecoderChannelInfo *v30; // rcx
  __m128 si128; // xmm7
  int v32; // edi
  __m128i v33; // xmm10
  unsigned int v34; // ebx
  _QWORD *v35; // r10
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // r13
  __int64 v39; // r14
  struct SamplingRateInfo *v40; // rcx
  int v41; // edx
  __int64 v42; // r15
  int v43; // ebx
  int v44; // ebp
  __int64 v45; // r12
  int v46; // edi
  int i; // esi
  int v48; // r9d
  unsigned __int8 v49; // cl
  __int64 v50; // r8
  __int64 v51; // rcx
  int v52; // ebx
  __int64 v53; // rax
  __int64 v54; // rcx
  __m128 v55; // xmm0
  __int64 v56; // rdi
  int v57; // ecx
  __m128 j; // xmm1
  __int64 v59; // rax
  __m128 v60; // xmm0
  float v61; // xmm6_4
  int v62; // ecx
  float v63; // xmm1_4
  int v64; // r8d
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // eax
  float v68; // xmm0_4
  __int64 v69; // rcx
  int v70; // eax
  float v71; // xmm0_4
  __int64 v72; // rcx
  int v73; // eax
  __int64 v74; // rdx
  __int64 k; // rdx
  int v76; // r8d
  float v77; // xmm3_4
  __int64 v78; // rdx
  int v79; // ecx
  float v81; // xmm1_4
  int v82; // eax
  int v83; // ecx
  unsigned int v84; // edx
  unsigned int v85; // ecx
  __int64 v86; // rdx
  int v87; // ecx
  int v88; // eax
  bool v89; // zf
  int v90; // ecx
  int v91; // esi
  struct TRANSPORTDEC *v92; // rdi
  float v93; // xmm4_4
  float v94; // xmm0_4
  int v95; // eax
  int v96; // ecx
  char v97; // dl
  __int64 v98; // rdx
  _BYTE *v99; // rax
  unsigned int v100; // ecx
  int v101; // ecx
  int v102; // eax
  unsigned __int8 v103; // al
  int v104; // r14d
  int v105; // r13d
  __int64 v106; // rbx
  __int64 v107; // r13
  int v108; // ecx
  int *v109; // rax
  unsigned __int8 v110; // r8
  int v111; // ecx
  char v112; // al
  _DWORD *v113; // rdx
  _DWORD *v114; // r8
  int v115; // r9d
  int v116; // ecx
  int v117; // eax
  unsigned int v118; // eax
  int v119; // ecx
  unsigned __int8 v120; // dl
  __int64 v121; // rdx
  __int64 v122; // rcx
  unsigned __int8 v123; // al
  int v124; // r10d
  __int64 v125; // rdx
  int v126; // eax
  struct CCplxPredictionData *v127; // r11
  struct CJointStereoPersistentData *v128; // rcx
  unsigned int v129; // eax
  unsigned int v130; // eax
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  unsigned int v138; // eax
  __int64 v139; // r9
  __int64 v140; // rdx
  int v141; // eax
  __int64 v142; // rax
  __int64 v143; // rcx
  int v144; // r8d
  __int64 v145; // rax
  unsigned int v146; // r11d
  int v147; // r8d
  __int64 v148; // rdx
  unsigned __int64 v149; // rcx
  int v150; // ecx
  struct CTnsData *v151; // r8
  __int64 v152; // rax
  unsigned int v153; // eax
  int v154; // r14d
  _QWORD *v155; // r12
  __int64 v156; // r13
  __int64 v157; // rcx
  int v158; // r8d
  int v159; // edx
  int v160; // eax
  int v161; // ebp
  int v162; // r14d
  int v163; // r13d
  int v164; // ebx
  int v165; // ebx
  int v166; // eax
  unsigned int v167; // eax
  int v168; // [rsp+20h] [rbp-138h]
  unsigned int v169; // [rsp+30h] [rbp-128h]
  unsigned int v170; // [rsp+60h] [rbp-F8h]
  _DWORD *v171; // [rsp+60h] [rbp-F8h]
  int v172; // [rsp+68h] [rbp-F0h]
  int v173; // [rsp+68h] [rbp-F0h]
  int started; // [rsp+6Ch] [rbp-ECh]
  int v175; // [rsp+70h] [rbp-E8h]
  __int64 (**v176)[2]; // [rsp+78h] [rbp-E0h]
  int v177; // [rsp+80h] [rbp-D8h]
  int v178; // [rsp+80h] [rbp-D8h]
  int v179; // [rsp+84h] [rbp-D4h]
  __int64 v180; // [rsp+88h] [rbp-D0h]
  _DWORD *v181; // [rsp+88h] [rbp-D0h]
  int v182; // [rsp+88h] [rbp-D0h]
  int v183; // [rsp+90h] [rbp-C8h]
  unsigned int v184; // [rsp+94h] [rbp-C4h]
  int v185; // [rsp+94h] [rbp-C4h]
  _BYTE *v186; // [rsp+98h] [rbp-C0h]
  int v187; // [rsp+98h] [rbp-C0h]
  int v188; // [rsp+98h] [rbp-C0h]
  __int64 v189; // [rsp+A0h] [rbp-B8h]
  __int64 v190; // [rsp+A0h] [rbp-B8h]
  __int64 v191; // [rsp+A0h] [rbp-B8h]
  __int64 v192; // [rsp+A0h] [rbp-B8h]
  __int64 v193; // [rsp+A0h] [rbp-B8h]
  int v194; // [rsp+A8h] [rbp-B0h]
  int v195; // [rsp+A8h] [rbp-B0h]
  int v199; // [rsp+178h] [rbp+20h] BYREF

  v11 = a9;
  if ( a4 != 29 )
  {
    switch ( a4 )
    {
      case 2:
      case 5:
        break;
      case 17:
      case 23:
        if ( a9 == 1 )
        {
          if ( a10 )
            v14 = (__int64 (**)[2])&off_180099FC8;
          else
            v14 = (__int64 (**)[2])&off_18009A028;
        }
        else if ( a10 )
        {
          v14 = &off_18009A130;
        }
        else
        {
          v14 = &off_18009A1C0;
        }
        goto LABEL_5;
      case 39:
        if ( a9 == 1 )
        {
          v14 = (__int64 (**)[2])&off_18009A160;
        }
        else if ( a10 > 0 )
        {
          v14 = (__int64 (**)[2])&off_18009A178;
        }
        else
        {
          v14 = (__int64 (**)[2])&off_18009A190;
        }
        goto LABEL_5;
      case 42:
      case 50:
        if ( (a7 & 0x20) != 0 )
        {
          v14 = (__int64 (**)[2])&off_18009A1D8;
        }
        else if ( a9 == 1 )
        {
          v14 = &off_18009A148;
        }
        else
        {
          v14 = off_18009A238;
        }
        goto LABEL_5;
      default:
        return 8195;
    }
  }
  if ( (a7 & 1) != 0 )
  {
    v14 = (__int64 (**)[2])&off_18009A070;
  }
  else
  {
    v14 = (__int64 (**)[2])&off_180098780;
    if ( a9 != 1 )
      v14 = (__int64 (**)[2])&off_180098798;
  }
LABEL_5:
  v15 = 0;
  v176 = v14;
  started = -1;
  v175 = -1;
  v16 = *(_QWORD *)(*a2 + 1704LL);
  v170 = 0;
  v177 = 0;
  v183 = 0;
  memset_0((void *)(v16 + 768), 0, 0x258u);
  v17 = a6;
  *(_QWORD *)(v16 + 1368) = 0;
  *(_WORD *)(v16 + 1376) = 0;
  v18 = v17 & 0x4300;
  v194 = v18;
  *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1379LL) = 0;
  if ( (v17 & 0x4300) != 0 )
  {
    *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1383LL) = 0;
    *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1384LL) = 0;
  }
  v19 = a2 + 1;
  if ( v11 == 2 )
  {
    v20 = *(_QWORD *)(*v19 + 1704LL);
    memset_0((void *)(v20 + 768), 0, 0x258u);
    *(_QWORD *)(v20 + 1368) = 0;
    *(_WORD *)(v20 + 1376) = 0;
    *(_BYTE *)(*(_QWORD *)(*v19 + 1704LL) + 1379LL) = 0;
  }
  v21 = a3;
  v22 = 0;
  v23 = a2;
  v184 = 0;
  if ( a3 && (a7 & 0x40) != 0 )
  {
    v19 = a2 + 1;
    *(_BYTE *)(*(_QWORD *)(*a2 + 1712LL) + 5041LL) = 0;
    v22 = 1;
    v184 = 1;
  }
  if ( (v17 & 0x18) != 0 || a4 == 256 && v11 == 2 )
  {
    *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1379LL) = 1;
    if ( v11 == 2 )
      *(_BYTE *)(*(_QWORD *)(*v19 + 1704LL) + 1379LL) = *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1379LL);
  }
  v24 = (__int64 *)*v14;
  v25 = 0;
  v26 = 0;
  v172 = 0;
  v179 = 0;
  while ( 2 )
  {
    v27 = *((_DWORD *)v24 + v26);
    if ( v27 == 14 )
      goto LABEL_23;
    switch ( v27 )
    {
      case 0:
        v95 = a1[1];
        v96 = 4 - v95;
        v199 = 0;
        if ( 4 - v95 > 0 )
        {
          if ( v96 != 32 )
            v199 = *a1 << v96;
          v130 = CDK_get32(a1 + 2, &_ImageBase, v21);
          v23 = a2;
          *a1 = v130;
          v95 = a1[1] + 32;
        }
        v97 = v199 | (*a1 >> (v95 - 4));
        a1[1] = v95 - 4;
        *(_BYTE *)(*v23 + 1696LL) = v97 & 0xF;
        if ( v11 == 2 )
          *(_BYTE *)(*v19 + 1696LL) = *(_BYTE *)(*v23 + 1696LL);
        goto LABEL_23;
      case 1:
        v123 = CDKreadBit(a1);
        v15 = v123;
        v179 = v123;
        *(_BYTE *)(*(_QWORD *)(a2[v25] + 1704LL) + 1379LL) = v123;
        if ( v11 == 2 )
          *(_BYTE *)(*(_QWORD *)(*v19 + 1704LL) + 1379LL) = *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1379LL);
        goto LABEL_23;
      case 2:
        v82 = a1[1];
        v83 = 8 - v82;
        v199 = 0;
        if ( 8 - v82 > 0 )
        {
          if ( v83 != 32 )
            v199 = *a1 << v83;
          v129 = CDK_get32(a1 + 2, &_ImageBase, v21);
          v23 = a2;
          *a1 = v129;
          v82 = a1[1] + 32;
        }
        v84 = *a1;
        a1[1] = v82 - 8;
        *(_BYTE *)(*(_QWORD *)(v23[v25] + 1704LL) + 1380LL) = v199 | (v84 >> (v82 - 8));
        goto LABEL_23;
      case 3:
        if ( (_DWORD)v22 && *(_BYTE *)(*(_QWORD *)(*v23 + 1704LL) + 1379LL) )
        {
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v21 + 4768LL) + 2080LL) = *(_BYTE *)(*v23 + 1684LL);
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v21 + 4768LL) + 2081LL) = *(_BYTE *)(*v23 + 1682LL);
        }
        v107 = v23[v25];
        v192 = v107;
        *(_BYTE *)(v107 + 1681) = 0;
        if ( (v17 & 0x10) != 0 )
        {
          v114 = (_DWORD *)(v107 + 1684);
          *(_BYTE *)(v107 + 1682) = 0;
          *(_DWORD *)(v107 + 1684) = 0;
          v113 = a1 + 1;
LABEL_128:
          v181 = v113;
          v171 = v114;
          goto LABEL_129;
        }
        if ( !v18 )
          CDKreadBit(a1);
        v108 = a1[1];
        v109 = (int *)(a1 + 1);
        v181 = a1 + 1;
        v110 = 0;
        if ( 2 - v108 > 0 )
        {
          v199 = *a1 << (2 - v108);
          v167 = CDK_get32(a1 + 2, (unsigned int)(2 - v108), 0);
          v110 = v199;
          *a1 = v167;
          v109 = (int *)(a1 + 1);
          v108 = *v181 + 32;
        }
        v111 = v108 - 2;
        *v109 = v111;
        v171 = (_DWORD *)(v107 + 1684);
        *(_DWORD *)(v107 + 1684) = (v110 | (unsigned __int8)(*a1 >> v111)) & 3;
        v112 = CDKreadBit(a1);
        v113 = a1 + 1;
        v114 = (_DWORD *)(v107 + 1684);
        *(_BYTE *)(v107 + 1682) = v112;
        if ( (v17 & 0x20) == 0 || !v112 )
          goto LABEL_128;
        *(_BYTE *)(v107 + 1682) = 2;
LABEL_129:
        if ( (v17 & 0x30) != 0 && *v114 )
        {
          *v114 = 0;
          SectionData = 16386;
        }
        else
        {
          v115 = 4;
          if ( *v114 != 2 )
            v115 = 6;
          v187 = v115;
          *(_BYTE *)(v107 + 1691) = *((_BYTE *)a5 + (*v114 == 2) + 16);
          v116 = *v113;
          v117 = v115 - v116;
          v199 = 0;
          if ( v115 - v116 > 0 )
          {
            if ( v117 != 32 )
              v199 = *a1 << v117;
            v118 = CDK_get32(a1 + 2, v113, v114);
            v113 = v181;
            v114 = v171;
            v115 = v187;
            *a1 = v118;
            *v181 += 32;
            v116 = *v181;
          }
          v119 = v116 - v115;
          *v113 = v119;
          v120 = LOBYTE(BitMask[v115]) & (v199 | (*a1 >> v119));
          *(_BYTE *)(v107 + 1688) = v120;
          if ( v120 > *(_BYTE *)(v107 + 1691) )
          {
            SectionData = 16386;
          }
          else
          {
            if ( *v114 == 2 )
            {
              *(_BYTE *)(v107 + 1690) = CDKreadBits(a1, 7);
              *(_BYTE *)(v107 + 1680) = 0;
              *(_BYTE *)(v107 + 1672) = 1;
              v131 = *(unsigned __int8 *)(v107 + 1680);
              if ( (*(_BYTE *)(v107 + 1690) & 0x40) != 0 )
                ++*(_BYTE *)(v131 + v107 + 1672);
              else
                *(_BYTE *)(v107 + 1680) = v131 + 1;
              *(_BYTE *)(v107 + 1673) = 1;
              v132 = *(unsigned __int8 *)(v107 + 1680);
              if ( (*(_BYTE *)(v107 + 1690) & 0x20) != 0 )
                ++*(_BYTE *)(v132 + v107 + 1672);
              else
                *(_BYTE *)(v107 + 1680) = v132 + 1;
              *(_BYTE *)(v107 + 1674) = 1;
              v133 = *(unsigned __int8 *)(v107 + 1680);
              if ( (*(_BYTE *)(v107 + 1690) & 0x10) != 0 )
                ++*(_BYTE *)(v133 + v107 + 1672);
              else
                *(_BYTE *)(v107 + 1680) = v133 + 1;
              *(_BYTE *)(v107 + 1675) = 1;
              v134 = *(unsigned __int8 *)(v107 + 1680);
              if ( (*(_BYTE *)(v107 + 1690) & 8) != 0 )
                ++*(_BYTE *)(v134 + v107 + 1672);
              else
                *(_BYTE *)(v107 + 1680) = v134 + 1;
              *(_BYTE *)(v107 + 1676) = 1;
              v135 = *(unsigned __int8 *)(v107 + 1680);
              if ( (*(_BYTE *)(v107 + 1690) & 4) != 0 )
                ++*(_BYTE *)(v135 + v107 + 1672);
              else
                *(_BYTE *)(v107 + 1680) = v135 + 1;
              *(_BYTE *)(v107 + 1677) = 1;
              v136 = *(unsigned __int8 *)(v107 + 1680);
              if ( (*(_BYTE *)(v107 + 1690) & 2) != 0 )
                ++*(_BYTE *)(v136 + v107 + 1672);
              else
                *(_BYTE *)(v107 + 1680) = v136 + 1;
              *(_BYTE *)(v107 + 1678) = 1;
              v137 = *(unsigned __int8 *)(v107 + 1680);
              if ( (*(_BYTE *)(v107 + 1690) & 1) != 0 )
                ++*(_BYTE *)(v137 + v107 + 1672);
              else
                *(_BYTE *)(v107 + 1680) = v137 + 1;
              ++*(_BYTE *)(v107 + 1680);
              *(_BYTE *)(v107 + 1679) = 1;
              goto LABEL_141;
            }
            if ( (v17 & 0x4398) != 0 || !(unsigned __int8)CDKreadBit(a1) )
            {
              *(_BYTE *)(v107 + 1680) = 1;
              *(_BYTE *)(v107 + 1672) = 1;
LABEL_141:
              SectionData = 0;
              *(_BYTE *)(v192 + 1681) = 1;
              goto LABEL_142;
            }
            SectionData = 16391;
          }
        }
LABEL_142:
        v170 = SectionData;
        if ( (a7 & 0x2000) == 0 || !*(_DWORD *)(a2[v25] + 1684LL) )
        {
          if ( v11 == 2 )
          {
            v121 = *a2;
            if ( *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1379LL) )
            {
              v122 = *v19;
              *(_OWORD *)(v122 + 1672) = *(_OWORD *)(v121 + 1672);
              *(_DWORD *)(v122 + 1688) = *(_DWORD *)(v121 + 1688);
            }
          }
LABEL_21:
          if ( SectionData )
          {
            v34 = v170;
            goto LABEL_80;
          }
          v15 = v179;
LABEL_23:
          ++v26;
          v24 = (__int64 *)*v176;
          if ( *((_DWORD *)*v176 + v26) == 40 )
          {
            si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
            v32 = 0;
            v33 = _mm_load_si128((const __m128i *)&_xmm);
            v34 = v170;
            v35 = a2;
            v36 = v11;
            v195 = v11;
            while ( 1 )
            {
              v173 = v32;
              if ( v32 >= v36 )
                goto LABEL_80;
              v37 = v35[v32];
              if ( (unsigned int)(*(_DWORD *)(v37 + 1700) - 1) <= 1 )
              {
                v38 = *(_QWORD *)(v37 + 1704) + 640LL;
                v189 = v38;
                *(__m128i *)v38 = v33;
                *(__m128i *)(v38 + 16) = v33;
                *(__m128i *)(v38 + 32) = v33;
                *(__m128i *)(v38 + 48) = v33;
                *(__m128i *)(v38 + 64) = v33;
                *(__m128i *)(v38 + 80) = v33;
                *(__m128i *)(v38 + 96) = v33;
                *(__m128i *)(v38 + 112) = v33;
                v39 = v35[v32];
                v40 = a5;
                v41 = *(unsigned __int8 *)(v39 + 1688);
                v42 = *(_QWORD *)(v39 + 1704);
                if ( *(_DWORD *)(v39 + 1684) == 2 )
                  v40 = (struct SamplingRateInfo *)((char *)a5 + 8);
                v43 = 0;
                v178 = *(unsigned __int8 *)(v39 + 1688);
                v44 = 0;
                a9 = *(_BYTE *)(v39 + 1691);
                v45 = *(_QWORD *)v40;
                v199 = 0;
                while ( v44 < *(unsigned __int8 *)(v39 + 1680) )
                {
                  v46 = 0;
LABEL_32:
                  v185 = v46;
                  if ( v46 < *(unsigned __int8 *)(v44 + v39 + 1672) )
                  {
                    for ( i = 0; ; ++i )
                    {
                      if ( i >= v41 )
                      {
                        v78 = *(__int16 *)(v45 + 2LL * v41);
                        memset_0(
                          (void *)(*(_QWORD *)(v39 + 1664) + 4 * (v78 + *(_DWORD *)(v39 + 1692) * v43)),
                          0,
                          (unsigned int)(4 * (*(__int16 *)(v45 + 2LL * a9) - (_DWORD)v78)));
                        v41 = v178;
                        v46 = v185 + 1;
                        v199 = ++v43;
                        goto LABEL_32;
                      }
                      v48 = i + 16 * v44;
                      v49 = *(_BYTE *)(v48 + v42 + 512);
                      if ( v49 >= 0x10u || (unsigned __int8)(v49 - 1) <= 0xBu )
                        break;
LABEL_51:
                      ;
                    }
                    v50 = *(__int16 *)(v45 + 2LL * i);
                    v51 = *(_DWORD *)(v39 + 1692) * v43;
                    v52 = *(__int16 *)(v45 + 2LL * i + 2) - (_DWORD)v50;
                    v53 = *(_QWORD *)(v39 + 1664);
                    v54 = v50 + v51;
                    v55 = *(__m128 *)(v53 + 4 * v54);
                    v56 = v53 + 4 * v54;
                    v57 = 4;
                    for ( j = _mm_and_ps(si128, v55);
                          v57 < v52;
                          j = _mm_max_ps(_mm_and_ps(*(__m128 *)(v56 + 4 * v59), si128), j) )
                    {
                      v59 = v57;
                      v57 += 4;
                    }
                    v60 = _mm_max_ps(_mm_shuffle_ps(j, j, 14), j);
                    v61 = fmax(_mm_shuffle_ps(v60, v60, 1).m128_f32[0], v60.m128_f32[0]);
                    if ( v61 > 8191.0 )
                      return 16386;
                    if ( v61 != 0.0 )
                    {
                      v62 = *(__int16 *)(v42 + 2LL * v48);
                      if ( v62 < 0 )
                      {
                        v79 = -v62;
                        if ( v79 >= 128 )
                        {
                          v81 = (float)v79 * -0.25;
                          goto LABEL_70;
                        }
                        v63 = 1.0 / *((float *)&ExponentTableFl + v79);
                      }
                      else
                      {
                        if ( v62 < 128 )
                        {
                          v63 = *((float *)&ExponentTableFl + *(__int16 *)(v42 + 2LL * v48));
                          goto LABEL_43;
                        }
                        v81 = (float)v62 * 0.25;
LABEL_70:
                        v63 = powf(2.0, v81);
                      }
LABEL_43:
                      if ( (int)v61 >= 1024 )
                      {
                        for ( k = 0; (int)k < v52; k = (unsigned int)(k + 1) )
                        {
                          v76 = (int)*(float *)(v56 + 4 * k);
                          if ( (int)((v76 - ((unsigned int)v76 >> 31)) ^ ((int)(v76 - ((unsigned int)v76 >> 31)) >> 31)) >= 1024 )
                          {
                            v93 = v63 * 16.0;
                            if ( v76 < 0 )
                            {
                              LODWORD(v93) = COERCE_UNSIGNED_INT(v63 * 16.0) ^ _xmm;
                              v76 = -v76;
                            }
                            v94 = *(float *)&dword_1800BC12C[(__int64)v76 >> 3];
                            v77 = (float)((float)((float)(*(float *)&dword_1800BC130[(__int64)v76 >> 3] - v94)
                                                * *((float *)&InverseQuantInterpolationTableFl + (v76 & 7)))
                                        + v94)
                                * v93;
                          }
                          else
                          {
                            v77 = v63 * *(float *)&dword_1800BC12C[v76];
                          }
                          *(float *)(v56 + 4 * k) = v77;
                        }
                      }
                      else
                      {
                        v64 = 0;
                        if ( v52 >= 5 )
                        {
                          do
                          {
                            v65 = v64;
                            v64 += 5;
                            v66 = (int)*(float *)(v56 + 4 * v65 + 4);
                            v67 = (int)*(float *)(v56 + 4 * v65 + 8);
                            *(float *)(v56 + 4 * v65) = v63 * *(float *)&dword_1800BC12C[*(float *)(v56 + 4 * v65)];
                            v68 = v63 * *(float *)&dword_1800BC12C[v66];
                            v69 = v67;
                            v70 = (int)*(float *)(v56 + 4 * v65 + 12);
                            *(float *)(v56 + 4 * v65 + 4) = v68;
                            v71 = v63 * *(float *)&dword_1800BC12C[v69];
                            v72 = v70;
                            v73 = (int)*(float *)(v56 + 4 * v65 + 16);
                            *(float *)(v56 + 4 * v65 + 8) = v71;
                            *(float *)(v56 + 4 * v65 + 12) = v63 * *(float *)&dword_1800BC12C[v72];
                            *(float *)(v56 + 4 * v65 + 16) = v63 * *(float *)&dword_1800BC12C[v73];
                          }
                          while ( v64 < v52 - 4 );
                        }
                        if ( v64 < v52 )
                        {
                          do
                          {
                            v74 = v64++;
                            *(float *)(v56 + 4 * v74) = v63 * *(float *)&dword_1800BC12C[*(float *)(v56 + 4 * v74)];
                          }
                          while ( v64 < v52 );
                          v38 = v189;
                        }
                      }
                      *(_BYTE *)(i + 16 * v44 + v38) = 0;
                    }
                    v43 = v199;
                    v41 = v178;
                    goto LABEL_51;
                  }
                  ++v44;
                }
                v34 = 0;
                v32 = v173;
                if ( (a7 & 2) != 0 )
                  CBlock_ApplyNoiseFl(
                    (struct CAacDecoderChannelInfo *)a2[v173],
                    a5,
                    (unsigned int *)(*(_QWORD *)(a3 + 8LL * v173) + 4108LL),
                    (unsigned __int8 *)v38);
                v35 = a2;
              }
              v36 = v195;
              ++v32;
            }
          }
          v22 = v184;
          v23 = a2;
          v21 = a3;
          continue;
        }
LABEL_79:
        v34 = 16386;
LABEL_80:
        v90 = started;
        v91 = v175;
        if ( started != -1 || v175 != -1 )
        {
          if ( !v34 )
            v34 = 16388;
          if ( started == -1 )
          {
            v92 = a11;
          }
          else
          {
LABEL_85:
            v92 = a11;
            transportDec_CrcEndReg(a11, v90);
          }
          if ( v91 != -1 )
            transportDec_CrcEndReg(v92, v91);
        }
        return v34;
      case 5:
        v124 = *(unsigned __int8 *)(*v23 + 1688LL);
        if ( (unsigned __int8)v124 <= *(_BYTE *)(*v19 + 1688LL) )
          v124 = *(unsigned __int8 *)(*v19 + 1688LL);
        *(_BYTE *)(*v23 + 1689LL) = v124;
        *(_BYTE *)(*v19 + 1689LL) = v124;
        if ( (v17 & 0x300) != 0 && !*(_BYTE *)(*(_QWORD *)(v23[v25] + 1704LL) + 1379LL) )
        {
          v145 = *v23;
          v146 = 0;
          v147 = *(unsigned __int8 *)(v145 + 1680);
          v148 = *(_QWORD *)(*(_QWORD *)a3 + 4768LL);
          if ( *(_BYTE *)(v145 + 1680) )
          {
            do
            {
              v149 = (unsigned __int64)v146++ << 7;
              *(_QWORD *)(v149 + v148 + 32) = 0;
              *(_QWORD *)(v149 + v148 + 1056) = 0;
              *(_QWORD *)(v149 + v148 + 40) = 0;
              *(_QWORD *)(v149 + v148 + 1064) = 0;
              *(_QWORD *)(v149 + v148 + 48) = 0;
              *(_QWORD *)(v149 + v148 + 1072) = 0;
              *(_QWORD *)(v149 + v148 + 56) = 0;
              *(_QWORD *)(v149 + v148 + 1080) = 0;
              *(_QWORD *)(v149 + v148 + 64) = 0;
              *(_QWORD *)(v149 + v148 + 1088) = 0;
              *(_QWORD *)(v149 + v148 + 72) = 0;
              *(_QWORD *)(v149 + v148 + 1096) = 0;
              *(_QWORD *)(v149 + v148 + 80) = 0;
              *(_QWORD *)(v149 + v148 + 1104) = 0;
              *(_QWORD *)(v149 + v148 + 88) = 0;
              *(_QWORD *)(v149 + v148 + 1112) = 0;
              *(_QWORD *)(v149 + v148 + 96) = 0;
              *(_QWORD *)(v149 + v148 + 1120) = 0;
              *(_QWORD *)(v149 + v148 + 104) = 0;
              *(_QWORD *)(v149 + v148 + 1128) = 0;
              *(_QWORD *)(v149 + v148 + 112) = 0;
              *(_QWORD *)(v149 + v148 + 1136) = 0;
              *(_QWORD *)(v149 + v148 + 120) = 0;
              *(_QWORD *)(v149 + v148 + 1144) = 0;
              *(_QWORD *)(v149 + v148 + 128) = 0;
              *(_QWORD *)(v149 + v148 + 1152) = 0;
              *(_QWORD *)(v149 + v148 + 136) = 0;
              *(_QWORD *)(v149 + v148 + 1160) = 0;
              *(_QWORD *)(v149 + v148 + 144) = 0;
              *(_QWORD *)(v149 + v148 + 1168) = 0;
              *(_QWORD *)(v149 + v148 + 152) = 0;
              *(_QWORD *)(v149 + v148 + 1176) = 0;
            }
            while ( (int)v146 < v147 );
          }
          v21 = a3;
          v23 = a2;
        }
        v125 = *v23;
        v126 = *(_DWORD *)(*v23 + 1684LL);
        v199 = *(unsigned __int8 *)(*v23 + 1691LL);
        if ( (_DWORD)v22 && v125 )
        {
          v127 = *(struct CCplxPredictionData **)(*(_QWORD *)(v125 + 1720) + 8LL);
          v126 = *(_DWORD *)(v125 + 1684);
        }
        else
        {
          v127 = 0;
          if ( !(_DWORD)v22 )
            goto LABEL_160;
        }
        if ( !v21 )
        {
LABEL_160:
          v128 = 0;
          goto LABEL_161;
        }
        v128 = *(struct CJointStereoPersistentData **)(*(_QWORD *)v21 + 4768LL);
        v126 = *(_DWORD *)(v125 + 1684);
LABEL_161:
        if ( (unsigned int)CJointStereo_Read(
                             (struct CDK_BITSTREAM *)a1,
                             (struct CJointStereoData *)(*(_QWORD *)(v125 + 1712) + 4976LL),
                             *(unsigned __int8 *)(v125 + 1680),
                             v124,
                             v168,
                             v128,
                             v127,
                             v22,
                             v199,
                             v126,
                             v17) )
          goto LABEL_79;
        goto LABEL_23;
      case 6:
        if ( !(unsigned int)CDKreadBit(a1) )
          goto LABEL_23;
        v34 = 16391;
        goto LABEL_80;
      case 8:
        SectionData = CBlock_ReadSectionData(a1, v23[v25], a5, v17);
        v170 = SectionData;
        goto LABEL_21;
      case 9:
        goto LABEL_19;
      case 10:
        v98 = v23[v25];
        v191 = v98;
        v180 = *(_QWORD *)a5;
        v99 = *(_BYTE **)(v98 + 1704);
        LOBYTE(v199) = *(_BYTE *)(v98 + 1688);
        v186 = v99;
        v99[1382] = 0;
        v100 = a1[1];
        if ( v100 )
        {
          v101 = v100 - 1;
          v102 = (*a1 >> v101) & 1;
        }
        else
        {
          v153 = CDK_get32(a1 + 2, v98, v21);
          v98 = v191;
          v101 = 31;
          *a1 = v153;
          v102 = v153 >> 31;
        }
        a1[1] = v101;
        v186[1382] = v102;
        if ( !(_BYTE)v102 )
          goto LABEL_23;
        if ( *(_DWORD *)(v98 + 1684) == 2 )
          goto LABEL_116;
        v186[1383] = CDKreadBits(a1, 2);
        v103 = CDKreadBits(a1, 6);
        v186[1384] = v103;
        if ( v103 >= (unsigned __int8)v199 )
          goto LABEL_116;
        v104 = 0;
        v105 = *(__int16 *)(v180 + 2LL * v103);
        do
        {
          v106 = v104;
          v186[v104 + 1385] = CDKreadBits(a1, 5);
          v186[v104++ + 1389] = CDKreadBits(a1, 4);
          v105 += (unsigned __int8)v186[v106 + 1385];
        }
        while ( v104 <= (unsigned __int8)v186[1383] );
        v11 = a9;
        v17 = a6;
        v199 = v105;
        v15 = v179;
        if ( v199 >= (__int16)a8 )
        {
LABEL_116:
          v34 = 16388;
          goto LABEL_80;
        }
        v25 = v172;
        goto LABEL_23;
      case 11:
        v85 = a1[1];
        v86 = v25;
        v190 = *(_QWORD *)(v23[v25] + 1704LL);
        if ( v85 )
        {
          v87 = v85 - 1;
          v88 = (*a1 >> v87) & 1;
        }
        else
        {
          v138 = CDK_get32(a1 + 2, v25, v21);
          v23 = a2;
          v87 = 31;
          *a1 = v138;
          v88 = v138 >> 31;
          v86 = v25;
        }
        v89 = (a7 & 0x2000) == 0;
        a1[1] = v87;
        *(_BYTE *)(v190 + 1376) = v88;
        if ( v89 || !*(_BYTE *)(*(_QWORD *)(v23[v86] + 1704LL) + 1376LL) )
          goto LABEL_23;
        goto LABEL_79;
      case 12:
        SectionData = CTns_Read(a1, *(_QWORD *)(v23[v25] + 1704LL) + 768LL, v23[v25] + 1672LL, v17);
        v170 = SectionData;
        goto LABEL_21;
      case 13:
        if ( !(unsigned int)CDKreadBit(a1) )
          goto LABEL_23;
        v34 = 16394;
        goto LABEL_80;
      case 15:
        if ( (v17 & 4) != 0 )
          CHcr_Read(a1, v23[v25], v11 == 2, v22);
        goto LABEL_23;
      case 16:
        if ( (v17 & 2) != 0 )
          CRvlc_Decode(
            (struct CAacDecoderChannelInfo *)v23[v25],
            *(struct CAacDecoderStaticChannelInfo **)(a3 + 8LL * v25),
            (struct CDK_BITSTREAM *)a1);
        goto LABEL_23;
      case 17:
        SectionData = CBlock_ReadSpectralDataFl(a1, v23[v25], a5, v17);
        v170 = SectionData;
        v29 = a2[v25];
        if ( (v17 & 0x10) != 0 )
        {
          *(_DWORD *)(v29 + 1700) = 2;
        }
        else if ( (v17 & 0x400) != 0 )
        {
          *(_DWORD *)(v29 + 1700) = 4;
        }
        else
        {
          *(_DWORD *)(v29 + 1700) = 1;
        }
        goto LABEL_21;
      case 18:
        CChannel_CodebookTableInit((struct CAacDecoderChannelInfo *)v23[v25]);
        v23 = a2;
LABEL_19:
        v30 = (struct CAacDecoderChannelInfo *)v23[v25];
        if ( (v17 & 2) == 0 )
        {
          SectionData = CBlock_ReadScaleFactorData(v30, a1, v17, v22);
          v170 = SectionData;
          goto LABEL_21;
        }
        CRvlc_Read(v30, (struct CDK_BITSTREAM *)a1);
        goto LABEL_23;
      case 19:
        v15 = CDKreadBit(a1);
        v179 = v15;
        *(_BYTE *)(a2[v25] + 544LL) = v15;
        if ( v25 == 1 && *(_BYTE *)(*a2 + 544LL) != *(_BYTE *)(a2[1] + 544LL) )
        {
          _mm_lfence();
          *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1379LL) = 0;
          *(_BYTE *)(*(_QWORD *)(a2[1] + 1704LL) + 1379LL) = 0;
        }
        goto LABEL_23;
      case 20:
      case 22:
        goto LABEL_23;
      case 21:
        v168 = v17;
        SectionData = CLpdChannelStream_Read(a1, v23[v25], *(_QWORD *)(v21 + 8LL * v25), a5);
        v170 = SectionData;
        *(_DWORD *)(a2[v25] + 1700LL) = 3;
        goto LABEL_228;
      case 23:
        if ( (a7 & 2) != 0 )
          *(_BYTE *)(*(_QWORD *)(a2[v25] + 1704LL) + 1382LL) = CDKreadBits_2(a1, 8);
        goto LABEL_23;
      case 24:
        v168 = a8;
        SectionData = CBlock_ReadAcSpectralData(a1, v23[v25], *(_QWORD *)(v21 + 8LL * v25), a5);
        v170 = SectionData;
        *(_DWORD *)(a2[v25] + 1700LL) = 1;
LABEL_228:
        v25 = v172;
        goto LABEL_21;
      case 25:
        v141 = CDKreadBit(a1);
        *(_QWORD *)(a2[v25] + 512LL) = a2[v25];
        if ( v141 )
        {
          if ( (a7 & 0x2000) != 0 )
            goto LABEL_79;
          v142 = *(_QWORD *)(a3 + 8LL * v25);
          if ( *(_DWORD *)(v142 + 1828) != 2 || *(_BYTE *)(v142 + 1832) )
          {
            *(_DWORD *)(a2[v25] + 548LL) = 2;
            *(_BYTE *)(a2[v25] + 552LL) = 0;
          }
          v143 = a2[v25];
          v144 = *(_DWORD *)(v143 + 1692);
          if ( *(_DWORD *)(v143 + 1684) == 2 )
            v144 = *(_DWORD *)(v143 + 1692) / 2;
          CLpd_FAC_Read((struct CDK_BITSTREAM *)a1, *(float **)(v143 + 512), v144, 1, v168);
        }
        else
        {
          v152 = *(_QWORD *)(a3 + 8LL * v25);
          if ( *(_DWORD *)(v152 + 1828) == 2 && !*(_BYTE *)(v152 + 1832) )
            memset_0((void *)a2[v25], 0, 0x200u);
        }
        goto LABEL_23;
      case 26:
        *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1383LL) = CDKreadBit(a1);
        goto LABEL_23;
      case 27:
        v139 = *v23;
        v140 = *(_QWORD *)(*v23 + 1704LL);
        if ( *(_BYTE *)(v140 + 1383) )
        {
          v150 = *(unsigned __int8 *)(v140 + 1379);
          v151 = (struct CTnsData *)(*(_QWORD *)(v23[1] + 1704LL) + 768LL);
          LOBYTE(v199) = 0;
          CTns_ReadDataPresentUsac(
            (struct CDK_BITSTREAM *)a1,
            (struct CTnsData *)(v140 + 768),
            v151,
            (unsigned __int8 *)&v199,
            (const struct CIcsInfo *)(v139 + 1672),
            v17,
            v169,
            v150);
          *(_BYTE *)(*(_QWORD *)(*a2 + 1704LL) + 1384LL) = v199;
        }
        else
        {
          *(_BYTE *)(v140 + 1384) = 1;
        }
        goto LABEL_23;
      case 28:
        if ( (unsigned int)CDKreadBit(a1) )
          goto LABEL_23;
        SectionData = IcsReadMaxSfb(a1, *v19 + 1672LL, a5);
        v170 = SectionData;
        goto LABEL_21;
      case 29:
        v177 = CDKreadBit(a1);
        v160 = CDKreadBits_2(a1, 3) + 1;
        v199 = 0;
        if ( v160 > 0 )
        {
          v161 = v183;
          v162 = v160;
          v163 = v199;
          do
          {
            ++v161;
            v164 = CDKreadBit(a1);
            CDKreadBits_2(a1, 4);
            if ( v164 )
            {
              v165 = CDKreadBit(a1);
              v166 = CDKreadBit(a1);
              if ( v165 )
              {
                if ( v166 )
                  ++v161;
              }
            }
            ++v163;
          }
          while ( v163 < v162 );
          v17 = a6;
          v25 = v172;
          v15 = v179;
          v183 = v161;
          v11 = a9;
        }
        CDKreadBit(a1);
        CDKreadBit(a1);
        CDKreadBits_2(a1, 2);
        goto LABEL_23;
      case 30:
        v188 = 1;
        v193 = *(_QWORD *)(v23[v25] + 1704LL);
        if ( v183 > 1 )
        {
          v154 = v177;
          v155 = a2;
          v156 = v25;
          do
          {
            if ( v154 || (unsigned int)CDKreadBit(a1) )
            {
              CBlock_DecodeHuffmanWord((struct CDK_BITSTREAM *)a1, (const struct CodeBookDescription *)&off_180098870);
            }
            else
            {
              v157 = v155[v156];
              v158 = 0;
              v182 = 0;
              if ( *(_BYTE *)(v157 + 1680) )
              {
                do
                {
                  v159 = 0;
                  v199 = 0;
                  if ( *(_BYTE *)(v157 + 1688) )
                  {
                    do
                    {
                      if ( *(_BYTE *)(v159 + v193 + 512) )
                      {
                        CBlock_DecodeHuffmanWord(
                          (struct CDK_BITSTREAM *)a1,
                          (const struct CodeBookDescription *)&off_180098870);
                        v159 = v199;
                      }
                      v157 = a2[v25];
                      v199 = ++v159;
                    }
                    while ( v159 < *(unsigned __int8 *)(v157 + 1688) );
                    v158 = v182;
                  }
                  v182 = ++v158;
                }
                while ( v158 < *(unsigned __int8 *)(v157 + 1680) );
                v154 = v177;
                v155 = a2;
                v156 = v25;
              }
            }
            ++v188;
          }
          while ( v188 < v183 );
          v11 = a9;
          v17 = a6;
          v18 = v194;
          v15 = v179;
        }
        goto LABEL_23;
      case 31:
        if ( a11 )
        {
          if ( *(_DWORD *)a11 == 2 )
          {
            if ( *((_BYTE *)a11 + 194) )
              started = 0;
            else
              started = CDKcrcStartReg(
                          (struct TRANSPORTDEC *)((char *)a11 + 216),
                          (struct TRANSPORTDEC *)((char *)a11 + 136),
                          192);
          }
          else
          {
            started = -1;
          }
        }
        goto LABEL_23;
      case 32:
        if ( a11 )
        {
          if ( *(_DWORD *)a11 == 2 )
          {
            if ( *((_BYTE *)a11 + 194) )
              v175 = 0;
            else
              v175 = CDKcrcStartReg(
                       (struct TRANSPORTDEC *)((char *)a11 + 216),
                       (struct TRANSPORTDEC *)((char *)a11 + 136),
                       128);
          }
          else
          {
            v175 = -1;
          }
        }
        goto LABEL_23;
      case 33:
      case 36:
        if ( a11 )
        {
          if ( *(_DWORD *)a11 == 2 )
            adtsRead_CrcEndReg(
              (struct TRANSPORTDEC *)((char *)a11 + 192),
              (struct TRANSPORTDEC *)((char *)a11 + 136),
              started);
          started = -1;
        }
        goto LABEL_23;
      case 34:
        v90 = started;
        if ( started != -1 )
        {
          v91 = v175;
          v34 = 16388;
          goto LABEL_85;
        }
        if ( a11 )
        {
          if ( *(_DWORD *)a11 == 2 )
            adtsRead_CrcEndReg(
              (struct TRANSPORTDEC *)((char *)a11 + 192),
              (struct TRANSPORTDEC *)((char *)a11 + 136),
              v175);
          v175 = -1;
        }
        goto LABEL_23;
      case 35:
        if ( a11 )
          started = transportDec_CrcStartReg(a11, 0);
        goto LABEL_23;
      case 37:
        v25 = (v25 + 1) % v11;
        v172 = v25;
        goto LABEL_23;
      case 39:
        v176 = (__int64 (**)[2])v176[v15 + 1];
        v26 = -1;
        goto LABEL_23;
      default:
        v34 = 8195;
        goto LABEL_80;
    }
  }
}

```

## disassembly

```asm
0x180014ae0  mov     rax, rsp
0x180014ae3  mov     [rax+18h], r8
0x180014ae7  mov     [rax+10h], rdx
0x180014aeb  mov     [rax+8], rcx
0x180014aef  push    rbx
0x180014af0  push    rbp
0x180014af1  push    rsi
0x180014af2  push    rdi
0x180014af3  push    r12
0x180014af5  push    r13
0x180014af7  push    r14
0x180014af9  push    r15
0x180014afb  sub     rsp, 118h
0x180014b02  movzx   ebp, [rsp+158h+arg_40]
0x180014b0a  mov     rdi, rdx
0x180014b0d  mov     edx, dword ptr [rsp+158h+arg_30]
0x180014b14  mov     esi, r9d
0x180014b17  movaps  xmmword ptr [rax-58h], xmm6
0x180014b1b  lea     r8, __ImageBase
0x180014b22  movaps  xmmword ptr [rax-68h], xmm7
0x180014b26  movaps  xmmword ptr [rax-78h], xmm8
0x180014b2b  movaps  xmmword ptr [rax-88h], xmm9
0x180014b33  movaps  xmmword ptr [rax-98h], xmm10
0x180014b3b  movaps  xmmword ptr [rax-0A8h], xmm11
0x180014b43  cmp     r9d, 1Dh
0x180014b47  jnz     loc_180015497
0x180014b4d  test    dl, 1; jumptable 0000000180016525 cases 2,5
0x180014b50  jnz     loc_1800165DC
0x180014b56  lea     r15, off_180098780
0x180014b5d  cmp     bpl, 1
0x180014b61  jz      short loc_180014B6A
0x180014b63  lea     r15, off_180098798
0x180014b6a  mov     rax, [rdi]
0x180014b6d  xor     r13d, r13d
0x180014b70  xor     edx, edx; Val
0x180014b72  mov     [rsp+158h+var_E0], r15
0x180014b77  mov     r8d, 258h; Size
0x180014b7d  mov     [rsp+158h+var_EC], 0FFFFFFFFh
0x180014b85  mov     [rsp+158h+var_E8], 0FFFFFFFFh
0x180014b8d  mov     rbx, [rax+6A8h]
0x180014b94  mov     dword ptr [rsp+158h+var_F8], r13d
0x180014b99  mov     [rsp+158h+var_D8], r13d
0x180014ba1  mov     [rsp+158h+var_C8], r13d
0x180014ba9  lea     rcx, [rbx+300h]; void *
0x180014bb0  call    memset_0
0x180014bb5  mov     r14d, [rsp+158h+arg_28]
0x180014bbd  xor     eax, eax
0x180014bbf  mov     [rbx+558h], rax
0x180014bc6  mov     r12d, r14d
0x180014bc9  mov     [rbx+560h], ax
0x180014bd0  and     r12d, 4300h
0x180014bd7  mov     rax, [rdi]
0x180014bda  mov     [rsp+158h+var_B0], r12d
0x180014be2  mov     rcx, [rax+6A8h]
0x180014be9  mov     [rcx+563h], r13b
0x180014bf0  jnz     loc_1800165E8
0x180014bf6  add     rdi, 8
0x180014bfa  cmp     bpl, 2
0x180014bfe  jnz     short loc_180014C3F
0x180014c00  mov     rax, [rdi]
0x180014c03  xor     edx, edx; Val
0x180014c05  mov     r8d, 258h; Size
0x180014c0b  mov     rbx, [rax+6A8h]
0x180014c12  lea     rcx, [rbx+300h]; void *
0x180014c19  call    memset_0
0x180014c1e  xor     eax, eax
0x180014c20  mov     [rbx+558h], rax
0x180014c27  mov     [rbx+560h], ax
0x180014c2e  mov     rax, [rdi]
0x180014c31  mov     rcx, [rax+6A8h]
0x180014c38  mov     [rcx+563h], r13b
0x180014c3f  mov     r8, [rsp+158h+arg_10]
0x180014c47  mov     r9d, r13d
0x180014c4a  mov     r11, [rsp+158h+arg_8]
0x180014c52  mov     [rsp+158h+var_C4], r13d
0x180014c5a  test    r8, r8
0x180014c5d  jnz     loc_18001587C
0x180014c63  test    r14b, 18h
0x180014c67  jnz     loc_180016619
0x180014c6d  cmp     esi, 100h
0x180014c73  jz      loc_18001660F
0x180014c79  mov     rcx, [r15]
0x180014c7c  mov     ebx, r13d
0x180014c7f  mov     r15, [rsp+158h+arg_0]
0x180014c87  mov     esi, r13d
0x180014c8a  mov     [rsp+158h+var_F0], ebx
0x180014c8e  mov     [rsp+158h+var_D4], r13d
0x180014c96  movsxd  rax, esi
0x180014c99  mov     r10d, 6
0x180014c9f  movsxd  rcx, dword ptr [rcx+rax*4]
0x180014ca3  cmp     ecx, 0Eh
0x180014ca6  jz      loc_180014D65; jumptable 0000000180014CC6 cases 20,22
0x180014cac  cmp     ecx, 27h; switch 40 cases
0x180014caf  ja      def_180014CC6; jumptable 0000000180014CC6 default case, cases 4,7,14,38
0x180014cb5  lea     rdx, __ImageBase
0x180014cbc  mov     ecx, ds:(jpt_180014CC6 - 180000000h)[rdx+rcx*4]
0x180014cc3  add     rcx, rdx
0x180014cc6  jmp     rcx; switch jump
0x180014ccc  mov     r8, [rsp+158h+arg_20]; jumptable 0000000180014CC6 case 17
0x180014cd4  mov     r9d, r14d
0x180014cd7  movsxd  rax, ebx
0x180014cda  mov     rcx, r15
0x180014cdd  mov     rdx, [r11+rax*8]
0x180014ce1  call    ?CBlock_ReadSpectralDataFl@@YA?AW4AAC_DECODER_ERROR@@PEAUCDK_BITSTREAM@@PEAUCAacDecoderChannelInfo@@PEBUSamplingRateInfo@@I@Z; CBlock_ReadSpectralDataFl(CDK_BITSTREAM *,CAacDecoderChannelInfo *,SamplingRateInfo const *,uint)
0x180014ce6  mov     rdx, [rsp+158h+arg_8]
0x180014cee  mov     r13d, eax
0x180014cf1  mov     dword ptr [rsp+158h+var_F8], eax
0x180014cf5  movsxd  rax, ebx
0x180014cf8  mov     rax, [rdx+rax*8]
0x180014cfc  test    r14b, 10h
0x180014d00  jnz     loc_18001592E
0x180014d06  bt      r14d, 0Ah
0x180014d0b  jb      loc_180015FF7
0x180014d11  mov     dword ptr [rax+6A4h], 1
0x180014d1b  jmp     short loc_180014D54
0x180014d1d  movsxd  rcx, ebx; jumptable 0000000180014CC6 case 18
0x180014d20  mov     rcx, [r11+rcx*8]; struct CAacDecoderChannelInfo *
0x180014d24  call    ?CChannel_CodebookTableInit@@YAXPEAUCAacDecoderChannelInfo@@@Z; CChannel_CodebookTableInit(CAacDecoderChannelInfo *)
0x180014d29  mov     r11, [rsp+158h+arg_8]
0x180014d31  movsxd  rax, ebx; jumptable 0000000180014CC6 case 9
0x180014d34  mov     rdx, r15; struct CDK_BITSTREAM *
0x180014d37  mov     rcx, [r11+rax*8]; struct CAacDecoderChannelInfo *
0x180014d3b  test    r14b, 2
0x180014d3f  jnz     loc_180015C97
0x180014d45  mov     r8d, r14d
0x180014d48  call    ?CBlock_ReadScaleFactorData@@YA?AW4AAC_DECODER_ERROR@@PEAUCAacDecoderChannelInfo@@PEAUCDK_BITSTREAM@@I@Z; CBlock_ReadScaleFactorData(CAacDecoderChannelInfo *,CDK_BITSTREAM *,uint)
0x180014d4d  mov     r13d, eax
0x180014d50  mov     dword ptr [rsp+158h+var_F8], eax
0x180014d54  test    r13d, r13d
0x180014d57  jnz     loc_180016724
0x180014d5d  mov     r13d, [rsp+158h+var_D4]
0x180014d65  mov     rax, [rsp+158h+var_E0]; jumptable 0000000180014CC6 cases 20,22
0x180014d6a  inc     esi
0x180014d6c  mov     rcx, [rax]
0x180014d6f  movsxd  rax, esi
0x180014d72  cmp     dword ptr [rcx+rax*4], 28h ; '('
0x180014d76  jnz     loc_180015188
0x180014d7c  movdqa  xmm7, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180014d84  xor     edi, edi
0x180014d86  movdqa  xmm10, cs:__xmm@01010101010101010101010101010101
0x180014d8f  xorps   xmm8, xmm8
0x180014d93  movss   xmm9, cs:__real@45fff800
0x180014d9c  movss   xmm11, cs:__real@41800000
0x180014da5  mov     ebx, dword ptr [rsp+158h+var_F8]
0x180014da9  mov     r10, [rsp+158h+arg_8]
0x180014db1  movzx   eax, bpl
0x180014db5  mov     [rsp+158h+var_B0], eax
0x180014dbc  mov     [rsp+158h+var_F0], edi
0x180014dc0  cmp     edi, eax
0x180014dc2  jge     loc_18001531C
0x180014dc8  movsxd  r14, edi
0x180014dcb  mov     rcx, [r10+r14*8]
0x180014dcf  mov     eax, [rcx+6A4h]
0x180014dd5  dec     eax
0x180014dd7  cmp     eax, 1
0x180014dda  ja      loc_18001517A
0x180014de0  mov     r13, [rcx+6A8h]
0x180014de7  add     r13, 280h
0x180014dee  mov     [rsp+158h+var_B8], r13
0x180014df6  movups  xmmword ptr [r13+0], xmm10
0x180014dfb  movups  xmmword ptr [r13+10h], xmm10
0x180014e00  movups  xmmword ptr [r13+20h], xmm10
0x180014e05  movups  xmmword ptr [r13+30h], xmm10
0x180014e0a  movups  xmmword ptr [r13+40h], xmm10
0x180014e0f  movups  xmmword ptr [r13+50h], xmm10
0x180014e14  movups  xmmword ptr [r13+60h], xmm10
0x180014e19  movups  xmmword ptr [r13+70h], xmm10
0x180014e1e  mov     r14, [r10+r14*8]
0x180014e22  mov     r10, [rsp+158h+arg_20]
0x180014e2a  mov     rcx, r10
0x180014e2d  cmp     dword ptr [r14+694h], 2
0x180014e35  movzx   edx, byte ptr [r14+698h]
0x180014e3d  lea     rax, [r10+8]
0x180014e41  mov     r15, [r14+6A8h]
0x180014e48  cmovz   rcx, rax
0x180014e4c  movzx   eax, byte ptr [r14+69Bh]
0x180014e54  xor     ebx, ebx
0x180014e56  mov     [rsp+158h+var_D8], edx
0x180014e5d  xor     ebp, ebp
0x180014e5f  mov     [rsp+158h+arg_40], al
0x180014e66  mov     r12, [rcx]
0x180014e69  mov     [rsp+158h+arg_18], ebx
0x180014e70  movzx   eax, byte ptr [r14+690h]
0x180014e78  cmp     ebp, eax
0x180014e7a  jge     loc_18001515E
0x180014e80  xor     edi, edi
0x180014e82  movsxd  rax, ebp
0x180014e85  mov     [rsp+158h+var_C4], edi
0x180014e8c  movzx   eax, byte ptr [rax+r14+688h]
0x180014e95  cmp     edi, eax
0x180014e97  jge     loc_180015157
0x180014e9d  xor     esi, esi
0x180014e9f  nop
0x180014ea0  cmp     esi, edx
0x180014ea2  jge     loc_1800150F8
0x180014ea8  mov     r9d, ebp
0x180014eab  shl     r9d, 4
0x180014eaf  add     r9d, esi
0x180014eb2  movsxd  rax, r9d
0x180014eb5  movzx   ecx, byte ptr [rax+r15+200h]
0x180014ebe  cmp     cl, 10h
0x180014ec1  jb      loc_180015092
0x180014ec7  mov     eax, ebx
0x180014ec9  movsxd  rdx, esi
0x180014ecc  imul    eax, [r14+69Ch]
0x180014ed4  movaps  xmm1, xmm7
0x180014ed7  movsx   r8, word ptr [r12+rdx*2]
0x180014edc  movsx   ebx, word ptr [r12+rdx*2+2]
0x180014ee2  movsxd  rcx, eax
0x180014ee5  sub     ebx, r8d
0x180014ee8  mov     rax, [r14+680h]
0x180014eef  add     rcx, r8
0x180014ef2  movups  xmm0, xmmword ptr [rax+rcx*4]
0x180014ef6  lea     rdi, [rax+rcx*4]
0x180014efa  mov     ecx, 4
0x180014eff  andps   xmm1, xmm0
0x180014f02  cmp     ebx, ecx
0x180014f04  jle     short loc_180014F1D
0x180014f06  movsxd  rax, ecx
0x180014f09  add     ecx, 4
0x180014f0c  movups  xmm0, xmmword ptr [rdi+rax*4]
0x180014f10  andps   xmm0, xmm7
0x180014f13  maxps   xmm0, xmm1
0x180014f16  movaps  xmm1, xmm0
0x180014f19  cmp     ecx, ebx
0x180014f1b  jl      short loc_180014F06
0x180014f1d  movaps  xmm0, xmm1
0x180014f20  shufps  xmm0, xmm1, 0Eh
0x180014f24  maxps   xmm0, xmm1
0x180014f27  movaps  xmm6, xmm0
0x180014f2a  shufps  xmm6, xmm0, 1
0x180014f2e  maxps   xmm6, xmm0
0x180014f31  comiss  xmm6, xmm9
0x180014f35  ja      loc_1800151CF
0x180014f3b  ucomiss xmm6, xmm8
0x180014f3f  jp      short loc_180014F47
0x180014f41  jz      loc_18001507D
0x180014f47  movsxd  rax, r9d
0x180014f4a  movsx   rcx, word ptr [r15+rax*2]
0x180014f4f  test    ecx, ecx
0x180014f51  js      loc_1800151A5
0x180014f57  cmp     ecx, 80h
0x180014f5d  jge     loc_18001522F
0x180014f63  mov     rax, rcx
0x180014f66  lea     rcx, __ImageBase
0x180014f6d  movss   xmm1, ds:rva ?ExponentTableFl@@3QBMB[rcx+rax*4]; float const near * const ExponentTableFl ...
0x180014f76  cvttss2si eax, xmm6
0x180014f7a  cmp     eax, 400h
0x180014f7f  jge     loc_18001509F
0x180014f85  xor     r8d, r8d
0x180014f88  cmp     ebx, 5
0x180014f8b  jl      loc_180015036
0x180014f91  lea     r9d, [rbx-4]
0x180014f95  lea     r10, __ImageBase
0x180014f9c  movsxd  rdx, r8d
0x180014f9f  movaps  xmm0, xmm1
0x180014fa2  add     r8d, 5
0x180014fa6  cvttss2si eax, dword ptr [rdi+rdx*4]
0x180014fab  movsxd  rcx, eax
0x180014fae  cvttss2si eax, dword ptr [rdi+rdx*4+4]
0x180014fb4  mulss   xmm0, ds:rva dword_1800BC12C[r10+rcx*4]
0x180014fbe  movsxd  rcx, eax
0x180014fc1  cvttss2si eax, dword ptr [rdi+rdx*4+8]
0x180014fc7  movss   dword ptr [rdi+rdx*4], xmm0
0x180014fcc  movaps  xmm0, xmm1
0x180014fcf  mulss   xmm0, ds:rva dword_1800BC12C[r10+rcx*4]
0x180014fd9  movsxd  rcx, eax
0x180014fdc  cvttss2si eax, dword ptr [rdi+rdx*4+0Ch]
0x180014fe2  movss   dword ptr [rdi+rdx*4+4], xmm0
0x180014fe8  movaps  xmm0, xmm1
0x180014feb  mulss   xmm0, ds:rva dword_1800BC12C[r10+rcx*4]
0x180014ff5  movsxd  rcx, eax
0x180014ff8  cvttss2si eax, dword ptr [rdi+rdx*4+10h]
0x180014ffe  movss   dword ptr [rdi+rdx*4+8], xmm0
0x180015004  movaps  xmm0, xmm1
0x180015007  mulss   xmm0, ds:rva dword_1800BC12C[r10+rcx*4]
0x180015011  movsxd  rcx, eax
0x180015014  movss   dword ptr [rdi+rdx*4+0Ch], xmm0
0x18001501a  movaps  xmm0, xmm1
0x18001501d  mulss   xmm0, ds:rva dword_1800BC12C[r10+rcx*4]
0x180015027  movss   dword ptr [rdi+rdx*4+10h], xmm0
0x18001502d  cmp     r8d, r9d
0x180015030  jl      loc_180014F9C
0x180015036  cmp     r8d, ebx
0x180015039  jge     short loc_18001506F
0x18001503b  lea     r13, __ImageBase
0x180015042  movsxd  rdx, r8d
0x180015045  movaps  xmm0, xmm1
0x180015048  inc     r8d
0x18001504b  cvttss2si eax, dword ptr [rdi+rdx*4]
0x180015050  movsxd  rcx, eax
0x180015053  mulss   xmm0, ds:rva dword_1800BC12C[r13+rcx*4]
0x18001505d  movss   dword ptr [rdi+rdx*4], xmm0
0x180015062  cmp     r8d, ebx
0x180015065  jl      short loc_180015042
0x180015067  mov     r13, [rsp+158h+var_B8]
0x18001506f  mov     eax, ebp
0x180015071  shl     eax, 4
0x180015074  add     eax, esi
0x180015076  cdqe
  ... truncated ...
```

# CBlock_ReadSpectralDataFl(CDK_BITSTREAM *,CAacDecoderChannelInfo *,SamplingRateInfo const *,uint)

- ea: `0x180016880`
- end: `0x180017539`
- name: `?CBlock_ReadSpectralDataFl@@YA?AW4AAC_DECODER_ERROR@@PEAUCDK_BITSTREAM@@PEAUCAacDecoderChannelInfo@@PEBUSamplingRateInfo@@I@Z`
- size: `3257`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014ae0`

## callees

- `0x180016880`
- `0x1800175b0`
- `0x180018214`
- `0x180018540`
- `0x18004dd14`
- `0x18007b844`
- `0x180089140`
- `0x18008949c`

## pseudocode

```c
__int64 __fastcall CBlock_ReadSpectralDataFl(unsigned int *a1, __int64 a2, __int16 **a3, char a4)
{
  char v4; // bl
  const struct SamplingRateInfo *v5; // rdi
  __int16 **v6; // rax
  __int64 v7; // r14
  unsigned int *v8; // rsi
  char *v9; // r13
  __int16 *v10; // rbp
  int v11; // r11d
  int v12; // ecx
  __int64 v13; // r10
  float v14; // xmm4_4
  __int64 v15; // r12
  int v16; // r15d
  int v17; // edi
  __int64 v18; // r8
  int v19; // edx
  int v20; // r9d
  int v21; // ebx
  unsigned __int8 v22; // r14
  __int64 v23; // r12
  char *v24; // r13
  int v25; // eax
  __int64 v26; // rcx
  unsigned int v27; // r9d
  __int64 i; // rdi
  unsigned int v29; // r8d
  unsigned int v30; // edx
  unsigned int v31; // edx
  __int64 v32; // rbx
  char v33; // r10
  unsigned int v34; // ecx
  unsigned __int8 v35; // r11
  __int64 v36; // r9
  __int64 v37; // rbp
  __int64 v38; // r14
  __int64 v39; // r15
  __int64 v40; // r8
  __int64 v41; // rdx
  unsigned int v42; // edi
  int v43; // r12d
  int v44; // r14d
  int v45; // ebp
  int v46; // edi
  int v47; // r10d
  int v48; // ebx
  int v49; // eax
  int v50; // ebp
  _BYTE *v51; // rdx
  unsigned int v53; // eax
  int v54; // ecx
  int v55; // eax
  int v56; // ebp
  int v57; // eax
  __int64 v58; // rdi
  int v59; // r15d
  unsigned int v60; // r9d
  __int64 j; // r8
  unsigned int v62; // r10d
  unsigned int v63; // edx
  __int64 v64; // rbx
  int v65; // r11d
  unsigned int v66; // ecx
  unsigned __int8 v67; // r12
  __int64 v68; // r9
  __int64 v69; // rdi
  __int64 v70; // rbp
  __int64 v71; // r14
  unsigned int v72; // edx
  int v73; // r9d
  unsigned int v74; // r10d
  unsigned int v75; // r8d
  __int64 v76; // rdx
  __int64 v77; // r8
  int v78; // eax
  unsigned int v79; // eax
  int v80; // r13d
  struct CErHcrInfo *v81; // rbx
  const struct SamplingRateInfo *v82; // r8
  float v83; // xmm0_4
  char *v84; // rax
  _DWORD *v85; // r13
  float v86; // xmm0_4
  int v87; // edi
  unsigned int v88; // r10d
  int v89; // r10d
  int v90; // eax
  int v91; // r14d
  int v92; // ecx
  unsigned int v93; // ecx
  unsigned int v94; // edx
  __int64 v95; // rbp
  char v96; // r11
  __int64 v97; // r9
  __int64 v98; // r8
  __int64 v99; // r15
  __int64 v100; // r12
  int v101; // edx
  int v102; // r10d
  unsigned int v103; // eax
  __m128i v104; // xmm1
  int v105; // edi
  unsigned int v106; // eax
  int v107; // r11d
  int v108; // ebp
  int v109; // ecx
  unsigned int v110; // ecx
  unsigned int v111; // edx
  int v112; // r9d
  unsigned int v113; // r8d
  __int64 v114; // r8
  __int64 v115; // r14
  __int64 v116; // r15
  __int64 v117; // r12
  __int64 v118; // r10
  unsigned int v119; // edx
  int v120; // r8d
  int v121; // r11d
  unsigned int v122; // r8d
  int v123; // eax
  unsigned int v124; // eax
  unsigned int v125; // eax
  __int64 v126; // r13
  float v127; // xmm1_4
  float v128; // xmm1_4
  int v129; // r8d
  int v130; // r9d
  float v131; // xmm1_4
  float v132; // xmm0_4
  float v133; // xmm0_4
  char v134; // [rsp+20h] [rbp-D8h]
  int v135; // [rsp+24h] [rbp-D4h]
  int v136; // [rsp+28h] [rbp-D0h]
  int v137; // [rsp+28h] [rbp-D0h]
  int v138; // [rsp+2Ch] [rbp-CCh]
  int v139; // [rsp+30h] [rbp-C8h]
  char *v140; // [rsp+38h] [rbp-C0h]
  int v141; // [rsp+44h] [rbp-B4h]
  int v142; // [rsp+48h] [rbp-B0h]
  int v143; // [rsp+4Ch] [rbp-ACh]
  int v144; // [rsp+50h] [rbp-A8h]
  char v145; // [rsp+54h] [rbp-A4h]
  int v146; // [rsp+58h] [rbp-A0h]
  int v147; // [rsp+5Ch] [rbp-9Ch]
  int v148; // [rsp+60h] [rbp-98h]
  int v149; // [rsp+64h] [rbp-94h]
  __int64 v150; // [rsp+68h] [rbp-90h]
  __int64 v151; // [rsp+70h] [rbp-88h]
  char *v152; // [rsp+78h] [rbp-80h]
  int v153; // [rsp+80h] [rbp-78h]
  int v154; // [rsp+84h] [rbp-74h]
  __int64 v155; // [rsp+88h] [rbp-70h]
  __int64 v156; // [rsp+88h] [rbp-70h]
  __int16 *v157; // [rsp+90h] [rbp-68h]

  v4 = a4;
  v5 = (const struct SamplingRateInfo *)a3;
  v6 = a3;
  v7 = a2;
  v8 = a1;
  if ( *(_DWORD *)(a2 + 1684) == 2 )
    v6 = a3 + 1;
  v9 = *(char **)(a2 + 1664);
  v10 = *v6;
  v157 = *v6;
  v152 = v9;
  memset_0(v9, 0, 0x1000u);
  if ( (v4 & 4) != 0 )
  {
    if ( *(_WORD *)(*(_QWORD *)(v7 + 1704) + 2162LL) )
    {
      v81 = (struct CErHcrInfo *)(*(_QWORD *)(v7 + 1712) + 5048LL);
      if ( HcrInit(v81, (struct CAacDecoderChannelInfo *)v7, v5, (struct CDK_BITSTREAM *)v8) )
        return 16388;
      if ( HcrDecoder(v81, (struct CAacDecoderChannelInfo *)v7, v82, (struct CDK_BITSTREAM *)v8) )
        HcrMuteErroneousLines(v81);
      CDKpushFor_3(v8, (unsigned int)*(__int16 *)(*(_QWORD *)(v7 + 1704) + 2162LL));
LABEL_37:
      v4 = a4;
    }
  }
  else
  {
    v154 = *(unsigned __int8 *)(v7 + 1680);
    if ( *(_BYTE *)(v7 + 1680) )
    {
      v11 = 0;
      v12 = *(unsigned __int8 *)(v7 + 1688);
      v13 = *(_QWORD *)(v7 + 1704) + 512LL;
      v14 = FLOAT_8192_0;
      v15 = 0;
      v16 = *(_DWORD *)(v7 + 1692);
      v149 = 0;
      v151 = v13;
      v153 = v12;
      v148 = v16;
      v143 = 0;
      while ( 1 )
      {
        v17 = *(unsigned __int8 *)(v15 + v7 + 1672);
        v18 = 0;
        v19 = *v10;
        v20 = 16 * v15;
        v139 = v17;
        v142 = 16 * v15;
        v141 = 0;
        if ( !v12 )
          goto LABEL_35;
        do
        {
          v21 = v19;
          v147 = v19;
          v19 = v10[v18 + 1];
          v146 = v19;
          v22 = *(_BYTE *)(v20 + v13);
          v134 = v22;
          if ( v22 >= 0x10u )
          {
            if ( v22 <= 0x1Fu )
            {
              v22 = 11;
              v134 = 11;
              *(_BYTE *)(v20 + v13) = 11;
            }
          }
          else if ( (unsigned __int8)(v22 - 1) > 0xBu )
          {
            goto LABEL_33;
          }
          v23 = *((_QWORD *)&AACcodeBookDescriptionTable + 2 * v22);
          v138 = (unsigned __int8)byte_1800987B8[16 * v22];
          v144 = (unsigned __int8)byte_1800987BA[16 * v22];
          v145 = byte_1800987B9[16 * v22];
          v150 = v23;
          v24 = &v9[4 * v143 * v16];
          v140 = v24;
          if ( !byte_1800987BA[16 * v22] )
          {
            v25 = 0;
            v136 = 0;
            if ( !v17 )
              goto LABEL_32;
            v26 = 4LL * v16;
            v155 = v26;
            while ( 1 )
            {
              v135 = v21;
              if ( v21 >= v19 )
                goto LABEL_30;
              do
              {
                v27 = *v8;
                for ( i = 0; ; i = v42 >> 2 )
                {
                  v29 = v8[1];
                  if ( (int)(2 - v29) <= 0 )
                  {
                    v35 = 0;
                  }
                  else
                  {
                    v30 = v8[5];
                    v8[2] -= 32;
                    v31 = v30 + 32;
                    v32 = *((_QWORD *)v8 + 3);
                    v33 = v31 & 7;
                    v34 = v8[9];
                    v35 = v27 << (2 - v29);
                    v36 = (v31 - 1) >> 3;
                    v8[5] = v31 & (v34 - 1);
                    v37 = (unsigned int)(v36 - 3);
                    v38 = (unsigned int)(v36 - 2);
                    v39 = (unsigned int)(v36 - 1);
                    if ( v31 > v34 )
                    {
                      v27 = (v31 & 7) != 0
                          ? ((unsigned int)(*(unsigned __int8 *)(((unsigned int)v36 & (v8[8] - 1)) + v32)
                                          | ((*(unsigned __int8 *)(((unsigned int)v39 & (v8[8] - 1)) + v32)
                                            | ((*(unsigned __int8 *)(((unsigned int)v38 & (v8[8] - 1)) + v32)
                                              | (*(unsigned __int8 *)(((unsigned int)v37 & (v8[8] - 1)) + v32) << 8)) << 8)) << 8)) >> (8 - v33))
                          | (*(unsigned __int8 *)(((v8[8] - 1) & ((_DWORD)v36 - 4)) + v32) << (v33 + 24))
                          : *(unsigned __int8 *)(((unsigned int)v36 & (v8[8] - 1)) + v32)
                          | ((*(unsigned __int8 *)(((unsigned int)v39 & (v8[8] - 1)) + v32)
                            | ((*(unsigned __int8 *)(((unsigned int)v38 & (v8[8] - 1)) + v32)
                              | (*(unsigned __int8 *)(((unsigned int)v37 & (v8[8] - 1)) + v32) << 8)) << 8)) << 8);
                      v23 = v150;
                    }
                    else
                    {
                      v27 = (v31 & 7) != 0
                          ? ((unsigned int)(*(unsigned __int8 *)(v36 + v32)
                                          | ((*(unsigned __int8 *)(v39 + v32)
                                            | ((*(unsigned __int8 *)(v38 + v32) | (*(unsigned __int8 *)(v37 + v32) << 8)) << 8)) << 8)) >> (8 - v33))
                          | (*(unsigned __int8 *)((unsigned int)(v36 - 4) + v32) << (v33 + 24))
                          : *(unsigned __int8 *)(v36 + v32)
                          | ((*(unsigned __int8 *)(v39 + v32)
                            | ((*(unsigned __int8 *)(v38 + v32) | (*(unsigned __int8 *)(v37 + v32) << 8)) << 8)) << 8);
                    }
                    *v8 = v27;
                    v29 += 32;
                  }
                  v40 = v29 - 2;
                  v8[1] = v40;
                  v41 = (v35 | (unsigned __int8)((unsigned __int64)v27 >> v40)) & 3;
                  v42 = *(unsigned __int16 *)(v23 + 2 * (v41 + 4 * i));
                  if ( (v42 & 1) != 0 )
                    break;
                }
                if ( (v42 & 2) != 0 )
                  v8[1] = v40 + 1;
                v43 = v138;
                v44 = 0;
                v45 = v135;
                v46 = v42 >> 2;
                if ( v138 )
                {
                  v47 = (1 << v145) - 1;
                  do
                  {
                    v48 = (v47 & v46) - v144;
                    if ( (v47 & v46) != v144 )
                    {
                      v53 = v8[1];
                      if ( v53 )
                      {
                        v54 = v53 - 1;
                        v55 = (*v8 >> (v53 - 1)) & 1;
                      }
                      else
                      {
                        v79 = CDK_get32(v8 + 2, v41, v40);
                        v47 = (1 << v145) - 1;
                        v54 = 31;
                        *v8 = v79;
                        v55 = v79 >> 31;
                      }
                      v8[1] = v54;
                      if ( v55 )
                        v48 = -v48;
                    }
                    v49 = v44 + v135;
                    ++v44;
                    *(float *)&v24[4 * v49] = (float)v48;
                    v46 >>= v145;
                  }
                  while ( v44 < v138 );
                }
                if ( v134 == 11 )
                {
                  v83 = *(float *)&v24[4 * v135];
                  if ( v83 != 16.0 && v83 != -16.0 )
                  {
                    v84 = v140;
                    v85 = v8 + 2;
                    goto LABEL_87;
                  }
                  v87 = 4;
                  do
                  {
                    v88 = v8[1];
                    v85 = v8 + 2;
                    if ( v88 )
                    {
                      v41 = *v8;
                      v89 = v88 - 1;
                      v90 = (*v8 >> v89) & 1;
                    }
                    else
                    {
                      v124 = CDK_get32(v8 + 2, v41, v40);
                      v41 = v124;
                      *v8 = v124;
                      v90 = v124 >> 31;
                      v89 = 31;
                    }
                    v8[1] = v89;
                    if ( !v90 )
                      break;
                    if ( ++v87 == 13 )
                    {
                      v84 = v140;
                      *(float *)&v140[4 * v135] = v14;
                      goto LABEL_87;
                    }
                  }
                  while ( v87 < 13 );
                  v91 = 0;
                  v92 = v87 - v89;
                  if ( v87 - v89 > 0 )
                  {
                    if ( v92 != 32 )
                      v91 = (_DWORD)v41 << v92;
                    v93 = v8[9];
                    v94 = v8[5] + 32;
                    *v85 -= 32;
                    v95 = *((_QWORD *)v8 + 3);
                    v96 = v94 & 7;
                    v97 = (v94 - 1) >> 3;
                    v8[5] = v94 & (v93 - 1);
                    v98 = (unsigned int)(v97 - 3);
                    v99 = (unsigned int)(v97 - 2);
                    v100 = (unsigned int)(v97 - 1);
                    if ( v94 > v93 )
                    {
                      v40 = *(unsigned __int8 *)(((unsigned int)v97 & (v8[8] - 1)) + v95)
                          | ((*(unsigned __int8 *)(((unsigned int)v100 & (v8[8] - 1)) + v95)
                            | ((*(unsigned __int8 *)(((unsigned int)v99 & (v8[8] - 1)) + v95)
                              | (*(unsigned __int8 *)(((unsigned int)v98 & (v8[8] - 1)) + v95) << 8)) << 8)) << 8);
                      if ( (v94 & 7) == 0 )
                        goto LABEL_132;
                      v101 = *(unsigned __int8 *)(((v8[8] - 1) & ((_DWORD)v97 - 4)) + v95);
LABEL_102:
                      v40 = (unsigned int)v40 >> (8 - v96);
                      LODWORD(v41) = v40 | (v101 << (v96 + 24));
                    }
                    else
                    {
                      v40 = *(unsigned __int8 *)(v97 + v95)
                          | ((*(unsigned __int8 *)(v100 + v95)
                            | ((*(unsigned __int8 *)(v99 + v95) | (*(unsigned __int8 *)(v98 + v95) << 8)) << 8)) << 8);
                      if ( (v94 & 7) != 0 )
                      {
                        v101 = *(unsigned __int8 *)((unsigned int)(v97 - 4) + v95);
                        goto LABEL_102;
                      }
LABEL_132:
                      LODWORD(v41) = v40;
                    }
                    v45 = v135;
                    v89 += 32;
                    v43 = v138;
                    *v8 = v41;
                  }
                  v102 = v89 - v87;
                  v8[1] = v102;
                  v41 = BitMask[v87] & (v91 | ((unsigned int)v41 >> v102));
                  v103 = -(v41 + (1 << v87));
                  if ( v83 >= 0.0 )
                    v103 = v41 + (1 << v87);
                  v104 = _mm_cvtsi32_si128(v103);
                  v84 = v140;
                  *(_DWORD *)&v140[4 * v135] = _mm_cvtepi32_ps(v104).m128_u32[0];
LABEL_87:
                  v86 = *(float *)&v84[4 * v135 + 4];
                  if ( v86 != 16.0 && v86 != -16.0 )
                  {
                    v24 = v140;
                    goto LABEL_28;
                  }
                  v105 = 4;
                  do
                  {
                    v106 = v8[1];
                    if ( v106 )
                    {
                      v107 = v106 - 1;
                      v8[1] = v106 - 1;
                      v40 = *v8;
                      v41 = (*v8 >> (v106 - 1)) & 1;
                    }
                    else
                    {
                      v125 = CDK_get32(v8 + 2, v41, v40);
                      *v8 = v125;
                      v41 = v125 >> 31;
                      v40 = v125;
                      v8[1] = 31;
                      v107 = 31;
                    }
                    if ( !(_DWORD)v41 )
                      break;
                    if ( ++v105 == 13 )
                    {
                      v24 = v140;
                      *(float *)&v140[4 * v135 + 4] = v14;
                      goto LABEL_28;
                    }
                  }
                  while ( v105 < 13 );
                  v108 = 0;
                  v109 = v105 - v107;
                  if ( v105 - v107 > 0 )
                  {
                    if ( v109 != 32 )
                      v108 = (_DWORD)v40 << v109;
                    v110 = v8[9];
                    v111 = v8[5] + 32;
                    v112 = (*((_BYTE *)v8 + 20) + 32) & 7;
                    v113 = v8[5] + 31;
                    v8[5] = v111 & (v110 - 1);
                    *v85 -= 32;
                    v114 = v113 >> 3;
                    v115 = (unsigned int)(v114 - 3);
                    v116 = (unsigned int)(v114 - 2);
                    v117 = (unsigned int)(v114 - 1);
                    if ( v111 > v110 )
                    {
                      v126 = *((_QWORD *)v8 + 3);
                      v119 = *(unsigned __int8 *)(((unsigned int)v114 & (v8[8] - 1)) + v126)
                           | ((*(unsigned __int8 *)(((unsigned int)v117 & (v8[8] - 1)) + v126)
                             | ((*(unsigned __int8 *)(((unsigned int)v116 & (v8[8] - 1)) + v126)
                               | (*(unsigned __int8 *)(((unsigned int)v115 & (v8[8] - 1)) + v126) << 8)) << 8)) << 8);
                      if ( !v112 )
                        goto LABEL_133;
                      v120 = *(unsigned __int8 *)(((v8[8] - 1) & ((_DWORD)v114 - 4)) + v126);
LABEL_119:
                      LODWORD(v40) = (v119 >> (8 - v112)) | (v120 << (v112 + 24));
                    }
                    else
                    {
                      v118 = *((_QWORD *)v8 + 3);
                      v119 = *(unsigned __int8 *)(v114 + v118)
                           | ((*(unsigned __int8 *)(v117 + v118)
                             | ((*(unsigned __int8 *)(v116 + v118) | (*(unsigned __int8 *)(v115 + v118) << 8)) << 8)) << 8);
                      if ( v112 )
                      {
                        v120 = *(unsigned __int8 *)((unsigned int)(v114 - 4) + v118);
                        goto LABEL_119;
                      }
LABEL_133:
                      LODWORD(v40) = v119;
                    }
                    *v8 = v40;
                    v107 += 32;
                  }
                  v24 = v140;
                  v121 = v107 - v105;
                  v43 = v138;
                  v122 = v108 | ((unsigned int)v40 >> v121);
                  v45 = v135;
                  v8[1] = v121;
                  v123 = -((BitMask[v105] & v122) + (1 << v105));
                  if ( v86 >= 0.0 )
                    v123 = (BitMask[v105] & v122) + (1 << v105);
                  *(float *)&v140[4 * v135 + 4] = (float)v123;
                }
LABEL_28:
                v19 = v146;
                v50 = v43 + v45;
                v23 = v150;
                v135 = v50;
              }
              while ( v50 < v146 );
              v25 = v136;
              v26 = v155;
              v21 = v147;
              v17 = v139;
LABEL_30:
              v24 += v26;
              ++v25;
              v140 = v24;
              v136 = v25;
              if ( v25 >= v17 )
              {
LABEL_31:
                v20 = v142;
                LODWORD(v18) = v141;
                goto LABEL_32;
              }
            }
          }
          v56 = 0;
          v137 = 0;
          if ( v17 )
          {
            v57 = v139;
            v58 = 4LL * v16;
            v156 = v58;
            while ( 1 )
            {
              v59 = v21;
              if ( v21 < v19 )
                break;
LABEL_68:
              v24 += v58;
              ++v56;
              v140 = v24;
              v137 = v56;
              if ( v56 >= v57 )
              {
                v17 = v139;
                goto LABEL_31;
              }
            }
LABEL_51:
            v60 = *v8;
            for ( j = 0; ; j = v75 >> 2 )
            {
              v62 = v8[1];
              if ( (int)(2 - v62) > 0 )
                break;
              v67 = 0;
LABEL_58:
              v74 = v62 - 2;
              v8[1] = v74;
              v75 = *(unsigned __int16 *)(v150
                                        + 2 * (((v67 | (unsigned __int8)((unsigned __int64)v60 >> v74)) & 3) + 4 * j));
              if ( (v75 & 1) != 0 )
              {
                if ( (v75 & 2) != 0 )
                  v8[1] = v74 + 1;
                v76 = 0;
                v24 = v140;
                v77 = v75 >> 2;
                if ( v138 )
                {
                  do
                  {
                    v78 = v76 + v59;
                    v76 = (unsigned int)(v76 + 1);
                    *(float *)&v140[4 * v78] = (float)(int)((((1 << v145) - 1) & v77) - v144);
                    v77 = (unsigned int)((int)v77 >> v145);
                  }
                  while ( (int)v76 < v138 );
                  v8 = a1;
                }
                if ( v134 == 11 )
                {
                  v127 = *(float *)&v140[4 * v59];
                  if ( v127 == 16.0 || v127 == -16.0 )
                    *(float *)&v140[4 * v59] = CBlock_GetEscape_fl(v8, v76, v77);
                  v128 = *(float *)&v140[4 * v59 + 4];
                  if ( v128 == 16.0 || v128 == -16.0 )
                    *(float *)&v140[4 * v59 + 4] = CBlock_GetEscape_fl(v8, v76, v77);
                }
                v19 = v146;
                v59 += v138;
                if ( v59 >= v146 )
                {
                  v58 = v156;
                  v56 = v137;
                  v21 = v147;
                  v57 = v139;
                  goto LABEL_68;
                }
                goto LABEL_51;
              }
            }
            v63 = v8[5];
            v8[2] -= 32;
            v63 += 32;
            v64 = *((_QWORD *)v8 + 3);
            v65 = v63 & 7;
            v66 = v8[9];
            v67 = v60 << (2 - v62);
            v68 = (v63 - 1) >> 3;
            v8[5] = v63 & (v66 - 1);
            v69 = (unsigned int)(v68 - 3);
            v70 = (unsigned int)(v68 - 2);
            v71 = (unsigned int)(v68 - 1);
            if ( v63 > v66 )
            {
              v80 = v8[8] - 1;
              v72 = *(unsigned __int8 *)(((unsigned int)v68 & v80) + v64)
                  | ((*(unsigned __int8 *)((v80 & (unsigned int)v71) + v64)
                    | ((*(unsigned __int8 *)((v80 & (unsigned int)v70) + v64)
                      | (*(unsigned __int8 *)((v80 & (unsigned int)v69) + v64) << 8)) << 8)) << 8);
              if ( !v65 )
                goto LABEL_81;
              v73 = *(unsigned __int8 *)((v80 & (unsigned int)(v68 - 4)) + v64);
LABEL_56:
              v60 = (v72 >> (8 - v65)) | (v73 << (v65 + 24));
            }
            else
            {
              v72 = *(unsigned __int8 *)(v68 + v64)
                  | ((*(unsigned __int8 *)(v71 + v64)
                    | ((*(unsigned __int8 *)(v70 + v64) | (*(unsigned __int8 *)(v69 + v64) << 8)) << 8)) << 8);
              if ( v65 )
              {
                v73 = *(unsigned __int8 *)((unsigned int)(v68 - 4) + v64);
                goto LABEL_56;
              }
LABEL_81:
              v60 = v72;
            }
            *v8 = v60;
            v62 += 32;
            goto LABEL_58;
          }
LABEL_32:
          v9 = v152;
          v13 = v151;
LABEL_33:
          v12 = v153;
          v18 = (unsigned int)(v18 + 1);
          v10 = v157;
          ++v20;
          v16 = v148;
          v141 = v18;
          v142 = v20;
        }
        while ( (int)v18 < v153 );
        v11 = v143;
        v7 = a2;
        LODWORD(v15) = v149;
LABEL_35:
        v11 += v17;
        v15 = (unsigned int)(v15 + 1);
        v143 = v11;
        v149 = v15;
        if ( (int)v15 >= v154 )
        {
          v5 = (const struct SamplingRateInfo *)a3;
          goto LABEL_37;
        }
      }
    }
  }
  if ( *(_DWORD *)(v7 + 1684) != 2 && (v4 & 0x18) == 0 )
  {
    v51 = *(_BYTE **)(v7 + 1704);
    if ( v51[1382] )
    {
      v129 = 0;
      v130 = *(__int16 *)(*(_QWORD *)v5 + 2LL * (unsigned __int8)v51[1384]);
      do
      {
        v130 += (unsigned __int8)v51[v129 + 1385];
        v131 = *(float *)&v9[4 * v130];
        v132 = (float)(unsigned __int8)v51[v129 + 1389];
        if ( v131 <= 0.0 )
          v133 = v131 - v132;
        else
          v133 = v132 + v131;
        *(float *)&v9[4 * v130] = v133;
        ++v129;
      }
      while ( v129 <= (unsigned __int8)v51[1383] );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016880  mov     rax, rsp
0x180016883  mov     [rax+20h], r9d
0x180016887  mov     [rax+18h], r8
0x18001688b  mov     [rax+10h], rdx
0x18001688f  mov     [rax+8], rcx
0x180016893  push    rbx
0x180016894  push    rbp
0x180016895  push    rsi
0x180016896  push    rdi
0x180016897  push    r13
0x180016899  push    r14
0x18001689b  sub     rsp, 0C8h
0x1800168a2  cmp     dword ptr [rdx+694h], 2
0x1800168a9  mov     ebx, r9d
0x1800168ac  movaps  xmmword ptr [rax-58h], xmm6
0x1800168b0  mov     rdi, r8
0x1800168b3  mov     rax, r8
0x1800168b6  mov     r14, rdx
0x1800168b9  mov     rsi, rcx
0x1800168bc  jnz     short loc_1800168C2
0x1800168be  lea     rax, [r8+8]
0x1800168c2  mov     r13, [rdx+680h]
0x1800168c9  mov     r8d, 1000h; Size
0x1800168cf  mov     rbp, [rax]
0x1800168d2  mov     rcx, r13; void *
0x1800168d5  xor     edx, edx; Val
0x1800168d7  mov     [rsp+0F8h+var_68], rbp
0x1800168df  mov     [rsp+0F8h+var_80], r13
0x1800168e4  call    memset_0
0x1800168e9  xorps   xmm6, xmm6
0x1800168ec  test    bl, 4
0x1800168ef  jnz     loc_180016FD4
0x1800168f5  movzx   eax, byte ptr [r14+690h]
0x1800168fd  mov     [rsp+0F8h+var_74], eax
0x180016904  test    eax, eax
0x180016906  jz      loc_180016C86
0x18001690c  mov     r10, [r14+6A8h]
0x180016913  xor     r11d, r11d
0x180016916  movzx   ecx, byte ptr [r14+698h]
0x18001691e  add     r10, 200h
0x180016925  movss   xmm3, cs:__real@41800000
0x18001692d  movss   xmm2, cs:__real@c1800000
0x180016935  movss   xmm4, cs:__real@46000000
0x18001693d  mov     [rsp+0F8h+var_38], r12
0x180016945  xor     r12d, r12d
0x180016948  mov     [rsp+0F8h+var_40], r15
0x180016950  mov     r15d, [r14+69Ch]
0x180016957  mov     [rsp+0F8h+var_94], r12d
0x18001695c  mov     [rsp+0F8h+var_88], r10
0x180016961  mov     [rsp+0F8h+var_78], ecx
0x180016968  mov     [rsp+0F8h+var_98], r15d
0x18001696d  mov     [rsp+0F8h+var_AC], r11d
0x180016972  movzx   edi, byte ptr [r12+r14+688h]
0x18001697b  xor     r8d, r8d
0x18001697e  movsx   edx, word ptr [rbp+0]
0x180016982  mov     r9d, r12d
0x180016985  shl     r9d, 4
0x180016989  mov     [rsp+0F8h+var_C8], edi
0x18001698d  mov     [rsp+0F8h+var_B0], r9d
0x180016992  mov     [rsp+0F8h+var_B4], r8d
0x180016997  test    ecx, ecx
0x180016999  jz      loc_180016C49
0x18001699f  nop
0x1800169a0  movsxd  rcx, r9d
0x1800169a3  mov     ebx, edx
0x1800169a5  mov     [rsp+0F8h+var_9C], edx
0x1800169a9  movsx   edx, word ptr [rbp+r8*2+2]
0x1800169af  mov     [rsp+0F8h+var_A0], edx
0x1800169b3  movzx   r14d, byte ptr [rcx+r10]
0x1800169b8  mov     [rsp+0F8h+var_D8], r14b
0x1800169bd  cmp     r14b, 10h
0x1800169c1  jnb     loc_18001702A
0x1800169c7  lea     eax, [r14-1]
0x1800169cb  cmp     al, 0Bh
0x1800169cd  ja      loc_180016CF3
0x1800169d3  lea     rbp, __ImageBase
0x1800169da  movzx   eax, r14b
0x1800169de  add     rax, rax
0x1800169e1  mov     r10d, 1
0x1800169e7  movzx   ecx, ss:rva byte_1800987B8[rbp+rax*8]
0x1800169ef  movzx   r11d, ss:rva byte_1800987BA[rbp+rax*8]
0x1800169f8  mov     r12, ss:rva ?AACcodeBookDescriptionTable@@3QBUCodeBookDescription@@B[rbp+rax*8]; CodeBookDescription const near * const AACcodeBookDescriptionTable ...
0x180016a00  mov     [rsp+0F8h+var_CC], ecx
0x180016a04  movzx   ecx, ss:rva byte_1800987B9[rbp+rax*8]
0x180016a0c  mov     eax, r15d
0x180016a0f  imul    eax, [rsp+0F8h+var_AC]
0x180016a14  shl     r10d, cl
0x180016a17  dec     r10d
0x180016a1a  mov     [rsp+0F8h+var_A8], r11d
0x180016a1f  mov     [rsp+0F8h+var_A4], ecx
0x180016a23  mov     [rsp+0F8h+var_B8], r10d
0x180016a28  cdqe
0x180016a2a  mov     [rsp+0F8h+var_90], r12
0x180016a2f  lea     r13, [r13+rax*4+0]
0x180016a34  mov     [rsp+0F8h+var_C0], r13
0x180016a39  test    r11d, r11d
0x180016a3c  jnz     loc_180016D02
0x180016a42  xor     eax, eax
0x180016a44  mov     [rsp+0F8h+var_D0], eax
0x180016a48  test    edi, edi
0x180016a4a  jz      loc_180016C00
0x180016a50  movsxd  rcx, r15d
0x180016a53  shl     rcx, 2
0x180016a57  mov     [rsp+0F8h+var_70], rcx
0x180016a5f  mov     [rsp+0F8h+var_D4], ebx
0x180016a63  cmp     ebx, edx
0x180016a65  jge     loc_180016BE0
0x180016a6b  nop     dword ptr [rax+rax+00h]
0x180016a70  mov     r9d, [rsi]
0x180016a73  xor     edi, edi
0x180016a75  mov     r8d, [rsi+4]
0x180016a79  mov     ecx, 2
0x180016a7e  sub     ecx, r8d
0x180016a81  test    ecx, ecx
0x180016a83  jle     loc_180016CEB
0x180016a89  mov     edx, [rsi+14h]
0x180016a8c  add     dword ptr [rsi+8], 0FFFFFFE0h
0x180016a90  add     edx, 20h ; ' '
0x180016a93  mov     rbx, [rsi+18h]
0x180016a97  mov     r10d, edx
0x180016a9a  shl     r9d, cl
0x180016a9d  and     r10d, 7
0x180016aa1  mov     ecx, [rsi+24h]
0x180016aa4  mov     r11d, r9d
0x180016aa7  lea     r9d, [rdx-1]
0x180016aab  shr     r9d, 3
0x180016aaf  lea     eax, [rcx-1]
0x180016ab2  and     eax, edx
0x180016ab4  mov     [rsi+14h], eax
0x180016ab7  lea     ebp, [r9-3]
0x180016abb  lea     r14d, [r9-2]
0x180016abf  lea     r15d, [r9-1]
0x180016ac3  cmp     edx, ecx
0x180016ac5  ja      loc_180016ED7
0x180016acb  movzx   ecx, byte ptr [r14+rbx]
0x180016ad0  movzx   edx, byte ptr [rbp+rbx+0]
0x180016ad5  shl     edx, 8
0x180016ad8  or      edx, ecx
0x180016ada  movzx   ecx, byte ptr [r15+rbx]
0x180016adf  shl     edx, 8
0x180016ae2  or      edx, ecx
0x180016ae4  movzx   ecx, byte ptr [r9+rbx]
0x180016ae9  shl     edx, 8
0x180016aec  or      edx, ecx
0x180016aee  test    r10d, r10d
0x180016af1  jz      loc_18001701A
0x180016af7  lea     eax, [r9-4]
0x180016afb  movzx   r9d, byte ptr [rax+rbx]
0x180016b00  lea     ecx, [r10+18h]
0x180016b04  shl     r9d, cl
0x180016b07  mov     ecx, 8
0x180016b0c  sub     ecx, r10d
0x180016b0f  shr     edx, cl
0x180016b11  or      r9d, edx
0x180016b14  mov     [rsi], r9d
0x180016b17  add     r8d, 20h ; ' '
0x180016b1b  add     r8d, 0FFFFFFFEh
0x180016b1f  mov     edx, r9d
0x180016b22  movzx   ecx, r8b
0x180016b26  mov     [rsi+4], r8d
0x180016b2a  shr     rdx, cl
0x180016b2d  mov     eax, r11d
0x180016b30  or      rdx, rax
0x180016b33  and     edx, 3
0x180016b36  lea     rcx, [rdx+rdi*4]
0x180016b3a  movzx   edi, word ptr [r12+rcx*2]
0x180016b3f  test    dil, 1
0x180016b43  jnz     short loc_180016B4D
0x180016b45  shr     edi, 2
0x180016b48  jmp     loc_180016A75
0x180016b4d  test    dil, 2
0x180016b51  jz      short loc_180016B5A
0x180016b53  lea     eax, [r8+1]
0x180016b57  mov     [rsi+4], eax
0x180016b5a  mov     r12d, [rsp+0F8h+var_CC]
0x180016b5f  xor     r14d, r14d
0x180016b62  mov     ebp, [rsp+0F8h+var_D4]
0x180016b66  shr     edi, 2
0x180016b69  test    r12d, r12d
0x180016b6c  jz      short loc_180016BA9
0x180016b6e  mov     r10d, [rsp+0F8h+var_B8]
0x180016b73  mov     r15d, [rsp+0F8h+var_A8]
0x180016b78  mov     ebx, edi
0x180016b7a  and     ebx, r10d
0x180016b7d  sub     ebx, r15d
0x180016b80  jnz     loc_180016CC4
0x180016b86  lea     eax, [r14+rbp]
0x180016b8a  movd    xmm0, ebx
0x180016b8e  movsxd  rcx, eax
0x180016b91  inc     r14d
0x180016b94  cvtdq2ps xmm0, xmm0
0x180016b97  movss   dword ptr [r13+rcx*4+0], xmm0
0x180016b9e  mov     ecx, [rsp+0F8h+var_A4]
0x180016ba2  sar     edi, cl
0x180016ba4  cmp     r14d, r12d
0x180016ba7  jl      short loc_180016B78
0x180016ba9  cmp     [rsp+0F8h+var_D8], 0Bh
0x180016bae  jz      loc_180017045
0x180016bb4  mov     edx, [rsp+0F8h+var_A0]
0x180016bb8  add     ebp, r12d
0x180016bbb  mov     r12, [rsp+0F8h+var_90]
0x180016bc0  mov     [rsp+0F8h+var_D4], ebp
0x180016bc4  cmp     ebp, edx
0x180016bc6  jl      loc_180016A70
0x180016bcc  mov     eax, [rsp+0F8h+var_D0]
0x180016bd0  mov     rcx, [rsp+0F8h+var_70]
0x180016bd8  mov     ebx, [rsp+0F8h+var_9C]
0x180016bdc  mov     edi, [rsp+0F8h+var_C8]
0x180016be0  add     r13, rcx
0x180016be3  inc     eax
0x180016be5  mov     [rsp+0F8h+var_C0], r13
0x180016bea  mov     [rsp+0F8h+var_D0], eax
0x180016bee  cmp     eax, edi
0x180016bf0  jl      loc_180016A5F
0x180016bf6  mov     r9d, [rsp+0F8h+var_B0]
0x180016bfb  mov     r8d, [rsp+0F8h+var_B4]
0x180016c00  mov     r13, [rsp+0F8h+var_80]
0x180016c05  mov     r10, [rsp+0F8h+var_88]
0x180016c0a  mov     ecx, [rsp+0F8h+var_78]
0x180016c11  inc     r8d
0x180016c14  mov     rbp, [rsp+0F8h+var_68]
0x180016c1c  inc     r9d
0x180016c1f  mov     r15d, [rsp+0F8h+var_98]
0x180016c24  mov     [rsp+0F8h+var_B4], r8d
0x180016c29  mov     [rsp+0F8h+var_B0], r9d
0x180016c2e  cmp     r8d, ecx
0x180016c31  jl      loc_1800169A0
0x180016c37  mov     r11d, [rsp+0F8h+var_AC]
0x180016c3c  mov     r14, [rsp+0F8h+arg_8]
0x180016c44  mov     r12d, [rsp+0F8h+var_94]
0x180016c49  add     r11d, edi
0x180016c4c  inc     r12d
0x180016c4f  mov     [rsp+0F8h+var_AC], r11d
0x180016c54  mov     [rsp+0F8h+var_94], r12d
0x180016c59  cmp     r12d, [rsp+0F8h+var_74]
0x180016c61  jl      loc_180016972
0x180016c67  mov     r15, [rsp+0F8h+var_40]
0x180016c6f  mov     r12, [rsp+0F8h+var_38]
0x180016c77  mov     rdi, [rsp+0F8h+arg_10]
0x180016c7f  mov     ebx, [rsp+0F8h+arg_18]
0x180016c86  cmp     dword ptr [r14+694h], 2
0x180016c8e  jz      short loc_180016CA9
0x180016c90  test    bl, 18h
0x180016c93  jnz     short loc_180016CA9
0x180016c95  mov     rdx, [r14+6A8h]
0x180016c9c  cmp     byte ptr [rdx+566h], 0
0x180016ca3  jnz     loc_1800174D3
0x180016ca9  xor     eax, eax
0x180016cab  movaps  xmm6, [rsp+0F8h+var_58]
0x180016cb3  add     rsp, 0C8h
0x180016cba  pop     r14
0x180016cbc  pop     r13
0x180016cbe  pop     rdi
0x180016cbf  pop     rsi
0x180016cc0  pop     rbp
0x180016cc1  pop     rbx
0x180016cc2  retn
0x180016cc4  mov     eax, [rsi+4]
0x180016cc7  test    eax, eax
0x180016cc9  jz      loc_180016F56
0x180016ccf  lea     ecx, [rax-1]
0x180016cd2  mov     eax, [rsi]
0x180016cd4  shr     eax, cl
0x180016cd6  and     eax, 1
0x180016cd9  mov     [rsi+4], ecx
0x180016cdc  test    eax, eax
0x180016cde  jz      loc_180016B86
0x180016ce4  neg     ebx
0x180016ce6  jmp     loc_180016B86
0x180016ceb  xor     r11d, r11d
0x180016cee  jmp     loc_180016B1B
0x180016cf3  cmp     r14b, 10h
0x180016cf7  jnb     loc_1800169D3
0x180016cfd  jmp     loc_180016C0A
0x180016d02  xor     ebp, ebp
0x180016d04  mov     [rsp+0F8h+var_D0], ebp
0x180016d08  test    edi, edi
0x180016d0a  jz      loc_180016C00
0x180016d10  mov     eax, [rsp+0F8h+var_C8]
0x180016d14  movsxd  rdi, r15d
0x180016d17  shl     rdi, 2
0x180016d1b  mov     [rsp+0F8h+var_70], rdi
0x180016d23  mov     r15d, ebx
0x180016d26  cmp     ebx, edx
0x180016d28  jge     loc_180016EB0
0x180016d2e  xchg    ax, ax
0x180016d30  mov     r9d, [rsi]
0x180016d33  xor     r8d, r8d
0x180016d36  mov     r10d, [rsi+4]
0x180016d3a  mov     ecx, 2
0x180016d3f  sub     ecx, r10d
0x180016d42  test    ecx, ecx
0x180016d44  jle     loc_180016ECF
0x180016d4a  mov     edx, [rsi+14h]
0x180016d4d  add     dword ptr [rsi+8], 0FFFFFFE0h
0x180016d51  add     edx, 20h ; ' '
0x180016d54  mov     rbx, [rsi+18h]
0x180016d58  mov     r11d, edx
0x180016d5b  shl     r9d, cl
0x180016d5e  and     r11d, 7
  ... truncated ...
```

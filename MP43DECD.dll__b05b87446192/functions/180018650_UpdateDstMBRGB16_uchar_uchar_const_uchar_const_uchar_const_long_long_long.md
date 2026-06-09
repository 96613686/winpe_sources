# UpdateDstMBRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180018650`
- end: `0x18001a1df`
- name: `?UpdateDstMBRGB16@@YAXPEAEPEBE11JJJ@Z`
- size: `7055`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d630`

## callees

- `0x180018650`

## pseudocode

```c
void __fastcall UpdateDstMBRGB16(
        unsigned __int8 *a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  unsigned __int8 *v7; // r13
  const unsigned __int8 *v8; // r14
  unsigned __int8 *v9; // rbp
  const unsigned __int8 *v10; // rdi
  const unsigned __int8 *v11; // r12
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // r11d
  int v15; // ecx
  __int64 v16; // rax
  int v17; // r9d
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // r8d
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  int v24; // r11d
  int v25; // ebx
  __int64 v26; // rax
  int v27; // r9d
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // ecx
  int v31; // r8d
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  int v35; // r11d
  int v36; // ebx
  __int64 v37; // rax
  int v38; // r9d
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // r12d
  int v42; // r14d
  int v43; // r13d
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // rdx
  __int64 v47; // rax
  int v48; // ebp
  int v49; // esi
  int v50; // r15d
  int v51; // r8d
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rax
  int v55; // edi
  int v56; // ebx
  int v57; // r11d
  int v58; // r8d
  int v59; // r9d
  int v60; // r8d
  int v61; // r9d
  int v62; // r8d
  __int64 v63; // rax
  int v64; // r8d
  __int64 v65; // rax
  int v66; // r8d
  int v67; // r9d
  int v68; // r8d
  __int64 v69; // rax
  int v70; // r8d
  int v71; // r9d
  unsigned __int8 *v72; // r12
  int v73; // r8d
  int v74; // r9d
  int v75; // r8d
  __int64 v76; // rax
  int v77; // r9d
  __int64 v78; // rcx
  bool v79; // zf
  __int64 v80; // rdx
  __int64 v81; // rax
  int v82; // ebx
  int v83; // r11d
  __int64 v84; // rax
  int v85; // r9d
  __int64 v86; // rdx
  __int64 v87; // rax
  int v88; // r8d
  __int64 v89; // rax
  __int64 v90; // rdx
  __int64 v91; // rax
  int v92; // r11d
  int v93; // ebx
  __int64 v94; // rax
  int v95; // r9d
  __int64 v96; // rdx
  __int64 v97; // rax
  int v98; // r8d
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rax
  int v102; // r11d
  int v103; // ebx
  __int64 v104; // rax
  int v105; // r9d
  __int64 v106; // rax
  int v107; // r15d
  __int64 v108; // rdx
  int v109; // r12d
  int v110; // r13d
  int v111; // r8d
  int v112; // r9d
  __int64 v113; // rdx
  __int64 v114; // rax
  int v115; // ebp
  int v116; // esi
  int v117; // r14d
  int v118; // r8d
  __int64 v119; // rax
  __int64 v120; // rdx
  __int64 v121; // rcx
  int v122; // edi
  int v123; // r11d
  int v124; // ebx
  int v125; // r8d
  int v126; // r9d
  int v127; // r8d
  __int64 v128; // rax
  int v129; // r8d
  __int64 v130; // rax
  int v131; // r8d
  __int64 v132; // rax
  int v133; // r8d
  __int64 v134; // rax
  int v135; // r8d
  __int64 v136; // rax
  int v137; // r8d
  int v138; // r9d
  unsigned __int8 *v139; // r12
  int v140; // r8d
  int v141; // r9d
  int v142; // r8d
  __int64 v143; // rax
  int v144; // r9d
  __int64 v145; // rcx
  int v146; // [rsp+0h] [rbp-98h]
  int v147; // [rsp+4h] [rbp-94h]
  int v148; // [rsp+4h] [rbp-94h]
  int v149; // [rsp+8h] [rbp-90h]
  int v150; // [rsp+8h] [rbp-90h]
  int v151; // [rsp+Ch] [rbp-8Ch]
  int v152; // [rsp+Ch] [rbp-8Ch]
  int v153; // [rsp+10h] [rbp-88h]
  int v154; // [rsp+10h] [rbp-88h]
  int v155; // [rsp+14h] [rbp-84h]
  int v156; // [rsp+14h] [rbp-84h]
  int v157; // [rsp+18h] [rbp-80h]
  int v158; // [rsp+18h] [rbp-80h]
  int v159; // [rsp+1Ch] [rbp-7Ch]
  int v160; // [rsp+1Ch] [rbp-7Ch]
  int v161; // [rsp+20h] [rbp-78h]
  int v162; // [rsp+20h] [rbp-78h]
  int v163; // [rsp+24h] [rbp-74h]
  int v164; // [rsp+24h] [rbp-74h]
  int v165; // [rsp+28h] [rbp-70h]
  int v166; // [rsp+28h] [rbp-70h]
  int v167; // [rsp+2Ch] [rbp-6Ch]
  int v168; // [rsp+2Ch] [rbp-6Ch]
  int v169; // [rsp+30h] [rbp-68h]
  int v170; // [rsp+30h] [rbp-68h]
  int v171; // [rsp+34h] [rbp-64h]
  int v172; // [rsp+38h] [rbp-60h]
  int v173; // [rsp+38h] [rbp-60h]
  int v174; // [rsp+3Ch] [rbp-5Ch]
  int v175; // [rsp+3Ch] [rbp-5Ch]
  __int64 v176; // [rsp+40h] [rbp-58h]
  unsigned __int8 *v177; // [rsp+A0h] [rbp+8h]
  const unsigned __int8 *v178; // [rsp+A8h] [rbp+10h]
  const unsigned __int8 *v179; // [rsp+B0h] [rbp+18h]
  const unsigned __int8 *v180; // [rsp+B8h] [rbp+20h]

  v180 = a4;
  v179 = a3;
  v178 = a2;
  v177 = a1;
  v7 = a1;
  v8 = a4;
  v9 = g_rgiClapTabDec;
  v10 = a3;
  v11 = a2;
  v146 = 8;
  v176 = 2LL * a7;
  if ( g_redscale == 7 )
  {
    do
    {
      v12 = *v10;
      v13 = *v8;
      v14 = *((_DWORD *)&g_iVtoR + v13);
      v15 = *((_DWORD *)&g_iVtoG + v13) + *((_DWORD *)&g_iUtoG + v12);
      v16 = v11[1];
      v161 = v15;
      v159 = *((_DWORD *)&g_iUtoB + v12);
      v157 = v14;
      v17 = *((_DWORD *)&g_iYscale + *v11);
      *(_DWORD *)v7 = ((unsigned int)(v9[v159 + v17] + (v9[v159 + *((_DWORD *)&g_iYscale + v16)] << 16)) >> 3)
                    & 0x1F001F
                    | ((v9[v14 + *((_DWORD *)&g_iYscale + v16)] << 23) + (v9[v14 + v17] << 7)) & 0x7C007C00
                    | ((v9[*((_DWORD *)&g_iYscale + v16) - v15] << 18) + 4 * v9[v17 - v15]) & 0x3E003E0;
      v18 = v10[1];
      v19 = v8[1];
      v163 = *((_DWORD *)&g_iVtoR + v19);
      v165 = *((_DWORD *)&g_iVtoG + v19) + *((_DWORD *)&g_iUtoG + v18);
      v20 = *((_DWORD *)&g_iYscale + v11[3]);
      v21 = v11[2];
      v147 = *((_DWORD *)&g_iUtoB + v18);
      *((_DWORD *)v7 + 1) = ((unsigned int)(v9[v147 + *((_DWORD *)&g_iYscale + v21)] + (v9[v147 + v20] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[v20 - v165] << 18) + 4 * v9[*((_DWORD *)&g_iYscale + v21) - v165]) & 0x3E003E0
                          | ((v9[v163 + v20] << 23) + (v9[v163 + *((_DWORD *)&g_iYscale + v21)] << 7)) & 0x7C007C00;
      v22 = v179[2];
      v23 = v8[2];
      v24 = *((_DWORD *)&g_iVtoR + v23);
      v25 = *((_DWORD *)&g_iVtoG + v23) + *((_DWORD *)&g_iUtoG + v22);
      v26 = v11[5];
      v149 = *((_DWORD *)&g_iUtoB + v22);
      v167 = v24;
      v169 = v25;
      v27 = *((_DWORD *)&g_iYscale + v11[4]);
      *((_DWORD *)v7 + 2) = ((unsigned int)(v9[v149 + v27] + (v9[v149 + *((_DWORD *)&g_iYscale + v26)] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[*((_DWORD *)&g_iYscale + v26) - v25] << 18) + 4 * v9[v27 - v25]) & 0x3E003E0
                          | ((v9[v24 + *((_DWORD *)&g_iYscale + v26)] << 23) + (v9[v24 + v27] << 7)) & 0x7C007C00;
      v28 = v179[3];
      v29 = v8[3];
      v30 = *((_DWORD *)&g_iVtoG + v29) + *((_DWORD *)&g_iUtoG + v28);
      v151 = *((_DWORD *)&g_iVtoR + v29);
      v31 = *((_DWORD *)&g_iYscale + v11[7]);
      v32 = v11[6];
      v153 = *((_DWORD *)&g_iUtoB + v28);
      *((_DWORD *)v7 + 3) = ((unsigned int)(v9[v153 + *((_DWORD *)&g_iYscale + v32)] + (v9[v153 + v31] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[v151 + v31] << 23) + (v9[v151 + *((_DWORD *)&g_iYscale + v32)] << 7)) & 0x7C007C00
                          | ((v9[v31 - v30] << 18) + 4 * v9[*((_DWORD *)&g_iYscale + v32) - v30]) & 0x3E003E0;
      v33 = v179[4];
      v34 = v8[4];
      v35 = *((_DWORD *)&g_iVtoR + v34);
      v36 = *((_DWORD *)&g_iVtoG + v34) + *((_DWORD *)&g_iUtoG + v33);
      v37 = v11[9];
      v174 = v36;
      v172 = v35;
      v155 = *((_DWORD *)&g_iUtoB + v33);
      v38 = *((_DWORD *)&g_iYscale + v11[8]);
      *((_DWORD *)v7 + 4) = ((unsigned int)(v9[v155 + v38] + (v9[v155 + *((_DWORD *)&g_iYscale + v37)] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[*((_DWORD *)&g_iYscale + v37) - v36] << 18) + 4 * v9[v38 - v36]) & 0x3E003E0
                          | ((v9[v35 + *((_DWORD *)&g_iYscale + v37)] << 23) + (v9[v35 + v38] << 7)) & 0x7C007C00;
      v39 = v8[5];
      v40 = v179[5];
      v41 = *((_DWORD *)&g_iVtoR + v39);
      v42 = *((_DWORD *)&g_iVtoG + v39) + *((_DWORD *)&g_iUtoG + v40);
      v43 = *((_DWORD *)&g_iUtoB + v40);
      v44 = *((_DWORD *)&g_iYscale + v178[11]);
      v45 = *((_DWORD *)&g_iYscale + v178[10]);
      *((_DWORD *)v177 + 5) = ((unsigned int)(v9[v45 + v43] + (v9[v44 + v43] << 16)) >> 3) & 0x1F001F
                            | ((v9[v41 + v44] << 23) + (v9[v41 + v45] << 7)) & 0x7C007C00
                            | ((v9[v44 - v42] << 18) + 4 * v9[v45 - v42]) & 0x3E003E0;
      v46 = v179[6];
      v47 = v180[6];
      v48 = *((_DWORD *)&g_iVtoG + v47) + *((_DWORD *)&g_iUtoG + v46);
      v49 = *((_DWORD *)&g_iVtoR + v47);
      v50 = *((_DWORD *)&g_iUtoB + v46);
      v51 = *((_DWORD *)&g_iYscale + v178[13]);
      v52 = v178[12];
      *((_DWORD *)v177 + 6) = ((unsigned int)(g_rgiClapTabDec[v50 + *((_DWORD *)&g_iYscale + v52)]
                                            + (g_rgiClapTabDec[v50 + v51] << 16)) >> 3)
                            & 0x1F001F
                            | ((g_rgiClapTabDec[v51 - v48] << 18)
                             + 4 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v52) - v48])
                            & 0x3E003E0
                            | ((g_rgiClapTabDec[v49 + v51] << 23)
                             + (g_rgiClapTabDec[v49 + *((_DWORD *)&g_iYscale + v52)] << 7))
                            & 0x7C007C00;
      v53 = v179[7];
      v54 = v180[7];
      v55 = *((_DWORD *)&g_iUtoB + v53);
      v56 = *((_DWORD *)&g_iVtoR + v54);
      v57 = *((_DWORD *)&g_iVtoG + v54) + *((_DWORD *)&g_iUtoG + v53);
      v58 = *((_DWORD *)&g_iYscale + v178[15]);
      v59 = *((_DWORD *)&g_iYscale + v178[14]);
      *((_DWORD *)v177 + 7) = ((unsigned int)(g_rgiClapTabDec[v55 + v59] + (g_rgiClapTabDec[v55 + v58] << 16)) >> 3)
                            & 0x1F001F
                            | ((g_rgiClapTabDec[v56 + v58] << 23) + (g_rgiClapTabDec[v56 + v59] << 7)) & 0x7C007C00
                            | ((g_rgiClapTabDec[v58 - v57] << 18) + 4 * g_rgiClapTabDec[v59 - v57]) & 0x3E003E0;
      v179 += a6;
      v180 += a6;
      v60 = *((_DWORD *)&g_iYscale + v178[a5 + 1]);
      v61 = *((_DWORD *)&g_iYscale + v178[a5]);
      *(_DWORD *)&v177[a7] = ((unsigned int)(g_rgiClapTabDec[v61 + v159] + (g_rgiClapTabDec[v60 + v159] << 16)) >> 3)
                           & 0x1F001F
                           | ((g_rgiClapTabDec[v60 + v157] << 23) + (g_rgiClapTabDec[v61 + v157] << 7)) & 0x7C007C00
                           | ((g_rgiClapTabDec[v60 - v161] << 18) + 4 * g_rgiClapTabDec[v61 - v161]) & 0x3E003E0;
      v62 = *((_DWORD *)&g_iYscale + v178[a5 + 3]);
      v63 = v178[a5 + 2];
      *(_DWORD *)&v177[a7 + 4] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v63) + v147]
                                               + (g_rgiClapTabDec[v62 + v147] << 16)) >> 3)
                               & 0x1F001F
                               | ((g_rgiClapTabDec[v62 - v165] << 18)
                                + 4 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v63) - v165])
                               & 0x3E003E0
                               | ((g_rgiClapTabDec[v163 + v62] << 23)
                                + (g_rgiClapTabDec[v163 + *((_DWORD *)&g_iYscale + v63)] << 7))
                               & 0x7C007C00;
      v64 = *((_DWORD *)&g_iYscale + v178[a5 + 5]);
      v65 = v178[a5 + 4];
      *(_DWORD *)&v177[a7 + 8] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v65) + v149]
                                               + (g_rgiClapTabDec[v64 + v149] << 16)) >> 3)
                               & 0x1F001F
                               | ((g_rgiClapTabDec[v64 - v169] << 18)
                                + 4 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v65) - v169])
                               & 0x3E003E0
                               | ((g_rgiClapTabDec[v167 + v64] << 23)
                                + (g_rgiClapTabDec[v167 + *((_DWORD *)&g_iYscale + v65)] << 7))
                               & 0x7C007C00;
      v66 = *((_DWORD *)&g_iYscale + v178[a5 + 7]);
      v67 = *((_DWORD *)&g_iYscale + v178[a5 + 6]);
      *(_DWORD *)&v177[a7 + 12] = ((unsigned int)(g_rgiClapTabDec[v67 + v153] + (g_rgiClapTabDec[v66 + v153] << 16)) >> 3)
                                & 0x1F001F
                                | ((g_rgiClapTabDec[v66 + v151] << 23) + (g_rgiClapTabDec[v67 + v151] << 7))
                                & 0x7C007C00
                                | ((g_rgiClapTabDec[v66 - v30] << 18) + 4 * g_rgiClapTabDec[v67 - v30]) & 0x3E003E0;
      v68 = *((_DWORD *)&g_iYscale + v178[a5 + 9]);
      v69 = v178[a5 + 8];
      *(_DWORD *)&v177[a7 + 16] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v69) + v155]
                                                + (g_rgiClapTabDec[v68 + v155] << 16)) >> 3)
                                & 0x1F001F
                                | ((g_rgiClapTabDec[v68 - v174] << 18)
                                 + 4 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v69) - v174])
                                & 0x3E003E0
                                | ((g_rgiClapTabDec[v172 + v68] << 23)
                                 + (g_rgiClapTabDec[v172 + *((_DWORD *)&g_iYscale + v69)] << 7))
                                & 0x7C007C00;
      v70 = *((_DWORD *)&g_iYscale + v178[a5 + 11]);
      v71 = *((_DWORD *)&g_iYscale + v178[a5 + 10]);
      LODWORD(v53) = g_rgiClapTabDec[v41 + v71];
      LODWORD(v69) = v41 + v70;
      v72 = g_rgiClapTabDec;
      *(_DWORD *)&v177[a7 + 20] = ((unsigned int)(g_rgiClapTabDec[v71 + v43] + (g_rgiClapTabDec[v70 + v43] << 16)) >> 3)
                                & 0x1F001F
                                | ((g_rgiClapTabDec[(int)v69] << 23) + ((_DWORD)v53 << 7)) & 0x7C007C00
                                | ((g_rgiClapTabDec[v70 - v42] << 18) + 4 * g_rgiClapTabDec[v71 - v42]) & 0x3E003E0;
      v73 = *((_DWORD *)&g_iYscale + v178[a5 + 13]);
      v74 = *((_DWORD *)&g_iYscale + v178[a5 + 12]);
      LODWORD(v53) = v72[v74 - v48];
      LODWORD(v69) = v73 - v48;
      v9 = v72;
      *(_DWORD *)&v177[a7 + 24] = ((unsigned int)(v72[v50 + v74] + (v72[v50 + v73] << 16)) >> 3) & 0x1F001F
                                | ((v72[(int)v69] << 18) + 4 * v53) & 0x3E003E0
                                | ((v72[v49 + v73] << 23) + (v72[v49 + v74] << 7)) & 0x7C007C00;
      v75 = *((_DWORD *)&g_iYscale + v178[a5 + 15]);
      v76 = v178[a5 + 14];
      v11 = &v178[2 * a5];
      v8 = v180;
      v178 = v11;
      v77 = *((_DWORD *)&g_iYscale + v76);
      v78 = v55 + v75;
      LODWORD(v76) = v55 + v77;
      v10 = v179;
      *(_DWORD *)&v177[a7 + 28] = ((unsigned int)(v9[(int)v76] + (v9[v78] << 16)) >> 3) & 0x1F001F
                                | ((v9[v56 + v75] << 23) + (v9[v56 + v77] << 7)) & 0x7C007C00
                                | ((v9[v75 - v57] << 18) + 4 * v9[v77 - v57]) & 0x3E003E0;
      v7 = &v177[v176];
      v79 = v146-- == 1;
      v177 += v176;
    }
    while ( !v79 );
  }
  else
  {
    do
    {
      v80 = *v10;
      v81 = *v180;
      v156 = *((_DWORD *)&g_iUtoB + v80);
      v82 = *((_DWORD *)&g_iVtoG + v81) + *((_DWORD *)&g_iUtoG + v80);
      v83 = *((_DWORD *)&g_iVtoR + v81);
      v84 = v11[1];
      v173 = v82;
      v175 = v83;
      v85 = *((_DWORD *)&g_iYscale + *v11);
      *(_DWORD *)v7 = ((unsigned int)(v9[v156 + v85] + (v9[v156 + *((_DWORD *)&g_iYscale + v84)] << 16)) >> 3)
                    & 0x1F001F
                    | ((v9[*((_DWORD *)&g_iYscale + v84) - v82] << 19) + 8 * v9[v85 - v82]) & 0x7E007E0
                    | ((v9[v83 + v85] << 8) + _byteswap_ulong(v9[v83 + *((_DWORD *)&g_iYscale + v84)])) & 0xF800F800;
      v86 = v179[1];
      v87 = v180[1];
      v171 = *((_DWORD *)&g_iVtoR + v87);
      v170 = *((_DWORD *)&g_iVtoG + v87) + *((_DWORD *)&g_iUtoG + v86);
      v88 = *((_DWORD *)&g_iYscale + v11[3]);
      v89 = v11[2];
      v154 = *((_DWORD *)&g_iUtoB + v86);
      *((_DWORD *)v7 + 1) = ((unsigned int)(v9[v154 + *((_DWORD *)&g_iYscale + v89)] + (v9[v154 + v88] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[v88 - v170] << 19) + 8 * v9[*((_DWORD *)&g_iYscale + v89) - v170]) & 0x7E007E0
                          | ((v9[v171 + *((_DWORD *)&g_iYscale + v89)] << 8) + _byteswap_ulong(v9[v171 + v88]))
                          & 0xF800F800;
      v90 = v179[2];
      v91 = v180[2];
      v92 = *((_DWORD *)&g_iVtoR + v91);
      v93 = *((_DWORD *)&g_iVtoG + v91) + *((_DWORD *)&g_iUtoG + v90);
      v94 = v11[5];
      v166 = v93;
      v168 = v92;
      v152 = *((_DWORD *)&g_iUtoB + v90);
      v95 = *((_DWORD *)&g_iYscale + v11[4]);
      *((_DWORD *)v7 + 2) = ((unsigned int)(v9[v152 + v95] + (v9[v152 + *((_DWORD *)&g_iYscale + v94)] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[*((_DWORD *)&g_iYscale + v94) - v93] << 19) + 8 * v9[v95 - v93]) & 0x7E007E0
                          | ((v9[v92 + v95] << 8) + _byteswap_ulong(v9[v92 + *((_DWORD *)&g_iYscale + v94)]))
                          & 0xF800F800;
      v96 = v179[3];
      v97 = v180[3];
      v164 = *((_DWORD *)&g_iVtoR + v97);
      v162 = *((_DWORD *)&g_iVtoG + v97) + *((_DWORD *)&g_iUtoG + v96);
      v98 = *((_DWORD *)&g_iYscale + v11[7]);
      v99 = v11[6];
      v150 = *((_DWORD *)&g_iUtoB + v96);
      *((_DWORD *)v7 + 3) = ((unsigned int)(v9[v150 + *((_DWORD *)&g_iYscale + v99)] + (v9[v150 + v98] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[v98 - v162] << 19) + 8 * v9[*((_DWORD *)&g_iYscale + v99) - v162]) & 0x7E007E0
                          | ((v9[v164 + *((_DWORD *)&g_iYscale + v99)] << 8) + _byteswap_ulong(v9[v164 + v98]))
                          & 0xF800F800;
      v100 = v179[4];
      v101 = v180[4];
      v102 = *((_DWORD *)&g_iVtoR + v101);
      v103 = *((_DWORD *)&g_iVtoG + v101) + *((_DWORD *)&g_iUtoG + v100);
      v104 = v11[9];
      v158 = v103;
      v160 = v102;
      v148 = *((_DWORD *)&g_iUtoB + v100);
      v105 = *((_DWORD *)&g_iYscale + v11[8]);
      *((_DWORD *)v7 + 4) = ((unsigned int)(v9[v148 + v105] + (v9[v148 + *((_DWORD *)&g_iYscale + v104)] << 16)) >> 3)
                          & 0x1F001F
                          | ((v9[*((_DWORD *)&g_iYscale + v104) - v103] << 19) + 8 * v9[v105 - v103]) & 0x7E007E0
                          | ((v9[v102 + v105] << 8) + _byteswap_ulong(v9[v102 + *((_DWORD *)&g_iYscale + v104)]))
                          & 0xF800F800;
      v106 = v180[5];
      v107 = *((_DWORD *)&g_iVtoR + v106);
      v108 = v179[5];
      v109 = *((_DWORD *)&g_iVtoG + v106) + *((_DWORD *)&g_iUtoG + v108);
      v110 = *((_DWORD *)&g_iUtoB + v108);
      v111 = *((_DWORD *)&g_iYscale + v178[11]);
      v112 = *((_DWORD *)&g_iYscale + v178[10]);
      *((_DWORD *)v177 + 5) = ((unsigned int)(v9[v112 + v110] + (v9[v111 + v110] << 16)) >> 3) & 0x1F001F
                            | ((v9[v111 - v109] << 19) + 8 * v9[v112 - v109]) & 0x7E007E0
                            | ((v9[v107 + v112] << 8) + _byteswap_ulong(v9[v107 + v111])) & 0xF800F800;
      v113 = v179[6];
      v114 = v180[6];
      v115 = *((_DWORD *)&g_iVtoG + v114) + *((_DWORD *)&g_iUtoG + v113);
      v116 = *((_DWORD *)&g_iVtoR + v114);
      v117 = *((_DWORD *)&g_iUtoB + v113);
      v118 = *((_DWORD *)&g_iYscale + v178[13]);
      v119 = v178[12];
      *((_DWORD *)v177 + 6) = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v119) + v117]
                                            + (g_rgiClapTabDec[v118 + v117] << 16)) >> 3)
                            & 0x1F001F
                            | ((g_rgiClapTabDec[v118 - v115] << 19)
                             + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v119) - v115])
                            & 0x7E007E0
                            | ((g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v119) + v116] << 8)
                             + _byteswap_ulong(g_rgiClapTabDec[v118 + v116]))
                            & 0xF800F800;
      v120 = v179[7];
      v121 = v180[7];
      v122 = *((_DWORD *)&g_iUtoB + v120);
      v123 = *((_DWORD *)&g_iVtoR + v121);
      v124 = *((_DWORD *)&g_iUtoG + v120) + *((_DWORD *)&g_iVtoG + v121);
      v125 = *((_DWORD *)&g_iYscale + v178[15]);
      v126 = *((_DWORD *)&g_iYscale + v178[14]);
      *((_DWORD *)v177 + 7) = ((unsigned int)(g_rgiClapTabDec[v126 + v122] + (g_rgiClapTabDec[v125 + v122] << 16)) >> 3)
                            & 0x1F001F
                            | ((g_rgiClapTabDec[v125 - v124] << 19) + 8 * g_rgiClapTabDec[v126 - v124]) & 0x7E007E0
                            | ((g_rgiClapTabDec[v123 + v126] << 8) + _byteswap_ulong(g_rgiClapTabDec[v123 + v125]))
                            & 0xF800F800;
      v179 += a6;
      v180 += a6;
      v127 = *((_DWORD *)&g_iYscale + v178[a5 + 1]);
      v128 = v178[a5];
      *(_DWORD *)&v177[a7] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v128) + v156]
                                           + (g_rgiClapTabDec[v127 + v156] << 16)) >> 3)
                           & 0x1F001F
                           | ((g_rgiClapTabDec[v127 - v173] << 19)
                            + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v128) - v173])
                           & 0x7E007E0
                           | ((g_rgiClapTabDec[v175 + *((_DWORD *)&g_iYscale + v128)] << 8)
                            + _byteswap_ulong(g_rgiClapTabDec[v175 + v127]))
                           & 0xF800F800;
      v129 = *((_DWORD *)&g_iYscale + v178[a5 + 3]);
      v130 = v178[a5 + 2];
      *(_DWORD *)&v177[a7 + 4] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v130) + v154]
                                               + (g_rgiClapTabDec[v129 + v154] << 16)) >> 3)
                               & 0x1F001F
                               | ((g_rgiClapTabDec[v129 - v170] << 19)
                                + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v130) - v170])
                               & 0x7E007E0
                               | ((g_rgiClapTabDec[v171 + *((_DWORD *)&g_iYscale + v130)] << 8)
                                + _byteswap_ulong(g_rgiClapTabDec[v171 + v129]))
                               & 0xF800F800;
      v131 = *((_DWORD *)&g_iYscale + v178[a5 + 5]);
      v132 = v178[a5 + 4];
      *(_DWORD *)&v177[a7 + 8] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v132) + v152]
                                               + (g_rgiClapTabDec[v131 + v152] << 16)) >> 3)
                               & 0x1F001F
                               | ((g_rgiClapTabDec[v131 - v166] << 19)
                                + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v132) - v166])
                               & 0x7E007E0
                               | ((g_rgiClapTabDec[v168 + *((_DWORD *)&g_iYscale + v132)] << 8)
                                + _byteswap_ulong(g_rgiClapTabDec[v168 + v131]))
                               & 0xF800F800;
      v133 = *((_DWORD *)&g_iYscale + v178[a5 + 7]);
      v134 = v178[a5 + 6];
      *(_DWORD *)&v177[a7 + 12] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v134) + v150]
                                                + (g_rgiClapTabDec[v133 + v150] << 16)) >> 3)
                                & 0x1F001F
                                | ((g_rgiClapTabDec[v133 - v162] << 19)
                                 + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v134) - v162])
                                & 0x7E007E0
                                | ((g_rgiClapTabDec[v164 + *((_DWORD *)&g_iYscale + v134)] << 8)
                                 + _byteswap_ulong(g_rgiClapTabDec[v164 + v133]))
                                & 0xF800F800;
      v135 = *((_DWORD *)&g_iYscale + v178[a5 + 9]);
      v136 = v178[a5 + 8];
      *(_DWORD *)&v177[a7 + 16] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v136) + v148]
                                                + (g_rgiClapTabDec[v135 + v148] << 16)) >> 3)
                                & 0x1F001F
                                | ((g_rgiClapTabDec[v135 - v158] << 19)
                                 + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v136) - v158])
                                & 0x7E007E0
                                | ((g_rgiClapTabDec[v160 + *((_DWORD *)&g_iYscale + v136)] << 8)
                                 + _byteswap_ulong(g_rgiClapTabDec[v160 + v135]))
                                & 0xF800F800;
      v137 = *((_DWORD *)&g_iYscale + v178[a5 + 11]);
      v138 = *((_DWORD *)&g_iYscale + v178[a5 + 10]);
      LODWORD(v120) = g_rgiClapTabDec[v138 - v109];
      LODWORD(v136) = v137 - v109;
      v139 = g_rgiClapTabDec;
      *(_DWORD *)&v177[a7 + 20] = ((unsigned int)(g_rgiClapTabDec[v138 + v110] + (g_rgiClapTabDec[v137 + v110] << 16)) >> 3)
                                & 0x1F001F
                                | ((g_rgiClapTabDec[(int)v136] << 19) + 8 * v120) & 0x7E007E0
                                | ((g_rgiClapTabDec[v107 + v138] << 8) + _byteswap_ulong(g_rgiClapTabDec[v107 + v137]))
                                & 0xF800F800;
      v140 = *((_DWORD *)&g_iYscale + v178[a5 + 13]);
      v141 = *((_DWORD *)&g_iYscale + v178[a5 + 12]);
      LODWORD(v120) = v139[v141 - v115];
      LODWORD(v136) = v140 - v115;
      v9 = v139;
      *(_DWORD *)&v177[a7 + 24] = ((unsigned int)(v139[v141 + v117] + (v139[v140 + v117] << 16)) >> 3) & 0x1F001F
                                | ((v139[(int)v136] << 19) + 8 * v120) & 0x7E007E0
                                | ((v139[v141 + v116] << 8) + _byteswap_ulong(v139[v140 + v116])) & 0xF800F800;
      v142 = *((_DWORD *)&g_iYscale + v178[a5 + 15]);
      v143 = v178[a5 + 14];
      v11 = &v178[2 * a5];
      v178 = v11;
      v144 = *((_DWORD *)&g_iYscale + v143);
      v145 = v142 + v122;
      LODWORD(v143) = v144 + v122;
      v10 = v179;
      *(_DWORD *)&v177[a7 + 28] = ((unsigned int)(v9[(int)v143] + (v9[v145] << 16)) >> 3) & 0x1F001F
                                | ((v9[v142 - v124] << 19) + 8 * v9[v144 - v124]) & 0x7E007E0
                                | ((v9[v123 + v144] << 8) + _byteswap_ulong(v9[v123 + v142])) & 0xF800F800;
      v7 = &v177[v176];
      v79 = v146-- == 1;
      v177 += v176;
    }
    while ( !v79 );
  }
}

```

## disassembly

```asm
0x180018650  mov     rax, rsp
0x180018653  mov     [rax+20h], r9
0x180018657  mov     [rax+18h], r8
0x18001865b  mov     [rax+10h], rdx
0x18001865f  mov     [rax+8], rcx
0x180018663  push    rbx
0x180018664  push    rbp
0x180018665  push    rsi
0x180018666  push    rdi
0x180018667  push    r12
0x180018669  push    r13
0x18001866b  push    r14
0x18001866d  push    r15
0x18001866f  sub     rsp, 58h
0x180018673  cmp     cs:?g_redscale@@3JA, 7; long g_redscale
0x18001867a  mov     r13, rcx
0x18001867d  movsxd  rcx, [rsp+98h+arg_30]
0x180018685  mov     r14, r9
0x180018688  mov     rbp, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001868f  mov     rdi, r8
0x180018692  mov     r12, rdx
0x180018695  mov     [rsp+98h+var_98], 8
0x18001869c  mov     esi, 1F001Fh
0x1800186a1  lea     rax, [rcx+rcx]
0x1800186a5  mov     [rsp+98h+var_58], rax
0x1800186aa  jnz     loc_180019449
0x1800186b0  lea     r15, __ImageBase
0x1800186b7  movzx   edx, byte ptr [rdi]
0x1800186ba  movzx   eax, byte ptr [r14]
0x1800186be  mov     ebx, rva ?g_iUtoB@@3PAJA[r15+rdx*4]; long near * g_iUtoB ...
0x1800186c6  mov     r11d, rva ?g_iVtoR@@3PAJA[r15+rax*4]; long near * g_iVtoR ...
0x1800186ce  mov     ecx, rva ?g_iUtoG@@3PAJA[r15+rdx*4]; long near * g_iUtoG ...
0x1800186d6  add     ecx, rva ?g_iVtoG@@3PAJA[r15+rax*4]; long near * g_iVtoG ...
0x1800186de  movzx   eax, byte ptr [r12+1]
0x1800186e4  mov     [rsp+98h+var_78], ecx
0x1800186e8  mov     [rsp+98h+var_7C], ebx
0x1800186ec  mov     [rsp+98h+var_80], r11d
0x1800186f1  mov     r8d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x1800186f9  movzx   eax, byte ptr [r12]
0x1800186fe  mov     r9d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018706  mov     eax, r9d
0x180018709  sub     eax, ecx
0x18001870b  cdqe
0x18001870d  movzx   edx, byte ptr [rax+rbp]
0x180018711  mov     eax, r8d
0x180018714  sub     eax, ecx
0x180018716  cdqe
0x180018718  movzx   ecx, byte ptr [rax+rbp]
0x18001871c  lea     eax, [r11+r9]
0x180018720  shl     ecx, 12h
0x180018723  lea     r10d, [rcx+rdx*4]
0x180018727  movsxd  rcx, eax
0x18001872a  and     r10d, 3E003E0h
0x180018731  lea     eax, [r11+r8]
0x180018735  movzx   edx, byte ptr [rcx+rbp]
0x180018739  movsxd  rcx, eax
0x18001873c  shl     edx, 7
0x18001873f  movzx   eax, byte ptr [rcx+rbp]
0x180018743  shl     eax, 17h
0x180018746  add     edx, eax
0x180018748  lea     eax, [rbx+r8]
0x18001874c  movsxd  rcx, eax
0x18001874f  and     edx, 7C007C00h
0x180018755  or      r10d, edx
0x180018758  lea     eax, [rbx+r9]
0x18001875c  movzx   edx, byte ptr [rcx+rbp]
0x180018760  movsxd  rcx, eax
0x180018763  shl     edx, 10h
0x180018766  movzx   eax, byte ptr [rcx+rbp]
0x18001876a  add     edx, eax
0x18001876c  shr     edx, 3
0x18001876f  and     edx, esi
0x180018771  or      r10d, edx
0x180018774  mov     [r13+0], r10d
0x180018778  movzx   edx, byte ptr [rdi+1]
0x18001877c  movzx   eax, byte ptr [r14+1]
0x180018781  mov     ebx, rva ?g_iUtoG@@3PAJA[r15+rdx*4]; long near * g_iUtoG ...
0x180018789  add     ebx, rva ?g_iVtoG@@3PAJA[r15+rax*4]; long near * g_iVtoG ...
0x180018791  mov     r11d, rva ?g_iVtoR@@3PAJA[r15+rax*4]; long near * g_iVtoR ...
0x180018799  movzx   eax, byte ptr [r12+3]
0x18001879f  mov     edi, rva ?g_iUtoB@@3PAJA[r15+rdx*4]; long near * g_iUtoB ...
0x1800187a7  mov     [rsp+98h+var_74], r11d
0x1800187ac  mov     [rsp+98h+var_70], ebx
0x1800187b0  mov     r8d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x1800187b8  movzx   eax, byte ptr [r12+2]
0x1800187be  mov     [rsp+98h+var_94], edi
0x1800187c2  mov     r9d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x1800187ca  lea     eax, [r11+r9]
0x1800187ce  movsxd  rcx, eax
0x1800187d1  lea     eax, [r11+r8]
0x1800187d5  movzx   r10d, byte ptr [rcx+rbp]
0x1800187da  movsxd  rcx, eax
0x1800187dd  shl     r10d, 7
0x1800187e1  movzx   eax, byte ptr [rcx+rbp]
0x1800187e5  shl     eax, 17h
0x1800187e8  add     r10d, eax
0x1800187eb  mov     eax, r9d
0x1800187ee  sub     eax, ebx
0x1800187f0  and     r10d, 7C007C00h
0x1800187f7  cdqe
0x1800187f9  movzx   edx, byte ptr [rax+rbp]
0x1800187fd  mov     eax, r8d
0x180018800  sub     eax, ebx
0x180018802  cdqe
0x180018804  movzx   ecx, byte ptr [rax+rbp]
0x180018808  shl     ecx, 12h
0x18001880b  lea     eax, [rcx+rdx*4]
0x18001880e  and     eax, 3E003E0h
0x180018813  or      r10d, eax
0x180018816  lea     eax, [rdi+r8]
0x18001881a  movsxd  rcx, eax
0x18001881d  lea     eax, [rdi+r9]
0x180018821  movzx   edx, byte ptr [rcx+rbp]
0x180018825  movsxd  rcx, eax
0x180018828  shl     edx, 10h
0x18001882b  movzx   eax, byte ptr [rcx+rbp]
0x18001882f  add     edx, eax
0x180018831  mov     rcx, [rsp+98h+arg_10]
0x180018839  shr     edx, 3
0x18001883c  and     edx, esi
0x18001883e  or      r10d, edx
0x180018841  mov     [r13+4], r10d
0x180018845  movzx   edx, byte ptr [rcx+2]
0x180018849  movzx   eax, byte ptr [r14+2]
0x18001884e  mov     edi, rva ?g_iUtoB@@3PAJA[r15+rdx*4]; long near * g_iUtoB ...
0x180018856  mov     r11d, rva ?g_iVtoR@@3PAJA[r15+rax*4]; long near * g_iVtoR ...
0x18001885e  mov     ebx, rva ?g_iUtoG@@3PAJA[r15+rdx*4]; long near * g_iUtoG ...
0x180018866  add     ebx, rva ?g_iVtoG@@3PAJA[r15+rax*4]; long near * g_iVtoG ...
0x18001886e  movzx   eax, byte ptr [r12+5]
0x180018874  mov     [rsp+98h+var_90], edi
0x180018878  mov     [rsp+98h+var_6C], r11d
0x18001887d  mov     [rsp+98h+var_68], ebx
0x180018881  mov     r8d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018889  movzx   eax, byte ptr [r12+4]
0x18001888f  mov     r9d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018897  lea     eax, [r11+r9]
0x18001889b  movsxd  rcx, eax
0x18001889e  lea     eax, [r11+r8]
0x1800188a2  movzx   r10d, byte ptr [rcx+rbp]
0x1800188a7  movsxd  rcx, eax
0x1800188aa  shl     r10d, 7
0x1800188ae  movzx   eax, byte ptr [rcx+rbp]
0x1800188b2  shl     eax, 17h
0x1800188b5  add     r10d, eax
0x1800188b8  mov     eax, r9d
0x1800188bb  sub     eax, ebx
0x1800188bd  and     r10d, 7C007C00h
0x1800188c4  cdqe
0x1800188c6  movzx   edx, byte ptr [rax+rbp]
0x1800188ca  mov     eax, r8d
0x1800188cd  sub     eax, ebx
0x1800188cf  cdqe
0x1800188d1  movzx   ecx, byte ptr [rax+rbp]
0x1800188d5  shl     ecx, 12h
0x1800188d8  lea     eax, [rcx+rdx*4]
0x1800188db  and     eax, 3E003E0h
0x1800188e0  or      r10d, eax
0x1800188e3  lea     eax, [rdi+r8]
0x1800188e7  movsxd  rcx, eax
0x1800188ea  lea     eax, [rdi+r9]
0x1800188ee  mov     rdi, [rsp+98h+arg_10]
0x1800188f6  movzx   edx, byte ptr [rcx+rbp]
0x1800188fa  movsxd  rcx, eax
0x1800188fd  shl     edx, 10h
0x180018900  movzx   eax, byte ptr [rcx+rbp]
0x180018904  add     edx, eax
0x180018906  shr     edx, 3
0x180018909  and     edx, esi
0x18001890b  or      r10d, edx
0x18001890e  mov     [r13+8], r10d
0x180018912  movzx   edx, byte ptr [rdi+3]
0x180018916  movzx   eax, byte ptr [r14+3]
0x18001891b  mov     ecx, rva ?g_iUtoG@@3PAJA[r15+rdx*4]; long near * g_iUtoG ...
0x180018923  add     ecx, rva ?g_iVtoG@@3PAJA[r15+rax*4]; long near * g_iVtoG ...
0x18001892b  mov     r11d, rva ?g_iVtoR@@3PAJA[r15+rax*4]; long near * g_iVtoR ...
0x180018933  movzx   eax, byte ptr [r12+7]
0x180018939  mov     ebx, rva ?g_iUtoB@@3PAJA[r15+rdx*4]; long near * g_iUtoB ...
0x180018941  mov     [rsp+98h+var_8C], r11d
0x180018946  mov     [rsp+98h+var_64], ecx
0x18001894a  mov     r8d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018952  movzx   eax, byte ptr [r12+6]
0x180018958  mov     [rsp+98h+var_88], ebx
0x18001895c  mov     r9d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018964  mov     eax, r9d
0x180018967  sub     eax, ecx
0x180018969  cdqe
0x18001896b  movzx   edx, byte ptr [rax+rbp]
0x18001896f  mov     eax, r8d
0x180018972  sub     eax, ecx
0x180018974  cdqe
0x180018976  movzx   ecx, byte ptr [rax+rbp]
0x18001897a  lea     eax, [r11+r9]
0x18001897e  shl     ecx, 12h
0x180018981  lea     r10d, [rcx+rdx*4]
0x180018985  movsxd  rcx, eax
0x180018988  and     r10d, 3E003E0h
0x18001898f  lea     eax, [r11+r8]
0x180018993  movzx   edx, byte ptr [rcx+rbp]
0x180018997  movsxd  rcx, eax
0x18001899a  shl     edx, 7
0x18001899d  movzx   eax, byte ptr [rcx+rbp]
0x1800189a1  shl     eax, 17h
0x1800189a4  add     edx, eax
0x1800189a6  lea     eax, [rbx+r8]
0x1800189aa  movsxd  rcx, eax
0x1800189ad  and     edx, 7C007C00h
0x1800189b3  or      r10d, edx
0x1800189b6  lea     eax, [rbx+r9]
0x1800189ba  movzx   edx, byte ptr [rcx+rbp]
0x1800189be  movsxd  rcx, eax
0x1800189c1  shl     edx, 10h
0x1800189c4  movzx   eax, byte ptr [rcx+rbp]
0x1800189c8  add     edx, eax
0x1800189ca  shr     edx, 3
0x1800189cd  and     edx, esi
0x1800189cf  or      r10d, edx
0x1800189d2  mov     [r13+0Ch], r10d
0x1800189d6  movzx   edx, byte ptr [rdi+4]
0x1800189da  movzx   eax, byte ptr [r14+4]
0x1800189df  mov     edi, rva ?g_iUtoB@@3PAJA[r15+rdx*4]; long near * g_iUtoB ...
0x1800189e7  mov     r11d, rva ?g_iVtoR@@3PAJA[r15+rax*4]; long near * g_iVtoR ...
0x1800189ef  mov     ebx, rva ?g_iUtoG@@3PAJA[r15+rdx*4]; long near * g_iUtoG ...
0x1800189f7  add     ebx, rva ?g_iVtoG@@3PAJA[r15+rax*4]; long near * g_iVtoG ...
0x1800189ff  movzx   eax, byte ptr [r12+9]
0x180018a05  mov     [rsp+98h+var_5C], ebx
0x180018a09  mov     [rsp+98h+var_60], r11d
0x180018a0e  mov     [rsp+98h+var_84], edi
0x180018a12  mov     r8d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018a1a  movzx   eax, byte ptr [r12+8]
0x180018a20  mov     r9d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018a28  lea     eax, [r11+r9]
0x180018a2c  movsxd  rcx, eax
0x180018a2f  lea     eax, [r11+r8]
0x180018a33  movzx   r10d, byte ptr [rcx+rbp]
0x180018a38  movsxd  rcx, eax
0x180018a3b  shl     r10d, 7
0x180018a3f  movzx   eax, byte ptr [rcx+rbp]
0x180018a43  shl     eax, 17h
0x180018a46  add     r10d, eax
0x180018a49  mov     eax, r9d
0x180018a4c  sub     eax, ebx
0x180018a4e  and     r10d, 7C007C00h
0x180018a55  cdqe
0x180018a57  movzx   edx, byte ptr [rax+rbp]
0x180018a5b  mov     eax, r8d
0x180018a5e  sub     eax, ebx
0x180018a60  mov     ebx, 3E003E0h
0x180018a65  cdqe
0x180018a67  movzx   ecx, byte ptr [rax+rbp]
0x180018a6b  shl     ecx, 12h
0x180018a6e  lea     eax, [rcx+rdx*4]
0x180018a71  and     eax, ebx
0x180018a73  or      r10d, eax
0x180018a76  lea     eax, [rdi+r8]
0x180018a7a  movsxd  rcx, eax
0x180018a7d  lea     eax, [rdi+r9]
0x180018a81  movzx   edx, byte ptr [rcx+rbp]
0x180018a85  shl     edx, 10h
0x180018a88  movsxd  rcx, eax
0x180018a8b  movzx   eax, byte ptr [rcx+rbp]
0x180018a8f  mov     rcx, [rsp+98h+arg_10]
0x180018a97  add     edx, eax
0x180018a99  shr     edx, 3
0x180018a9c  and     edx, esi
0x180018a9e  or      r10d, edx
0x180018aa1  mov     [r13+10h], r10d
0x180018aa5  movzx   eax, byte ptr [r14+5]
0x180018aaa  movzx   edx, byte ptr [rcx+5]
0x180018aae  mov     r12d, rva ?g_iVtoR@@3PAJA[r15+rax*4]; long near * g_iVtoR ...
0x180018ab6  mov     r14d, rva ?g_iUtoG@@3PAJA[r15+rdx*4]; long near * g_iUtoG ...
0x180018abe  add     r14d, rva ?g_iVtoG@@3PAJA[r15+rax*4]; long near * g_iVtoG ...
0x180018ac6  mov     r13d, rva ?g_iUtoB@@3PAJA[r15+rdx*4]; long near * g_iUtoB ...
0x180018ace  mov     r11, [rsp+98h+arg_8]
0x180018ad6  mov     rdi, [rsp+98h+arg_18]
0x180018ade  movzx   eax, byte ptr [r11+0Bh]
0x180018ae3  mov     r8d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018aeb  movzx   eax, byte ptr [r11+0Ah]
0x180018af0  mov     r9d, rva ?g_iYscale@@3PAJA[r15+rax*4]; long near * g_iYscale ...
0x180018af8  mov     eax, r9d
0x180018afb  sub     eax, r14d
0x180018afe  cdqe
0x180018b00  movzx   edx, byte ptr [rax+rbp]
0x180018b04  mov     eax, r8d
0x180018b07  sub     eax, r14d
0x180018b0a  cdqe
0x180018b0c  movzx   ecx, byte ptr [rax+rbp]
0x180018b10  lea     eax, [r12+r9]
0x180018b14  shl     ecx, 12h
0x180018b17  lea     r10d, [rcx+rdx*4]
0x180018b1b  movsxd  rcx, eax
0x180018b1e  and     r10d, ebx
0x180018b21  lea     eax, [r12+r8]
0x180018b25  mov     rbx, [rsp+98h+arg_0]
0x180018b2d  movzx   edx, byte ptr [rcx+rbp]
0x180018b31  movsxd  rcx, eax
0x180018b34  shl     edx, 7
0x180018b37  movzx   eax, byte ptr [rcx+rbp]
0x180018b3b  shl     eax, 17h
0x180018b3e  add     edx, eax
0x180018b40  lea     eax, [r8+r13]
  ... truncated ...
```

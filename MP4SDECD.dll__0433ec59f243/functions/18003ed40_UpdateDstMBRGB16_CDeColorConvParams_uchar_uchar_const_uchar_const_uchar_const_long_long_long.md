# UpdateDstMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003ed40`
- end: `0x1800408a4`
- name: `?UpdateDstMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `7012`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180043120`

## callees

- `0x18003ed40`

## pseudocode

```c
void __fastcall UpdateDstMBRGB16(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  unsigned __int8 *v8; // r13
  const unsigned __int8 *v9; // r14
  __int64 v10; // rbp
  const unsigned __int8 *v11; // r12
  const unsigned __int8 *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // r11d
  int v16; // ecx
  __int64 v17; // rax
  int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // r8d
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  int v25; // r11d
  int v26; // ebx
  __int64 v27; // rax
  int v28; // r9d
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // ecx
  int v32; // r8d
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rax
  int v36; // r11d
  int v37; // ebx
  __int64 v38; // rax
  int v39; // r9d
  __int64 v40; // rax
  __int64 v41; // rdx
  int v42; // r12d
  int v43; // r14d
  int v44; // r13d
  int v45; // r8d
  int v46; // r9d
  __int64 v47; // rax
  int v48; // esi
  __int64 v49; // rdx
  int v50; // ebp
  int v51; // r15d
  int v52; // r8d
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdx
  int v56; // ebx
  int v57; // edi
  int v58; // r11d
  int v59; // r8d
  __int64 v60; // rax
  int v61; // r8d
  int v62; // r9d
  int v63; // r8d
  __int64 v64; // rax
  int v65; // r8d
  __int64 v66; // rax
  int v67; // r8d
  int v68; // r9d
  int v69; // r8d
  __int64 v70; // rax
  int v71; // r8d
  int v72; // r9d
  __int64 v73; // r12
  int v74; // r8d
  int v75; // r9d
  int v76; // r8d
  __int64 v77; // rax
  int v78; // r9d
  __int64 v79; // rcx
  bool v80; // zf
  const unsigned __int8 *v81; // rax
  __int64 v82; // rax
  __int64 v83; // rdx
  int v84; // ebx
  __int64 v85; // rax
  int v86; // r9d
  __int64 v87; // rax
  __int64 v88; // rdx
  int v89; // r8d
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rdx
  int v93; // r11d
  int v94; // ebx
  __int64 v95; // rax
  int v96; // r9d
  __int64 v97; // rax
  __int64 v98; // rdx
  int v99; // r8d
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rdx
  int v103; // r11d
  int v104; // ebx
  __int64 v105; // rax
  int v106; // r9d
  __int64 v107; // rax
  int v108; // r15d
  __int64 v109; // rdx
  int v110; // r12d
  int v111; // r13d
  int v112; // r8d
  int v113; // r9d
  __int64 v114; // rax
  __int64 v115; // rdx
  int v116; // esi
  int v117; // ebp
  int v118; // r14d
  int v119; // r8d
  __int64 v120; // rax
  __int64 v121; // rcx
  __int64 v122; // rdx
  int v123; // r11d
  int v124; // ebx
  int v125; // edi
  int v126; // r8d
  int v127; // r9d
  int v128; // r8d
  __int64 v129; // rax
  int v130; // r8d
  __int64 v131; // rax
  int v132; // r8d
  __int64 v133; // rax
  int v134; // r8d
  __int64 v135; // rax
  int v136; // r8d
  __int64 v137; // rax
  int v138; // r8d
  int v139; // r9d
  __int64 v140; // r12
  int v141; // r8d
  int v142; // r9d
  int v143; // r8d
  __int64 v144; // rax
  const unsigned __int8 *v145; // [rsp+0h] [rbp-98h]
  const unsigned __int8 *v146; // [rsp+0h] [rbp-98h]
  int v147; // [rsp+8h] [rbp-90h]
  int v148; // [rsp+8h] [rbp-90h]
  int v149; // [rsp+Ch] [rbp-8Ch]
  int v150; // [rsp+Ch] [rbp-8Ch]
  int v151; // [rsp+10h] [rbp-88h]
  int v152; // [rsp+10h] [rbp-88h]
  int v153; // [rsp+14h] [rbp-84h]
  int v154; // [rsp+14h] [rbp-84h]
  int v155; // [rsp+18h] [rbp-80h]
  int v156; // [rsp+18h] [rbp-80h]
  int v157; // [rsp+1Ch] [rbp-7Ch]
  int v158; // [rsp+1Ch] [rbp-7Ch]
  int v159; // [rsp+20h] [rbp-78h]
  int v160; // [rsp+20h] [rbp-78h]
  int v161; // [rsp+24h] [rbp-74h]
  int v162; // [rsp+24h] [rbp-74h]
  int v163; // [rsp+28h] [rbp-70h]
  int v164; // [rsp+28h] [rbp-70h]
  int v165; // [rsp+2Ch] [rbp-6Ch]
  int v166; // [rsp+2Ch] [rbp-6Ch]
  int v167; // [rsp+30h] [rbp-68h]
  int v168; // [rsp+30h] [rbp-68h]
  int v169; // [rsp+34h] [rbp-64h]
  int v170; // [rsp+34h] [rbp-64h]
  int v171; // [rsp+38h] [rbp-60h]
  int v172; // [rsp+3Ch] [rbp-5Ch]
  int v173; // [rsp+3Ch] [rbp-5Ch]
  int v174; // [rsp+40h] [rbp-58h]
  int v175; // [rsp+40h] [rbp-58h]
  __int64 v176; // [rsp+48h] [rbp-50h]
  int v177; // [rsp+A0h] [rbp+8h]
  unsigned __int8 *v178; // [rsp+A8h] [rbp+10h]
  const unsigned __int8 *v179; // [rsp+B0h] [rbp+18h]
  const unsigned __int8 *v180; // [rsp+B8h] [rbp+20h]

  v180 = a4;
  v179 = a3;
  v178 = a2;
  v8 = a2;
  v9 = a4;
  v10 = g_rgiClapTabDec;
  v11 = a3;
  v177 = 8;
  v176 = 2LL * a8;
  if ( *((_DWORD *)a1 + 26) == 7 )
  {
    v12 = a5;
    v145 = a5;
    do
    {
      v13 = *v9;
      v14 = *v12;
      v15 = g_iVtoR[v14];
      v16 = g_iVtoG[v14] + g_iUtoG[v13];
      v17 = v11[1];
      v161 = v16;
      v159 = g_iUtoB[v13];
      v157 = v15;
      v18 = g_iYscale[*v11];
      *(_DWORD *)v8 = ((unsigned int)(*(unsigned __int8 *)(v159 + v18 + v10)
                                    + (*(unsigned __int8 *)(v159 + g_iYscale[v17] + v10) << 16)) >> 3)
                    & 0x1F001F
                    | ((*(unsigned __int8 *)(v15 + g_iYscale[v17] + v10) << 23)
                     + (*(unsigned __int8 *)(v15 + v18 + v10) << 7))
                    & 0x7C007C00
                    | ((*(unsigned __int8 *)(g_iYscale[v17] - v16 + v10) << 18)
                     + 4 * *(unsigned __int8 *)(v18 - v16 + v10))
                    & 0x3E003E0;
      v19 = v12[1];
      v20 = v9[1];
      v163 = g_iVtoR[v19];
      v165 = g_iVtoG[v19] + g_iUtoG[v20];
      v21 = g_iYscale[v11[3]];
      v22 = v11[2];
      v147 = g_iUtoB[v20];
      *((_DWORD *)v8 + 1) = ((unsigned int)(*(unsigned __int8 *)(v147 + g_iYscale[v22] + v10)
                                          + (*(unsigned __int8 *)(v147 + v21 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v21 - v165 + v10) << 18)
                           + 4 * *(unsigned __int8 *)(g_iYscale[v22] - v165 + v10))
                          & 0x3E003E0
                          | ((*(unsigned __int8 *)(v163 + v21 + v10) << 23)
                           + (*(unsigned __int8 *)(v163 + g_iYscale[v22] + v10) << 7))
                          & 0x7C007C00;
      v23 = v145[2];
      v24 = v9[2];
      v25 = g_iVtoR[v23];
      v26 = g_iVtoG[v23] + g_iUtoG[v24];
      v27 = v11[5];
      v149 = g_iUtoB[v24];
      v167 = v25;
      v169 = v26;
      v28 = g_iYscale[v11[4]];
      *((_DWORD *)v8 + 2) = ((unsigned int)(*(unsigned __int8 *)(v149 + v28 + v10)
                                          + (*(unsigned __int8 *)(v149 + g_iYscale[v27] + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(g_iYscale[v27] - v26 + v10) << 18)
                           + 4 * *(unsigned __int8 *)(v28 - v26 + v10))
                          & 0x3E003E0
                          | ((*(unsigned __int8 *)(v25 + g_iYscale[v27] + v10) << 23)
                           + (*(unsigned __int8 *)(v25 + v28 + v10) << 7))
                          & 0x7C007C00;
      v29 = v9[3];
      v30 = v145[3];
      v31 = g_iVtoG[v30] + g_iUtoG[v29];
      v151 = g_iVtoR[v30];
      v32 = g_iYscale[v11[7]];
      v33 = v11[6];
      v153 = g_iUtoB[v29];
      *((_DWORD *)v8 + 3) = ((unsigned int)(*(unsigned __int8 *)(v153 + g_iYscale[v33] + v10)
                                          + (*(unsigned __int8 *)(v153 + v32 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v151 + v32 + v10) << 23)
                           + (*(unsigned __int8 *)(v151 + g_iYscale[v33] + v10) << 7))
                          & 0x7C007C00
                          | ((*(unsigned __int8 *)(v32 - v31 + v10) << 18)
                           + 4 * *(unsigned __int8 *)(g_iYscale[v33] - v31 + v10))
                          & 0x3E003E0;
      v34 = v9[4];
      v35 = v145[4];
      v36 = g_iVtoR[v35];
      v37 = g_iVtoG[v35] + g_iUtoG[v34];
      v38 = v11[9];
      v174 = v37;
      v155 = g_iUtoB[v34];
      v172 = v36;
      v39 = g_iYscale[v11[8]];
      *((_DWORD *)v8 + 4) = ((unsigned int)(*(unsigned __int8 *)(v155 + v39 + v10)
                                          + (*(unsigned __int8 *)(v155 + g_iYscale[v38] + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(g_iYscale[v38] - v37 + v10) << 18)
                           + 4 * *(unsigned __int8 *)(v39 - v37 + v10))
                          & 0x3E003E0
                          | ((*(unsigned __int8 *)(v36 + g_iYscale[v38] + v10) << 23)
                           + (*(unsigned __int8 *)(v36 + v39 + v10) << 7))
                          & 0x7C007C00;
      v40 = v145[5];
      v41 = v9[5];
      v42 = g_iVtoR[v40];
      v43 = g_iVtoG[v40] + g_iUtoG[v41];
      v44 = g_iUtoB[v41];
      v45 = g_iYscale[v179[11]];
      v46 = g_iYscale[v179[10]];
      *((_DWORD *)v178 + 5) = ((unsigned int)(*(unsigned __int8 *)(v46 + v44 + v10)
                                            + (*(unsigned __int8 *)(v45 + v44 + v10) << 16)) >> 3)
                            & 0x1F001F
                            | ((*(unsigned __int8 *)(v42 + v45 + v10) << 23)
                             + (*(unsigned __int8 *)(v42 + v46 + v10) << 7))
                            & 0x7C007C00
                            | ((*(unsigned __int8 *)(v45 - v43 + v10) << 18) + 4 * *(unsigned __int8 *)(v46 - v43 + v10))
                            & 0x3E003E0;
      v47 = v145[6];
      v48 = g_iVtoR[v47];
      v49 = v180[6];
      v50 = g_iVtoG[v47] + g_iUtoG[v49];
      v51 = g_iUtoB[v49];
      v52 = g_iYscale[v179[13]];
      v53 = v179[12];
      *((_DWORD *)v178 + 6) = ((unsigned int)(*(unsigned __int8 *)(v51 + g_iYscale[v53] + g_rgiClapTabDec)
                                            + (*(unsigned __int8 *)(v51 + v52 + g_rgiClapTabDec) << 16)) >> 3)
                            & 0x1F001F
                            | ((*(unsigned __int8 *)(v52 - v50 + g_rgiClapTabDec) << 18)
                             + 4 * *(unsigned __int8 *)(g_iYscale[v53] - v50 + g_rgiClapTabDec))
                            & 0x3E003E0
                            | ((*(unsigned __int8 *)(v48 + v52 + g_rgiClapTabDec) << 23)
                             + (*(unsigned __int8 *)(v48 + g_iYscale[v53] + g_rgiClapTabDec) << 7))
                            & 0x7C007C00;
      v54 = v145[7];
      v55 = v180[7];
      v56 = g_iVtoR[v54];
      v57 = g_iUtoB[v55];
      v58 = g_iVtoG[v54] + g_iUtoG[v55];
      v59 = g_iYscale[v179[15]];
      v60 = v179[14];
      *((_DWORD *)v178 + 7) = ((unsigned int)(*(unsigned __int8 *)(v57 + g_iYscale[v60] + g_rgiClapTabDec)
                                            + (*(unsigned __int8 *)(v57 + v59 + g_rgiClapTabDec) << 16)) >> 3)
                            & 0x1F001F
                            | ((*(unsigned __int8 *)(v56 + v59 + g_rgiClapTabDec) << 23)
                             + (*(unsigned __int8 *)(v56 + g_iYscale[v60] + g_rgiClapTabDec) << 7))
                            & 0x7C007C00
                            | ((*(unsigned __int8 *)(v59 - v58 + g_rgiClapTabDec) << 18)
                             + 4 * *(unsigned __int8 *)(g_iYscale[v60] - v58 + g_rgiClapTabDec))
                            & 0x3E003E0;
      v180 += a7;
      v145 += a7;
      v61 = g_iYscale[v179[a6 + 1]];
      v62 = g_iYscale[v179[a6]];
      *(_DWORD *)&v178[a8] = ((unsigned int)(*(unsigned __int8 *)(v62 + v159 + g_rgiClapTabDec)
                                           + (*(unsigned __int8 *)(v61 + v159 + g_rgiClapTabDec) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v61 + v157 + g_rgiClapTabDec) << 23)
                            + (*(unsigned __int8 *)(v62 + v157 + g_rgiClapTabDec) << 7))
                           & 0x7C007C00
                           | ((*(unsigned __int8 *)(v61 - v161 + g_rgiClapTabDec) << 18)
                            + 4 * *(unsigned __int8 *)(v62 - v161 + g_rgiClapTabDec))
                           & 0x3E003E0;
      v63 = g_iYscale[v179[a6 + 3]];
      v64 = v179[a6 + 2];
      *(_DWORD *)&v178[a8 + 4] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v64] + v147 + g_rgiClapTabDec)
                                               + (*(unsigned __int8 *)(v63 + v147 + g_rgiClapTabDec) << 16)) >> 3)
                               & 0x1F001F
                               | ((*(unsigned __int8 *)(v63 - v165 + g_rgiClapTabDec) << 18)
                                + 4 * *(unsigned __int8 *)(g_iYscale[v64] - v165 + g_rgiClapTabDec))
                               & 0x3E003E0
                               | ((*(unsigned __int8 *)(v163 + v63 + g_rgiClapTabDec) << 23)
                                + (*(unsigned __int8 *)(v163 + g_iYscale[v64] + g_rgiClapTabDec) << 7))
                               & 0x7C007C00;
      v65 = g_iYscale[v179[a6 + 5]];
      v66 = v179[a6 + 4];
      *(_DWORD *)&v178[a8 + 8] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v66] + v149 + g_rgiClapTabDec)
                                               + (*(unsigned __int8 *)(v65 + v149 + g_rgiClapTabDec) << 16)) >> 3)
                               & 0x1F001F
                               | ((*(unsigned __int8 *)(v65 - v169 + g_rgiClapTabDec) << 18)
                                + 4 * *(unsigned __int8 *)(g_iYscale[v66] - v169 + g_rgiClapTabDec))
                               & 0x3E003E0
                               | ((*(unsigned __int8 *)(v167 + v65 + g_rgiClapTabDec) << 23)
                                + (*(unsigned __int8 *)(v167 + g_iYscale[v66] + g_rgiClapTabDec) << 7))
                               & 0x7C007C00;
      v67 = g_iYscale[v179[a6 + 7]];
      v68 = g_iYscale[v179[a6 + 6]];
      *(_DWORD *)&v178[a8 + 12] = ((unsigned int)(*(unsigned __int8 *)(v68 + v153 + g_rgiClapTabDec)
                                                + (*(unsigned __int8 *)(v67 + v153 + g_rgiClapTabDec) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)(v67 + v151 + g_rgiClapTabDec) << 23)
                                 + (*(unsigned __int8 *)(v68 + v151 + g_rgiClapTabDec) << 7))
                                & 0x7C007C00
                                | ((*(unsigned __int8 *)(v67 - v31 + g_rgiClapTabDec) << 18)
                                 + 4 * *(unsigned __int8 *)(v68 - v31 + g_rgiClapTabDec))
                                & 0x3E003E0;
      v69 = g_iYscale[v179[a6 + 9]];
      v70 = v179[a6 + 8];
      *(_DWORD *)&v178[a8 + 16] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v70] + v155 + g_rgiClapTabDec)
                                                + (*(unsigned __int8 *)(v69 + v155 + g_rgiClapTabDec) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)(v69 - v174 + g_rgiClapTabDec) << 18)
                                 + 4 * *(unsigned __int8 *)(g_iYscale[v70] - v174 + g_rgiClapTabDec))
                                & 0x3E003E0
                                | ((*(unsigned __int8 *)(v172 + v69 + g_rgiClapTabDec) << 23)
                                 + (*(unsigned __int8 *)(v172 + g_iYscale[v70] + g_rgiClapTabDec) << 7))
                                & 0x7C007C00;
      v71 = g_iYscale[v179[a6 + 11]];
      v72 = g_iYscale[v179[a6 + 10]];
      LODWORD(v55) = *(unsigned __int8 *)(v42 + v72 + g_rgiClapTabDec);
      LODWORD(v70) = v42 + v71;
      v73 = g_rgiClapTabDec;
      *(_DWORD *)&v178[a8 + 20] = ((unsigned int)(*(unsigned __int8 *)(v72 + v44 + g_rgiClapTabDec)
                                                + (*(unsigned __int8 *)(v71 + v44 + g_rgiClapTabDec) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)((int)v70 + g_rgiClapTabDec) << 23) + ((_DWORD)v55 << 7))
                                & 0x7C007C00
                                | ((*(unsigned __int8 *)(v71 - v43 + g_rgiClapTabDec) << 18)
                                 + 4 * *(unsigned __int8 *)(v72 - v43 + g_rgiClapTabDec))
                                & 0x3E003E0;
      v74 = g_iYscale[v179[a6 + 13]];
      v75 = g_iYscale[v179[a6 + 12]];
      LODWORD(v55) = *(unsigned __int8 *)(v75 - v50 + v73);
      LODWORD(v70) = v74 - v50;
      v10 = v73;
      *(_DWORD *)&v178[a8 + 24] = ((unsigned int)(*(unsigned __int8 *)(v51 + v75 + v73)
                                                + (*(unsigned __int8 *)(v51 + v74 + v73) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)((int)v70 + v73) << 18) + 4 * v55) & 0x3E003E0
                                | ((*(unsigned __int8 *)(v48 + v74 + v73) << 23)
                                 + (*(unsigned __int8 *)(v48 + v75 + v73) << 7))
                                & 0x7C007C00;
      v76 = g_iYscale[v179[a6 + 15]];
      v77 = v179[a6 + 14];
      v11 = &v179[2 * a6];
      v9 = v180;
      v179 = v11;
      v78 = g_iYscale[v77];
      v79 = v57 + v76;
      LODWORD(v77) = v57 + v78;
      v12 = v145;
      *(_DWORD *)&v178[a8 + 28] = ((unsigned int)(*(unsigned __int8 *)((int)v77 + v10)
                                                + (*(unsigned __int8 *)(v79 + v10) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)(v56 + v76 + v10) << 23)
                                 + (*(unsigned __int8 *)(v56 + v78 + v10) << 7))
                                & 0x7C007C00
                                | ((*(unsigned __int8 *)(v76 - v58 + v10) << 18)
                                 + 4 * *(unsigned __int8 *)(v78 - v58 + v10))
                                & 0x3E003E0;
      v8 = &v178[v176];
      v80 = v177-- == 1;
      v178 += v176;
    }
    while ( !v80 );
  }
  else
  {
    v81 = a5;
    v146 = a5;
    do
    {
      v82 = *v81;
      v83 = *v180;
      v175 = g_iVtoR[v82];
      v84 = g_iVtoG[v82] + g_iUtoG[v83];
      v85 = v11[1];
      v173 = v84;
      v156 = g_iUtoB[v83];
      v86 = g_iYscale[*v11];
      *(_DWORD *)v8 = ((unsigned int)(*(unsigned __int8 *)(v156 + v86 + v10)
                                    + (*(unsigned __int8 *)(v156 + g_iYscale[v85] + v10) << 16)) >> 3)
                    & 0x1F001F
                    | ((*(unsigned __int8 *)(g_iYscale[v85] - v84 + v10) << 19)
                     + 8 * *(unsigned __int8 *)(v86 - v84 + v10))
                    & 0x7E007E0
                    | ((*(unsigned __int8 *)(v175 + v86 + v10) << 8)
                     + _byteswap_ulong(*(unsigned __int8 *)(v175 + g_iYscale[v85] + v10)))
                    & 0xF800F800;
      v87 = v146[1];
      v88 = v180[1];
      v171 = g_iVtoR[v87];
      v170 = g_iVtoG[v87] + g_iUtoG[v88];
      v89 = g_iYscale[v11[3]];
      v90 = v11[2];
      v154 = g_iUtoB[v88];
      *((_DWORD *)v8 + 1) = ((unsigned int)(*(unsigned __int8 *)(v154 + g_iYscale[v90] + v10)
                                          + (*(unsigned __int8 *)(v154 + v89 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v89 - v170 + v10) << 19)
                           + 8 * *(unsigned __int8 *)(g_iYscale[v90] - v170 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v171 + g_iYscale[v90] + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v171 + v89 + v10)))
                          & 0xF800F800;
      v91 = v146[2];
      v92 = v180[2];
      v93 = g_iVtoR[v91];
      v94 = g_iVtoG[v91] + g_iUtoG[v92];
      v95 = v11[5];
      v166 = v94;
      v168 = v93;
      v152 = g_iUtoB[v92];
      v96 = g_iYscale[v11[4]];
      *((_DWORD *)v8 + 2) = ((unsigned int)(*(unsigned __int8 *)(v152 + v96 + v10)
                                          + (*(unsigned __int8 *)(v152 + g_iYscale[v95] + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(g_iYscale[v95] - v94 + v10) << 19)
                           + 8 * *(unsigned __int8 *)(v96 - v94 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v93 + v96 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v93 + g_iYscale[v95] + v10)))
                          & 0xF800F800;
      v97 = v146[3];
      v98 = v180[3];
      v164 = g_iVtoR[v97];
      v162 = g_iVtoG[v97] + g_iUtoG[v98];
      v99 = g_iYscale[v11[7]];
      v100 = v11[6];
      v150 = g_iUtoB[v98];
      *((_DWORD *)v8 + 3) = ((unsigned int)(*(unsigned __int8 *)(v150 + g_iYscale[v100] + v10)
                                          + (*(unsigned __int8 *)(v150 + v99 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v99 - v162 + v10) << 19)
                           + 8 * *(unsigned __int8 *)(g_iYscale[v100] - v162 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v164 + g_iYscale[v100] + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v164 + v99 + v10)))
                          & 0xF800F800;
      v101 = v146[4];
      v102 = v180[4];
      v103 = g_iVtoR[v101];
      v104 = g_iVtoG[v101] + g_iUtoG[v102];
      v105 = v11[9];
      v158 = v104;
      v160 = v103;
      v148 = g_iUtoB[v102];
      v106 = g_iYscale[v11[8]];
      *((_DWORD *)v8 + 4) = ((unsigned int)(*(unsigned __int8 *)(v148 + v106 + v10)
                                          + (*(unsigned __int8 *)(v148 + g_iYscale[v105] + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(g_iYscale[v105] - v104 + v10) << 19)
                           + 8 * *(unsigned __int8 *)(v106 - v104 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v103 + v106 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v103 + g_iYscale[v105] + v10)))
                          & 0xF800F800;
      v107 = v146[5];
      v108 = g_iVtoR[v107];
      v109 = v180[5];
      v110 = g_iVtoG[v107] + g_iUtoG[v109];
      v111 = g_iUtoB[v109];
      v112 = g_iYscale[v179[11]];
      v113 = g_iYscale[v179[10]];
      *((_DWORD *)v178 + 5) = ((unsigned int)(*(unsigned __int8 *)(v113 + v111 + v10)
                                            + (*(unsigned __int8 *)(v112 + v111 + v10) << 16)) >> 3)
                            & 0x1F001F
                            | ((*(unsigned __int8 *)(v112 - v110 + v10) << 19)
                             + 8 * *(unsigned __int8 *)(v113 - v110 + v10))
                            & 0x7E007E0
                            | ((*(unsigned __int8 *)(v108 + v113 + v10) << 8)
                             + _byteswap_ulong(*(unsigned __int8 *)(v108 + v112 + v10)))
                            & 0xF800F800;
      v114 = v146[6];
      v115 = v180[6];
      v116 = g_iVtoR[v114];
      v117 = g_iVtoG[v114] + g_iUtoG[v115];
      v118 = g_iUtoB[v115];
      v119 = g_iYscale[v179[13]];
      v120 = v179[12];
      *((_DWORD *)v178 + 6) = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v120] + v118 + g_rgiClapTabDec)
                                            + (*(unsigned __int8 *)(v119 + v118 + g_rgiClapTabDec) << 16)) >> 3)
                            & 0x1F001F
                            | ((*(unsigned __int8 *)(v119 - v117 + g_rgiClapTabDec) << 19)
                             + 8 * *(unsigned __int8 *)(g_iYscale[v120] - v117 + g_rgiClapTabDec))
                            & 0x7E007E0
                            | ((*(unsigned __int8 *)(g_iYscale[v120] + v116 + g_rgiClapTabDec) << 8)
                             + _byteswap_ulong(*(unsigned __int8 *)(v119 + v116 + g_rgiClapTabDec)))
                            & 0xF800F800;
      v121 = v146[7];
      v122 = v180[7];
      v123 = g_iVtoR[v121];
      v124 = g_iUtoG[v122] + g_iVtoG[v121];
      v125 = g_iUtoB[v122];
      v126 = g_iYscale[v179[15]];
      v127 = g_iYscale[v179[14]];
      *((_DWORD *)v178 + 7) = ((unsigned int)(*(unsigned __int8 *)(v127 + v125 + g_rgiClapTabDec)
                                            + (*(unsigned __int8 *)(v126 + v125 + g_rgiClapTabDec) << 16)) >> 3)
                            & 0x1F001F
                            | ((*(unsigned __int8 *)(v126 - v124 + g_rgiClapTabDec) << 19)
                             + 8 * *(unsigned __int8 *)(v127 - v124 + g_rgiClapTabDec))
                            & 0x7E007E0
                            | ((*(unsigned __int8 *)(v123 + v127 + g_rgiClapTabDec) << 8)
                             + _byteswap_ulong(*(unsigned __int8 *)(v123 + v126 + g_rgiClapTabDec)))
                            & 0xF800F800;
      v180 += a7;
      v146 += a7;
      v128 = g_iYscale[v179[a6 + 1]];
      v129 = v179[a6];
      *(_DWORD *)&v178[a8] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v129] + v156 + g_rgiClapTabDec)
                                           + (*(unsigned __int8 *)(v128 + v156 + g_rgiClapTabDec) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v128 - v173 + g_rgiClapTabDec) << 19)
                            + 8 * *(unsigned __int8 *)(g_iYscale[v129] - v173 + g_rgiClapTabDec))
                           & 0x7E007E0
                           | ((*(unsigned __int8 *)(v175 + g_iYscale[v129] + g_rgiClapTabDec) << 8)
                            + _byteswap_ulong(*(unsigned __int8 *)(v175 + v128 + g_rgiClapTabDec)))
                           & 0xF800F800;
      v130 = g_iYscale[v179[a6 + 3]];
      v131 = v179[a6 + 2];
      *(_DWORD *)&v178[a8 + 4] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v131] + v154 + g_rgiClapTabDec)
                                               + (*(unsigned __int8 *)(v130 + v154 + g_rgiClapTabDec) << 16)) >> 3)
                               & 0x1F001F
                               | ((*(unsigned __int8 *)(v130 - v170 + g_rgiClapTabDec) << 19)
                                + 8 * *(unsigned __int8 *)(g_iYscale[v131] - v170 + g_rgiClapTabDec))
                               & 0x7E007E0
                               | ((*(unsigned __int8 *)(v171 + g_iYscale[v131] + g_rgiClapTabDec) << 8)
                                + _byteswap_ulong(*(unsigned __int8 *)(v171 + v130 + g_rgiClapTabDec)))
                               & 0xF800F800;
      v132 = g_iYscale[v179[a6 + 5]];
      v133 = v179[a6 + 4];
      *(_DWORD *)&v178[a8 + 8] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v133] + v152 + g_rgiClapTabDec)
                                               + (*(unsigned __int8 *)(v132 + v152 + g_rgiClapTabDec) << 16)) >> 3)
                               & 0x1F001F
                               | ((*(unsigned __int8 *)(v132 - v166 + g_rgiClapTabDec) << 19)
                                + 8 * *(unsigned __int8 *)(g_iYscale[v133] - v166 + g_rgiClapTabDec))
                               & 0x7E007E0
                               | ((*(unsigned __int8 *)(v168 + g_iYscale[v133] + g_rgiClapTabDec) << 8)
                                + _byteswap_ulong(*(unsigned __int8 *)(v168 + v132 + g_rgiClapTabDec)))
                               & 0xF800F800;
      v134 = g_iYscale[v179[a6 + 7]];
      v135 = v179[a6 + 6];
      *(_DWORD *)&v178[a8 + 12] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v135] + v150 + g_rgiClapTabDec)
                                                + (*(unsigned __int8 *)(v134 + v150 + g_rgiClapTabDec) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)(v134 - v162 + g_rgiClapTabDec) << 19)
                                 + 8 * *(unsigned __int8 *)(g_iYscale[v135] - v162 + g_rgiClapTabDec))
                                & 0x7E007E0
                                | ((*(unsigned __int8 *)(v164 + g_iYscale[v135] + g_rgiClapTabDec) << 8)
                                 + _byteswap_ulong(*(unsigned __int8 *)(v164 + v134 + g_rgiClapTabDec)))
                                & 0xF800F800;
      v136 = g_iYscale[v179[a6 + 9]];
      v137 = v179[a6 + 8];
      *(_DWORD *)&v178[a8 + 16] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v137] + v148 + g_rgiClapTabDec)
                                                + (*(unsigned __int8 *)(v136 + v148 + g_rgiClapTabDec) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)(v136 - v158 + g_rgiClapTabDec) << 19)
                                 + 8 * *(unsigned __int8 *)(g_iYscale[v137] - v158 + g_rgiClapTabDec))
                                & 0x7E007E0
                                | ((*(unsigned __int8 *)(v160 + g_iYscale[v137] + g_rgiClapTabDec) << 8)
                                 + _byteswap_ulong(*(unsigned __int8 *)(v160 + v136 + g_rgiClapTabDec)))
                                & 0xF800F800;
      v138 = g_iYscale[v179[a6 + 11]];
      v139 = g_iYscale[v179[a6 + 10]];
      LODWORD(v122) = *(unsigned __int8 *)(v139 - v110 + g_rgiClapTabDec);
      LODWORD(v137) = v138 - v110;
      v140 = g_rgiClapTabDec;
      *(_DWORD *)&v178[a8 + 20] = ((unsigned int)(*(unsigned __int8 *)(v139 + v111 + g_rgiClapTabDec)
                                                + (*(unsigned __int8 *)(v138 + v111 + g_rgiClapTabDec) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)((int)v137 + g_rgiClapTabDec) << 19) + 8 * v122) & 0x7E007E0
                                | ((*(unsigned __int8 *)(v108 + v139 + g_rgiClapTabDec) << 8)
                                 + _byteswap_ulong(*(unsigned __int8 *)(v108 + v138 + g_rgiClapTabDec)))
                                & 0xF800F800;
      v141 = g_iYscale[v179[a6 + 13]];
      v142 = g_iYscale[v179[a6 + 12]];
      LODWORD(v122) = *(unsigned __int8 *)(v142 - v117 + v140);
      LODWORD(v137) = v141 - v117;
      v10 = v140;
      *(_DWORD *)&v178[a8 + 24] = ((unsigned int)(*(unsigned __int8 *)(v142 + v118 + v140)
                                                + (*(unsigned __int8 *)(v141 + v118 + v140) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)((int)v137 + v140) << 19) + 8 * v122) & 0x7E007E0
                                | ((*(unsigned __int8 *)(v142 + v116 + v140) << 8)
                                 + _byteswap_ulong(*(unsigned __int8 *)(v141 + v116 + v140)))
                                & 0xF800F800;
      v143 = g_iYscale[v179[a6 + 15]];
      v144 = v179[a6 + 14];
      v11 = &v179[2 * a6];
      v179 = v11;
      *(_DWORD *)&v178[a8 + 28] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v144] + v125 + v10)
                                                + (*(unsigned __int8 *)(v143 + v125 + v10) << 16)) >> 3)
                                & 0x1F001F
                                | ((*(unsigned __int8 *)(v143 - v124 + v10) << 19)
                                 + 8 * *(unsigned __int8 *)(g_iYscale[v144] - v124 + v10))
                                & 0x7E007E0
                                | ((*(unsigned __int8 *)(v123 + g_iYscale[v144] + v10) << 8)
                                 + _byteswap_ulong(*(unsigned __int8 *)(v123 + v143 + v10)))
                                & 0xF800F800;
      v8 = &v178[v176];
      v80 = v177-- == 1;
      v81 = v146;
      v178 += v176;
    }
    while ( !v80 );
  }
}

```

## disassembly

```asm
0x18003ed40  mov     [rsp+arg_18], r9
0x18003ed45  mov     [rsp+arg_10], r8
0x18003ed4a  mov     [rsp+arg_8], rdx
0x18003ed4f  push    rbx
0x18003ed50  push    rbp
0x18003ed51  push    rsi
0x18003ed52  push    rdi
0x18003ed53  push    r12
0x18003ed55  push    r13
0x18003ed57  push    r14
0x18003ed59  push    r15
0x18003ed5b  sub     rsp, 58h
0x18003ed5f  cmp     dword ptr [rcx+68h], 7
0x18003ed63  mov     r13, rdx
0x18003ed66  movsxd  rdx, [rsp+98h+arg_38]
0x18003ed6e  mov     r14, r9
0x18003ed71  mov     rbp, cs:g_rgiClapTabDec
0x18003ed78  mov     r12, r8
0x18003ed7b  mov     [rsp+98h+arg_0], 8
0x18003ed86  mov     esi, 1F001Fh
0x18003ed8b  lea     rax, [rdx+rdx]
0x18003ed8f  mov     [rsp+98h+var_50], rax
0x18003ed94  jnz     loc_18003FB23
0x18003ed9a  mov     rdi, [rsp+98h+arg_20]
0x18003eda2  lea     r15, __ImageBase
0x18003eda9  mov     [rsp+98h+var_98], rdi
0x18003edad  movzx   edx, byte ptr [r14]
0x18003edb1  movzx   eax, byte ptr [rdi]
0x18003edb4  mov     ebx, rva g_iUtoB[r15+rdx*4]
0x18003edbc  mov     r11d, rva g_iVtoR[r15+rax*4]
0x18003edc4  mov     ecx, rva g_iUtoG[r15+rdx*4]
0x18003edcc  add     ecx, rva g_iVtoG[r15+rax*4]
0x18003edd4  movzx   eax, byte ptr [r12+1]
0x18003edda  mov     [rsp+98h+var_74], ecx
0x18003edde  mov     [rsp+98h+var_78], ebx
0x18003ede2  mov     [rsp+98h+var_7C], r11d
0x18003ede7  mov     r8d, rva g_iYscale[r15+rax*4]
0x18003edef  movzx   eax, byte ptr [r12]
0x18003edf4  mov     r9d, rva g_iYscale[r15+rax*4]
0x18003edfc  mov     eax, r9d
0x18003edff  sub     eax, ecx
0x18003ee01  cdqe
0x18003ee03  movzx   edx, byte ptr [rax+rbp]
0x18003ee07  mov     eax, r8d
0x18003ee0a  sub     eax, ecx
0x18003ee0c  cdqe
0x18003ee0e  movzx   ecx, byte ptr [rax+rbp]
0x18003ee12  lea     eax, [r11+r9]
0x18003ee16  shl     ecx, 12h
0x18003ee19  lea     r10d, [rcx+rdx*4]
0x18003ee1d  movsxd  rcx, eax
0x18003ee20  and     r10d, 3E003E0h
0x18003ee27  lea     eax, [r11+r8]
0x18003ee2b  movzx   edx, byte ptr [rcx+rbp]
0x18003ee2f  movsxd  rcx, eax
0x18003ee32  shl     edx, 7
0x18003ee35  movzx   eax, byte ptr [rcx+rbp]
0x18003ee39  shl     eax, 17h
0x18003ee3c  add     edx, eax
0x18003ee3e  lea     eax, [rbx+r8]
0x18003ee42  movsxd  rcx, eax
0x18003ee45  and     edx, 7C007C00h
0x18003ee4b  or      r10d, edx
0x18003ee4e  lea     eax, [rbx+r9]
0x18003ee52  movzx   edx, byte ptr [rcx+rbp]
0x18003ee56  movsxd  rcx, eax
0x18003ee59  shl     edx, 10h
0x18003ee5c  movzx   eax, byte ptr [rcx+rbp]
0x18003ee60  add     edx, eax
0x18003ee62  shr     edx, 3
0x18003ee65  and     edx, esi
0x18003ee67  or      r10d, edx
0x18003ee6a  mov     [r13+0], r10d
0x18003ee6e  movzx   eax, byte ptr [rdi+1]
0x18003ee72  movzx   edx, byte ptr [r14+1]
0x18003ee77  mov     r11d, rva g_iVtoR[r15+rax*4]
0x18003ee7f  mov     ebx, rva g_iUtoG[r15+rdx*4]
0x18003ee87  add     ebx, rva g_iVtoG[r15+rax*4]
0x18003ee8f  movzx   eax, byte ptr [r12+3]
0x18003ee95  mov     edi, rva g_iUtoB[r15+rdx*4]
0x18003ee9d  mov     [rsp+98h+var_70], r11d
0x18003eea2  mov     [rsp+98h+var_6C], ebx
0x18003eea6  mov     r8d, rva g_iYscale[r15+rax*4]
0x18003eeae  movzx   eax, byte ptr [r12+2]
0x18003eeb4  mov     [rsp+98h+var_90], edi
0x18003eeb8  mov     r9d, rva g_iYscale[r15+rax*4]
0x18003eec0  lea     eax, [r11+r9]
0x18003eec4  movsxd  rcx, eax
0x18003eec7  lea     eax, [r11+r8]
0x18003eecb  movzx   r10d, byte ptr [rcx+rbp]
0x18003eed0  movsxd  rcx, eax
0x18003eed3  shl     r10d, 7
0x18003eed7  movzx   eax, byte ptr [rcx+rbp]
0x18003eedb  shl     eax, 17h
0x18003eede  add     r10d, eax
0x18003eee1  mov     eax, r9d
0x18003eee4  sub     eax, ebx
0x18003eee6  and     r10d, 7C007C00h
0x18003eeed  cdqe
0x18003eeef  movzx   edx, byte ptr [rax+rbp]
0x18003eef3  mov     eax, r8d
0x18003eef6  sub     eax, ebx
0x18003eef8  cdqe
0x18003eefa  movzx   ecx, byte ptr [rax+rbp]
0x18003eefe  shl     ecx, 12h
0x18003ef01  lea     eax, [rcx+rdx*4]
0x18003ef04  and     eax, 3E003E0h
0x18003ef09  or      r10d, eax
0x18003ef0c  lea     eax, [rdi+r8]
0x18003ef10  movsxd  rcx, eax
0x18003ef13  lea     eax, [rdi+r9]
0x18003ef17  movzx   edx, byte ptr [rcx+rbp]
0x18003ef1b  movsxd  rcx, eax
0x18003ef1e  shl     edx, 10h
0x18003ef21  movzx   eax, byte ptr [rcx+rbp]
0x18003ef25  add     edx, eax
0x18003ef27  mov     rax, [rsp+98h+var_98]
0x18003ef2b  shr     edx, 3
0x18003ef2e  and     edx, esi
0x18003ef30  or      r10d, edx
0x18003ef33  mov     [r13+4], r10d
0x18003ef37  movzx   eax, byte ptr [rax+2]
0x18003ef3b  movzx   edx, byte ptr [r14+2]
0x18003ef40  mov     r11d, rva g_iVtoR[r15+rax*4]
0x18003ef48  mov     edi, rva g_iUtoB[r15+rdx*4]
0x18003ef50  mov     ebx, rva g_iUtoG[r15+rdx*4]
0x18003ef58  add     ebx, rva g_iVtoG[r15+rax*4]
0x18003ef60  movzx   eax, byte ptr [r12+5]
0x18003ef66  mov     [rsp+98h+var_8C], edi
0x18003ef6a  mov     [rsp+98h+var_68], r11d
0x18003ef6f  mov     [rsp+98h+var_64], ebx
0x18003ef73  mov     r8d, rva g_iYscale[r15+rax*4]
0x18003ef7b  movzx   eax, byte ptr [r12+4]
0x18003ef81  mov     r9d, rva g_iYscale[r15+rax*4]
0x18003ef89  lea     eax, [r11+r9]
0x18003ef8d  movsxd  rcx, eax
0x18003ef90  lea     eax, [r11+r8]
0x18003ef94  movzx   r10d, byte ptr [rcx+rbp]
0x18003ef99  movsxd  rcx, eax
0x18003ef9c  shl     r10d, 7
0x18003efa0  movzx   eax, byte ptr [rcx+rbp]
0x18003efa4  shl     eax, 17h
0x18003efa7  add     r10d, eax
0x18003efaa  mov     eax, r9d
0x18003efad  sub     eax, ebx
0x18003efaf  and     r10d, 7C007C00h
0x18003efb6  cdqe
0x18003efb8  movzx   edx, byte ptr [rax+rbp]
0x18003efbc  mov     eax, r8d
0x18003efbf  sub     eax, ebx
0x18003efc1  cdqe
0x18003efc3  movzx   ecx, byte ptr [rax+rbp]
0x18003efc7  shl     ecx, 12h
0x18003efca  lea     eax, [rcx+rdx*4]
0x18003efcd  and     eax, 3E003E0h
0x18003efd2  or      r10d, eax
0x18003efd5  lea     eax, [rdi+r8]
0x18003efd9  movsxd  rcx, eax
0x18003efdc  lea     eax, [rdi+r9]
0x18003efe0  mov     rdi, [rsp+98h+var_98]
0x18003efe4  movzx   edx, byte ptr [rcx+rbp]
0x18003efe8  movsxd  rcx, eax
0x18003efeb  shl     edx, 10h
0x18003efee  movzx   eax, byte ptr [rcx+rbp]
0x18003eff2  add     edx, eax
0x18003eff4  shr     edx, 3
0x18003eff7  and     edx, esi
0x18003eff9  or      r10d, edx
0x18003effc  mov     [r13+8], r10d
0x18003f000  movzx   edx, byte ptr [r14+3]
0x18003f005  movzx   eax, byte ptr [rdi+3]
0x18003f009  mov     ecx, rva g_iUtoG[r15+rdx*4]
0x18003f011  add     ecx, rva g_iVtoG[r15+rax*4]
0x18003f019  mov     r11d, rva g_iVtoR[r15+rax*4]
0x18003f021  movzx   eax, byte ptr [r12+7]
0x18003f027  mov     ebx, rva g_iUtoB[r15+rdx*4]
0x18003f02f  mov     [rsp+98h+var_88], r11d
0x18003f034  mov     [rsp+98h+var_60], ecx
0x18003f038  mov     r8d, rva g_iYscale[r15+rax*4]
0x18003f040  movzx   eax, byte ptr [r12+6]
0x18003f046  mov     [rsp+98h+var_84], ebx
0x18003f04a  mov     r9d, rva g_iYscale[r15+rax*4]
0x18003f052  mov     eax, r9d
0x18003f055  sub     eax, ecx
0x18003f057  cdqe
0x18003f059  movzx   edx, byte ptr [rax+rbp]
0x18003f05d  mov     eax, r8d
0x18003f060  sub     eax, ecx
0x18003f062  cdqe
0x18003f064  movzx   ecx, byte ptr [rax+rbp]
0x18003f068  lea     eax, [r11+r9]
0x18003f06c  shl     ecx, 12h
0x18003f06f  lea     r10d, [rcx+rdx*4]
0x18003f073  movsxd  rcx, eax
0x18003f076  and     r10d, 3E003E0h
0x18003f07d  lea     eax, [r11+r8]
0x18003f081  movzx   edx, byte ptr [rcx+rbp]
0x18003f085  movsxd  rcx, eax
0x18003f088  shl     edx, 7
0x18003f08b  movzx   eax, byte ptr [rcx+rbp]
0x18003f08f  shl     eax, 17h
0x18003f092  add     edx, eax
0x18003f094  lea     eax, [rbx+r8]
0x18003f098  movsxd  rcx, eax
0x18003f09b  and     edx, 7C007C00h
0x18003f0a1  or      r10d, edx
0x18003f0a4  lea     eax, [rbx+r9]
0x18003f0a8  movzx   edx, byte ptr [rcx+rbp]
0x18003f0ac  movsxd  rcx, eax
0x18003f0af  shl     edx, 10h
0x18003f0b2  movzx   eax, byte ptr [rcx+rbp]
0x18003f0b6  add     edx, eax
0x18003f0b8  shr     edx, 3
0x18003f0bb  and     edx, esi
0x18003f0bd  or      r10d, edx
0x18003f0c0  mov     [r13+0Ch], r10d
0x18003f0c4  movzx   edx, byte ptr [r14+4]
0x18003f0c9  movzx   eax, byte ptr [rdi+4]
0x18003f0cd  mov     edi, rva g_iUtoB[r15+rdx*4]
0x18003f0d5  mov     r11d, rva g_iVtoR[r15+rax*4]
0x18003f0dd  mov     ebx, rva g_iUtoG[r15+rdx*4]
0x18003f0e5  add     ebx, rva g_iVtoG[r15+rax*4]
0x18003f0ed  movzx   eax, byte ptr [r12+9]
0x18003f0f3  mov     [rsp+98h+var_58], ebx
0x18003f0f7  mov     [rsp+98h+var_80], edi
0x18003f0fb  mov     [rsp+98h+var_5C], r11d
0x18003f100  mov     r8d, rva g_iYscale[r15+rax*4]
0x18003f108  movzx   eax, byte ptr [r12+8]
0x18003f10e  mov     r9d, rva g_iYscale[r15+rax*4]
0x18003f116  lea     eax, [r11+r9]
0x18003f11a  movsxd  rcx, eax
0x18003f11d  lea     eax, [r11+r8]
0x18003f121  movzx   r10d, byte ptr [rcx+rbp]
0x18003f126  movsxd  rcx, eax
0x18003f129  shl     r10d, 7
0x18003f12d  movzx   eax, byte ptr [rcx+rbp]
0x18003f131  shl     eax, 17h
0x18003f134  add     r10d, eax
0x18003f137  mov     eax, r9d
0x18003f13a  sub     eax, ebx
0x18003f13c  and     r10d, 7C007C00h
0x18003f143  cdqe
0x18003f145  movzx   edx, byte ptr [rax+rbp]
0x18003f149  mov     eax, r8d
0x18003f14c  sub     eax, ebx
0x18003f14e  mov     ebx, 3E003E0h
0x18003f153  cdqe
0x18003f155  movzx   ecx, byte ptr [rax+rbp]
0x18003f159  shl     ecx, 12h
0x18003f15c  lea     eax, [rcx+rdx*4]
0x18003f15f  and     eax, ebx
0x18003f161  or      r10d, eax
0x18003f164  lea     eax, [rdi+r8]
0x18003f168  movsxd  rcx, eax
0x18003f16b  lea     eax, [rdi+r9]
0x18003f16f  mov     rdi, [rsp+98h+var_98]
0x18003f173  movzx   edx, byte ptr [rcx+rbp]
0x18003f177  shl     edx, 10h
0x18003f17a  movsxd  rcx, eax
0x18003f17d  movzx   eax, byte ptr [rcx+rbp]
0x18003f181  add     edx, eax
0x18003f183  shr     edx, 3
0x18003f186  and     edx, esi
0x18003f188  or      r10d, edx
0x18003f18b  mov     [r13+10h], r10d
0x18003f18f  movzx   eax, byte ptr [rdi+5]
0x18003f193  movzx   edx, byte ptr [r14+5]
0x18003f198  mov     r12d, rva g_iVtoR[r15+rax*4]
0x18003f1a0  mov     r14d, rva g_iUtoG[r15+rdx*4]
0x18003f1a8  add     r14d, rva g_iVtoG[r15+rax*4]
0x18003f1b0  mov     r13d, rva g_iUtoB[r15+rdx*4]
0x18003f1b8  mov     r11, [rsp+98h+arg_10]
0x18003f1c0  movzx   eax, byte ptr [r11+0Bh]
0x18003f1c5  mov     r8d, rva g_iYscale[r15+rax*4]
0x18003f1cd  movzx   eax, byte ptr [r11+0Ah]
0x18003f1d2  mov     r9d, rva g_iYscale[r15+rax*4]
0x18003f1da  mov     eax, r9d
0x18003f1dd  sub     eax, r14d
0x18003f1e0  cdqe
0x18003f1e2  movzx   edx, byte ptr [rax+rbp]
0x18003f1e6  mov     eax, r8d
0x18003f1e9  sub     eax, r14d
0x18003f1ec  cdqe
0x18003f1ee  movzx   ecx, byte ptr [rax+rbp]
0x18003f1f2  lea     eax, [r12+r9]
0x18003f1f6  shl     ecx, 12h
0x18003f1f9  lea     r10d, [rcx+rdx*4]
0x18003f1fd  movsxd  rcx, eax
0x18003f200  and     r10d, ebx
0x18003f203  lea     eax, [r12+r8]
0x18003f207  mov     rbx, [rsp+98h+arg_8]
0x18003f20f  movzx   edx, byte ptr [rcx+rbp]
0x18003f213  movsxd  rcx, eax
0x18003f216  shl     edx, 7
0x18003f219  movzx   eax, byte ptr [rcx+rbp]
0x18003f21d  shl     eax, 17h
0x18003f220  add     edx, eax
0x18003f222  lea     eax, [r8+r13]
0x18003f226  movsxd  rcx, eax
0x18003f229  and     edx, 7C007C00h
  ... truncated ...
```

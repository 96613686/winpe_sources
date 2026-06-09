# UpdateDstMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x1800415e0`
- end: `0x1800427c2`
- name: `?UpdateDstMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `4578`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180043390`

## callees

- `0x1800415e0`

## pseudocode

```c
void __fastcall UpdateDstMBRGB8(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  const unsigned __int8 *v8; // rdi
  char v9; // al
  __int64 v10; // rdx
  int v11; // esi
  int v12; // r14d
  __int64 v13; // rdx
  int v14; // r10d
  __int64 v15; // rax
  int v16; // r8d
  int v17; // esi
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // r11d
  int v23; // r13d
  int v24; // r15d
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // r12d
  int v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rax
  int v36; // ebp
  int v37; // edi
  __int64 v38; // rdx
  __int64 v39; // rax
  int v40; // r9d
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // r9
  int v44; // r8d
  int v45; // r8d
  int v46; // r8d
  __int64 v47; // rax
  int v48; // r8d
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // r9
  __int64 v54; // rcx
  int v55; // r8d
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // r9
  int v59; // r8d
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // r9
  int v64; // r8d
  int v65; // r8d
  int v66; // r8d
  int v67; // r8d
  int v68; // r8d
  int v69; // r8d
  int v70; // r8d
  int v71; // r10d
  int v72; // r8d
  __int64 v73; // r11
  __int64 v74; // rcx
  int v75; // r8d
  int v76; // r8d
  __int64 v77; // r8
  __int64 v78; // rcx
  __int64 v79; // rbp
  __int64 v80; // rax
  int v81; // [rsp+0h] [rbp-78h]
  int v82; // [rsp+4h] [rbp-74h]
  int v83; // [rsp+8h] [rbp-70h]
  int v84; // [rsp+Ch] [rbp-6Ch]
  int v85; // [rsp+10h] [rbp-68h]
  int v86; // [rsp+14h] [rbp-64h]
  int v87; // [rsp+18h] [rbp-60h]
  int v88; // [rsp+1Ch] [rbp-5Ch]
  int v89; // [rsp+20h] [rbp-58h]
  int v90; // [rsp+24h] [rbp-54h]
  int v91; // [rsp+28h] [rbp-50h]
  int v92; // [rsp+2Ch] [rbp-4Ch]
  int v93; // [rsp+30h] [rbp-48h]
  int v94; // [rsp+34h] [rbp-44h]
  int v95; // [rsp+38h] [rbp-40h]
  int v96; // [rsp+3Ch] [rbp-3Ch]
  unsigned __int8 *v97; // [rsp+88h] [rbp+10h]
  const unsigned __int8 *v99; // [rsp+98h] [rbp+20h]

  v99 = a4;
  v97 = a2;
  LOBYTE(a2) = 0;
  v96 = 0;
  v8 = a4;
  do
  {
    v9 = (char)a2;
    v10 = *v8;
    v11 = g_iUtoG[v10];
    v12 = g_iUtoB[v10];
    v13 = v8[1];
    v14 = 3 * ((-2 * v9) & 3);
    v15 = *a5;
    v14 <<= 10;
    v16 = g_iVtoR[v15];
    v17 = g_iVtoG[v15] + v11;
    v18 = a5[1];
    v86 = v16;
    v19 = g_iVtoR[v18];
    v87 = g_iUtoG[v13] + g_iVtoG[v18];
    LODWORD(v18) = g_iUtoB[v13];
    v20 = v8[2];
    v88 = v18;
    v21 = a5[2];
    v89 = v19;
    v22 = g_iUtoB[v20];
    v23 = g_iVtoG[v21] + g_iUtoG[v20];
    v24 = g_iVtoR[v21];
    v25 = v8[3];
    v26 = a5[3];
    v27 = g_iVtoR[v26];
    v91 = g_iUtoG[v25] + g_iVtoG[v26];
    LODWORD(v26) = g_iUtoB[v25];
    v28 = v8[4];
    v90 = v26;
    v29 = a5[4];
    v83 = v27;
    v30 = g_iVtoR[v29];
    LODWORD(v29) = g_iUtoG[v28] + g_iVtoG[v29];
    v31 = g_iUtoB[v28];
    v32 = v8[5];
    v81 = v29;
    v33 = a5[5];
    v84 = g_iVtoR[v33];
    v93 = g_iUtoG[v32] + g_iVtoG[v33];
    LODWORD(v33) = g_iUtoB[v32];
    v34 = v8[6];
    v92 = v33;
    v35 = a5[6];
    v36 = g_iVtoR[v35];
    v37 = g_iUtoB[v34];
    v82 = g_iUtoG[v34] + g_iVtoG[v35];
    v38 = v99[7];
    v39 = a5[7];
    v85 = g_iVtoR[v39];
    v94 = g_iUtoG[v38] + g_iVtoG[v39];
    v95 = g_iUtoB[v38];
    v40 = g_iYscale[*a3];
    LOBYTE(v16) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v40 + v16 + g_rgiClapTabDec));
    v41 = v14 + (unsigned int)*(unsigned __int8 *)(v40 + v12 + g_rgiClapTabDec);
    v42 = v40 - v17;
    v43 = g_rgiClapTabDec;
    *v97 = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v42 + g_rgiClapTabDec) + 256)
         + *((_BYTE *)&g_rgDitherMap + v41 + 512)
         + v16;
    v44 = g_iYscale[a3[4]];
    v97[4] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v44 + v24 + v43))
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v44 - v23 + v43) + 256)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v44 + v22 + v43) + 512);
    v45 = g_iYscale[a3[8]];
    v97[8] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v45 + v30 + v43))
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v45 - v81 + v43) + 256)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v45 + v31 + v43) + 512);
    v46 = g_iYscale[a3[12]];
    LOBYTE(v38) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v46 - v82 + v43) + 256)
                + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v46 + v37 + v43) + 512);
    v47 = v14 + (unsigned int)*(unsigned __int8 *)(v46 + v36 + v43);
    v14 += 768;
    v97[12] = *((_BYTE *)&g_rgDitherMap + v47) + v38;
    v48 = g_iYscale[a3[1]];
    v97[1] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v48 + v86 + v43))
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v12 + v48 + v43) + 512)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v48 - v17 + v43) + 256);
    LODWORD(v43) = g_iYscale[a3[5]];
    v49 = g_rgiClapTabDec;
    v97[5] = *((_BYTE *)&g_rgDitherMap + v14
                                       + (unsigned int)*(unsigned __int8 *)((int)v43 - v23 + g_rgiClapTabDec)
                                       + 256)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v24 + (int)v43 + g_rgiClapTabDec))
           + *((_BYTE *)&g_rgDitherMap + v14
                                       + (unsigned int)*(unsigned __int8 *)(v22 + (int)v43 + g_rgiClapTabDec)
                                       + 512);
    LODWORD(v43) = g_iYscale[a3[9]];
    LOBYTE(v48) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v31 + (int)v43 + v49) + 512);
    v50 = g_rgiClapTabDec;
    v97[9] = *((_BYTE *)&g_rgDitherMap + v14
                                       + (unsigned int)*(unsigned __int8 *)((int)v43 - v81 + g_rgiClapTabDec)
                                       + 256)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v30 + (int)v43 + g_rgiClapTabDec))
           + v48;
    LODWORD(v43) = g_iYscale[a3[13]];
    LOBYTE(v48) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v37 + (int)v43 + v50) + 512);
    v51 = v14 + (unsigned int)*(unsigned __int8 *)((int)v43 + v36 + g_rgiClapTabDec);
    v52 = (int)v43 - v82;
    v53 = g_rgiClapTabDec;
    LOBYTE(v48) = *((_BYTE *)&g_rgDitherMap + v51) + v48;
    v54 = v14 + (unsigned int)*(unsigned __int8 *)(v52 + g_rgiClapTabDec);
    v14 += 768;
    v97[13] = *((_BYTE *)&g_rgDitherMap + v54 + 256) + v48;
    v55 = g_iYscale[a3[2]];
    v97[2] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v55 + v89 + v53))
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v55 + v88 + v53) + 512)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v55 - v87 + v53) + 256);
    LODWORD(v53) = g_iYscale[a3[6]];
    a2 = (unsigned __int8 *)g_rgiClapTabDec;
    v97[6] = *((_BYTE *)&g_rgDitherMap + v14
                                       + (unsigned int)*(unsigned __int8 *)((int)v53 - v91 + g_rgiClapTabDec)
                                       + 256)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)((int)v53 + v83 + g_rgiClapTabDec))
           + *((_BYTE *)&g_rgDitherMap + v14
                                       + (unsigned int)*(unsigned __int8 *)((int)v53 + v90 + g_rgiClapTabDec)
                                       + 512);
    LODWORD(v53) = g_iYscale[a3[10]];
    LOBYTE(v55) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)a2[(int)v53 + v92] + 512);
    v56 = v14 + (unsigned int)*(unsigned __int8 *)((int)v53 + v84 + g_rgiClapTabDec);
    v57 = (int)v53 - v93;
    v58 = g_rgiClapTabDec;
    v97[10] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v57 + g_rgiClapTabDec) + 256)
            + *((_BYTE *)&g_rgDitherMap + v56)
            + v55;
    v59 = g_iYscale[a3[14]];
    LOBYTE(a2) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v59 + v95 + v58) + 512)
               + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v59 - v94 + v58) + 256);
    v60 = v14 + (unsigned int)*(unsigned __int8 *)(v59 + v85 + v58);
    v14 += 768;
    v97[14] = *((_BYTE *)&g_rgDitherMap + v60) + (_BYTE)a2;
    LODWORD(v58) = g_iYscale[a3[3]];
    LOBYTE(v59) = *((_BYTE *)&g_rgDitherMap
                  + v14
                  + (unsigned int)*(unsigned __int8 *)((int)v58 + v88 + g_rgiClapTabDec)
                  + 512);
    v61 = v14 + (unsigned int)*(unsigned __int8 *)((int)v58 + v89 + g_rgiClapTabDec);
    v62 = (int)v58 - v87;
    v63 = g_rgiClapTabDec;
    v97[3] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v62 + g_rgiClapTabDec) + 256)
           + *((_BYTE *)&g_rgDitherMap + v61)
           + v59;
    v64 = g_iYscale[a3[7]];
    v97[7] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v64 + v83 + v63))
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v64 + v90 + v63) + 512)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v64 - v91 + v63) + 256);
    v65 = g_iYscale[a3[11]];
    v97[11] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v65 + v84 + v63))
            + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v65 + v92 + v63) + 512)
            + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v65 - v93 + v63) + 256);
    v66 = g_iYscale[a3[15]];
    v97[15] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v66 + v85 + v63))
            + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v66 + v95 + v63) + 512)
            + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)*(unsigned __int8 *)(v66 - v94 + v63) + 256);
    v99 += a7;
    a5 += a7;
    LODWORD(v63) = 3072 * ((1 - 2 * (_BYTE)v96) & 3);
    v67 = g_iYscale[a3[a6]];
    v97[a8] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v63 + *(unsigned __int8 *)(v67 + v86 + g_rgiClapTabDec))
            + *((_BYTE *)&g_rgDitherMap + (unsigned int)v63 + *(unsigned __int8 *)(v67 - v17 + g_rgiClapTabDec) + 256)
            + *((_BYTE *)&g_rgDitherMap + (unsigned int)v63 + *(unsigned __int8 *)(v67 + v12 + g_rgiClapTabDec) + 512);
    v68 = g_iYscale[a3[a6 + 4]];
    v97[a8 + 4] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v63 + *(unsigned __int8 *)(v68 + v24 + g_rgiClapTabDec))
                + *((_BYTE *)&g_rgDitherMap + (unsigned int)v63
                                            + *(unsigned __int8 *)(v68 - v23 + g_rgiClapTabDec)
                                            + 256)
                + *((_BYTE *)&g_rgDitherMap + (unsigned int)v63
                                            + *(unsigned __int8 *)(v68 + v22 + g_rgiClapTabDec)
                                            + 512);
    v69 = g_iYscale[a3[a6 + 8]];
    v97[a8 + 8] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v63 + *(unsigned __int8 *)(v69 + v30 + g_rgiClapTabDec))
                + *((_BYTE *)&g_rgDitherMap + (unsigned int)v63
                                            + *(unsigned __int8 *)(v69 - v81 + g_rgiClapTabDec)
                                            + 256)
                + *((_BYTE *)&g_rgDitherMap + (unsigned int)v63
                                            + *(unsigned __int8 *)(v69 + v31 + g_rgiClapTabDec)
                                            + 512);
    v70 = g_iYscale[a3[a6 + 12]];
    v97[a8 + 12] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v63 + *(unsigned __int8 *)(v70 + v36 + g_rgiClapTabDec))
                 + *((_BYTE *)&g_rgDitherMap
                   + (unsigned int)v63
                   + *(unsigned __int8 *)(v70 - v82 + g_rgiClapTabDec)
                   + 256)
                 + *((_BYTE *)&g_rgDitherMap
                   + (unsigned int)v63
                   + *(unsigned __int8 *)(v70 + v37 + g_rgiClapTabDec)
                   + 512);
    v71 = v63 + 768;
    v72 = g_iYscale[a3[a6 + 1]];
    v97[a8 + 1] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v63
                                            + *(unsigned __int8 *)(v72 + v86 + g_rgiClapTabDec)
                                            + 768)
                + *((_BYTE *)&g_rgDitherMap
                  + (unsigned int)v63
                  + *(unsigned __int8 *)(v12 + v72 + g_rgiClapTabDec)
                  + 1280)
                + *((_BYTE *)&g_rgDitherMap
                  + (unsigned int)v63
                  + *(unsigned __int8 *)(v72 - v17 + g_rgiClapTabDec)
                  + 1024);
    LODWORD(v63) = g_iYscale[a3[a6 + 5]];
    LODWORD(v62) = v22 + v63;
    v73 = g_rgiClapTabDec;
    v97[a8 + 5] = *((_BYTE *)&g_rgDitherMap
                  + v71
                  + (unsigned int)*(unsigned __int8 *)((int)v63 - v23 + g_rgiClapTabDec)
                  + 256)
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v24 + (int)v63 + g_rgiClapTabDec))
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v62 + g_rgiClapTabDec) + 512);
    LODWORD(v63) = g_iYscale[a3[a6 + 9]];
    v97[a8 + 9] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 - v81 + v73) + 256)
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v30 + (int)v63 + v73))
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v31 + (int)v63 + v73) + 512);
    LODWORD(v63) = g_iYscale[a3[a6 + 13]];
    LOBYTE(v72) = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 + v36 + v73))
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v37 + (int)v63 + v73) + 512);
    v74 = v71 + (unsigned int)*(unsigned __int8 *)((int)v63 - v82 + v73);
    v71 += 768;
    v97[a8 + 13] = *((_BYTE *)&g_rgDitherMap + v74 + 256) + v72;
    v75 = g_iYscale[a3[a6 + 2]];
    v97[a8 + 2] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v75 + v89 + v73))
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v88 + v75 + v73) + 512)
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v75 - v87 + v73) + 256);
    LODWORD(v63) = g_iYscale[a3[a6 + 6]];
    v97[a8 + 6] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 - v91 + v73) + 256)
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 + v83 + v73))
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v90 + (int)v63 + v73) + 512);
    LODWORD(v63) = g_iYscale[a3[a6 + 10]];
    v97[a8 + 10] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 - v93 + v73) + 256)
                 + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 + v84 + v73))
                 + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v92 + (int)v63 + v73) + 512);
    v76 = g_iYscale[a3[a6 + 14]];
    LOBYTE(a2) = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v95 + v76 + g_rgiClapTabDec) + 512)
               + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v76 - v94 + v73) + 256);
    LODWORD(v62) = v76 + v85;
    v77 = g_rgiClapTabDec;
    v78 = v71 + (unsigned int)*(unsigned __int8 *)((int)v62 + g_rgiClapTabDec);
    v71 += 768;
    v97[a8 + 14] = *((_BYTE *)&g_rgDitherMap + v78) + (_BYTE)a2;
    LODWORD(v63) = g_iYscale[a3[a6 + 3]];
    v79 = v77;
    v97[a8 + 3] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 - v87 + v77) + 256)
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v63 + v89 + v77))
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v88 + (int)v63 + v77) + 512);
    v8 = v99;
    LODWORD(v77) = g_iYscale[a3[a6 + 7]];
    v97[a8 + 7] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v77 + v83 + v79))
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v90 + (int)v77 + v79) + 512)
                + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v77 - v91 + v79) + 256);
    LODWORD(v77) = g_iYscale[a3[a6 + 11]];
    v97[a8 + 11] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v77 + v84 + v79))
                 + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(v92 + (int)v77 + v79) + 512)
                 + *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)((int)v77 - v93 + v79) + 256);
    v80 = a3[a6 + 15];
    a3 += 2 * a6;
    v97[a8 + 15] = *((_BYTE *)&g_rgDitherMap + v71 + (unsigned int)*(unsigned __int8 *)(g_iYscale[v80] + v85 + v79))
                 + *((_BYTE *)&g_rgDitherMap + v71
                                             + (unsigned int)*(unsigned __int8 *)(v95 + g_iYscale[v80] + v79)
                                             + 512)
                 + *((_BYTE *)&g_rgDitherMap + v71
                                             + (unsigned int)*(unsigned __int8 *)(g_iYscale[v80] - v94 + v79)
                                             + 256);
    LODWORD(a2) = v96 + 1;
    v97 += 2 * a8;
    v96 = (int)a2;
  }
  while ( (unsigned int)a2 < 8 );
}

```

## disassembly

```asm
0x1800415e0  mov     rax, rsp
0x1800415e3  mov     [rax+8], rbx
0x1800415e7  mov     [rax+20h], r9
0x1800415eb  mov     [rax+18h], r8
0x1800415ef  mov     [rax+10h], rdx
0x1800415f3  push    rbp
0x1800415f4  push    rsi
0x1800415f5  push    rdi
0x1800415f6  push    r12
0x1800415f8  push    r13
0x1800415fa  push    r14
0x1800415fc  push    r15
0x1800415fe  sub     rsp, 40h
0x180041602  xor     edx, edx
0x180041604  lea     rbx, __ImageBase
0x18004160b  mov     [rsp+78h+var_3C], edx
0x18004160f  mov     rdi, r9
0x180041612  mov     rbp, [rsp+78h+arg_20]
0x18004161a  lea     r9, __ImageBase
0x180041621  mov     eax, edx
0x180041623  movzx   edx, byte ptr [rdi]
0x180041626  neg     eax
0x180041628  add     eax, eax
0x18004162a  and     eax, 3
0x18004162d  mov     esi, rva g_iUtoG[rbx+rdx*4]
0x180041634  mov     r14d, rva g_iUtoB[rbx+rdx*4]
0x18004163c  movzx   edx, byte ptr [rdi+1]
0x180041640  lea     r10d, [rax+rax*2]
0x180041644  movzx   eax, byte ptr [rbp+0]
0x180041648  shl     r10d, 0Ah
0x18004164c  mov     r8d, rva g_iVtoR[rbx+rax*4]
0x180041654  add     esi, rva g_iVtoG[rbx+rax*4]
0x18004165b  movzx   eax, byte ptr [rbp+1]
0x18004165f  mov     [rsp+78h+var_64], r8d
0x180041664  mov     ecx, rva g_iVtoR[rbx+rax*4]
0x18004166b  mov     eax, rva g_iVtoG[rbx+rax*4]
0x180041672  add     eax, rva g_iUtoG[rbx+rdx*4]
0x180041679  mov     [rsp+78h+var_60], eax
0x18004167d  mov     eax, rva g_iUtoB[rbx+rdx*4]
0x180041684  movzx   edx, byte ptr [rdi+2]
0x180041688  mov     [rsp+78h+var_5C], eax
0x18004168c  movzx   eax, byte ptr [rbp+2]
0x180041690  mov     [rsp+78h+var_58], ecx
0x180041694  mov     r13d, rva g_iUtoG[rbx+rdx*4]
0x18004169c  mov     r11d, rva g_iUtoB[rbx+rdx*4]
0x1800416a4  add     r13d, rva g_iVtoG[rbx+rax*4]
0x1800416ac  mov     r15d, rva g_iVtoR[rbx+rax*4]
0x1800416b4  movzx   edx, byte ptr [rdi+3]
0x1800416b8  movzx   eax, byte ptr [rbp+3]
0x1800416bc  mov     ecx, rva g_iVtoR[rbx+rax*4]
0x1800416c3  mov     eax, rva g_iVtoG[rbx+rax*4]
0x1800416ca  add     eax, rva g_iUtoG[rbx+rdx*4]
0x1800416d1  mov     [rsp+78h+var_50], eax
0x1800416d5  mov     eax, rva g_iUtoB[rbx+rdx*4]
0x1800416dc  movzx   edx, byte ptr [rdi+4]
0x1800416e0  mov     [rsp+78h+var_54], eax
0x1800416e4  movzx   eax, byte ptr [rbp+4]
0x1800416e8  mov     [rsp+78h+var_70], ecx
0x1800416ec  lea     rcx, __ImageBase
0x1800416f3  mov     r12d, rva g_iVtoR[rbx+rax*4]
0x1800416fb  mov     eax, rva g_iVtoG[rbx+rax*4]
0x180041702  add     eax, rva g_iUtoG[rbx+rdx*4]
0x180041709  mov     ebx, rva g_iUtoB[rbx+rdx*4]
0x180041710  movzx   edx, byte ptr [rdi+5]
0x180041714  mov     [rsp+78h+var_78], eax
0x180041717  movzx   eax, byte ptr [rbp+5]
0x18004171b  mov     ecx, rva g_iVtoR[rcx+rax*4]
0x180041722  mov     eax, rva g_iVtoG[r9+rax*4]
0x18004172a  lea     r9, __ImageBase
0x180041731  mov     [rsp+78h+var_6C], ecx
0x180041735  lea     rcx, __ImageBase
0x18004173c  add     eax, rva g_iUtoG[rcx+rdx*4]
0x180041743  lea     rcx, __ImageBase
0x18004174a  mov     [rsp+78h+var_48], eax
0x18004174e  mov     eax, rva g_iUtoB[rcx+rdx*4]
0x180041755  movzx   edx, byte ptr [rdi+6]
0x180041759  lea     rdi, __ImageBase
0x180041760  mov     [rsp+78h+var_4C], eax
0x180041764  movzx   eax, byte ptr [rbp+6]
0x180041768  mov     ebp, rva g_iVtoR[rcx+rax*4]
0x18004176f  mov     eax, rva g_iVtoG[rdi+rax*4]
0x180041776  add     eax, rva g_iUtoG[rcx+rdx*4]
0x18004177d  lea     rcx, __ImageBase
0x180041784  mov     edi, rva g_iUtoB[rcx+rdx*4]
0x18004178b  mov     rdx, [rsp+78h+arg_18]
0x180041793  mov     [rsp+78h+var_74], eax
0x180041797  mov     rax, [rsp+78h+arg_20]
0x18004179f  movzx   edx, byte ptr [rdx+7]
0x1800417a3  movzx   eax, byte ptr [rax+7]
0x1800417a7  mov     ecx, rva g_iVtoR[rcx+rax*4]
0x1800417ae  mov     eax, rva g_iVtoG[r9+rax*4]
0x1800417b6  mov     [rsp+78h+var_68], ecx
0x1800417ba  lea     rcx, __ImageBase
0x1800417c1  add     eax, rva g_iUtoG[rcx+rdx*4]
0x1800417c8  lea     rcx, __ImageBase
0x1800417cf  mov     [rsp+78h+var_44], eax
0x1800417d3  mov     eax, rva g_iUtoB[rcx+rdx*4]
0x1800417da  mov     [rsp+78h+var_40], eax
0x1800417de  mov     r9, [rsp+78h+arg_10]
0x1800417e6  movzx   eax, byte ptr [r9]
0x1800417ea  mov     r9d, rva g_iYscale[rcx+rax*4]
0x1800417f2  lea     eax, [r9+r8]
0x1800417f6  mov     r8, cs:g_rgiClapTabDec
0x1800417fd  movsxd  rcx, eax
0x180041800  lea     eax, [r9+r14]
0x180041804  sub     r9d, esi
0x180041807  movzx   edx, byte ptr [rcx+r8]
0x18004180c  movsxd  rcx, eax
0x18004180f  add     edx, r10d
0x180041812  lea     rax, __ImageBase
0x180041819  movzx   ecx, byte ptr [rcx+r8]
0x18004181e  mov     r8b, [rdx+rax+59800h]
0x180041826  add     ecx, r10d
0x180041829  lea     rdx, __ImageBase
0x180041830  movsxd  rax, r9d
0x180041833  mov     r9, cs:g_rgiClapTabDec
0x18004183a  add     r8b, [rcx+rdx+59A00h]
0x180041842  movzx   ecx, byte ptr [rax+r9]
0x180041847  mov     rax, [rsp+78h+arg_8]
0x18004184f  add     ecx, r10d
0x180041852  add     r8b, [rcx+rdx+59900h]
0x18004185a  mov     [rax], r8b
0x18004185d  mov     rcx, [rsp+78h+arg_10]
0x180041865  movzx   eax, byte ptr [rcx+4]
0x180041869  mov     r8d, rva g_iYscale[rdx+rax*4]
0x180041871  lea     eax, [r8+r11]
0x180041875  movsxd  rcx, eax
0x180041878  mov     eax, r8d
0x18004187b  sub     eax, r13d
0x18004187e  cdqe
0x180041880  movzx   edx, byte ptr [rcx+r9]
0x180041885  lea     rcx, __ImageBase
0x18004188c  add     edx, r10d
0x18004188f  movzx   eax, byte ptr [rax+r9]
0x180041894  add     eax, r10d
0x180041897  mov     dl, [rdx+rcx+59A00h]
0x18004189e  add     dl, [rax+rcx+59900h]
0x1800418a5  lea     eax, [r8+r15]
0x1800418a9  movsxd  rcx, eax
0x1800418ac  lea     r8, __ImageBase
0x1800418b3  movzx   eax, byte ptr [rcx+r9]
0x1800418b8  add     eax, r10d
0x1800418bb  add     dl, [rax+r8+59800h]
0x1800418c3  mov     rax, [rsp+78h+arg_8]
0x1800418cb  mov     [rax+4], dl
0x1800418ce  mov     rax, [rsp+78h+arg_10]
0x1800418d6  movzx   eax, byte ptr [rax+8]
0x1800418da  mov     r8d, rva g_iYscale[r8+rax*4]
0x1800418e2  lea     eax, [r8+rbx]
0x1800418e6  movsxd  rcx, eax
0x1800418e9  mov     eax, r8d
0x1800418ec  sub     eax, [rsp+78h+var_78]
0x1800418ef  cdqe
0x1800418f1  movzx   edx, byte ptr [rcx+r9]
0x1800418f6  lea     rcx, __ImageBase
0x1800418fd  add     edx, r10d
0x180041900  movzx   eax, byte ptr [rax+r9]
0x180041905  add     eax, r10d
0x180041908  mov     dl, [rdx+rcx+59A00h]
0x18004190f  add     dl, [rax+rcx+59900h]
0x180041916  lea     eax, [r8+r12]
0x18004191a  movsxd  rcx, eax
0x18004191d  lea     r8, __ImageBase
0x180041924  movzx   eax, byte ptr [rcx+r9]
0x180041929  add     eax, r10d
0x18004192c  add     dl, [rax+r8+59800h]
0x180041934  mov     rax, [rsp+78h+arg_8]
0x18004193c  mov     [rax+8], dl
0x18004193f  mov     rax, [rsp+78h+arg_10]
0x180041947  movzx   eax, byte ptr [rax+0Ch]
0x18004194b  mov     r8d, rva g_iYscale[r8+rax*4]
0x180041953  lea     eax, [r8+rdi]
0x180041957  movsxd  rcx, eax
0x18004195a  mov     eax, r8d
0x18004195d  movzx   edx, byte ptr [rcx+r9]
0x180041962  add     edx, r10d
0x180041965  sub     eax, [rsp+78h+var_74]
0x180041969  cdqe
0x18004196b  movzx   eax, byte ptr [rax+r9]
0x180041970  add     eax, r10d
0x180041973  lea     rcx, __ImageBase
0x18004197a  mov     dl, [rdx+rcx+59A00h]
0x180041981  add     dl, [rax+rcx+59900h]
0x180041988  lea     eax, [r8+rbp]
0x18004198c  movsxd  rcx, eax
0x18004198f  lea     r8, __ImageBase
0x180041996  movzx   eax, byte ptr [rcx+r9]
0x18004199b  add     eax, r10d
0x18004199e  add     r10d, 300h
0x1800419a5  add     dl, [rax+r8+59800h]
0x1800419ad  mov     rax, [rsp+78h+arg_8]
0x1800419b5  mov     [rax+0Ch], dl
0x1800419b8  mov     rax, [rsp+78h+arg_10]
0x1800419c0  movzx   eax, byte ptr [rax+1]
0x1800419c4  mov     r8d, rva g_iYscale[r8+rax*4]
0x1800419cc  mov     eax, r8d
0x1800419cf  sub     eax, esi
0x1800419d1  cdqe
0x1800419d3  movzx   edx, byte ptr [rax+r9]
0x1800419d8  lea     eax, [r14+r8]
0x1800419dc  movsxd  rcx, eax
0x1800419df  add     edx, r10d
0x1800419e2  lea     rax, __ImageBase
0x1800419e9  mov     dl, [rdx+rax+59900h]
0x1800419f0  movzx   ecx, byte ptr [rcx+r9]
0x1800419f5  add     ecx, r10d
0x1800419f8  add     dl, [rcx+rax+59A00h]
0x1800419ff  mov     eax, [rsp+78h+var_64]
0x180041a03  add     eax, r8d
0x180041a06  lea     r8, __ImageBase
0x180041a0d  movsxd  rcx, eax
0x180041a10  movzx   eax, byte ptr [rcx+r9]
0x180041a15  add     eax, r10d
0x180041a18  add     dl, [rax+r8+59800h]
0x180041a20  mov     rax, [rsp+78h+arg_8]
0x180041a28  mov     [rax+1], dl
0x180041a2b  mov     rax, [rsp+78h+arg_10]
0x180041a33  movzx   eax, byte ptr [rax+5]
0x180041a37  mov     r9d, rva g_iYscale[r8+rax*4]
0x180041a3f  mov     r8, cs:g_rgiClapTabDec
0x180041a46  lea     eax, [r11+r9]
0x180041a4a  movsxd  rcx, eax
0x180041a4d  lea     eax, [r15+r9]
0x180041a51  sub     r9d, r13d
0x180041a54  movzx   edx, byte ptr [rcx+r8]
0x180041a59  movsxd  rcx, eax
0x180041a5c  add     edx, r10d
0x180041a5f  lea     rax, __ImageBase
0x180041a66  movzx   ecx, byte ptr [rcx+r8]
0x180041a6b  mov     r8b, [rdx+rax+59A00h]
0x180041a73  add     ecx, r10d
0x180041a76  mov     rdx, cs:g_rgiClapTabDec
0x180041a7d  add     r8b, [rcx+rax+59800h]
0x180041a85  lea     rcx, __ImageBase
0x180041a8c  movsxd  rax, r9d
0x180041a8f  movzx   eax, byte ptr [rax+rdx]
0x180041a93  add     eax, r10d
0x180041a96  add     r8b, [rax+rcx+59900h]
0x180041a9e  mov     rax, [rsp+78h+arg_8]
0x180041aa6  mov     [rax+5], r8b
0x180041aaa  mov     rax, [rsp+78h+arg_10]
0x180041ab2  movzx   eax, byte ptr [rax+9]
0x180041ab6  mov     r9d, rva g_iYscale[rcx+rax*4]
0x180041abe  lea     eax, [rbx+r9]
0x180041ac2  movsxd  rcx, eax
0x180041ac5  lea     eax, [r12+r9]
0x180041ac9  sub     r9d, [rsp+78h+var_78]
0x180041acd  movzx   edx, byte ptr [rcx+rdx]
0x180041ad1  movsxd  rcx, eax
0x180041ad4  add     edx, r10d
0x180041ad7  mov     rax, cs:g_rgiClapTabDec
0x180041ade  movzx   ecx, byte ptr [rcx+rax]
0x180041ae2  lea     rax, __ImageBase
0x180041ae9  mov     r8b, [rdx+rax+59A00h]
0x180041af1  add     ecx, r10d
0x180041af4  mov     rdx, cs:g_rgiClapTabDec
0x180041afb  add     r8b, [rcx+rax+59800h]
0x180041b03  movsxd  rax, r9d
0x180041b06  movzx   eax, byte ptr [rax+rdx]
0x180041b0a  add     eax, r10d
0x180041b0d  lea     rcx, __ImageBase
0x180041b14  add     r8b, [rax+rcx+59900h]
0x180041b1c  mov     rax, [rsp+78h+arg_8]
0x180041b24  mov     [rax+9], r8b
0x180041b28  mov     rax, [rsp+78h+arg_10]
0x180041b30  movzx   eax, byte ptr [rax+0Dh]
0x180041b34  mov     r9d, rva g_iYscale[rcx+rax*4]
0x180041b3c  lea     eax, [rdi+r9]
0x180041b40  movsxd  rcx, eax
0x180041b43  lea     eax, [r9+rbp]
0x180041b47  sub     r9d, [rsp+78h+var_74]
0x180041b4c  movzx   edx, byte ptr [rcx+rdx]
0x180041b50  movsxd  rcx, eax
0x180041b53  add     edx, r10d
0x180041b56  mov     rax, cs:g_rgiClapTabDec
0x180041b5d  movzx   ecx, byte ptr [rcx+rax]
0x180041b61  lea     rax, __ImageBase
0x180041b68  mov     r8b, [rdx+rax+59A00h]
0x180041b70  add     ecx, r10d
0x180041b73  lea     rdx, __ImageBase
0x180041b7a  movsxd  rax, r9d
0x180041b7d  mov     r9, cs:g_rgiClapTabDec
0x180041b84  add     r8b, [rcx+rdx+59800h]
0x180041b8c  movzx   ecx, byte ptr [rax+r9]
0x180041b91  mov     rax, [rsp+78h+arg_8]
0x180041b99  add     ecx, r10d
0x180041b9c  add     r10d, 300h
0x180041ba3  add     r8b, [rcx+rdx+59900h]
0x180041bab  mov     [rax+0Dh], r8b
0x180041baf  mov     rax, [rsp+78h+arg_10]
0x180041bb7  movzx   eax, byte ptr [rax+2]
0x180041bbb  mov     r8d, rva g_iYscale[rdx+rax*4]
0x180041bc3  mov     eax, r8d
0x180041bc6  sub     eax, [rsp+78h+var_60]
0x180041bca  cdqe
0x180041bcc  movzx   edx, byte ptr [rax+r9]
0x180041bd1  mov     eax, [rsp+78h+var_5C]
0x180041bd5  add     edx, r10d
0x180041bd8  add     eax, r8d
0x180041bdb  movsxd  rcx, eax
  ... truncated ...
```

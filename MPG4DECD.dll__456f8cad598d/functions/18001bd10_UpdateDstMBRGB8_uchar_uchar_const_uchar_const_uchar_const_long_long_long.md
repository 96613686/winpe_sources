# UpdateDstMBRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001bd10`
- end: `0x18001cee8`
- name: `?UpdateDstMBRGB8@@YAXPEAEPEBE11JJJ@Z`
- size: `4568`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d980`

## callees

- `0x18001bd10`

## pseudocode

```c
void __fastcall UpdateDstMBRGB8(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  const unsigned __int8 *v7; // rdi
  const unsigned __int8 *v8; // rbp
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
  __int64 v25; // rax
  __int64 v26; // rdx
  int v27; // ecx
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // r12d
  int v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // rax
  int v34; // ecx
  __int64 v35; // rax
  int v36; // ebp
  __int64 v37; // rdx
  int v38; // edi
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // r9d
  __int64 v42; // rcx
  __int64 v43; // rax
  unsigned __int8 *v44; // r9
  int v45; // r8d
  int v46; // r8d
  int v47; // r8d
  __int64 v48; // rax
  int v49; // r8d
  unsigned __int8 *v50; // rdx
  unsigned __int8 *v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rax
  unsigned __int8 *v54; // r9
  __int64 v55; // rcx
  int v56; // r8d
  __int64 v57; // rcx
  __int64 v58; // rax
  unsigned __int8 *v59; // r9
  int v60; // r8d
  __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  unsigned __int8 *v64; // r9
  int v65; // r8d
  int v66; // r8d
  int v67; // r8d
  int v68; // r8d
  int v69; // r8d
  int v70; // r8d
  int v71; // r8d
  int v72; // r10d
  int v73; // r8d
  unsigned __int8 *v74; // r11
  __int64 v75; // rcx
  int v76; // r8d
  int v77; // r8d
  unsigned __int8 *v78; // r8
  __int64 v79; // rcx
  unsigned __int8 *v80; // rbp
  __int64 v81; // rax
  int v82; // [rsp+0h] [rbp-88h]
  int v83; // [rsp+4h] [rbp-84h]
  int v84; // [rsp+8h] [rbp-80h]
  int v85; // [rsp+Ch] [rbp-7Ch]
  int v86; // [rsp+10h] [rbp-78h]
  int v87; // [rsp+14h] [rbp-74h]
  int v88; // [rsp+18h] [rbp-70h]
  int v89; // [rsp+1Ch] [rbp-6Ch]
  int v90; // [rsp+20h] [rbp-68h]
  int v91; // [rsp+24h] [rbp-64h]
  int v92; // [rsp+28h] [rbp-60h]
  int v93; // [rsp+2Ch] [rbp-5Ch]
  int v94; // [rsp+30h] [rbp-58h]
  int v95; // [rsp+34h] [rbp-54h]
  int v96; // [rsp+38h] [rbp-50h]
  int v97; // [rsp+3Ch] [rbp-4Ch]
  const unsigned __int8 *v99; // [rsp+98h] [rbp+10h]
  const unsigned __int8 *v100; // [rsp+A0h] [rbp+18h]
  const unsigned __int8 *v101; // [rsp+A8h] [rbp+20h]

  v101 = a4;
  v100 = a3;
  v99 = a2;
  LOBYTE(a2) = 0;
  v97 = 0;
  v7 = a4;
  v8 = a3;
  do
  {
    v9 = (char)a2;
    v10 = *v8;
    v11 = *((_DWORD *)&g_iUtoG + v10);
    v12 = *((_DWORD *)&g_iUtoB + v10);
    v13 = v8[1];
    v14 = 3 * ((-2 * v9) & 3);
    v15 = *v7;
    v14 <<= 10;
    v16 = *((_DWORD *)&g_iVtoR + v15);
    v17 = *((_DWORD *)&g_iVtoG + v15) + v11;
    v18 = v7[1];
    v87 = v16;
    v19 = *((_DWORD *)&g_iVtoR + v18);
    v88 = *((_DWORD *)&g_iUtoG + v13) + *((_DWORD *)&g_iVtoG + v18);
    LODWORD(v18) = *((_DWORD *)&g_iUtoB + v13);
    v20 = v8[2];
    v89 = v18;
    v21 = v7[2];
    v90 = v19;
    v22 = *((_DWORD *)&g_iUtoB + v20);
    v23 = *((_DWORD *)&g_iVtoG + v21) + *((_DWORD *)&g_iUtoG + v20);
    v24 = *((_DWORD *)&g_iVtoR + v21);
    v25 = v7[3];
    v26 = v8[3];
    v27 = *((_DWORD *)&g_iVtoR + v25);
    v92 = *((_DWORD *)&g_iUtoG + v26) + *((_DWORD *)&g_iVtoG + v25);
    LODWORD(v25) = *((_DWORD *)&g_iUtoB + v26);
    v28 = v8[4];
    v91 = v25;
    v29 = v7[4];
    v84 = v27;
    v30 = *((_DWORD *)&g_iVtoR + v29);
    LODWORD(v29) = *((_DWORD *)&g_iUtoG + v28) + *((_DWORD *)&g_iVtoG + v29);
    v31 = *((_DWORD *)&g_iUtoB + v28);
    v32 = v8[5];
    v82 = v29;
    v33 = v7[5];
    v34 = *((_DWORD *)&g_iVtoR + v33);
    v94 = *((_DWORD *)&g_iUtoG + v32) + *((_DWORD *)&g_iVtoG + v33);
    v93 = *((_DWORD *)&g_iUtoB + v32);
    v35 = v7[6];
    v85 = v34;
    v36 = *((_DWORD *)&g_iVtoR + v35);
    v37 = v100[6];
    v38 = *((_DWORD *)&g_iUtoB + v37);
    v83 = *((_DWORD *)&g_iUtoG + v37) + *((_DWORD *)&g_iVtoG + v35);
    v39 = v101[7];
    v86 = *((_DWORD *)&g_iVtoR + v39);
    v40 = v100[7];
    v95 = *((_DWORD *)&g_iUtoG + v40) + *((_DWORD *)&g_iVtoG + v39);
    v96 = *((_DWORD *)&g_iUtoB + v40);
    v41 = *((_DWORD *)&g_iYscale + *v99);
    LOBYTE(v16) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v41 + v16]);
    v42 = v14 + (unsigned int)g_rgiClapTabDec[v41 + v12];
    v43 = v41 - v17;
    v44 = g_rgiClapTabDec;
    *a1 = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v43] + 256)
        + *((_BYTE *)&g_rgDitherMap + v42 + 512)
        + v16;
    v45 = *((_DWORD *)&g_iYscale + v99[4]);
    a1[4] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v45 + v24])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v45 - v23] + 256)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v45 + v22] + 512);
    v46 = *((_DWORD *)&g_iYscale + v99[8]);
    a1[8] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v46 + v30])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v46 - v82] + 256)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v46 + v31] + 512);
    v47 = *((_DWORD *)&g_iYscale + v99[12]);
    LOBYTE(v40) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v47 - v83] + 256)
                + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v47 + v38] + 512);
    v48 = v14 + (unsigned int)v44[v47 + v36];
    v14 += 768;
    a1[12] = *((_BYTE *)&g_rgDitherMap + v48) + v40;
    v49 = *((_DWORD *)&g_iYscale + v99[1]);
    a1[1] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v49 + v87])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v12 + v49] + 512)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v44[v49 - v17] + 256);
    LODWORD(v44) = *((_DWORD *)&g_iYscale + v99[5]);
    v50 = g_rgiClapTabDec;
    a1[5] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v44 - v23] + 256)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v24 + (int)v44])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v22 + (int)v44] + 512);
    LODWORD(v44) = *((_DWORD *)&g_iYscale + v99[9]);
    LOBYTE(v49) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v50[v31 + (int)v44] + 512);
    v51 = g_rgiClapTabDec;
    a1[9] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v44 - v82] + 256)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v30 + (int)v44])
          + v49;
    LODWORD(v44) = *((_DWORD *)&g_iYscale + v99[13]);
    LOBYTE(v49) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v51[v38 + (int)v44] + 512);
    v52 = v14 + (unsigned int)g_rgiClapTabDec[(int)v44 + v36];
    v53 = (int)v44 - v83;
    v54 = g_rgiClapTabDec;
    LOBYTE(v49) = *((_BYTE *)&g_rgDitherMap + v52) + v49;
    v55 = v14 + (unsigned int)g_rgiClapTabDec[v53];
    v14 += 768;
    a1[13] = *((_BYTE *)&g_rgDitherMap + v55 + 256) + v49;
    v56 = *((_DWORD *)&g_iYscale + v99[2]);
    a1[2] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v54[v56 + v90])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v54[v56 + v89] + 512)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v54[v56 - v88] + 256);
    LODWORD(v54) = *((_DWORD *)&g_iYscale + v99[6]);
    a2 = g_rgiClapTabDec;
    a1[6] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v54 - v92] + 256)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v54 + v84])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v54 + v91] + 512);
    LODWORD(v54) = *((_DWORD *)&g_iYscale + v99[10]);
    LOBYTE(v56) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)a2[(int)v54 + v93] + 512);
    v57 = v14 + (unsigned int)g_rgiClapTabDec[(int)v54 + v85];
    v58 = (int)v54 - v94;
    v59 = g_rgiClapTabDec;
    a1[10] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v58] + 256)
           + *((_BYTE *)&g_rgDitherMap + v57)
           + v56;
    v60 = *((_DWORD *)&g_iYscale + v99[14]);
    LOBYTE(a2) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v59[v60 + v96] + 512)
               + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v59[v60 - v95] + 256);
    v61 = v14 + (unsigned int)v59[v60 + v86];
    v14 += 768;
    a1[14] = *((_BYTE *)&g_rgDitherMap + v61) + (_BYTE)a2;
    LODWORD(v59) = *((_DWORD *)&g_iYscale + v99[3]);
    LOBYTE(v60) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v59 + v89] + 512);
    v62 = v14 + (unsigned int)g_rgiClapTabDec[(int)v59 + v90];
    v63 = (int)v59 - v88;
    v64 = g_rgiClapTabDec;
    a1[3] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v63] + 256)
          + *((_BYTE *)&g_rgDitherMap + v62)
          + v60;
    v65 = *((_DWORD *)&g_iYscale + v99[7]);
    a1[7] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v65 + v84])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v65 + v91] + 512)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v65 - v92] + 256);
    v66 = *((_DWORD *)&g_iYscale + v99[11]);
    a1[11] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v66 + v85])
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v66 + v93] + 512)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v66 - v94] + 256);
    v67 = *((_DWORD *)&g_iYscale + v99[15]);
    a1[15] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v67 + v86])
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v67 + v96] + 512)
           + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v64[v67 - v95] + 256);
    v100 += a6;
    v101 += a6;
    LODWORD(v64) = 3072 * ((1 - 2 * (_BYTE)v97) & 3);
    v68 = *((_DWORD *)&g_iYscale + v99[a5]);
    a1[a7] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v68 + v87])
           + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v68 - v17] + 256)
           + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v68 + v12] + 512);
    v69 = *((_DWORD *)&g_iYscale + v99[a5 + 4]);
    a1[a7 + 4] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v69 + v24])
               + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v69 - v23] + 256)
               + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v69 + v22] + 512);
    v70 = *((_DWORD *)&g_iYscale + v99[a5 + 8]);
    a1[a7 + 8] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v70 + v30])
               + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v70 - v82] + 256)
               + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v70 + v31] + 512);
    v71 = *((_DWORD *)&g_iYscale + v99[a5 + 12]);
    a1[a7 + 12] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v71 + v36])
                + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v71 - v83] + 256)
                + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v71 + v38] + 512);
    v72 = (_DWORD)v64 + 768;
    v73 = *((_DWORD *)&g_iYscale + v99[a5 + 1]);
    a1[a7 + 1] = *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v73 + v87] + 768)
               + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v12 + v73] + 1280)
               + *((_BYTE *)&g_rgDitherMap + (unsigned int)v64 + g_rgiClapTabDec[v73 - v17] + 1024);
    LODWORD(v64) = *((_DWORD *)&g_iYscale + v99[a5 + 5]);
    LODWORD(v63) = v22 + (_DWORD)v64;
    v74 = g_rgiClapTabDec;
    a1[a7 + 5] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)g_rgiClapTabDec[(int)v64 - v23] + 256)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)g_rgiClapTabDec[v24 + (int)v64])
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)g_rgiClapTabDec[(int)v63] + 512);
    LODWORD(v64) = *((_DWORD *)&g_iYscale + v99[a5 + 9]);
    a1[a7 + 9] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[(int)v64 - v82] + 256)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v30 + (int)v64])
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v31 + (int)v64] + 512);
    LODWORD(v64) = *((_DWORD *)&g_iYscale + v99[a5 + 13]);
    LOBYTE(v73) = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[(int)v64 + v36])
                + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v38 + (int)v64] + 512);
    v75 = v72 + (unsigned int)v74[(int)v64 - v83];
    v72 += 768;
    a1[a7 + 13] = *((_BYTE *)&g_rgDitherMap + v75 + 256) + v73;
    v76 = *((_DWORD *)&g_iYscale + v99[a5 + 2]);
    a1[a7 + 2] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v76 + v90])
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v89 + v76] + 512)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v76 - v88] + 256);
    LODWORD(v64) = *((_DWORD *)&g_iYscale + v99[a5 + 6]);
    a1[a7 + 6] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[(int)v64 - v92] + 256)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[(int)v64 + v84])
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v91 + (int)v64] + 512);
    LODWORD(v64) = *((_DWORD *)&g_iYscale + v99[a5 + 10]);
    a1[a7 + 10] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[(int)v64 - v94] + 256)
                + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[(int)v64 + v85])
                + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v93 + (int)v64] + 512);
    v77 = *((_DWORD *)&g_iYscale + v99[a5 + 14]);
    LOBYTE(a2) = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)g_rgiClapTabDec[v96 + v77] + 512)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v74[v77 - v95] + 256);
    LODWORD(v63) = v77 + v86;
    v78 = g_rgiClapTabDec;
    v79 = v72 + (unsigned int)g_rgiClapTabDec[(int)v63];
    v72 += 768;
    a1[a7 + 14] = *((_BYTE *)&g_rgDitherMap + v79) + (_BYTE)a2;
    LODWORD(v64) = *((_DWORD *)&g_iYscale + v99[a5 + 3]);
    v80 = v78;
    a1[a7 + 3] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v78[(int)v64 - v88] + 256)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v78[(int)v64 + v90])
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v78[v89 + (int)v64] + 512);
    LODWORD(v78) = *((_DWORD *)&g_iYscale + v99[a5 + 7]);
    v7 = v101;
    a1[a7 + 7] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[(int)v78 + v84])
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[v91 + (int)v78] + 512)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[(int)v78 - v92] + 256);
    LODWORD(v78) = *((_DWORD *)&g_iYscale + v99[a5 + 11]);
    a1[a7 + 11] = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[(int)v78 + v85])
                + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[v93 + (int)v78] + 512)
                + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[(int)v78 - v94] + 256);
    v81 = v99[a5 + 15];
    v99 += 2 * a5;
    LODWORD(v78) = *((_DWORD *)&g_iYscale + v81);
    LOBYTE(a2) = *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[v96 + (int)v78] + 512)
               + *((_BYTE *)&g_rgDitherMap + v72 + (unsigned int)v80[(int)v78 - v95] + 256);
    LODWORD(v81) = v80[(int)v78 + v86];
    v8 = v100;
    a1[a7 + 15] = *((_BYTE *)&g_rgDitherMap + (unsigned int)(v72 + v81)) + (_BYTE)a2;
    LODWORD(a2) = v97 + 1;
    a1 += 2 * a7;
    v97 = (int)a2;
  }
  while ( (unsigned int)a2 < 8 );
}

```

## disassembly

```asm
0x18001bd10  mov     rax, rsp
0x18001bd13  mov     [rax+20h], r9
0x18001bd17  mov     [rax+18h], r8
0x18001bd1b  mov     [rax+10h], rdx
0x18001bd1f  mov     [rax+8], rcx
0x18001bd23  push    rbx
0x18001bd24  push    rbp
0x18001bd25  push    rsi
0x18001bd26  push    rdi
0x18001bd27  push    r12
0x18001bd29  push    r13
0x18001bd2b  push    r14
0x18001bd2d  push    r15
0x18001bd2f  sub     rsp, 48h
0x18001bd33  xor     edx, edx
0x18001bd35  lea     rbx, __ImageBase
0x18001bd3c  mov     [rsp+88h+var_4C], edx
0x18001bd40  mov     rdi, r9
0x18001bd43  mov     rbp, r8
0x18001bd46  mov     eax, edx
0x18001bd48  lea     r9, __ImageBase
0x18001bd4f  movzx   edx, byte ptr [rbp+0]
0x18001bd53  neg     eax
0x18001bd55  add     eax, eax
0x18001bd57  and     eax, 3
0x18001bd5a  mov     esi, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bd61  mov     r14d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bd69  movzx   edx, byte ptr [rbp+1]
0x18001bd6d  lea     r10d, [rax+rax*2]
0x18001bd71  movzx   eax, byte ptr [rdi]
0x18001bd74  shl     r10d, 0Ah
0x18001bd78  mov     r8d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bd80  add     esi, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bd87  movzx   eax, byte ptr [rdi+1]
0x18001bd8b  mov     [rsp+88h+var_74], r8d
0x18001bd90  mov     ecx, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bd97  mov     eax, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bd9e  add     eax, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bda5  mov     [rsp+88h+var_70], eax
0x18001bda9  mov     eax, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bdb0  movzx   edx, byte ptr [rbp+2]
0x18001bdb4  mov     [rsp+88h+var_6C], eax
0x18001bdb8  movzx   eax, byte ptr [rdi+2]
0x18001bdbc  mov     [rsp+88h+var_68], ecx
0x18001bdc0  mov     r13d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bdc8  mov     r11d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bdd0  add     r13d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bdd8  mov     r15d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bde0  movzx   eax, byte ptr [rdi+3]
0x18001bde4  movzx   edx, byte ptr [rbp+3]
0x18001bde8  mov     ecx, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bdef  mov     eax, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bdf6  add     eax, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bdfd  mov     [rsp+88h+var_60], eax
0x18001be01  mov     eax, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001be08  movzx   edx, byte ptr [rbp+4]
0x18001be0c  mov     [rsp+88h+var_64], eax
0x18001be10  movzx   eax, byte ptr [rdi+4]
0x18001be14  mov     [rsp+88h+var_80], ecx
0x18001be18  lea     rcx, __ImageBase
0x18001be1f  mov     r12d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001be27  mov     eax, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001be2e  add     eax, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001be35  mov     ebx, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001be3c  movzx   edx, byte ptr [rbp+5]
0x18001be40  lea     rbp, __ImageBase
0x18001be47  mov     [rsp+88h+var_88], eax
0x18001be4a  movzx   eax, byte ptr [rdi+5]
0x18001be4e  mov     ecx, rva ?g_iVtoR@@3PAJA[rcx+rax*4]; long near * g_iVtoR ...
0x18001be55  mov     eax, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001be5c  add     eax, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001be63  mov     [rsp+88h+var_58], eax
0x18001be67  mov     eax, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001be6e  mov     [rsp+88h+var_5C], eax
0x18001be72  movzx   eax, byte ptr [rdi+6]
0x18001be76  lea     rdi, __ImageBase
0x18001be7d  mov     [rsp+88h+var_7C], ecx
0x18001be81  mov     rcx, [rsp+88h+arg_10]
0x18001be89  mov     ebp, rva ?g_iVtoR@@3PAJA[rdi+rax*4]; long near * g_iVtoR ...
0x18001be90  mov     eax, rva ?g_iVtoG@@3PAJA[rdi+rax*4]; long near * g_iVtoG ...
0x18001be97  movzx   edx, byte ptr [rcx+6]
0x18001be9b  lea     rcx, __ImageBase
0x18001bea2  add     eax, rva ?g_iUtoG@@3PAJA[rdi+rdx*4]; long near * g_iUtoG ...
0x18001bea9  mov     edi, rva ?g_iUtoB@@3PAJA[rdi+rdx*4]; long near * g_iUtoB ...
0x18001beb0  mov     [rsp+88h+var_84], eax
0x18001beb4  mov     rax, [rsp+88h+arg_18]
0x18001bebc  movzx   eax, byte ptr [rax+7]
0x18001bec0  mov     ecx, rva ?g_iVtoR@@3PAJA[rcx+rax*4]; long near * g_iVtoR ...
0x18001bec7  mov     eax, rva ?g_iVtoG@@3PAJA[r9+rax*4]; long near * g_iVtoG ...
0x18001becf  mov     r9, [rsp+88h+arg_8]
0x18001bed7  mov     [rsp+88h+var_78], ecx
0x18001bedb  mov     rcx, [rsp+88h+arg_10]
0x18001bee3  movzx   edx, byte ptr [rcx+7]
0x18001bee7  lea     rcx, __ImageBase
0x18001beee  add     eax, rva ?g_iUtoG@@3PAJA[rcx+rdx*4]; long near * g_iUtoG ...
0x18001bef5  lea     rcx, __ImageBase
0x18001befc  mov     [rsp+88h+var_54], eax
0x18001bf00  mov     eax, rva ?g_iUtoB@@3PAJA[rcx+rdx*4]; long near * g_iUtoB ...
0x18001bf07  mov     [rsp+88h+var_50], eax
0x18001bf0b  movzx   eax, byte ptr [r9]
0x18001bf0f  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001bf17  lea     eax, [r9+r8]
0x18001bf1b  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001bf22  movsxd  rcx, eax
0x18001bf25  lea     eax, [r9+r14]
0x18001bf29  sub     r9d, esi
0x18001bf2c  movzx   edx, byte ptr [rcx+r8]
0x18001bf31  movsxd  rcx, eax
0x18001bf34  add     edx, r10d
0x18001bf37  lea     rax, __ImageBase
0x18001bf3e  movzx   ecx, byte ptr [rcx+r8]
0x18001bf43  mov     r8b, [rdx+rax+39B50h]
0x18001bf4b  add     ecx, r10d
0x18001bf4e  lea     rdx, __ImageBase
0x18001bf55  movsxd  rax, r9d
0x18001bf58  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001bf5f  add     r8b, [rcx+rdx+39D50h]
0x18001bf67  movzx   ecx, byte ptr [rax+r9]
0x18001bf6c  mov     rax, [rsp+88h+arg_0]
0x18001bf74  add     ecx, r10d
0x18001bf77  add     r8b, [rcx+rdx+39C50h]
0x18001bf7f  mov     [rax], r8b
0x18001bf82  mov     rcx, [rsp+88h+arg_8]
0x18001bf8a  movzx   eax, byte ptr [rcx+4]
0x18001bf8e  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001bf96  lea     eax, [r8+r11]
0x18001bf9a  movsxd  rcx, eax
0x18001bf9d  mov     eax, r8d
0x18001bfa0  sub     eax, r13d
0x18001bfa3  cdqe
0x18001bfa5  movzx   edx, byte ptr [rcx+r9]
0x18001bfaa  lea     rcx, __ImageBase
0x18001bfb1  add     edx, r10d
0x18001bfb4  movzx   eax, byte ptr [rax+r9]
0x18001bfb9  add     eax, r10d
0x18001bfbc  mov     dl, [rdx+rcx+39D50h]
0x18001bfc3  add     dl, [rax+rcx+39C50h]
0x18001bfca  lea     eax, [r8+r15]
0x18001bfce  movsxd  rcx, eax
0x18001bfd1  lea     r8, __ImageBase
0x18001bfd8  movzx   eax, byte ptr [rcx+r9]
0x18001bfdd  add     eax, r10d
0x18001bfe0  add     dl, [rax+r8+39B50h]
0x18001bfe8  mov     rax, [rsp+88h+arg_0]
0x18001bff0  mov     [rax+4], dl
0x18001bff3  mov     rax, [rsp+88h+arg_8]
0x18001bffb  movzx   eax, byte ptr [rax+8]
0x18001bfff  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001c007  lea     eax, [r8+rbx]
0x18001c00b  movsxd  rcx, eax
0x18001c00e  mov     eax, r8d
0x18001c011  sub     eax, [rsp+88h+var_88]
0x18001c014  cdqe
0x18001c016  movzx   edx, byte ptr [rcx+r9]
0x18001c01b  lea     rcx, __ImageBase
0x18001c022  add     edx, r10d
0x18001c025  movzx   eax, byte ptr [rax+r9]
0x18001c02a  add     eax, r10d
0x18001c02d  mov     dl, [rdx+rcx+39D50h]
0x18001c034  add     dl, [rax+rcx+39C50h]
0x18001c03b  lea     eax, [r8+r12]
0x18001c03f  movsxd  rcx, eax
0x18001c042  lea     r8, __ImageBase
0x18001c049  movzx   eax, byte ptr [rcx+r9]
0x18001c04e  add     eax, r10d
0x18001c051  add     dl, [rax+r8+39B50h]
0x18001c059  mov     rax, [rsp+88h+arg_0]
0x18001c061  mov     [rax+8], dl
0x18001c064  mov     rax, [rsp+88h+arg_8]
0x18001c06c  movzx   eax, byte ptr [rax+0Ch]
0x18001c070  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001c078  lea     eax, [r8+rdi]
0x18001c07c  movsxd  rcx, eax
0x18001c07f  mov     eax, r8d
0x18001c082  sub     eax, [rsp+88h+var_84]
0x18001c086  cdqe
0x18001c088  movzx   edx, byte ptr [rcx+r9]
0x18001c08d  lea     rcx, __ImageBase
0x18001c094  add     edx, r10d
0x18001c097  movzx   eax, byte ptr [rax+r9]
0x18001c09c  add     eax, r10d
0x18001c09f  mov     dl, [rdx+rcx+39D50h]
0x18001c0a6  add     dl, [rax+rcx+39C50h]
0x18001c0ad  lea     eax, [r8+rbp]
0x18001c0b1  movsxd  rcx, eax
0x18001c0b4  lea     r8, __ImageBase
0x18001c0bb  movzx   eax, byte ptr [rcx+r9]
0x18001c0c0  add     eax, r10d
0x18001c0c3  add     r10d, 300h
0x18001c0ca  add     dl, [rax+r8+39B50h]
0x18001c0d2  mov     rax, [rsp+88h+arg_0]
0x18001c0da  mov     [rax+0Ch], dl
0x18001c0dd  mov     rax, [rsp+88h+arg_8]
0x18001c0e5  movzx   eax, byte ptr [rax+1]
0x18001c0e9  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001c0f1  mov     eax, r8d
0x18001c0f4  sub     eax, esi
0x18001c0f6  cdqe
0x18001c0f8  movzx   edx, byte ptr [rax+r9]
0x18001c0fd  lea     eax, [r14+r8]
0x18001c101  movsxd  rcx, eax
0x18001c104  add     edx, r10d
0x18001c107  lea     rax, __ImageBase
0x18001c10e  mov     dl, [rdx+rax+39C50h]
0x18001c115  movzx   ecx, byte ptr [rcx+r9]
0x18001c11a  add     ecx, r10d
0x18001c11d  add     dl, [rcx+rax+39D50h]
0x18001c124  mov     eax, [rsp+88h+var_74]
0x18001c128  add     eax, r8d
0x18001c12b  lea     r8, __ImageBase
0x18001c132  movsxd  rcx, eax
0x18001c135  movzx   eax, byte ptr [rcx+r9]
0x18001c13a  add     eax, r10d
0x18001c13d  add     dl, [rax+r8+39B50h]
0x18001c145  mov     rax, [rsp+88h+arg_0]
0x18001c14d  mov     [rax+1], dl
0x18001c150  mov     rax, [rsp+88h+arg_8]
0x18001c158  movzx   eax, byte ptr [rax+5]
0x18001c15c  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001c164  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c16b  lea     eax, [r11+r9]
0x18001c16f  movsxd  rcx, eax
0x18001c172  lea     eax, [r15+r9]
0x18001c176  sub     r9d, r13d
0x18001c179  movzx   edx, byte ptr [rcx+r8]
0x18001c17e  movsxd  rcx, eax
0x18001c181  add     edx, r10d
0x18001c184  lea     rax, __ImageBase
0x18001c18b  movzx   ecx, byte ptr [rcx+r8]
0x18001c190  mov     r8b, [rdx+rax+39D50h]
0x18001c198  add     ecx, r10d
0x18001c19b  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c1a2  add     r8b, [rcx+rax+39B50h]
0x18001c1aa  lea     rcx, __ImageBase
0x18001c1b1  movsxd  rax, r9d
0x18001c1b4  movzx   eax, byte ptr [rax+rdx]
0x18001c1b8  add     eax, r10d
0x18001c1bb  add     r8b, [rax+rcx+39C50h]
0x18001c1c3  mov     rax, [rsp+88h+arg_0]
0x18001c1cb  mov     [rax+5], r8b
0x18001c1cf  mov     rax, [rsp+88h+arg_8]
0x18001c1d7  movzx   eax, byte ptr [rax+9]
0x18001c1db  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001c1e3  lea     eax, [rbx+r9]
0x18001c1e7  movsxd  rcx, eax
0x18001c1ea  lea     eax, [r12+r9]
0x18001c1ee  sub     r9d, [rsp+88h+var_88]
0x18001c1f2  movzx   edx, byte ptr [rcx+rdx]
0x18001c1f6  movsxd  rcx, eax
0x18001c1f9  add     edx, r10d
0x18001c1fc  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c203  movzx   ecx, byte ptr [rcx+rax]
0x18001c207  lea     rax, __ImageBase
0x18001c20e  mov     r8b, [rdx+rax+39D50h]
0x18001c216  add     ecx, r10d
0x18001c219  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c220  add     r8b, [rcx+rax+39B50h]
0x18001c228  lea     rcx, __ImageBase
0x18001c22f  movsxd  rax, r9d
0x18001c232  movzx   eax, byte ptr [rax+rdx]
0x18001c236  add     eax, r10d
0x18001c239  add     r8b, [rax+rcx+39C50h]
0x18001c241  mov     rax, [rsp+88h+arg_0]
0x18001c249  mov     [rax+9], r8b
0x18001c24d  mov     rax, [rsp+88h+arg_8]
0x18001c255  movzx   eax, byte ptr [rax+0Dh]
0x18001c259  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001c261  lea     eax, [rdi+r9]
0x18001c265  movsxd  rcx, eax
0x18001c268  lea     eax, [r9+rbp]
0x18001c26c  sub     r9d, [rsp+88h+var_84]
0x18001c271  movzx   edx, byte ptr [rcx+rdx]
0x18001c275  movsxd  rcx, eax
0x18001c278  add     edx, r10d
0x18001c27b  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c282  movzx   ecx, byte ptr [rcx+rax]
0x18001c286  lea     rax, __ImageBase
0x18001c28d  mov     r8b, [rdx+rax+39D50h]
0x18001c295  add     ecx, r10d
0x18001c298  lea     rdx, __ImageBase
0x18001c29f  movsxd  rax, r9d
0x18001c2a2  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c2a9  add     r8b, [rcx+rdx+39B50h]
0x18001c2b1  movzx   ecx, byte ptr [rax+r9]
0x18001c2b6  mov     rax, [rsp+88h+arg_0]
0x18001c2be  add     ecx, r10d
0x18001c2c1  add     r10d, 300h
0x18001c2c8  add     r8b, [rcx+rdx+39C50h]
0x18001c2d0  mov     [rax+0Dh], r8b
0x18001c2d4  mov     rax, [rsp+88h+arg_8]
0x18001c2dc  movzx   eax, byte ptr [rax+2]
0x18001c2e0  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001c2e8  mov     eax, r8d
0x18001c2eb  sub     eax, [rsp+88h+var_70]
0x18001c2ef  cdqe
0x18001c2f1  movzx   edx, byte ptr [rax+r9]
0x18001c2f6  mov     eax, [rsp+88h+var_6C]
0x18001c2fa  add     edx, r10d
0x18001c2fd  add     eax, r8d
0x18001c300  movsxd  rcx, eax
  ... truncated ...
```

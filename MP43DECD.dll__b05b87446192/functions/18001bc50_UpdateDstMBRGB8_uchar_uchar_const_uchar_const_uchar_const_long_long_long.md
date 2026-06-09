# UpdateDstMBRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001bc50`
- end: `0x18001ce28`
- name: `?UpdateDstMBRGB8@@YAXPEAEPEBE11JJJ@Z`
- size: `4568`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d8c0`

## callees

- `0x18001bc50`

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
0x18001bc50  mov     rax, rsp
0x18001bc53  mov     [rax+20h], r9
0x18001bc57  mov     [rax+18h], r8
0x18001bc5b  mov     [rax+10h], rdx
0x18001bc5f  mov     [rax+8], rcx
0x18001bc63  push    rbx
0x18001bc64  push    rbp
0x18001bc65  push    rsi
0x18001bc66  push    rdi
0x18001bc67  push    r12
0x18001bc69  push    r13
0x18001bc6b  push    r14
0x18001bc6d  push    r15
0x18001bc6f  sub     rsp, 48h
0x18001bc73  xor     edx, edx
0x18001bc75  lea     rbx, __ImageBase
0x18001bc7c  mov     [rsp+88h+var_4C], edx
0x18001bc80  mov     rdi, r9
0x18001bc83  mov     rbp, r8
0x18001bc86  mov     eax, edx
0x18001bc88  lea     r9, __ImageBase
0x18001bc8f  movzx   edx, byte ptr [rbp+0]
0x18001bc93  neg     eax
0x18001bc95  add     eax, eax
0x18001bc97  and     eax, 3
0x18001bc9a  mov     esi, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bca1  mov     r14d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bca9  movzx   edx, byte ptr [rbp+1]
0x18001bcad  lea     r10d, [rax+rax*2]
0x18001bcb1  movzx   eax, byte ptr [rdi]
0x18001bcb4  shl     r10d, 0Ah
0x18001bcb8  mov     r8d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bcc0  add     esi, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bcc7  movzx   eax, byte ptr [rdi+1]
0x18001bccb  mov     [rsp+88h+var_74], r8d
0x18001bcd0  mov     ecx, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bcd7  mov     eax, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bcde  add     eax, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bce5  mov     [rsp+88h+var_70], eax
0x18001bce9  mov     eax, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bcf0  movzx   edx, byte ptr [rbp+2]
0x18001bcf4  mov     [rsp+88h+var_6C], eax
0x18001bcf8  movzx   eax, byte ptr [rdi+2]
0x18001bcfc  mov     [rsp+88h+var_68], ecx
0x18001bd00  mov     r13d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bd08  mov     r11d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bd10  add     r13d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bd18  mov     r15d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bd20  movzx   eax, byte ptr [rdi+3]
0x18001bd24  movzx   edx, byte ptr [rbp+3]
0x18001bd28  mov     ecx, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bd2f  mov     eax, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bd36  add     eax, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bd3d  mov     [rsp+88h+var_60], eax
0x18001bd41  mov     eax, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bd48  movzx   edx, byte ptr [rbp+4]
0x18001bd4c  mov     [rsp+88h+var_64], eax
0x18001bd50  movzx   eax, byte ptr [rdi+4]
0x18001bd54  mov     [rsp+88h+var_80], ecx
0x18001bd58  lea     rcx, __ImageBase
0x18001bd5f  mov     r12d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x18001bd67  mov     eax, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001bd6e  add     eax, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x18001bd75  mov     ebx, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001bd7c  movzx   edx, byte ptr [rbp+5]
0x18001bd80  lea     rbp, __ImageBase
0x18001bd87  mov     [rsp+88h+var_88], eax
0x18001bd8a  movzx   eax, byte ptr [rdi+5]
0x18001bd8e  mov     ecx, rva ?g_iVtoR@@3PAJA[rcx+rax*4]; long near * g_iVtoR ...
0x18001bd95  mov     eax, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001bd9c  add     eax, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001bda3  mov     [rsp+88h+var_58], eax
0x18001bda7  mov     eax, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001bdae  mov     [rsp+88h+var_5C], eax
0x18001bdb2  movzx   eax, byte ptr [rdi+6]
0x18001bdb6  lea     rdi, __ImageBase
0x18001bdbd  mov     [rsp+88h+var_7C], ecx
0x18001bdc1  mov     rcx, [rsp+88h+arg_10]
0x18001bdc9  mov     ebp, rva ?g_iVtoR@@3PAJA[rdi+rax*4]; long near * g_iVtoR ...
0x18001bdd0  mov     eax, rva ?g_iVtoG@@3PAJA[rdi+rax*4]; long near * g_iVtoG ...
0x18001bdd7  movzx   edx, byte ptr [rcx+6]
0x18001bddb  lea     rcx, __ImageBase
0x18001bde2  add     eax, rva ?g_iUtoG@@3PAJA[rdi+rdx*4]; long near * g_iUtoG ...
0x18001bde9  mov     edi, rva ?g_iUtoB@@3PAJA[rdi+rdx*4]; long near * g_iUtoB ...
0x18001bdf0  mov     [rsp+88h+var_84], eax
0x18001bdf4  mov     rax, [rsp+88h+arg_18]
0x18001bdfc  movzx   eax, byte ptr [rax+7]
0x18001be00  mov     ecx, rva ?g_iVtoR@@3PAJA[rcx+rax*4]; long near * g_iVtoR ...
0x18001be07  mov     eax, rva ?g_iVtoG@@3PAJA[r9+rax*4]; long near * g_iVtoG ...
0x18001be0f  mov     r9, [rsp+88h+arg_8]
0x18001be17  mov     [rsp+88h+var_78], ecx
0x18001be1b  mov     rcx, [rsp+88h+arg_10]
0x18001be23  movzx   edx, byte ptr [rcx+7]
0x18001be27  lea     rcx, __ImageBase
0x18001be2e  add     eax, rva ?g_iUtoG@@3PAJA[rcx+rdx*4]; long near * g_iUtoG ...
0x18001be35  lea     rcx, __ImageBase
0x18001be3c  mov     [rsp+88h+var_54], eax
0x18001be40  mov     eax, rva ?g_iUtoB@@3PAJA[rcx+rdx*4]; long near * g_iUtoB ...
0x18001be47  mov     [rsp+88h+var_50], eax
0x18001be4b  movzx   eax, byte ptr [r9]
0x18001be4f  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001be57  lea     eax, [r9+r8]
0x18001be5b  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001be62  movsxd  rcx, eax
0x18001be65  lea     eax, [r9+r14]
0x18001be69  sub     r9d, esi
0x18001be6c  movzx   edx, byte ptr [rcx+r8]
0x18001be71  movsxd  rcx, eax
0x18001be74  add     edx, r10d
0x18001be77  lea     rax, __ImageBase
0x18001be7e  movzx   ecx, byte ptr [rcx+r8]
0x18001be83  mov     r8b, [rdx+rax+39B10h]
0x18001be8b  add     ecx, r10d
0x18001be8e  lea     rdx, __ImageBase
0x18001be95  movsxd  rax, r9d
0x18001be98  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001be9f  add     r8b, [rcx+rdx+39D10h]
0x18001bea7  movzx   ecx, byte ptr [rax+r9]
0x18001beac  mov     rax, [rsp+88h+arg_0]
0x18001beb4  add     ecx, r10d
0x18001beb7  add     r8b, [rcx+rdx+39C10h]
0x18001bebf  mov     [rax], r8b
0x18001bec2  mov     rcx, [rsp+88h+arg_8]
0x18001beca  movzx   eax, byte ptr [rcx+4]
0x18001bece  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001bed6  lea     eax, [r8+r11]
0x18001beda  movsxd  rcx, eax
0x18001bedd  mov     eax, r8d
0x18001bee0  sub     eax, r13d
0x18001bee3  cdqe
0x18001bee5  movzx   edx, byte ptr [rcx+r9]
0x18001beea  lea     rcx, __ImageBase
0x18001bef1  add     edx, r10d
0x18001bef4  movzx   eax, byte ptr [rax+r9]
0x18001bef9  add     eax, r10d
0x18001befc  mov     dl, [rdx+rcx+39D10h]
0x18001bf03  add     dl, [rax+rcx+39C10h]
0x18001bf0a  lea     eax, [r8+r15]
0x18001bf0e  movsxd  rcx, eax
0x18001bf11  lea     r8, __ImageBase
0x18001bf18  movzx   eax, byte ptr [rcx+r9]
0x18001bf1d  add     eax, r10d
0x18001bf20  add     dl, [rax+r8+39B10h]
0x18001bf28  mov     rax, [rsp+88h+arg_0]
0x18001bf30  mov     [rax+4], dl
0x18001bf33  mov     rax, [rsp+88h+arg_8]
0x18001bf3b  movzx   eax, byte ptr [rax+8]
0x18001bf3f  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001bf47  lea     eax, [r8+rbx]
0x18001bf4b  movsxd  rcx, eax
0x18001bf4e  mov     eax, r8d
0x18001bf51  sub     eax, [rsp+88h+var_88]
0x18001bf54  cdqe
0x18001bf56  movzx   edx, byte ptr [rcx+r9]
0x18001bf5b  lea     rcx, __ImageBase
0x18001bf62  add     edx, r10d
0x18001bf65  movzx   eax, byte ptr [rax+r9]
0x18001bf6a  add     eax, r10d
0x18001bf6d  mov     dl, [rdx+rcx+39D10h]
0x18001bf74  add     dl, [rax+rcx+39C10h]
0x18001bf7b  lea     eax, [r8+r12]
0x18001bf7f  movsxd  rcx, eax
0x18001bf82  lea     r8, __ImageBase
0x18001bf89  movzx   eax, byte ptr [rcx+r9]
0x18001bf8e  add     eax, r10d
0x18001bf91  add     dl, [rax+r8+39B10h]
0x18001bf99  mov     rax, [rsp+88h+arg_0]
0x18001bfa1  mov     [rax+8], dl
0x18001bfa4  mov     rax, [rsp+88h+arg_8]
0x18001bfac  movzx   eax, byte ptr [rax+0Ch]
0x18001bfb0  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001bfb8  lea     eax, [r8+rdi]
0x18001bfbc  movsxd  rcx, eax
0x18001bfbf  mov     eax, r8d
0x18001bfc2  sub     eax, [rsp+88h+var_84]
0x18001bfc6  cdqe
0x18001bfc8  movzx   edx, byte ptr [rcx+r9]
0x18001bfcd  lea     rcx, __ImageBase
0x18001bfd4  add     edx, r10d
0x18001bfd7  movzx   eax, byte ptr [rax+r9]
0x18001bfdc  add     eax, r10d
0x18001bfdf  mov     dl, [rdx+rcx+39D10h]
0x18001bfe6  add     dl, [rax+rcx+39C10h]
0x18001bfed  lea     eax, [r8+rbp]
0x18001bff1  movsxd  rcx, eax
0x18001bff4  lea     r8, __ImageBase
0x18001bffb  movzx   eax, byte ptr [rcx+r9]
0x18001c000  add     eax, r10d
0x18001c003  add     r10d, 300h
0x18001c00a  add     dl, [rax+r8+39B10h]
0x18001c012  mov     rax, [rsp+88h+arg_0]
0x18001c01a  mov     [rax+0Ch], dl
0x18001c01d  mov     rax, [rsp+88h+arg_8]
0x18001c025  movzx   eax, byte ptr [rax+1]
0x18001c029  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001c031  mov     eax, r8d
0x18001c034  sub     eax, esi
0x18001c036  cdqe
0x18001c038  movzx   edx, byte ptr [rax+r9]
0x18001c03d  lea     eax, [r14+r8]
0x18001c041  movsxd  rcx, eax
0x18001c044  add     edx, r10d
0x18001c047  lea     rax, __ImageBase
0x18001c04e  mov     dl, [rdx+rax+39C10h]
0x18001c055  movzx   ecx, byte ptr [rcx+r9]
0x18001c05a  add     ecx, r10d
0x18001c05d  add     dl, [rcx+rax+39D10h]
0x18001c064  mov     eax, [rsp+88h+var_74]
0x18001c068  add     eax, r8d
0x18001c06b  lea     r8, __ImageBase
0x18001c072  movsxd  rcx, eax
0x18001c075  movzx   eax, byte ptr [rcx+r9]
0x18001c07a  add     eax, r10d
0x18001c07d  add     dl, [rax+r8+39B10h]
0x18001c085  mov     rax, [rsp+88h+arg_0]
0x18001c08d  mov     [rax+1], dl
0x18001c090  mov     rax, [rsp+88h+arg_8]
0x18001c098  movzx   eax, byte ptr [rax+5]
0x18001c09c  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x18001c0a4  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c0ab  lea     eax, [r11+r9]
0x18001c0af  movsxd  rcx, eax
0x18001c0b2  lea     eax, [r15+r9]
0x18001c0b6  sub     r9d, r13d
0x18001c0b9  movzx   edx, byte ptr [rcx+r8]
0x18001c0be  movsxd  rcx, eax
0x18001c0c1  add     edx, r10d
0x18001c0c4  lea     rax, __ImageBase
0x18001c0cb  movzx   ecx, byte ptr [rcx+r8]
0x18001c0d0  mov     r8b, [rdx+rax+39D10h]
0x18001c0d8  add     ecx, r10d
0x18001c0db  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c0e2  add     r8b, [rcx+rax+39B10h]
0x18001c0ea  lea     rcx, __ImageBase
0x18001c0f1  movsxd  rax, r9d
0x18001c0f4  movzx   eax, byte ptr [rax+rdx]
0x18001c0f8  add     eax, r10d
0x18001c0fb  add     r8b, [rax+rcx+39C10h]
0x18001c103  mov     rax, [rsp+88h+arg_0]
0x18001c10b  mov     [rax+5], r8b
0x18001c10f  mov     rax, [rsp+88h+arg_8]
0x18001c117  movzx   eax, byte ptr [rax+9]
0x18001c11b  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001c123  lea     eax, [rbx+r9]
0x18001c127  movsxd  rcx, eax
0x18001c12a  lea     eax, [r12+r9]
0x18001c12e  sub     r9d, [rsp+88h+var_88]
0x18001c132  movzx   edx, byte ptr [rcx+rdx]
0x18001c136  movsxd  rcx, eax
0x18001c139  add     edx, r10d
0x18001c13c  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c143  movzx   ecx, byte ptr [rcx+rax]
0x18001c147  lea     rax, __ImageBase
0x18001c14e  mov     r8b, [rdx+rax+39D10h]
0x18001c156  add     ecx, r10d
0x18001c159  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c160  add     r8b, [rcx+rax+39B10h]
0x18001c168  lea     rcx, __ImageBase
0x18001c16f  movsxd  rax, r9d
0x18001c172  movzx   eax, byte ptr [rax+rdx]
0x18001c176  add     eax, r10d
0x18001c179  add     r8b, [rax+rcx+39C10h]
0x18001c181  mov     rax, [rsp+88h+arg_0]
0x18001c189  mov     [rax+9], r8b
0x18001c18d  mov     rax, [rsp+88h+arg_8]
0x18001c195  movzx   eax, byte ptr [rax+0Dh]
0x18001c199  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001c1a1  lea     eax, [rdi+r9]
0x18001c1a5  movsxd  rcx, eax
0x18001c1a8  lea     eax, [r9+rbp]
0x18001c1ac  sub     r9d, [rsp+88h+var_84]
0x18001c1b1  movzx   edx, byte ptr [rcx+rdx]
0x18001c1b5  movsxd  rcx, eax
0x18001c1b8  add     edx, r10d
0x18001c1bb  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c1c2  movzx   ecx, byte ptr [rcx+rax]
0x18001c1c6  lea     rax, __ImageBase
0x18001c1cd  mov     r8b, [rdx+rax+39D10h]
0x18001c1d5  add     ecx, r10d
0x18001c1d8  lea     rdx, __ImageBase
0x18001c1df  movsxd  rax, r9d
0x18001c1e2  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001c1e9  add     r8b, [rcx+rdx+39B10h]
0x18001c1f1  movzx   ecx, byte ptr [rax+r9]
0x18001c1f6  mov     rax, [rsp+88h+arg_0]
0x18001c1fe  add     ecx, r10d
0x18001c201  add     r10d, 300h
0x18001c208  add     r8b, [rcx+rdx+39C10h]
0x18001c210  mov     [rax+0Dh], r8b
0x18001c214  mov     rax, [rsp+88h+arg_8]
0x18001c21c  movzx   eax, byte ptr [rax+2]
0x18001c220  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001c228  mov     eax, r8d
0x18001c22b  sub     eax, [rsp+88h+var_70]
0x18001c22f  cdqe
0x18001c231  movzx   edx, byte ptr [rax+r9]
0x18001c236  mov     eax, [rsp+88h+var_6C]
0x18001c23a  add     edx, r10d
0x18001c23d  add     eax, r8d
0x18001c240  movsxd  rcx, eax
  ... truncated ...
```

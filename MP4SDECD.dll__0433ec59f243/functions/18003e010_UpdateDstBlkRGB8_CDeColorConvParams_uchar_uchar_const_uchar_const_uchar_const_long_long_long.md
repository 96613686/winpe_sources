# UpdateDstBlkRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003e010`
- end: `0x18003e8b6`
- name: `?UpdateDstBlkRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `2214`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003e010`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB8(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  const unsigned __int8 *v8; // r12
  const unsigned __int8 *v9; // r9
  char v10; // al
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // edi
  __int64 v14; // rdx
  int v15; // r10d
  __int64 v16; // rax
  int v17; // r15d
  int v18; // ebx
  int v19; // r14d
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rdx
  __int64 v23; // rax
  int v24; // r11d
  int v25; // ebp
  int v26; // esi
  __int64 v27; // rax
  __int64 v28; // rdx
  int v29; // r13d
  int v30; // r12d
  __int64 v31; // rax
  __int64 v32; // r9
  int v33; // r8d
  int v34; // r8d
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r9
  __int64 v38; // rcx
  int v39; // r8d
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // r9
  int v45; // r8d
  int v46; // r10d
  __int64 v47; // rcx
  int v48; // r8d
  __int64 v49; // rbx
  __int64 v50; // rcx
  int v51; // r8d
  __int64 v52; // rcx
  __int64 v53; // rax
  int v54; // r8d
  int v55; // [rsp+0h] [rbp-48h]
  int v56; // [rsp+4h] [rbp-44h]
  int v57; // [rsp+8h] [rbp-40h]
  int v58; // [rsp+Ch] [rbp-3Ch]
  unsigned __int8 *v59; // [rsp+58h] [rbp+10h]
  const unsigned __int8 *v60; // [rsp+60h] [rbp+18h]
  const unsigned __int8 *v61; // [rsp+68h] [rbp+20h]

  v61 = a4;
  v60 = a3;
  v59 = a2;
  LOBYTE(a2) = 0;
  v8 = a4;
  v58 = 0;
  v9 = a3;
  do
  {
    v10 = (char)a2;
    v11 = *v8;
    v12 = g_iUtoG[v11];
    v13 = g_iUtoB[v11];
    v14 = v8[1];
    v15 = 3 * ((-2 * v10) & 3);
    v16 = *a5;
    v15 <<= 10;
    v17 = g_iUtoB[v14];
    v18 = g_iVtoG[v16] + v12;
    v19 = g_iVtoR[v16];
    v20 = a5[1];
    v21 = g_iVtoR[v20];
    LODWORD(v20) = g_iUtoG[v14] + g_iVtoG[v20];
    v22 = v8[2];
    v55 = v20;
    v23 = a5[2];
    v56 = v21;
    v24 = g_iUtoB[v22];
    v25 = g_iVtoG[v23] + g_iUtoG[v22];
    v26 = g_iVtoR[v23];
    v27 = a5[3];
    v28 = v8[3];
    v29 = g_iVtoR[v27];
    v30 = g_iVtoG[v27] + g_iUtoG[v28];
    v57 = g_iUtoB[v28];
    v31 = *v9;
    v32 = g_rgiClapTabDec;
    *v59 = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v19 + g_iYscale[v31] + g_rgiClapTabDec))
         + *((_BYTE *)&g_rgDitherMap
           + v15
           + (unsigned int)*(unsigned __int8 *)(v13 + g_iYscale[v31] + g_rgiClapTabDec)
           + 512)
         + *((_BYTE *)&g_rgDitherMap
           + v15
           + (unsigned int)*(unsigned __int8 *)(g_iYscale[v31] - v18 + g_rgiClapTabDec)
           + 256);
    v33 = g_iYscale[v60[4]];
    v59[4] = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v26 + v33 + v32))
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v24 + v33 + v32) + 512)
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v33 - v25 + v32) + 256);
    v15 += 768;
    v34 = g_iYscale[v60[1]];
    v59[1] = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v19 + v34 + v32))
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v13 + v34 + v32) + 512)
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v34 - v18 + v32) + 256);
    LODWORD(v32) = g_iYscale[v60[5]];
    LOBYTE(v34) = *((_BYTE *)&g_rgDitherMap
                  + v15
                  + (unsigned int)*(unsigned __int8 *)(v24 + (int)v32 + g_rgiClapTabDec)
                  + 512);
    v35 = v15 + (unsigned int)*(unsigned __int8 *)(v26 + (int)v32 + g_rgiClapTabDec);
    v36 = (int)v32 - v25;
    v37 = g_rgiClapTabDec;
    LOBYTE(v34) = *((_BYTE *)&g_rgDitherMap + v35) + v34;
    v38 = v15 + (unsigned int)*(unsigned __int8 *)(v36 + g_rgiClapTabDec);
    v15 += 768;
    v59[5] = *((_BYTE *)&g_rgDitherMap + v38 + 256) + v34;
    v39 = g_iYscale[v60[2]];
    v59[2] = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v39 + v56 + v37))
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v17 + v39 + v37) + 512)
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v39 - v55 + v37) + 256);
    LODWORD(v37) = g_iYscale[v60[6]];
    v40 = g_rgiClapTabDec;
    LOBYTE(v39) = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)((int)v37 + v29 + g_rgiClapTabDec))
                + *((_BYTE *)&g_rgDitherMap
                  + v15
                  + (unsigned int)*(unsigned __int8 *)((int)v37 + v57 + g_rgiClapTabDec)
                  + 512);
    v41 = v15 + (unsigned int)*(unsigned __int8 *)((int)v37 - v30 + g_rgiClapTabDec);
    v15 += 768;
    v59[6] = *((_BYTE *)&g_rgDitherMap + v41 + 256) + v39;
    LODWORD(v37) = g_iYscale[v60[3]];
    LOBYTE(v39) = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v17 + (int)v37 + v40) + 512);
    v42 = v15 + (unsigned int)*(unsigned __int8 *)((int)v37 + v56 + g_rgiClapTabDec);
    v43 = (int)v37 - v55;
    v44 = g_rgiClapTabDec;
    v59[3] = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v43 + g_rgiClapTabDec) + 256)
           + *((_BYTE *)&g_rgDitherMap + v42)
           + v39;
    v45 = g_iYscale[v60[7]];
    v59[7] = *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v45 + v57 + v44) + 512)
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v45 - v30 + v44) + 256)
           + *((_BYTE *)&g_rgDitherMap + v15 + (unsigned int)*(unsigned __int8 *)(v45 + v29 + v44));
    v61 += a7;
    a5 += a7;
    v46 = 3072 * ((1 - 2 * (_BYTE)v58) & 3);
    LODWORD(v44) = g_iYscale[v60[a6]];
    a2 = (unsigned __int8 *)g_rgiClapTabDec;
    v59[a8] = *((_BYTE *)&g_rgDitherMap
              + v46
              + (unsigned int)*(unsigned __int8 *)((int)v44 - v18 + g_rgiClapTabDec)
              + 256)
            + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v19 + (int)v44 + g_rgiClapTabDec))
            + *((_BYTE *)&g_rgDitherMap
              + v46
              + (unsigned int)*(unsigned __int8 *)(v13 + (int)v44 + g_rgiClapTabDec)
              + 512);
    LODWORD(v44) = g_iYscale[v60[a6 + 4]];
    LOBYTE(v45) = *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v26 + (int)v44 + g_rgiClapTabDec))
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)a2[v24 + (int)v44] + 512);
    v47 = v46 + (unsigned int)*(unsigned __int8 *)((int)v44 - v25 + g_rgiClapTabDec);
    v46 += 768;
    v59[a8 + 4] = *((_BYTE *)&g_rgDitherMap + v47 + 256) + v45;
    v48 = g_iYscale[v60[a6 + 1]];
    LODWORD(v43) = v48 - v18;
    v49 = g_rgiClapTabDec;
    v59[a8 + 1] = *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v19 + v48 + g_rgiClapTabDec))
                + *((_BYTE *)&g_rgDitherMap + v46
                                            + (unsigned int)*(unsigned __int8 *)(v13 + v48 + g_rgiClapTabDec)
                                            + 512)
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)((int)v43 + g_rgiClapTabDec) + 256);
    LODWORD(v44) = g_iYscale[v60[a6 + 5]];
    LOBYTE(v48) = *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v26 + (int)v44 + v49))
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v24 + (int)v44 + v49) + 512);
    v50 = v46 + (unsigned int)*(unsigned __int8 *)((int)v44 - v25 + v49);
    v46 += 768;
    v59[a8 + 5] = *((_BYTE *)&g_rgDitherMap + v50 + 256) + v48;
    v51 = g_iYscale[v60[a6 + 2]];
    v59[a8 + 2] = *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v56 + v51 + v49))
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v17 + v51 + v49) + 512)
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v51 - v55 + v49) + 256);
    LODWORD(v44) = g_iYscale[v60[a6 + 6]];
    LOBYTE(v51) = *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)((int)v44 + v29 + v49))
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v57 + (int)v44 + v49) + 512);
    v52 = v46 + (unsigned int)*(unsigned __int8 *)((int)v44 - v30 + v49);
    v46 += 768;
    v59[a8 + 6] = *((_BYTE *)&g_rgDitherMap + v52 + 256) + v51;
    LODWORD(v44) = g_iYscale[v60[a6 + 3]];
    v59[a8 + 3] = *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)((int)v44 - v55 + v49) + 256)
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v56 + (int)v44 + v49))
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v17 + (int)v44 + v49) + 512);
    v53 = v60[a6 + 7];
    v9 = &v60[2 * a6];
    v60 = v9;
    v54 = g_iYscale[v53];
    LODWORD(v53) = v54 - v30;
    v8 = v61;
    v59[a8 + 7] = *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v57 + v54 + v49) + 512)
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)((int)v53 + v49) + 256)
                + *((_BYTE *)&g_rgDitherMap + v46 + (unsigned int)*(unsigned __int8 *)(v54 + v29 + v49));
    LODWORD(a2) = v58 + 1;
    v59 += 2 * a8;
    v58 = (int)a2;
  }
  while ( (unsigned int)a2 < 4 );
}

```

## disassembly

```asm
0x18003e010  mov     rax, rsp
0x18003e013  mov     [rax+8], rbx
0x18003e017  mov     [rax+20h], r9
0x18003e01b  mov     [rax+18h], r8
0x18003e01f  mov     [rax+10h], rdx
0x18003e023  push    rbp
0x18003e024  push    rsi
0x18003e025  push    rdi
0x18003e026  push    r12
0x18003e028  push    r13
0x18003e02a  push    r14
0x18003e02c  push    r15
0x18003e02e  sub     rsp, 10h
0x18003e032  xor     edx, edx
0x18003e034  lea     r13, __ImageBase
0x18003e03b  mov     r12, r9
0x18003e03e  mov     [rsp+48h+var_3C], edx
0x18003e042  mov     r9, r8
0x18003e045  mov     r8, [rsp+48h+arg_20]
0x18003e04a  mov     eax, edx
0x18003e04c  movzx   edx, byte ptr [r12]
0x18003e051  neg     eax
0x18003e053  add     eax, eax
0x18003e055  and     eax, 3
0x18003e058  mov     ebx, rva g_iUtoG[r13+rdx*4]
0x18003e060  mov     edi, rva g_iUtoB[r13+rdx*4]
0x18003e068  movzx   edx, byte ptr [r12+1]
0x18003e06e  lea     r10d, [rax+rax*2]
0x18003e072  movzx   eax, byte ptr [r8]
0x18003e076  shl     r10d, 0Ah
0x18003e07a  mov     r15d, rva g_iUtoB[r13+rdx*4]
0x18003e082  add     ebx, rva g_iVtoG[r13+rax*4]
0x18003e08a  mov     r14d, rva g_iVtoR[r13+rax*4]
0x18003e092  movzx   eax, byte ptr [r8+1]
0x18003e097  mov     ecx, rva g_iVtoR[r13+rax*4]
0x18003e09f  mov     eax, rva g_iVtoG[r13+rax*4]
0x18003e0a7  add     eax, rva g_iUtoG[r13+rdx*4]
0x18003e0af  movzx   edx, byte ptr [r12+2]
0x18003e0b5  mov     [rsp+48h+var_48], eax
0x18003e0b8  movzx   eax, byte ptr [r8+2]
0x18003e0bd  mov     [rsp+48h+var_44], ecx
0x18003e0c1  mov     ebp, rva g_iUtoG[r13+rdx*4]
0x18003e0c9  mov     r11d, rva g_iUtoB[r13+rdx*4]
0x18003e0d1  add     ebp, rva g_iVtoG[r13+rax*4]
0x18003e0d9  mov     esi, rva g_iVtoR[r13+rax*4]
0x18003e0e1  movzx   eax, byte ptr [r8+3]
0x18003e0e6  lea     r8, __ImageBase
0x18003e0ed  movzx   edx, byte ptr [r12+3]
0x18003e0f3  mov     r13d, rva g_iVtoR[r13+rax*4]
0x18003e0fb  mov     r12d, rva g_iUtoG[r8+rdx*4]
0x18003e103  add     r12d, rva g_iVtoG[r8+rax*4]
0x18003e10b  mov     eax, rva g_iUtoB[r8+rdx*4]
0x18003e113  mov     [rsp+48h+var_40], eax
0x18003e117  movzx   eax, byte ptr [r9]
0x18003e11b  mov     r9, cs:g_rgiClapTabDec
0x18003e122  mov     r8d, rva g_iYscale[r8+rax*4]
0x18003e12a  mov     eax, r8d
0x18003e12d  sub     eax, ebx
0x18003e12f  cdqe
0x18003e131  movzx   edx, byte ptr [rax+r9]
0x18003e136  lea     eax, [rdi+r8]
0x18003e13a  movsxd  rcx, eax
0x18003e13d  add     edx, r10d
0x18003e140  lea     rax, __ImageBase
0x18003e147  mov     dl, [rdx+rax+59900h]
0x18003e14e  movzx   ecx, byte ptr [rcx+r9]
0x18003e153  add     ecx, r10d
0x18003e156  add     dl, [rcx+rax+59A00h]
0x18003e15d  lea     eax, [r14+r8]
0x18003e161  movsxd  rcx, eax
0x18003e164  lea     r8, __ImageBase
0x18003e16b  movzx   eax, byte ptr [rcx+r9]
0x18003e170  mov     rcx, [rsp+48h+arg_8]
0x18003e175  add     eax, r10d
0x18003e178  add     dl, [rax+r8+59800h]
0x18003e180  mov     rax, [rsp+48h+arg_10]
0x18003e185  mov     [rcx], dl
0x18003e187  movzx   eax, byte ptr [rax+4]
0x18003e18b  mov     r8d, rva g_iYscale[r8+rax*4]
0x18003e193  mov     eax, r8d
0x18003e196  sub     eax, ebp
0x18003e198  cdqe
0x18003e19a  movzx   edx, byte ptr [rax+r9]
0x18003e19f  lea     eax, [r11+r8]
0x18003e1a3  movsxd  rcx, eax
0x18003e1a6  add     edx, r10d
0x18003e1a9  lea     rax, __ImageBase
0x18003e1b0  mov     dl, [rdx+rax+59900h]
0x18003e1b7  movzx   ecx, byte ptr [rcx+r9]
0x18003e1bc  add     ecx, r10d
0x18003e1bf  add     dl, [rcx+rax+59A00h]
0x18003e1c6  lea     eax, [rsi+r8]
0x18003e1ca  movsxd  rcx, eax
0x18003e1cd  lea     r8, __ImageBase
0x18003e1d4  movzx   eax, byte ptr [rcx+r9]
0x18003e1d9  add     eax, r10d
0x18003e1dc  add     dl, [rax+r8+59800h]
0x18003e1e4  mov     rax, [rsp+48h+arg_8]
0x18003e1e9  mov     [rax+4], dl
0x18003e1ec  mov     rax, [rsp+48h+arg_10]
0x18003e1f1  add     r10d, 300h
0x18003e1f8  movzx   eax, byte ptr [rax+1]
0x18003e1fc  mov     r8d, rva g_iYscale[r8+rax*4]
0x18003e204  mov     eax, r8d
0x18003e207  sub     eax, ebx
0x18003e209  cdqe
0x18003e20b  movzx   edx, byte ptr [rax+r9]
0x18003e210  lea     eax, [rdi+r8]
0x18003e214  movsxd  rcx, eax
0x18003e217  add     edx, r10d
0x18003e21a  lea     rax, __ImageBase
0x18003e221  mov     dl, [rdx+rax+59900h]
0x18003e228  movzx   ecx, byte ptr [rcx+r9]
0x18003e22d  add     ecx, r10d
0x18003e230  add     dl, [rcx+rax+59A00h]
0x18003e237  lea     eax, [r14+r8]
0x18003e23b  movsxd  rcx, eax
0x18003e23e  lea     r8, __ImageBase
0x18003e245  movzx   eax, byte ptr [rcx+r9]
0x18003e24a  add     eax, r10d
0x18003e24d  add     dl, [rax+r8+59800h]
0x18003e255  mov     rax, [rsp+48h+arg_8]
0x18003e25a  mov     [rax+1], dl
0x18003e25d  mov     rax, [rsp+48h+arg_10]
0x18003e262  movzx   eax, byte ptr [rax+5]
0x18003e266  mov     r9d, rva g_iYscale[r8+rax*4]
0x18003e26e  mov     r8, cs:g_rgiClapTabDec
0x18003e275  lea     eax, [r11+r9]
0x18003e279  movsxd  rcx, eax
0x18003e27c  lea     eax, [rsi+r9]
0x18003e280  sub     r9d, ebp
0x18003e283  movzx   edx, byte ptr [rcx+r8]
0x18003e288  movsxd  rcx, eax
0x18003e28b  add     edx, r10d
0x18003e28e  lea     rax, __ImageBase
0x18003e295  movzx   ecx, byte ptr [rcx+r8]
0x18003e29a  mov     r8b, [rdx+rax+59A00h]
0x18003e2a2  add     ecx, r10d
0x18003e2a5  lea     rdx, __ImageBase
0x18003e2ac  movsxd  rax, r9d
0x18003e2af  mov     r9, cs:g_rgiClapTabDec
0x18003e2b6  add     r8b, [rcx+rdx+59800h]
0x18003e2be  movzx   ecx, byte ptr [rax+r9]
0x18003e2c3  mov     rax, [rsp+48h+arg_8]
0x18003e2c8  add     ecx, r10d
0x18003e2cb  add     r10d, 300h
0x18003e2d2  add     r8b, [rcx+rdx+59900h]
0x18003e2da  mov     [rax+5], r8b
0x18003e2de  mov     rax, [rsp+48h+arg_10]
0x18003e2e3  movzx   eax, byte ptr [rax+2]
0x18003e2e7  mov     r8d, rva g_iYscale[rdx+rax*4]
0x18003e2ef  mov     eax, r8d
0x18003e2f2  sub     eax, [rsp+48h+var_48]
0x18003e2f5  cdqe
0x18003e2f7  movzx   edx, byte ptr [rax+r9]
0x18003e2fc  lea     eax, [r15+r8]
0x18003e300  movsxd  rcx, eax
0x18003e303  add     edx, r10d
0x18003e306  lea     rax, __ImageBase
0x18003e30d  mov     dl, [rdx+rax+59900h]
0x18003e314  movzx   ecx, byte ptr [rcx+r9]
0x18003e319  add     ecx, r10d
0x18003e31c  add     dl, [rcx+rax+59A00h]
0x18003e323  mov     eax, [rsp+48h+var_44]
0x18003e327  add     eax, r8d
0x18003e32a  lea     r8, __ImageBase
0x18003e331  movsxd  rcx, eax
0x18003e334  movzx   eax, byte ptr [rcx+r9]
0x18003e339  add     eax, r10d
0x18003e33c  add     dl, [rax+r8+59800h]
0x18003e344  mov     rax, [rsp+48h+arg_8]
0x18003e349  mov     [rax+2], dl
0x18003e34c  mov     rax, [rsp+48h+arg_10]
0x18003e351  movzx   eax, byte ptr [rax+6]
0x18003e355  mov     r9d, rva g_iYscale[r8+rax*4]
0x18003e35d  mov     eax, [rsp+48h+var_40]
0x18003e361  mov     r8, cs:g_rgiClapTabDec
0x18003e368  add     eax, r9d
0x18003e36b  movsxd  rcx, eax
0x18003e36e  movzx   edx, byte ptr [rcx+r8]
0x18003e373  add     edx, r10d
0x18003e376  lea     eax, [r9+r13]
0x18003e37a  movsxd  rcx, eax
0x18003e37d  sub     r9d, r12d
0x18003e380  lea     rax, __ImageBase
0x18003e387  movzx   ecx, byte ptr [rcx+r8]
0x18003e38c  mov     r8b, [rdx+rax+59A00h]
0x18003e394  add     ecx, r10d
0x18003e397  mov     rdx, cs:g_rgiClapTabDec
0x18003e39e  add     r8b, [rcx+rax+59800h]
0x18003e3a6  lea     rcx, __ImageBase
0x18003e3ad  movsxd  rax, r9d
0x18003e3b0  movzx   eax, byte ptr [rax+rdx]
0x18003e3b4  add     eax, r10d
0x18003e3b7  add     r10d, 300h
0x18003e3be  add     r8b, [rax+rcx+59900h]
0x18003e3c6  mov     rax, [rsp+48h+arg_8]
0x18003e3cb  mov     [rax+6], r8b
0x18003e3cf  mov     rax, [rsp+48h+arg_10]
0x18003e3d4  movzx   eax, byte ptr [rax+3]
0x18003e3d8  mov     r9d, rva g_iYscale[rcx+rax*4]
0x18003e3e0  lea     eax, [r15+r9]
0x18003e3e4  movsxd  rcx, eax
0x18003e3e7  mov     eax, [rsp+48h+var_44]
0x18003e3eb  add     eax, r9d
0x18003e3ee  sub     r9d, [rsp+48h+var_48]
0x18003e3f2  movzx   edx, byte ptr [rcx+rdx]
0x18003e3f6  movsxd  rcx, eax
0x18003e3f9  add     edx, r10d
0x18003e3fc  mov     rax, cs:g_rgiClapTabDec
0x18003e403  movzx   ecx, byte ptr [rcx+rax]
0x18003e407  lea     rax, __ImageBase
0x18003e40e  mov     r8b, [rdx+rax+59A00h]
0x18003e416  add     ecx, r10d
0x18003e419  lea     rdx, __ImageBase
0x18003e420  movsxd  rax, r9d
0x18003e423  mov     r9, cs:g_rgiClapTabDec
0x18003e42a  add     r8b, [rcx+rdx+59800h]
0x18003e432  movzx   ecx, byte ptr [rax+r9]
0x18003e437  mov     rax, [rsp+48h+arg_8]
0x18003e43c  add     ecx, r10d
0x18003e43f  add     r8b, [rcx+rdx+59900h]
0x18003e447  mov     [rax+3], r8b
0x18003e44b  mov     rax, [rsp+48h+arg_10]
0x18003e450  movzx   eax, byte ptr [rax+7]
0x18003e454  mov     r8d, rva g_iYscale[rdx+rax*4]
0x18003e45c  lea     eax, [r8+r13]
0x18003e460  movsxd  rcx, eax
0x18003e463  mov     eax, r8d
0x18003e466  sub     eax, r12d
0x18003e469  cdqe
0x18003e46b  movzx   edx, byte ptr [rcx+r9]
0x18003e470  lea     rcx, __ImageBase
0x18003e477  add     edx, r10d
0x18003e47a  movzx   eax, byte ptr [rax+r9]
0x18003e47f  add     eax, r10d
0x18003e482  mov     dl, [rdx+rcx+59800h]
0x18003e489  add     dl, [rax+rcx+59900h]
0x18003e490  mov     eax, [rsp+48h+var_40]
0x18003e494  add     eax, r8d
0x18003e497  lea     r8, __ImageBase
0x18003e49e  movsxd  rcx, eax
0x18003e4a1  movzx   eax, byte ptr [rcx+r9]
0x18003e4a6  mov     ecx, 1
0x18003e4ab  add     eax, r10d
0x18003e4ae  add     dl, [rax+r8+59A00h]
0x18003e4b6  mov     rax, [rsp+48h+arg_8]
0x18003e4bb  mov     [rax+7], dl
0x18003e4be  movsxd  rax, [rsp+48h+arg_30]
0x18003e4c6  add     [rsp+48h+arg_18], rax
0x18003e4cb  add     [rsp+48h+arg_20], rax
0x18003e4d0  mov     eax, [rsp+48h+var_3C]
0x18003e4d4  add     eax, eax
0x18003e4d6  sub     ecx, eax
0x18003e4d8  movsxd  rax, [rsp+48h+arg_28]
0x18003e4dd  and     ecx, 3
0x18003e4e0  lea     r10d, [rcx+rcx*2]
0x18003e4e4  mov     rcx, [rsp+48h+arg_10]
0x18003e4e9  shl     r10d, 0Ah
0x18003e4ed  movzx   eax, byte ptr [rax+rcx]
0x18003e4f1  mov     r9d, rva g_iYscale[r8+rax*4]
0x18003e4f9  mov     r8, cs:g_rgiClapTabDec
0x18003e500  lea     eax, [rdi+r9]
0x18003e504  movsxd  rcx, eax
0x18003e507  lea     eax, [r14+r9]
0x18003e50b  sub     r9d, ebx
0x18003e50e  movzx   edx, byte ptr [rcx+r8]
0x18003e513  movsxd  rcx, eax
0x18003e516  add     edx, r10d
0x18003e519  lea     rax, __ImageBase
0x18003e520  movzx   ecx, byte ptr [rcx+r8]
0x18003e525  mov     r8b, [rdx+rax+59A00h]
0x18003e52d  add     ecx, r10d
0x18003e530  mov     rdx, cs:g_rgiClapTabDec
0x18003e537  add     r8b, [rcx+rax+59800h]
0x18003e53f  lea     rcx, __ImageBase
0x18003e546  movsxd  rax, r9d
0x18003e549  movzx   eax, byte ptr [rax+rdx]
0x18003e54d  add     eax, r10d
0x18003e550  add     r8b, [rax+rcx+59900h]
0x18003e558  movsxd  rax, [rsp+48h+arg_38]
0x18003e560  mov     rcx, [rsp+48h+arg_8]
0x18003e565  mov     [rax+rcx], r8b
0x18003e569  lea     r8, __ImageBase
0x18003e570  mov     rcx, [rsp+48h+arg_10]
0x18003e575  movsxd  rax, [rsp+48h+arg_28]
0x18003e57a  movzx   eax, byte ptr [rax+rcx+4]
0x18003e57f  mov     r9d, rva g_iYscale[r8+rax*4]
0x18003e587  lea     eax, [r11+r9]
0x18003e58b  movsxd  rcx, eax
0x18003e58e  lea     eax, [rsi+r9]
0x18003e592  sub     r9d, ebp
0x18003e595  movzx   edx, byte ptr [rcx+rdx]
0x18003e599  movsxd  rcx, eax
0x18003e59c  add     edx, r10d
0x18003e59f  mov     rax, cs:g_rgiClapTabDec
0x18003e5a6  mov     r8b, [rdx+r8+59A00h]
0x18003e5ae  lea     rdx, __ImageBase
0x18003e5b5  movzx   eax, byte ptr [rcx+rax]
0x18003e5b9  mov     rcx, cs:g_rgiClapTabDec
  ... truncated ...
```

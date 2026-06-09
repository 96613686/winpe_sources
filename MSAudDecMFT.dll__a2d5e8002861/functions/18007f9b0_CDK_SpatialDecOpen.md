# CDK_SpatialDecOpen

- ea: `0x18007f9b0`
- end: `0x18008020d`
- name: `CDK_SpatialDecOpen`
- size: `2141`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800056a8`

## callees

- `0x18003eee0`
- `0x18007c14c`
- `0x18007c1d8`
- `0x18007c268`
- `0x18007c304`
- `0x18007c3ec`
- `0x18007f9b0`
- `0x18008bda0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fa29`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fa6a`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fa8b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007faac`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fc50`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fc72`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fdb1`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fdd2`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fdf3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fe14`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fe88`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007feb0`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007ff7f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007ffa5`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800800c6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800800ea`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18008010e`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180080197`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fa29`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fa6a`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fa8b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007faac`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fc50`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fc72`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fdb1`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fdd2`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fdf3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fe14`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007fe88`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007feb0`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007ff7f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18007ffa5`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800800c6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800800ea`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18008010e`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180080197`

## pseudocode

```c
char *__fastcall CDK_SpatialDecOpen(_DWORD *a1)
{
  __m128d si128; // xmm6
  char *v3; // rax
  char *v4; // rbx
  void *v5; // rax
  void *v6; // rax
  void *v7; // rax
  void **v8; // rax
  unsigned int v9; // r8d
  void ***v10; // rax
  unsigned int v11; // r8d
  void ***v12; // rax
  unsigned int v13; // r8d
  void ***v14; // rax
  void **v15; // rax
  void **v16; // rax
  unsigned int v17; // r8d
  void ***v18; // rax
  void **v19; // rax
  void **v20; // rax
  void **v21; // rax
  void **v22; // rax
  unsigned int v23; // r8d
  void ***v24; // rax
  unsigned int v25; // r8d
  void ***v26; // rax
  void *v27; // rax
  void *v28; // rax
  void **v29; // rax
  void **v30; // rax
  __int64 v31; // rax
  unsigned int v32; // r8d
  void ***v33; // rax
  __int64 v34; // rax
  unsigned int v35; // r8d
  void ***v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  void *v41; // rax
  void *v42; // rax
  void *v43; // rax
  void *v44; // rax
  int i; // edi
  __int64 v46; // rax
  __int64 v47; // rax
  void *v48; // rax
  void *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  void *v56; // rax
  void *v57; // rax
  __int64 v58; // rax
  void **v59; // rax
  void *v60; // r8
  __int64 v61; // r9
  int v62; // esi
  __int64 v63; // rax
  unsigned int v64; // edi
  void **v65; // rax
  void *v66; // rdx
  __int64 v67; // r8
  void *v68; // rax
  void *v69; // rax
  void *v70; // rax
  __int64 v71; // rax
  int v72; // r9d
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rcx
  void *v76; // rax
  __int128 v78; // [rsp+30h] [rbp-50h]
  __int128 v79; // [rsp+40h] [rbp-40h]
  __int128 v80; // [rsp+50h] [rbp-30h]

  if ( *a1 )
    return 0;
  si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
  LODWORD(v78) = 1;
  *((_QWORD *)&v80 + 1) = *(_QWORD *)&si128.m128d_f64[0];
  HIDWORD(v79) = 64;
  HIDWORD(v78) = 71;
  *(_QWORD *)&v80 = 0x100000047LL;
  *(_QWORD *)((char *)&v78 + 4) = 0x4000000002LL;
  LODWORD(v79) = 2;
  *(_QWORD *)((char *)&v79 + 4) = 0x100000002LL;
  v3 = (char *)calloc(1u, 0x578u);
  v4 = v3;
  if ( !v3 )
    goto LABEL_67;
  *(_OWORD *)(v3 + 20) = v78;
  *(_OWORD *)(v3 + 36) = v79;
  *(_OWORD *)(v3 + 52) = v80;
  *(_QWORD *)(v3 + 68) = *(_OWORD *)&_mm_unpackhi_pd(si128, si128);
  v5 = calloc(0x1Du, 4u);
  *((_QWORD *)v4 + 27) = v5;
  if ( !v5 )
    goto LABEL_67;
  v6 = calloc(1u, 4u);
  *((_QWORD *)v4 + 48) = v6;
  if ( !v6 )
    goto LABEL_67;
  v7 = calloc(9u, 4u);
  *((_QWORD *)v4 + 50) = v7;
  if ( !v7 )
    goto LABEL_67;
  v8 = cdkCallocMatrix2D(9u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 51) = v8;
  if ( !v8 )
    goto LABEL_67;
  v10 = cdkCallocMatrix3D(1u, 9u, v9, 1u);
  *((_QWORD *)v4 + 62) = v10;
  if ( !v10 )
    goto LABEL_67;
  v12 = cdkCallocMatrix3D(1u, 9u, v11, 1u);
  *((_QWORD *)v4 + 63) = v12;
  if ( !v12 )
    goto LABEL_67;
  v14 = cdkCallocMatrix3D(1u, 9u, v13, 1u);
  *((_QWORD *)v4 + 69) = v14;
  if ( !v14 )
    goto LABEL_67;
  v15 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 52) = v15;
  if ( !v15 )
    goto LABEL_67;
  v16 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 53) = v16;
  if ( !v16 )
    goto LABEL_67;
  v18 = cdkCallocMatrix3D(1u, 9u, v17, 1u);
  *((_QWORD *)v4 + 59) = v18;
  if ( !v18 )
    goto LABEL_67;
  v19 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 55) = v19;
  if ( !v19 )
    goto LABEL_67;
  v20 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 54) = v20;
  if ( !v20 )
    goto LABEL_67;
  v21 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 57) = v21;
  if ( !v21 )
    goto LABEL_67;
  v22 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 58) = v22;
  if ( !v22 )
    goto LABEL_67;
  v24 = cdkCallocMatrix3D(1u, 9u, v23, 1u);
  *((_QWORD *)v4 + 56) = v24;
  if ( !v24 )
    goto LABEL_67;
  v26 = cdkCallocMatrix3D(1u, 9u, v25, 1u);
  *((_QWORD *)v4 + 64) = v26;
  if ( !v26 )
    goto LABEL_67;
  v27 = calloc(1u, 4u);
  *((_QWORD *)v4 + 65) = v27;
  if ( !v27 )
    goto LABEL_67;
  v28 = calloc(1u, 4u);
  *((_QWORD *)v4 + 66) = v28;
  if ( !v28 )
    goto LABEL_67;
  v29 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 61) = v29;
  if ( !v29 )
    goto LABEL_67;
  v30 = cdkCallocMatrix2D(1u, 0x1Cu, 1u);
  *((_QWORD *)v4 + 60) = v30;
  if ( !v30 )
    goto LABEL_67;
  v31 = cdkCallocMatrix3D_int(2, 2);
  *((_QWORD *)v4 + 127) = v31;
  if ( !v31 )
    goto LABEL_67;
  v33 = cdkCallocMatrix3D(2u, 2u, v32, 4u);
  *((_QWORD *)v4 + 128) = v33;
  if ( !v33 )
    goto LABEL_67;
  v34 = cdkCallocMatrix3D_int(2, 2);
  *((_QWORD *)v4 + 129) = v34;
  if ( !v34 )
    goto LABEL_67;
  v36 = cdkCallocMatrix3D(2u, 2u, v35, 4u);
  *((_QWORD *)v4 + 130) = v36;
  if ( !v36 )
    goto LABEL_67;
  v37 = cdkCallocMatrix2D_int_aligned(1, 64);
  *((_QWORD *)v4 + 134) = v37;
  if ( !v37 )
    goto LABEL_67;
  v38 = cdkCallocMatrix2D_int_aligned(1, 64);
  *((_QWORD *)v4 + 135) = v38;
  if ( !v38 )
    goto LABEL_67;
  v39 = cdkCallocMatrix2D_int(1, 71);
  *((_QWORD *)v4 + 136) = v39;
  if ( !v39 )
    goto LABEL_67;
  v40 = cdkCallocMatrix2D_int(1, 71);
  *((_QWORD *)v4 + 137) = v40;
  if ( !v40 )
    goto LABEL_67;
  v41 = calloc(1u, 8u);
  *((_QWORD *)v4 + 141) = v41;
  if ( !v41 )
    goto LABEL_67;
  v42 = calloc(1u, 8u);
  *((_QWORD *)v4 + 142) = v42;
  if ( !v42 )
    goto LABEL_67;
  v43 = calloc(1u, 8u);
  *((_QWORD *)v4 + 143) = v43;
  if ( !v43 )
    goto LABEL_67;
  v44 = calloc(1u, 8u);
  *((_QWORD *)v4 + 144) = v44;
  if ( !v44 )
    goto LABEL_67;
  for ( i = 0; i < 1; ++i )
  {
    v46 = cdkCallocMatrix2D_int_aligned(1, 64);
    *(_QWORD *)(*((_QWORD *)v4 + 141) + 8LL * i) = v46;
    if ( !v46 )
      goto LABEL_67;
    v47 = cdkCallocMatrix2D_int_aligned(1, 64);
    *(_QWORD *)(*((_QWORD *)v4 + 142) + 8LL * i) = v47;
    if ( !v47 )
      goto LABEL_67;
    v48 = calloc(0x47u, 4u);
    *(_QWORD *)(*((_QWORD *)v4 + 143) + 8LL * i) = v48;
    if ( !v48 )
      goto LABEL_67;
    v49 = calloc(0x47u, 4u);
    *(_QWORD *)(*((_QWORD *)v4 + 144) + 8LL * i) = v49;
    if ( !v49 )
      goto LABEL_67;
  }
  v50 = cdkCallocMatrix2D_int(2, 71);
  *((_QWORD *)v4 + 149) = v50;
  if ( !v50 )
    goto LABEL_67;
  v51 = cdkCallocMatrix2D_int(2, 71);
  *((_QWORD *)v4 + 150) = v51;
  if ( !v51 )
    goto LABEL_67;
  v52 = cdkCallocMatrix2D_int(2, 71);
  *((_QWORD *)v4 + 151) = v52;
  if ( !v52 )
    goto LABEL_67;
  v53 = cdkCallocMatrix2D_int(2, 71);
  *((_QWORD *)v4 + 152) = v53;
  if ( !v53 )
    goto LABEL_67;
  v54 = cdkCallocMatrix2D_int(2, 71);
  *((_QWORD *)v4 + 153) = v54;
  if ( !v54 )
    goto LABEL_67;
  v55 = cdkCallocMatrix2D_int(2, 71);
  *((_QWORD *)v4 + 154) = v55;
  if ( !v55 )
    goto LABEL_67;
  v56 = calloc(2u, 0x10u);
  *((_QWORD *)v4 + 158) = v56;
  if ( !v56 )
    goto LABEL_67;
  v57 = calloc(2u, 0x138u);
  *((_QWORD *)v4 + 157) = v57;
  if ( !v57 )
    goto LABEL_67;
  v58 = cdkCallocMatrix2D_int(1, 78);
  *((_QWORD *)v4 + 159) = v58;
  if ( !v58 )
    goto LABEL_67;
  v59 = cdkCallocMatrix2D(1u, 0x2DCu, 4u);
  *((_QWORD *)v4 + 160) = v59;
  if ( !v59 )
    goto LABEL_67;
  v60 = *v59;
  v61 = *((_QWORD *)v4 + 157);
  *(_QWORD *)(v61 + 280) = **((_QWORD **)v4 + 159);
  *(_DWORD *)(v61 + 296) = 312;
  *(_QWORD *)(v61 + 288) = v60;
  *(_DWORD *)(v61 + 300) = 2928;
  v62 = a1[1];
  v63 = cdkCallocMatrix2D_int(1, 78);
  *((_QWORD *)v4 + 161) = v63;
  if ( !v63 )
    goto LABEL_67;
  v64 = 396;
  if ( v62 != 1 )
    v64 = 732;
  v65 = cdkCallocMatrix2D(1u, v64, 4u);
  *((_QWORD *)v4 + 162) = v65;
  if ( !v65 )
    goto LABEL_67;
  v66 = *v65;
  v67 = *((_QWORD *)v4 + 157);
  *(_QWORD *)(v67 + 592) = **((_QWORD **)v4 + 161);
  *(_QWORD *)(v67 + 600) = v66;
  *(_DWORD *)(v67 + 608) = 312;
  *(_DWORD *)(v67 + 612) = 4 * v64;
  v68 = calloc(1u, 0x104u);
  *((_QWORD *)v4 + 165) = v68;
  if ( !v68 )
    goto LABEL_67;
  v69 = calloc(1u, 0xE4u);
  *((_QWORD *)v4 + 166) = v69;
  if ( !v69 )
    goto LABEL_67;
  v70 = calloc(1u, 0xD60u);
  *((_QWORD *)v4 + 163) = v70;
  if ( !v70 )
    goto LABEL_67;
  v71 = cdkCallocMatrix2D_int(1, 2396);
  *((_QWORD *)v4 + 164) = v71;
  if ( !v71 )
    goto LABEL_67;
  v72 = 0;
  while ( v72 < 1 )
  {
    v73 = *((_QWORD *)v4 + 163);
    v74 = 3424LL * v72;
    v75 = *(_QWORD *)(*((_QWORD *)v4 + 164) + 8LL * v72++);
    *(_QWORD *)(v74 + v73 + 8) = v75;
    *(_DWORD *)(v74 + v73) = 0;
    *(_QWORD *)(v74 + v73 + 24) = 0;
    *(_DWORD *)(v74 + v73 + 16) = 0;
  }
  v76 = calloc(1u, 0x38u);
  if ( !v76 )
  {
LABEL_67:
    CDK_SpatialDecClose(v4);
    return 0;
  }
  if ( v4 != (char *)-1344LL )
    *((_QWORD *)v4 + 168) = v76;
  *((_DWORD *)v4 + 2) = *a1;
  *((_DWORD *)v4 + 3) = a1[1];
  *((_DWORD *)v4 + 4) = a1[3];
  SpatialDecConcealment_Init((struct SpatialDecConcealmentInfo *)(v4 + 1364), 0xFFu);
  return v4;
}

```

## disassembly

```asm
0x18007f9b0  mov     [rsp-28h+arg_0], rbx
0x18007f9b5  mov     [rsp-28h+arg_10], rsi
0x18007f9ba  push    rbp
0x18007f9bb  push    rdi
0x18007f9bc  push    r12
0x18007f9be  push    r13
0x18007f9c0  push    r14
0x18007f9c2  mov     rbp, rsp
0x18007f9c5  sub     rsp, 80h
0x18007f9cc  cmp     dword ptr [rcx], 0
0x18007f9cf  mov     r14, rcx
0x18007f9d2  movaps  [rsp+80h+var_10], xmm6
0x18007f9d7  jnz     loc_1800801E9
0x18007f9dd  movdqa  xmm6, cs:__xmm@00000002000000010000000000000001
0x18007f9e5  mov     r12d, 1
0x18007f9eb  mov     edx, 578h; Size
0x18007f9f0  mov     dword ptr [rbp+var_50], r12d
0x18007f9f4  mov     dword ptr [rbp+var_40+8], r12d
0x18007f9f8  movdqu  [rbp+var_30+8], xmm6
0x18007f9fd  lea     ecx, [r12+3Fh]
0x18007fa02  mov     dword ptr [rbp+var_30+4], r12d
0x18007fa06  lea     esi, [rcx+7]
0x18007fa09  mov     dword ptr [rbp+var_50+8], ecx
0x18007fa0c  lea     r13d, [r12+1]
0x18007fa11  mov     dword ptr [rbp+var_40+0Ch], ecx
0x18007fa14  mov     ecx, r12d; Count
0x18007fa17  mov     dword ptr [rbp+var_50+0Ch], esi
0x18007fa1a  mov     dword ptr [rbp+var_30], esi
0x18007fa1d  mov     dword ptr [rbp+var_50+4], r13d
0x18007fa21  mov     dword ptr [rbp+var_40], r13d
0x18007fa25  mov     dword ptr [rbp+var_40+4], r13d
0x18007fa29  call    cs:__imp_calloc
0x18007fa30  nop     dword ptr [rax+rax+00h]
0x18007fa35  mov     rbx, rax
0x18007fa38  test    rax, rax
0x18007fa3b  jz      loc_1800801E1
0x18007fa41  movups  xmm0, [rbp+var_50]
0x18007fa45  lea     edi, [rsi-43h]
0x18007fa48  movups  xmm1, [rbp+var_40]
0x18007fa4c  mov     edx, edi; Size
0x18007fa4e  lea     ecx, [rsi-2Ah]; Count
0x18007fa51  movups  xmmword ptr [rax+14h], xmm0
0x18007fa55  movups  xmm0, [rbp+var_30]
0x18007fa59  movups  xmmword ptr [rax+24h], xmm1
0x18007fa5d  unpckhpd xmm6, xmm6
0x18007fa61  movups  xmmword ptr [rax+34h], xmm0
0x18007fa65  movsd   qword ptr [rax+44h], xmm6
0x18007fa6a  call    cs:__imp_calloc
0x18007fa71  nop     dword ptr [rax+rax+00h]
0x18007fa76  mov     [rbx+0D8h], rax
0x18007fa7d  test    rax, rax
0x18007fa80  jz      loc_1800801E1
0x18007fa86  mov     edx, edi; Size
0x18007fa88  mov     ecx, r12d; Count
0x18007fa8b  call    cs:__imp_calloc
0x18007fa92  nop     dword ptr [rax+rax+00h]
0x18007fa97  mov     [rbx+180h], rax
0x18007fa9e  test    rax, rax
0x18007faa1  jz      loc_1800801E1
0x18007faa7  mov     edx, edi; Size
0x18007faa9  lea     ecx, [rsi-3Eh]; Count
0x18007faac  call    cs:__imp_calloc
0x18007fab3  nop     dword ptr [rax+rax+00h]
0x18007fab8  mov     [rbx+190h], rax
0x18007fabf  test    rax, rax
0x18007fac2  jz      loc_1800801E1
0x18007fac8  lea     edi, [rsi-2Bh]
0x18007facb  mov     r8d, r12d; unsigned int
0x18007face  mov     edx, edi; unsigned int
0x18007fad0  lea     ecx, [rsi-3Eh]; Count
0x18007fad3  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fad8  mov     [rbx+198h], rax
0x18007fadf  test    rax, rax
0x18007fae2  jz      loc_1800801E1
0x18007fae8  mov     r9d, r12d; unsigned int
0x18007faeb  lea     edx, [rsi-3Eh]; unsigned int
0x18007faee  mov     ecx, r12d; Count
0x18007faf1  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007faf6  mov     [rbx+1F0h], rax
0x18007fafd  test    rax, rax
0x18007fb00  jz      loc_1800801E1
0x18007fb06  mov     r9d, r12d; unsigned int
0x18007fb09  lea     edx, [rsi-3Eh]; unsigned int
0x18007fb0c  mov     ecx, r12d; Count
0x18007fb0f  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007fb14  mov     [rbx+1F8h], rax
0x18007fb1b  test    rax, rax
0x18007fb1e  jz      loc_1800801E1
0x18007fb24  mov     r9d, r12d; unsigned int
0x18007fb27  lea     edx, [rsi-3Eh]; unsigned int
0x18007fb2a  mov     ecx, r12d; Count
0x18007fb2d  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007fb32  mov     [rbx+228h], rax
0x18007fb39  test    rax, rax
0x18007fb3c  jz      loc_1800801E1
0x18007fb42  mov     r8d, r12d; unsigned int
0x18007fb45  mov     edx, edi; unsigned int
0x18007fb47  mov     ecx, r12d; Count
0x18007fb4a  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fb4f  mov     [rbx+1A0h], rax
0x18007fb56  test    rax, rax
0x18007fb59  jz      loc_1800801E1
0x18007fb5f  mov     r8d, r12d; unsigned int
0x18007fb62  mov     edx, edi; unsigned int
0x18007fb64  mov     ecx, r12d; Count
0x18007fb67  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fb6c  mov     [rbx+1A8h], rax
0x18007fb73  test    rax, rax
0x18007fb76  jz      loc_1800801E1
0x18007fb7c  mov     r9d, r12d; unsigned int
0x18007fb7f  lea     edx, [rsi-3Eh]; unsigned int
0x18007fb82  mov     ecx, r12d; Count
0x18007fb85  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007fb8a  mov     [rbx+1D8h], rax
0x18007fb91  test    rax, rax
0x18007fb94  jz      loc_1800801E1
0x18007fb9a  mov     r8d, r12d; unsigned int
0x18007fb9d  mov     edx, edi; unsigned int
0x18007fb9f  mov     ecx, r12d; Count
0x18007fba2  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fba7  mov     [rbx+1B8h], rax
0x18007fbae  test    rax, rax
0x18007fbb1  jz      loc_1800801E1
0x18007fbb7  mov     r8d, r12d; unsigned int
0x18007fbba  mov     edx, edi; unsigned int
0x18007fbbc  mov     ecx, r12d; Count
0x18007fbbf  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fbc4  mov     [rbx+1B0h], rax
0x18007fbcb  test    rax, rax
0x18007fbce  jz      loc_1800801E1
0x18007fbd4  mov     r8d, r12d; unsigned int
0x18007fbd7  mov     edx, edi; unsigned int
0x18007fbd9  mov     ecx, r12d; Count
0x18007fbdc  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fbe1  mov     [rbx+1C8h], rax
0x18007fbe8  test    rax, rax
0x18007fbeb  jz      loc_1800801E1
0x18007fbf1  mov     r8d, r12d; unsigned int
0x18007fbf4  mov     edx, edi; unsigned int
0x18007fbf6  mov     ecx, r12d; Count
0x18007fbf9  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fbfe  mov     [rbx+1D0h], rax
0x18007fc05  test    rax, rax
0x18007fc08  jz      loc_1800801E1
0x18007fc0e  mov     r9d, r12d; unsigned int
0x18007fc11  lea     edx, [rsi-3Eh]; unsigned int
0x18007fc14  mov     ecx, r12d; Count
0x18007fc17  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007fc1c  mov     [rbx+1C0h], rax
0x18007fc23  test    rax, rax
0x18007fc26  jz      loc_1800801E1
0x18007fc2c  mov     r9d, r12d; unsigned int
0x18007fc2f  lea     edx, [rsi-3Eh]; unsigned int
0x18007fc32  mov     ecx, r12d; Count
0x18007fc35  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007fc3a  mov     [rbx+200h], rax
0x18007fc41  test    rax, rax
0x18007fc44  jz      loc_1800801E1
0x18007fc4a  lea     edx, [rsi-43h]; Size
0x18007fc4d  mov     ecx, r12d; Count
0x18007fc50  call    cs:__imp_calloc
0x18007fc57  nop     dword ptr [rax+rax+00h]
0x18007fc5c  mov     [rbx+208h], rax
0x18007fc63  test    rax, rax
0x18007fc66  jz      loc_1800801E1
0x18007fc6c  lea     edx, [rsi-43h]; Size
0x18007fc6f  mov     ecx, r12d; Count
0x18007fc72  call    cs:__imp_calloc
0x18007fc79  nop     dword ptr [rax+rax+00h]
0x18007fc7e  mov     [rbx+210h], rax
0x18007fc85  test    rax, rax
0x18007fc88  jz      loc_1800801E1
0x18007fc8e  mov     r8d, r12d; unsigned int
0x18007fc91  mov     edx, edi; unsigned int
0x18007fc93  mov     ecx, r12d; Count
0x18007fc96  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fc9b  mov     [rbx+1E8h], rax
0x18007fca2  test    rax, rax
0x18007fca5  jz      loc_1800801E1
0x18007fcab  mov     r8d, r12d; unsigned int
0x18007fcae  mov     edx, edi; unsigned int
0x18007fcb0  mov     ecx, r12d; Count
0x18007fcb3  call    ?cdkCallocMatrix2D@@YAPEAPEAXIII@Z; cdkCallocMatrix2D(uint,uint,uint)
0x18007fcb8  mov     [rbx+1E0h], rax
0x18007fcbf  test    rax, rax
0x18007fcc2  jz      loc_1800801E1
0x18007fcc8  mov     edx, r13d
0x18007fccb  mov     ecx, r13d
0x18007fcce  call    ?cdkCallocMatrix3D_int@@YAPEAPEAPEAXIIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix3D_int(uint,uint,uint,uint,MEMORY_SECTION)
0x18007fcd3  mov     [rbx+3F8h], rax
0x18007fcda  test    rax, rax
0x18007fcdd  jz      loc_1800801E1
0x18007fce3  lea     r9d, [r12+3]; unsigned int
0x18007fce8  mov     edx, r13d; unsigned int
0x18007fceb  mov     ecx, r13d; Count
0x18007fcee  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007fcf3  mov     [rbx+400h], rax
0x18007fcfa  test    rax, rax
0x18007fcfd  jz      loc_1800801E1
0x18007fd03  mov     edx, r13d
0x18007fd06  mov     ecx, r13d
0x18007fd09  call    ?cdkCallocMatrix3D_int@@YAPEAPEAPEAXIIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix3D_int(uint,uint,uint,uint,MEMORY_SECTION)
0x18007fd0e  mov     [rbx+408h], rax
0x18007fd15  test    rax, rax
0x18007fd18  jz      loc_1800801E1
0x18007fd1e  lea     r9d, [r12+3]; unsigned int
0x18007fd23  mov     edx, r13d; unsigned int
0x18007fd26  mov     ecx, r13d; Count
0x18007fd29  call    ?cdkCallocMatrix3D@@YAPEAPEAPEAXIIII@Z; cdkCallocMatrix3D(uint,uint,uint,uint)
0x18007fd2e  mov     [rbx+410h], rax
0x18007fd35  test    rax, rax
0x18007fd38  jz      loc_1800801E1
0x18007fd3e  lea     edi, [rsi-7]
0x18007fd41  mov     ecx, r12d
0x18007fd44  mov     edx, edi
0x18007fd46  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18007fd4b  mov     [rbx+430h], rax
0x18007fd52  test    rax, rax
0x18007fd55  jz      loc_1800801E1
0x18007fd5b  mov     edx, edi
0x18007fd5d  mov     ecx, r12d
0x18007fd60  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18007fd65  mov     [rbx+438h], rax
0x18007fd6c  test    rax, rax
0x18007fd6f  jz      loc_1800801E1
0x18007fd75  mov     edx, esi
0x18007fd77  mov     ecx, r12d
0x18007fd7a  call    ?cdkCallocMatrix2D_int@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int(uint,uint,uint,MEMORY_SECTION)
0x18007fd7f  mov     [rbx+440h], rax
0x18007fd86  test    rax, rax
0x18007fd89  jz      loc_1800801E1
0x18007fd8f  mov     edx, esi
0x18007fd91  mov     ecx, r12d
0x18007fd94  call    ?cdkCallocMatrix2D_int@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int(uint,uint,uint,MEMORY_SECTION)
0x18007fd99  mov     [rbx+448h], rax
0x18007fda0  test    rax, rax
0x18007fda3  jz      loc_1800801E1
0x18007fda9  lea     edi, [rsi-3Fh]
0x18007fdac  mov     ecx, r12d; Count
0x18007fdaf  mov     edx, edi; Size
0x18007fdb1  call    cs:__imp_calloc
0x18007fdb8  nop     dword ptr [rax+rax+00h]
0x18007fdbd  mov     [rbx+468h], rax
0x18007fdc4  test    rax, rax
0x18007fdc7  jz      loc_1800801E1
0x18007fdcd  mov     edx, edi; Size
0x18007fdcf  mov     ecx, r12d; Count
0x18007fdd2  call    cs:__imp_calloc
0x18007fdd9  nop     dword ptr [rax+rax+00h]
0x18007fdde  mov     [rbx+470h], rax
0x18007fde5  test    rax, rax
0x18007fde8  jz      loc_1800801E1
0x18007fdee  mov     edx, edi; Size
0x18007fdf0  mov     ecx, r12d; Count
0x18007fdf3  call    cs:__imp_calloc
0x18007fdfa  nop     dword ptr [rax+rax+00h]
0x18007fdff  mov     [rbx+478h], rax
0x18007fe06  test    rax, rax
0x18007fe09  jz      loc_1800801E1
0x18007fe0f  mov     edx, edi; Size
0x18007fe11  mov     ecx, r12d; Count
0x18007fe14  call    cs:__imp_calloc
0x18007fe1b  nop     dword ptr [rax+rax+00h]
0x18007fe20  mov     [rbx+480h], rax
0x18007fe27  test    rax, rax
0x18007fe2a  jz      loc_1800801E1
0x18007fe30  xor     edi, edi
0x18007fe32  cmp     edi, r12d
0x18007fe35  jge     loc_18007FED8
0x18007fe3b  mov     edx, 40h ; '@'
0x18007fe40  mov     ecx, r12d
0x18007fe43  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18007fe48  mov     rcx, [rbx+468h]
0x18007fe4f  movsxd  rsi, edi
0x18007fe52  mov     [rcx+rsi*8], rax
0x18007fe56  test    rax, rax
0x18007fe59  jz      loc_1800801E1
0x18007fe5f  mov     edx, 40h ; '@'
0x18007fe64  mov     ecx, r12d
0x18007fe67  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18007fe6c  mov     rcx, [rbx+470h]
0x18007fe73  mov     [rcx+rsi*8], rax
0x18007fe77  test    rax, rax
0x18007fe7a  jz      loc_1800801E1
0x18007fe80  mov     edx, 4; Size
0x18007fe85  lea     ecx, [rdx+43h]; Count
0x18007fe88  call    cs:__imp_calloc
0x18007fe8f  nop     dword ptr [rax+rax+00h]
0x18007fe94  mov     rcx, [rbx+478h]
0x18007fe9b  mov     [rcx+rsi*8], rax
0x18007fe9f  test    rax, rax
0x18007fea2  jz      loc_1800801E1
0x18007fea8  mov     edx, 4; Size
0x18007fead  lea     ecx, [rdx+43h]; Count
0x18007feb0  call    cs:__imp_calloc
0x18007feb7  nop     dword ptr [rax+rax+00h]
0x18007febc  mov     rcx, [rbx+480h]
0x18007fec3  mov     [rcx+rsi*8], rax
0x18007fec7  test    rax, rax
0x18007feca  jz      loc_1800801E1
  ... truncated ...
```

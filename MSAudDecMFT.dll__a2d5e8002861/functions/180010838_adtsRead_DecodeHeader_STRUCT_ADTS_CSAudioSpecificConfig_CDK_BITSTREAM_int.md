# adtsRead_DecodeHeader(STRUCT_ADTS *,CSAudioSpecificConfig *,CDK_BITSTREAM *,int)

- ea: `0x180010838`
- end: `0x1800110ba`
- name: `?adtsRead_DecodeHeader@@YA?AW4TRANSPORTDEC_ERROR@@PEAUSTRUCT_ADTS@@PEAUCSAudioSpecificConfig@@PEAUCDK_BITSTREAM@@H@Z`
- size: `2178`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800103a0`

## callees

- `0x18000e9b0`
- `0x180010838`
- `0x1800110c0`
- `0x18001112c`
- `0x18001115c`
- `0x180012264`
- `0x1800127d8`
- `0x1800130bc`
- `0x1800130d8`
- `0x180013fd0`
- `0x180014058`
- `0x18004b854`
- `0x18004d320`
- `0x18004dd14`

## pseudocode

```c
__int64 __fastcall adtsRead_DecodeHeader(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v7; // r13
  _OWORD *v9; // rax
  _OWORD *v10; // rcx
  __int64 v11; // rdx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  char v23; // al
  unsigned int v24; // r14d
  __int64 v25; // r12
  int v26; // r9d
  int v27; // r10d
  unsigned int v28; // r11d
  __int64 v30; // rdx
  int v31; // r12d
  int CrcStartReg; // r13d
  _OWORD *v33; // rax
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  int v41; // r13d
  __int16 v42; // ax
  __int64 v43; // rcx
  __int16 v44; // ax
  signed int v45; // r12d
  char v46; // al
  _OWORD *v47; // rax
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  char v59; // al
  _OWORD *v60; // rax
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  __int128 v65; // xmm1
  __int128 v66; // xmm0
  __int128 v67; // xmm1
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  char v72; // al
  __int128 v73; // xmm1
  __int128 v74; // xmm0
  __int128 v75; // xmm1
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  __int128 v82; // xmm1
  __int128 v83; // xmm0
  char v84; // al
  signed int v85; // eax
  char v86; // [rsp+20h] [rbp-E0h]
  char v87; // [rsp+24h] [rbp-DCh]
  __int128 v88; // [rsp+28h] [rbp-D8h]
  __int16 v89; // [rsp+38h] [rbp-C8h]
  int v90; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v91; // [rsp+44h] [rbp-BCh]
  char v92; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 v93; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v94; // [rsp+58h] [rbp-A8h]
  int started; // [rsp+60h] [rbp-A0h]
  char v96; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v98; // [rsp+6Ch] [rbp-94h]
  unsigned __int8 v99; // [rsp+70h] [rbp-90h]
  __int64 v101; // [rsp+80h] [rbp-80h]
  _OWORD v102[4]; // [rsp+90h] [rbp-70h]
  _BYTE v103[461]; // [rsp+D0h] [rbp-30h] BYREF
  char v104; // [rsp+29Dh] [rbp+19Dh]
  _BYTE v105[480]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v4 = a2 + 732;
  v5 = 3;
  v101 = a2 + 732;
  v7 = a2;
  v88 = 0;
  v9 = (_OWORD *)(a2 + 732);
  v10 = v103;
  v11 = 3;
  do
  {
    v12 = v9[1];
    *v10 = *v9;
    v13 = v9[2];
    v10[1] = v12;
    v14 = v9[3];
    v10[2] = v13;
    v15 = v9[4];
    v10[3] = v14;
    v16 = v9[5];
    v10[4] = v15;
    v17 = v9[6];
    v10[5] = v16;
    v18 = v9[7];
    v9 += 8;
    v10[6] = v17;
    v10[7] = v18;
    v10 += 8;
    --v11;
  }
  while ( v11 );
  v19 = v9[1];
  *v10 = *v9;
  v20 = v9[2];
  v10[1] = v19;
  v21 = v9[3];
  v10[2] = v20;
  v22 = v9[4];
  v23 = *((_BYTE *)v9 + 80);
  v10[3] = v21;
  v10[4] = v22;
  *((_BYTE *)v10 + 80) = v23;
  CDKsyncCache_0(a3);
  v24 = 56;
  v90 = *(_DWORD *)(a3 + 8) + 12;
  if ( v90 < 56 )
    return 257;
  v86 = CDKreadBits(a3, 1);
  LOBYTE(v88) = v86;
  v96 = CDKreadBits(a3, 2);
  BYTE1(v88) = v96;
  v92 = CDKreadBits(a3, 1);
  BYTE2(v88) = v92;
  v99 = CDKreadBits(a3, 2);
  BYTE3(v88) = v99;
  v91 = CDKreadBits(a3, 4);
  BYTE4(v88) = v91;
  BYTE5(v88) = CDKreadBits(a3, 1);
  v94 = CDKreadBits(a3, 3);
  BYTE6(v88) = v94;
  BYTE7(v88) = CDKreadBits(a3, 1);
  BYTE8(v88) = CDKreadBits(a3, 1);
  BYTE9(v88) = CDKreadBits(a3, 1);
  BYTE10(v88) = CDKreadBits(a3, 1);
  v93 = CDKreadBits(a3, 13);
  WORD6(v88) = v93;
  v98 = CDKreadBits(a3, 11);
  HIWORD(v88) = v98;
  LOBYTE(v25) = CDKreadBits(a3, 2);
  v87 = v25;
  v89 = (unsigned __int8)v25;
  if ( v90 < 8 * v93 )
    goto LABEL_19;
  CDKcrcReset((struct CDK_CRCINFO *)(a1 + 24));
  if ( v92 )
  {
LABEL_6:
    if ( v96 || v91 >= 0xDu || !v86 && !*(_BYTE *)(a1 + 18) )
    {
      v30 = v28;
LABEL_14:
      CDKpushFor(a3, v30);
      return 1026;
    }
    if ( !a4 )
    {
      v102[0] = _mm_load_si128((const __m128i *)&_xmm);
      v102[1] = _mm_load_si128((const __m128i *)&_xmm);
      v102[2] = _mm_load_si128((const __m128i *)&_xmm);
      v102[3] = _mm_load_si128((const __m128i *)&_xmm);
      if ( v98 != 2047 )
      {
        if ( *(_BYTE *)(a1 + 20) )
        {
          v31 = 8 * (v27 + 4 * *((_DWORD *)v102 + v94) * v98);
          if ( v26 < v31 )
          {
            CDKpushBack(a3, v24);
            return (unsigned int)((int)(v31 + v24) > 262137) + 257;
          }
          *(_BYTE *)(a1 + 20) = 0;
        }
      }
    }
    memset_0((void *)v7, 0, 0x6DCu);
    *(_BYTE *)(v7 + 1225) = -1;
    *(_BYTE *)(v4 + 2) = 15;
    *(_DWORD *)(v7 + 1200) = v99 + 1;
    *(_BYTE *)(v7 + 1231) = v91;
    *(_DWORD *)(v7 + 1208) = 1024;
    *(_DWORD *)(v7 + 1204) = dword_18009C260[v91];
    *(_BYTE *)(v7 + 1224) = v94;
    if ( v94 )
    {
LABEL_11:
      *(_OWORD *)a1 = v88;
      *(_WORD *)(a1 + 16) = v89;
      return 0;
    }
    CDKsyncCache_0(a3);
    v45 = *(_DWORD *)(a3 + 8);
    if ( (unsigned int)CDKreadBits(a3, 3) != 5 )
    {
      CDKpushBack(a3, 3);
      if ( v104 )
      {
        v46 = v86;
        if ( v91 == *(_BYTE *)(a1 + 4) && !*(_BYTE *)(a1 + 6) && v86 == *(_BYTE *)a1 )
        {
          v47 = v103;
          do
          {
            v48 = v47[1];
            *(_OWORD *)v4 = *v47;
            v49 = v47[2];
            *(_OWORD *)(v4 + 16) = v48;
            v50 = v47[3];
            *(_OWORD *)(v4 + 32) = v49;
            v51 = v47[4];
            *(_OWORD *)(v4 + 48) = v50;
            v52 = v47[5];
            *(_OWORD *)(v4 + 64) = v51;
            v53 = v47[6];
            *(_OWORD *)(v4 + 80) = v52;
            v54 = v47[7];
            v47 += 8;
            *(_OWORD *)(v4 + 96) = v53;
            *(_OWORD *)(v4 + 112) = v54;
            v4 += 128;
            --v5;
          }
          while ( v5 );
          v55 = v47[1];
          *(_OWORD *)v4 = *v47;
          v56 = v47[2];
          *(_OWORD *)(v4 + 16) = v55;
          v57 = v47[3];
          *(_OWORD *)(v4 + 32) = v56;
          v58 = v47[4];
          v59 = *((_BYTE *)v47 + 80);
          *(_OWORD *)(v4 + 48) = v57;
          *(_OWORD *)(v4 + 64) = v58;
          *(_BYTE *)(v4 + 80) = v59;
          goto LABEL_11;
        }
      }
      else
      {
        v46 = v86;
      }
      if ( !v46 )
      {
        v30 = 8 * v93 - v24 - 3;
        goto LABEL_14;
      }
      *(_OWORD *)a1 = v88;
      *(_WORD *)(a1 + 16) = v89;
      *(_BYTE *)(a1 + 19) = 1;
      goto LABEL_19;
    }
    CrcStartReg = adtsRead_CrcStartReg((struct STRUCT_ADTS *)a1, (struct CDK_BITSTREAM *)a3, 0);
    memset_0(v105, 0, 0x1D1u);
    v105[2] = 15;
    CProgramConfig_Read((struct CProgramConfig *)v105, (struct CDK_BITSTREAM *)a3, v45);
    if ( v105[461] )
    {
      if ( v104
        && (unsigned int)CProgramConfig_Compare(
                           (const struct CProgramConfig *const)v105,
                           (const struct CProgramConfig *const)v103) >= 2 )
      {
        v60 = v103;
        do
        {
          v61 = v60[1];
          *(_OWORD *)v4 = *v60;
          v62 = v60[2];
          *(_OWORD *)(v4 + 16) = v61;
          v63 = v60[3];
          *(_OWORD *)(v4 + 32) = v62;
          v64 = v60[4];
          *(_OWORD *)(v4 + 48) = v63;
          v65 = v60[5];
          *(_OWORD *)(v4 + 64) = v64;
          v66 = v60[6];
          *(_OWORD *)(v4 + 80) = v65;
          v67 = v60[7];
          v60 += 8;
          *(_OWORD *)(v4 + 96) = v66;
          *(_OWORD *)(v4 + 112) = v67;
          v4 += 128;
          --v5;
        }
        while ( v5 );
        v68 = v60[1];
        *(_OWORD *)v4 = *v60;
        v69 = v60[2];
        *(_OWORD *)(v4 + 16) = v68;
        v70 = v60[3];
        *(_OWORD *)(v4 + 32) = v69;
        v71 = v60[4];
        v72 = *((_BYTE *)v60 + 80);
        *(_OWORD *)(v4 + 48) = v70;
        *(_OWORD *)(v4 + 64) = v71;
        *(_BYTE *)(v4 + 80) = v72;
        goto LABEL_23;
      }
      v33 = v105;
      do
      {
        v34 = v33[1];
        *(_OWORD *)v4 = *v33;
        v35 = v33[2];
        *(_OWORD *)(v4 + 16) = v34;
        v36 = v33[3];
        *(_OWORD *)(v4 + 32) = v35;
        v37 = v33[4];
        *(_OWORD *)(v4 + 48) = v36;
        v38 = v33[5];
        *(_OWORD *)(v4 + 64) = v37;
        v39 = v33[6];
        *(_OWORD *)(v4 + 80) = v38;
        v40 = v33[7];
        v33 += 8;
        *(_OWORD *)(v4 + 96) = v39;
        *(_OWORD *)(v4 + 112) = v40;
        v4 += 128;
        --v5;
      }
      while ( v5 );
    }
    else
    {
      if ( !v104 )
      {
LABEL_23:
        CDKpushBack(a3, v24);
        return 1025;
      }
      v33 = v103;
      do
      {
        v73 = v33[1];
        *(_OWORD *)v4 = *v33;
        v74 = v33[2];
        *(_OWORD *)(v4 + 16) = v73;
        v75 = v33[3];
        *(_OWORD *)(v4 + 32) = v74;
        v76 = v33[4];
        *(_OWORD *)(v4 + 48) = v75;
        v77 = v33[5];
        *(_OWORD *)(v4 + 64) = v76;
        v78 = v33[6];
        *(_OWORD *)(v4 + 80) = v77;
        v79 = v33[7];
        v33 += 8;
        *(_OWORD *)(v4 + 96) = v78;
        *(_OWORD *)(v4 + 112) = v79;
        v4 += 128;
        --v5;
      }
      while ( v5 );
    }
    v80 = v33[1];
    *(_OWORD *)v4 = *v33;
    v81 = v33[2];
    *(_OWORD *)(v4 + 16) = v80;
    v82 = v33[3];
    *(_OWORD *)(v4 + 32) = v81;
    v83 = v33[4];
    v84 = *((_BYTE *)v33 + 80);
    *(_OWORD *)(v4 + 48) = v82;
    *(_OWORD *)(v4 + 64) = v83;
    *(_BYTE *)(v4 + 80) = v84;
    adtsRead_CrcEndReg((struct STRUCT_ADTS *)a1, (struct CDK_BITSTREAM *)a3, CrcStartReg);
    CDKsyncCache_0(a3);
    v85 = v45 - *(_DWORD *)(a3 + 8);
    if ( v85 <= v45 )
    {
      HIBYTE(v89) = v45 - *(_BYTE *)(a3 + 8);
      goto LABEL_11;
    }
    v24 += v85;
    goto LABEL_19;
  }
  CDKpushBack(a3, 56);
  started = CDKcrcStartReg((struct CDK_CRCINFO *)(a1 + 24), (struct CDK_BITSTREAM *const)a3, 0);
  CDKpushFor(a3, 56);
  if ( (_BYTE)v25 )
  {
    CDKsyncCache_0(a3);
    v25 = (unsigned __int8)v25;
    if ( *(_DWORD *)(a3 + 8) >= 16 * (unsigned __int8)v25 )
    {
      v41 = 0;
      do
      {
        v42 = CDKreadBits(a3, 16);
        v43 = (unsigned int)v41;
        v24 += 16;
        ++v41;
        *(_WORD *)(a1 + 2 * v43 + 106) = v42;
      }
      while ( v41 < (unsigned __int8)v25 );
      v4 = v101;
      *(_WORD *)(a1 + 2LL * (unsigned __int8)v25 + 106) = v93 - 2 * (unsigned __int8)v25 - 9;
      do
      {
        *(_WORD *)(a1 + 2 * v25 + 106) -= *(_WORD *)(a1 + 2 * v25 + 104);
        v25 = (unsigned int)(v25 - 1);
      }
      while ( (int)v25 > 0 );
      v7 = a2;
      LOBYTE(v25) = v87;
      goto LABEL_35;
    }
LABEL_19:
    CDKpushBack(a3, v24);
    return 257;
  }
LABEL_35:
  CDKcrcEndReg((struct CDK_CRCINFO *)(a1 + 24), (struct CDK_BITSTREAM *const)a3, started);
  CDKsyncCache_0(a3);
  if ( *(int *)(a3 + 8) < 16 )
    goto LABEL_19;
  v24 += 16;
  v44 = CDKreadBits(a3, 16);
  *(_WORD *)(a1 + 104) = v44;
  if ( !(_BYTE)v25 )
  {
LABEL_40:
    v28 = 8 * v93;
    v27 = v93;
    v26 = v90;
    goto LABEL_6;
  }
  if ( v44 == (*(_WORD *)(a1 + 96) & (unsigned __int16)(2 * *(_WORD *)(a1 + 82) - 1)) )
  {
    CDKcrcReset((struct CDK_CRCINFO *)(a1 + 24));
    goto LABEL_40;
  }
  return 1027;
}

```

## disassembly

```asm
0x180010838  mov     [rsp-8+arg_18], rbx
0x18001083d  push    rbp
0x18001083e  push    rsi
0x18001083f  push    rdi
0x180010840  push    r12
0x180010842  push    r13
0x180010844  push    r14
0x180010846  push    r15
0x180010848  lea     rbp, [rsp-3A0h]
0x180010850  sub     rsp, 4A0h
0x180010857  mov     rax, cs:__security_cookie
0x18001085e  xor     rax, rsp
0x180010861  mov     [rbp+3D0h+var_40], rax
0x180010868  lea     rbx, [rdx+2DCh]
0x18001086f  mov     [rsp+4D0h+var_458], rdx
0x180010874  mov     r15d, 3
0x18001087a  mov     [rsp+4D0h+var_468], r9d
0x18001087f  xor     eax, eax
0x180010881  mov     [rbp+3D0h+var_450], rbx
0x180010885  xorps   xmm0, xmm0
0x180010888  mov     [rsp+4D0h+var_498], ax
0x18001088d  mov     rdi, r8
0x180010890  mov     r13, rdx
0x180010893  mov     rsi, rcx
0x180010896  lea     r8d, [r15+7Dh]
0x18001089a  movups  [rsp+4D0h+var_4A8], xmm0
0x18001089f  mov     rax, rbx
0x1800108a2  lea     rcx, [rbp+3D0h+var_400]
0x1800108a6  mov     edx, r15d
0x1800108a9  movups  xmm0, xmmword ptr [rax]
0x1800108ac  movups  xmm1, xmmword ptr [rax+10h]
0x1800108b0  movups  xmmword ptr [rcx], xmm0
0x1800108b3  movups  xmm0, xmmword ptr [rax+20h]
0x1800108b7  movups  xmmword ptr [rcx+10h], xmm1
0x1800108bb  movups  xmm1, xmmword ptr [rax+30h]
0x1800108bf  movups  xmmword ptr [rcx+20h], xmm0
0x1800108c3  movups  xmm0, xmmword ptr [rax+40h]
0x1800108c7  movups  xmmword ptr [rcx+30h], xmm1
0x1800108cb  movups  xmm1, xmmword ptr [rax+50h]
0x1800108cf  movups  xmmword ptr [rcx+40h], xmm0
0x1800108d3  movups  xmm0, xmmword ptr [rax+60h]
0x1800108d7  movups  xmmword ptr [rcx+50h], xmm1
0x1800108db  movups  xmm1, xmmword ptr [rax+70h]
0x1800108df  add     rax, r8
0x1800108e2  movups  xmmword ptr [rcx+60h], xmm0
0x1800108e6  movups  xmmword ptr [rcx+70h], xmm1
0x1800108ea  add     rcx, r8
0x1800108ed  sub     rdx, 1
0x1800108f1  jnz     short loc_1800108A9
0x1800108f3  movups  xmm0, xmmword ptr [rax]
0x1800108f6  movups  xmm1, xmmword ptr [rax+10h]
0x1800108fa  movups  xmmword ptr [rcx], xmm0
0x1800108fd  movups  xmm0, xmmword ptr [rax+20h]
0x180010901  movups  xmmword ptr [rcx+10h], xmm1
0x180010905  movups  xmm1, xmmword ptr [rax+30h]
0x180010909  movups  xmmword ptr [rcx+20h], xmm0
0x18001090d  movups  xmm0, xmmword ptr [rax+40h]
0x180010911  mov     al, [rax+50h]
0x180010914  movups  xmmword ptr [rcx+30h], xmm1
0x180010918  movups  xmmword ptr [rcx+40h], xmm0
0x18001091c  mov     [rcx+50h], al
0x18001091f  mov     rcx, rdi
0x180010922  call    CDKsyncCache_0
0x180010927  mov     eax, [rdi+8]
0x18001092a  mov     r14d, 38h ; '8'
0x180010930  add     eax, 0Ch
0x180010933  mov     [rsp+4D0h+var_490], eax
0x180010937  cmp     eax, r14d
0x18001093a  jl      loc_180010C1B
0x180010940  lea     edx, [r14-37h]
0x180010944  mov     rcx, rdi
0x180010947  call    CDKreadBits
0x18001094c  lea     r12d, [r14-36h]
0x180010950  mov     [rsp+4D0h+var_4B0], eax
0x180010954  mov     edx, r12d
0x180010957  mov     byte ptr [rsp+4D0h+var_4A8], al
0x18001095b  mov     rcx, rdi
0x18001095e  call    CDKreadBits
0x180010963  lea     edx, [r14-37h]
0x180010967  mov     [rsp+4D0h+var_46C], eax
0x18001096b  mov     rcx, rdi
0x18001096e  mov     byte ptr [rsp+4D0h+var_4A8+1], al
0x180010972  call    CDKreadBits
0x180010977  mov     edx, r12d
0x18001097a  mov     [rsp+4D0h+var_484], eax
0x18001097e  mov     rcx, rdi
0x180010981  mov     byte ptr [rsp+4D0h+var_4A8+2], al
0x180010985  call    CDKreadBits
0x18001098a  lea     edx, [r14-34h]
0x18001098e  mov     dword ptr [rsp+4D0h+var_460], eax
0x180010992  mov     rcx, rdi
0x180010995  mov     byte ptr [rsp+4D0h+var_4A8+3], al
0x180010999  call    CDKreadBits
0x18001099e  lea     edx, [r14-37h]
0x1800109a2  mov     [rsp+4D0h+var_48C], eax
0x1800109a6  mov     rcx, rdi
0x1800109a9  mov     byte ptr [rsp+4D0h+var_4A8+4], al
0x1800109ad  call    CDKreadBits
0x1800109b2  mov     edx, r15d
0x1800109b5  mov     byte ptr [rsp+4D0h+var_4A8+5], al
0x1800109b9  mov     rcx, rdi
0x1800109bc  call    CDKreadBits
0x1800109c1  lea     edx, [r14-37h]
0x1800109c5  mov     dword ptr [rsp+4D0h+var_478], eax
0x1800109c9  mov     rcx, rdi
0x1800109cc  mov     byte ptr [rsp+4D0h+var_4A8+6], al
0x1800109d0  call    CDKreadBits
0x1800109d5  lea     edx, [r14-37h]
0x1800109d9  mov     byte ptr [rsp+4D0h+var_4A8+7], al
0x1800109dd  mov     rcx, rdi
0x1800109e0  call    CDKreadBits
0x1800109e5  lea     edx, [r14-37h]
0x1800109e9  mov     byte ptr [rsp+4D0h+var_4A8+8], al
0x1800109ed  mov     rcx, rdi
0x1800109f0  call    CDKreadBits
0x1800109f5  lea     edx, [r14-37h]
0x1800109f9  mov     byte ptr [rsp+4D0h+var_4A8+9], al
0x1800109fd  mov     rcx, rdi
0x180010a00  call    CDKreadBits
0x180010a05  lea     edx, [r14-2Bh]
0x180010a09  mov     byte ptr [rsp+4D0h+var_4A8+0Ah], al
0x180010a0d  mov     rcx, rdi
0x180010a10  call    CDKreadBits
0x180010a15  lea     edx, [r14-2Dh]
0x180010a19  mov     [rsp+4D0h+var_480], eax
0x180010a1d  mov     rcx, rdi
0x180010a20  mov     word ptr [rsp+4D0h+var_4A8+0Ch], ax
0x180010a25  call    CDKreadBits
0x180010a2a  mov     edx, r12d
0x180010a2d  mov     [rsp+4D0h+var_464], eax
0x180010a31  mov     rcx, rdi
0x180010a34  mov     word ptr [rsp+4D0h+var_4A8+0Eh], ax
0x180010a39  call    CDKreadBits
0x180010a3e  movzx   r10d, word ptr [rsp+4D0h+var_480]
0x180010a44  mov     r12d, eax
0x180010a47  mov     r9d, [rsp+4D0h+var_490]
0x180010a4c  mov     [rsp+4D0h+var_4AC], eax
0x180010a50  mov     byte ptr [rsp+4D0h+var_498], r12b
0x180010a55  lea     r11d, ds:0[r10*8]
0x180010a5d  mov     byte ptr [rsp+4D0h+var_498+1], 0
0x180010a62  mov     [rsp+4D0h+var_488], r10d
0x180010a67  mov     [rsp+4D0h+var_47C], r11d
0x180010a6c  cmp     r9d, r11d
0x180010a6f  jl      loc_180010C10
0x180010a75  lea     rcx, [rsi+18h]; struct CDK_CRCINFO *
0x180010a79  call    ?CDKcrcReset@@YAXPEAUCDK_CRCINFO@@@Z; CDKcrcReset(CDK_CRCINFO *)
0x180010a7e  xor     r8d, r8d
0x180010a81  cmp     byte ptr [rsp+4D0h+var_484], r8b
0x180010a86  jz      loc_180010CF5
0x180010a8c  cmp     byte ptr [rsp+4D0h+var_46C], r8b
0x180010a91  jnz     loc_180010B68
0x180010a97  mov     eax, [rsp+4D0h+var_48C]
0x180010a9b  cmp     al, 0Dh
0x180010a9d  jnb     loc_180010B68
0x180010aa3  cmp     byte ptr [rsp+4D0h+var_4B0], r8b
0x180010aa8  jz      loc_180010B5E
0x180010aae  cmp     [rsp+4D0h+var_468], r8d
0x180010ab3  jz      loc_180010B7A
0x180010ab9  xor     edx, edx; Val
0x180010abb  mov     r8d, 6DCh; Size
0x180010ac1  mov     rcx, r13; void *
0x180010ac4  call    memset_0
0x180010ac9  movzx   eax, [rsp+4D0h+var_460]
0x180010ace  lea     rcx, dword_18009C260
0x180010ad5  inc     eax
0x180010ad7  mov     byte ptr [r13+4C9h], 0FFh
0x180010adf  mov     byte ptr [rbx+2], 0Fh
0x180010ae3  mov     [r13+4B0h], eax
0x180010aea  mov     eax, [rsp+4D0h+var_48C]
0x180010aee  mov     [r13+4CFh], al
0x180010af5  movzx   eax, al
0x180010af8  mov     dword ptr [r13+4B8h], 400h
0x180010b03  mov     eax, [rcx+rax*4]
0x180010b06  mov     [r13+4B4h], eax
0x180010b0d  mov     eax, dword ptr [rsp+4D0h+var_478]
0x180010b11  mov     [r13+4C8h], al
0x180010b18  test    al, al
0x180010b1a  jz      loc_180010E4C
0x180010b20  movzx   eax, [rsp+4D0h+var_498]
0x180010b25  movups  xmm0, [rsp+4D0h+var_4A8]
0x180010b2a  movups  xmmword ptr [rsi], xmm0
0x180010b2d  mov     [rsi+10h], ax
0x180010b31  xor     eax, eax
0x180010b33  mov     rcx, [rbp+3D0h+var_40]
0x180010b3a  xor     rcx, rsp; StackCookie
0x180010b3d  call    __security_check_cookie
0x180010b42  mov     rbx, [rsp+4D0h+arg_18]
0x180010b4a  add     rsp, 4A0h
0x180010b51  pop     r15
0x180010b53  pop     r14
0x180010b55  pop     r13
0x180010b57  pop     r12
0x180010b59  pop     rdi
0x180010b5a  pop     rsi
0x180010b5b  pop     rbp
0x180010b5c  retn
0x180010b5e  cmp     [rsi+12h], r8b
0x180010b62  jnz     loc_180010AAE
0x180010b68  mov     edx, r11d
0x180010b6b  mov     rcx, rdi
0x180010b6e  call    CDKpushFor
0x180010b73  mov     eax, 402h
0x180010b78  jmp     short loc_180010B33
0x180010b7a  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x180010b82  mov     eax, 7FFh
0x180010b87  movdqa  xmm1, cs:__xmm@00000007000000050000000500000004
0x180010b8f  mov     ecx, [rsp+4D0h+var_464]
0x180010b93  movdqa  [rbp+3D0h+var_440], xmm0
0x180010b98  movdqa  xmm0, cs:__xmm@00000006000000000000000000000000
0x180010ba0  movdqa  [rbp+3D0h+var_430], xmm1
0x180010ba5  movdqa  xmm1, cs:__xmm@00000000000000070000001600000007
0x180010bad  movdqa  [rbp+3D0h+var_420], xmm0
0x180010bb2  movdqa  [rbp+3D0h+var_410], xmm1
0x180010bb7  cmp     cx, ax
0x180010bba  jz      loc_180010AB9
0x180010bc0  cmp     [rsi+14h], r8b
0x180010bc4  jz      loc_180010AB9
0x180010bca  movzx   eax, [rsp+4D0h+var_478]
0x180010bcf  movzx   edx, cx
0x180010bd2  imul    edx, dword ptr [rbp+rax*4+3D0h+var_440]
0x180010bd7  lea     eax, [r10+rdx*4]
0x180010bdb  lea     r12d, ds:0[rax*8]
0x180010be3  cmp     r9d, r12d
0x180010be6  jge     loc_180010E43
0x180010bec  mov     edx, r14d
0x180010bef  mov     rcx, rdi
0x180010bf2  call    CDKpushBack
0x180010bf7  xor     eax, eax
0x180010bf9  lea     ecx, [r12+r14]
0x180010bfd  cmp     ecx, 3FFF9h
0x180010c03  setnle  al
0x180010c06  add     eax, 101h
0x180010c0b  jmp     loc_180010B33
0x180010c10  mov     edx, r14d
0x180010c13  mov     rcx, rdi
0x180010c16  call    CDKpushBack
0x180010c1b  mov     eax, 101h
0x180010c20  jmp     loc_180010B33
0x180010c25  xor     r8d, r8d; int
0x180010c28  mov     rdx, rdi; struct CDK_BITSTREAM *
0x180010c2b  mov     rcx, rsi; struct STRUCT_ADTS *
0x180010c2e  call    ?adtsRead_CrcStartReg@@YAHPEAUSTRUCT_ADTS@@PEAUCDK_BITSTREAM@@H@Z; adtsRead_CrcStartReg(STRUCT_ADTS *,CDK_BITSTREAM *,int)
0x180010c33  xor     edx, edx; Val
0x180010c35  lea     rcx, [rbp+3D0h+var_220]; void *
0x180010c3c  mov     r8d, 1D1h; Size
0x180010c42  mov     r13d, eax
0x180010c45  call    memset_0
0x180010c4a  mov     r8d, r12d; unsigned int
0x180010c4d  mov     [rbp+3D0h+var_21E], 0Fh
0x180010c54  mov     rdx, rdi; struct CDK_BITSTREAM *
0x180010c57  lea     rcx, [rbp+3D0h+var_220]; struct CProgramConfig *
0x180010c5e  call    ?CProgramConfig_Read@@YAXPEAUCProgramConfig@@PEAUCDK_BITSTREAM@@I@Z; CProgramConfig_Read(CProgramConfig *,CDK_BITSTREAM *,uint)
0x180010c63  xor     eax, eax
0x180010c65  cmp     [rbp+3D0h+var_53], al
0x180010c6b  jnz     short loc_180010C8E
0x180010c6d  cmp     [rbp+3D0h+var_233], al
0x180010c73  jnz     loc_180010FD5
0x180010c79  mov     edx, r14d
0x180010c7c  mov     rcx, rdi
0x180010c7f  call    CDKpushBack
0x180010c84  mov     eax, 401h
0x180010c89  jmp     loc_180010B33
0x180010c8e  cmp     [rbp+3D0h+var_233], al
0x180010c94  jnz     loc_180010F2B
0x180010c9a  lea     rax, [rbp+3D0h+var_220]
0x180010ca1  mov     ecx, 80h
0x180010ca6  movups  xmm0, xmmword ptr [rax]
0x180010ca9  movups  xmm1, xmmword ptr [rax+10h]
0x180010cad  movups  xmmword ptr [rbx], xmm0
0x180010cb0  movups  xmm0, xmmword ptr [rax+20h]
0x180010cb4  movups  xmmword ptr [rbx+10h], xmm1
0x180010cb8  movups  xmm1, xmmword ptr [rax+30h]
0x180010cbc  movups  xmmword ptr [rbx+20h], xmm0
0x180010cc0  movups  xmm0, xmmword ptr [rax+40h]
0x180010cc4  movups  xmmword ptr [rbx+30h], xmm1
0x180010cc8  movups  xmm1, xmmword ptr [rax+50h]
0x180010ccc  movups  xmmword ptr [rbx+40h], xmm0
0x180010cd0  movups  xmm0, xmmword ptr [rax+60h]
0x180010cd4  movups  xmmword ptr [rbx+50h], xmm1
0x180010cd8  movups  xmm1, xmmword ptr [rax+70h]
0x180010cdc  add     rax, rcx
0x180010cdf  movups  xmmword ptr [rbx+60h], xmm0
0x180010ce3  movups  xmmword ptr [rbx+70h], xmm1
0x180010ce7  add     rbx, rcx
0x180010cea  sub     r15, 1
0x180010cee  jnz     short loc_180010CA6
0x180010cf0  jmp     loc_180011028
0x180010cf5  mov     edx, r14d
0x180010cf8  mov     rcx, rdi
0x180010cfb  call    CDKpushBack
0x180010d00  xor     r8d, r8d; int
0x180010d03  lea     rcx, [rsi+18h]; struct CDK_CRCINFO *
0x180010d07  mov     rdx, rdi; struct CDK_BITSTREAM *
0x180010d0a  call    ?CDKcrcStartReg@@YAHPEAUCDK_CRCINFO@@QEAUCDK_BITSTREAM@@H@Z; CDKcrcStartReg(CDK_CRCINFO *,CDK_BITSTREAM * const,int)
0x180010d0f  mov     edx, r14d
0x180010d12  mov     [rsp+4D0h+var_470], eax
0x180010d16  mov     rcx, rdi
0x180010d19  call    CDKpushFor
0x180010d1e  test    r12b, r12b
0x180010d21  jz      loc_180010DC6
  ... truncated ...
```

# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<float *>,4,1>,Binary::IntegratedSelection::MixedResponse<3,1,32,0>>::ReduceComprehensiveSDK<Data::HighDescription<ushort *>>(Binary::Definition::GeneralQuality<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<float *>,4,1>> &,Binary::Definition::GeneralQuality<Data::HighDescription<ushort *>> &)

- ea: `0x180063060`
- end: `0x1800639b9`
- name: `??$ReduceComprehensiveSDK@V?$HighDescription@PEAG@Data@@@?$SlowLocation@V?$ActiveRegion@V?$HighDescription@PEAM@Data@@$03$00@IntegratedSelection@Binary@@V?$MixedResponse@$02$00$0CA@$0A@@23@@IntegratedSelection@Binary@@AEAAXAEAV?$GeneralQuality@V?$ActiveRegion@V?$HighDescription@PEAM@Data@@$03$00@IntegratedSelection@Binary@@@Definition@2@AEAV?$GeneralQuality@V?$HighDescription@PEAG@Data@@@42@@Z`
- size: `2393`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180056cd0`

## callees

- `0x180063060`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<float *>,4,1>,Binary::IntegratedSelection::MixedResponse<3,1,32,0>>::ReduceComprehensiveSDK<Data::HighDescription<unsigned short *>>(
        _DWORD *a1,
        __int64 a2,
        int *a3)
{
  int v3; // r15d
  __int64 v4; // r9
  int v8; // r15d
  int v9; // ecx
  __int64 v10; // rbp
  int v11; // r14d
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  int v18; // r8d
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rbp
  int v23; // ecx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // edi
  __int64 v28; // rdx
  int v29; // edi
  __int64 v30; // rdx
  int v31; // edi
  __int64 v32; // rdx
  int v33; // edi
  __int64 v34; // rdx
  int v35; // edi
  __int64 v36; // rdx
  int v37; // edi
  __int64 v38; // rdx
  int v39; // edi
  __int64 v40; // rdx
  int v41; // edi
  __int64 v42; // rcx
  __int64 v43; // rbp
  __int64 v44; // r14
  int v45; // edx
  __int64 v46; // r8
  int v47; // edi
  __int64 v48; // r8
  int v49; // edi
  __int64 v50; // r8
  int v51; // edi
  __int64 v52; // r8
  int v53; // edi
  __int64 v54; // rdx
  int v55; // r8d
  int v56; // r8d
  int v57; // r14d
  int v58; // edi
  int v59; // ebp
  char v60; // al
  int v61; // ebx
  __int64 v62; // rdx
  int v63; // ecx
  int v64; // edx
  int v65; // ebp
  __int64 v66; // r15
  __int64 v67; // rcx
  int v68; // r8d
  int v69; // ecx

  v3 = a1[8];
  v4 = 0;
  if ( v3 > 0 )
    v3 = 0;
  v8 = -v3;
  *(_QWORD *)(a2 + 8) += 16LL * v8;
  v9 = a1[11];
  if ( v9 == 1 )
  {
    v10 = (int)a1[388];
    v11 = *(_DWORD *)a2 - v8;
    v12 = *a3;
    if ( (_DWORD)v10 == 1 )
    {
      v20 = a1[3];
      if ( v20 > (int)v12 )
        v20 = *a3;
      if ( v20 <= v11 )
        v11 = v20;
      v21 = 8LL * (v11 / 8);
      LOBYTE(v15) = 8 * (v11 / 8);
      if ( (unsigned __int64)(v21 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        v22 = (int)v21;
        if ( (int)v21 > 0 )
        {
          v23 = 2;
          v15 = 0;
          v24 = 6;
          do
          {
            v25 = *(_QWORD *)(a2 + 8);
            v26 = 2 * v15;
            v27 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v25 + 8 * v26 + 4) + *(float *)(v25 + 8 * v26))
                                 + *(float *)(v25 + 8 * v26 + 8))
                         * 341.0));
            if ( (unsigned __int16)v27 > 0x3ECu && (int)v4 > 0 )
              v27 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v25 + 8 * v26 - 12) + *(float *)(v25 + 8 * v26 - 16))
                                   + *(float *)(v25 + 8 * v26 - 8))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 6) = v27;
            v28 = *(_QWORD *)(a2 + 8);
            v29 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v28 + 16LL * v23 - 12) + *(float *)(v28 + 16LL * v23 - 16))
                                 + *(float *)(v28 + 16LL * v23 - 8))
                         * 341.0));
            if ( (unsigned __int16)v29 > 0x3ECu && v23 - 1 > 0 )
              v29 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v28 + 16LL * v23 - 28) + *(float *)(v28 + 16LL * v23 - 32))
                                   + *(float *)(v28 + 16LL * v23 - 24))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 4) = v29;
            v30 = *(_QWORD *)(a2 + 8);
            v31 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v30 + 16LL * v23 + 4) + *(float *)(v30 + 16LL * v23))
                                 + *(float *)(v30 + 16LL * v23 + 8))
                         * 341.0));
            if ( (unsigned __int16)v31 > 0x3ECu && v23 > 0 )
              v31 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v30 + 16LL * v23 - 12) + *(float *)(v30 + 16LL * v23 - 16))
                                   + *(float *)(v30 + 16LL * v23 - 8))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 2) = v31;
            v32 = *(_QWORD *)(a2 + 8);
            v33 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v32 + 16 * (v23 + 1LL) + 4) + *(float *)(v32 + 16 * (v23 + 1LL)))
                                 + *(float *)(v32 + 16 * (v23 + 1LL) + 8))
                         * 341.0));
            if ( (unsigned __int16)v33 > 0x3ECu && v23 + 1 > 0 )
              v33 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v32 + 16 * (v23 + 1LL) - 12)
                                           + *(float *)(v32 + 16 * (v23 + 1LL) - 16))
                                   + *(float *)(v32 + 16 * (v23 + 1LL) - 8))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1)) = v33;
            v34 = *(_QWORD *)(a2 + 8);
            v35 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v34 + 16 * (v23 + 2LL) + 4) + *(float *)(v34 + 16 * (v23 + 2LL)))
                                 + *(float *)(v34 + 16 * (v23 + 2LL) + 8))
                         * 341.0));
            if ( (unsigned __int16)v35 > 0x3ECu && v23 + 2 > 0 )
              v35 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v34 + 16 * (v23 + 2LL) - 12)
                                           + *(float *)(v34 + 16 * (v23 + 2LL) - 16))
                                   + *(float *)(v34 + 16 * (v23 + 2LL) - 8))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 2) = v35;
            v36 = *(_QWORD *)(a2 + 8);
            v37 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v36 + 16 * (v23 + 3LL) + 4) + *(float *)(v36 + 16 * (v23 + 3LL)))
                                 + *(float *)(v36 + 16 * (v23 + 3LL) + 8))
                         * 341.0));
            if ( (unsigned __int16)v37 > 0x3ECu && v23 + 3 > 0 )
              v37 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v36 + 16 * (v23 + 3LL) - 12)
                                           + *(float *)(v36 + 16 * (v23 + 3LL) - 16))
                                   + *(float *)(v36 + 16 * (v23 + 3LL) - 8))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 4) = v37;
            v38 = *(_QWORD *)(a2 + 8);
            v39 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v38 + 16 * (v23 + 4LL) + 4) + *(float *)(v38 + 16 * (v23 + 4LL)))
                                 + *(float *)(v38 + 16 * (v23 + 4LL) + 8))
                         * 341.0));
            if ( (unsigned __int16)v39 > 0x3ECu && v23 + 4 > 0 )
              v39 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v38 + 16 * (v23 + 4LL) - 12)
                                           + *(float *)(v38 + 16 * (v23 + 4LL) - 16))
                                   + *(float *)(v38 + 16 * (v23 + 4LL) - 8))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 6) = v39;
            v40 = *(_QWORD *)(a2 + 8);
            v41 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v40 + 16 * (v23 + 5LL) + 4) + *(float *)(v40 + 16 * (v23 + 5LL)))
                                 + *(float *)(v40 + 16 * (v23 + 5LL) + 8))
                         * 341.0));
            if ( (unsigned __int16)v41 > 0x3ECu && v23 + 5 > 0 )
              v41 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v40 + 16 * (v23 + 5LL) - 12)
                                           + *(float *)(v40 + 16 * (v23 + 5LL) - 16))
                                   + *(float *)(v40 + 16 * (v23 + 5LL) - 8))
                           * 341.0));
            LODWORD(v4) = v4 + 8;
            v23 += 8;
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 8) = v41;
            v24 += 16;
            v15 = (int)v4;
          }
          while ( (int)v4 < v22 );
        }
      }
      v42 = (int)v4;
      v43 = v11;
      if ( (int)v4 < (__int64)v11 )
      {
        if ( v11 - (__int64)(int)v4 < 4 )
          goto LABEL_104;
        v44 = v11 - 3LL;
        v45 = v4 + 2;
        do
        {
          v46 = *(_QWORD *)(a2 + 8);
          v47 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(v46 + 16LL * (int)v4 + 4) + *(float *)(v46 + 16LL * (int)v4))
                               + *(float *)(v46 + 16LL * (int)v4 + 8))
                       * 341.0));
          if ( (unsigned __int16)v47 > 0x3ECu && (int)v4 > 0 )
            v47 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v46 + 16LL * (int)v4 - 12) + *(float *)(v46 + 16LL * (int)v4 - 16))
                                 + *(float *)(v46 + 16LL * (int)v4 - 8))
                         * 341.0));
          *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v42) = v47;
          v48 = *(_QWORD *)(a2 + 8);
          v49 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(v48 + 16LL * v45 - 12) + *(float *)(v48 + 16LL * v45 - 16))
                               + *(float *)(v48 + 16LL * v45 - 8))
                       * 341.0));
          if ( (unsigned __int16)v49 > 0x3ECu && v45 - 1 > 0 )
            v49 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v48 + 16LL * v45 - 28) + *(float *)(v48 + 16LL * v45 - 32))
                                 + *(float *)(v48 + 16LL * v45 - 24))
                         * 341.0));
          *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v42 + 2) = v49;
          v50 = *(_QWORD *)(a2 + 8);
          v51 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(v50 + 16LL * v45 + 4) + *(float *)(v50 + 16LL * v45))
                               + *(float *)(v50 + 16LL * v45 + 8))
                       * 341.0));
          if ( (unsigned __int16)v51 > 0x3ECu && v45 > 0 )
            v51 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v50 + 16LL * v45 - 12) + *(float *)(v50 + 16LL * v45 - 16))
                                 + *(float *)(v50 + 16LL * v45 - 8))
                         * 341.0));
          *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v42 + 4) = v51;
          v52 = *(_QWORD *)(a2 + 8);
          v53 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(v52 + 16 * (v45 + 1LL) + 4) + *(float *)(v52 + 16 * (v45 + 1LL)))
                               + *(float *)(v52 + 16 * (v45 + 1LL) + 8))
                       * 341.0));
          if ( (unsigned __int16)v53 > 0x3ECu && v45 + 1 > 0 )
            v53 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v52 + 16 * (v45 + 1LL) - 12)
                                         + *(float *)(v52 + 16 * (v45 + 1LL) - 16))
                                 + *(float *)(v52 + 16 * (v45 + 1LL) - 8))
                         * 341.0));
          v15 = *((_QWORD *)a3 + 1);
          LODWORD(v4) = v4 + 4;
          v45 += 4;
          *(_WORD *)(v15 + 2 * v42 + 6) = v53;
          v42 += 4;
        }
        while ( v42 < v44 );
        if ( v42 < v43 )
        {
LABEL_104:
          do
          {
            v54 = *(_QWORD *)(a2 + 8);
            v55 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v54 + 16LL * (int)v4 + 4) + *(float *)(v54 + 16LL * (int)v4))
                                 + *(float *)(v54 + 16LL * (int)v4 + 8))
                         * 341.0));
            if ( (unsigned __int16)v55 > 0x3ECu && (int)v4 > 0 )
              v55 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(v54 + 16LL * (int)v4 - 12)
                                           + *(float *)(v54 + 16LL * (int)v4 - 16))
                                   + *(float *)(v54 + 16LL * (int)v4 - 8))
                           * 341.0));
            v15 = *((_QWORD *)a3 + 1);
            LODWORD(v4) = v4 + 1;
            *(_WORD *)(v15 + 2 * v42++) = v55;
          }
          while ( v42 < v43 );
        }
      }
    }
    else
    {
      v13 = v10 * v12;
      v14 = 0;
      if ( (unsigned __int64)(v13 + 0x80000000LL) > 0xFFFFFFFF )
      {
        LOBYTE(v15) = 0;
      }
      else
      {
        v14 = v13;
        LOBYTE(v15) = 1;
      }
      v16 = 0;
      if ( !(_BYTE)v15 )
        v14 = 0;
      if ( a1[3] <= v14 )
        v14 = a1[3];
      if ( v14 > v11 )
        v14 = v11;
      if ( v14 > 0 )
      {
        do
        {
          v17 = *(_QWORD *)(a2 + 8);
          v18 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(v17 + 16LL * v16 + 4) + *(float *)(v17 + 16LL * v16))
                               + *(float *)(v17 + 16LL * v16 + 8))
                       * 341.0));
          if ( (unsigned __int16)v18 > 0x3ECu && v16 > 0 )
            v18 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(v17 + 16LL * v16 - 12) + *(float *)(v17 + 16LL * v16 - 16))
                                 + *(float *)(v17 + 16LL * v16 - 8))
                         * 341.0));
          v15 = *((_QWORD *)a3 + 1);
          v19 = v4++;
          v16 += v10;
          *(_WORD *)(v15 + 2 * v19) = v18;
        }
        while ( v16 < v14 );
      }
    }
  }
  else
  {
    v56 = a1[9];
    v57 = v9;
    if ( v9 <= 0 )
      v57 = 1;
    if ( v56 < 0 || v56 >= v57 )
    {
      v56 %= v57;
      if ( v56 < 0 )
        v56 += v57;
    }
    v58 = v56;
    v59 = 0;
    if ( (unsigned __int64)(*a3 * (__int64)(int)a1[762] + 0x80000000LL) > 0xFFFFFFFF )
    {
      v60 = 0;
    }
    else
    {
      v59 = *a3 * a1[762];
      v60 = 1;
    }
    if ( !v60 )
      v59 = 0;
    v61 = v59 / v9;
    v62 = (unsigned int)(*a3 >> 31);
    LODWORD(v62) = *a3 % v9;
    LODWORD(v15) = *a3 / v9;
    if ( (int)v62 > 0 )
    {
      do
      {
        v61 += a1[v56 + 388];
        v63 = v56 + 1;
        v56 = 0;
        if ( v63 < v57 )
          v56 = v63;
        --v62;
      }
      while ( v62 );
    }
    v64 = 0;
    v65 = *(_DWORD *)a2 - v8;
    if ( v61 > a1[3] )
      v61 = a1[3];
    if ( v61 <= v65 )
      v65 = v61;
    if ( v65 > 0 )
    {
      v66 = 0;
      do
      {
        v67 = *(_QWORD *)(a2 + 8);
        v68 = (int)fmaxf(
                     0.0,
                     fminf(
                       1023.0,
                       (float)((float)(*(float *)(v67 + 16LL * v64 + 4) + *(float *)(v67 + 16LL * v64))
                             + *(float *)(v67 + 16LL * v64 + 8))
                     * 341.0));
        if ( (unsigned __int16)v68 > 0x3ECu && v64 > 0 )
          v68 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(v67 + 16LL * v64 - 12) + *(float *)(v67 + 16LL * v64 - 16))
                               + *(float *)(v67 + 16LL * v64 - 8))
                       * 341.0));
        v69 = v58 + 1;
        *(_WORD *)(v66 + *((_QWORD *)a3 + 1)) = v68;
        v66 += 2;
        v15 = v58;
        v58 = 0;
        v64 += a1[v15 + 388];
        if ( v69 < v57 )
          v58 = v69;
      }
      while ( v64 < v65 );
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180063060  mov     [rsp+arg_0], rbx
0x180063065  mov     [rsp+arg_8], rbp
0x18006306a  mov     [rsp+arg_10], rsi
0x18006306f  mov     [rsp+arg_18], rdi
0x180063074  push    r14
0x180063076  push    r15
0x180063078  mov     r15d, [rcx+20h]
0x18006307c  xor     r9d, r9d
0x18006307f  test    r15d, r15d
0x180063082  mov     rsi, rcx
0x180063085  mov     r10, r8
0x180063088  mov     r11, rdx
0x18006308b  cmovg   r15d, r9d
0x18006308f  neg     r15d
0x180063092  movsxd  rax, r15d
0x180063095  shl     rax, 4
0x180063099  add     [rdx+8], rax
0x18006309d  mov     ecx, [rcx+2Ch]
0x1800630a0  cmp     ecx, 1
0x1800630a3  jnz     loc_18006383F
0x1800630a9  mov     r14d, [rdx]
0x1800630ac  movsxd  rbp, dword ptr [rsi+610h]
0x1800630b3  sub     r14d, r15d
0x1800630b6  movsxd  rcx, dword ptr [r8]
0x1800630b9  cmp     ebp, 1
0x1800630bc  jz      loc_18006319F
0x1800630c2  imul    rcx, rbp
0x1800630c6  mov     eax, 80000000h
0x1800630cb  mov     edx, 0FFFFFFFFh
0x1800630d0  add     rax, rcx
0x1800630d3  mov     edi, r9d
0x1800630d6  cmp     rax, rdx
0x1800630d9  ja      short loc_1800630E1
0x1800630db  mov     edi, ecx
0x1800630dd  mov     al, 1
0x1800630df  jmp     short loc_1800630E3
0x1800630e1  xor     al, al
0x1800630e3  test    al, al
0x1800630e5  mov     edx, r9d
0x1800630e8  cmovz   edi, r9d
0x1800630ec  cmp     [rsi+0Ch], edi
0x1800630ef  cmovle  edi, [rsi+0Ch]
0x1800630f3  cmp     edi, r14d
0x1800630f6  cmovg   edi, r14d
0x1800630fa  test    edi, edi
0x1800630fc  jle     loc_1800639A0
0x180063102  movss   xmm2, cs:__real@43aa8000
0x18006310a  mov     ebx, 3ECh
0x18006310f  movss   xmm3, cs:__real@447fc000
0x180063117  nop     word ptr [rax+rax+00000000h]
0x180063120  mov     rcx, [r11+8]
0x180063124  movaps  xmm1, xmm3
0x180063127  movsxd  rax, edx
0x18006312a  add     rax, rax
0x18006312d  movss   xmm0, dword ptr [rcx+rax*8+4]
0x180063133  addss   xmm0, dword ptr [rcx+rax*8]
0x180063138  addss   xmm0, dword ptr [rcx+rax*8+8]
0x18006313e  mulss   xmm0, xmm2
0x180063142  minss   xmm1, xmm0
0x180063146  xorps   xmm0, xmm0
0x180063149  maxss   xmm0, xmm1
0x18006314d  cvttss2si r8d, xmm0
0x180063152  cmp     r8w, bx
0x180063156  jbe     short loc_180063185
0x180063158  test    edx, edx
0x18006315a  jle     short loc_180063185
0x18006315c  movss   xmm0, dword ptr [rcx+rax*8-0Ch]
0x180063162  movaps  xmm1, xmm3
0x180063165  addss   xmm0, dword ptr [rcx+rax*8-10h]
0x18006316b  addss   xmm0, dword ptr [rcx+rax*8-8]
0x180063171  mulss   xmm0, xmm2
0x180063175  minss   xmm1, xmm0
0x180063179  xorps   xmm0, xmm0
0x18006317c  maxss   xmm0, xmm1
0x180063180  cvttss2si r8d, xmm0
0x180063185  mov     rax, [r10+8]
0x180063189  mov     rcx, r9
0x18006318c  inc     r9
0x18006318f  add     edx, ebp
0x180063191  mov     [rax+rcx*2], r8w
0x180063196  cmp     edx, edi
0x180063198  jl      short loc_180063120
0x18006319a  jmp     loc_1800639A0
0x18006319f  mov     eax, [rsi+0Ch]
0x1800631a2  mov     ebx, 3ECh
0x1800631a7  movss   xmm2, cs:__real@43aa8000
0x1800631af  cmp     eax, ecx
0x1800631b1  movss   xmm3, cs:__real@447fc000
0x1800631b9  cmovg   eax, ecx
0x1800631bc  cmp     eax, r14d
0x1800631bf  cmovle  r14d, eax
0x1800631c3  mov     eax, r14d
0x1800631c6  cdq
0x1800631c7  and     edx, 7
0x1800631ca  add     eax, edx
0x1800631cc  mov     edx, 0FFFFFFFFh
0x1800631d1  sar     eax, 3
0x1800631d4  movsxd  rcx, eax
0x1800631d7  mov     eax, 80000000h
0x1800631dc  shl     rcx, 3
0x1800631e0  add     rax, rcx
0x1800631e3  cmp     rax, rdx
0x1800631e6  ja      loc_1800635AA
0x1800631ec  movsxd  rbp, ecx
0x1800631ef  test    ecx, ecx
0x1800631f1  jle     loc_1800635AA
0x1800631f7  mov     ecx, 2
0x1800631fc  mov     rax, r9
0x1800631ff  lea     r8d, [rcx+4]
0x180063203  nop     dword ptr [rax+00h]
0x180063207  nop     word ptr [rax+rax+00000000h]
0x180063210  mov     rdx, [r11+8]
0x180063214  add     rax, rax
0x180063217  movaps  xmm1, xmm3
0x18006321a  movss   xmm0, dword ptr [rdx+rax*8+4]
0x180063220  addss   xmm0, dword ptr [rdx+rax*8]
0x180063225  addss   xmm0, dword ptr [rdx+rax*8+8]
0x18006322b  mulss   xmm0, xmm2
0x18006322f  minss   xmm1, xmm0
0x180063233  xorps   xmm0, xmm0
0x180063236  maxss   xmm0, xmm1
0x18006323a  cvttss2si edi, xmm0
0x18006323e  cmp     di, bx
0x180063241  jbe     short loc_180063270
0x180063243  test    r9d, r9d
0x180063246  jle     short loc_180063270
0x180063248  movss   xmm0, dword ptr [rdx+rax*8-0Ch]
0x18006324e  movaps  xmm1, xmm3
0x180063251  addss   xmm0, dword ptr [rdx+rax*8-10h]
0x180063257  addss   xmm0, dword ptr [rdx+rax*8-8]
0x18006325d  mulss   xmm0, xmm2
0x180063261  minss   xmm1, xmm0
0x180063265  xorps   xmm0, xmm0
0x180063268  maxss   xmm0, xmm1
0x18006326c  cvttss2si edi, xmm0
0x180063270  mov     rax, [r10+8]
0x180063274  lea     esi, [rcx-1]
0x180063277  movaps  xmm1, xmm3
0x18006327a  mov     [r8+rax-6], di
0x180063280  mov     rdx, [r11+8]
0x180063284  movsxd  rax, ecx
0x180063287  add     rax, rax
0x18006328a  movss   xmm0, dword ptr [rdx+rax*8-0Ch]
0x180063290  addss   xmm0, dword ptr [rdx+rax*8-10h]
0x180063296  addss   xmm0, dword ptr [rdx+rax*8-8]
0x18006329c  mulss   xmm0, xmm2
0x1800632a0  minss   xmm1, xmm0
0x1800632a4  xorps   xmm0, xmm0
0x1800632a7  maxss   xmm0, xmm1
0x1800632ab  cvttss2si edi, xmm0
0x1800632af  cmp     di, bx
0x1800632b2  jbe     short loc_1800632E0
0x1800632b4  test    esi, esi
0x1800632b6  jle     short loc_1800632E0
0x1800632b8  movss   xmm0, dword ptr [rdx+rax*8-1Ch]
0x1800632be  movaps  xmm1, xmm3
0x1800632c1  addss   xmm0, dword ptr [rdx+rax*8-20h]
0x1800632c7  addss   xmm0, dword ptr [rdx+rax*8-18h]
0x1800632cd  mulss   xmm0, xmm2
0x1800632d1  minss   xmm1, xmm0
0x1800632d5  xorps   xmm0, xmm0
0x1800632d8  maxss   xmm0, xmm1
0x1800632dc  cvttss2si edi, xmm0
0x1800632e0  mov     rax, [r10+8]
0x1800632e4  movaps  xmm1, xmm3
0x1800632e7  mov     [r8+rax-4], di
0x1800632ed  mov     rdx, [r11+8]
0x1800632f1  movsxd  rax, ecx
0x1800632f4  add     rax, rax
0x1800632f7  movss   xmm0, dword ptr [rdx+rax*8+4]
0x1800632fd  addss   xmm0, dword ptr [rdx+rax*8]
0x180063302  addss   xmm0, dword ptr [rdx+rax*8+8]
0x180063308  mulss   xmm0, xmm2
0x18006330c  minss   xmm1, xmm0
0x180063310  xorps   xmm0, xmm0
0x180063313  maxss   xmm0, xmm1
0x180063317  cvttss2si edi, xmm0
0x18006331b  cmp     di, bx
0x18006331e  jbe     short loc_18006334C
0x180063320  test    ecx, ecx
0x180063322  jle     short loc_18006334C
0x180063324  movss   xmm0, dword ptr [rdx+rax*8-0Ch]
0x18006332a  movaps  xmm1, xmm3
0x18006332d  addss   xmm0, dword ptr [rdx+rax*8-10h]
0x180063333  addss   xmm0, dword ptr [rdx+rax*8-8]
0x180063339  mulss   xmm0, xmm2
0x18006333d  minss   xmm1, xmm0
0x180063341  xorps   xmm0, xmm0
0x180063344  maxss   xmm0, xmm1
0x180063348  cvttss2si edi, xmm0
0x18006334c  mov     rax, [r10+8]
0x180063350  lea     esi, [rcx+1]
0x180063353  movaps  xmm1, xmm3
0x180063356  mov     [r8+rax-2], di
0x18006335c  mov     rdx, [r11+8]
0x180063360  movsxd  rax, ecx
0x180063363  inc     rax
0x180063366  add     rax, rax
0x180063369  movss   xmm0, dword ptr [rdx+rax*8+4]
0x18006336f  addss   xmm0, dword ptr [rdx+rax*8]
0x180063374  addss   xmm0, dword ptr [rdx+rax*8+8]
0x18006337a  mulss   xmm0, xmm2
0x18006337e  minss   xmm1, xmm0
0x180063382  xorps   xmm0, xmm0
0x180063385  maxss   xmm0, xmm1
0x180063389  cvttss2si edi, xmm0
0x18006338d  cmp     di, bx
0x180063390  jbe     short loc_1800633BE
0x180063392  test    esi, esi
0x180063394  jle     short loc_1800633BE
0x180063396  movss   xmm0, dword ptr [rdx+rax*8-0Ch]
0x18006339c  movaps  xmm1, xmm3
0x18006339f  addss   xmm0, dword ptr [rdx+rax*8-10h]
0x1800633a5  addss   xmm0, dword ptr [rdx+rax*8-8]
0x1800633ab  mulss   xmm0, xmm2
0x1800633af  minss   xmm1, xmm0
0x1800633b3  xorps   xmm0, xmm0
0x1800633b6  maxss   xmm0, xmm1
0x1800633ba  cvttss2si edi, xmm0
0x1800633be  mov     rax, [r10+8]
0x1800633c2  lea     esi, [rcx+2]
0x1800633c5  movaps  xmm1, xmm3
0x1800633c8  mov     [r8+rax], di
0x1800633cd  mov     rdx, [r11+8]
0x1800633d1  movsxd  rax, ecx
0x1800633d4  add     rax, 2
0x1800633d8  add     rax, rax
0x1800633db  movss   xmm0, dword ptr [rdx+rax*8+4]
0x1800633e1  addss   xmm0, dword ptr [rdx+rax*8]
0x1800633e6  addss   xmm0, dword ptr [rdx+rax*8+8]
0x1800633ec  mulss   xmm0, xmm2
0x1800633f0  minss   xmm1, xmm0
0x1800633f4  xorps   xmm0, xmm0
0x1800633f7  maxss   xmm0, xmm1
0x1800633fb  cvttss2si edi, xmm0
0x1800633ff  cmp     di, bx
0x180063402  jbe     short loc_180063430
0x180063404  test    esi, esi
0x180063406  jle     short loc_180063430
0x180063408  movss   xmm0, dword ptr [rdx+rax*8-0Ch]
0x18006340e  movaps  xmm1, xmm3
0x180063411  addss   xmm0, dword ptr [rdx+rax*8-10h]
0x180063417  addss   xmm0, dword ptr [rdx+rax*8-8]
0x18006341d  mulss   xmm0, xmm2
0x180063421  minss   xmm1, xmm0
0x180063425  xorps   xmm0, xmm0
0x180063428  maxss   xmm0, xmm1
0x18006342c  cvttss2si edi, xmm0
0x180063430  mov     rax, [r10+8]
0x180063434  lea     esi, [rcx+3]
0x180063437  movaps  xmm1, xmm3
0x18006343a  mov     [r8+rax+2], di
0x180063440  mov     rdx, [r11+8]
0x180063444  movsxd  rax, ecx
0x180063447  add     rax, 3
0x18006344b  add     rax, rax
0x18006344e  movss   xmm0, dword ptr [rdx+rax*8+4]
0x180063454  addss   xmm0, dword ptr [rdx+rax*8]
0x180063459  addss   xmm0, dword ptr [rdx+rax*8+8]
0x18006345f  mulss   xmm0, xmm2
0x180063463  minss   xmm1, xmm0
0x180063467  xorps   xmm0, xmm0
0x18006346a  maxss   xmm0, xmm1
0x18006346e  cvttss2si edi, xmm0
0x180063472  cmp     di, bx
0x180063475  jbe     short loc_1800634A3
0x180063477  test    esi, esi
0x180063479  jle     short loc_1800634A3
0x18006347b  movss   xmm0, dword ptr [rdx+rax*8-0Ch]
0x180063481  movaps  xmm1, xmm3
0x180063484  addss   xmm0, dword ptr [rdx+rax*8-10h]
0x18006348a  addss   xmm0, dword ptr [rdx+rax*8-8]
0x180063490  mulss   xmm0, xmm2
0x180063494  minss   xmm1, xmm0
0x180063498  xorps   xmm0, xmm0
0x18006349b  maxss   xmm0, xmm1
0x18006349f  cvttss2si edi, xmm0
0x1800634a3  mov     rax, [r10+8]
0x1800634a7  lea     esi, [rcx+4]
0x1800634aa  movaps  xmm1, xmm3
0x1800634ad  mov     [r8+rax+4], di
0x1800634b3  mov     rdx, [r11+8]
0x1800634b7  movsxd  rax, ecx
0x1800634ba  add     rax, 4
0x1800634be  add     rax, rax
0x1800634c1  movss   xmm0, dword ptr [rdx+rax*8+4]
0x1800634c7  addss   xmm0, dword ptr [rdx+rax*8]
0x1800634cc  addss   xmm0, dword ptr [rdx+rax*8+8]
0x1800634d2  mulss   xmm0, xmm2
0x1800634d6  minss   xmm1, xmm0
0x1800634da  xorps   xmm0, xmm0
0x1800634dd  maxss   xmm0, xmm1
0x1800634e1  cvttss2si edi, xmm0
0x1800634e5  cmp     di, bx
0x1800634e8  jbe     short loc_180063516
0x1800634ea  test    esi, esi
0x1800634ec  jle     short loc_180063516
0x1800634ee  movss   xmm0, dword ptr [rdx+rax*8-0Ch]
0x1800634f4  movaps  xmm1, xmm3
0x1800634f7  addss   xmm0, dword ptr [rdx+rax*8-10h]
  ... truncated ...
```

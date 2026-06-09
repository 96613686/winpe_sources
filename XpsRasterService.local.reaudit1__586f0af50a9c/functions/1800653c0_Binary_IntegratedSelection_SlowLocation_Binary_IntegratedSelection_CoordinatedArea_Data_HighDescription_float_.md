# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<float *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,1,32,0>>::ReduceComprehensiveSDK<Data::HighDescription<ushort *>>(Binary::Definition::GeneralQuality<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<float *>,3,0>> &,Binary::Definition::GeneralQuality<Data::HighDescription<ushort *>> &)

- ea: `0x1800653c0`
- end: `0x180065d8a`
- name: `??$ReduceComprehensiveSDK@V?$HighDescription@PEAG@Data@@@?$SlowLocation@V?$CoordinatedArea@V?$HighDescription@PEAM@Data@@$02$0A@@IntegratedSelection@Binary@@V?$MixedResponse@$02$00$0CA@$0A@@23@@IntegratedSelection@Binary@@AEAAXAEAV?$GeneralQuality@V?$CoordinatedArea@V?$HighDescription@PEAM@Data@@$02$0A@@IntegratedSelection@Binary@@@Definition@2@AEAV?$GeneralQuality@V?$HighDescription@PEAG@Data@@@42@@Z`
- size: `2506`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800582d0`

## callees

- `0x1800653c0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<float *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,1,32,0>>::ReduceComprehensiveSDK<Data::HighDescription<unsigned short *>>(
        _DWORD *a1,
        __int64 a2,
        int *a3)
{
  int v3; // r15d
  __int64 v5; // r10
  int v8; // r15d
  __int64 v9; // rcx
  int v10; // ecx
  __int64 v11; // r14
  int v12; // r12d
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // ebx
  __int64 v16; // rax
  int v17; // r11d
  int v18; // edx
  __int64 v19; // r8
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r15
  __int64 v24; // rbx
  __int64 v25; // rdi
  int v26; // r11d
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // r8
  int v30; // ecx
  __int64 v31; // r8
  __int64 v32; // rax
  int v33; // ecx
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  int v37; // ecx
  __int64 v38; // rax
  __int64 v39; // r8
  int v40; // ecx
  __int64 v41; // r8
  __int64 v42; // r8
  int v43; // ecx
  __int64 v44; // r8
  __int64 v45; // rax
  __int64 v46; // r8
  int v47; // ecx
  __int64 v48; // r8
  __int64 v49; // rax
  __int64 v50; // r8
  int v51; // ecx
  __int64 v52; // r8
  __int64 v53; // r11
  __int64 v54; // rax
  int v55; // ecx
  __int64 v56; // r8
  int v57; // r8d
  int v58; // r14d
  __int64 v59; // r13
  int v60; // ebx
  int v61; // r12d
  char v62; // al
  int v63; // r11d
  int v64; // ecx
  int v65; // r12d
  int v66; // r11d
  __int64 v67; // r15
  int v68; // ecx
  int v69; // ecx

  v3 = a1[8];
  v5 = 0;
  if ( v3 > 0 )
    v3 = 0;
  v8 = -v3;
  *(_QWORD *)(a2 + 8) += 4 * *(_QWORD *)(a2 + 32) * v8;
  v9 = 4 * *(_QWORD *)(a2 + 32) * v8;
  *(_QWORD *)(a2 + 16) += v9;
  *(_QWORD *)(a2 + 24) += v9;
  v10 = a1[11];
  if ( v10 == 1 )
  {
    v11 = (int)a1[388];
    v12 = *(_DWORD *)a2 - v8;
    v13 = *a3;
    if ( (_DWORD)v11 == 1 )
    {
      v21 = a1[3];
      if ( v21 > (int)v13 )
        v21 = *a3;
      if ( v21 <= v12 )
        v12 = v21;
      v22 = 8LL * (v12 / 8);
      LOBYTE(v16) = 8 * (v12 / 8);
      if ( (unsigned __int64)(v22 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        v23 = (int)v22;
        if ( (int)v22 > 0 )
        {
          v24 = 6;
          v25 = 0;
          v26 = 2;
          do
          {
            v27 = *(_QWORD *)(a2 + 24);
            v28 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * *(_QWORD *)(a2 + 32) * v25)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * *(_QWORD *)(a2 + 32) * v25))
                                 + *(float *)(v27 + 4 * *(_QWORD *)(a2 + 32) * v25))
                         * 341.0));
            if ( (unsigned __int16)v28 > 0x3ECu && (int)v5 > 0 )
              v28 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * *(_QWORD *)(a2 + 32) * (v25 - 1))
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * *(_QWORD *)(a2 + 32) * (v25 - 1)))
                                   + *(float *)(v27 + 4 * *(_QWORD *)(a2 + 32) * (v25 - 1)))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 6) = v28;
            v29 = *(_QWORD *)(a2 + 32) * (v26 - 1LL);
            v30 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 16) + 4 * v29)
                                         + *(float *)(*(_QWORD *)(a2 + 8) + 4 * v29))
                                 + *(float *)(*(_QWORD *)(a2 + 24) + 4 * v29))
                         * 341.0));
            if ( (unsigned __int16)v30 > 0x3ECu && v26 - 1 > 0 )
            {
              v31 = *(_QWORD *)(a2 + 32) * (v26 - 2LL);
              v30 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v31)
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v31))
                                   + *(float *)(*(_QWORD *)(a2 + 24) + 4 * v31))
                           * 341.0));
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 - 4) = v30;
            v32 = *(_QWORD *)(a2 + 24);
            v33 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * *(_QWORD *)(a2 + 32) * v26)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * *(_QWORD *)(a2 + 32) * v26))
                                 + *(float *)(v32 + 4 * *(_QWORD *)(a2 + 32) * v26))
                         * 341.0));
            if ( (unsigned __int16)v33 > 0x3ECu && v26 > 0 )
            {
              v34 = *(_QWORD *)(a2 + 32) * (v26 - 1LL);
              v33 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v34)
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v34))
                                   + *(float *)(v32 + 4 * v34))
                           * 341.0));
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 - 2) = v33;
            v35 = *(_QWORD *)(a2 + 24);
            v36 = *(_QWORD *)(a2 + 32) * (v26 + 1LL);
            v37 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v36)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v36))
                                 + *(float *)(v35 + 4 * v36))
                         * 341.0));
            if ( (unsigned __int16)v37 > 0x3ECu && v26 + 1 > 0 )
              v37 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * *(_QWORD *)(a2 + 32) * v26)
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * *(_QWORD *)(a2 + 32) * v26))
                                   + *(float *)(v35 + 4 * *(_QWORD *)(a2 + 32) * v26))
                           * 341.0));
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1)) = v37;
            v38 = *(_QWORD *)(a2 + 24);
            v39 = *(_QWORD *)(a2 + 32) * (v26 + 2LL);
            v40 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v39)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v39))
                                 + *(float *)(v38 + 4 * v39))
                         * 341.0));
            if ( (unsigned __int16)v40 > 0x3ECu && v26 + 2 > 0 )
            {
              v41 = *(_QWORD *)(a2 + 32) * (v26 + 1LL);
              v40 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v41)
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v41))
                                   + *(float *)(v38 + 4 * v41))
                           * 341.0));
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 + 2) = v40;
            v42 = *(_QWORD *)(a2 + 32) * (v26 + 3LL);
            v43 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 16) + 4 * v42)
                                         + *(float *)(*(_QWORD *)(a2 + 8) + 4 * v42))
                                 + *(float *)(*(_QWORD *)(a2 + 24) + 4 * v42))
                         * 341.0));
            if ( (unsigned __int16)v43 > 0x3ECu && v26 + 3 > 0 )
            {
              v44 = *(_QWORD *)(a2 + 32) * (v26 + 2LL);
              v43 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v44)
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v44))
                                   + *(float *)(*(_QWORD *)(a2 + 24) + 4 * v44))
                           * 341.0));
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 + 4) = v43;
            v45 = *(_QWORD *)(a2 + 24);
            v46 = *(_QWORD *)(a2 + 32) * (v26 + 4LL);
            v47 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v46)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v46))
                                 + *(float *)(v45 + 4 * v46))
                         * 341.0));
            if ( (unsigned __int16)v47 > 0x3ECu && v26 + 4 > 0 )
            {
              v48 = *(_QWORD *)(a2 + 32) * (v26 + 3LL);
              v47 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v48)
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v48))
                                   + *(float *)(v45 + 4 * v48))
                           * 341.0));
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 6) = v47;
            v49 = *(_QWORD *)(a2 + 24);
            v50 = *(_QWORD *)(a2 + 32) * (v26 + 5LL);
            v51 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v50)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v50))
                                 + *(float *)(v49 + 4 * v50))
                         * 341.0));
            if ( (unsigned __int16)v51 > 0x3ECu && v26 + 5 > 0 )
            {
              v52 = *(_QWORD *)(a2 + 32) * (v26 + 4LL);
              v51 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v52)
                                           + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v52))
                                   + *(float *)(v49 + 4 * v52))
                           * 341.0));
            }
            v16 = *((_QWORD *)a3 + 1);
            LODWORD(v5) = v5 + 8;
            v26 += 8;
            v25 = (int)v5;
            *(_WORD *)(v24 + v16 + 8) = v51;
            v24 += 16;
          }
          while ( (int)v5 < v23 );
        }
      }
      v53 = (int)v5;
      if ( (int)v5 < (__int64)v12 )
      {
        do
        {
          v54 = *(_QWORD *)(a2 + 24);
          v55 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * *(_QWORD *)(a2 + 32) * (int)v5)
                                       + *(float *)(*(_QWORD *)(a2 + 16) + 4 * *(_QWORD *)(a2 + 32) * (int)v5))
                               + *(float *)(v54 + 4 * *(_QWORD *)(a2 + 32) * (int)v5))
                       * 341.0));
          if ( (unsigned __int16)v55 > 0x3ECu && (int)v5 > 0 )
          {
            v56 = *(_QWORD *)(a2 + 32) * ((int)v5 - 1LL);
            v55 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v56)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v56))
                                 + *(float *)(v54 + 4 * v56))
                         * 341.0));
          }
          v16 = *((_QWORD *)a3 + 1);
          LODWORD(v5) = v5 + 1;
          *(_WORD *)(v16 + 2 * v53++) = v55;
        }
        while ( v53 < v12 );
      }
    }
    else
    {
      v14 = v11 * v13;
      v15 = 0;
      if ( (unsigned __int64)(v14 + 0x80000000LL) > 0xFFFFFFFF )
      {
        LOBYTE(v16) = 0;
      }
      else
      {
        v15 = v14;
        LOBYTE(v16) = 1;
      }
      v17 = 0;
      if ( !(_BYTE)v16 )
        v15 = 0;
      if ( a1[3] <= v15 )
        v15 = a1[3];
      if ( v15 > v12 )
        v15 = *(_DWORD *)a2 - v8;
      if ( v15 > 0 )
      {
        do
        {
          v18 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v17 * *(_QWORD *)(a2 + 32))
                                       + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v17 * *(_QWORD *)(a2 + 32)))
                               + *(float *)(*(_QWORD *)(a2 + 24) + 4 * v17 * *(_QWORD *)(a2 + 32)))
                       * 341.0));
          if ( (unsigned __int16)v18 > 0x3ECu && v17 > 0 )
          {
            v19 = (v17 - 1LL) * *(_QWORD *)(a2 + 32);
            v18 = (int)fmaxf(
                         0.0,
                         fminf(
                           1023.0,
                           (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v19)
                                         + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v19))
                                 + *(float *)(*(_QWORD *)(a2 + 24) + 4 * v19))
                         * 341.0));
          }
          v16 = *((_QWORD *)a3 + 1);
          v20 = v5++;
          v17 += v11;
          *(_WORD *)(v16 + 2 * v20) = v18;
        }
        while ( v17 < v15 );
      }
    }
  }
  else
  {
    v57 = a1[9];
    v58 = a1[11];
    if ( v10 <= 0 )
      v58 = 1;
    if ( v57 < 0 || v57 >= v58 )
    {
      v57 %= v58;
      if ( v57 < 0 )
        v57 += v58;
    }
    v59 = *a3;
    v60 = v57;
    v61 = 0;
    if ( (unsigned __int64)(v59 * (int)a1[762] + 0x80000000LL) > 0xFFFFFFFF )
    {
      v62 = 0;
    }
    else
    {
      v61 = v59 * a1[762];
      v62 = 1;
    }
    if ( !v62 )
      v61 = 0;
    v63 = v61 / v10;
    LODWORD(v16) = (int)v59 / v10;
    if ( (int)v59 % v10 > 0 )
    {
      v16 = (unsigned int)((int)v59 % v10);
      do
      {
        v63 += a1[v57 + 388];
        v64 = v57 + 1;
        v57 = 0;
        if ( v64 < v58 )
          v57 = v64;
        --v16;
      }
      while ( v16 );
    }
    v65 = *(_DWORD *)a2 - v8;
    if ( v63 > a1[3] )
      v63 = a1[3];
    if ( v63 <= v65 )
      v65 = v63;
    v66 = 0;
    if ( v65 > 0 )
    {
      v67 = 0;
      do
      {
        v68 = (int)fmaxf(
                     0.0,
                     fminf(
                       1023.0,
                       (float)((float)(*(float *)(*(_QWORD *)(a2 + 8) + 4 * v66 * *(_QWORD *)(a2 + 32))
                                     + *(float *)(*(_QWORD *)(a2 + 16) + 4 * v66 * *(_QWORD *)(a2 + 32)))
                             + *(float *)(*(_QWORD *)(a2 + 24) + 4 * v66 * *(_QWORD *)(a2 + 32)))
                     * 341.0));
        if ( (unsigned __int16)v68 > 0x3ECu && v66 > 0 )
          v68 = (int)fmaxf(
                       0.0,
                       fminf(
                         1023.0,
                         (float)((float)(*(float *)(*(_QWORD *)(a2 + 16) + 4 * (v66 - 1LL) * *(_QWORD *)(a2 + 32))
                                       + *(float *)(*(_QWORD *)(a2 + 8) + 4 * (v66 - 1LL) * *(_QWORD *)(a2 + 32)))
                               + *(float *)(*(_QWORD *)(a2 + 24) + 4 * (v66 - 1LL) * *(_QWORD *)(a2 + 32)))
                       * 341.0));
        *(_WORD *)(v67 + *((_QWORD *)a3 + 1)) = v68;
        v69 = v60 + 1;
        v16 = v60;
        v67 += 2;
        v60 = 0;
        v66 += a1[v16 + 388];
        if ( v69 < v58 )
          v60 = v69;
      }
      while ( v66 < v65 );
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1800653c0  mov     [rsp-28h+arg_0], rbx
0x1800653c5  mov     [rsp-28h+arg_10], rsi
0x1800653ca  mov     [rsp-28h+arg_18], rdi
0x1800653cf  push    rbp
0x1800653d0  push    r12
0x1800653d2  push    r13
0x1800653d4  push    r14
0x1800653d6  push    r15
0x1800653d8  mov     rbp, rsp
0x1800653db  sub     rsp, 20h
0x1800653df  mov     r15d, [rcx+20h]
0x1800653e3  mov     rdi, rcx
0x1800653e6  xor     r10d, r10d
0x1800653e9  mov     rsi, r8
0x1800653ec  test    r15d, r15d
0x1800653ef  mov     r9, rdx
0x1800653f2  cmovg   r15d, r10d
0x1800653f6  neg     r15d
0x1800653f9  movsxd  rcx, r15d
0x1800653fc  mov     rax, rcx
0x1800653ff  imul    rax, [rdx+20h]
0x180065404  shl     rax, 2
0x180065408  add     [rdx+8], rax
0x18006540c  imul    rcx, [rdx+20h]
0x180065411  shl     rcx, 2
0x180065415  add     [rdx+10h], rcx
0x180065419  add     [rdx+18h], rcx
0x18006541d  mov     ecx, [rdi+2Ch]
0x180065420  cmp     ecx, 1
0x180065423  jnz     loc_180065BC4
0x180065429  mov     r12d, [rdx]
0x18006542c  movsxd  r14, dword ptr [rdi+610h]
0x180065433  sub     r12d, r15d
0x180065436  movsxd  rcx, dword ptr [r8]
0x180065439  cmp     r14d, 1
0x18006543d  jz      loc_18006555D
0x180065443  imul    rcx, r14
0x180065447  mov     eax, 80000000h
0x18006544c  mov     edx, 0FFFFFFFFh
0x180065451  add     rax, rcx
0x180065454  mov     ebx, r10d
0x180065457  cmp     rax, rdx
0x18006545a  ja      short loc_180065462
0x18006545c  mov     ebx, ecx
0x18006545e  mov     al, 1
0x180065460  jmp     short loc_180065464
0x180065462  xor     al, al
0x180065464  test    al, al
0x180065466  mov     r11d, r10d
0x180065469  cmovz   ebx, r10d
0x18006546d  cmp     [rdi+0Ch], ebx
0x180065470  cmovle  ebx, [rdi+0Ch]
0x180065474  cmp     ebx, r12d
0x180065477  cmovg   ebx, r12d
0x18006547b  test    ebx, ebx
0x18006547d  jle     loc_180065D6D
0x180065483  movss   xmm3, cs:__real@43aa8000
0x18006548b  mov     r13d, 3ECh
0x180065491  movss   xmm4, cs:__real@447fc000
0x180065499  nop     dword ptr [rax+00000000h]
0x1800654a0  movups  xmm1, xmmword ptr [r9+8]
0x1800654a5  mov     r8, [r9+20h]
0x1800654a9  mov     rax, [r9+18h]
0x1800654ad  movq    rdx, xmm1
0x1800654b2  movsxd  rdi, r11d
0x1800654b5  imul    r8, rdi
0x1800654b9  movups  [rbp+var_20], xmm1
0x1800654bd  movaps  xmm1, xmm4
0x1800654c0  mov     rcx, qword ptr [rbp+var_20+8]
0x1800654c4  movss   xmm0, dword ptr [rdx+r8*4]
0x1800654ca  addss   xmm0, dword ptr [rcx+r8*4]
0x1800654d0  addss   xmm0, dword ptr [rax+r8*4]
0x1800654d6  mulss   xmm0, xmm3
0x1800654da  minss   xmm1, xmm0
0x1800654de  xorps   xmm0, xmm0
0x1800654e1  maxss   xmm0, xmm1
0x1800654e5  cvttss2si edx, xmm0
0x1800654e9  cmp     dx, r13w
0x1800654ed  jbe     short loc_18006553E
0x1800654ef  test    r11d, r11d
0x1800654f2  jle     short loc_18006553E
0x1800654f4  movups  xmm1, xmmword ptr [r9+8]
0x1800654f9  mov     r8, [r9+20h]
0x1800654fd  lea     rax, [rdi-1]
0x180065501  imul    r8, rax
0x180065505  movq    rdx, xmm1
0x18006550a  movups  [rbp+var_20], xmm1
0x18006550e  movaps  xmm1, xmm4
0x180065511  mov     rax, [r9+18h]
0x180065515  mov     rcx, qword ptr [rbp+var_20+8]
0x180065519  movss   xmm0, dword ptr [rdx+r8*4]
0x18006551f  addss   xmm0, dword ptr [rcx+r8*4]
0x180065525  addss   xmm0, dword ptr [rax+r8*4]
0x18006552b  mulss   xmm0, xmm3
0x18006552f  minss   xmm1, xmm0
0x180065533  xorps   xmm0, xmm0
0x180065536  maxss   xmm0, xmm1
0x18006553a  cvttss2si edx, xmm0
0x18006553e  mov     rax, [rsi+8]
0x180065542  mov     rcx, r10
0x180065545  inc     r10
0x180065548  add     r11d, r14d
0x18006554b  mov     [rax+rcx*2], dx
0x18006554f  cmp     r11d, ebx
0x180065552  jl      loc_1800654A0
0x180065558  jmp     loc_180065D6D
0x18006555d  mov     eax, [rdi+0Ch]
0x180065560  mov     r13d, 3ECh
0x180065566  movss   xmm3, cs:__real@43aa8000
0x18006556e  cmp     eax, ecx
0x180065570  movss   xmm4, cs:__real@447fc000
0x180065578  cmovg   eax, ecx
0x18006557b  cmp     eax, r12d
0x18006557e  cmovle  r12d, eax
0x180065582  mov     eax, r12d
0x180065585  cdq
0x180065586  and     edx, 7
0x180065589  add     eax, edx
0x18006558b  mov     edx, 0FFFFFFFFh
0x180065590  sar     eax, 3
0x180065593  movsxd  rcx, eax
0x180065596  mov     eax, 80000000h
0x18006559b  shl     rcx, 3
0x18006559f  add     rax, rcx
0x1800655a2  cmp     rax, rdx
0x1800655a5  ja      loc_180065AF8
0x1800655ab  movsxd  r15, ecx
0x1800655ae  test    ecx, ecx
0x1800655b0  jle     loc_180065AF8
0x1800655b6  mov     ebx, 6
0x1800655bb  mov     rdi, r10
0x1800655be  lea     r11d, [rbx-4]
0x1800655c2  movups  xmm1, xmmword ptr [r9+8]
0x1800655c7  mov     rax, [r9+18h]
0x1800655cb  mov     r8, rdi
0x1800655ce  imul    r8, [r9+20h]
0x1800655d3  movq    rdx, xmm1
0x1800655d8  movups  [rbp+var_20], xmm1
0x1800655dc  movaps  xmm1, xmm4
0x1800655df  mov     rcx, qword ptr [rbp+var_20+8]
0x1800655e3  movss   xmm0, dword ptr [rdx+r8*4]
0x1800655e9  addss   xmm0, dword ptr [rcx+r8*4]
0x1800655ef  addss   xmm0, dword ptr [rax+r8*4]
0x1800655f5  mulss   xmm0, xmm3
0x1800655f9  minss   xmm1, xmm0
0x1800655fd  xorps   xmm0, xmm0
0x180065600  maxss   xmm0, xmm1
0x180065604  cvttss2si ecx, xmm0
0x180065608  cmp     cx, r13w
0x18006560c  jbe     short loc_180065656
0x18006560e  test    r10d, r10d
0x180065611  jle     short loc_180065656
0x180065613  movups  xmm1, xmmword ptr [r9+8]
0x180065618  lea     r8, [rdi-1]
0x18006561c  imul    r8, [r9+20h]
0x180065621  movq    rdx, xmm1
0x180065626  movups  [rbp+var_20], xmm1
0x18006562a  movaps  xmm1, xmm4
0x18006562d  mov     rcx, qword ptr [rbp+var_20+8]
0x180065631  movss   xmm0, dword ptr [rdx+r8*4]
0x180065637  addss   xmm0, dword ptr [rcx+r8*4]
0x18006563d  addss   xmm0, dword ptr [rax+r8*4]
0x180065643  mulss   xmm0, xmm3
0x180065647  minss   xmm1, xmm0
0x18006564b  xorps   xmm0, xmm0
0x18006564e  maxss   xmm0, xmm1
0x180065652  cvttss2si ecx, xmm0
0x180065656  mov     rax, [rsi+8]
0x18006565a  lea     edi, [r11-1]
0x18006565e  movsxd  r14, r11d
0x180065661  mov     [rbx+rax-6], cx
0x180065666  movups  xmm1, xmmword ptr [r9+8]
0x18006566b  mov     rcx, [r9+18h]
0x18006566f  lea     r8, [r14-1]
0x180065673  imul    r8, [r9+20h]
0x180065678  movups  [rbp+var_20], xmm1
0x18006567c  movq    rdx, xmm1
0x180065681  movaps  xmm1, xmm4
0x180065684  mov     rax, qword ptr [rbp+var_20+8]
0x180065688  movss   xmm0, dword ptr [rax+r8*4]
0x18006568e  addss   xmm0, dword ptr [rdx+r8*4]
0x180065694  addss   xmm0, dword ptr [rcx+r8*4]
0x18006569a  mulss   xmm0, xmm3
0x18006569e  minss   xmm1, xmm0
0x1800656a2  xorps   xmm0, xmm0
0x1800656a5  maxss   xmm0, xmm1
0x1800656a9  cvttss2si ecx, xmm0
0x1800656ad  cmp     cx, r13w
0x1800656b1  jbe     short loc_1800656FE
0x1800656b3  test    edi, edi
0x1800656b5  jle     short loc_1800656FE
0x1800656b7  movups  xmm1, xmmword ptr [r9+8]
0x1800656bc  mov     rax, [r9+18h]
0x1800656c0  lea     r8, [r14-2]
0x1800656c4  imul    r8, [r9+20h]
0x1800656c9  movq    rdx, xmm1
0x1800656ce  movups  [rbp+var_20], xmm1
0x1800656d2  movaps  xmm1, xmm4
0x1800656d5  mov     rcx, qword ptr [rbp+var_20+8]
0x1800656d9  movss   xmm0, dword ptr [rdx+r8*4]
0x1800656df  addss   xmm0, dword ptr [rcx+r8*4]
0x1800656e5  addss   xmm0, dword ptr [rax+r8*4]
0x1800656eb  mulss   xmm0, xmm3
0x1800656ef  minss   xmm1, xmm0
0x1800656f3  xorps   xmm0, xmm0
0x1800656f6  maxss   xmm0, xmm1
0x1800656fa  cvttss2si ecx, xmm0
0x1800656fe  mov     rax, [rsi+8]
0x180065702  movsxd  rdi, r11d
0x180065705  mov     r8, rdi
0x180065708  mov     [rax+rbx-4], cx
0x18006570d  imul    r8, [r9+20h]
0x180065712  movups  xmm1, xmmword ptr [r9+8]
0x180065717  movq    rdx, xmm1
0x18006571c  mov     rax, [r9+18h]
0x180065720  movups  [rbp+var_20], xmm1
0x180065724  mov     rcx, qword ptr [rbp+var_20+8]
0x180065728  movaps  xmm1, xmm4
0x18006572b  movss   xmm0, dword ptr [rdx+r8*4]
0x180065731  addss   xmm0, dword ptr [rcx+r8*4]
0x180065737  addss   xmm0, dword ptr [rax+r8*4]
0x18006573d  mulss   xmm0, xmm3
0x180065741  minss   xmm1, xmm0
0x180065745  xorps   xmm0, xmm0
0x180065748  maxss   xmm0, xmm1
0x18006574c  cvttss2si ecx, xmm0
0x180065750  cmp     cx, r13w
0x180065754  jbe     short loc_18006579E
0x180065756  test    r11d, r11d
0x180065759  jle     short loc_18006579E
0x18006575b  movups  xmm1, xmmword ptr [r9+8]
0x180065760  lea     r8, [rdi-1]
0x180065764  imul    r8, [r9+20h]
0x180065769  movq    rdx, xmm1
0x18006576e  movups  [rbp+var_20], xmm1
0x180065772  movaps  xmm1, xmm4
0x180065775  mov     rcx, qword ptr [rbp+var_20+8]
0x180065779  movss   xmm0, dword ptr [rdx+r8*4]
0x18006577f  addss   xmm0, dword ptr [rcx+r8*4]
0x180065785  addss   xmm0, dword ptr [rax+r8*4]
0x18006578b  mulss   xmm0, xmm3
0x18006578f  minss   xmm1, xmm0
0x180065793  xorps   xmm0, xmm0
0x180065796  maxss   xmm0, xmm1
0x18006579a  cvttss2si ecx, xmm0
0x18006579e  mov     rax, [rsi+8]
0x1800657a2  lea     edi, [r11+1]
0x1800657a6  movsxd  r14, r11d
0x1800657a9  mov     [rax+rbx-2], cx
0x1800657ae  movups  xmm1, xmmword ptr [r9+8]
0x1800657b3  mov     rax, [r9+18h]
0x1800657b7  lea     r8, [r14+1]
0x1800657bb  imul    r8, [r9+20h]
0x1800657c0  movq    rdx, xmm1
0x1800657c5  movups  [rbp+var_20], xmm1
0x1800657c9  movaps  xmm1, xmm4
0x1800657cc  mov     rcx, qword ptr [rbp+var_20+8]
0x1800657d0  movss   xmm0, dword ptr [rdx+r8*4]
0x1800657d6  addss   xmm0, dword ptr [rcx+r8*4]
0x1800657dc  addss   xmm0, dword ptr [rax+r8*4]
0x1800657e2  mulss   xmm0, xmm3
0x1800657e6  minss   xmm1, xmm0
0x1800657ea  xorps   xmm0, xmm0
0x1800657ed  maxss   xmm0, xmm1
0x1800657f1  cvttss2si ecx, xmm0
0x1800657f5  cmp     cx, r13w
0x1800657f9  jbe     short loc_180065841
0x1800657fb  test    edi, edi
0x1800657fd  jle     short loc_180065841
0x1800657ff  movups  xmm1, xmmword ptr [r9+8]
0x180065804  mov     r8, r14
0x180065807  imul    r8, [r9+20h]
0x18006580c  movq    rdx, xmm1
0x180065811  movups  [rbp+var_20], xmm1
0x180065815  movaps  xmm1, xmm4
0x180065818  mov     rcx, qword ptr [rbp+var_20+8]
0x18006581c  movss   xmm0, dword ptr [rdx+r8*4]
0x180065822  addss   xmm0, dword ptr [rcx+r8*4]
0x180065828  addss   xmm0, dword ptr [rax+r8*4]
0x18006582e  mulss   xmm0, xmm3
0x180065832  minss   xmm1, xmm0
0x180065836  xorps   xmm0, xmm0
0x180065839  maxss   xmm0, xmm1
0x18006583d  cvttss2si ecx, xmm0
0x180065841  mov     rax, [rsi+8]
0x180065845  lea     edi, [r11+2]
0x180065849  movsxd  r14, r11d
0x18006584c  mov     [rbx+rax], cx
0x180065850  movups  xmm1, xmmword ptr [r9+8]
0x180065855  mov     rax, [r9+18h]
0x180065859  lea     r8, [r14+2]
0x18006585d  imul    r8, [r9+20h]
0x180065862  movq    rdx, xmm1
0x180065867  movups  [rbp+var_20], xmm1
0x18006586b  movaps  xmm1, xmm4
0x18006586e  mov     rcx, qword ptr [rbp+var_20+8]
0x180065872  movss   xmm0, dword ptr [rdx+r8*4]
0x180065878  addss   xmm0, dword ptr [rcx+r8*4]
0x18006587e  addss   xmm0, dword ptr [rax+r8*4]
0x180065884  mulss   xmm0, xmm3
  ... truncated ...
```

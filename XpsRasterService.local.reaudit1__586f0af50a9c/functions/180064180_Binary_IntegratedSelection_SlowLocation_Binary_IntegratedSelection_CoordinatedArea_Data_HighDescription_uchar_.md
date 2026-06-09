# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<uchar *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ReduceComprehensiveSDK<Data::HighDescription<ushort *>>(Binary::Definition::GeneralQuality<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<uchar *>,3,0>> &,Binary::Definition::GeneralQuality<Data::HighDescription<ushort *>> &)

- ea: `0x180064180`
- end: `0x1800649c3`
- name: `??$ReduceComprehensiveSDK@V?$HighDescription@PEAG@Data@@@?$SlowLocation@V?$CoordinatedArea@V?$HighDescription@PEAE@Data@@$02$0A@@IntegratedSelection@Binary@@V?$MixedResponse@$02$0A@$07$0A@@23@@IntegratedSelection@Binary@@AEAAXAEAV?$GeneralQuality@V?$CoordinatedArea@V?$HighDescription@PEAE@Data@@$02$0A@@IntegratedSelection@Binary@@@Definition@2@AEAV?$GeneralQuality@V?$HighDescription@PEAG@Data@@@42@@Z`
- size: `2115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800577a0`

## callees

- `0x180064180`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned char *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ReduceComprehensiveSDK<Data::HighDescription<unsigned short *>>(
        _DWORD *a1,
        __int64 a2,
        int *a3)
{
  int v3; // r15d
  __int64 v4; // r10
  int v8; // r15d
  __int64 v9; // rcx
  int v10; // r12d
  __int64 v11; // r14
  int v12; // r12d
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // rax
  int v16; // r11d
  __int64 v17; // rcx
  unsigned int v18; // r8d
  __int64 v19; // r8
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r15
  __int64 v24; // rbx
  __int64 v25; // rsi
  int v26; // r11d
  __int128 v27; // xmm1
  unsigned int v28; // ecx
  __int128 v29; // xmm1
  __int64 v30; // r8
  unsigned int v31; // ecx
  __int64 v32; // r8
  unsigned int v33; // ecx
  __int64 v34; // r8
  __int64 v35; // rcx
  unsigned int v36; // edx
  __int128 v37; // xmm1
  __int64 v38; // r8
  unsigned int v39; // ecx
  __int64 v40; // rcx
  __int128 v41; // xmm1
  __int64 v42; // r8
  unsigned int v43; // ecx
  __int64 v44; // r8
  __int128 v45; // xmm1
  __int64 v46; // rdx
  unsigned int v47; // ecx
  __int64 v48; // r8
  __int64 v49; // rcx
  unsigned int v50; // edx
  __int64 v51; // r8
  __int64 v52; // r11
  unsigned int v53; // ecx
  __int64 v54; // rcx
  int v55; // r8d
  int v56; // r14d
  __int64 v57; // r13
  int v58; // ebx
  int v59; // r11d
  char v60; // al
  int v61; // r11d
  int v62; // ecx
  int v63; // r12d
  int v64; // r11d
  __int64 v65; // r15
  unsigned int v66; // edx
  __int64 v67; // r8
  int v68; // ecx

  v3 = a1[8];
  v4 = 0;
  if ( v3 > 0 )
    v3 = 0;
  v8 = -v3;
  *(_QWORD *)(a2 + 8) += *(_QWORD *)(a2 + 32) * v8;
  v9 = *(_QWORD *)(a2 + 32) * v8;
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
      LOBYTE(v15) = 8 * (v12 / 8);
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
            v27 = *(_OWORD *)(a2 + 8);
            v28 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + *(_QWORD *)(a2 + 32) * v25)
                  + *(unsigned __int8 *)(*((_QWORD *)&v27 + 1) + *(_QWORD *)(a2 + 32) * v25)
                  + (unsigned int)*(unsigned __int8 *)(v27 + *(_QWORD *)(a2 + 32) * v25))) >> 6;
            if ( (unsigned __int16)v28 > 0x3ECu && (int)v4 > 0 )
              v28 = (85
                   * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 32) * (v25 - 1) + *((_QWORD *)&v27 + 1))
                    + *(unsigned __int8 *)(*(_QWORD *)(a2 + 32) * (v25 - 1) + v27)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + *(_QWORD *)(a2 + 32) * (v25 - 1)))) >> 6;
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 6) = v28;
            v29 = *(_OWORD *)(a2 + 8);
            v30 = *(_QWORD *)(a2 + 32) * (v26 - 1LL);
            v31 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v30)
                  + *(unsigned __int8 *)(*((_QWORD *)&v29 + 1) + v30)
                  + (unsigned int)*(unsigned __int8 *)(v29 + v30))) >> 6;
            if ( (unsigned __int16)v31 > 0x3ECu && v26 - 1 > 0 )
            {
              v32 = *(_QWORD *)(a2 + 32) * (v26 - 2LL);
              v31 = (85
                   * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v32)
                    + *(unsigned __int8 *)(*((_QWORD *)&v29 + 1) + v32)
                    + (unsigned int)*(unsigned __int8 *)(v29 + v32))) >> 6;
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 4) = v31;
            v33 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 32) * v26 + *(_QWORD *)(a2 + 8))
                  + *(unsigned __int8 *)(*(_QWORD *)(a2 + 32) * v26 + *(_QWORD *)(a2 + 24))
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 32) * v26))) >> 6;
            if ( (unsigned __int16)v33 > 0x3ECu && v26 > 0 )
            {
              v34 = *(_QWORD *)(a2 + 32) * (v26 - 1LL);
              v33 = (85
                   * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v34)
                    + *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + v34)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v34))) >> 6;
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 2) = v33;
            v35 = *(_QWORD *)(a2 + 32) * (v26 + 1LL);
            v36 = (85
                 * (*(unsigned __int8 *)(v35 + *(_QWORD *)(a2 + 16))
                  + *(unsigned __int8 *)(v35 + *(_QWORD *)(a2 + 8))
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v35))) >> 6;
            if ( (unsigned __int16)v36 > 0x3ECu && v26 + 1 > 0 )
              v36 = (85
                   * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + *(_QWORD *)(a2 + 32) * v26)
                    + *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 32) * v26)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + *(_QWORD *)(a2 + 32) * v26))) >> 6;
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1)) = v36;
            v37 = *(_OWORD *)(a2 + 8);
            v38 = *(_QWORD *)(a2 + 32) * (v26 + 2LL);
            v39 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v38)
                  + *(unsigned __int8 *)(*((_QWORD *)&v37 + 1) + v38)
                  + (unsigned int)*(unsigned __int8 *)(v37 + v38))) >> 6;
            if ( (unsigned __int16)v39 > 0x3ECu && v26 + 2 > 0 )
            {
              v40 = *(_QWORD *)(a2 + 32) * (v26 + 1LL);
              v39 = (85
                   * (*(unsigned __int8 *)(v40 + *((_QWORD *)&v37 + 1))
                    + *(unsigned __int8 *)(v40 + v37)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v40))) >> 6;
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 2) = v39;
            v41 = *(_OWORD *)(a2 + 8);
            v42 = *(_QWORD *)(a2 + 32) * (v26 + 3LL);
            v43 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v42)
                  + *(unsigned __int8 *)(*((_QWORD *)&v41 + 1) + v42)
                  + (unsigned int)*(unsigned __int8 *)(v41 + v42))) >> 6;
            if ( (unsigned __int16)v43 > 0x3ECu && v26 + 3 > 0 )
            {
              v44 = *(_QWORD *)(a2 + 32) * (v26 + 2LL);
              v43 = (85
                   * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v44)
                    + *(unsigned __int8 *)(*((_QWORD *)&v41 + 1) + v44)
                    + (unsigned int)*(unsigned __int8 *)(v41 + v44))) >> 6;
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 4) = v43;
            v45 = *(_OWORD *)(a2 + 8);
            v46 = *(_QWORD *)(a2 + 32) * (v26 + 4LL);
            v47 = (85
                 * (*(unsigned __int8 *)(v46 + v45)
                  + *(unsigned __int8 *)(v46 + *(_QWORD *)(a2 + 24))
                  + (unsigned int)*(unsigned __int8 *)(*((_QWORD *)&v45 + 1) + v46))) >> 6;
            if ( (unsigned __int16)v47 > 0x3ECu && v26 + 4 > 0 )
            {
              v48 = *(_QWORD *)(a2 + 32) * (v26 + 3LL);
              v47 = (85
                   * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v48)
                    + *(unsigned __int8 *)(*((_QWORD *)&v45 + 1) + v48)
                    + (unsigned int)*(unsigned __int8 *)(v45 + v48))) >> 6;
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) + 6) = v47;
            v49 = *(_QWORD *)(a2 + 32) * (v26 + 5LL);
            v50 = (85
                 * (*(unsigned __int8 *)(v49 + *(_QWORD *)(a2 + 16))
                  + *(unsigned __int8 *)(v49 + *(_QWORD *)(a2 + 8))
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v49))) >> 6;
            if ( (unsigned __int16)v50 > 0x3ECu && v26 + 5 > 0 )
            {
              v51 = *(_QWORD *)(a2 + 32) * (v26 + 4LL);
              v50 = (85
                   * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v51)
                    + *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + v51)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v51))) >> 6;
            }
            v15 = *((_QWORD *)a3 + 1);
            LODWORD(v4) = v4 + 8;
            v26 += 8;
            v25 = (int)v4;
            *(_WORD *)(v24 + v15 + 8) = v50;
            v24 += 16;
          }
          while ( (int)v4 < v23 );
        }
      }
      v52 = (int)v4;
      if ( (int)v4 < (__int64)v12 )
      {
        do
        {
          v53 = (85
               * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + *(_QWORD *)(a2 + 32) * (int)v4)
                + *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 32) * (int)v4)
                + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + *(_QWORD *)(a2 + 32) * (int)v4))) >> 6;
          if ( (unsigned __int16)v53 > 0x3ECu && (int)v4 > 0 )
          {
            v54 = *(_QWORD *)(a2 + 32) * ((int)v4 - 1LL);
            v53 = (85
                 * (*(unsigned __int8 *)(v54 + *(_QWORD *)(a2 + 16))
                  + *(unsigned __int8 *)(v54 + *(_QWORD *)(a2 + 8))
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v54))) >> 6;
          }
          v15 = *((_QWORD *)a3 + 1);
          LODWORD(v4) = v4 + 1;
          *(_WORD *)(v15 + 2 * v52++) = v53;
        }
        while ( v52 < v12 );
      }
    }
    else
    {
      v14 = 0;
      if ( (unsigned __int64)(v11 * v13 + 0x80000000LL) > 0xFFFFFFFF )
      {
        LOBYTE(v15) = 0;
      }
      else
      {
        v14 = v11 * v13;
        LOBYTE(v15) = 1;
      }
      v16 = 0;
      if ( !(_BYTE)v15 )
        v14 = 0;
      if ( a1[3] <= v14 )
        v14 = a1[3];
      if ( v14 > v12 )
        v14 = *(_DWORD *)a2 - v8;
      if ( v14 > 0 )
      {
        do
        {
          v17 = *(_QWORD *)(a2 + 24);
          v18 = (85
               * (*(unsigned __int8 *)(v17 + *(_QWORD *)(a2 + 32) * v16)
                + *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 32) * v16)
                + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + *(_QWORD *)(a2 + 32) * v16))) >> 6;
          if ( (unsigned __int16)v18 > 0x3ECu && v16 > 0 )
          {
            v19 = *(_QWORD *)(a2 + 32) * (v16 - 1LL);
            v18 = (85
                 * (*(unsigned __int8 *)(v17 + v19)
                  + *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + v19)
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v19))) >> 6;
          }
          v15 = *((_QWORD *)a3 + 1);
          v20 = v4++;
          v16 += v11;
          *(_WORD *)(v15 + 2 * v20) = v18;
        }
        while ( v16 < v14 );
      }
    }
  }
  else
  {
    v55 = a1[9];
    v56 = a1[11];
    if ( v10 <= 0 )
      v56 = 1;
    if ( v55 < 0 || v55 >= v56 )
    {
      v55 %= v56;
      if ( v55 < 0 )
        v55 += v56;
    }
    v57 = *a3;
    v58 = v55;
    v59 = 0;
    if ( (unsigned __int64)(v57 * (int)a1[762] + 0x80000000LL) > 0xFFFFFFFF )
    {
      v60 = 0;
    }
    else
    {
      v59 = v57 * a1[762];
      v60 = 1;
    }
    if ( !v60 )
      v59 = 0;
    v61 = v59 / v10;
    LODWORD(v15) = (int)v57 / v10;
    if ( (int)v57 % v10 > 0 )
    {
      v15 = (unsigned int)((int)v57 % v10);
      do
      {
        v61 += a1[v55 + 388];
        v62 = v55 + 1;
        v55 = 0;
        if ( v62 < v56 )
          v55 = v62;
        --v15;
      }
      while ( v15 );
    }
    v63 = *(_DWORD *)a2 - v8;
    if ( v61 > a1[3] )
      v61 = a1[3];
    if ( v61 <= v63 )
      v63 = v61;
    v64 = 0;
    if ( v63 > 0 )
    {
      v65 = 0;
      do
      {
        v66 = (85
             * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 32) * v64 + *(_QWORD *)(a2 + 16))
              + *(unsigned __int8 *)(*(_QWORD *)(a2 + 32) * v64 + *(_QWORD *)(a2 + 8))
              + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + *(_QWORD *)(a2 + 32) * v64))) >> 6;
        if ( (unsigned __int16)v66 > 0x3ECu && v64 > 0 )
        {
          v67 = *(_QWORD *)(a2 + 32) * (v64 - 1LL);
          v66 = (85
               * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v67)
                + *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + v67)
                + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v67))) >> 6;
        }
        v68 = v58 + 1;
        *(_WORD *)(v65 + *((_QWORD *)a3 + 1)) = v66;
        v65 += 2;
        v15 = v58;
        v58 = 0;
        v64 += a1[v15 + 388];
        if ( v68 < v56 )
          v58 = v68;
      }
      while ( v64 < v63 );
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180064180  mov     [rsp-28h+arg_0], rbx
0x180064185  mov     [rsp-28h+arg_10], rsi
0x18006418a  mov     [rsp-28h+arg_18], rdi
0x18006418f  push    rbp
0x180064190  push    r12
0x180064192  push    r13
0x180064194  push    r14
0x180064196  push    r15
0x180064198  mov     rbp, rsp
0x18006419b  sub     rsp, 20h
0x18006419f  mov     r15d, [rcx+20h]
0x1800641a3  xor     r10d, r10d
0x1800641a6  test    r15d, r15d
0x1800641a9  mov     rsi, rcx
0x1800641ac  mov     rdi, r8
0x1800641af  mov     r9, rdx
0x1800641b2  cmovg   r15d, r10d
0x1800641b6  neg     r15d
0x1800641b9  movsxd  rcx, r15d
0x1800641bc  mov     rax, rcx
0x1800641bf  imul    rax, [rdx+20h]
0x1800641c4  add     [rdx+8], rax
0x1800641c8  imul    rcx, [rdx+20h]
0x1800641cd  add     [rdx+10h], rcx
0x1800641d1  add     [rdx+18h], rcx
0x1800641d5  mov     r12d, [rsi+2Ch]
0x1800641d9  cmp     r12d, 1
0x1800641dd  jnz     loc_180064837
0x1800641e3  mov     r12d, [rdx]
0x1800641e6  movsxd  r14, dword ptr [rsi+610h]
0x1800641ed  sub     r12d, r15d
0x1800641f0  movsxd  rcx, dword ptr [r8]
0x1800641f3  cmp     r14d, 1
0x1800641f7  jz      loc_1800642E8
0x1800641fd  mov     rdx, rcx
0x180064200  mov     eax, 80000000h
0x180064205  imul    rdx, r14
0x180064209  mov     ecx, 0FFFFFFFFh
0x18006420e  mov     ebx, r10d
0x180064211  add     rax, rdx
0x180064214  cmp     rax, rcx
0x180064217  ja      short loc_18006421F
0x180064219  mov     ebx, edx
0x18006421b  mov     al, 1
0x18006421d  jmp     short loc_180064221
0x18006421f  xor     al, al
0x180064221  test    al, al
0x180064223  mov     r11d, r10d
0x180064226  cmovz   ebx, r10d
0x18006422a  cmp     [rsi+0Ch], ebx
0x18006422d  cmovle  ebx, [rsi+0Ch]
0x180064231  cmp     ebx, r12d
0x180064234  cmovg   ebx, r12d
0x180064238  test    ebx, ebx
0x18006423a  jle     loc_1800649A6
0x180064240  mov     r13d, 3ECh
0x180064246  nop     word ptr [rax+rax+00000000h]
0x180064250  movups  xmm1, xmmword ptr [r9+8]
0x180064255  mov     rcx, [r9+18h]
0x180064259  movsxd  rsi, r11d
0x18006425c  mov     r8, rsi
0x18006425f  movq    rdx, xmm1
0x180064264  imul    r8, [r9+20h]
0x180064269  movups  [rbp+var_20], xmm1
0x18006426d  mov     rax, qword ptr [rbp+var_20+8]
0x180064271  movzx   edx, byte ptr [rdx+r8]
0x180064276  movzx   eax, byte ptr [rax+r8]
0x18006427b  add     edx, eax
0x18006427d  movzx   eax, byte ptr [rcx+r8]
0x180064282  add     edx, eax
0x180064284  imul    r8d, edx, 55h ; 'U'
0x180064288  shr     r8d, 6
0x18006428c  cmp     r8w, r13w
0x180064290  jbe     short loc_1800642C8
0x180064292  test    r11d, r11d
0x180064295  jle     short loc_1800642C8
0x180064297  lea     r8, [rsi-1]
0x18006429b  movq    rdx, xmm1
0x1800642a0  imul    r8, [r9+20h]
0x1800642a5  movups  [rbp+var_20], xmm1
0x1800642a9  mov     rax, qword ptr [rbp+var_20+8]
0x1800642ad  movzx   edx, byte ptr [rdx+r8]
0x1800642b2  movzx   eax, byte ptr [rax+r8]
0x1800642b7  add     edx, eax
0x1800642b9  movzx   eax, byte ptr [rcx+r8]
0x1800642be  add     edx, eax
0x1800642c0  imul    r8d, edx, 55h ; 'U'
0x1800642c4  shr     r8d, 6
0x1800642c8  mov     rax, [rdi+8]
0x1800642cc  mov     rcx, r10
0x1800642cf  inc     r10
0x1800642d2  add     r11d, r14d
0x1800642d5  mov     [rax+rcx*2], r8w
0x1800642da  cmp     r11d, ebx
0x1800642dd  jl      loc_180064250
0x1800642e3  jmp     loc_1800649A6
0x1800642e8  mov     eax, [rsi+0Ch]
0x1800642eb  mov     r13d, 3ECh
0x1800642f1  cmp     eax, ecx
0x1800642f3  cmovg   eax, ecx
0x1800642f6  mov     ecx, 0FFFFFFFFh
0x1800642fb  cmp     eax, r12d
0x1800642fe  cmovle  r12d, eax
0x180064302  mov     eax, r12d
0x180064305  cdq
0x180064306  and     edx, 7
0x180064309  add     eax, edx
0x18006430b  sar     eax, 3
0x18006430e  movsxd  rdx, eax
0x180064311  mov     eax, 80000000h
0x180064316  shl     rdx, 3
0x18006431a  add     rax, rdx
0x18006431d  cmp     rax, rcx
0x180064320  ja      loc_180064783
0x180064326  movsxd  r15, edx
0x180064329  test    edx, edx
0x18006432b  jle     loc_180064783
0x180064331  mov     ebx, 6
0x180064336  mov     rsi, r10
0x180064339  lea     r11d, [rbx-4]
0x18006433d  nop     dword ptr [rax]
0x180064340  movups  xmm1, xmmword ptr [r9+8]
0x180064345  mov     rcx, [r9+18h]
0x180064349  mov     r8, rsi
0x18006434c  imul    r8, [r9+20h]
0x180064351  movups  [rbp+var_20], xmm1
0x180064355  movq    rdx, xmm1
0x18006435a  mov     rax, qword ptr [rbp+var_20+8]
0x18006435e  movzx   edx, byte ptr [rdx+r8]
0x180064363  movzx   eax, byte ptr [rax+r8]
0x180064368  add     edx, eax
0x18006436a  movzx   eax, byte ptr [rcx+r8]
0x18006436f  add     edx, eax
0x180064371  imul    ecx, edx, 55h ; 'U'
0x180064374  shr     ecx, 6
0x180064377  cmp     cx, r13w
0x18006437b  jbe     short loc_1800643B7
0x18006437d  test    r10d, r10d
0x180064380  jle     short loc_1800643B7
0x180064382  mov     rax, [r9+18h]
0x180064386  lea     rcx, [rsi-1]
0x18006438a  imul    rcx, [r9+20h]
0x18006438f  movq    rdx, xmm1
0x180064394  movups  [rbp+var_20], xmm1
0x180064398  mov     r8, qword ptr [rbp+var_20+8]
0x18006439c  add     rdx, rcx
0x18006439f  add     r8, rcx
0x1800643a2  movzx   ecx, byte ptr [rax+rcx]
0x1800643a6  movzx   eax, byte ptr [rdx]
0x1800643a9  add     ecx, eax
0x1800643ab  movzx   eax, byte ptr [r8]
0x1800643af  add     ecx, eax
0x1800643b1  imul    ecx, 55h ; 'U'
0x1800643b4  shr     ecx, 6
0x1800643b7  mov     rax, [rdi+8]
0x1800643bb  lea     esi, [r11-1]
0x1800643bf  movsxd  r14, r11d
0x1800643c2  mov     [rbx+rax-6], cx
0x1800643c7  movups  xmm1, xmmword ptr [r9+8]
0x1800643cc  mov     rcx, [r9+18h]
0x1800643d0  lea     r8, [r14-1]
0x1800643d4  imul    r8, [r9+20h]
0x1800643d9  movups  [rbp+var_20], xmm1
0x1800643dd  movq    rdx, xmm1
0x1800643e2  mov     rax, qword ptr [rbp+var_20+8]
0x1800643e6  movzx   edx, byte ptr [rdx+r8]
0x1800643eb  movzx   eax, byte ptr [rax+r8]
0x1800643f0  add     edx, eax
0x1800643f2  movzx   eax, byte ptr [rcx+r8]
0x1800643f7  add     edx, eax
0x1800643f9  imul    ecx, edx, 55h ; 'U'
0x1800643fc  shr     ecx, 6
0x1800643ff  cmp     cx, r13w
0x180064403  jbe     short loc_18006443C
0x180064405  test    esi, esi
0x180064407  jle     short loc_18006443C
0x180064409  mov     rcx, [r9+18h]
0x18006440d  lea     r8, [r14-2]
0x180064411  imul    r8, [r9+20h]
0x180064416  movups  [rbp+var_20], xmm1
0x18006441a  movq    rdx, xmm1
0x18006441f  mov     rax, qword ptr [rbp+var_20+8]
0x180064423  movzx   edx, byte ptr [rdx+r8]
0x180064428  movzx   eax, byte ptr [rax+r8]
0x18006442d  add     edx, eax
0x18006442f  movzx   eax, byte ptr [rcx+r8]
0x180064434  add     edx, eax
0x180064436  imul    ecx, edx, 55h ; 'U'
0x180064439  shr     ecx, 6
0x18006443c  mov     rax, [rdi+8]
0x180064440  movsxd  rsi, r11d
0x180064443  mov     rdx, rsi
0x180064446  mov     [rbx+rax-4], cx
0x18006444b  imul    rdx, [r9+20h]
0x180064450  movups  xmm1, xmmword ptr [r9+8]
0x180064455  movq    r8, xmm1
0x18006445a  mov     rax, [r9+18h]
0x18006445e  add     rax, rdx
0x180064461  add     r8, rdx
0x180064464  movups  [rbp+var_20], xmm1
0x180064468  mov     rcx, qword ptr [rbp+var_20+8]
0x18006446c  movzx   eax, byte ptr [rax]
0x18006446f  movzx   edx, byte ptr [rcx+rdx]
0x180064473  add     edx, eax
0x180064475  movzx   eax, byte ptr [r8]
0x180064479  add     edx, eax
0x18006447b  imul    ecx, edx, 55h ; 'U'
0x18006447e  shr     ecx, 6
0x180064481  cmp     cx, r13w
0x180064485  jbe     short loc_1800644BF
0x180064487  test    r11d, r11d
0x18006448a  jle     short loc_1800644BF
0x18006448c  mov     rcx, [r9+18h]
0x180064490  lea     r8, [rsi-1]
0x180064494  imul    r8, [r9+20h]
0x180064499  movups  [rbp+var_20], xmm1
0x18006449d  movq    rdx, xmm1
0x1800644a2  mov     rax, qword ptr [rbp+var_20+8]
0x1800644a6  movzx   edx, byte ptr [rdx+r8]
0x1800644ab  movzx   eax, byte ptr [rax+r8]
0x1800644b0  add     edx, eax
0x1800644b2  movzx   eax, byte ptr [rcx+r8]
0x1800644b7  add     edx, eax
0x1800644b9  imul    ecx, edx, 55h ; 'U'
0x1800644bc  shr     ecx, 6
0x1800644bf  mov     rax, [rdi+8]
0x1800644c3  lea     esi, [r11+1]
0x1800644c7  movsxd  r14, r11d
0x1800644ca  mov     [rbx+rax-2], cx
0x1800644cf  movups  xmm1, xmmword ptr [r9+8]
0x1800644d4  mov     rax, [r9+18h]
0x1800644d8  lea     rcx, [r14+1]
0x1800644dc  imul    rcx, [r9+20h]
0x1800644e1  movq    rdx, xmm1
0x1800644e6  movups  [rbp+var_20], xmm1
0x1800644ea  mov     r8, qword ptr [rbp+var_20+8]
0x1800644ee  add     rdx, rcx
0x1800644f1  add     r8, rcx
0x1800644f4  movzx   ecx, byte ptr [rax+rcx]
0x1800644f8  movzx   eax, byte ptr [rdx]
0x1800644fb  add     ecx, eax
0x1800644fd  movzx   eax, byte ptr [r8]
0x180064501  add     ecx, eax
0x180064503  imul    edx, ecx, 55h ; 'U'
0x180064506  shr     edx, 6
0x180064509  cmp     dx, r13w
0x18006450d  jbe     short loc_180064545
0x18006450f  test    esi, esi
0x180064511  jle     short loc_180064545
0x180064513  mov     rcx, [r9+18h]
0x180064517  mov     r8, r14
0x18006451a  imul    r8, [r9+20h]
0x18006451f  movups  [rbp+var_20], xmm1
0x180064523  movq    rdx, xmm1
0x180064528  mov     rax, qword ptr [rbp+var_20+8]
0x18006452c  movzx   edx, byte ptr [rdx+r8]
0x180064531  movzx   eax, byte ptr [rax+r8]
0x180064536  add     edx, eax
0x180064538  movzx   eax, byte ptr [rcx+r8]
0x18006453d  add     edx, eax
0x18006453f  imul    edx, 55h ; 'U'
0x180064542  shr     edx, 6
0x180064545  mov     rax, [rdi+8]
0x180064549  lea     r14d, [r11+2]
0x18006454d  movsxd  rsi, r11d
0x180064550  mov     [rbx+rax], dx
0x180064554  movups  xmm1, xmmword ptr [r9+8]
0x180064559  mov     rcx, [r9+18h]
0x18006455d  lea     r8, [rsi+2]
0x180064561  imul    r8, [r9+20h]
0x180064566  movups  [rbp+var_20], xmm1
0x18006456a  movq    rdx, xmm1
0x18006456f  mov     rax, qword ptr [rbp+var_20+8]
0x180064573  movzx   edx, byte ptr [rdx+r8]
0x180064578  movzx   eax, byte ptr [rax+r8]
0x18006457d  add     edx, eax
0x18006457f  movzx   eax, byte ptr [rcx+r8]
0x180064584  add     edx, eax
0x180064586  imul    ecx, edx, 55h ; 'U'
0x180064589  shr     ecx, 6
0x18006458c  cmp     cx, r13w
0x180064590  jbe     short loc_1800645CC
0x180064592  test    r14d, r14d
0x180064595  jle     short loc_1800645CC
0x180064597  mov     rax, [r9+18h]
0x18006459b  lea     rcx, [rsi+1]
0x18006459f  imul    rcx, [r9+20h]
0x1800645a4  movq    rdx, xmm1
0x1800645a9  movups  [rbp+var_20], xmm1
0x1800645ad  mov     r8, qword ptr [rbp+var_20+8]
0x1800645b1  add     rdx, rcx
0x1800645b4  add     r8, rcx
0x1800645b7  movzx   ecx, byte ptr [rax+rcx]
0x1800645bb  movzx   eax, byte ptr [rdx]
0x1800645be  add     ecx, eax
0x1800645c0  movzx   eax, byte ptr [r8]
0x1800645c4  add     ecx, eax
0x1800645c6  imul    ecx, 55h ; 'U'
0x1800645c9  shr     ecx, 6
0x1800645cc  mov     rax, [rdi+8]
  ... truncated ...
```

# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<uchar *>,3,1>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ReduceComprehensiveSDK<Data::HighDescription<ushort *>>(Binary::Definition::GeneralQuality<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<uchar *>,3,1>> &,Binary::Definition::GeneralQuality<Data::HighDescription<ushort *>> &)

- ea: `0x1800639c0`
- end: `0x180064178`
- name: `??$ReduceComprehensiveSDK@V?$HighDescription@PEAG@Data@@@?$SlowLocation@V?$CoordinatedArea@V?$HighDescription@PEAE@Data@@$02$00@IntegratedSelection@Binary@@V?$MixedResponse@$02$0A@$07$0A@@23@@IntegratedSelection@Binary@@AEAAXAEAV?$GeneralQuality@V?$CoordinatedArea@V?$HighDescription@PEAE@Data@@$02$00@IntegratedSelection@Binary@@@Definition@2@AEAV?$GeneralQuality@V?$HighDescription@PEAG@Data@@@42@@Z`
- size: `1976`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800572c0`

## callees

- `0x1800639c0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned char *>,3,1>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ReduceComprehensiveSDK<Data::HighDescription<unsigned short *>>(
        _DWORD *a1,
        __int64 a2,
        int *a3)
{
  int v3; // ebx
  __int64 v4; // r11
  int v8; // ebx
  int v9; // ecx
  __int64 v10; // r15
  int v11; // r12d
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rax
  int v16; // ebx
  __int128 v17; // xmm0
  __int64 v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r15
  int v24; // ebx
  __int64 v25; // r10
  __int64 v26; // rdi
  __int128 v27; // xmm0
  unsigned int v28; // ecx
  __int64 v29; // r10
  __int128 v30; // xmm0
  unsigned int v31; // ecx
  __int128 v32; // xmm0
  unsigned int v33; // ecx
  unsigned int v34; // edx
  __int128 v35; // xmm0
  unsigned int v36; // ecx
  __int64 v37; // r10
  __int128 v38; // xmm0
  unsigned int v39; // ecx
  __int64 v40; // r10
  __int128 v41; // xmm0
  unsigned int v42; // ecx
  __int64 v43; // r10
  unsigned int v44; // edx
  __int64 v45; // r10
  __int128 v46; // xmm0
  unsigned int v47; // ecx
  int v48; // r8d
  int v49; // r15d
  __int64 v50; // r13
  int v51; // edi
  int v52; // r12d
  char v53; // al
  int v54; // r10d
  __int64 v55; // rdx
  int v56; // ecx
  int v57; // ecx
  int v58; // ebx
  __int64 v59; // r12
  unsigned int v60; // edx
  int v61; // ecx
  int v63; // [rsp+20h] [rbp-10h]

  v3 = a1[8];
  v4 = 0;
  if ( v3 > 0 )
    v3 = 0;
  v8 = -v3;
  *(_QWORD *)(a2 + 8) += v8;
  *(_QWORD *)(a2 + 16) += v8;
  *(_QWORD *)(a2 + 24) += v8;
  v9 = a1[11];
  if ( v9 == 1 )
  {
    v10 = (int)a1[388];
    v11 = *(_DWORD *)a2 - v8;
    v12 = *a3;
    if ( (_DWORD)v10 == 1 )
    {
      v21 = a1[3];
      if ( v21 > (int)v12 )
        v21 = *a3;
      if ( v21 <= v11 )
        v11 = v21;
      v22 = 8LL * (v11 / 8);
      LOBYTE(v15) = 8 * (v11 / 8);
      if ( (unsigned __int64)(v22 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        v23 = (int)v22;
        if ( (int)v22 > 0 )
        {
          v24 = 2;
          v25 = 0;
          v26 = 6;
          do
          {
            v27 = *(_OWORD *)(a2 + 8);
            v28 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v25)
                  + *(unsigned __int8 *)(*((_QWORD *)&v27 + 1) + v25)
                  + (unsigned int)*(unsigned __int8 *)(v27 + v25))) >> 6;
            if ( (unsigned __int16)v28 > 0x3ECu && (int)v4 > 0 )
              v28 = (85
                   * (*(unsigned __int8 *)(*((_QWORD *)&v27 + 1) + v25 - 1)
                    + *(unsigned __int8 *)(v27 + v25 - 1)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v25 - 1))) >> 6;
            v29 = v24 - 1LL;
            *(_WORD *)(v26 + *((_QWORD *)a3 + 1) - 6) = v28;
            v30 = *(_OWORD *)(a2 + 8);
            v31 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v29)
                  + *(unsigned __int8 *)(*((_QWORD *)&v30 + 1) + v29)
                  + (unsigned int)*(unsigned __int8 *)(v30 + v29))) >> 6;
            if ( (unsigned __int16)v31 > 0x3ECu && v24 - 1 > 0 )
              v31 = (85
                   * (*(unsigned __int8 *)(v29 + *(_QWORD *)(a2 + 24) - 1)
                    + *(unsigned __int8 *)(v29 + *((_QWORD *)&v30 + 1) - 1)
                    + (unsigned int)*(unsigned __int8 *)(v30 + v29 - 1))) >> 6;
            *(_WORD *)(*((_QWORD *)a3 + 1) + v26 - 4) = v31;
            v32 = *(_OWORD *)(a2 + 8);
            v33 = (85
                 * (*(unsigned __int8 *)(v32 + v24)
                  + *(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v24)
                  + (unsigned int)*(unsigned __int8 *)(*((_QWORD *)&v32 + 1) + v24))) >> 6;
            if ( (unsigned __int16)v33 > 0x3ECu && v24 > 0 )
              v33 = (85
                   * (*(unsigned __int8 *)(v24 + *(_QWORD *)(a2 + 24) - 1LL)
                    + *(unsigned __int8 *)(v24 + *((_QWORD *)&v32 + 1) - 1LL)
                    + (unsigned int)*(unsigned __int8 *)(v32 + v24 - 1))) >> 6;
            *(_WORD *)(v26 + *((_QWORD *)a3 + 1) - 2) = v33;
            v34 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + v24 + 1LL)
                  + *(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v24 + 1LL)
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v24 + 1LL))) >> 6;
            if ( (unsigned __int16)v34 > 0x3ECu && v24 + 1 > 0 )
              v34 = (85
                   * (*(unsigned __int8 *)(v24 + *(_QWORD *)(a2 + 24))
                    + *(unsigned __int8 *)(v24 + *(_QWORD *)(a2 + 16))
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v24))) >> 6;
            *(_WORD *)(v26 + *((_QWORD *)a3 + 1)) = v34;
            v35 = *(_OWORD *)(a2 + 8);
            v36 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v24 + 2LL)
                  + *(unsigned __int8 *)(*((_QWORD *)&v35 + 1) + v24 + 2LL)
                  + (unsigned int)*(unsigned __int8 *)(v35 + v24 + 2))) >> 6;
            if ( (unsigned __int16)v36 > 0x3ECu && v24 + 2 > 0 )
              v36 = (85
                   * (*(unsigned __int8 *)(*((_QWORD *)&v35 + 1) + v24 + 1LL)
                    + *(unsigned __int8 *)(v35 + v24 + 1)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v24 + 1LL))) >> 6;
            v37 = v24 + 3LL;
            *(_WORD *)(v26 + *((_QWORD *)a3 + 1) + 2) = v36;
            v38 = *(_OWORD *)(a2 + 8);
            v39 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v37)
                  + *(unsigned __int8 *)(*((_QWORD *)&v38 + 1) + v37)
                  + (unsigned int)*(unsigned __int8 *)(v38 + v37))) >> 6;
            if ( (unsigned __int16)v39 > 0x3ECu && v24 + 3 > 0 )
              v39 = (85
                   * (*(unsigned __int8 *)(v37 + *(_QWORD *)(a2 + 24) - 1)
                    + *(unsigned __int8 *)(v37 + *((_QWORD *)&v38 + 1) - 1)
                    + (unsigned int)*(unsigned __int8 *)(v38 + v37 - 1))) >> 6;
            v40 = v24 + 4LL;
            *(_WORD *)(v26 + *((_QWORD *)a3 + 1) + 4) = v39;
            v41 = *(_OWORD *)(a2 + 8);
            v42 = (85
                 * (*(unsigned __int8 *)(v41 + v40)
                  + *(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v40)
                  + (unsigned int)*(unsigned __int8 *)(*((_QWORD *)&v41 + 1) + v40))) >> 6;
            if ( (unsigned __int16)v42 > 0x3ECu && v24 + 4 > 0 )
              v42 = (85
                   * (*(unsigned __int8 *)(v40 + *(_QWORD *)(a2 + 24) - 1)
                    + *(unsigned __int8 *)(v40 + *((_QWORD *)&v41 + 1) - 1)
                    + (unsigned int)*(unsigned __int8 *)(v41 + v40 - 1))) >> 6;
            v43 = v24 + 5LL;
            *(_WORD *)(v26 + *((_QWORD *)a3 + 1) + 6) = v42;
            v44 = (85
                 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + v43)
                  + *(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v43)
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v43))) >> 6;
            if ( (unsigned __int16)v44 > 0x3ECu && v24 + 5 > 0 )
              v44 = (85
                   * (*(unsigned __int8 *)(v43 + *(_QWORD *)(a2 + 24) - 1)
                    + *(unsigned __int8 *)(v43 + *(_QWORD *)(a2 + 16) - 1)
                    + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v43 - 1))) >> 6;
            v15 = *((_QWORD *)a3 + 1);
            LODWORD(v4) = v4 + 8;
            v24 += 8;
            v25 = (int)v4;
            *(_WORD *)(v26 + v15 + 8) = v44;
            v26 += 16;
          }
          while ( (int)v4 < v23 );
        }
      }
      v45 = (int)v4;
      if ( (int)v4 < (__int64)v11 )
      {
        do
        {
          v46 = *(_OWORD *)(a2 + 8);
          v47 = (85
               * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + (int)v4)
                + *(unsigned __int8 *)(*((_QWORD *)&v46 + 1) + (int)v4)
                + (unsigned int)*(unsigned __int8 *)(v46 + (int)v4))) >> 6;
          if ( (unsigned __int16)v47 > 0x3ECu && (int)v4 > 0 )
            v47 = (85
                 * (*(unsigned __int8 *)(*((_QWORD *)&v46 + 1) + (int)v4 - 1LL)
                  + *(unsigned __int8 *)(v46 + (int)v4 - 1)
                  + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + (int)v4 - 1LL))) >> 6;
          v15 = *((_QWORD *)a3 + 1);
          LODWORD(v4) = v4 + 1;
          *(_WORD *)(v15 + 2 * v45++) = v47;
        }
        while ( v45 < v11 );
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
          v17 = *(_OWORD *)(a2 + 8);
          v18 = *(_QWORD *)(a2 + 24);
          v19 = (85
               * (*(unsigned __int8 *)(v18 + v16)
                + *(unsigned __int8 *)(*((_QWORD *)&v17 + 1) + v16)
                + (unsigned int)*(unsigned __int8 *)(v17 + v16))) >> 6;
          if ( (unsigned __int16)v19 > 0x3ECu && v16 > 0 )
            v19 = (85
                 * (*(unsigned __int8 *)(v16 + v18 - 1)
                  + *(unsigned __int8 *)(v16 + *((_QWORD *)&v17 + 1) - 1LL)
                  + (unsigned int)*(unsigned __int8 *)(v17 + v16 - 1))) >> 6;
          v15 = *((_QWORD *)a3 + 1);
          v20 = v4++;
          v16 += v10;
          *(_WORD *)(v15 + 2 * v20) = v19;
        }
        while ( v16 < v14 );
      }
    }
  }
  else
  {
    v48 = a1[9];
    v49 = v9;
    if ( v9 <= 0 )
      v49 = 1;
    if ( v48 < 0 || v48 >= v49 )
    {
      v48 %= v49;
      if ( v48 < 0 )
        v48 += v49;
    }
    v50 = *a3;
    v51 = v48;
    v52 = 0;
    if ( (unsigned __int64)(v50 * (int)a1[762] + 0x80000000LL) > 0xFFFFFFFF )
    {
      v53 = 0;
    }
    else
    {
      v52 = v50 * a1[762];
      v53 = 1;
    }
    if ( !v53 )
      v52 = 0;
    v54 = v52 / v9;
    v55 = (unsigned int)((int)v50 >> 31);
    LODWORD(v55) = (int)v50 % v9;
    LODWORD(v15) = (int)v50 / v9;
    if ( (int)v50 % v9 > 0 )
    {
      do
      {
        v54 += a1[v48 + 388];
        v56 = v48 + 1;
        v48 = 0;
        if ( v56 < v49 )
          v48 = v56;
        --v55;
      }
      while ( v55 );
    }
    v57 = *(_DWORD *)a2 - v8;
    v58 = 0;
    if ( v54 > a1[3] )
      v54 = a1[3];
    if ( v54 <= v57 )
      v57 = v54;
    v63 = v57;
    if ( v57 > 0 )
    {
      v59 = 0;
      do
      {
        v60 = (85
             * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + v58)
              + *(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v58)
              + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 24) + v58))) >> 6;
        if ( (unsigned __int16)v60 > 0x3ECu && v58 > 0 )
          v60 = (85
               * (*(unsigned __int8 *)(v58 + *(_QWORD *)(a2 + 24) - 1LL)
                + *(unsigned __int8 *)(v58 + *(_QWORD *)(a2 + 16) - 1LL)
                + (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(a2 + 8) + v58 - 1LL))) >> 6;
        v61 = v51 + 1;
        *(_WORD *)(v59 + *((_QWORD *)a3 + 1)) = v60;
        v59 += 2;
        v15 = v51;
        v51 = 0;
        v58 += a1[v15 + 388];
        if ( v61 < v49 )
          v51 = v61;
      }
      while ( v58 < v63 );
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800639c0  mov     [rsp-28h+arg_0], rbx
0x1800639c5  mov     [rsp-28h+arg_10], rsi
0x1800639ca  mov     [rsp-28h+arg_18], rdi
0x1800639cf  push    rbp
0x1800639d0  push    r12
0x1800639d2  push    r13
0x1800639d4  push    r14
0x1800639d6  push    r15
0x1800639d8  mov     rbp, rsp
0x1800639db  sub     rsp, 30h
0x1800639df  mov     ebx, [rcx+20h]
0x1800639e2  xor     r11d, r11d
0x1800639e5  test    ebx, ebx
0x1800639e7  mov     r14, rcx
0x1800639ea  mov     rsi, r8
0x1800639ed  mov     r9, rdx
0x1800639f0  cmovg   ebx, r11d
0x1800639f4  neg     ebx
0x1800639f6  movsxd  rax, ebx
0x1800639f9  add     [rdx+8], rax
0x1800639fd  add     [rdx+10h], rax
0x180063a01  add     [rdx+18h], rax
0x180063a05  mov     ecx, [rcx+2Ch]
0x180063a08  cmp     ecx, 1
0x180063a0b  jnz     loc_180063FEE
0x180063a11  mov     r12d, [rdx]
0x180063a14  movsxd  r15, dword ptr [r14+610h]
0x180063a1b  sub     r12d, ebx
0x180063a1e  movsxd  rcx, dword ptr [r8]
0x180063a21  cmp     r15d, 1
0x180063a25  jz      loc_180063B0C
0x180063a2b  imul    rcx, r15
0x180063a2f  mov     eax, 80000000h
0x180063a34  mov     edx, 0FFFFFFFFh
0x180063a39  add     rax, rcx
0x180063a3c  mov     edi, r11d
0x180063a3f  cmp     rax, rdx
0x180063a42  ja      short loc_180063A4A
0x180063a44  mov     edi, ecx
0x180063a46  mov     al, 1
0x180063a48  jmp     short loc_180063A4C
0x180063a4a  xor     al, al
0x180063a4c  test    al, al
0x180063a4e  mov     ebx, r11d
0x180063a51  cmovz   edi, r11d
0x180063a55  cmp     [r14+0Ch], edi
0x180063a59  cmovle  edi, [r14+0Ch]
0x180063a5e  cmp     edi, r12d
0x180063a61  cmovg   edi, r12d
0x180063a65  test    edi, edi
0x180063a67  jle     loc_18006415B
0x180063a6d  mov     r13d, 3ECh
0x180063a73  nop     dword ptr [rax+00h]
0x180063a77  nop     word ptr [rax+rax+00000000h]
0x180063a80  movups  xmm0, xmmword ptr [r9+8]
0x180063a85  mov     rcx, [r9+18h]
0x180063a89  movsxd  r10, ebx
0x180063a8c  movups  [rbp+var_30], xmm0
0x180063a90  mov     rax, qword ptr [rbp+var_30+8]
0x180063a94  movq    rdx, xmm0
0x180063a99  movzx   eax, byte ptr [rax+r10]
0x180063a9e  movzx   edx, byte ptr [rdx+r10]
0x180063aa3  add     edx, eax
0x180063aa5  movzx   eax, byte ptr [rcx+r10]
0x180063aaa  add     edx, eax
0x180063aac  imul    r8d, edx, 55h ; 'U'
0x180063ab0  shr     r8d, 6
0x180063ab4  cmp     r8w, r13w
0x180063ab8  jbe     short loc_180063AED
0x180063aba  test    ebx, ebx
0x180063abc  jle     short loc_180063AED
0x180063abe  add     rcx, r10
0x180063ac1  movq    r8, xmm0
0x180063ac6  movups  [rbp+var_30], xmm0
0x180063aca  mov     rdx, qword ptr [rbp+var_30+8]
0x180063ace  add     rdx, r10
0x180063ad1  movzx   r10d, byte ptr [r8+r10-1]
0x180063ad7  movzx   eax, byte ptr [rdx-1]
0x180063adb  add     r10d, eax
0x180063ade  movzx   eax, byte ptr [rcx-1]
0x180063ae2  add     r10d, eax
0x180063ae5  imul    r8d, r10d, 55h ; 'U'
0x180063ae9  shr     r8d, 6
0x180063aed  mov     rax, [rsi+8]
0x180063af1  mov     rcx, r11
0x180063af4  inc     r11
0x180063af7  add     ebx, r15d
0x180063afa  mov     [rax+rcx*2], r8w
0x180063aff  cmp     ebx, edi
0x180063b01  jl      loc_180063A80
0x180063b07  jmp     loc_18006415B
0x180063b0c  mov     eax, [r14+0Ch]
0x180063b10  mov     r13d, 3ECh
0x180063b16  cmp     eax, ecx
0x180063b18  cmovg   eax, ecx
0x180063b1b  cmp     eax, r12d
0x180063b1e  cmovle  r12d, eax
0x180063b22  mov     eax, r12d
0x180063b25  cdq
0x180063b26  and     edx, 7
0x180063b29  add     eax, edx
0x180063b2b  mov     edx, 0FFFFFFFFh
0x180063b30  sar     eax, 3
0x180063b33  movsxd  rcx, eax
0x180063b36  mov     eax, 80000000h
0x180063b3b  shl     rcx, 3
0x180063b3f  add     rax, rcx
0x180063b42  cmp     rax, rdx
0x180063b45  ja      loc_180063F56
0x180063b4b  movsxd  r15, ecx
0x180063b4e  test    ecx, ecx
0x180063b50  jle     loc_180063F56
0x180063b56  mov     ebx, 2
0x180063b5b  mov     r10, r11
0x180063b5e  lea     edi, [rbx+4]
0x180063b61  movups  xmm0, xmmword ptr [r9+8]
0x180063b66  mov     rcx, [r9+18h]
0x180063b6a  movups  [rbp+var_30], xmm0
0x180063b6e  mov     rax, qword ptr [rbp+var_30+8]
0x180063b72  movq    rdx, xmm0
0x180063b77  movzx   eax, byte ptr [rax+r10]
0x180063b7c  movzx   edx, byte ptr [rdx+r10]
0x180063b81  add     edx, eax
0x180063b83  movzx   eax, byte ptr [rcx+r10]
0x180063b88  add     edx, eax
0x180063b8a  imul    ecx, edx, 55h ; 'U'
0x180063b8d  shr     ecx, 6
0x180063b90  cmp     cx, r13w
0x180063b94  jbe     short loc_180063BC8
0x180063b96  test    r11d, r11d
0x180063b99  jle     short loc_180063BC8
0x180063b9b  mov     rax, [r9+18h]
0x180063b9f  movq    rdx, xmm0
0x180063ba4  movups  [rbp+var_30], xmm0
0x180063ba8  mov     r8, qword ptr [rbp+var_30+8]
0x180063bac  movzx   ecx, byte ptr [rax+r10-1]
0x180063bb2  movzx   eax, byte ptr [rdx+r10-1]
0x180063bb8  add     ecx, eax
0x180063bba  movzx   eax, byte ptr [r8+r10-1]
0x180063bc0  add     ecx, eax
0x180063bc2  imul    ecx, 55h ; 'U'
0x180063bc5  shr     ecx, 6
0x180063bc8  mov     rax, [rsi+8]
0x180063bcc  lea     r8d, [rbx-1]
0x180063bd0  movsxd  r10, ebx
0x180063bd3  dec     r10
0x180063bd6  mov     [rdi+rax-6], cx
0x180063bdb  movups  xmm0, xmmword ptr [r9+8]
0x180063be0  mov     rcx, [r9+18h]
0x180063be4  movups  [rbp+var_30], xmm0
0x180063be8  mov     rax, qword ptr [rbp+var_30+8]
0x180063bec  movq    rdx, xmm0
0x180063bf1  movzx   eax, byte ptr [rax+r10]
0x180063bf6  movzx   edx, byte ptr [rdx+r10]
0x180063bfb  add     edx, eax
0x180063bfd  movzx   eax, byte ptr [rcx+r10]
0x180063c02  add     edx, eax
0x180063c04  imul    ecx, edx, 55h ; 'U'
0x180063c07  shr     ecx, 6
0x180063c0a  cmp     cx, r13w
0x180063c0e  jbe     short loc_180063C47
0x180063c10  test    r8d, r8d
0x180063c13  jle     short loc_180063C47
0x180063c15  mov     rcx, [r9+18h]
0x180063c19  movq    r8, xmm0
0x180063c1e  add     rcx, r10
0x180063c21  movups  [rbp+var_30], xmm0
0x180063c25  mov     rdx, qword ptr [rbp+var_30+8]
0x180063c29  add     rdx, r10
0x180063c2c  movzx   r10d, byte ptr [r8+r10-1]
0x180063c32  movzx   eax, byte ptr [rdx-1]
0x180063c36  add     r10d, eax
0x180063c39  movzx   eax, byte ptr [rcx-1]
0x180063c3d  add     r10d, eax
0x180063c40  imul    ecx, r10d, 55h ; 'U'
0x180063c44  shr     ecx, 6
0x180063c47  mov     rax, [rsi+8]
0x180063c4b  movsxd  r10, ebx
0x180063c4e  mov     [rax+rdi-4], cx
0x180063c53  movups  xmm0, xmmword ptr [r9+8]
0x180063c58  mov     rax, [r9+18h]
0x180063c5c  movups  [rbp+var_30], xmm0
0x180063c60  mov     rcx, qword ptr [rbp+var_30+8]
0x180063c64  movzx   eax, byte ptr [rax+r10]
0x180063c69  movq    r8, xmm0
0x180063c6e  movzx   edx, byte ptr [rcx+r10]
0x180063c73  add     edx, eax
0x180063c75  movzx   eax, byte ptr [r8+r10]
0x180063c7a  add     edx, eax
0x180063c7c  imul    ecx, edx, 55h ; 'U'
0x180063c7f  shr     ecx, 6
0x180063c82  cmp     cx, r13w
0x180063c86  jbe     short loc_180063CBE
0x180063c88  test    ebx, ebx
0x180063c8a  jle     short loc_180063CBE
0x180063c8c  mov     rcx, [r9+18h]
0x180063c90  movq    r8, xmm0
0x180063c95  add     rcx, r10
0x180063c98  movups  [rbp+var_30], xmm0
0x180063c9c  mov     rdx, qword ptr [rbp+var_30+8]
0x180063ca0  add     rdx, r10
0x180063ca3  movzx   r10d, byte ptr [r8+r10-1]
0x180063ca9  movzx   eax, byte ptr [rdx-1]
0x180063cad  add     r10d, eax
0x180063cb0  movzx   eax, byte ptr [rcx-1]
0x180063cb4  add     r10d, eax
0x180063cb7  imul    ecx, r10d, 55h ; 'U'
0x180063cbb  shr     ecx, 6
0x180063cbe  mov     rax, [rsi+8]
0x180063cc2  lea     r14d, [rbx+1]
0x180063cc6  movsxd  r10, ebx
0x180063cc9  inc     r10
0x180063ccc  mov     [rdi+rax-2], cx
0x180063cd1  movups  xmm0, xmmword ptr [r9+8]
0x180063cd6  mov     rax, [r9+18h]
0x180063cda  movq    rdx, xmm0
0x180063cdf  movups  [rbp+var_30], xmm0
0x180063ce3  movzx   ecx, byte ptr [rax+r10]
0x180063ce8  mov     r8, qword ptr [rbp+var_30+8]
0x180063cec  movzx   eax, byte ptr [rdx+r10]
0x180063cf1  add     ecx, eax
0x180063cf3  movzx   eax, byte ptr [r8+r10]
0x180063cf8  add     ecx, eax
0x180063cfa  imul    edx, ecx, 55h ; 'U'
0x180063cfd  shr     edx, 6
0x180063d00  cmp     dx, r13w
0x180063d04  jbe     short loc_180063D3D
0x180063d06  test    r14d, r14d
0x180063d09  jle     short loc_180063D3D
0x180063d0b  mov     rcx, [r9+18h]
0x180063d0f  movq    r8, xmm0
0x180063d14  add     rcx, r10
0x180063d17  movups  [rbp+var_30], xmm0
0x180063d1b  mov     rdx, qword ptr [rbp+var_30+8]
0x180063d1f  add     rdx, r10
0x180063d22  movzx   r10d, byte ptr [r8+r10-1]
0x180063d28  movzx   eax, byte ptr [rdx-1]
0x180063d2c  add     r10d, eax
0x180063d2f  movzx   eax, byte ptr [rcx-1]
0x180063d33  add     r10d, eax
0x180063d36  imul    edx, r10d, 55h ; 'U'
0x180063d3a  shr     edx, 6
0x180063d3d  mov     rax, [rsi+8]
0x180063d41  lea     r8d, [rbx+2]
0x180063d45  movsxd  r10, ebx
0x180063d48  mov     [rdi+rax], dx
0x180063d4c  movups  xmm0, xmmword ptr [r9+8]
0x180063d51  mov     rcx, [r9+18h]
0x180063d55  movups  [rbp+var_30], xmm0
0x180063d59  mov     rax, qword ptr [rbp+var_30+8]
0x180063d5d  movq    rdx, xmm0
0x180063d62  movzx   eax, byte ptr [rax+r10+2]
0x180063d68  movzx   edx, byte ptr [rdx+r10+2]
0x180063d6e  add     edx, eax
0x180063d70  movzx   eax, byte ptr [rcx+r10+2]
0x180063d76  add     edx, eax
0x180063d78  imul    ecx, edx, 55h ; 'U'
0x180063d7b  shr     ecx, 6
0x180063d7e  cmp     cx, r13w
0x180063d82  jbe     short loc_180063DB6
0x180063d84  test    r8d, r8d
0x180063d87  jle     short loc_180063DB6
0x180063d89  mov     rax, [r9+18h]
0x180063d8d  movq    rdx, xmm0
0x180063d92  movups  [rbp+var_30], xmm0
0x180063d96  mov     r8, qword ptr [rbp+var_30+8]
0x180063d9a  movzx   ecx, byte ptr [rax+r10+1]
0x180063da0  movzx   eax, byte ptr [rdx+r10+1]
0x180063da6  add     ecx, eax
0x180063da8  movzx   eax, byte ptr [r8+r10+1]
0x180063dae  add     ecx, eax
0x180063db0  imul    ecx, 55h ; 'U'
0x180063db3  shr     ecx, 6
0x180063db6  mov     rax, [rsi+8]
0x180063dba  lea     r8d, [rbx+3]
0x180063dbe  movsxd  r10, ebx
0x180063dc1  add     r10, 3
0x180063dc5  mov     [rdi+rax+2], cx
0x180063dca  movups  xmm0, xmmword ptr [r9+8]
0x180063dcf  mov     rcx, [r9+18h]
0x180063dd3  movups  [rbp+var_30], xmm0
0x180063dd7  mov     rax, qword ptr [rbp+var_30+8]
0x180063ddb  movq    rdx, xmm0
0x180063de0  movzx   eax, byte ptr [rax+r10]
0x180063de5  movzx   edx, byte ptr [rdx+r10]
0x180063dea  add     edx, eax
0x180063dec  movzx   eax, byte ptr [rcx+r10]
0x180063df1  add     edx, eax
0x180063df3  imul    ecx, edx, 55h ; 'U'
0x180063df6  shr     ecx, 6
0x180063df9  cmp     cx, r13w
0x180063dfd  jbe     short loc_180063E36
0x180063dff  test    r8d, r8d
0x180063e02  jle     short loc_180063E36
0x180063e04  mov     rcx, [r9+18h]
0x180063e08  movq    r8, xmm0
0x180063e0d  add     rcx, r10
0x180063e10  movups  [rbp+var_30], xmm0
0x180063e14  mov     rdx, qword ptr [rbp+var_30+8]
0x180063e18  add     rdx, r10
  ... truncated ...
```

# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<uchar *>,4,1>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ReduceComprehensiveSDK<Data::HighDescription<ushort *>>(Binary::Definition::GeneralQuality<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<uchar *>,4,1>> &,Binary::Definition::GeneralQuality<Data::HighDescription<ushort *>> &)

- ea: `0x1800624d0`
- end: `0x180062ae0`
- name: `??$ReduceComprehensiveSDK@V?$HighDescription@PEAG@Data@@@?$SlowLocation@V?$ActiveRegion@V?$HighDescription@PEAE@Data@@$03$00@IntegratedSelection@Binary@@V?$MixedResponse@$02$0A@$07$0A@@23@@IntegratedSelection@Binary@@AEAAXAEAV?$GeneralQuality@V?$ActiveRegion@V?$HighDescription@PEAE@Data@@$03$00@IntegratedSelection@Binary@@@Definition@2@AEAV?$GeneralQuality@V?$HighDescription@PEAG@Data@@@42@@Z`
- size: `1552`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800564a0`

## callees

- `0x1800624d0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned char *>,4,1>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ReduceComprehensiveSDK<Data::HighDescription<unsigned short *>>(
        _DWORD *a1,
        __int64 a2,
        int *a3)
{
  int v3; // edi
  __int64 v4; // r9
  int v8; // edi
  int v9; // ecx
  __int64 v10; // r15
  int v11; // r12d
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // rax
  int v16; // r10d
  __int64 v17; // rax
  unsigned int v18; // r11d
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r14
  int v23; // r10d
  __int64 v24; // r8
  __int64 v25; // r11
  __int64 v26; // rax
  unsigned int v27; // ecx
  __int64 v28; // rax
  unsigned int v29; // ecx
  __int64 v30; // rax
  unsigned int v31; // ecx
  __int64 v32; // rax
  unsigned int v33; // ecx
  __int64 v34; // rax
  unsigned int v35; // ecx
  __int64 v36; // rax
  unsigned int v37; // ecx
  __int64 v38; // rax
  unsigned int v39; // ecx
  __int64 v40; // rax
  unsigned int v41; // ecx
  __int64 v42; // r10
  __int64 v43; // rax
  unsigned int v44; // ecx
  int v45; // r8d
  int v46; // r14d
  __int64 v47; // r12
  int v48; // r11d
  int v49; // r15d
  char v50; // al
  int v51; // r10d
  __int64 v52; // rdx
  int v53; // ecx
  int v54; // r12d
  int v55; // r10d
  __int64 v56; // r15
  __int64 v57; // rax
  unsigned int v58; // ecx
  int v59; // ecx

  v3 = a1[8];
  v4 = 0;
  if ( v3 > 0 )
    v3 = 0;
  v8 = -v3;
  *(_QWORD *)(a2 + 8) += 4LL * v8;
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
          v24 = 0;
          v25 = 6;
          do
          {
            v26 = *(_QWORD *)(a2 + 8);
            v27 = (85
                 * (*(unsigned __int8 *)(v26 + 4 * v24)
                  + *(unsigned __int8 *)(v26 + 4 * v24 + 1)
                  + (unsigned int)*(unsigned __int8 *)(v26 + 4 * v24 + 2))) >> 6;
            if ( (unsigned __int16)v27 > 0x3ECu && (int)v4 > 0 )
              v27 = (85
                   * (*(unsigned __int8 *)(v26 + 4 * v24 - 4)
                    + *(unsigned __int8 *)(v26 + 4 * v24 - 3)
                    + (unsigned int)*(unsigned __int8 *)(v26 + 4 * v24 - 2))) >> 6;
            *(_WORD *)(v25 + *((_QWORD *)a3 + 1) - 6) = v27;
            v28 = *(_QWORD *)(a2 + 8);
            v29 = (85
                 * (*(unsigned __int8 *)(v28 + 4LL * v23 - 4)
                  + *(unsigned __int8 *)(v28 + 4LL * v23 - 3)
                  + (unsigned int)*(unsigned __int8 *)(v28 + 4LL * v23 - 2))) >> 6;
            if ( (unsigned __int16)v29 > 0x3ECu && v23 - 1 > 0 )
              v29 = (85
                   * (*(unsigned __int8 *)(v28 + 4LL * v23 - 8)
                    + *(unsigned __int8 *)(v28 + 4LL * v23 - 7)
                    + (unsigned int)*(unsigned __int8 *)(v28 + 4LL * v23 - 6))) >> 6;
            *(_WORD *)(v25 + *((_QWORD *)a3 + 1) - 4) = v29;
            v30 = *(_QWORD *)(a2 + 8);
            v31 = (85
                 * (*(unsigned __int8 *)(v30 + 4LL * v23)
                  + *(unsigned __int8 *)(v30 + 4LL * v23 + 1)
                  + (unsigned int)*(unsigned __int8 *)(v30 + 4LL * v23 + 2))) >> 6;
            if ( (unsigned __int16)v31 > 0x3ECu && v23 > 0 )
              v31 = (85
                   * (*(unsigned __int8 *)(v30 + 4LL * v23 - 4)
                    + *(unsigned __int8 *)(v30 + 4LL * v23 - 3)
                    + (unsigned int)*(unsigned __int8 *)(v30 + 4LL * v23 - 2))) >> 6;
            *(_WORD *)(v25 + *((_QWORD *)a3 + 1) - 2) = v31;
            v32 = *(_QWORD *)(a2 + 8);
            v33 = (85
                 * (*(unsigned __int8 *)(v32 + 4LL * v23 + 4)
                  + *(unsigned __int8 *)(v32 + 4LL * v23 + 5)
                  + (unsigned int)*(unsigned __int8 *)(v32 + 4LL * v23 + 6))) >> 6;
            if ( (unsigned __int16)v33 > 0x3ECu && v23 + 1 > 0 )
              v33 = (85
                   * (*(unsigned __int8 *)(v32 + 4LL * v23)
                    + *(unsigned __int8 *)(v32 + 4LL * v23 + 1)
                    + (unsigned int)*(unsigned __int8 *)(v32 + 4LL * v23 + 2))) >> 6;
            *(_WORD *)(v25 + *((_QWORD *)a3 + 1)) = v33;
            v34 = *(_QWORD *)(a2 + 8);
            v35 = (85
                 * (*(unsigned __int8 *)(v34 + 4LL * v23 + 8)
                  + *(unsigned __int8 *)(v34 + 4LL * v23 + 9)
                  + (unsigned int)*(unsigned __int8 *)(v34 + 4LL * v23 + 10))) >> 6;
            if ( (unsigned __int16)v35 > 0x3ECu && v23 + 2 > 0 )
              v35 = (85
                   * (*(unsigned __int8 *)(v34 + 4LL * v23 + 4)
                    + *(unsigned __int8 *)(v34 + 4LL * v23 + 5)
                    + (unsigned int)*(unsigned __int8 *)(v34 + 4LL * v23 + 6))) >> 6;
            *(_WORD *)(v25 + *((_QWORD *)a3 + 1) + 2) = v35;
            v36 = *(_QWORD *)(a2 + 8);
            v37 = (85
                 * (*(unsigned __int8 *)(v36 + 4LL * v23 + 12)
                  + *(unsigned __int8 *)(v36 + 4LL * v23 + 13)
                  + (unsigned int)*(unsigned __int8 *)(v36 + 4LL * v23 + 14))) >> 6;
            if ( (unsigned __int16)v37 > 0x3ECu && v23 + 3 > 0 )
              v37 = (85
                   * (*(unsigned __int8 *)(v36 + 4LL * v23 + 8)
                    + *(unsigned __int8 *)(v36 + 4LL * v23 + 9)
                    + (unsigned int)*(unsigned __int8 *)(v36 + 4LL * v23 + 10))) >> 6;
            *(_WORD *)(v25 + *((_QWORD *)a3 + 1) + 4) = v37;
            v38 = *(_QWORD *)(a2 + 8);
            v39 = (85
                 * (*(unsigned __int8 *)(v38 + 4LL * v23 + 16)
                  + *(unsigned __int8 *)(v38 + 4LL * v23 + 17)
                  + (unsigned int)*(unsigned __int8 *)(v38 + 4LL * v23 + 18))) >> 6;
            if ( (unsigned __int16)v39 > 0x3ECu && v23 + 4 > 0 )
              v39 = (85
                   * (*(unsigned __int8 *)(v38 + 4LL * v23 + 12)
                    + *(unsigned __int8 *)(v38 + 4LL * v23 + 13)
                    + (unsigned int)*(unsigned __int8 *)(v38 + 4LL * v23 + 14))) >> 6;
            *(_WORD *)(v25 + *((_QWORD *)a3 + 1) + 6) = v39;
            v40 = *(_QWORD *)(a2 + 8);
            v41 = (85
                 * (*(unsigned __int8 *)(v40 + 4LL * v23 + 20)
                  + *(unsigned __int8 *)(v40 + 4LL * v23 + 21)
                  + (unsigned int)*(unsigned __int8 *)(v40 + 4LL * v23 + 22))) >> 6;
            if ( (unsigned __int16)v41 > 0x3ECu && v23 + 5 > 0 )
              v41 = (85
                   * (*(unsigned __int8 *)(v40 + 4LL * v23 + 16)
                    + *(unsigned __int8 *)(v40 + 4LL * v23 + 17)
                    + (unsigned int)*(unsigned __int8 *)(v40 + 4LL * v23 + 18))) >> 6;
            v15 = *((_QWORD *)a3 + 1);
            LODWORD(v4) = v4 + 8;
            v23 += 8;
            v24 = (int)v4;
            *(_WORD *)(v25 + v15 + 8) = v41;
            v25 += 16;
          }
          while ( (int)v4 < v22 );
        }
      }
      v42 = (int)v4;
      if ( (int)v4 < (__int64)v11 )
      {
        do
        {
          v43 = *(_QWORD *)(a2 + 8);
          v44 = (85
               * (*(unsigned __int8 *)(v43 + 4LL * (int)v4)
                + *(unsigned __int8 *)(v43 + 4LL * (int)v4 + 1)
                + (unsigned int)*(unsigned __int8 *)(v43 + 4LL * (int)v4 + 2))) >> 6;
          if ( (unsigned __int16)v44 > 0x3ECu && (int)v4 > 0 )
            v44 = (85
                 * (*(unsigned __int8 *)(v43 + 4LL * (int)v4 - 4)
                  + *(unsigned __int8 *)(v43 + 4LL * (int)v4 - 3)
                  + (unsigned int)*(unsigned __int8 *)(v43 + 4LL * (int)v4 - 2))) >> 6;
          v15 = *((_QWORD *)a3 + 1);
          LODWORD(v4) = v4 + 1;
          *(_WORD *)(v15 + 2 * v42++) = v44;
        }
        while ( v42 < v11 );
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
        v14 = *(_DWORD *)a2 - v8;
      if ( v14 > 0 )
      {
        do
        {
          v17 = *(_QWORD *)(a2 + 8);
          v18 = (85
               * (*(unsigned __int8 *)(v17 + 4LL * v16)
                + *(unsigned __int8 *)(v17 + 4LL * v16 + 1)
                + (unsigned int)*(unsigned __int8 *)(v17 + 4LL * v16 + 2))) >> 6;
          if ( (unsigned __int16)v18 > 0x3ECu && v16 > 0 )
            v18 = (85
                 * (*(unsigned __int8 *)(v17 + 4LL * v16 - 4)
                  + *(unsigned __int8 *)(v17 + 4LL * v16 - 3)
                  + (unsigned int)*(unsigned __int8 *)(v17 + 4LL * v16 - 2))) >> 6;
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
    v45 = a1[9];
    v46 = v9;
    if ( v9 <= 0 )
      v46 = 1;
    if ( v45 < 0 || v45 >= v46 )
    {
      v45 %= v46;
      if ( v45 < 0 )
        v45 += v46;
    }
    v47 = *a3;
    v48 = v45;
    v49 = 0;
    if ( (unsigned __int64)(v47 * (int)a1[762] + 0x80000000LL) > 0xFFFFFFFF )
    {
      v50 = 0;
    }
    else
    {
      v49 = v47 * a1[762];
      v50 = 1;
    }
    if ( !v50 )
      v49 = 0;
    v51 = v49 / v9;
    v52 = (unsigned int)((int)v47 >> 31);
    LODWORD(v52) = (int)v47 % v9;
    LODWORD(v15) = (int)v47 / v9;
    if ( (int)v47 % v9 > 0 )
    {
      do
      {
        v51 += a1[v45 + 388];
        v53 = v45 + 1;
        v45 = 0;
        if ( v53 < v46 )
          v45 = v53;
        --v52;
      }
      while ( v52 );
    }
    v54 = *(_DWORD *)a2 - v8;
    if ( v51 > a1[3] )
      v51 = a1[3];
    if ( v51 <= v54 )
      v54 = v51;
    v55 = 0;
    if ( v54 > 0 )
    {
      v56 = 0;
      do
      {
        v57 = *(_QWORD *)(a2 + 8);
        v58 = (85
             * (*(unsigned __int8 *)(v57 + 4LL * v55)
              + *(unsigned __int8 *)(v57 + 4LL * v55 + 1)
              + (unsigned int)*(unsigned __int8 *)(v57 + 4LL * v55 + 2))) >> 6;
        if ( (unsigned __int16)v58 > 0x3ECu && v55 > 0 )
          v58 = (85
               * (*(unsigned __int8 *)(v57 + 4LL * v55 - 4)
                + *(unsigned __int8 *)(v57 + 4LL * v55 - 3)
                + (unsigned int)*(unsigned __int8 *)(v57 + 4LL * v55 - 2))) >> 6;
        *(_WORD *)(v56 + *((_QWORD *)a3 + 1)) = v58;
        v59 = v48 + 1;
        v15 = v48;
        v56 += 2;
        v48 = 0;
        v55 += a1[v15 + 388];
        if ( v59 < v46 )
          v48 = v59;
      }
      while ( v55 < v54 );
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800624d0  mov     [rsp+arg_0], rbx
0x1800624d5  mov     [rsp+arg_8], rbp
0x1800624da  mov     [rsp+arg_10], rsi
0x1800624df  mov     [rsp+arg_18], rdi
0x1800624e4  push    r12
0x1800624e6  push    r14
0x1800624e8  push    r15
0x1800624ea  mov     edi, [rcx+20h]
0x1800624ed  xor     r9d, r9d
0x1800624f0  test    edi, edi
0x1800624f2  mov     rbp, rcx
0x1800624f5  mov     rbx, r8
0x1800624f8  mov     rsi, rdx
0x1800624fb  cmovg   edi, r9d
0x1800624ff  neg     edi
0x180062501  movsxd  rax, edi
0x180062504  shl     rax, 2
0x180062508  add     [rdx+8], rax
0x18006250c  mov     ecx, [rcx+2Ch]
0x18006250f  cmp     ecx, 1
0x180062512  jnz     loc_180062983
0x180062518  mov     r12d, [rdx]
0x18006251b  movsxd  r15, dword ptr [rbp+610h]
0x180062522  sub     r12d, edi
0x180062525  movsxd  rcx, dword ptr [r8]
0x180062528  cmp     r15d, 1
0x18006252c  jz      loc_1800625E9
0x180062532  imul    rcx, r15
0x180062536  mov     eax, 80000000h
0x18006253b  mov     edx, 0FFFFFFFFh
0x180062540  add     rax, rcx
0x180062543  mov     r14d, r9d
0x180062546  cmp     rax, rdx
0x180062549  ja      short loc_180062552
0x18006254b  mov     r14d, ecx
0x18006254e  mov     al, 1
0x180062550  jmp     short loc_180062554
0x180062552  xor     al, al
0x180062554  test    al, al
0x180062556  mov     r10d, r9d
0x180062559  cmovz   r14d, r9d
0x18006255d  cmp     [rbp+0Ch], r14d
0x180062561  cmovle  r14d, [rbp+0Ch]
0x180062566  cmp     r14d, r12d
0x180062569  cmovg   r14d, r12d
0x18006256d  test    r14d, r14d
0x180062570  jle     loc_180062AC5
0x180062576  mov     edi, 3ECh
0x18006257b  nop     dword ptr [rax+rax+00h]
0x180062580  mov     rax, [rsi+8]
0x180062584  movsxd  rdx, r10d
0x180062587  movzx   ecx, byte ptr [rax+rdx*4+1]
0x18006258c  movzx   r8d, byte ptr [rax+rdx*4+2]
0x180062592  add     r8d, ecx
0x180062595  movzx   ecx, byte ptr [rax+rdx*4]
0x180062599  add     r8d, ecx
0x18006259c  imul    r11d, r8d, 55h ; 'U'
0x1800625a0  shr     r11d, 6
0x1800625a4  cmp     r11w, di
0x1800625a8  jbe     short loc_1800625CD
0x1800625aa  test    r10d, r10d
0x1800625ad  jle     short loc_1800625CD
0x1800625af  movzx   ecx, byte ptr [rax+rdx*4-3]
0x1800625b4  movzx   r8d, byte ptr [rax+rdx*4-2]
0x1800625ba  add     r8d, ecx
0x1800625bd  movzx   ecx, byte ptr [rax+rdx*4-4]
0x1800625c2  add     r8d, ecx
0x1800625c5  imul    r11d, r8d, 55h ; 'U'
0x1800625c9  shr     r11d, 6
0x1800625cd  mov     rax, [rbx+8]
0x1800625d1  mov     rcx, r9
0x1800625d4  inc     r9
0x1800625d7  add     r10d, r15d
0x1800625da  mov     [rax+rcx*2], r11w
0x1800625df  cmp     r10d, r14d
0x1800625e2  jl      short loc_180062580
0x1800625e4  jmp     loc_180062AC5
0x1800625e9  mov     eax, [rbp+0Ch]
0x1800625ec  mov     edi, 3ECh
0x1800625f1  cmp     eax, ecx
0x1800625f3  cmovg   eax, ecx
0x1800625f6  cmp     eax, r12d
0x1800625f9  cmovle  r12d, eax
0x1800625fd  mov     eax, r12d
0x180062600  cdq
0x180062601  and     edx, 7
0x180062604  add     eax, edx
0x180062606  mov     edx, 0FFFFFFFFh
0x18006260b  sar     eax, 3
0x18006260e  movsxd  rcx, eax
0x180062611  mov     eax, 80000000h
0x180062616  shl     rcx, 3
0x18006261a  add     rax, rcx
0x18006261d  cmp     rax, rdx
0x180062620  ja      loc_180062909
0x180062626  movsxd  r14, ecx
0x180062629  test    ecx, ecx
0x18006262b  jle     loc_180062909
0x180062631  mov     r10d, 2
0x180062637  mov     r8, r9
0x18006263a  lea     r11d, [r10+4]
0x18006263e  xchg    ax, ax
0x180062640  mov     rax, [rsi+8]
0x180062644  movzx   ecx, byte ptr [rax+r8*4+1]
0x18006264a  movzx   edx, byte ptr [rax+r8*4+2]
0x180062650  add     edx, ecx
0x180062652  movzx   ecx, byte ptr [rax+r8*4]
0x180062657  add     edx, ecx
0x180062659  imul    ecx, edx, 55h ; 'U'
0x18006265c  shr     ecx, 6
0x18006265f  cmp     cx, di
0x180062662  jbe     short loc_180062685
0x180062664  test    r9d, r9d
0x180062667  jle     short loc_180062685
0x180062669  movzx   ecx, byte ptr [rax+r8*4-3]
0x18006266f  movzx   edx, byte ptr [rax+r8*4-2]
0x180062675  add     edx, ecx
0x180062677  movzx   ecx, byte ptr [rax+r8*4-4]
0x18006267d  add     edx, ecx
0x18006267f  imul    ecx, edx, 55h ; 'U'
0x180062682  shr     ecx, 6
0x180062685  mov     rax, [rbx+8]
0x180062689  lea     ebp, [r10-1]
0x18006268d  movsxd  rdx, r10d
0x180062690  mov     [r11+rax-6], cx
0x180062696  mov     rax, [rsi+8]
0x18006269a  movzx   ecx, byte ptr [rax+rdx*4-3]
0x18006269f  movzx   r8d, byte ptr [rax+rdx*4-2]
0x1800626a5  add     r8d, ecx
0x1800626a8  movzx   ecx, byte ptr [rax+rdx*4-4]
0x1800626ad  add     r8d, ecx
0x1800626b0  imul    ecx, r8d, 55h ; 'U'
0x1800626b4  shr     ecx, 6
0x1800626b7  cmp     cx, di
0x1800626ba  jbe     short loc_1800626DD
0x1800626bc  test    ebp, ebp
0x1800626be  jle     short loc_1800626DD
0x1800626c0  movzx   ecx, byte ptr [rax+rdx*4-7]
0x1800626c5  movzx   r8d, byte ptr [rax+rdx*4-6]
0x1800626cb  add     r8d, ecx
0x1800626ce  movzx   ecx, byte ptr [rax+rdx*4-8]
0x1800626d3  add     r8d, ecx
0x1800626d6  imul    ecx, r8d, 55h ; 'U'
0x1800626da  shr     ecx, 6
0x1800626dd  mov     rax, [rbx+8]
0x1800626e1  movsxd  rdx, r10d
0x1800626e4  mov     [r11+rax-4], cx
0x1800626ea  mov     rax, [rsi+8]
0x1800626ee  movzx   ecx, byte ptr [rax+rdx*4+1]
0x1800626f3  movzx   r8d, byte ptr [rax+rdx*4+2]
0x1800626f9  add     r8d, ecx
0x1800626fc  movzx   ecx, byte ptr [rax+rdx*4]
0x180062700  add     r8d, ecx
0x180062703  imul    ecx, r8d, 55h ; 'U'
0x180062707  shr     ecx, 6
0x18006270a  cmp     cx, di
0x18006270d  jbe     short loc_180062731
0x18006270f  test    r10d, r10d
0x180062712  jle     short loc_180062731
0x180062714  movzx   ecx, byte ptr [rax+rdx*4-3]
0x180062719  movzx   r8d, byte ptr [rax+rdx*4-2]
0x18006271f  add     r8d, ecx
0x180062722  movzx   ecx, byte ptr [rax+rdx*4-4]
0x180062727  add     r8d, ecx
0x18006272a  imul    ecx, r8d, 55h ; 'U'
0x18006272e  shr     ecx, 6
0x180062731  mov     rax, [rbx+8]
0x180062735  lea     ebp, [r10+1]
0x180062739  movsxd  rdx, r10d
0x18006273c  mov     [r11+rax-2], cx
0x180062742  mov     rax, [rsi+8]
0x180062746  movzx   ecx, byte ptr [rax+rdx*4+5]
0x18006274b  movzx   r8d, byte ptr [rax+rdx*4+6]
0x180062751  add     r8d, ecx
0x180062754  movzx   ecx, byte ptr [rax+rdx*4+4]
0x180062759  add     r8d, ecx
0x18006275c  imul    ecx, r8d, 55h ; 'U'
0x180062760  shr     ecx, 6
0x180062763  cmp     cx, di
0x180062766  jbe     short loc_180062788
0x180062768  test    ebp, ebp
0x18006276a  jle     short loc_180062788
0x18006276c  movzx   ecx, byte ptr [rax+rdx*4+1]
0x180062771  movzx   r8d, byte ptr [rax+rdx*4+2]
0x180062777  add     r8d, ecx
0x18006277a  movzx   ecx, byte ptr [rax+rdx*4]
0x18006277e  add     r8d, ecx
0x180062781  imul    ecx, r8d, 55h ; 'U'
0x180062785  shr     ecx, 6
0x180062788  mov     rax, [rbx+8]
0x18006278c  lea     ebp, [r10+2]
0x180062790  movsxd  rdx, r10d
0x180062793  mov     [r11+rax], cx
0x180062798  mov     rax, [rsi+8]
0x18006279c  movzx   ecx, byte ptr [rax+rdx*4+9]
0x1800627a1  movzx   r8d, byte ptr [rax+rdx*4+0Ah]
0x1800627a7  add     r8d, ecx
0x1800627aa  movzx   ecx, byte ptr [rax+rdx*4+8]
0x1800627af  add     r8d, ecx
0x1800627b2  imul    ecx, r8d, 55h ; 'U'
0x1800627b6  shr     ecx, 6
0x1800627b9  cmp     cx, di
0x1800627bc  jbe     short loc_1800627DF
0x1800627be  test    ebp, ebp
0x1800627c0  jle     short loc_1800627DF
0x1800627c2  movzx   ecx, byte ptr [rax+rdx*4+5]
0x1800627c7  movzx   r8d, byte ptr [rax+rdx*4+6]
0x1800627cd  add     r8d, ecx
0x1800627d0  movzx   ecx, byte ptr [rax+rdx*4+4]
0x1800627d5  add     r8d, ecx
0x1800627d8  imul    ecx, r8d, 55h ; 'U'
0x1800627dc  shr     ecx, 6
0x1800627df  mov     rax, [rbx+8]
0x1800627e3  lea     ebp, [r10+3]
0x1800627e7  movsxd  rdx, r10d
0x1800627ea  mov     [r11+rax+2], cx
0x1800627f0  mov     rax, [rsi+8]
0x1800627f4  movzx   ecx, byte ptr [rax+rdx*4+0Dh]
0x1800627f9  movzx   r8d, byte ptr [rax+rdx*4+0Eh]
0x1800627ff  add     r8d, ecx
0x180062802  movzx   ecx, byte ptr [rax+rdx*4+0Ch]
0x180062807  add     r8d, ecx
0x18006280a  imul    ecx, r8d, 55h ; 'U'
0x18006280e  shr     ecx, 6
0x180062811  cmp     cx, di
0x180062814  jbe     short loc_180062837
0x180062816  test    ebp, ebp
0x180062818  jle     short loc_180062837
0x18006281a  movzx   ecx, byte ptr [rax+rdx*4+9]
0x18006281f  movzx   r8d, byte ptr [rax+rdx*4+0Ah]
0x180062825  add     r8d, ecx
0x180062828  movzx   ecx, byte ptr [rax+rdx*4+8]
0x18006282d  add     r8d, ecx
0x180062830  imul    ecx, r8d, 55h ; 'U'
0x180062834  shr     ecx, 6
0x180062837  mov     rax, [rbx+8]
0x18006283b  lea     ebp, [r10+4]
0x18006283f  movsxd  rdx, r10d
0x180062842  mov     [r11+rax+4], cx
0x180062848  mov     rax, [rsi+8]
0x18006284c  movzx   ecx, byte ptr [rax+rdx*4+11h]
0x180062851  movzx   r8d, byte ptr [rax+rdx*4+12h]
0x180062857  add     r8d, ecx
0x18006285a  movzx   ecx, byte ptr [rax+rdx*4+10h]
0x18006285f  add     r8d, ecx
0x180062862  imul    ecx, r8d, 55h ; 'U'
0x180062866  shr     ecx, 6
0x180062869  cmp     cx, di
0x18006286c  jbe     short loc_18006288F
0x18006286e  test    ebp, ebp
0x180062870  jle     short loc_18006288F
0x180062872  movzx   ecx, byte ptr [rax+rdx*4+0Dh]
0x180062877  movzx   r8d, byte ptr [rax+rdx*4+0Eh]
0x18006287d  add     r8d, ecx
0x180062880  movzx   ecx, byte ptr [rax+rdx*4+0Ch]
0x180062885  add     r8d, ecx
0x180062888  imul    ecx, r8d, 55h ; 'U'
0x18006288c  shr     ecx, 6
0x18006288f  mov     rax, [rbx+8]
0x180062893  lea     ebp, [r10+5]
0x180062897  movsxd  rdx, r10d
0x18006289a  mov     [r11+rax+6], cx
0x1800628a0  mov     rax, [rsi+8]
0x1800628a4  movzx   ecx, byte ptr [rax+rdx*4+15h]
0x1800628a9  movzx   r8d, byte ptr [rax+rdx*4+16h]
0x1800628af  add     r8d, ecx
0x1800628b2  movzx   ecx, byte ptr [rax+rdx*4+14h]
0x1800628b7  add     r8d, ecx
0x1800628ba  imul    ecx, r8d, 55h ; 'U'
0x1800628be  shr     ecx, 6
0x1800628c1  cmp     cx, di
0x1800628c4  jbe     short loc_1800628E7
0x1800628c6  test    ebp, ebp
0x1800628c8  jle     short loc_1800628E7
0x1800628ca  movzx   ecx, byte ptr [rax+rdx*4+11h]
0x1800628cf  movzx   r8d, byte ptr [rax+rdx*4+12h]
0x1800628d5  add     r8d, ecx
0x1800628d8  movzx   ecx, byte ptr [rax+rdx*4+10h]
0x1800628dd  add     r8d, ecx
0x1800628e0  imul    ecx, r8d, 55h ; 'U'
0x1800628e4  shr     ecx, 6
0x1800628e7  mov     rax, [rbx+8]
0x1800628eb  add     r9d, 8
0x1800628ef  add     r10d, 8
0x1800628f3  movsxd  r8, r9d
0x1800628f6  mov     [r11+rax+8], cx
0x1800628fc  add     r11, 10h
0x180062900  cmp     r8, r14
0x180062903  jl      loc_180062640
0x180062909  movsxd  r10, r9d
0x18006290c  movsxd  r11, r12d
0x18006290f  cmp     r10, r11
0x180062912  jge     loc_180062AC5
0x180062918  nop     dword ptr [rax+rax+00000000h]
0x180062920  mov     rax, [rsi+8]
0x180062924  movsxd  rdx, r9d
0x180062927  movzx   ecx, byte ptr [rax+rdx*4+1]
0x18006292c  movzx   r8d, byte ptr [rax+rdx*4+2]
0x180062932  add     r8d, ecx
0x180062935  movzx   ecx, byte ptr [rax+rdx*4]
  ... truncated ...
```

# BConfigureIFIMetrics

- ea: `0x18002258c`
- end: `0x180022aaf`
- name: `BConfigureIFIMetrics`
- size: `1315`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021f84`
- `0x180043eec`

## callees

- `0x18002258c`
- `0x180074580`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180022680`
- `KERNEL32!LocalAlloc` at `0x180022680`

## pseudocode

```c
__int64 __fastcall BConfigureIFIMetrics(__int64 a1, __int64 a2)
{
  _WORD *v4; // r14
  _WORD *v5; // r13
  void *v6; // r9
  _WORD *v7; // r12
  int v8; // ecx
  __int64 v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // ebp
  __int64 v13; // rax
  _OWORD *v14; // rax
  _OWORD *v15; // rsi
  int *v17; // r8
  _DWORD *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  _WORD *v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rbp
  __int64 v34; // rax
  void *Src; // [rsp+20h] [rbp-58h]
  unsigned int Size; // [rsp+80h] [rbp+8h]
  unsigned int v37; // [rsp+88h] [rbp+10h]
  unsigned int v38; // [rsp+90h] [rbp+18h]
  unsigned int v39; // [rsp+98h] [rbp+20h]

  if ( *(_DWORD *)(a2 + 8) )
    v4 = (_WORD *)(a2 + *(int *)(a2 + 8));
  else
    v4 = 0;
  if ( *(_DWORD *)(a2 + 12) )
    v5 = (_WORD *)(a2 + *(int *)(a2 + 12));
  else
    v5 = 0;
  if ( *(_DWORD *)(a2 + 16) )
    v6 = (void *)(a2 + *(int *)(a2 + 16));
  else
    v6 = 0;
  Src = v6;
  if ( *(_DWORD *)(a2 + 20) )
    v7 = (_WORD *)(a2 + *(int *)(a2 + 20));
  else
    v7 = 0;
  Size = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  if ( *(_DWORD *)(a2 + 4) )
  {
    LODWORD(v9) = 224;
    v8 = *(_DWORD *)(a2 + 188) != 0 ? 0x18 : 0;
    if ( *(_DWORD *)(a2 + 196) )
      v8 += 72;
  }
  else
  {
    v8 = 0;
    LODWORD(v9) = 200;
  }
  v10 = v9 + v8;
  v11 = v9 + v8 + 16;
  if ( !*(_DWORD *)(a2 + 40) )
    v11 = v10;
  v12 = v11 + 72;
  if ( !*(_DWORD *)(a2 + 24) )
    v12 = v11;
  if ( v4 )
  {
    if ( (*(_DWORD *)(a2 + 48) & 0x8000000) != 0 )
    {
      v31 = v4;
      do
      {
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        v31 += (unsigned int)(v32 + 1);
        v12 += 2 * v32 + 2;
      }
      while ( *v31 );
      v12 += 2;
    }
    else
    {
      v28 = -1;
      do
        ++v28;
      while ( v4[v28] );
      Size = 2 * v28 + 2;
      v12 += Size;
    }
  }
  if ( v5 )
  {
    v29 = -1;
    do
      ++v29;
    while ( v5[v29] );
    v37 = 2 * v29 + 2;
    v12 += v37;
  }
  if ( v6 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v6 + v30) );
    v38 = 2 * v30 + 2;
    v12 += v38;
  }
  if ( v7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v7[v13] );
    v39 = 2 * v13 + 2;
    v12 += v39;
  }
  v14 = LocalAlloc(0x40u, v12);
  *(_QWORD *)(a1 + 16) = v14;
  v15 = v14;
  if ( !v14 )
    return 0;
  v17 = 0;
  if ( *(_DWORD *)(a2 + 24) )
    v17 = (int *)(a2 + *(int *)(a2 + 24));
  *(_DWORD *)(a1 + 12) &= ~0x40u;
  *v14 = *(_OWORD *)a2;
  v14[1] = *(_OWORD *)(a2 + 16);
  v14[2] = *(_OWORD *)(a2 + 32);
  v14[3] = *(_OWORD *)(a2 + 48);
  v14[4] = *(_OWORD *)(a2 + 64);
  v14[5] = *(_OWORD *)(a2 + 80);
  v14[6] = *(_OWORD *)(a2 + 96);
  v14[7] = *(_OWORD *)(a2 + 112);
  v14[8] = *(_OWORD *)(a2 + 128);
  v14[9] = *(_OWORD *)(a2 + 144);
  v14[10] = *(_OWORD *)(a2 + 160);
  v14[11] = *(_OWORD *)(a2 + 176);
  if ( *(_DWORD *)(a2 + 4) )
  {
    v18 = *(_DWORD **)(a1 + 16);
    v18[48] = *(_DWORD *)(a2 + 184);
    v18[50] = *(_DWORD *)(a2 + 192);
    v19 = *(int *)(a2 + 188);
    if ( (_DWORD)v19 )
    {
      *(_OWORD *)((char *)v15 + (unsigned int)v9) = *(_OWORD *)(v19 + a2);
      *(_QWORD *)((char *)v15 + (unsigned int)v9 + 16) = *(_QWORD *)(v19 + a2 + 16);
      v18[49] = v9;
      LODWORD(v9) = v9 + 24;
    }
    v20 = *(int *)(a2 + 196);
    if ( (_DWORD)v20 )
    {
      *(_OWORD *)((char *)v15 + (unsigned int)v9) = *(_OWORD *)(v20 + a2);
      *(_OWORD *)((char *)v15 + (unsigned int)v9 + 16) = *(_OWORD *)(v20 + a2 + 16);
      *(_OWORD *)((char *)v15 + (unsigned int)v9 + 32) = *(_OWORD *)(v20 + a2 + 32);
      *(_OWORD *)((char *)v15 + (unsigned int)v9 + 48) = *(_OWORD *)(v20 + a2 + 48);
      *(_QWORD *)((char *)v15 + (unsigned int)v9 + 64) = *(_QWORD *)(v20 + a2 + 64);
      v18[51] = v9;
      LODWORD(v9) = v9 + 72;
    }
    v18[52] = 0;
  }
  **(_DWORD **)(a1 + 16) = v12;
  if ( v17 )
  {
    v21 = (unsigned int)v9;
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = v9;
    v9 = (unsigned int)(v9 + 12);
    if ( *v17 )
    {
      v22 = *(int *)(a2 + 24);
      v23 = a2 + *v17;
      *(_OWORD *)((char *)v15 + v9) = *(_OWORD *)(v22 + v23);
      *(_DWORD *)((char *)v15 + v9 + 16) = *(_DWORD *)(v22 + v23 + 16);
      *(_DWORD *)((char *)v15 + v21) = v9 - *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      v9 = (unsigned int)(v9 + 20);
    }
    if ( v17[1] )
    {
      v24 = *(int *)(a2 + 24);
      v25 = a2 + v17[1];
      *(_OWORD *)((char *)v15 + v9) = *(_OWORD *)(v24 + v25);
      *(_DWORD *)((char *)v15 + v9 + 16) = *(_DWORD *)(v24 + v25 + 16);
      *(_DWORD *)((char *)v15 + v21 + 4) = v9 - *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      v9 = (unsigned int)(v9 + 20);
    }
    if ( v17[2] )
    {
      v26 = *(int *)(a2 + 24);
      v27 = a2 + v17[2];
      *(_OWORD *)((char *)v15 + v9) = *(_OWORD *)(v26 + v27);
      *(_DWORD *)((char *)v15 + v9 + 16) = *(_DWORD *)(v26 + v27 + 16);
      *(_DWORD *)((char *)v15 + v21 + 8) = v9 - *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      LODWORD(v9) = v9 + 20;
    }
  }
  if ( *(_DWORD *)(a2 + 40) )
  {
    *(_OWORD *)((char *)v15 + (int)v9) = *(_OWORD *)(*(int *)(a2 + 40) + a2);
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL) = v9;
    LODWORD(v9) = v9 + 16;
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL) = 0;
  }
  if ( v4 )
  {
    if ( (*(_DWORD *)(a2 + 48) & 0x8000000) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 8LL) = v9;
      do
      {
        v33 = -1;
        do
          ++v33;
        while ( v4[v33] );
        memcpy_0((char *)v15 + (int)v9, v4, (unsigned int)(2 * v33 + 2));
        LODWORD(v9) = 2 * v33 + 2 + v9;
        v4 += (unsigned int)(v33 + 1);
      }
      while ( *v4 );
      v34 = (int)v9;
      LODWORD(v9) = v9 + 2;
      *(_WORD *)((char *)v15 + v34) = 0;
    }
    else
    {
      memcpy_0((char *)v15 + (int)v9, v4, Size);
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 8LL) = v9;
      LODWORD(v9) = Size + v9;
    }
  }
  if ( v5 )
  {
    memcpy_0((char *)v15 + (int)v9, v5, v37);
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 12LL) = v9;
    LODWORD(v9) = v37 + v9;
  }
  if ( Src )
  {
    memcpy_0((char *)v15 + (int)v9, Src, v38);
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL) = v9;
    LODWORD(v9) = v38 + v9;
  }
  if ( v7 )
  {
    memcpy_0((char *)v15 + (int)v9, v7, v39);
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 20LL) = v9;
  }
  return 1;
}

```

## disassembly

```asm
0x18002258c  push    rbx
0x18002258e  push    rbp
0x18002258f  push    rsi
0x180022590  push    rdi
0x180022591  push    r12
0x180022593  push    r13
0x180022595  push    r14
0x180022597  push    r15
0x180022599  sub     rsp, 38h
0x18002259d  xor     r10d, r10d
0x1800225a0  mov     rbx, rdx
0x1800225a3  mov     r15, rcx
0x1800225a6  cmp     [rdx+8], r10d
0x1800225aa  jz      loc_1800226A9
0x1800225b0  movsxd  r14, dword ptr [rdx+8]
0x1800225b4  add     r14, rdx
0x1800225b7  cmp     [rdx+0Ch], r10d
0x1800225bb  jz      loc_1800226B1
0x1800225c1  movsxd  r13, dword ptr [rdx+0Ch]
0x1800225c5  add     r13, rbx
0x1800225c8  cmp     [rdx+10h], r10d
0x1800225cc  jz      loc_1800226B9
0x1800225d2  movsxd  r9, dword ptr [rdx+10h]
0x1800225d6  add     r9, rbx
0x1800225d9  mov     [rsp+78h+Src], r9
0x1800225de  cmp     [rdx+14h], r10d
0x1800225e2  jz      loc_1800226C1
0x1800225e8  movsxd  r12, dword ptr [rdx+14h]
0x1800225ec  add     r12, rbx
0x1800225ef  mov     dword ptr [rsp+78h+Size], r10d
0x1800225f7  mov     dword ptr [rsp+78h+arg_8], r10d
0x1800225ff  mov     dword ptr [rsp+78h+arg_10], r10d
0x180022607  mov     dword ptr [rsp+78h+arg_18], r10d
0x18002260f  cmp     [rdx+4], r10d
0x180022613  jnz     loc_1800226C9
0x180022619  mov     ecx, r10d
0x18002261c  mov     edi, 0C8h
0x180022621  cmp     [rdx+28h], r10d
0x180022625  lea     eax, [rdi+rcx]
0x180022628  lea     ecx, [rax+10h]
0x18002262b  cmovz   ecx, eax
0x18002262e  cmp     [rdx+18h], r10d
0x180022632  lea     ebp, [rcx+48h]
0x180022635  cmovz   ebp, ecx
0x180022638  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002263c  test    r14, r14
0x18002263f  jnz     loc_180022930
0x180022645  test    r13, r13
0x180022648  jnz     loc_18002295F
0x18002264e  test    r9, r9
0x180022651  jnz     loc_180022982
0x180022657  test    r12, r12
0x18002265a  jz      short loc_180022679
0x18002265c  mov     rax, rcx
0x18002265f  inc     rax
0x180022662  cmp     [r12+rax*2], r10w
0x180022667  jnz     short loc_18002265F
0x180022669  lea     eax, ds:2[rax*2]
0x180022670  mov     dword ptr [rsp+78h+arg_18], eax
0x180022677  add     ebp, eax
0x180022679  mov     edx, ebp; uBytes
0x18002267b  mov     ecx, 40h ; '@'; uFlags
0x180022680  call    cs:__imp_LocalAlloc
0x180022686  xor     r10d, r10d
0x180022689  mov     [r15+10h], rax
0x18002268d  mov     rsi, rax
0x180022690  test    rax, rax
0x180022693  jnz     short loc_1800226F0
0x180022695  mov     eax, r10d
0x180022698  add     rsp, 38h
0x18002269c  pop     r15
0x18002269e  pop     r14
0x1800226a0  pop     r13
0x1800226a2  pop     r12
0x1800226a4  pop     rdi
0x1800226a5  pop     rsi
0x1800226a6  pop     rbp
0x1800226a7  pop     rbx
0x1800226a8  retn
0x1800226a9  mov     r14, r10
0x1800226ac  jmp     loc_1800225B7
0x1800226b1  mov     r13, r10
0x1800226b4  jmp     loc_1800225C8
0x1800226b9  mov     r9, r10
0x1800226bc  jmp     loc_1800225D9
0x1800226c1  mov     r12, r10
0x1800226c4  jmp     loc_1800225EF
0x1800226c9  mov     eax, [rdx+0BCh]
0x1800226cf  mov     edi, 0E0h
0x1800226d4  neg     eax
0x1800226d6  sbb     ecx, ecx
0x1800226d8  and     ecx, 18h
0x1800226db  cmp     [rdx+0C4h], r10d
0x1800226e2  jz      loc_180022621
0x1800226e8  add     ecx, 48h ; 'H'
0x1800226eb  jmp     loc_180022621
0x1800226f0  mov     r8, r10
0x1800226f3  cmp     [rbx+18h], r10d
0x1800226f7  jz      short loc_180022700
0x1800226f9  movsxd  r8, dword ptr [rbx+18h]
0x1800226fd  add     r8, rbx
0x180022700  and     dword ptr [r15+0Ch], 0FFFFFFBFh
0x180022705  movups  xmm0, xmmword ptr [rbx]
0x180022708  movups  xmmword ptr [rax], xmm0
0x18002270b  movups  xmm1, xmmword ptr [rbx+10h]
0x18002270f  movups  xmmword ptr [rax+10h], xmm1
0x180022713  movups  xmm0, xmmword ptr [rbx+20h]
0x180022717  movups  xmmword ptr [rax+20h], xmm0
0x18002271b  movups  xmm1, xmmword ptr [rbx+30h]
0x18002271f  movups  xmmword ptr [rax+30h], xmm1
0x180022723  movups  xmm0, xmmword ptr [rbx+40h]
0x180022727  movups  xmmword ptr [rax+40h], xmm0
0x18002272b  movups  xmm1, xmmword ptr [rbx+50h]
0x18002272f  movups  xmmword ptr [rax+50h], xmm1
0x180022733  movups  xmm0, xmmword ptr [rbx+60h]
0x180022737  movups  xmmword ptr [rax+60h], xmm0
0x18002273b  movups  xmm1, xmmword ptr [rbx+70h]
0x18002273f  movups  xmmword ptr [rax+70h], xmm1
0x180022743  movups  xmm0, xmmword ptr [rbx+80h]
0x18002274a  movups  xmmword ptr [rax+80h], xmm0
0x180022751  movups  xmm1, xmmword ptr [rbx+90h]
0x180022758  movups  xmmword ptr [rax+90h], xmm1
0x18002275f  movups  xmm0, xmmword ptr [rbx+0A0h]
0x180022766  movups  xmmword ptr [rax+0A0h], xmm0
0x18002276d  movups  xmm1, xmmword ptr [rbx+0B0h]
0x180022774  movups  xmmword ptr [rax+0B0h], xmm1
0x18002277b  cmp     [rbx+4], r10d
0x18002277f  jz      short loc_1800227C2
0x180022781  mov     eax, [rbx+0B8h]
0x180022787  mov     rdx, [r15+10h]
0x18002278b  mov     [rdx+0C0h], eax
0x180022791  mov     eax, [rbx+0C0h]
0x180022797  mov     [rdx+0C8h], eax
0x18002279d  movsxd  rax, dword ptr [rbx+0BCh]
0x1800227a4  test    eax, eax
0x1800227a6  jnz     loc_1800229F9
0x1800227ac  movsxd  rax, dword ptr [rbx+0C4h]
0x1800227b3  test    eax, eax
0x1800227b5  jnz     loc_180022A1D
0x1800227bb  mov     [rdx+0D0h], r10d
0x1800227c2  mov     rax, [r15+10h]
0x1800227c6  mov     [rax], ebp
0x1800227c8  test    r8, r8
0x1800227cb  jz      loc_180022871
0x1800227d1  mov     rax, [r15+10h]
0x1800227d5  mov     r9d, edi
0x1800227d8  mov     [rax+18h], edi
0x1800227db  add     edi, 0Ch
0x1800227de  cmp     [r8], r10d
0x1800227e1  jz      short loc_18002280D
0x1800227e3  movsxd  rdx, dword ptr [rbx+18h]
0x1800227e7  mov     ecx, edi
0x1800227e9  movsxd  rax, dword ptr [r8]
0x1800227ec  add     rax, rbx
0x1800227ef  movups  xmm0, xmmword ptr [rdx+rax]
0x1800227f3  movups  xmmword ptr [rdi+rsi], xmm0
0x1800227f7  mov     eax, [rdx+rax+10h]
0x1800227fb  mov     [rdi+rsi+10h], eax
0x1800227ff  mov     rax, [r15+10h]
0x180022803  sub     ecx, [rax+18h]
0x180022806  mov     [r9+rsi], ecx
0x18002280a  add     edi, 14h
0x18002280d  cmp     [r8+4], r10d
0x180022811  jz      short loc_18002283F
0x180022813  movsxd  rdx, dword ptr [rbx+18h]
0x180022817  mov     ecx, edi
0x180022819  movsxd  rax, dword ptr [r8+4]
0x18002281d  add     rax, rbx
0x180022820  movups  xmm0, xmmword ptr [rdx+rax]
0x180022824  movups  xmmword ptr [rdi+rsi], xmm0
0x180022828  mov     eax, [rdx+rax+10h]
0x18002282c  mov     [rdi+rsi+10h], eax
0x180022830  mov     rax, [r15+10h]
0x180022834  sub     ecx, [rax+18h]
0x180022837  mov     [r9+rsi+4], ecx
0x18002283c  add     edi, 14h
0x18002283f  cmp     [r8+8], r10d
0x180022843  jz      short loc_180022871
0x180022845  movsxd  rdx, dword ptr [rbx+18h]
0x180022849  mov     ecx, edi
0x18002284b  movsxd  rax, dword ptr [r8+8]
0x18002284f  add     rax, rbx
0x180022852  movups  xmm0, xmmword ptr [rdx+rax]
0x180022856  movups  xmmword ptr [rdi+rsi], xmm0
0x18002285a  mov     eax, [rdx+rax+10h]
0x18002285e  mov     [rdi+rsi+10h], eax
0x180022862  mov     rax, [r15+10h]
0x180022866  sub     ecx, [rax+18h]
0x180022869  mov     [r9+rsi+8], ecx
0x18002286e  add     edi, 14h
0x180022871  cmp     [rbx+28h], r10d
0x180022875  jnz     loc_1800229A4
0x18002287b  mov     rax, [r15+10h]
0x18002287f  mov     [rax+28h], r10d
0x180022883  test    r14, r14
0x180022886  jz      short loc_1800228B6
0x180022888  test    dword ptr [rbx+30h], 8000000h
0x18002288f  jnz     loc_180022A5F
0x180022895  mov     ebx, dword ptr [rsp+78h+Size]
0x18002289c  mov     rdx, r14; Src
0x18002289f  movsxd  rcx, edi
0x1800228a2  mov     r8d, ebx; Size
0x1800228a5  add     rcx, rsi; void *
0x1800228a8  call    memcpy_0
0x1800228ad  mov     rax, [r15+10h]
0x1800228b1  mov     [rax+8], edi
0x1800228b4  add     edi, ebx
0x1800228b6  test    r13, r13
0x1800228b9  jz      short loc_1800228DC
0x1800228bb  mov     ebx, dword ptr [rsp+78h+arg_8]
0x1800228c2  mov     rdx, r13; Src
0x1800228c5  movsxd  rcx, edi
0x1800228c8  mov     r8d, ebx; Size
0x1800228cb  add     rcx, rsi; void *
0x1800228ce  call    memcpy_0
0x1800228d3  mov     rax, [r15+10h]
0x1800228d7  mov     [rax+0Ch], edi
0x1800228da  add     edi, ebx
0x1800228dc  mov     rdx, [rsp+78h+Src]; Src
0x1800228e1  test    rdx, rdx
0x1800228e4  jz      short loc_180022904
0x1800228e6  mov     ebx, dword ptr [rsp+78h+arg_10]
0x1800228ed  movsxd  rcx, edi
0x1800228f0  mov     r8d, ebx; Size
0x1800228f3  add     rcx, rsi; void *
0x1800228f6  call    memcpy_0
0x1800228fb  mov     rax, [r15+10h]
0x1800228ff  mov     [rax+10h], edi
0x180022902  add     edi, ebx
0x180022904  test    r12, r12
0x180022907  jz      short loc_180022926
0x180022909  mov     r8d, dword ptr [rsp+78h+arg_18]; Size
0x180022911  mov     rdx, r12; Src
0x180022914  movsxd  rcx, edi
0x180022917  add     rcx, rsi; void *
0x18002291a  call    memcpy_0
0x18002291f  mov     rax, [r15+10h]
0x180022923  mov     [rax+14h], edi
0x180022926  mov     eax, 1
0x18002292b  jmp     loc_180022698
0x180022930  test    dword ptr [rdx+30h], 8000000h
0x180022937  jnz     loc_1800229C3
0x18002293d  mov     rax, rcx
0x180022940  inc     rax
0x180022943  cmp     [r14+rax*2], r10w
0x180022948  jnz     short loc_180022940
0x18002294a  lea     edx, ds:2[rax*2]
0x180022951  mov     dword ptr [rsp+78h+Size], edx
0x180022958  add     ebp, edx
0x18002295a  jmp     loc_180022645
0x18002295f  mov     rax, rcx
0x180022962  inc     rax
0x180022965  cmp     [r13+rax*2+0], r10w
0x18002296b  jnz     short loc_180022962
0x18002296d  lea     edx, ds:2[rax*2]
0x180022974  mov     dword ptr [rsp+78h+arg_8], edx
0x18002297b  add     ebp, edx
0x18002297d  jmp     loc_18002264E
0x180022982  mov     rax, rcx
0x180022985  inc     rax
0x180022988  cmp     [r9+rax*2], r10w
0x18002298d  jnz     short loc_180022985
0x18002298f  lea     edx, ds:2[rax*2]
0x180022996  mov     dword ptr [rsp+78h+arg_10], edx
0x18002299d  add     ebp, edx
0x18002299f  jmp     loc_180022657
0x1800229a4  movsxd  rax, dword ptr [rbx+28h]
0x1800229a8  movsxd  rcx, edi
0x1800229ab  movups  xmm0, xmmword ptr [rax+rbx]
0x1800229af  movdqu  xmmword ptr [rcx+rsi], xmm0
0x1800229b4  mov     rax, [r15+10h]
0x1800229b8  mov     [rax+28h], edi
0x1800229bb  add     edi, 10h
0x1800229be  jmp     loc_180022883
0x1800229c3  mov     r8, r14
0x1800229c6  mov     rdx, rcx
0x1800229c9  inc     rdx
0x1800229cc  cmp     [r8+rdx*2], r10w
0x1800229d1  jnz     short loc_1800229C9
0x1800229d3  lea     eax, [rdx+1]
0x1800229d6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800229dd  lea     ebp, [rbp+rdx*2+0]
0x1800229e1  lea     r8, [r8+rax*2]
0x1800229e5  add     ebp, 2
0x1800229e8  cmp     [r8], r10w
0x1800229ec  jnz     short loc_1800229C6
0x1800229ee  add     ebp, 2
0x1800229f1  or      rcx, rcx
0x1800229f4  jmp     loc_180022645
0x1800229f9  movups  xmm0, xmmword ptr [rax+rbx]
0x1800229fd  mov     ecx, edi
0x1800229ff  movups  xmmword ptr [rcx+rsi], xmm0
0x180022a03  movsd   xmm1, qword ptr [rax+rbx+10h]
0x180022a09  movsd   qword ptr [rcx+rsi+10h], xmm1
0x180022a0f  mov     [rdx+0C4h], edi
0x180022a15  add     edi, 18h
0x180022a18  jmp     loc_1800227AC
0x180022a1d  movups  xmm0, xmmword ptr [rax+rbx]
0x180022a21  mov     ecx, edi
0x180022a23  movups  xmmword ptr [rcx+rsi], xmm0
  ... truncated ...
```

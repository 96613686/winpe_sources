# BConfigureIFIMetrics

- ea: `0x180022a74`
- end: `0x180022f9e`
- name: `BConfigureIFIMetrics`
- size: `1322`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800224a4`
- `0x180044ce0`

## callees

- `0x180022a74`
- `0x180076660`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180022b68`
- `KERNEL32!LocalAlloc` at `0x180022b68`

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
0x180022a74  push    rbx
0x180022a76  push    rbp
0x180022a77  push    rsi
0x180022a78  push    rdi
0x180022a79  push    r12
0x180022a7b  push    r13
0x180022a7d  push    r14
0x180022a7f  push    r15
0x180022a81  sub     rsp, 38h
0x180022a85  xor     r10d, r10d
0x180022a88  mov     rbx, rdx
0x180022a8b  mov     r15, rcx
0x180022a8e  cmp     [rdx+8], r10d
0x180022a92  jz      loc_180022B98
0x180022a98  movsxd  r14, dword ptr [rdx+8]
0x180022a9c  add     r14, rdx
0x180022a9f  cmp     [rdx+0Ch], r10d
0x180022aa3  jz      loc_180022BA0
0x180022aa9  movsxd  r13, dword ptr [rdx+0Ch]
0x180022aad  add     r13, rbx
0x180022ab0  cmp     [rdx+10h], r10d
0x180022ab4  jz      loc_180022BA8
0x180022aba  movsxd  r9, dword ptr [rdx+10h]
0x180022abe  add     r9, rbx
0x180022ac1  mov     [rsp+78h+Src], r9
0x180022ac6  cmp     [rdx+14h], r10d
0x180022aca  jz      loc_180022BB0
0x180022ad0  movsxd  r12, dword ptr [rdx+14h]
0x180022ad4  add     r12, rbx
0x180022ad7  mov     dword ptr [rsp+78h+Size], r10d
0x180022adf  mov     dword ptr [rsp+78h+arg_8], r10d
0x180022ae7  mov     dword ptr [rsp+78h+arg_10], r10d
0x180022aef  mov     dword ptr [rsp+78h+arg_18], r10d
0x180022af7  cmp     [rdx+4], r10d
0x180022afb  jnz     loc_180022BB8
0x180022b01  mov     ecx, r10d
0x180022b04  mov     edi, 0C8h
0x180022b09  cmp     [rdx+28h], r10d
0x180022b0d  lea     eax, [rdi+rcx]
0x180022b10  lea     ecx, [rax+10h]
0x180022b13  cmovz   ecx, eax
0x180022b16  cmp     [rdx+18h], r10d
0x180022b1a  lea     ebp, [rcx+48h]
0x180022b1d  cmovz   ebp, ecx
0x180022b20  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180022b24  test    r14, r14
0x180022b27  jnz     loc_180022E1F
0x180022b2d  test    r13, r13
0x180022b30  jnz     loc_180022E4E
0x180022b36  test    r9, r9
0x180022b39  jnz     loc_180022E71
0x180022b3f  test    r12, r12
0x180022b42  jz      short loc_180022B61
0x180022b44  mov     rax, rcx
0x180022b47  inc     rax
0x180022b4a  cmp     [r12+rax*2], r10w
0x180022b4f  jnz     short loc_180022B47
0x180022b51  lea     eax, ds:2[rax*2]
0x180022b58  mov     dword ptr [rsp+78h+arg_18], eax
0x180022b5f  add     ebp, eax
0x180022b61  mov     edx, ebp; uBytes
0x180022b63  mov     ecx, 40h ; '@'; uFlags
0x180022b68  call    cs:__imp_LocalAlloc
0x180022b6f  nop     dword ptr [rax+rax+00h]
0x180022b74  xor     r10d, r10d
0x180022b77  mov     [r15+10h], rax
0x180022b7b  mov     rsi, rax
0x180022b7e  test    rax, rax
0x180022b81  jnz     short loc_180022BDF
0x180022b83  mov     eax, r10d
0x180022b86  add     rsp, 38h
0x180022b8a  pop     r15
0x180022b8c  pop     r14
0x180022b8e  pop     r13
0x180022b90  pop     r12
0x180022b92  pop     rdi
0x180022b93  pop     rsi
0x180022b94  pop     rbp
0x180022b95  pop     rbx
0x180022b96  retn
0x180022b98  mov     r14, r10
0x180022b9b  jmp     loc_180022A9F
0x180022ba0  mov     r13, r10
0x180022ba3  jmp     loc_180022AB0
0x180022ba8  mov     r9, r10
0x180022bab  jmp     loc_180022AC1
0x180022bb0  mov     r12, r10
0x180022bb3  jmp     loc_180022AD7
0x180022bb8  mov     eax, [rdx+0BCh]
0x180022bbe  mov     edi, 0E0h
0x180022bc3  neg     eax
0x180022bc5  sbb     ecx, ecx
0x180022bc7  and     ecx, 18h
0x180022bca  cmp     [rdx+0C4h], r10d
0x180022bd1  jz      loc_180022B09
0x180022bd7  add     ecx, 48h ; 'H'
0x180022bda  jmp     loc_180022B09
0x180022bdf  mov     r8, r10
0x180022be2  cmp     [rbx+18h], r10d
0x180022be6  jz      short loc_180022BEF
0x180022be8  movsxd  r8, dword ptr [rbx+18h]
0x180022bec  add     r8, rbx
0x180022bef  and     dword ptr [r15+0Ch], 0FFFFFFBFh
0x180022bf4  movups  xmm0, xmmword ptr [rbx]
0x180022bf7  movups  xmmword ptr [rax], xmm0
0x180022bfa  movups  xmm1, xmmword ptr [rbx+10h]
0x180022bfe  movups  xmmword ptr [rax+10h], xmm1
0x180022c02  movups  xmm0, xmmword ptr [rbx+20h]
0x180022c06  movups  xmmword ptr [rax+20h], xmm0
0x180022c0a  movups  xmm1, xmmword ptr [rbx+30h]
0x180022c0e  movups  xmmword ptr [rax+30h], xmm1
0x180022c12  movups  xmm0, xmmword ptr [rbx+40h]
0x180022c16  movups  xmmword ptr [rax+40h], xmm0
0x180022c1a  movups  xmm1, xmmword ptr [rbx+50h]
0x180022c1e  movups  xmmword ptr [rax+50h], xmm1
0x180022c22  movups  xmm0, xmmword ptr [rbx+60h]
0x180022c26  movups  xmmword ptr [rax+60h], xmm0
0x180022c2a  movups  xmm1, xmmword ptr [rbx+70h]
0x180022c2e  movups  xmmword ptr [rax+70h], xmm1
0x180022c32  movups  xmm0, xmmword ptr [rbx+80h]
0x180022c39  movups  xmmword ptr [rax+80h], xmm0
0x180022c40  movups  xmm1, xmmword ptr [rbx+90h]
0x180022c47  movups  xmmword ptr [rax+90h], xmm1
0x180022c4e  movups  xmm0, xmmword ptr [rbx+0A0h]
0x180022c55  movups  xmmword ptr [rax+0A0h], xmm0
0x180022c5c  movups  xmm1, xmmword ptr [rbx+0B0h]
0x180022c63  movups  xmmword ptr [rax+0B0h], xmm1
0x180022c6a  cmp     [rbx+4], r10d
0x180022c6e  jz      short loc_180022CB1
0x180022c70  mov     eax, [rbx+0B8h]
0x180022c76  mov     rdx, [r15+10h]
0x180022c7a  mov     [rdx+0C0h], eax
0x180022c80  mov     eax, [rbx+0C0h]
0x180022c86  mov     [rdx+0C8h], eax
0x180022c8c  movsxd  rax, dword ptr [rbx+0BCh]
0x180022c93  test    eax, eax
0x180022c95  jnz     loc_180022EE8
0x180022c9b  movsxd  rax, dword ptr [rbx+0C4h]
0x180022ca2  test    eax, eax
0x180022ca4  jnz     loc_180022F0C
0x180022caa  mov     [rdx+0D0h], r10d
0x180022cb1  mov     rax, [r15+10h]
0x180022cb5  mov     [rax], ebp
0x180022cb7  test    r8, r8
0x180022cba  jz      loc_180022D60
0x180022cc0  mov     rax, [r15+10h]
0x180022cc4  mov     r9d, edi
0x180022cc7  mov     [rax+18h], edi
0x180022cca  add     edi, 0Ch
0x180022ccd  cmp     [r8], r10d
0x180022cd0  jz      short loc_180022CFC
0x180022cd2  movsxd  rdx, dword ptr [rbx+18h]
0x180022cd6  mov     ecx, edi
0x180022cd8  movsxd  rax, dword ptr [r8]
0x180022cdb  add     rax, rbx
0x180022cde  movups  xmm0, xmmword ptr [rdx+rax]
0x180022ce2  movups  xmmword ptr [rdi+rsi], xmm0
0x180022ce6  mov     eax, [rdx+rax+10h]
0x180022cea  mov     [rdi+rsi+10h], eax
0x180022cee  mov     rax, [r15+10h]
0x180022cf2  sub     ecx, [rax+18h]
0x180022cf5  mov     [r9+rsi], ecx
0x180022cf9  add     edi, 14h
0x180022cfc  cmp     [r8+4], r10d
0x180022d00  jz      short loc_180022D2E
0x180022d02  movsxd  rdx, dword ptr [rbx+18h]
0x180022d06  mov     ecx, edi
0x180022d08  movsxd  rax, dword ptr [r8+4]
0x180022d0c  add     rax, rbx
0x180022d0f  movups  xmm0, xmmword ptr [rdx+rax]
0x180022d13  movups  xmmword ptr [rdi+rsi], xmm0
0x180022d17  mov     eax, [rdx+rax+10h]
0x180022d1b  mov     [rdi+rsi+10h], eax
0x180022d1f  mov     rax, [r15+10h]
0x180022d23  sub     ecx, [rax+18h]
0x180022d26  mov     [r9+rsi+4], ecx
0x180022d2b  add     edi, 14h
0x180022d2e  cmp     [r8+8], r10d
0x180022d32  jz      short loc_180022D60
0x180022d34  movsxd  rdx, dword ptr [rbx+18h]
0x180022d38  mov     ecx, edi
0x180022d3a  movsxd  rax, dword ptr [r8+8]
0x180022d3e  add     rax, rbx
0x180022d41  movups  xmm0, xmmword ptr [rdx+rax]
0x180022d45  movups  xmmword ptr [rdi+rsi], xmm0
0x180022d49  mov     eax, [rdx+rax+10h]
0x180022d4d  mov     [rdi+rsi+10h], eax
0x180022d51  mov     rax, [r15+10h]
0x180022d55  sub     ecx, [rax+18h]
0x180022d58  mov     [r9+rsi+8], ecx
0x180022d5d  add     edi, 14h
0x180022d60  cmp     [rbx+28h], r10d
0x180022d64  jnz     loc_180022E93
0x180022d6a  mov     rax, [r15+10h]
0x180022d6e  mov     [rax+28h], r10d
0x180022d72  test    r14, r14
0x180022d75  jz      short loc_180022DA5
0x180022d77  test    dword ptr [rbx+30h], 8000000h
0x180022d7e  jnz     loc_180022F4E
0x180022d84  mov     ebx, dword ptr [rsp+78h+Size]
0x180022d8b  mov     rdx, r14; Src
0x180022d8e  movsxd  rcx, edi
0x180022d91  mov     r8d, ebx; Size
0x180022d94  add     rcx, rsi; void *
0x180022d97  call    memcpy_0
0x180022d9c  mov     rax, [r15+10h]
0x180022da0  mov     [rax+8], edi
0x180022da3  add     edi, ebx
0x180022da5  test    r13, r13
0x180022da8  jz      short loc_180022DCB
0x180022daa  mov     ebx, dword ptr [rsp+78h+arg_8]
0x180022db1  mov     rdx, r13; Src
0x180022db4  movsxd  rcx, edi
0x180022db7  mov     r8d, ebx; Size
0x180022dba  add     rcx, rsi; void *
0x180022dbd  call    memcpy_0
0x180022dc2  mov     rax, [r15+10h]
0x180022dc6  mov     [rax+0Ch], edi
0x180022dc9  add     edi, ebx
0x180022dcb  mov     rdx, [rsp+78h+Src]; Src
0x180022dd0  test    rdx, rdx
0x180022dd3  jz      short loc_180022DF3
0x180022dd5  mov     ebx, dword ptr [rsp+78h+arg_10]
0x180022ddc  movsxd  rcx, edi
0x180022ddf  mov     r8d, ebx; Size
0x180022de2  add     rcx, rsi; void *
0x180022de5  call    memcpy_0
0x180022dea  mov     rax, [r15+10h]
0x180022dee  mov     [rax+10h], edi
0x180022df1  add     edi, ebx
0x180022df3  test    r12, r12
0x180022df6  jz      short loc_180022E15
0x180022df8  mov     r8d, dword ptr [rsp+78h+arg_18]; Size
0x180022e00  mov     rdx, r12; Src
0x180022e03  movsxd  rcx, edi
0x180022e06  add     rcx, rsi; void *
0x180022e09  call    memcpy_0
0x180022e0e  mov     rax, [r15+10h]
0x180022e12  mov     [rax+14h], edi
0x180022e15  mov     eax, 1
0x180022e1a  jmp     loc_180022B86
0x180022e1f  test    dword ptr [rdx+30h], 8000000h
0x180022e26  jnz     loc_180022EB2
0x180022e2c  mov     rax, rcx
0x180022e2f  inc     rax
0x180022e32  cmp     [r14+rax*2], r10w
0x180022e37  jnz     short loc_180022E2F
0x180022e39  lea     edx, ds:2[rax*2]
0x180022e40  mov     dword ptr [rsp+78h+Size], edx
0x180022e47  add     ebp, edx
0x180022e49  jmp     loc_180022B2D
0x180022e4e  mov     rax, rcx
0x180022e51  inc     rax
0x180022e54  cmp     [r13+rax*2+0], r10w
0x180022e5a  jnz     short loc_180022E51
0x180022e5c  lea     edx, ds:2[rax*2]
0x180022e63  mov     dword ptr [rsp+78h+arg_8], edx
0x180022e6a  add     ebp, edx
0x180022e6c  jmp     loc_180022B36
0x180022e71  mov     rax, rcx
0x180022e74  inc     rax
0x180022e77  cmp     [r9+rax*2], r10w
0x180022e7c  jnz     short loc_180022E74
0x180022e7e  lea     edx, ds:2[rax*2]
0x180022e85  mov     dword ptr [rsp+78h+arg_10], edx
0x180022e8c  add     ebp, edx
0x180022e8e  jmp     loc_180022B3F
0x180022e93  movsxd  rax, dword ptr [rbx+28h]
0x180022e97  movsxd  rcx, edi
0x180022e9a  movups  xmm0, xmmword ptr [rax+rbx]
0x180022e9e  movdqu  xmmword ptr [rcx+rsi], xmm0
0x180022ea3  mov     rax, [r15+10h]
0x180022ea7  mov     [rax+28h], edi
0x180022eaa  add     edi, 10h
0x180022ead  jmp     loc_180022D72
0x180022eb2  mov     r8, r14
0x180022eb5  mov     rdx, rcx
0x180022eb8  inc     rdx
0x180022ebb  cmp     [r8+rdx*2], r10w
0x180022ec0  jnz     short loc_180022EB8
0x180022ec2  lea     eax, [rdx+1]
0x180022ec5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022ecc  lea     ebp, [rbp+rdx*2+0]
0x180022ed0  lea     r8, [r8+rax*2]
0x180022ed4  add     ebp, 2
0x180022ed7  cmp     [r8], r10w
0x180022edb  jnz     short loc_180022EB5
0x180022edd  add     ebp, 2
0x180022ee0  or      rcx, rcx
0x180022ee3  jmp     loc_180022B2D
0x180022ee8  movups  xmm0, xmmword ptr [rax+rbx]
0x180022eec  mov     ecx, edi
0x180022eee  movups  xmmword ptr [rcx+rsi], xmm0
0x180022ef2  movsd   xmm1, qword ptr [rax+rbx+10h]
0x180022ef8  movsd   qword ptr [rcx+rsi+10h], xmm1
0x180022efe  mov     [rdx+0C4h], edi
0x180022f04  add     edi, 18h
0x180022f07  jmp     loc_180022C9B
0x180022f0c  movups  xmm0, xmmword ptr [rax+rbx]
0x180022f10  mov     ecx, edi
  ... truncated ...
```

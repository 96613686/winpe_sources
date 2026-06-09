# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000b4e0`
- end: `0x14000b7ba`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ad84`

## callees

- `0x14000b4e0`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // edx
  unsigned __int32 v9; // ett
  int v10; // ecx
  signed __int32 v11; // edx
  int v12; // ebx
  signed __int32 v13; // r9d
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  BOOL v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r8d
  signed __int32 v22; // eax
  signed __int32 v23; // edx
  BOOL v24; // ebp
  unsigned int v25; // eax
  int v26; // r9d
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  signed __int32 v29; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v23 = *a2;
      v24 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v25 = v23 | 1;
        if ( (((v23 | 1u) >> 14) & 1) != v24 )
        {
          if ( ((v25 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v25 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v25 = v23 & 0xFFFFC01E | 1;
          }
          v26 = 0;
          if ( a3 == 4 )
            v26 = 0x4000;
          v25 = v25 & 0xFFFFBFFF | v26;
        }
        v27 = (v25 >> 5) & 0x1FF;
        v28 = v27 + 1;
        if ( v27 + 1 > 0x1FF || v28 < v27 )
        {
          LOWORD(v28) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v27;
        }
        v29 = _InterlockedCompareExchange(
                a2,
                v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v28)) & 0x3FE0,
                v23);
        if ( v23 == v29 )
          break;
        v23 = v29;
      }
      *(_DWORD *)a1 = (v23 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v15 = *a2;
      v16 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v17 = v15 | 1;
        if ( (((v15 | 1u) >> 22) & 1) != v16 )
        {
          if ( ((v17 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v17 >> 15) & 0x7F;
            v18 = 5;
            if ( a3 != 1 )
              v18 = 1;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v19 = 0;
          if ( a3 == 5 )
            v19 = 0x400000;
          v17 = v17 & 0xFFBFFFFF | v19;
        }
        v20 = (v17 >> 15) & 0x7F;
        v21 = v20 + 1;
        if ( v20 + 1 > 0x7F || v21 < v20 )
        {
          v21 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v20;
        }
        v22 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v21 << 15)) & 0x3F8000, v15);
        if ( v15 == v22 )
          break;
        v15 = v22;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v6 = a3 - 320;
    if ( v6 >= 64 )
      goto LABEL_16;
    v7 = *((_DWORD *)a2 + 1);
    do
    {
      v8 = (v7 & 0x10) != 0 && ((v7 >> 5) & 0x3F) == v6;
      *(_DWORD *)(a1 + 16) = v8;
      v9 = v7;
      v7 = _InterlockedCompareExchange(
             a2 + 1,
             v7 ^ ((unsigned __int16)v7 ^ (unsigned __int16)(32 * v6)) & 0x7E0 | 0x10,
             v7);
    }
    while ( v9 != v7 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v10 = 0;
  switch ( a3 )
  {
    case 2:
      v10 = 2;
      break;
    case 3:
      v10 = 8;
      break;
    case 6:
      v10 = 4;
      break;
    case 7:
      v10 = 16;
      break;
  }
  v11 = *a2;
  v12 = 1;
  while ( 1 )
  {
    v13 = v11 | v10 | 1;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    if ( (v11 | v10) == v11 )
      v13 = v11 | v10;
    v14 = _InterlockedCompareExchange(a2, v13, v11);
    if ( v11 == v14 )
      break;
    v11 = v14;
  }
  if ( (v13 & 1) == 0 || (v11 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x14000b4e0  push    rbx
0x14000b4e2  push    rbp
0x14000b4e3  push    rsi
0x14000b4e4  push    rdi
0x14000b4e5  xor     eax, eax
0x14000b4e7  xorps   xmm0, xmm0
0x14000b4ea  mov     r11d, r8d
0x14000b4ed  mov     rsi, rdx
0x14000b4f0  mov     r10, rcx
0x14000b4f3  mov     r9d, r8d
0x14000b4f6  movups  xmmword ptr [rcx], xmm0
0x14000b4f9  mov     [rcx+10h], rax
0x14000b4fd  test    r8d, r8d
0x14000b500  jz      loc_14000B6E4
0x14000b506  sub     r9d, 1
0x14000b50a  jz      loc_14000B62B
0x14000b510  sub     r9d, 1
0x14000b514  jz      loc_14000B5B2
0x14000b51a  sub     r9d, 1
0x14000b51e  jz      loc_14000B5B2
0x14000b524  sub     r9d, 1
0x14000b528  jz      loc_14000B6E4
0x14000b52e  sub     r9d, 1
0x14000b532  jz      loc_14000B62B
0x14000b538  sub     r9d, 1
0x14000b53c  jz      short loc_14000B5B2
0x14000b53e  cmp     r9d, 1
0x14000b542  jz      short loc_14000B5B2
0x14000b544  add     r8d, 0FFFFFEC0h
0x14000b54b  lea     ebx, [rax+1]
0x14000b54e  cmp     r8d, 40h ; '@'
0x14000b552  jge     short loc_14000B59D
0x14000b554  mov     eax, [rdx+4]
0x14000b557  lea     ecx, [rbx+0Fh]
0x14000b55a  mov     r9d, r8d
0x14000b55d  shl     r9d, 5
0x14000b561  test    cl, al
0x14000b563  jz      short loc_14000B576
0x14000b565  mov     edx, eax
0x14000b567  shr     edx, 5
0x14000b56a  and     edx, 3Fh
0x14000b56d  cmp     edx, r8d
0x14000b570  jnz     short loc_14000B576
0x14000b572  mov     edx, ebx
0x14000b574  jmp     short loc_14000B578
0x14000b576  xor     edx, edx
0x14000b578  mov     [r10+10h], edx
0x14000b57c  mov     edx, r9d
0x14000b57f  xor     edx, eax
0x14000b581  and     edx, 7E0h
0x14000b587  xor     edx, eax
0x14000b589  or      edx, ecx
0x14000b58b  lock cmpxchg [rsi+4], edx
0x14000b590  jnz     short loc_14000B561
0x14000b592  cmp     dword ptr [r10+10h], 0
0x14000b597  jnz     loc_14000B7B2
0x14000b59d  mov     [r10+8], r11d
0x14000b5a1  mov     [r10+4], ebx
0x14000b5a5  mov     dword ptr [r10+0Ch], 0
0x14000b5ad  jmp     loc_14000B7B2
0x14000b5b2  xor     ecx, ecx
0x14000b5b4  sub     r11d, 2
0x14000b5b8  jz      short loc_14000B5E0
0x14000b5ba  sub     r11d, 1
0x14000b5be  jz      short loc_14000B5D9
0x14000b5c0  sub     r11d, 3
0x14000b5c4  jz      short loc_14000B5D2
0x14000b5c6  cmp     r11d, 1
0x14000b5ca  jnz     short loc_14000B5E5
0x14000b5cc  lea     ecx, [r11+0Fh]
0x14000b5d0  jmp     short loc_14000B5E5
0x14000b5d2  mov     ecx, 4
0x14000b5d7  jmp     short loc_14000B5E5
0x14000b5d9  mov     ecx, 8
0x14000b5de  jmp     short loc_14000B5E5
0x14000b5e0  mov     ecx, 2
0x14000b5e5  mov     edx, [rdx]
0x14000b5e7  mov     ebx, 1
0x14000b5ec  xor     eax, eax
0x14000b5ee  mov     r8d, ecx
0x14000b5f1  or      r8d, edx
0x14000b5f4  cmp     r8d, edx
0x14000b5f7  mov     r9d, r8d
0x14000b5fa  setz    al
0x14000b5fd  or      r9d, ebx
0x14000b600  cmp     r8d, edx
0x14000b603  mov     [r10+10h], eax
0x14000b607  mov     eax, edx
0x14000b609  cmovz   r9d, r8d
0x14000b60d  lock cmpxchg [rsi], r9d
0x14000b612  jz      short loc_14000B618
0x14000b614  mov     edx, eax
0x14000b616  jmp     short loc_14000B5EC
0x14000b618  test    bl, r9b
0x14000b61b  jz      short loc_14000B621
0x14000b61d  test    bl, dl
0x14000b61f  jz      short loc_14000B623
0x14000b621  xor     ebx, ebx
0x14000b623  mov     [r10], ebx
0x14000b626  jmp     loc_14000B7B2
0x14000b62b  mov     ecx, [rdx]
0x14000b62d  xor     r9d, r9d
0x14000b630  cmp     r11d, 5
0x14000b634  mov     ebx, 1
0x14000b639  setz    r9b
0x14000b63d  mov     eax, ecx
0x14000b63f  mov     dword ptr [r10+4], 0
0x14000b647  or      eax, ebx
0x14000b649  mov     edx, eax
0x14000b64b  shr     edx, 16h
0x14000b64e  and     edx, ebx
0x14000b650  cmp     edx, r9d
0x14000b653  jz      short loc_14000B695
0x14000b655  mov     r8d, eax
0x14000b658  shr     r8d, 0Fh
0x14000b65c  and     r8d, 7Fh
0x14000b660  jbe     short loc_14000B67A
0x14000b662  cmp     r11d, ebx
0x14000b665  mov     [r10+4], r8d
0x14000b669  mov     edx, 5
0x14000b66e  cmovnz  edx, ebx
0x14000b671  and     eax, 0FFC07FFFh
0x14000b676  mov     [r10+8], edx
0x14000b67a  xor     r8d, r8d
0x14000b67d  mov     edx, 400000h
0x14000b682  cmp     r11d, 5
0x14000b686  cmovz   r8d, edx
0x14000b68a  mov     edx, eax
0x14000b68c  btr     edx, 16h
0x14000b690  mov     eax, r8d
0x14000b693  or      eax, edx
0x14000b695  mov     edx, eax
0x14000b697  shr     edx, 0Fh
0x14000b69a  and     edx, 7Fh
0x14000b69d  lea     r8d, [rdx+1]
0x14000b6a1  cmp     r8d, 7Fh
0x14000b6a5  ja      short loc_14000B6AC
0x14000b6a7  cmp     r8d, edx
0x14000b6aa  jnb     short loc_14000B6B7
0x14000b6ac  mov     r8d, ebx
0x14000b6af  mov     [r10+8], r11d
0x14000b6b3  mov     [r10+4], edx
0x14000b6b7  shl     r8d, 0Fh
0x14000b6bb  xor     r8d, eax
0x14000b6be  and     r8d, 3F8000h
0x14000b6c5  xor     r8d, eax
0x14000b6c8  mov     eax, ecx
0x14000b6ca  lock cmpxchg [rsi], r8d
0x14000b6cf  jz      short loc_14000B6D8
0x14000b6d1  mov     ecx, eax
0x14000b6d3  jmp     loc_14000B63D
0x14000b6d8  not     ecx
0x14000b6da  and     ecx, ebx
0x14000b6dc  mov     [r10], ecx
0x14000b6df  jmp     loc_14000B7AA
0x14000b6e4  mov     edx, [rdx]
0x14000b6e6  xor     ebp, ebp
0x14000b6e8  lea     ecx, [rbp+4]
0x14000b6eb  cmp     r11d, ecx
0x14000b6ee  lea     ebx, [rcx-3]
0x14000b6f1  setz    bpl
0x14000b6f5  mov     eax, edx
0x14000b6f7  mov     dword ptr [r10+4], 0
0x14000b6ff  or      eax, ebx
0x14000b701  mov     r8d, eax
0x14000b704  shr     r8d, 0Eh
0x14000b708  and     r8d, ebx
0x14000b70b  cmp     r8d, ebp
0x14000b70e  jz      short loc_14000B757
0x14000b710  mov     edi, eax
0x14000b712  shr     edi, 5
0x14000b715  and     edi, 1FFh
0x14000b71b  jbe     short loc_14000B739
0x14000b71d  mov     r8d, r11d
0x14000b720  mov     [r10+4], edi
0x14000b724  neg     r8d
0x14000b727  sbb     r9d, r9d
0x14000b72a  not     r9d
0x14000b72d  and     r9d, ecx
0x14000b730  mov     [r10+8], r9d
0x14000b734  and     eax, 0FFFFC01Fh
0x14000b739  xor     r9d, r9d
0x14000b73c  mov     r8d, 4000h
0x14000b742  cmp     r11d, ecx
0x14000b745  cmovz   r9d, r8d
0x14000b749  mov     r8d, eax
0x14000b74c  btr     r8d, 0Eh
0x14000b751  mov     eax, r9d
0x14000b754  or      eax, r8d
0x14000b757  mov     r8d, eax
0x14000b75a  shr     r8d, 5
0x14000b75e  and     r8d, 1FFh
0x14000b765  lea     r9d, [r8+1]
0x14000b769  cmp     r9d, 1FFh
0x14000b770  ja      short loc_14000B777
0x14000b772  cmp     r9d, r8d
0x14000b775  jnb     short loc_14000B782
0x14000b777  mov     r9d, ebx
0x14000b77a  mov     [r10+8], r11d
0x14000b77e  mov     [r10+4], r8d
0x14000b782  shl     r9d, 5
0x14000b786  xor     r9d, eax
0x14000b789  and     r9d, 3FE0h
0x14000b790  xor     r9d, eax
0x14000b793  mov     eax, edx
0x14000b795  lock cmpxchg [rsi], r9d
0x14000b79a  jz      short loc_14000B7A3
0x14000b79c  mov     edx, eax
0x14000b79e  jmp     loc_14000B6F5
0x14000b7a3  not     edx
0x14000b7a5  and     edx, ebx
0x14000b7a7  mov     [r10], edx
0x14000b7aa  mov     dword ptr [r10+10h], 0
0x14000b7b2  mov     rax, r10
0x14000b7b5  pop     rdi
0x14000b7b6  pop     rsi
0x14000b7b7  pop     rbp
0x14000b7b8  pop     rbx
0x14000b7b9  retn
```

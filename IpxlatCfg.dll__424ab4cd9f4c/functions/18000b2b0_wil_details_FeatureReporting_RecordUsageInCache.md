# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000b2b0`
- end: `0x18000b58a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ae4c`

## callees

- `0x18000b2b0`

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
0x18000b2b0  push    rbx
0x18000b2b2  push    rbp
0x18000b2b3  push    rsi
0x18000b2b4  push    rdi
0x18000b2b5  xor     eax, eax
0x18000b2b7  xorps   xmm0, xmm0
0x18000b2ba  mov     r11d, r8d
0x18000b2bd  mov     rsi, rdx
0x18000b2c0  mov     r10, rcx
0x18000b2c3  mov     r9d, r8d
0x18000b2c6  movups  xmmword ptr [rcx], xmm0
0x18000b2c9  mov     [rcx+10h], rax
0x18000b2cd  test    r8d, r8d
0x18000b2d0  jz      loc_18000B4B4
0x18000b2d6  sub     r9d, 1
0x18000b2da  jz      loc_18000B3FB
0x18000b2e0  sub     r9d, 1
0x18000b2e4  jz      loc_18000B382
0x18000b2ea  sub     r9d, 1
0x18000b2ee  jz      loc_18000B382
0x18000b2f4  sub     r9d, 1
0x18000b2f8  jz      loc_18000B4B4
0x18000b2fe  sub     r9d, 1
0x18000b302  jz      loc_18000B3FB
0x18000b308  sub     r9d, 1
0x18000b30c  jz      short loc_18000B382
0x18000b30e  cmp     r9d, 1
0x18000b312  jz      short loc_18000B382
0x18000b314  add     r8d, 0FFFFFEC0h
0x18000b31b  lea     ebx, [rax+1]
0x18000b31e  cmp     r8d, 40h ; '@'
0x18000b322  jge     short loc_18000B36D
0x18000b324  mov     eax, [rdx+4]
0x18000b327  lea     ecx, [rbx+0Fh]
0x18000b32a  mov     r9d, r8d
0x18000b32d  shl     r9d, 5
0x18000b331  test    cl, al
0x18000b333  jz      short loc_18000B346
0x18000b335  mov     edx, eax
0x18000b337  shr     edx, 5
0x18000b33a  and     edx, 3Fh
0x18000b33d  cmp     edx, r8d
0x18000b340  jnz     short loc_18000B346
0x18000b342  mov     edx, ebx
0x18000b344  jmp     short loc_18000B348
0x18000b346  xor     edx, edx
0x18000b348  mov     [r10+10h], edx
0x18000b34c  mov     edx, r9d
0x18000b34f  xor     edx, eax
0x18000b351  and     edx, 7E0h
0x18000b357  xor     edx, eax
0x18000b359  or      edx, ecx
0x18000b35b  lock cmpxchg [rsi+4], edx
0x18000b360  jnz     short loc_18000B331
0x18000b362  cmp     dword ptr [r10+10h], 0
0x18000b367  jnz     loc_18000B582
0x18000b36d  mov     [r10+8], r11d
0x18000b371  mov     [r10+4], ebx
0x18000b375  mov     dword ptr [r10+0Ch], 0
0x18000b37d  jmp     loc_18000B582
0x18000b382  xor     ecx, ecx
0x18000b384  sub     r11d, 2
0x18000b388  jz      short loc_18000B3B0
0x18000b38a  sub     r11d, 1
0x18000b38e  jz      short loc_18000B3A9
0x18000b390  sub     r11d, 3
0x18000b394  jz      short loc_18000B3A2
0x18000b396  cmp     r11d, 1
0x18000b39a  jnz     short loc_18000B3B5
0x18000b39c  lea     ecx, [r11+0Fh]
0x18000b3a0  jmp     short loc_18000B3B5
0x18000b3a2  mov     ecx, 4
0x18000b3a7  jmp     short loc_18000B3B5
0x18000b3a9  mov     ecx, 8
0x18000b3ae  jmp     short loc_18000B3B5
0x18000b3b0  mov     ecx, 2
0x18000b3b5  mov     edx, [rdx]
0x18000b3b7  mov     ebx, 1
0x18000b3bc  xor     eax, eax
0x18000b3be  mov     r8d, ecx
0x18000b3c1  or      r8d, edx
0x18000b3c4  cmp     r8d, edx
0x18000b3c7  mov     r9d, r8d
0x18000b3ca  setz    al
0x18000b3cd  or      r9d, ebx
0x18000b3d0  cmp     r8d, edx
0x18000b3d3  mov     [r10+10h], eax
0x18000b3d7  mov     eax, edx
0x18000b3d9  cmovz   r9d, r8d
0x18000b3dd  lock cmpxchg [rsi], r9d
0x18000b3e2  jz      short loc_18000B3E8
0x18000b3e4  mov     edx, eax
0x18000b3e6  jmp     short loc_18000B3BC
0x18000b3e8  test    bl, r9b
0x18000b3eb  jz      short loc_18000B3F1
0x18000b3ed  test    bl, dl
0x18000b3ef  jz      short loc_18000B3F3
0x18000b3f1  xor     ebx, ebx
0x18000b3f3  mov     [r10], ebx
0x18000b3f6  jmp     loc_18000B582
0x18000b3fb  mov     ecx, [rdx]
0x18000b3fd  xor     r9d, r9d
0x18000b400  cmp     r11d, 5
0x18000b404  mov     ebx, 1
0x18000b409  setz    r9b
0x18000b40d  mov     eax, ecx
0x18000b40f  mov     dword ptr [r10+4], 0
0x18000b417  or      eax, ebx
0x18000b419  mov     edx, eax
0x18000b41b  shr     edx, 16h
0x18000b41e  and     edx, ebx
0x18000b420  cmp     edx, r9d
0x18000b423  jz      short loc_18000B465
0x18000b425  mov     r8d, eax
0x18000b428  shr     r8d, 0Fh
0x18000b42c  and     r8d, 7Fh
0x18000b430  jbe     short loc_18000B44A
0x18000b432  cmp     r11d, ebx
0x18000b435  mov     [r10+4], r8d
0x18000b439  mov     edx, 5
0x18000b43e  cmovnz  edx, ebx
0x18000b441  and     eax, 0FFC07FFFh
0x18000b446  mov     [r10+8], edx
0x18000b44a  xor     r8d, r8d
0x18000b44d  mov     edx, 400000h
0x18000b452  cmp     r11d, 5
0x18000b456  cmovz   r8d, edx
0x18000b45a  mov     edx, eax
0x18000b45c  btr     edx, 16h
0x18000b460  mov     eax, r8d
0x18000b463  or      eax, edx
0x18000b465  mov     edx, eax
0x18000b467  shr     edx, 0Fh
0x18000b46a  and     edx, 7Fh
0x18000b46d  lea     r8d, [rdx+1]
0x18000b471  cmp     r8d, 7Fh
0x18000b475  ja      short loc_18000B47C
0x18000b477  cmp     r8d, edx
0x18000b47a  jnb     short loc_18000B487
0x18000b47c  mov     r8d, ebx
0x18000b47f  mov     [r10+8], r11d
0x18000b483  mov     [r10+4], edx
0x18000b487  shl     r8d, 0Fh
0x18000b48b  xor     r8d, eax
0x18000b48e  and     r8d, 3F8000h
0x18000b495  xor     r8d, eax
0x18000b498  mov     eax, ecx
0x18000b49a  lock cmpxchg [rsi], r8d
0x18000b49f  jz      short loc_18000B4A8
0x18000b4a1  mov     ecx, eax
0x18000b4a3  jmp     loc_18000B40D
0x18000b4a8  not     ecx
0x18000b4aa  and     ecx, ebx
0x18000b4ac  mov     [r10], ecx
0x18000b4af  jmp     loc_18000B57A
0x18000b4b4  mov     edx, [rdx]
0x18000b4b6  xor     ebp, ebp
0x18000b4b8  lea     ecx, [rbp+4]
0x18000b4bb  cmp     r11d, ecx
0x18000b4be  lea     ebx, [rcx-3]
0x18000b4c1  setz    bpl
0x18000b4c5  mov     eax, edx
0x18000b4c7  mov     dword ptr [r10+4], 0
0x18000b4cf  or      eax, ebx
0x18000b4d1  mov     r8d, eax
0x18000b4d4  shr     r8d, 0Eh
0x18000b4d8  and     r8d, ebx
0x18000b4db  cmp     r8d, ebp
0x18000b4de  jz      short loc_18000B527
0x18000b4e0  mov     edi, eax
0x18000b4e2  shr     edi, 5
0x18000b4e5  and     edi, 1FFh
0x18000b4eb  jbe     short loc_18000B509
0x18000b4ed  mov     r8d, r11d
0x18000b4f0  mov     [r10+4], edi
0x18000b4f4  neg     r8d
0x18000b4f7  sbb     r9d, r9d
0x18000b4fa  not     r9d
0x18000b4fd  and     r9d, ecx
0x18000b500  mov     [r10+8], r9d
0x18000b504  and     eax, 0FFFFC01Fh
0x18000b509  xor     r9d, r9d
0x18000b50c  mov     r8d, 4000h
0x18000b512  cmp     r11d, ecx
0x18000b515  cmovz   r9d, r8d
0x18000b519  mov     r8d, eax
0x18000b51c  btr     r8d, 0Eh
0x18000b521  mov     eax, r9d
0x18000b524  or      eax, r8d
0x18000b527  mov     r8d, eax
0x18000b52a  shr     r8d, 5
0x18000b52e  and     r8d, 1FFh
0x18000b535  lea     r9d, [r8+1]
0x18000b539  cmp     r9d, 1FFh
0x18000b540  ja      short loc_18000B547
0x18000b542  cmp     r9d, r8d
0x18000b545  jnb     short loc_18000B552
0x18000b547  mov     r9d, ebx
0x18000b54a  mov     [r10+8], r11d
0x18000b54e  mov     [r10+4], r8d
0x18000b552  shl     r9d, 5
0x18000b556  xor     r9d, eax
0x18000b559  and     r9d, 3FE0h
0x18000b560  xor     r9d, eax
0x18000b563  mov     eax, edx
0x18000b565  lock cmpxchg [rsi], r9d
0x18000b56a  jz      short loc_18000B573
0x18000b56c  mov     edx, eax
0x18000b56e  jmp     loc_18000B4C5
0x18000b573  not     edx
0x18000b575  and     edx, ebx
0x18000b577  mov     [r10], edx
0x18000b57a  mov     dword ptr [r10+10h], 0
0x18000b582  mov     rax, r10
0x18000b585  pop     rdi
0x18000b586  pop     rsi
0x18000b587  pop     rbp
0x18000b588  pop     rbx
0x18000b589  retn
```

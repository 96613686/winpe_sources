# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18003b8d8`
- end: `0x18003bbab`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003bcd4`

## callees

- `0x18003b8d8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

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
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x18003b8d8  push    rbx
0x18003b8da  push    rbp
0x18003b8db  push    rsi
0x18003b8dc  push    rdi
0x18003b8dd  xor     eax, eax
0x18003b8df  xorps   xmm0, xmm0
0x18003b8e2  mov     r10, rcx
0x18003b8e5  mov     edi, r9d
0x18003b8e8  mov     r11d, r8d
0x18003b8eb  mov     rsi, rdx
0x18003b8ee  movups  xmmword ptr [rcx], xmm0
0x18003b8f1  mov     [rcx+10h], rax
0x18003b8f5  mov     ecx, r8d
0x18003b8f8  test    r8d, r8d
0x18003b8fb  jz      loc_18003BAD4
0x18003b901  sub     ecx, 1
0x18003b904  jz      loc_18003BA1B
0x18003b90a  sub     ecx, 1
0x18003b90d  jz      loc_18003B9A2
0x18003b913  sub     ecx, 1
0x18003b916  jz      loc_18003B9A2
0x18003b91c  sub     ecx, 1
0x18003b91f  jz      loc_18003BAD4
0x18003b925  sub     ecx, 1
0x18003b928  jz      loc_18003BA1B
0x18003b92e  sub     ecx, 1
0x18003b931  jz      short loc_18003B9A2
0x18003b933  cmp     ecx, 1
0x18003b936  jz      short loc_18003B9A2
0x18003b938  add     r8d, 0FFFFFEC0h
0x18003b93f  lea     ebx, [rax+1]
0x18003b942  cmp     r8d, 40h ; '@'
0x18003b946  jge     short loc_18003B991
0x18003b948  mov     eax, [rdx+4]
0x18003b94b  lea     ecx, [rbx+0Fh]
0x18003b94e  mov     r9d, r8d
0x18003b951  shl     r9d, 5
0x18003b955  test    cl, al
0x18003b957  jz      short loc_18003B96A
0x18003b959  mov     edx, eax
0x18003b95b  shr     edx, 5
0x18003b95e  and     edx, 3Fh
0x18003b961  cmp     edx, r8d
0x18003b964  jnz     short loc_18003B96A
0x18003b966  mov     edx, ebx
0x18003b968  jmp     short loc_18003B96C
0x18003b96a  xor     edx, edx
0x18003b96c  mov     [r10+10h], edx
0x18003b970  mov     edx, r9d
0x18003b973  xor     edx, eax
0x18003b975  and     edx, 7E0h
0x18003b97b  xor     edx, eax
0x18003b97d  or      edx, ecx
0x18003b97f  lock cmpxchg [rsi+4], edx
0x18003b984  jnz     short loc_18003B955
0x18003b986  cmp     dword ptr [r10+10h], 0
0x18003b98b  jnz     loc_18003BBA2
0x18003b991  mov     [r10+8], r11d
0x18003b995  mov     [r10+4], ebx
0x18003b999  mov     [r10+0Ch], edi
0x18003b99d  jmp     loc_18003BBA2
0x18003b9a2  xor     ecx, ecx
0x18003b9a4  sub     r11d, 2
0x18003b9a8  jz      short loc_18003B9D0
0x18003b9aa  sub     r11d, 1
0x18003b9ae  jz      short loc_18003B9C9
0x18003b9b0  sub     r11d, 3
0x18003b9b4  jz      short loc_18003B9C2
0x18003b9b6  cmp     r11d, 1
0x18003b9ba  jnz     short loc_18003B9D5
0x18003b9bc  lea     ecx, [r11+0Fh]
0x18003b9c0  jmp     short loc_18003B9D5
0x18003b9c2  mov     ecx, 4
0x18003b9c7  jmp     short loc_18003B9D5
0x18003b9c9  mov     ecx, 8
0x18003b9ce  jmp     short loc_18003B9D5
0x18003b9d0  mov     ecx, 2
0x18003b9d5  mov     edx, [rdx]
0x18003b9d7  mov     ebx, 1
0x18003b9dc  xor     eax, eax
0x18003b9de  mov     r8d, ecx
0x18003b9e1  or      r8d, edx
0x18003b9e4  cmp     r8d, edx
0x18003b9e7  mov     r9d, r8d
0x18003b9ea  setz    al
0x18003b9ed  or      r9d, ebx
0x18003b9f0  cmp     r8d, edx
0x18003b9f3  mov     [r10+10h], eax
0x18003b9f7  mov     eax, edx
0x18003b9f9  cmovz   r9d, r8d
0x18003b9fd  lock cmpxchg [rsi], r9d
0x18003ba02  jz      short loc_18003BA08
0x18003ba04  mov     edx, eax
0x18003ba06  jmp     short loc_18003B9DC
0x18003ba08  test    bl, r9b
0x18003ba0b  jz      short loc_18003BA11
0x18003ba0d  test    bl, dl
0x18003ba0f  jz      short loc_18003BA13
0x18003ba11  xor     ebx, ebx
0x18003ba13  mov     [r10], ebx
0x18003ba16  jmp     loc_18003BBA2
0x18003ba1b  mov     ecx, [rdx]
0x18003ba1d  xor     r9d, r9d
0x18003ba20  cmp     r11d, 5
0x18003ba24  mov     ebx, 1
0x18003ba29  setz    r9b
0x18003ba2d  mov     eax, ecx
0x18003ba2f  mov     dword ptr [r10+4], 0
0x18003ba37  or      eax, ebx
0x18003ba39  mov     edx, eax
0x18003ba3b  shr     edx, 16h
0x18003ba3e  and     edx, ebx
0x18003ba40  cmp     edx, r9d
0x18003ba43  jz      short loc_18003BA85
0x18003ba45  mov     r8d, eax
0x18003ba48  shr     r8d, 0Fh
0x18003ba4c  and     r8d, 7Fh
0x18003ba50  jbe     short loc_18003BA6A
0x18003ba52  cmp     r11d, ebx
0x18003ba55  mov     [r10+4], r8d
0x18003ba59  mov     edx, 5
0x18003ba5e  cmovnz  edx, ebx
0x18003ba61  and     eax, 0FFC07FFFh
0x18003ba66  mov     [r10+8], edx
0x18003ba6a  xor     r8d, r8d
0x18003ba6d  mov     edx, 400000h
0x18003ba72  cmp     r11d, 5
0x18003ba76  cmovz   r8d, edx
0x18003ba7a  mov     edx, eax
0x18003ba7c  btr     edx, 16h
0x18003ba80  mov     eax, r8d
0x18003ba83  or      eax, edx
0x18003ba85  mov     edx, eax
0x18003ba87  shr     edx, 0Fh
0x18003ba8a  and     edx, 7Fh
0x18003ba8d  lea     r8d, [rdx+1]
0x18003ba91  cmp     r8d, 7Fh
0x18003ba95  ja      short loc_18003BA9C
0x18003ba97  cmp     r8d, edx
0x18003ba9a  jnb     short loc_18003BAA7
0x18003ba9c  mov     r8d, ebx
0x18003ba9f  mov     [r10+8], r11d
0x18003baa3  mov     [r10+4], edx
0x18003baa7  shl     r8d, 0Fh
0x18003baab  xor     r8d, eax
0x18003baae  and     r8d, 3F8000h
0x18003bab5  xor     r8d, eax
0x18003bab8  mov     eax, ecx
0x18003baba  lock cmpxchg [rsi], r8d
0x18003babf  jz      short loc_18003BAC8
0x18003bac1  mov     ecx, eax
0x18003bac3  jmp     loc_18003BA2D
0x18003bac8  not     ecx
0x18003baca  and     ecx, ebx
0x18003bacc  mov     [r10], ecx
0x18003bacf  jmp     loc_18003BB9A
0x18003bad4  mov     edx, [rdx]
0x18003bad6  xor     ebp, ebp
0x18003bad8  lea     ecx, [rbp+4]
0x18003badb  cmp     r11d, ecx
0x18003bade  lea     ebx, [rcx-3]
0x18003bae1  setz    bpl
0x18003bae5  mov     eax, edx
0x18003bae7  mov     dword ptr [r10+4], 0
0x18003baef  or      eax, ebx
0x18003baf1  mov     r8d, eax
0x18003baf4  shr     r8d, 0Eh
0x18003baf8  and     r8d, ebx
0x18003bafb  cmp     r8d, ebp
0x18003bafe  jz      short loc_18003BB47
0x18003bb00  mov     edi, eax
0x18003bb02  shr     edi, 5
0x18003bb05  and     edi, 1FFh
0x18003bb0b  jbe     short loc_18003BB29
0x18003bb0d  mov     r8d, r11d
0x18003bb10  mov     [r10+4], edi
0x18003bb14  neg     r8d
0x18003bb17  sbb     r9d, r9d
0x18003bb1a  not     r9d
0x18003bb1d  and     r9d, ecx
0x18003bb20  mov     [r10+8], r9d
0x18003bb24  and     eax, 0FFFFC01Fh
0x18003bb29  xor     r9d, r9d
0x18003bb2c  mov     r8d, 4000h
0x18003bb32  cmp     r11d, ecx
0x18003bb35  cmovz   r9d, r8d
0x18003bb39  mov     r8d, eax
0x18003bb3c  btr     r8d, 0Eh
0x18003bb41  mov     eax, r9d
0x18003bb44  or      eax, r8d
0x18003bb47  mov     r8d, eax
0x18003bb4a  shr     r8d, 5
0x18003bb4e  and     r8d, 1FFh
0x18003bb55  lea     r9d, [r8+1]
0x18003bb59  cmp     r9d, 1FFh
0x18003bb60  ja      short loc_18003BB67
0x18003bb62  cmp     r9d, r8d
0x18003bb65  jnb     short loc_18003BB72
0x18003bb67  mov     r9d, ebx
0x18003bb6a  mov     [r10+8], r11d
0x18003bb6e  mov     [r10+4], r8d
0x18003bb72  shl     r9d, 5
0x18003bb76  xor     r9d, eax
0x18003bb79  and     r9d, 3FE0h
0x18003bb80  xor     r9d, eax
0x18003bb83  mov     eax, edx
0x18003bb85  lock cmpxchg [rsi], r9d
0x18003bb8a  jz      short loc_18003BB93
0x18003bb8c  mov     edx, eax
0x18003bb8e  jmp     loc_18003BAE5
0x18003bb93  not     edx
0x18003bb95  and     edx, ebx
0x18003bb97  mov     [r10], edx
0x18003bb9a  mov     dword ptr [r10+10h], 0
0x18003bba2  mov     rax, r10
0x18003bba5  pop     rdi
0x18003bba6  pop     rsi
0x18003bba7  pop     rbp
0x18003bba8  pop     rbx
0x18003bba9  retn
```

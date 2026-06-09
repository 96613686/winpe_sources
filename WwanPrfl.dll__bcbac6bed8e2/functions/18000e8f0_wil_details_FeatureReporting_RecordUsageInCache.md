# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000e8f0`
- end: `0x18000ebca`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007788`

## callees

- `0x18000e8f0`

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
0x18000e8f0  push    rbx
0x18000e8f2  push    rbp
0x18000e8f3  push    rsi
0x18000e8f4  push    rdi
0x18000e8f5  xor     eax, eax
0x18000e8f7  xorps   xmm0, xmm0
0x18000e8fa  mov     r11d, r8d
0x18000e8fd  mov     rsi, rdx
0x18000e900  mov     r10, rcx
0x18000e903  mov     r9d, r8d
0x18000e906  movups  xmmword ptr [rcx], xmm0
0x18000e909  mov     [rcx+10h], rax
0x18000e90d  test    r8d, r8d
0x18000e910  jz      loc_18000EAF4
0x18000e916  sub     r9d, 1
0x18000e91a  jz      loc_18000EA3B
0x18000e920  sub     r9d, 1
0x18000e924  jz      loc_18000E9C2
0x18000e92a  sub     r9d, 1
0x18000e92e  jz      loc_18000E9C2
0x18000e934  sub     r9d, 1
0x18000e938  jz      loc_18000EAF4
0x18000e93e  sub     r9d, 1
0x18000e942  jz      loc_18000EA3B
0x18000e948  sub     r9d, 1
0x18000e94c  jz      short loc_18000E9C2
0x18000e94e  cmp     r9d, 1
0x18000e952  jz      short loc_18000E9C2
0x18000e954  add     r8d, 0FFFFFEC0h
0x18000e95b  lea     ebx, [rax+1]
0x18000e95e  cmp     r8d, 40h ; '@'
0x18000e962  jge     short loc_18000E9AD
0x18000e964  mov     eax, [rdx+4]
0x18000e967  lea     ecx, [rbx+0Fh]
0x18000e96a  mov     r9d, r8d
0x18000e96d  shl     r9d, 5
0x18000e971  test    cl, al
0x18000e973  jz      short loc_18000E986
0x18000e975  mov     edx, eax
0x18000e977  shr     edx, 5
0x18000e97a  and     edx, 3Fh
0x18000e97d  cmp     edx, r8d
0x18000e980  jnz     short loc_18000E986
0x18000e982  mov     edx, ebx
0x18000e984  jmp     short loc_18000E988
0x18000e986  xor     edx, edx
0x18000e988  mov     [r10+10h], edx
0x18000e98c  mov     edx, r9d
0x18000e98f  xor     edx, eax
0x18000e991  and     edx, 7E0h
0x18000e997  xor     edx, eax
0x18000e999  or      edx, ecx
0x18000e99b  lock cmpxchg [rsi+4], edx
0x18000e9a0  jnz     short loc_18000E971
0x18000e9a2  cmp     dword ptr [r10+10h], 0
0x18000e9a7  jnz     loc_18000EBC2
0x18000e9ad  mov     [r10+8], r11d
0x18000e9b1  mov     [r10+4], ebx
0x18000e9b5  mov     dword ptr [r10+0Ch], 0
0x18000e9bd  jmp     loc_18000EBC2
0x18000e9c2  xor     ecx, ecx
0x18000e9c4  sub     r11d, 2
0x18000e9c8  jz      short loc_18000E9F0
0x18000e9ca  sub     r11d, 1
0x18000e9ce  jz      short loc_18000E9E9
0x18000e9d0  sub     r11d, 3
0x18000e9d4  jz      short loc_18000E9E2
0x18000e9d6  cmp     r11d, 1
0x18000e9da  jnz     short loc_18000E9F5
0x18000e9dc  lea     ecx, [r11+0Fh]
0x18000e9e0  jmp     short loc_18000E9F5
0x18000e9e2  mov     ecx, 4
0x18000e9e7  jmp     short loc_18000E9F5
0x18000e9e9  mov     ecx, 8
0x18000e9ee  jmp     short loc_18000E9F5
0x18000e9f0  mov     ecx, 2
0x18000e9f5  mov     edx, [rdx]
0x18000e9f7  mov     ebx, 1
0x18000e9fc  xor     eax, eax
0x18000e9fe  mov     r8d, ecx
0x18000ea01  or      r8d, edx
0x18000ea04  cmp     r8d, edx
0x18000ea07  mov     r9d, r8d
0x18000ea0a  setz    al
0x18000ea0d  or      r9d, ebx
0x18000ea10  cmp     r8d, edx
0x18000ea13  mov     [r10+10h], eax
0x18000ea17  mov     eax, edx
0x18000ea19  cmovz   r9d, r8d
0x18000ea1d  lock cmpxchg [rsi], r9d
0x18000ea22  jz      short loc_18000EA28
0x18000ea24  mov     edx, eax
0x18000ea26  jmp     short loc_18000E9FC
0x18000ea28  test    bl, r9b
0x18000ea2b  jz      short loc_18000EA31
0x18000ea2d  test    bl, dl
0x18000ea2f  jz      short loc_18000EA33
0x18000ea31  xor     ebx, ebx
0x18000ea33  mov     [r10], ebx
0x18000ea36  jmp     loc_18000EBC2
0x18000ea3b  mov     ecx, [rdx]
0x18000ea3d  xor     r9d, r9d
0x18000ea40  cmp     r11d, 5
0x18000ea44  mov     ebx, 1
0x18000ea49  setz    r9b
0x18000ea4d  mov     eax, ecx
0x18000ea4f  mov     dword ptr [r10+4], 0
0x18000ea57  or      eax, ebx
0x18000ea59  mov     edx, eax
0x18000ea5b  shr     edx, 16h
0x18000ea5e  and     edx, ebx
0x18000ea60  cmp     edx, r9d
0x18000ea63  jz      short loc_18000EAA5
0x18000ea65  mov     r8d, eax
0x18000ea68  shr     r8d, 0Fh
0x18000ea6c  and     r8d, 7Fh
0x18000ea70  jbe     short loc_18000EA8A
0x18000ea72  cmp     r11d, ebx
0x18000ea75  mov     [r10+4], r8d
0x18000ea79  mov     edx, 5
0x18000ea7e  cmovnz  edx, ebx
0x18000ea81  and     eax, 0FFC07FFFh
0x18000ea86  mov     [r10+8], edx
0x18000ea8a  xor     r8d, r8d
0x18000ea8d  mov     edx, 400000h
0x18000ea92  cmp     r11d, 5
0x18000ea96  cmovz   r8d, edx
0x18000ea9a  mov     edx, eax
0x18000ea9c  btr     edx, 16h
0x18000eaa0  mov     eax, r8d
0x18000eaa3  or      eax, edx
0x18000eaa5  mov     edx, eax
0x18000eaa7  shr     edx, 0Fh
0x18000eaaa  and     edx, 7Fh
0x18000eaad  lea     r8d, [rdx+1]
0x18000eab1  cmp     r8d, 7Fh
0x18000eab5  ja      short loc_18000EABC
0x18000eab7  cmp     r8d, edx
0x18000eaba  jnb     short loc_18000EAC7
0x18000eabc  mov     r8d, ebx
0x18000eabf  mov     [r10+8], r11d
0x18000eac3  mov     [r10+4], edx
0x18000eac7  shl     r8d, 0Fh
0x18000eacb  xor     r8d, eax
0x18000eace  and     r8d, 3F8000h
0x18000ead5  xor     r8d, eax
0x18000ead8  mov     eax, ecx
0x18000eada  lock cmpxchg [rsi], r8d
0x18000eadf  jz      short loc_18000EAE8
0x18000eae1  mov     ecx, eax
0x18000eae3  jmp     loc_18000EA4D
0x18000eae8  not     ecx
0x18000eaea  and     ecx, ebx
0x18000eaec  mov     [r10], ecx
0x18000eaef  jmp     loc_18000EBBA
0x18000eaf4  mov     edx, [rdx]
0x18000eaf6  xor     ebp, ebp
0x18000eaf8  lea     ecx, [rbp+4]
0x18000eafb  cmp     r11d, ecx
0x18000eafe  lea     ebx, [rcx-3]
0x18000eb01  setz    bpl
0x18000eb05  mov     eax, edx
0x18000eb07  mov     dword ptr [r10+4], 0
0x18000eb0f  or      eax, ebx
0x18000eb11  mov     r8d, eax
0x18000eb14  shr     r8d, 0Eh
0x18000eb18  and     r8d, ebx
0x18000eb1b  cmp     r8d, ebp
0x18000eb1e  jz      short loc_18000EB67
0x18000eb20  mov     edi, eax
0x18000eb22  shr     edi, 5
0x18000eb25  and     edi, 1FFh
0x18000eb2b  jbe     short loc_18000EB49
0x18000eb2d  mov     r8d, r11d
0x18000eb30  mov     [r10+4], edi
0x18000eb34  neg     r8d
0x18000eb37  sbb     r9d, r9d
0x18000eb3a  not     r9d
0x18000eb3d  and     r9d, ecx
0x18000eb40  mov     [r10+8], r9d
0x18000eb44  and     eax, 0FFFFC01Fh
0x18000eb49  xor     r9d, r9d
0x18000eb4c  mov     r8d, 4000h
0x18000eb52  cmp     r11d, ecx
0x18000eb55  cmovz   r9d, r8d
0x18000eb59  mov     r8d, eax
0x18000eb5c  btr     r8d, 0Eh
0x18000eb61  mov     eax, r9d
0x18000eb64  or      eax, r8d
0x18000eb67  mov     r8d, eax
0x18000eb6a  shr     r8d, 5
0x18000eb6e  and     r8d, 1FFh
0x18000eb75  lea     r9d, [r8+1]
0x18000eb79  cmp     r9d, 1FFh
0x18000eb80  ja      short loc_18000EB87
0x18000eb82  cmp     r9d, r8d
0x18000eb85  jnb     short loc_18000EB92
0x18000eb87  mov     r9d, ebx
0x18000eb8a  mov     [r10+8], r11d
0x18000eb8e  mov     [r10+4], r8d
0x18000eb92  shl     r9d, 5
0x18000eb96  xor     r9d, eax
0x18000eb99  and     r9d, 3FE0h
0x18000eba0  xor     r9d, eax
0x18000eba3  mov     eax, edx
0x18000eba5  lock cmpxchg [rsi], r9d
0x18000ebaa  jz      short loc_18000EBB3
0x18000ebac  mov     edx, eax
0x18000ebae  jmp     loc_18000EB05
0x18000ebb3  not     edx
0x18000ebb5  and     edx, ebx
0x18000ebb7  mov     [r10], edx
0x18000ebba  mov     dword ptr [r10+10h], 0
0x18000ebc2  mov     rax, r10
0x18000ebc5  pop     rdi
0x18000ebc6  pop     rsi
0x18000ebc7  pop     rbp
0x18000ebc8  pop     rbx
0x18000ebc9  retn
```

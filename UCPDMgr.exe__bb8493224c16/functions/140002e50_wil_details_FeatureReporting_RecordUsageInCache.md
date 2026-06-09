# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140002e50`
- end: `0x14000311e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `718`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004318`

## callees

- `0x140002e50`

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
  int v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  unsigned int v20; // edx
  signed __int32 v21; // eax
  signed __int32 v22; // edx
  int v23; // ebp
  unsigned int v24; // eax
  unsigned int v25; // r9d
  unsigned int v26; // r8d
  signed __int32 v27; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_46;
    case 1:
      goto LABEL_33;
    case 2:
    case 3:
      goto LABEL_16;
    case 4:
LABEL_46:
      v22 = *a2;
      v23 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v24 = v22 | 1;
        if ( (((v22 | 1u) >> 14) & 1) != v23 )
        {
          if ( ((v24 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v24 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v24 = v22 & 0xFFFFC01E | 1;
          }
          v24 = (v23 << 14) | v24 & 0xFFFFBFFF;
        }
        v25 = (v24 >> 5) & 0x1FF;
        v26 = v25 + 1;
        if ( v25 + 1 > 0x1FF || v26 < v25 )
        {
          LOWORD(v26) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v25;
        }
        v27 = _InterlockedCompareExchange(
                a2,
                v24 ^ ((unsigned __int16)v24 ^ (unsigned __int16)(32 * v26)) & 0x3FE0,
                v22);
        if ( v22 == v27 )
          break;
        v22 = v27;
      }
      *(_DWORD *)a1 = (v22 & 1) == 0;
      goto LABEL_57;
    case 5:
LABEL_33:
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
            v18 = 1;
            if ( a3 == 1 )
              v18 = 5;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v17 = v17 & 0xFFBFFFFF | (v16 << 22);
        }
        v19 = (v17 >> 15) & 0x7F;
        v20 = v19 + 1;
        if ( v19 + 1 > 0x7F || v20 < v19 )
        {
          v20 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v19;
        }
        v21 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v20 << 15)) & 0x3F8000, v15);
        if ( v15 == v21 )
          break;
        v15 = v21;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_57:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v6 = a3 - 320;
    if ( v6 < 64 )
    {
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
    }
    *(_DWORD *)(a1 + 8) = a3;
    *(_DWORD *)(a1 + 4) = 1;
    *(_DWORD *)(a1 + 12) = 0;
    return a1;
  }
LABEL_16:
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
0x140002e50  mov     rax, rsp
0x140002e53  mov     [rax+8], rbx
0x140002e57  mov     [rax+10h], rbp
0x140002e5b  mov     [rax+18h], rsi
0x140002e5f  mov     [rax+20h], rdi
0x140002e63  xor     eax, eax
0x140002e65  xorps   xmm0, xmm0
0x140002e68  mov     r11d, r8d
0x140002e6b  mov     rsi, rdx
0x140002e6e  mov     r10, rcx
0x140002e71  mov     r9d, r8d
0x140002e74  movups  xmmword ptr [rcx], xmm0
0x140002e77  mov     [rcx+10h], rax
0x140002e7b  test    r8d, r8d
0x140002e7e  jz      loc_140003048
0x140002e84  sub     r9d, 1
0x140002e88  jz      loc_140002F9E
0x140002e8e  sub     r9d, 1
0x140002e92  jz      loc_140002F25
0x140002e98  sub     r9d, 1
0x140002e9c  jz      loc_140002F25
0x140002ea2  sub     r9d, 1
0x140002ea6  jz      loc_140003048
0x140002eac  sub     r9d, 1
0x140002eb0  jz      loc_140002F9E
0x140002eb6  sub     r9d, 1
0x140002eba  jz      short loc_140002F25
0x140002ebc  cmp     r9d, 1
0x140002ec0  jz      short loc_140002F25
0x140002ec2  add     r8d, 0FFFFFEC0h
0x140002ec9  lea     ebx, [rax+1]
0x140002ecc  cmp     r8d, 40h ; '@'
0x140002ed0  jge     short loc_140002F10
0x140002ed2  mov     eax, [rdx+4]
0x140002ed5  lea     ecx, [rbx+0Fh]
0x140002ed8  mov     r9d, r8d
0x140002edb  shl     r9d, 5
0x140002edf  test    cl, al
0x140002ee1  jz      short loc_140002EF4
0x140002ee3  mov     edx, eax
0x140002ee5  shr     edx, 5
0x140002ee8  and     edx, 3Fh
0x140002eeb  cmp     edx, r8d
0x140002eee  jnz     short loc_140002EF4
0x140002ef0  mov     edx, ebx
0x140002ef2  jmp     short loc_140002EF6
0x140002ef4  xor     edx, edx
0x140002ef6  mov     [r10+10h], edx
0x140002efa  mov     edx, r9d
0x140002efd  xor     edx, eax
0x140002eff  and     edx, 7E0h
0x140002f05  xor     edx, eax
0x140002f07  or      edx, ecx
0x140002f09  lock cmpxchg [rsi+4], edx
0x140002f0e  jnz     short loc_140002EDF
0x140002f10  mov     [r10+8], r11d
0x140002f14  mov     [r10+4], ebx
0x140002f18  mov     dword ptr [r10+0Ch], 0
0x140002f20  jmp     loc_140003106
0x140002f25  xor     ecx, ecx
0x140002f27  sub     r11d, 2
0x140002f2b  jz      short loc_140002F53
0x140002f2d  sub     r11d, 1
0x140002f31  jz      short loc_140002F4C
0x140002f33  sub     r11d, 3
0x140002f37  jz      short loc_140002F45
0x140002f39  cmp     r11d, 1
0x140002f3d  jnz     short loc_140002F58
0x140002f3f  lea     ecx, [r11+0Fh]
0x140002f43  jmp     short loc_140002F58
0x140002f45  mov     ecx, 4
0x140002f4a  jmp     short loc_140002F58
0x140002f4c  mov     ecx, 8
0x140002f51  jmp     short loc_140002F58
0x140002f53  mov     ecx, 2
0x140002f58  mov     edx, [rdx]
0x140002f5a  mov     ebx, 1
0x140002f5f  xor     eax, eax
0x140002f61  mov     r8d, ecx
0x140002f64  or      r8d, edx
0x140002f67  cmp     r8d, edx
0x140002f6a  mov     r9d, r8d
0x140002f6d  setz    al
0x140002f70  or      r9d, ebx
0x140002f73  cmp     r8d, edx
0x140002f76  mov     [r10+10h], eax
0x140002f7a  mov     eax, edx
0x140002f7c  cmovz   r9d, r8d
0x140002f80  lock cmpxchg [rsi], r9d
0x140002f85  jz      short loc_140002F8B
0x140002f87  mov     edx, eax
0x140002f89  jmp     short loc_140002F5F
0x140002f8b  test    bl, r9b
0x140002f8e  jz      short loc_140002F94
0x140002f90  test    bl, dl
0x140002f92  jz      short loc_140002F96
0x140002f94  xor     ebx, ebx
0x140002f96  mov     [r10], ebx
0x140002f99  jmp     loc_140003106
0x140002f9e  mov     ecx, [rdx]
0x140002fa0  xor     r9d, r9d
0x140002fa3  lea     edi, [r9+5]
0x140002fa7  cmp     r11d, edi
0x140002faa  lea     ebx, [rdi-4]
0x140002fad  setz    r9b
0x140002fb1  mov     eax, ecx
0x140002fb3  mov     dword ptr [r10+4], 0
0x140002fbb  or      eax, ebx
0x140002fbd  mov     edx, eax
0x140002fbf  shr     edx, 16h
0x140002fc2  and     edx, ebx
0x140002fc4  cmp     edx, r9d
0x140002fc7  jz      short loc_140002FFD
0x140002fc9  mov     r8d, eax
0x140002fcc  shr     r8d, 0Fh
0x140002fd0  and     r8d, 7Fh
0x140002fd4  jbe     short loc_140002FEB
0x140002fd6  cmp     r11d, ebx
0x140002fd9  mov     [r10+4], r8d
0x140002fdd  mov     edx, ebx
0x140002fdf  cmovz   edx, edi
0x140002fe2  and     eax, 0FFC07FFFh
0x140002fe7  mov     [r10+8], edx
0x140002feb  mov     edx, eax
0x140002fed  mov     r8d, r9d
0x140002ff0  shl     r8d, 16h
0x140002ff4  btr     edx, 16h
0x140002ff8  mov     eax, r8d
0x140002ffb  or      eax, edx
0x140002ffd  mov     r8d, eax
0x140003000  shr     r8d, 0Fh
0x140003004  and     r8d, 7Fh
0x140003008  lea     edx, [r8+1]
0x14000300c  cmp     edx, 7Fh
0x14000300f  ja      short loc_140003016
0x140003011  cmp     edx, r8d
0x140003014  jnb     short loc_140003020
0x140003016  mov     edx, ebx
0x140003018  mov     [r10+8], r11d
0x14000301c  mov     [r10+4], r8d
0x140003020  shl     edx, 0Fh
0x140003023  xor     edx, eax
0x140003025  and     edx, 3F8000h
0x14000302b  xor     edx, eax
0x14000302d  mov     eax, ecx
0x14000302f  lock cmpxchg [rsi], edx
0x140003033  jz      short loc_14000303C
0x140003035  mov     ecx, eax
0x140003037  jmp     loc_140002FB1
0x14000303c  not     ecx
0x14000303e  and     ecx, ebx
0x140003040  mov     [r10], ecx
0x140003043  jmp     loc_1400030FE
0x140003048  mov     edx, [rdx]
0x14000304a  xor     ebp, ebp
0x14000304c  lea     ecx, [rbp+4]
0x14000304f  cmp     r11d, ecx
0x140003052  lea     ebx, [rcx-3]
0x140003055  setz    bpl
0x140003059  mov     eax, edx
0x14000305b  mov     dword ptr [r10+4], 0
0x140003063  or      eax, ebx
0x140003065  mov     r8d, eax
0x140003068  shr     r8d, 0Eh
0x14000306c  and     r8d, ebx
0x14000306f  cmp     r8d, ebp
0x140003072  jz      short loc_1400030AB
0x140003074  mov     edi, eax
0x140003076  shr     edi, 5
0x140003079  and     edi, 1FFh
0x14000307f  jbe     short loc_14000309D
0x140003081  mov     r8d, r11d
0x140003084  mov     [r10+4], edi
0x140003088  neg     r8d
0x14000308b  sbb     r9d, r9d
0x14000308e  not     r9d
0x140003091  and     r9d, ecx
0x140003094  mov     [r10+8], r9d
0x140003098  and     eax, 0FFFFC01Fh
0x14000309d  mov     r8d, ebp
0x1400030a0  btr     eax, 0Eh
0x1400030a4  shl     r8d, 0Eh
0x1400030a8  or      eax, r8d
0x1400030ab  mov     r9d, eax
0x1400030ae  shr     r9d, 5
0x1400030b2  and     r9d, 1FFh
0x1400030b9  lea     r8d, [r9+1]
0x1400030bd  cmp     r8d, 1FFh
0x1400030c4  ja      short loc_1400030CB
0x1400030c6  cmp     r8d, r9d
0x1400030c9  jnb     short loc_1400030D6
0x1400030cb  mov     r8d, ebx
0x1400030ce  mov     [r10+8], r11d
0x1400030d2  mov     [r10+4], r9d
0x1400030d6  shl     r8d, 5
0x1400030da  xor     r8d, eax
0x1400030dd  and     r8d, 3FE0h
0x1400030e4  xor     r8d, eax
0x1400030e7  mov     eax, edx
0x1400030e9  lock cmpxchg [rsi], r8d
0x1400030ee  jz      short loc_1400030F7
0x1400030f0  mov     edx, eax
0x1400030f2  jmp     loc_140003059
0x1400030f7  not     edx
0x1400030f9  and     edx, ebx
0x1400030fb  mov     [r10], edx
0x1400030fe  mov     dword ptr [r10+10h], 0
0x140003106  mov     rbx, [rsp+arg_0]
0x14000310b  mov     rax, r10
0x14000310e  mov     rbp, [rsp+arg_8]
0x140003113  mov     rsi, [rsp+arg_10]
0x140003118  mov     rdi, [rsp+arg_18]
0x14000311d  retn
```

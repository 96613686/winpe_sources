# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180002ef0`
- end: `0x1800031c2`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800032e4`

## callees

- `0x180002ef0`

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
0x180002ef0  push    rbx
0x180002ef2  push    rbp
0x180002ef3  push    rsi
0x180002ef4  push    rdi
0x180002ef5  xor     eax, eax
0x180002ef7  xorps   xmm0, xmm0
0x180002efa  mov     r10, rcx
0x180002efd  mov     edi, r9d
0x180002f00  mov     r11d, r8d
0x180002f03  mov     rsi, rdx
0x180002f06  movups  xmmword ptr [rcx], xmm0
0x180002f09  mov     [rcx+10h], rax
0x180002f0d  mov     ecx, r8d
0x180002f10  test    r8d, r8d
0x180002f13  jz      loc_1800030EC
0x180002f19  sub     ecx, 1
0x180002f1c  jz      loc_180003033
0x180002f22  sub     ecx, 1
0x180002f25  jz      loc_180002FBA
0x180002f2b  sub     ecx, 1
0x180002f2e  jz      loc_180002FBA
0x180002f34  sub     ecx, 1
0x180002f37  jz      loc_1800030EC
0x180002f3d  sub     ecx, 1
0x180002f40  jz      loc_180003033
0x180002f46  sub     ecx, 1
0x180002f49  jz      short loc_180002FBA
0x180002f4b  cmp     ecx, 1
0x180002f4e  jz      short loc_180002FBA
0x180002f50  add     r8d, 0FFFFFEC0h
0x180002f57  lea     ebx, [rax+1]
0x180002f5a  cmp     r8d, 40h ; '@'
0x180002f5e  jge     short loc_180002FA9
0x180002f60  mov     eax, [rdx+4]
0x180002f63  lea     ecx, [rbx+0Fh]
0x180002f66  mov     r9d, r8d
0x180002f69  shl     r9d, 5
0x180002f6d  test    cl, al
0x180002f6f  jz      short loc_180002F82
0x180002f71  mov     edx, eax
0x180002f73  shr     edx, 5
0x180002f76  and     edx, 3Fh
0x180002f79  cmp     edx, r8d
0x180002f7c  jnz     short loc_180002F82
0x180002f7e  mov     edx, ebx
0x180002f80  jmp     short loc_180002F84
0x180002f82  xor     edx, edx
0x180002f84  mov     [r10+10h], edx
0x180002f88  mov     edx, r9d
0x180002f8b  xor     edx, eax
0x180002f8d  and     edx, 7E0h
0x180002f93  xor     edx, eax
0x180002f95  or      edx, ecx
0x180002f97  lock cmpxchg [rsi+4], edx
0x180002f9c  jnz     short loc_180002F6D
0x180002f9e  cmp     dword ptr [r10+10h], 0
0x180002fa3  jnz     loc_1800031BA
0x180002fa9  mov     [r10+8], r11d
0x180002fad  mov     [r10+4], ebx
0x180002fb1  mov     [r10+0Ch], edi
0x180002fb5  jmp     loc_1800031BA
0x180002fba  xor     ecx, ecx
0x180002fbc  sub     r11d, 2
0x180002fc0  jz      short loc_180002FE8
0x180002fc2  sub     r11d, 1
0x180002fc6  jz      short loc_180002FE1
0x180002fc8  sub     r11d, 3
0x180002fcc  jz      short loc_180002FDA
0x180002fce  cmp     r11d, 1
0x180002fd2  jnz     short loc_180002FED
0x180002fd4  lea     ecx, [r11+0Fh]
0x180002fd8  jmp     short loc_180002FED
0x180002fda  mov     ecx, 4
0x180002fdf  jmp     short loc_180002FED
0x180002fe1  mov     ecx, 8
0x180002fe6  jmp     short loc_180002FED
0x180002fe8  mov     ecx, 2
0x180002fed  mov     edx, [rdx]
0x180002fef  mov     ebx, 1
0x180002ff4  xor     eax, eax
0x180002ff6  mov     r8d, ecx
0x180002ff9  or      r8d, edx
0x180002ffc  cmp     r8d, edx
0x180002fff  mov     r9d, r8d
0x180003002  setz    al
0x180003005  or      r9d, ebx
0x180003008  cmp     r8d, edx
0x18000300b  mov     [r10+10h], eax
0x18000300f  mov     eax, edx
0x180003011  cmovz   r9d, r8d
0x180003015  lock cmpxchg [rsi], r9d
0x18000301a  jz      short loc_180003020
0x18000301c  mov     edx, eax
0x18000301e  jmp     short loc_180002FF4
0x180003020  test    bl, r9b
0x180003023  jz      short loc_180003029
0x180003025  test    bl, dl
0x180003027  jz      short loc_18000302B
0x180003029  xor     ebx, ebx
0x18000302b  mov     [r10], ebx
0x18000302e  jmp     loc_1800031BA
0x180003033  mov     ecx, [rdx]
0x180003035  xor     r9d, r9d
0x180003038  cmp     r11d, 5
0x18000303c  mov     ebx, 1
0x180003041  setz    r9b
0x180003045  mov     eax, ecx
0x180003047  mov     dword ptr [r10+4], 0
0x18000304f  or      eax, ebx
0x180003051  mov     edx, eax
0x180003053  shr     edx, 16h
0x180003056  and     edx, ebx
0x180003058  cmp     edx, r9d
0x18000305b  jz      short loc_18000309D
0x18000305d  mov     r8d, eax
0x180003060  shr     r8d, 0Fh
0x180003064  and     r8d, 7Fh
0x180003068  jbe     short loc_180003082
0x18000306a  cmp     r11d, ebx
0x18000306d  mov     [r10+4], r8d
0x180003071  mov     edx, 5
0x180003076  cmovnz  edx, ebx
0x180003079  and     eax, 0FFC07FFFh
0x18000307e  mov     [r10+8], edx
0x180003082  xor     r8d, r8d
0x180003085  mov     edx, 400000h
0x18000308a  cmp     r11d, 5
0x18000308e  cmovz   r8d, edx
0x180003092  mov     edx, eax
0x180003094  btr     edx, 16h
0x180003098  mov     eax, r8d
0x18000309b  or      eax, edx
0x18000309d  mov     edx, eax
0x18000309f  shr     edx, 0Fh
0x1800030a2  and     edx, 7Fh
0x1800030a5  lea     r8d, [rdx+1]
0x1800030a9  cmp     r8d, 7Fh
0x1800030ad  ja      short loc_1800030B4
0x1800030af  cmp     r8d, edx
0x1800030b2  jnb     short loc_1800030BF
0x1800030b4  mov     r8d, ebx
0x1800030b7  mov     [r10+8], r11d
0x1800030bb  mov     [r10+4], edx
0x1800030bf  shl     r8d, 0Fh
0x1800030c3  xor     r8d, eax
0x1800030c6  and     r8d, 3F8000h
0x1800030cd  xor     r8d, eax
0x1800030d0  mov     eax, ecx
0x1800030d2  lock cmpxchg [rsi], r8d
0x1800030d7  jz      short loc_1800030E0
0x1800030d9  mov     ecx, eax
0x1800030db  jmp     loc_180003045
0x1800030e0  not     ecx
0x1800030e2  and     ecx, ebx
0x1800030e4  mov     [r10], ecx
0x1800030e7  jmp     loc_1800031B2
0x1800030ec  mov     edx, [rdx]
0x1800030ee  xor     ebp, ebp
0x1800030f0  lea     ecx, [rbp+4]
0x1800030f3  cmp     r11d, ecx
0x1800030f6  lea     ebx, [rcx-3]
0x1800030f9  setz    bpl
0x1800030fd  mov     eax, edx
0x1800030ff  mov     dword ptr [r10+4], 0
0x180003107  or      eax, ebx
0x180003109  mov     r8d, eax
0x18000310c  shr     r8d, 0Eh
0x180003110  and     r8d, ebx
0x180003113  cmp     r8d, ebp
0x180003116  jz      short loc_18000315F
0x180003118  mov     edi, eax
0x18000311a  shr     edi, 5
0x18000311d  and     edi, 1FFh
0x180003123  jbe     short loc_180003141
0x180003125  mov     r8d, r11d
0x180003128  mov     [r10+4], edi
0x18000312c  neg     r8d
0x18000312f  sbb     r9d, r9d
0x180003132  not     r9d
0x180003135  and     r9d, ecx
0x180003138  mov     [r10+8], r9d
0x18000313c  and     eax, 0FFFFC01Fh
0x180003141  xor     r9d, r9d
0x180003144  mov     r8d, 4000h
0x18000314a  cmp     r11d, ecx
0x18000314d  cmovz   r9d, r8d
0x180003151  mov     r8d, eax
0x180003154  btr     r8d, 0Eh
0x180003159  mov     eax, r9d
0x18000315c  or      eax, r8d
0x18000315f  mov     r8d, eax
0x180003162  shr     r8d, 5
0x180003166  and     r8d, 1FFh
0x18000316d  lea     r9d, [r8+1]
0x180003171  cmp     r9d, 1FFh
0x180003178  ja      short loc_18000317F
0x18000317a  cmp     r9d, r8d
0x18000317d  jnb     short loc_18000318A
0x18000317f  mov     r9d, ebx
0x180003182  mov     [r10+8], r11d
0x180003186  mov     [r10+4], r8d
0x18000318a  shl     r9d, 5
0x18000318e  xor     r9d, eax
0x180003191  and     r9d, 3FE0h
0x180003198  xor     r9d, eax
0x18000319b  mov     eax, edx
0x18000319d  lock cmpxchg [rsi], r9d
0x1800031a2  jz      short loc_1800031AB
0x1800031a4  mov     edx, eax
0x1800031a6  jmp     loc_1800030FD
0x1800031ab  not     edx
0x1800031ad  and     edx, ebx
0x1800031af  mov     [r10], edx
0x1800031b2  mov     dword ptr [r10+10h], 0
0x1800031ba  mov     rax, r10
0x1800031bd  pop     rdi
0x1800031be  pop     rsi
0x1800031bf  pop     rbp
0x1800031c0  pop     rbx
0x1800031c1  retn
```

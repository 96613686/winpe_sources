# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180002f2c`
- end: `0x1800031ff`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003328`

## callees

- `0x180002f2c`

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
0x180002f2c  push    rbx
0x180002f2e  push    rbp
0x180002f2f  push    rsi
0x180002f30  push    rdi
0x180002f31  xor     eax, eax
0x180002f33  xorps   xmm0, xmm0
0x180002f36  mov     r10, rcx
0x180002f39  mov     edi, r9d
0x180002f3c  mov     r11d, r8d
0x180002f3f  mov     rsi, rdx
0x180002f42  movups  xmmword ptr [rcx], xmm0
0x180002f45  mov     [rcx+10h], rax
0x180002f49  mov     ecx, r8d
0x180002f4c  test    r8d, r8d
0x180002f4f  jz      loc_180003128
0x180002f55  sub     ecx, 1
0x180002f58  jz      loc_18000306F
0x180002f5e  sub     ecx, 1
0x180002f61  jz      loc_180002FF6
0x180002f67  sub     ecx, 1
0x180002f6a  jz      loc_180002FF6
0x180002f70  sub     ecx, 1
0x180002f73  jz      loc_180003128
0x180002f79  sub     ecx, 1
0x180002f7c  jz      loc_18000306F
0x180002f82  sub     ecx, 1
0x180002f85  jz      short loc_180002FF6
0x180002f87  cmp     ecx, 1
0x180002f8a  jz      short loc_180002FF6
0x180002f8c  add     r8d, 0FFFFFEC0h
0x180002f93  lea     ebx, [rax+1]
0x180002f96  cmp     r8d, 40h ; '@'
0x180002f9a  jge     short loc_180002FE5
0x180002f9c  mov     eax, [rdx+4]
0x180002f9f  lea     ecx, [rbx+0Fh]
0x180002fa2  mov     r9d, r8d
0x180002fa5  shl     r9d, 5
0x180002fa9  test    cl, al
0x180002fab  jz      short loc_180002FBE
0x180002fad  mov     edx, eax
0x180002faf  shr     edx, 5
0x180002fb2  and     edx, 3Fh
0x180002fb5  cmp     edx, r8d
0x180002fb8  jnz     short loc_180002FBE
0x180002fba  mov     edx, ebx
0x180002fbc  jmp     short loc_180002FC0
0x180002fbe  xor     edx, edx
0x180002fc0  mov     [r10+10h], edx
0x180002fc4  mov     edx, r9d
0x180002fc7  xor     edx, eax
0x180002fc9  and     edx, 7E0h
0x180002fcf  xor     edx, eax
0x180002fd1  or      edx, ecx
0x180002fd3  lock cmpxchg [rsi+4], edx
0x180002fd8  jnz     short loc_180002FA9
0x180002fda  cmp     dword ptr [r10+10h], 0
0x180002fdf  jnz     loc_1800031F6
0x180002fe5  mov     [r10+8], r11d
0x180002fe9  mov     [r10+4], ebx
0x180002fed  mov     [r10+0Ch], edi
0x180002ff1  jmp     loc_1800031F6
0x180002ff6  xor     ecx, ecx
0x180002ff8  sub     r11d, 2
0x180002ffc  jz      short loc_180003024
0x180002ffe  sub     r11d, 1
0x180003002  jz      short loc_18000301D
0x180003004  sub     r11d, 3
0x180003008  jz      short loc_180003016
0x18000300a  cmp     r11d, 1
0x18000300e  jnz     short loc_180003029
0x180003010  lea     ecx, [r11+0Fh]
0x180003014  jmp     short loc_180003029
0x180003016  mov     ecx, 4
0x18000301b  jmp     short loc_180003029
0x18000301d  mov     ecx, 8
0x180003022  jmp     short loc_180003029
0x180003024  mov     ecx, 2
0x180003029  mov     edx, [rdx]
0x18000302b  mov     ebx, 1
0x180003030  xor     eax, eax
0x180003032  mov     r8d, ecx
0x180003035  or      r8d, edx
0x180003038  cmp     r8d, edx
0x18000303b  mov     r9d, r8d
0x18000303e  setz    al
0x180003041  or      r9d, ebx
0x180003044  cmp     r8d, edx
0x180003047  mov     [r10+10h], eax
0x18000304b  mov     eax, edx
0x18000304d  cmovz   r9d, r8d
0x180003051  lock cmpxchg [rsi], r9d
0x180003056  jz      short loc_18000305C
0x180003058  mov     edx, eax
0x18000305a  jmp     short loc_180003030
0x18000305c  test    bl, r9b
0x18000305f  jz      short loc_180003065
0x180003061  test    bl, dl
0x180003063  jz      short loc_180003067
0x180003065  xor     ebx, ebx
0x180003067  mov     [r10], ebx
0x18000306a  jmp     loc_1800031F6
0x18000306f  mov     ecx, [rdx]
0x180003071  xor     r9d, r9d
0x180003074  cmp     r11d, 5
0x180003078  mov     ebx, 1
0x18000307d  setz    r9b
0x180003081  mov     eax, ecx
0x180003083  mov     dword ptr [r10+4], 0
0x18000308b  or      eax, ebx
0x18000308d  mov     edx, eax
0x18000308f  shr     edx, 16h
0x180003092  and     edx, ebx
0x180003094  cmp     edx, r9d
0x180003097  jz      short loc_1800030D9
0x180003099  mov     r8d, eax
0x18000309c  shr     r8d, 0Fh
0x1800030a0  and     r8d, 7Fh
0x1800030a4  jbe     short loc_1800030BE
0x1800030a6  cmp     r11d, ebx
0x1800030a9  mov     [r10+4], r8d
0x1800030ad  mov     edx, 5
0x1800030b2  cmovnz  edx, ebx
0x1800030b5  and     eax, 0FFC07FFFh
0x1800030ba  mov     [r10+8], edx
0x1800030be  xor     r8d, r8d
0x1800030c1  mov     edx, 400000h
0x1800030c6  cmp     r11d, 5
0x1800030ca  cmovz   r8d, edx
0x1800030ce  mov     edx, eax
0x1800030d0  btr     edx, 16h
0x1800030d4  mov     eax, r8d
0x1800030d7  or      eax, edx
0x1800030d9  mov     edx, eax
0x1800030db  shr     edx, 0Fh
0x1800030de  and     edx, 7Fh
0x1800030e1  lea     r8d, [rdx+1]
0x1800030e5  cmp     r8d, 7Fh
0x1800030e9  ja      short loc_1800030F0
0x1800030eb  cmp     r8d, edx
0x1800030ee  jnb     short loc_1800030FB
0x1800030f0  mov     r8d, ebx
0x1800030f3  mov     [r10+8], r11d
0x1800030f7  mov     [r10+4], edx
0x1800030fb  shl     r8d, 0Fh
0x1800030ff  xor     r8d, eax
0x180003102  and     r8d, 3F8000h
0x180003109  xor     r8d, eax
0x18000310c  mov     eax, ecx
0x18000310e  lock cmpxchg [rsi], r8d
0x180003113  jz      short loc_18000311C
0x180003115  mov     ecx, eax
0x180003117  jmp     loc_180003081
0x18000311c  not     ecx
0x18000311e  and     ecx, ebx
0x180003120  mov     [r10], ecx
0x180003123  jmp     loc_1800031EE
0x180003128  mov     edx, [rdx]
0x18000312a  xor     ebp, ebp
0x18000312c  lea     ecx, [rbp+4]
0x18000312f  cmp     r11d, ecx
0x180003132  lea     ebx, [rcx-3]
0x180003135  setz    bpl
0x180003139  mov     eax, edx
0x18000313b  mov     dword ptr [r10+4], 0
0x180003143  or      eax, ebx
0x180003145  mov     r8d, eax
0x180003148  shr     r8d, 0Eh
0x18000314c  and     r8d, ebx
0x18000314f  cmp     r8d, ebp
0x180003152  jz      short loc_18000319B
0x180003154  mov     edi, eax
0x180003156  shr     edi, 5
0x180003159  and     edi, 1FFh
0x18000315f  jbe     short loc_18000317D
0x180003161  mov     r8d, r11d
0x180003164  mov     [r10+4], edi
0x180003168  neg     r8d
0x18000316b  sbb     r9d, r9d
0x18000316e  not     r9d
0x180003171  and     r9d, ecx
0x180003174  mov     [r10+8], r9d
0x180003178  and     eax, 0FFFFC01Fh
0x18000317d  xor     r9d, r9d
0x180003180  mov     r8d, 4000h
0x180003186  cmp     r11d, ecx
0x180003189  cmovz   r9d, r8d
0x18000318d  mov     r8d, eax
0x180003190  btr     r8d, 0Eh
0x180003195  mov     eax, r9d
0x180003198  or      eax, r8d
0x18000319b  mov     r8d, eax
0x18000319e  shr     r8d, 5
0x1800031a2  and     r8d, 1FFh
0x1800031a9  lea     r9d, [r8+1]
0x1800031ad  cmp     r9d, 1FFh
0x1800031b4  ja      short loc_1800031BB
0x1800031b6  cmp     r9d, r8d
0x1800031b9  jnb     short loc_1800031C6
0x1800031bb  mov     r9d, ebx
0x1800031be  mov     [r10+8], r11d
0x1800031c2  mov     [r10+4], r8d
0x1800031c6  shl     r9d, 5
0x1800031ca  xor     r9d, eax
0x1800031cd  and     r9d, 3FE0h
0x1800031d4  xor     r9d, eax
0x1800031d7  mov     eax, edx
0x1800031d9  lock cmpxchg [rsi], r9d
0x1800031de  jz      short loc_1800031E7
0x1800031e0  mov     edx, eax
0x1800031e2  jmp     loc_180003139
0x1800031e7  not     edx
0x1800031e9  and     edx, ebx
0x1800031eb  mov     [r10], edx
0x1800031ee  mov     dword ptr [r10+10h], 0
0x1800031f6  mov     rax, r10
0x1800031f9  pop     rdi
0x1800031fa  pop     rsi
0x1800031fb  pop     rbp
0x1800031fc  pop     rbx
0x1800031fd  retn
```

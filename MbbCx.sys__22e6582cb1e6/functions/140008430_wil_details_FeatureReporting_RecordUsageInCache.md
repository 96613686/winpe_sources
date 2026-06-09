# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140008430`
- end: `0x140008703`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008838`

## callees

- `0x140008430`

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
0x140008430  push    rbx
0x140008432  push    rbp
0x140008433  push    rsi
0x140008434  push    rdi
0x140008435  xor     eax, eax
0x140008437  xorps   xmm0, xmm0
0x14000843a  mov     r10, rcx
0x14000843d  mov     edi, r9d
0x140008440  mov     r11d, r8d
0x140008443  mov     rsi, rdx
0x140008446  movups  xmmword ptr [rcx], xmm0
0x140008449  mov     [rcx+10h], rax
0x14000844d  mov     ecx, r8d
0x140008450  test    r8d, r8d
0x140008453  jz      loc_14000862C
0x140008459  sub     ecx, 1
0x14000845c  jz      loc_140008573
0x140008462  sub     ecx, 1
0x140008465  jz      loc_1400084FA
0x14000846b  sub     ecx, 1
0x14000846e  jz      loc_1400084FA
0x140008474  sub     ecx, 1
0x140008477  jz      loc_14000862C
0x14000847d  sub     ecx, 1
0x140008480  jz      loc_140008573
0x140008486  sub     ecx, 1
0x140008489  jz      short loc_1400084FA
0x14000848b  cmp     ecx, 1
0x14000848e  jz      short loc_1400084FA
0x140008490  add     r8d, 0FFFFFEC0h
0x140008497  lea     ebx, [rax+1]
0x14000849a  cmp     r8d, 40h ; '@'
0x14000849e  jge     short loc_1400084E9
0x1400084a0  mov     eax, [rdx+4]
0x1400084a3  lea     ecx, [rbx+0Fh]
0x1400084a6  mov     r9d, r8d
0x1400084a9  shl     r9d, 5
0x1400084ad  test    cl, al
0x1400084af  jz      short loc_1400084C2
0x1400084b1  mov     edx, eax
0x1400084b3  shr     edx, 5
0x1400084b6  and     edx, 3Fh
0x1400084b9  cmp     edx, r8d
0x1400084bc  jnz     short loc_1400084C2
0x1400084be  mov     edx, ebx
0x1400084c0  jmp     short loc_1400084C4
0x1400084c2  xor     edx, edx
0x1400084c4  mov     [r10+10h], edx
0x1400084c8  mov     edx, r9d
0x1400084cb  xor     edx, eax
0x1400084cd  and     edx, 7E0h
0x1400084d3  xor     edx, eax
0x1400084d5  or      edx, ecx
0x1400084d7  lock cmpxchg [rsi+4], edx
0x1400084dc  jnz     short loc_1400084AD
0x1400084de  cmp     dword ptr [r10+10h], 0
0x1400084e3  jnz     loc_1400086FA
0x1400084e9  mov     [r10+8], r11d
0x1400084ed  mov     [r10+4], ebx
0x1400084f1  mov     [r10+0Ch], edi
0x1400084f5  jmp     loc_1400086FA
0x1400084fa  xor     ecx, ecx
0x1400084fc  sub     r11d, 2
0x140008500  jz      short loc_140008528
0x140008502  sub     r11d, 1
0x140008506  jz      short loc_140008521
0x140008508  sub     r11d, 3
0x14000850c  jz      short loc_14000851A
0x14000850e  cmp     r11d, 1
0x140008512  jnz     short loc_14000852D
0x140008514  lea     ecx, [r11+0Fh]
0x140008518  jmp     short loc_14000852D
0x14000851a  mov     ecx, 4
0x14000851f  jmp     short loc_14000852D
0x140008521  mov     ecx, 8
0x140008526  jmp     short loc_14000852D
0x140008528  mov     ecx, 2
0x14000852d  mov     edx, [rdx]
0x14000852f  mov     ebx, 1
0x140008534  xor     eax, eax
0x140008536  mov     r8d, ecx
0x140008539  or      r8d, edx
0x14000853c  cmp     r8d, edx
0x14000853f  mov     r9d, r8d
0x140008542  setz    al
0x140008545  or      r9d, ebx
0x140008548  cmp     r8d, edx
0x14000854b  mov     [r10+10h], eax
0x14000854f  mov     eax, edx
0x140008551  cmovz   r9d, r8d
0x140008555  lock cmpxchg [rsi], r9d
0x14000855a  jz      short loc_140008560
0x14000855c  mov     edx, eax
0x14000855e  jmp     short loc_140008534
0x140008560  test    bl, r9b
0x140008563  jz      short loc_140008569
0x140008565  test    bl, dl
0x140008567  jz      short loc_14000856B
0x140008569  xor     ebx, ebx
0x14000856b  mov     [r10], ebx
0x14000856e  jmp     loc_1400086FA
0x140008573  mov     ecx, [rdx]
0x140008575  xor     r9d, r9d
0x140008578  cmp     r11d, 5
0x14000857c  mov     ebx, 1
0x140008581  setz    r9b
0x140008585  mov     eax, ecx
0x140008587  mov     dword ptr [r10+4], 0
0x14000858f  or      eax, ebx
0x140008591  mov     edx, eax
0x140008593  shr     edx, 16h
0x140008596  and     edx, ebx
0x140008598  cmp     edx, r9d
0x14000859b  jz      short loc_1400085DD
0x14000859d  mov     r8d, eax
0x1400085a0  shr     r8d, 0Fh
0x1400085a4  and     r8d, 7Fh
0x1400085a8  jbe     short loc_1400085C2
0x1400085aa  cmp     r11d, ebx
0x1400085ad  mov     [r10+4], r8d
0x1400085b1  mov     edx, 5
0x1400085b6  cmovnz  edx, ebx
0x1400085b9  and     eax, 0FFC07FFFh
0x1400085be  mov     [r10+8], edx
0x1400085c2  xor     r8d, r8d
0x1400085c5  mov     edx, 400000h
0x1400085ca  cmp     r11d, 5
0x1400085ce  cmovz   r8d, edx
0x1400085d2  mov     edx, eax
0x1400085d4  btr     edx, 16h
0x1400085d8  mov     eax, r8d
0x1400085db  or      eax, edx
0x1400085dd  mov     edx, eax
0x1400085df  shr     edx, 0Fh
0x1400085e2  and     edx, 7Fh
0x1400085e5  lea     r8d, [rdx+1]
0x1400085e9  cmp     r8d, 7Fh
0x1400085ed  ja      short loc_1400085F4
0x1400085ef  cmp     r8d, edx
0x1400085f2  jnb     short loc_1400085FF
0x1400085f4  mov     r8d, ebx
0x1400085f7  mov     [r10+8], r11d
0x1400085fb  mov     [r10+4], edx
0x1400085ff  shl     r8d, 0Fh
0x140008603  xor     r8d, eax
0x140008606  and     r8d, 3F8000h
0x14000860d  xor     r8d, eax
0x140008610  mov     eax, ecx
0x140008612  lock cmpxchg [rsi], r8d
0x140008617  jz      short loc_140008620
0x140008619  mov     ecx, eax
0x14000861b  jmp     loc_140008585
0x140008620  not     ecx
0x140008622  and     ecx, ebx
0x140008624  mov     [r10], ecx
0x140008627  jmp     loc_1400086F2
0x14000862c  mov     edx, [rdx]
0x14000862e  xor     ebp, ebp
0x140008630  lea     ecx, [rbp+4]
0x140008633  cmp     r11d, ecx
0x140008636  lea     ebx, [rcx-3]
0x140008639  setz    bpl
0x14000863d  mov     eax, edx
0x14000863f  mov     dword ptr [r10+4], 0
0x140008647  or      eax, ebx
0x140008649  mov     r8d, eax
0x14000864c  shr     r8d, 0Eh
0x140008650  and     r8d, ebx
0x140008653  cmp     r8d, ebp
0x140008656  jz      short loc_14000869F
0x140008658  mov     edi, eax
0x14000865a  shr     edi, 5
0x14000865d  and     edi, 1FFh
0x140008663  jbe     short loc_140008681
0x140008665  mov     r8d, r11d
0x140008668  mov     [r10+4], edi
0x14000866c  neg     r8d
0x14000866f  sbb     r9d, r9d
0x140008672  not     r9d
0x140008675  and     r9d, ecx
0x140008678  mov     [r10+8], r9d
0x14000867c  and     eax, 0FFFFC01Fh
0x140008681  xor     r9d, r9d
0x140008684  mov     r8d, 4000h
0x14000868a  cmp     r11d, ecx
0x14000868d  cmovz   r9d, r8d
0x140008691  mov     r8d, eax
0x140008694  btr     r8d, 0Eh
0x140008699  mov     eax, r9d
0x14000869c  or      eax, r8d
0x14000869f  mov     r8d, eax
0x1400086a2  shr     r8d, 5
0x1400086a6  and     r8d, 1FFh
0x1400086ad  lea     r9d, [r8+1]
0x1400086b1  cmp     r9d, 1FFh
0x1400086b8  ja      short loc_1400086BF
0x1400086ba  cmp     r9d, r8d
0x1400086bd  jnb     short loc_1400086CA
0x1400086bf  mov     r9d, ebx
0x1400086c2  mov     [r10+8], r11d
0x1400086c6  mov     [r10+4], r8d
0x1400086ca  shl     r9d, 5
0x1400086ce  xor     r9d, eax
0x1400086d1  and     r9d, 3FE0h
0x1400086d8  xor     r9d, eax
0x1400086db  mov     eax, edx
0x1400086dd  lock cmpxchg [rsi], r9d
0x1400086e2  jz      short loc_1400086EB
0x1400086e4  mov     edx, eax
0x1400086e6  jmp     loc_14000863D
0x1400086eb  not     edx
0x1400086ed  and     edx, ebx
0x1400086ef  mov     [r10], edx
0x1400086f2  mov     dword ptr [r10+10h], 0
0x1400086fa  mov     rax, r10
0x1400086fd  pop     rdi
0x1400086fe  pop     rsi
0x1400086ff  pop     rbp
0x140008700  pop     rbx
0x140008701  retn
```

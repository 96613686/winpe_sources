# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140003758`
- end: `0x140003a2b`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003b54`

## callees

- `0x140003758`

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
0x140003758  push    rbx
0x14000375a  push    rbp
0x14000375b  push    rsi
0x14000375c  push    rdi
0x14000375d  xor     eax, eax
0x14000375f  xorps   xmm0, xmm0
0x140003762  mov     r10, rcx
0x140003765  mov     edi, r9d
0x140003768  mov     r11d, r8d
0x14000376b  mov     rsi, rdx
0x14000376e  movups  xmmword ptr [rcx], xmm0
0x140003771  mov     [rcx+10h], rax
0x140003775  mov     ecx, r8d
0x140003778  test    r8d, r8d
0x14000377b  jz      loc_140003954
0x140003781  sub     ecx, 1
0x140003784  jz      loc_14000389B
0x14000378a  sub     ecx, 1
0x14000378d  jz      loc_140003822
0x140003793  sub     ecx, 1
0x140003796  jz      loc_140003822
0x14000379c  sub     ecx, 1
0x14000379f  jz      loc_140003954
0x1400037a5  sub     ecx, 1
0x1400037a8  jz      loc_14000389B
0x1400037ae  sub     ecx, 1
0x1400037b1  jz      short loc_140003822
0x1400037b3  cmp     ecx, 1
0x1400037b6  jz      short loc_140003822
0x1400037b8  add     r8d, 0FFFFFEC0h
0x1400037bf  lea     ebx, [rax+1]
0x1400037c2  cmp     r8d, 40h ; '@'
0x1400037c6  jge     short loc_140003811
0x1400037c8  mov     eax, [rdx+4]
0x1400037cb  lea     ecx, [rbx+0Fh]
0x1400037ce  mov     r9d, r8d
0x1400037d1  shl     r9d, 5
0x1400037d5  test    cl, al
0x1400037d7  jz      short loc_1400037EA
0x1400037d9  mov     edx, eax
0x1400037db  shr     edx, 5
0x1400037de  and     edx, 3Fh
0x1400037e1  cmp     edx, r8d
0x1400037e4  jnz     short loc_1400037EA
0x1400037e6  mov     edx, ebx
0x1400037e8  jmp     short loc_1400037EC
0x1400037ea  xor     edx, edx
0x1400037ec  mov     [r10+10h], edx
0x1400037f0  mov     edx, r9d
0x1400037f3  xor     edx, eax
0x1400037f5  and     edx, 7E0h
0x1400037fb  xor     edx, eax
0x1400037fd  or      edx, ecx
0x1400037ff  lock cmpxchg [rsi+4], edx
0x140003804  jnz     short loc_1400037D5
0x140003806  cmp     dword ptr [r10+10h], 0
0x14000380b  jnz     loc_140003A22
0x140003811  mov     [r10+8], r11d
0x140003815  mov     [r10+4], ebx
0x140003819  mov     [r10+0Ch], edi
0x14000381d  jmp     loc_140003A22
0x140003822  xor     ecx, ecx
0x140003824  sub     r11d, 2
0x140003828  jz      short loc_140003850
0x14000382a  sub     r11d, 1
0x14000382e  jz      short loc_140003849
0x140003830  sub     r11d, 3
0x140003834  jz      short loc_140003842
0x140003836  cmp     r11d, 1
0x14000383a  jnz     short loc_140003855
0x14000383c  lea     ecx, [r11+0Fh]
0x140003840  jmp     short loc_140003855
0x140003842  mov     ecx, 4
0x140003847  jmp     short loc_140003855
0x140003849  mov     ecx, 8
0x14000384e  jmp     short loc_140003855
0x140003850  mov     ecx, 2
0x140003855  mov     edx, [rdx]
0x140003857  mov     ebx, 1
0x14000385c  xor     eax, eax
0x14000385e  mov     r8d, ecx
0x140003861  or      r8d, edx
0x140003864  cmp     r8d, edx
0x140003867  mov     r9d, r8d
0x14000386a  setz    al
0x14000386d  or      r9d, ebx
0x140003870  cmp     r8d, edx
0x140003873  mov     [r10+10h], eax
0x140003877  mov     eax, edx
0x140003879  cmovz   r9d, r8d
0x14000387d  lock cmpxchg [rsi], r9d
0x140003882  jz      short loc_140003888
0x140003884  mov     edx, eax
0x140003886  jmp     short loc_14000385C
0x140003888  test    bl, r9b
0x14000388b  jz      short loc_140003891
0x14000388d  test    bl, dl
0x14000388f  jz      short loc_140003893
0x140003891  xor     ebx, ebx
0x140003893  mov     [r10], ebx
0x140003896  jmp     loc_140003A22
0x14000389b  mov     ecx, [rdx]
0x14000389d  xor     r9d, r9d
0x1400038a0  cmp     r11d, 5
0x1400038a4  mov     ebx, 1
0x1400038a9  setz    r9b
0x1400038ad  mov     eax, ecx
0x1400038af  mov     dword ptr [r10+4], 0
0x1400038b7  or      eax, ebx
0x1400038b9  mov     edx, eax
0x1400038bb  shr     edx, 16h
0x1400038be  and     edx, ebx
0x1400038c0  cmp     edx, r9d
0x1400038c3  jz      short loc_140003905
0x1400038c5  mov     r8d, eax
0x1400038c8  shr     r8d, 0Fh
0x1400038cc  and     r8d, 7Fh
0x1400038d0  jbe     short loc_1400038EA
0x1400038d2  cmp     r11d, ebx
0x1400038d5  mov     [r10+4], r8d
0x1400038d9  mov     edx, 5
0x1400038de  cmovnz  edx, ebx
0x1400038e1  and     eax, 0FFC07FFFh
0x1400038e6  mov     [r10+8], edx
0x1400038ea  xor     r8d, r8d
0x1400038ed  mov     edx, 400000h
0x1400038f2  cmp     r11d, 5
0x1400038f6  cmovz   r8d, edx
0x1400038fa  mov     edx, eax
0x1400038fc  btr     edx, 16h
0x140003900  mov     eax, r8d
0x140003903  or      eax, edx
0x140003905  mov     edx, eax
0x140003907  shr     edx, 0Fh
0x14000390a  and     edx, 7Fh
0x14000390d  lea     r8d, [rdx+1]
0x140003911  cmp     r8d, 7Fh
0x140003915  ja      short loc_14000391C
0x140003917  cmp     r8d, edx
0x14000391a  jnb     short loc_140003927
0x14000391c  mov     r8d, ebx
0x14000391f  mov     [r10+8], r11d
0x140003923  mov     [r10+4], edx
0x140003927  shl     r8d, 0Fh
0x14000392b  xor     r8d, eax
0x14000392e  and     r8d, 3F8000h
0x140003935  xor     r8d, eax
0x140003938  mov     eax, ecx
0x14000393a  lock cmpxchg [rsi], r8d
0x14000393f  jz      short loc_140003948
0x140003941  mov     ecx, eax
0x140003943  jmp     loc_1400038AD
0x140003948  not     ecx
0x14000394a  and     ecx, ebx
0x14000394c  mov     [r10], ecx
0x14000394f  jmp     loc_140003A1A
0x140003954  mov     edx, [rdx]
0x140003956  xor     ebp, ebp
0x140003958  lea     ecx, [rbp+4]
0x14000395b  cmp     r11d, ecx
0x14000395e  lea     ebx, [rcx-3]
0x140003961  setz    bpl
0x140003965  mov     eax, edx
0x140003967  mov     dword ptr [r10+4], 0
0x14000396f  or      eax, ebx
0x140003971  mov     r8d, eax
0x140003974  shr     r8d, 0Eh
0x140003978  and     r8d, ebx
0x14000397b  cmp     r8d, ebp
0x14000397e  jz      short loc_1400039C7
0x140003980  mov     edi, eax
0x140003982  shr     edi, 5
0x140003985  and     edi, 1FFh
0x14000398b  jbe     short loc_1400039A9
0x14000398d  mov     r8d, r11d
0x140003990  mov     [r10+4], edi
0x140003994  neg     r8d
0x140003997  sbb     r9d, r9d
0x14000399a  not     r9d
0x14000399d  and     r9d, ecx
0x1400039a0  mov     [r10+8], r9d
0x1400039a4  and     eax, 0FFFFC01Fh
0x1400039a9  xor     r9d, r9d
0x1400039ac  mov     r8d, 4000h
0x1400039b2  cmp     r11d, ecx
0x1400039b5  cmovz   r9d, r8d
0x1400039b9  mov     r8d, eax
0x1400039bc  btr     r8d, 0Eh
0x1400039c1  mov     eax, r9d
0x1400039c4  or      eax, r8d
0x1400039c7  mov     r8d, eax
0x1400039ca  shr     r8d, 5
0x1400039ce  and     r8d, 1FFh
0x1400039d5  lea     r9d, [r8+1]
0x1400039d9  cmp     r9d, 1FFh
0x1400039e0  ja      short loc_1400039E7
0x1400039e2  cmp     r9d, r8d
0x1400039e5  jnb     short loc_1400039F2
0x1400039e7  mov     r9d, ebx
0x1400039ea  mov     [r10+8], r11d
0x1400039ee  mov     [r10+4], r8d
0x1400039f2  shl     r9d, 5
0x1400039f6  xor     r9d, eax
0x1400039f9  and     r9d, 3FE0h
0x140003a00  xor     r9d, eax
0x140003a03  mov     eax, edx
0x140003a05  lock cmpxchg [rsi], r9d
0x140003a0a  jz      short loc_140003A13
0x140003a0c  mov     edx, eax
0x140003a0e  jmp     loc_140003965
0x140003a13  not     edx
0x140003a15  and     edx, ebx
0x140003a17  mov     [r10], edx
0x140003a1a  mov     dword ptr [r10+10h], 0
0x140003a22  mov     rax, r10
0x140003a25  pop     rdi
0x140003a26  pop     rsi
0x140003a27  pop     rbp
0x140003a28  pop     rbx
0x140003a29  retn
```

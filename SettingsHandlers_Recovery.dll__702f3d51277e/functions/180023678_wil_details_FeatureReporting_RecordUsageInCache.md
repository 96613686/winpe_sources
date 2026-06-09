# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180023678`
- end: `0x18002394a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ea10`
- `0x180028b94`

## callees

- `0x180023678`

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
0x180023678  push    rbx
0x18002367a  push    rbp
0x18002367b  push    rsi
0x18002367c  push    rdi
0x18002367d  xor     eax, eax
0x18002367f  xorps   xmm0, xmm0
0x180023682  mov     r10, rcx
0x180023685  mov     edi, r9d
0x180023688  mov     r11d, r8d
0x18002368b  mov     rsi, rdx
0x18002368e  movups  xmmword ptr [rcx], xmm0
0x180023691  mov     [rcx+10h], rax
0x180023695  mov     ecx, r8d
0x180023698  test    r8d, r8d
0x18002369b  jz      loc_180023874
0x1800236a1  sub     ecx, 1
0x1800236a4  jz      loc_1800237BB
0x1800236aa  sub     ecx, 1
0x1800236ad  jz      loc_180023742
0x1800236b3  sub     ecx, 1
0x1800236b6  jz      loc_180023742
0x1800236bc  sub     ecx, 1
0x1800236bf  jz      loc_180023874
0x1800236c5  sub     ecx, 1
0x1800236c8  jz      loc_1800237BB
0x1800236ce  sub     ecx, 1
0x1800236d1  jz      short loc_180023742
0x1800236d3  cmp     ecx, 1
0x1800236d6  jz      short loc_180023742
0x1800236d8  add     r8d, 0FFFFFEC0h
0x1800236df  lea     ebx, [rax+1]
0x1800236e2  cmp     r8d, 40h ; '@'
0x1800236e6  jge     short loc_180023731
0x1800236e8  mov     eax, [rdx+4]
0x1800236eb  lea     ecx, [rbx+0Fh]
0x1800236ee  mov     r9d, r8d
0x1800236f1  shl     r9d, 5
0x1800236f5  test    cl, al
0x1800236f7  jz      short loc_18002370A
0x1800236f9  mov     edx, eax
0x1800236fb  shr     edx, 5
0x1800236fe  and     edx, 3Fh
0x180023701  cmp     edx, r8d
0x180023704  jnz     short loc_18002370A
0x180023706  mov     edx, ebx
0x180023708  jmp     short loc_18002370C
0x18002370a  xor     edx, edx
0x18002370c  mov     [r10+10h], edx
0x180023710  mov     edx, r9d
0x180023713  xor     edx, eax
0x180023715  and     edx, 7E0h
0x18002371b  xor     edx, eax
0x18002371d  or      edx, ecx
0x18002371f  lock cmpxchg [rsi+4], edx
0x180023724  jnz     short loc_1800236F5
0x180023726  cmp     dword ptr [r10+10h], 0
0x18002372b  jnz     loc_180023942
0x180023731  mov     [r10+8], r11d
0x180023735  mov     [r10+4], ebx
0x180023739  mov     [r10+0Ch], edi
0x18002373d  jmp     loc_180023942
0x180023742  xor     ecx, ecx
0x180023744  sub     r11d, 2
0x180023748  jz      short loc_180023770
0x18002374a  sub     r11d, 1
0x18002374e  jz      short loc_180023769
0x180023750  sub     r11d, 3
0x180023754  jz      short loc_180023762
0x180023756  cmp     r11d, 1
0x18002375a  jnz     short loc_180023775
0x18002375c  lea     ecx, [r11+0Fh]
0x180023760  jmp     short loc_180023775
0x180023762  mov     ecx, 4
0x180023767  jmp     short loc_180023775
0x180023769  mov     ecx, 8
0x18002376e  jmp     short loc_180023775
0x180023770  mov     ecx, 2
0x180023775  mov     edx, [rdx]
0x180023777  mov     ebx, 1
0x18002377c  xor     eax, eax
0x18002377e  mov     r8d, ecx
0x180023781  or      r8d, edx
0x180023784  cmp     r8d, edx
0x180023787  mov     r9d, r8d
0x18002378a  setz    al
0x18002378d  or      r9d, ebx
0x180023790  cmp     r8d, edx
0x180023793  mov     [r10+10h], eax
0x180023797  mov     eax, edx
0x180023799  cmovz   r9d, r8d
0x18002379d  lock cmpxchg [rsi], r9d
0x1800237a2  jz      short loc_1800237A8
0x1800237a4  mov     edx, eax
0x1800237a6  jmp     short loc_18002377C
0x1800237a8  test    bl, r9b
0x1800237ab  jz      short loc_1800237B1
0x1800237ad  test    bl, dl
0x1800237af  jz      short loc_1800237B3
0x1800237b1  xor     ebx, ebx
0x1800237b3  mov     [r10], ebx
0x1800237b6  jmp     loc_180023942
0x1800237bb  mov     ecx, [rdx]
0x1800237bd  xor     r9d, r9d
0x1800237c0  cmp     r11d, 5
0x1800237c4  mov     ebx, 1
0x1800237c9  setz    r9b
0x1800237cd  mov     eax, ecx
0x1800237cf  mov     dword ptr [r10+4], 0
0x1800237d7  or      eax, ebx
0x1800237d9  mov     edx, eax
0x1800237db  shr     edx, 16h
0x1800237de  and     edx, ebx
0x1800237e0  cmp     edx, r9d
0x1800237e3  jz      short loc_180023825
0x1800237e5  mov     r8d, eax
0x1800237e8  shr     r8d, 0Fh
0x1800237ec  and     r8d, 7Fh
0x1800237f0  jbe     short loc_18002380A
0x1800237f2  cmp     r11d, ebx
0x1800237f5  mov     [r10+4], r8d
0x1800237f9  mov     edx, 5
0x1800237fe  cmovnz  edx, ebx
0x180023801  and     eax, 0FFC07FFFh
0x180023806  mov     [r10+8], edx
0x18002380a  xor     r8d, r8d
0x18002380d  mov     edx, 400000h
0x180023812  cmp     r11d, 5
0x180023816  cmovz   r8d, edx
0x18002381a  mov     edx, eax
0x18002381c  btr     edx, 16h
0x180023820  mov     eax, r8d
0x180023823  or      eax, edx
0x180023825  mov     edx, eax
0x180023827  shr     edx, 0Fh
0x18002382a  and     edx, 7Fh
0x18002382d  lea     r8d, [rdx+1]
0x180023831  cmp     r8d, 7Fh
0x180023835  ja      short loc_18002383C
0x180023837  cmp     r8d, edx
0x18002383a  jnb     short loc_180023847
0x18002383c  mov     r8d, ebx
0x18002383f  mov     [r10+8], r11d
0x180023843  mov     [r10+4], edx
0x180023847  shl     r8d, 0Fh
0x18002384b  xor     r8d, eax
0x18002384e  and     r8d, 3F8000h
0x180023855  xor     r8d, eax
0x180023858  mov     eax, ecx
0x18002385a  lock cmpxchg [rsi], r8d
0x18002385f  jz      short loc_180023868
0x180023861  mov     ecx, eax
0x180023863  jmp     loc_1800237CD
0x180023868  not     ecx
0x18002386a  and     ecx, ebx
0x18002386c  mov     [r10], ecx
0x18002386f  jmp     loc_18002393A
0x180023874  mov     edx, [rdx]
0x180023876  xor     ebp, ebp
0x180023878  lea     ecx, [rbp+4]
0x18002387b  cmp     r11d, ecx
0x18002387e  lea     ebx, [rcx-3]
0x180023881  setz    bpl
0x180023885  mov     eax, edx
0x180023887  mov     dword ptr [r10+4], 0
0x18002388f  or      eax, ebx
0x180023891  mov     r8d, eax
0x180023894  shr     r8d, 0Eh
0x180023898  and     r8d, ebx
0x18002389b  cmp     r8d, ebp
0x18002389e  jz      short loc_1800238E7
0x1800238a0  mov     edi, eax
0x1800238a2  shr     edi, 5
0x1800238a5  and     edi, 1FFh
0x1800238ab  jbe     short loc_1800238C9
0x1800238ad  mov     r8d, r11d
0x1800238b0  mov     [r10+4], edi
0x1800238b4  neg     r8d
0x1800238b7  sbb     r9d, r9d
0x1800238ba  not     r9d
0x1800238bd  and     r9d, ecx
0x1800238c0  mov     [r10+8], r9d
0x1800238c4  and     eax, 0FFFFC01Fh
0x1800238c9  xor     r9d, r9d
0x1800238cc  mov     r8d, 4000h
0x1800238d2  cmp     r11d, ecx
0x1800238d5  cmovz   r9d, r8d
0x1800238d9  mov     r8d, eax
0x1800238dc  btr     r8d, 0Eh
0x1800238e1  mov     eax, r9d
0x1800238e4  or      eax, r8d
0x1800238e7  mov     r8d, eax
0x1800238ea  shr     r8d, 5
0x1800238ee  and     r8d, 1FFh
0x1800238f5  lea     r9d, [r8+1]
0x1800238f9  cmp     r9d, 1FFh
0x180023900  ja      short loc_180023907
0x180023902  cmp     r9d, r8d
0x180023905  jnb     short loc_180023912
0x180023907  mov     r9d, ebx
0x18002390a  mov     [r10+8], r11d
0x18002390e  mov     [r10+4], r8d
0x180023912  shl     r9d, 5
0x180023916  xor     r9d, eax
0x180023919  and     r9d, 3FE0h
0x180023920  xor     r9d, eax
0x180023923  mov     eax, edx
0x180023925  lock cmpxchg [rsi], r9d
0x18002392a  jz      short loc_180023933
0x18002392c  mov     edx, eax
0x18002392e  jmp     loc_180023885
0x180023933  not     edx
0x180023935  and     edx, ebx
0x180023937  mov     [r10], edx
0x18002393a  mov     dword ptr [r10+10h], 0
0x180023942  mov     rax, r10
0x180023945  pop     rdi
0x180023946  pop     rsi
0x180023947  pop     rbp
0x180023948  pop     rbx
0x180023949  retn
```

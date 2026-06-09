# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000f898`
- end: `0x18000fb6a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fc8c`

## callees

- `0x18000f898`

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
0x18000f898  push    rbx
0x18000f89a  push    rbp
0x18000f89b  push    rsi
0x18000f89c  push    rdi
0x18000f89d  xor     eax, eax
0x18000f89f  xorps   xmm0, xmm0
0x18000f8a2  mov     r10, rcx
0x18000f8a5  mov     edi, r9d
0x18000f8a8  mov     r11d, r8d
0x18000f8ab  mov     rsi, rdx
0x18000f8ae  movups  xmmword ptr [rcx], xmm0
0x18000f8b1  mov     [rcx+10h], rax
0x18000f8b5  mov     ecx, r8d
0x18000f8b8  test    r8d, r8d
0x18000f8bb  jz      loc_18000FA94
0x18000f8c1  sub     ecx, 1
0x18000f8c4  jz      loc_18000F9DB
0x18000f8ca  sub     ecx, 1
0x18000f8cd  jz      loc_18000F962
0x18000f8d3  sub     ecx, 1
0x18000f8d6  jz      loc_18000F962
0x18000f8dc  sub     ecx, 1
0x18000f8df  jz      loc_18000FA94
0x18000f8e5  sub     ecx, 1
0x18000f8e8  jz      loc_18000F9DB
0x18000f8ee  sub     ecx, 1
0x18000f8f1  jz      short loc_18000F962
0x18000f8f3  cmp     ecx, 1
0x18000f8f6  jz      short loc_18000F962
0x18000f8f8  add     r8d, 0FFFFFEC0h
0x18000f8ff  lea     ebx, [rax+1]
0x18000f902  cmp     r8d, 40h ; '@'
0x18000f906  jge     short loc_18000F951
0x18000f908  mov     eax, [rdx+4]
0x18000f90b  lea     ecx, [rbx+0Fh]
0x18000f90e  mov     r9d, r8d
0x18000f911  shl     r9d, 5
0x18000f915  test    cl, al
0x18000f917  jz      short loc_18000F92A
0x18000f919  mov     edx, eax
0x18000f91b  shr     edx, 5
0x18000f91e  and     edx, 3Fh
0x18000f921  cmp     edx, r8d
0x18000f924  jnz     short loc_18000F92A
0x18000f926  mov     edx, ebx
0x18000f928  jmp     short loc_18000F92C
0x18000f92a  xor     edx, edx
0x18000f92c  mov     [r10+10h], edx
0x18000f930  mov     edx, r9d
0x18000f933  xor     edx, eax
0x18000f935  and     edx, 7E0h
0x18000f93b  xor     edx, eax
0x18000f93d  or      edx, ecx
0x18000f93f  lock cmpxchg [rsi+4], edx
0x18000f944  jnz     short loc_18000F915
0x18000f946  cmp     dword ptr [r10+10h], 0
0x18000f94b  jnz     loc_18000FB62
0x18000f951  mov     [r10+8], r11d
0x18000f955  mov     [r10+4], ebx
0x18000f959  mov     [r10+0Ch], edi
0x18000f95d  jmp     loc_18000FB62
0x18000f962  xor     ecx, ecx
0x18000f964  sub     r11d, 2
0x18000f968  jz      short loc_18000F990
0x18000f96a  sub     r11d, 1
0x18000f96e  jz      short loc_18000F989
0x18000f970  sub     r11d, 3
0x18000f974  jz      short loc_18000F982
0x18000f976  cmp     r11d, 1
0x18000f97a  jnz     short loc_18000F995
0x18000f97c  lea     ecx, [r11+0Fh]
0x18000f980  jmp     short loc_18000F995
0x18000f982  mov     ecx, 4
0x18000f987  jmp     short loc_18000F995
0x18000f989  mov     ecx, 8
0x18000f98e  jmp     short loc_18000F995
0x18000f990  mov     ecx, 2
0x18000f995  mov     edx, [rdx]
0x18000f997  mov     ebx, 1
0x18000f99c  xor     eax, eax
0x18000f99e  mov     r8d, ecx
0x18000f9a1  or      r8d, edx
0x18000f9a4  cmp     r8d, edx
0x18000f9a7  mov     r9d, r8d
0x18000f9aa  setz    al
0x18000f9ad  or      r9d, ebx
0x18000f9b0  cmp     r8d, edx
0x18000f9b3  mov     [r10+10h], eax
0x18000f9b7  mov     eax, edx
0x18000f9b9  cmovz   r9d, r8d
0x18000f9bd  lock cmpxchg [rsi], r9d
0x18000f9c2  jz      short loc_18000F9C8
0x18000f9c4  mov     edx, eax
0x18000f9c6  jmp     short loc_18000F99C
0x18000f9c8  test    bl, r9b
0x18000f9cb  jz      short loc_18000F9D1
0x18000f9cd  test    bl, dl
0x18000f9cf  jz      short loc_18000F9D3
0x18000f9d1  xor     ebx, ebx
0x18000f9d3  mov     [r10], ebx
0x18000f9d6  jmp     loc_18000FB62
0x18000f9db  mov     ecx, [rdx]
0x18000f9dd  xor     r9d, r9d
0x18000f9e0  cmp     r11d, 5
0x18000f9e4  mov     ebx, 1
0x18000f9e9  setz    r9b
0x18000f9ed  mov     eax, ecx
0x18000f9ef  mov     dword ptr [r10+4], 0
0x18000f9f7  or      eax, ebx
0x18000f9f9  mov     edx, eax
0x18000f9fb  shr     edx, 16h
0x18000f9fe  and     edx, ebx
0x18000fa00  cmp     edx, r9d
0x18000fa03  jz      short loc_18000FA45
0x18000fa05  mov     r8d, eax
0x18000fa08  shr     r8d, 0Fh
0x18000fa0c  and     r8d, 7Fh
0x18000fa10  jbe     short loc_18000FA2A
0x18000fa12  cmp     r11d, ebx
0x18000fa15  mov     [r10+4], r8d
0x18000fa19  mov     edx, 5
0x18000fa1e  cmovnz  edx, ebx
0x18000fa21  and     eax, 0FFC07FFFh
0x18000fa26  mov     [r10+8], edx
0x18000fa2a  xor     r8d, r8d
0x18000fa2d  mov     edx, 400000h
0x18000fa32  cmp     r11d, 5
0x18000fa36  cmovz   r8d, edx
0x18000fa3a  mov     edx, eax
0x18000fa3c  btr     edx, 16h
0x18000fa40  mov     eax, r8d
0x18000fa43  or      eax, edx
0x18000fa45  mov     edx, eax
0x18000fa47  shr     edx, 0Fh
0x18000fa4a  and     edx, 7Fh
0x18000fa4d  lea     r8d, [rdx+1]
0x18000fa51  cmp     r8d, 7Fh
0x18000fa55  ja      short loc_18000FA5C
0x18000fa57  cmp     r8d, edx
0x18000fa5a  jnb     short loc_18000FA67
0x18000fa5c  mov     r8d, ebx
0x18000fa5f  mov     [r10+8], r11d
0x18000fa63  mov     [r10+4], edx
0x18000fa67  shl     r8d, 0Fh
0x18000fa6b  xor     r8d, eax
0x18000fa6e  and     r8d, 3F8000h
0x18000fa75  xor     r8d, eax
0x18000fa78  mov     eax, ecx
0x18000fa7a  lock cmpxchg [rsi], r8d
0x18000fa7f  jz      short loc_18000FA88
0x18000fa81  mov     ecx, eax
0x18000fa83  jmp     loc_18000F9ED
0x18000fa88  not     ecx
0x18000fa8a  and     ecx, ebx
0x18000fa8c  mov     [r10], ecx
0x18000fa8f  jmp     loc_18000FB5A
0x18000fa94  mov     edx, [rdx]
0x18000fa96  xor     ebp, ebp
0x18000fa98  lea     ecx, [rbp+4]
0x18000fa9b  cmp     r11d, ecx
0x18000fa9e  lea     ebx, [rcx-3]
0x18000faa1  setz    bpl
0x18000faa5  mov     eax, edx
0x18000faa7  mov     dword ptr [r10+4], 0
0x18000faaf  or      eax, ebx
0x18000fab1  mov     r8d, eax
0x18000fab4  shr     r8d, 0Eh
0x18000fab8  and     r8d, ebx
0x18000fabb  cmp     r8d, ebp
0x18000fabe  jz      short loc_18000FB07
0x18000fac0  mov     edi, eax
0x18000fac2  shr     edi, 5
0x18000fac5  and     edi, 1FFh
0x18000facb  jbe     short loc_18000FAE9
0x18000facd  mov     r8d, r11d
0x18000fad0  mov     [r10+4], edi
0x18000fad4  neg     r8d
0x18000fad7  sbb     r9d, r9d
0x18000fada  not     r9d
0x18000fadd  and     r9d, ecx
0x18000fae0  mov     [r10+8], r9d
0x18000fae4  and     eax, 0FFFFC01Fh
0x18000fae9  xor     r9d, r9d
0x18000faec  mov     r8d, 4000h
0x18000faf2  cmp     r11d, ecx
0x18000faf5  cmovz   r9d, r8d
0x18000faf9  mov     r8d, eax
0x18000fafc  btr     r8d, 0Eh
0x18000fb01  mov     eax, r9d
0x18000fb04  or      eax, r8d
0x18000fb07  mov     r8d, eax
0x18000fb0a  shr     r8d, 5
0x18000fb0e  and     r8d, 1FFh
0x18000fb15  lea     r9d, [r8+1]
0x18000fb19  cmp     r9d, 1FFh
0x18000fb20  ja      short loc_18000FB27
0x18000fb22  cmp     r9d, r8d
0x18000fb25  jnb     short loc_18000FB32
0x18000fb27  mov     r9d, ebx
0x18000fb2a  mov     [r10+8], r11d
0x18000fb2e  mov     [r10+4], r8d
0x18000fb32  shl     r9d, 5
0x18000fb36  xor     r9d, eax
0x18000fb39  and     r9d, 3FE0h
0x18000fb40  xor     r9d, eax
0x18000fb43  mov     eax, edx
0x18000fb45  lock cmpxchg [rsi], r9d
0x18000fb4a  jz      short loc_18000FB53
0x18000fb4c  mov     edx, eax
0x18000fb4e  jmp     loc_18000FAA5
0x18000fb53  not     edx
0x18000fb55  and     edx, ebx
0x18000fb57  mov     [r10], edx
0x18000fb5a  mov     dword ptr [r10+10h], 0
0x18000fb62  mov     rax, r10
0x18000fb65  pop     rdi
0x18000fb66  pop     rsi
0x18000fb67  pop     rbp
0x18000fb68  pop     rbx
0x18000fb69  retn
```

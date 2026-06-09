# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180009c10`
- end: `0x180009eea`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009884`

## callees

- `0x180009c10`

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
0x180009c10  push    rbx
0x180009c12  push    rbp
0x180009c13  push    rsi
0x180009c14  push    rdi
0x180009c15  xor     eax, eax
0x180009c17  xorps   xmm0, xmm0
0x180009c1a  mov     r11d, r8d
0x180009c1d  mov     rsi, rdx
0x180009c20  mov     r10, rcx
0x180009c23  mov     r9d, r8d
0x180009c26  movups  xmmword ptr [rcx], xmm0
0x180009c29  mov     [rcx+10h], rax
0x180009c2d  test    r8d, r8d
0x180009c30  jz      loc_180009E14
0x180009c36  sub     r9d, 1
0x180009c3a  jz      loc_180009D5B
0x180009c40  sub     r9d, 1
0x180009c44  jz      loc_180009CE2
0x180009c4a  sub     r9d, 1
0x180009c4e  jz      loc_180009CE2
0x180009c54  sub     r9d, 1
0x180009c58  jz      loc_180009E14
0x180009c5e  sub     r9d, 1
0x180009c62  jz      loc_180009D5B
0x180009c68  sub     r9d, 1
0x180009c6c  jz      short loc_180009CE2
0x180009c6e  cmp     r9d, 1
0x180009c72  jz      short loc_180009CE2
0x180009c74  add     r8d, 0FFFFFEC0h
0x180009c7b  lea     ebx, [rax+1]
0x180009c7e  cmp     r8d, 40h ; '@'
0x180009c82  jge     short loc_180009CCD
0x180009c84  mov     eax, [rdx+4]
0x180009c87  lea     ecx, [rbx+0Fh]
0x180009c8a  mov     r9d, r8d
0x180009c8d  shl     r9d, 5
0x180009c91  test    cl, al
0x180009c93  jz      short loc_180009CA6
0x180009c95  mov     edx, eax
0x180009c97  shr     edx, 5
0x180009c9a  and     edx, 3Fh
0x180009c9d  cmp     edx, r8d
0x180009ca0  jnz     short loc_180009CA6
0x180009ca2  mov     edx, ebx
0x180009ca4  jmp     short loc_180009CA8
0x180009ca6  xor     edx, edx
0x180009ca8  mov     [r10+10h], edx
0x180009cac  mov     edx, r9d
0x180009caf  xor     edx, eax
0x180009cb1  and     edx, 7E0h
0x180009cb7  xor     edx, eax
0x180009cb9  or      edx, ecx
0x180009cbb  lock cmpxchg [rsi+4], edx
0x180009cc0  jnz     short loc_180009C91
0x180009cc2  cmp     dword ptr [r10+10h], 0
0x180009cc7  jnz     loc_180009EE2
0x180009ccd  mov     [r10+8], r11d
0x180009cd1  mov     [r10+4], ebx
0x180009cd5  mov     dword ptr [r10+0Ch], 0
0x180009cdd  jmp     loc_180009EE2
0x180009ce2  xor     ecx, ecx
0x180009ce4  sub     r11d, 2
0x180009ce8  jz      short loc_180009D10
0x180009cea  sub     r11d, 1
0x180009cee  jz      short loc_180009D09
0x180009cf0  sub     r11d, 3
0x180009cf4  jz      short loc_180009D02
0x180009cf6  cmp     r11d, 1
0x180009cfa  jnz     short loc_180009D15
0x180009cfc  lea     ecx, [r11+0Fh]
0x180009d00  jmp     short loc_180009D15
0x180009d02  mov     ecx, 4
0x180009d07  jmp     short loc_180009D15
0x180009d09  mov     ecx, 8
0x180009d0e  jmp     short loc_180009D15
0x180009d10  mov     ecx, 2
0x180009d15  mov     edx, [rdx]
0x180009d17  mov     ebx, 1
0x180009d1c  xor     eax, eax
0x180009d1e  mov     r8d, ecx
0x180009d21  or      r8d, edx
0x180009d24  cmp     r8d, edx
0x180009d27  mov     r9d, r8d
0x180009d2a  setz    al
0x180009d2d  or      r9d, ebx
0x180009d30  cmp     r8d, edx
0x180009d33  mov     [r10+10h], eax
0x180009d37  mov     eax, edx
0x180009d39  cmovz   r9d, r8d
0x180009d3d  lock cmpxchg [rsi], r9d
0x180009d42  jz      short loc_180009D48
0x180009d44  mov     edx, eax
0x180009d46  jmp     short loc_180009D1C
0x180009d48  test    bl, r9b
0x180009d4b  jz      short loc_180009D51
0x180009d4d  test    bl, dl
0x180009d4f  jz      short loc_180009D53
0x180009d51  xor     ebx, ebx
0x180009d53  mov     [r10], ebx
0x180009d56  jmp     loc_180009EE2
0x180009d5b  mov     ecx, [rdx]
0x180009d5d  xor     r9d, r9d
0x180009d60  cmp     r11d, 5
0x180009d64  mov     ebx, 1
0x180009d69  setz    r9b
0x180009d6d  mov     eax, ecx
0x180009d6f  mov     dword ptr [r10+4], 0
0x180009d77  or      eax, ebx
0x180009d79  mov     edx, eax
0x180009d7b  shr     edx, 16h
0x180009d7e  and     edx, ebx
0x180009d80  cmp     edx, r9d
0x180009d83  jz      short loc_180009DC5
0x180009d85  mov     r8d, eax
0x180009d88  shr     r8d, 0Fh
0x180009d8c  and     r8d, 7Fh
0x180009d90  jbe     short loc_180009DAA
0x180009d92  cmp     r11d, ebx
0x180009d95  mov     [r10+4], r8d
0x180009d99  mov     edx, 5
0x180009d9e  cmovnz  edx, ebx
0x180009da1  and     eax, 0FFC07FFFh
0x180009da6  mov     [r10+8], edx
0x180009daa  xor     r8d, r8d
0x180009dad  mov     edx, 400000h
0x180009db2  cmp     r11d, 5
0x180009db6  cmovz   r8d, edx
0x180009dba  mov     edx, eax
0x180009dbc  btr     edx, 16h
0x180009dc0  mov     eax, r8d
0x180009dc3  or      eax, edx
0x180009dc5  mov     edx, eax
0x180009dc7  shr     edx, 0Fh
0x180009dca  and     edx, 7Fh
0x180009dcd  lea     r8d, [rdx+1]
0x180009dd1  cmp     r8d, 7Fh
0x180009dd5  ja      short loc_180009DDC
0x180009dd7  cmp     r8d, edx
0x180009dda  jnb     short loc_180009DE7
0x180009ddc  mov     r8d, ebx
0x180009ddf  mov     [r10+8], r11d
0x180009de3  mov     [r10+4], edx
0x180009de7  shl     r8d, 0Fh
0x180009deb  xor     r8d, eax
0x180009dee  and     r8d, 3F8000h
0x180009df5  xor     r8d, eax
0x180009df8  mov     eax, ecx
0x180009dfa  lock cmpxchg [rsi], r8d
0x180009dff  jz      short loc_180009E08
0x180009e01  mov     ecx, eax
0x180009e03  jmp     loc_180009D6D
0x180009e08  not     ecx
0x180009e0a  and     ecx, ebx
0x180009e0c  mov     [r10], ecx
0x180009e0f  jmp     loc_180009EDA
0x180009e14  mov     edx, [rdx]
0x180009e16  xor     ebp, ebp
0x180009e18  lea     ecx, [rbp+4]
0x180009e1b  cmp     r11d, ecx
0x180009e1e  lea     ebx, [rcx-3]
0x180009e21  setz    bpl
0x180009e25  mov     eax, edx
0x180009e27  mov     dword ptr [r10+4], 0
0x180009e2f  or      eax, ebx
0x180009e31  mov     r8d, eax
0x180009e34  shr     r8d, 0Eh
0x180009e38  and     r8d, ebx
0x180009e3b  cmp     r8d, ebp
0x180009e3e  jz      short loc_180009E87
0x180009e40  mov     edi, eax
0x180009e42  shr     edi, 5
0x180009e45  and     edi, 1FFh
0x180009e4b  jbe     short loc_180009E69
0x180009e4d  mov     r8d, r11d
0x180009e50  mov     [r10+4], edi
0x180009e54  neg     r8d
0x180009e57  sbb     r9d, r9d
0x180009e5a  not     r9d
0x180009e5d  and     r9d, ecx
0x180009e60  mov     [r10+8], r9d
0x180009e64  and     eax, 0FFFFC01Fh
0x180009e69  xor     r9d, r9d
0x180009e6c  mov     r8d, 4000h
0x180009e72  cmp     r11d, ecx
0x180009e75  cmovz   r9d, r8d
0x180009e79  mov     r8d, eax
0x180009e7c  btr     r8d, 0Eh
0x180009e81  mov     eax, r9d
0x180009e84  or      eax, r8d
0x180009e87  mov     r8d, eax
0x180009e8a  shr     r8d, 5
0x180009e8e  and     r8d, 1FFh
0x180009e95  lea     r9d, [r8+1]
0x180009e99  cmp     r9d, 1FFh
0x180009ea0  ja      short loc_180009EA7
0x180009ea2  cmp     r9d, r8d
0x180009ea5  jnb     short loc_180009EB2
0x180009ea7  mov     r9d, ebx
0x180009eaa  mov     [r10+8], r11d
0x180009eae  mov     [r10+4], r8d
0x180009eb2  shl     r9d, 5
0x180009eb6  xor     r9d, eax
0x180009eb9  and     r9d, 3FE0h
0x180009ec0  xor     r9d, eax
0x180009ec3  mov     eax, edx
0x180009ec5  lock cmpxchg [rsi], r9d
0x180009eca  jz      short loc_180009ED3
0x180009ecc  mov     edx, eax
0x180009ece  jmp     loc_180009E25
0x180009ed3  not     edx
0x180009ed5  and     edx, ebx
0x180009ed7  mov     [r10], edx
0x180009eda  mov     dword ptr [r10+10h], 0
0x180009ee2  mov     rax, r10
0x180009ee5  pop     rdi
0x180009ee6  pop     rsi
0x180009ee7  pop     rbp
0x180009ee8  pop     rbx
0x180009ee9  retn
```

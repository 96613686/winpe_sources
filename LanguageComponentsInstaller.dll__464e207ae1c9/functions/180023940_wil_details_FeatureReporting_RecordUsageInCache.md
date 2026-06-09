# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180023940`
- end: `0x180023c12`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b218`
- `0x180027740`

## callees

- `0x180023940`

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
0x180023940  push    rbx
0x180023942  push    rbp
0x180023943  push    rsi
0x180023944  push    rdi
0x180023945  xor     eax, eax
0x180023947  xorps   xmm0, xmm0
0x18002394a  mov     r10, rcx
0x18002394d  mov     edi, r9d
0x180023950  mov     r11d, r8d
0x180023953  mov     rsi, rdx
0x180023956  movups  xmmword ptr [rcx], xmm0
0x180023959  mov     [rcx+10h], rax
0x18002395d  mov     ecx, r8d
0x180023960  test    r8d, r8d
0x180023963  jz      loc_180023B3C
0x180023969  sub     ecx, 1
0x18002396c  jz      loc_180023A83
0x180023972  sub     ecx, 1
0x180023975  jz      loc_180023A0A
0x18002397b  sub     ecx, 1
0x18002397e  jz      loc_180023A0A
0x180023984  sub     ecx, 1
0x180023987  jz      loc_180023B3C
0x18002398d  sub     ecx, 1
0x180023990  jz      loc_180023A83
0x180023996  sub     ecx, 1
0x180023999  jz      short loc_180023A0A
0x18002399b  cmp     ecx, 1
0x18002399e  jz      short loc_180023A0A
0x1800239a0  add     r8d, 0FFFFFEC0h
0x1800239a7  lea     ebx, [rax+1]
0x1800239aa  cmp     r8d, 40h ; '@'
0x1800239ae  jge     short loc_1800239F9
0x1800239b0  mov     eax, [rdx+4]
0x1800239b3  lea     ecx, [rbx+0Fh]
0x1800239b6  mov     r9d, r8d
0x1800239b9  shl     r9d, 5
0x1800239bd  test    cl, al
0x1800239bf  jz      short loc_1800239D2
0x1800239c1  mov     edx, eax
0x1800239c3  shr     edx, 5
0x1800239c6  and     edx, 3Fh
0x1800239c9  cmp     edx, r8d
0x1800239cc  jnz     short loc_1800239D2
0x1800239ce  mov     edx, ebx
0x1800239d0  jmp     short loc_1800239D4
0x1800239d2  xor     edx, edx
0x1800239d4  mov     [r10+10h], edx
0x1800239d8  mov     edx, r9d
0x1800239db  xor     edx, eax
0x1800239dd  and     edx, 7E0h
0x1800239e3  xor     edx, eax
0x1800239e5  or      edx, ecx
0x1800239e7  lock cmpxchg [rsi+4], edx
0x1800239ec  jnz     short loc_1800239BD
0x1800239ee  cmp     dword ptr [r10+10h], 0
0x1800239f3  jnz     loc_180023C0A
0x1800239f9  mov     [r10+8], r11d
0x1800239fd  mov     [r10+4], ebx
0x180023a01  mov     [r10+0Ch], edi
0x180023a05  jmp     loc_180023C0A
0x180023a0a  xor     ecx, ecx
0x180023a0c  sub     r11d, 2
0x180023a10  jz      short loc_180023A38
0x180023a12  sub     r11d, 1
0x180023a16  jz      short loc_180023A31
0x180023a18  sub     r11d, 3
0x180023a1c  jz      short loc_180023A2A
0x180023a1e  cmp     r11d, 1
0x180023a22  jnz     short loc_180023A3D
0x180023a24  lea     ecx, [r11+0Fh]
0x180023a28  jmp     short loc_180023A3D
0x180023a2a  mov     ecx, 4
0x180023a2f  jmp     short loc_180023A3D
0x180023a31  mov     ecx, 8
0x180023a36  jmp     short loc_180023A3D
0x180023a38  mov     ecx, 2
0x180023a3d  mov     edx, [rdx]
0x180023a3f  mov     ebx, 1
0x180023a44  xor     eax, eax
0x180023a46  mov     r8d, ecx
0x180023a49  or      r8d, edx
0x180023a4c  cmp     r8d, edx
0x180023a4f  mov     r9d, r8d
0x180023a52  setz    al
0x180023a55  or      r9d, ebx
0x180023a58  cmp     r8d, edx
0x180023a5b  mov     [r10+10h], eax
0x180023a5f  mov     eax, edx
0x180023a61  cmovz   r9d, r8d
0x180023a65  lock cmpxchg [rsi], r9d
0x180023a6a  jz      short loc_180023A70
0x180023a6c  mov     edx, eax
0x180023a6e  jmp     short loc_180023A44
0x180023a70  test    bl, r9b
0x180023a73  jz      short loc_180023A79
0x180023a75  test    bl, dl
0x180023a77  jz      short loc_180023A7B
0x180023a79  xor     ebx, ebx
0x180023a7b  mov     [r10], ebx
0x180023a7e  jmp     loc_180023C0A
0x180023a83  mov     ecx, [rdx]
0x180023a85  xor     r9d, r9d
0x180023a88  cmp     r11d, 5
0x180023a8c  mov     ebx, 1
0x180023a91  setz    r9b
0x180023a95  mov     eax, ecx
0x180023a97  mov     dword ptr [r10+4], 0
0x180023a9f  or      eax, ebx
0x180023aa1  mov     edx, eax
0x180023aa3  shr     edx, 16h
0x180023aa6  and     edx, ebx
0x180023aa8  cmp     edx, r9d
0x180023aab  jz      short loc_180023AED
0x180023aad  mov     r8d, eax
0x180023ab0  shr     r8d, 0Fh
0x180023ab4  and     r8d, 7Fh
0x180023ab8  jbe     short loc_180023AD2
0x180023aba  cmp     r11d, ebx
0x180023abd  mov     [r10+4], r8d
0x180023ac1  mov     edx, 5
0x180023ac6  cmovnz  edx, ebx
0x180023ac9  and     eax, 0FFC07FFFh
0x180023ace  mov     [r10+8], edx
0x180023ad2  xor     r8d, r8d
0x180023ad5  mov     edx, 400000h
0x180023ada  cmp     r11d, 5
0x180023ade  cmovz   r8d, edx
0x180023ae2  mov     edx, eax
0x180023ae4  btr     edx, 16h
0x180023ae8  mov     eax, r8d
0x180023aeb  or      eax, edx
0x180023aed  mov     edx, eax
0x180023aef  shr     edx, 0Fh
0x180023af2  and     edx, 7Fh
0x180023af5  lea     r8d, [rdx+1]
0x180023af9  cmp     r8d, 7Fh
0x180023afd  ja      short loc_180023B04
0x180023aff  cmp     r8d, edx
0x180023b02  jnb     short loc_180023B0F
0x180023b04  mov     r8d, ebx
0x180023b07  mov     [r10+8], r11d
0x180023b0b  mov     [r10+4], edx
0x180023b0f  shl     r8d, 0Fh
0x180023b13  xor     r8d, eax
0x180023b16  and     r8d, 3F8000h
0x180023b1d  xor     r8d, eax
0x180023b20  mov     eax, ecx
0x180023b22  lock cmpxchg [rsi], r8d
0x180023b27  jz      short loc_180023B30
0x180023b29  mov     ecx, eax
0x180023b2b  jmp     loc_180023A95
0x180023b30  not     ecx
0x180023b32  and     ecx, ebx
0x180023b34  mov     [r10], ecx
0x180023b37  jmp     loc_180023C02
0x180023b3c  mov     edx, [rdx]
0x180023b3e  xor     ebp, ebp
0x180023b40  lea     ecx, [rbp+4]
0x180023b43  cmp     r11d, ecx
0x180023b46  lea     ebx, [rcx-3]
0x180023b49  setz    bpl
0x180023b4d  mov     eax, edx
0x180023b4f  mov     dword ptr [r10+4], 0
0x180023b57  or      eax, ebx
0x180023b59  mov     r8d, eax
0x180023b5c  shr     r8d, 0Eh
0x180023b60  and     r8d, ebx
0x180023b63  cmp     r8d, ebp
0x180023b66  jz      short loc_180023BAF
0x180023b68  mov     edi, eax
0x180023b6a  shr     edi, 5
0x180023b6d  and     edi, 1FFh
0x180023b73  jbe     short loc_180023B91
0x180023b75  mov     r8d, r11d
0x180023b78  mov     [r10+4], edi
0x180023b7c  neg     r8d
0x180023b7f  sbb     r9d, r9d
0x180023b82  not     r9d
0x180023b85  and     r9d, ecx
0x180023b88  mov     [r10+8], r9d
0x180023b8c  and     eax, 0FFFFC01Fh
0x180023b91  xor     r9d, r9d
0x180023b94  mov     r8d, 4000h
0x180023b9a  cmp     r11d, ecx
0x180023b9d  cmovz   r9d, r8d
0x180023ba1  mov     r8d, eax
0x180023ba4  btr     r8d, 0Eh
0x180023ba9  mov     eax, r9d
0x180023bac  or      eax, r8d
0x180023baf  mov     r8d, eax
0x180023bb2  shr     r8d, 5
0x180023bb6  and     r8d, 1FFh
0x180023bbd  lea     r9d, [r8+1]
0x180023bc1  cmp     r9d, 1FFh
0x180023bc8  ja      short loc_180023BCF
0x180023bca  cmp     r9d, r8d
0x180023bcd  jnb     short loc_180023BDA
0x180023bcf  mov     r9d, ebx
0x180023bd2  mov     [r10+8], r11d
0x180023bd6  mov     [r10+4], r8d
0x180023bda  shl     r9d, 5
0x180023bde  xor     r9d, eax
0x180023be1  and     r9d, 3FE0h
0x180023be8  xor     r9d, eax
0x180023beb  mov     eax, edx
0x180023bed  lock cmpxchg [rsi], r9d
0x180023bf2  jz      short loc_180023BFB
0x180023bf4  mov     edx, eax
0x180023bf6  jmp     loc_180023B4D
0x180023bfb  not     edx
0x180023bfd  and     edx, ebx
0x180023bff  mov     [r10], edx
0x180023c02  mov     dword ptr [r10+10h], 0
0x180023c0a  mov     rax, r10
0x180023c0d  pop     rdi
0x180023c0e  pop     rsi
0x180023c0f  pop     rbp
0x180023c10  pop     rbx
0x180023c11  retn
```

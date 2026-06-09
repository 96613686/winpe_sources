# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000aec0`
- end: `0x14000b19a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400090c0`

## callees

- `0x14000aec0`

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
0x14000aec0  push    rbx
0x14000aec2  push    rbp
0x14000aec3  push    rsi
0x14000aec4  push    rdi
0x14000aec5  xor     eax, eax
0x14000aec7  xorps   xmm0, xmm0
0x14000aeca  mov     r11d, r8d
0x14000aecd  mov     rsi, rdx
0x14000aed0  mov     r10, rcx
0x14000aed3  mov     r9d, r8d
0x14000aed6  movups  xmmword ptr [rcx], xmm0
0x14000aed9  mov     [rcx+10h], rax
0x14000aedd  test    r8d, r8d
0x14000aee0  jz      loc_14000B0C4
0x14000aee6  sub     r9d, 1
0x14000aeea  jz      loc_14000B00B
0x14000aef0  sub     r9d, 1
0x14000aef4  jz      loc_14000AF92
0x14000aefa  sub     r9d, 1
0x14000aefe  jz      loc_14000AF92
0x14000af04  sub     r9d, 1
0x14000af08  jz      loc_14000B0C4
0x14000af0e  sub     r9d, 1
0x14000af12  jz      loc_14000B00B
0x14000af18  sub     r9d, 1
0x14000af1c  jz      short loc_14000AF92
0x14000af1e  cmp     r9d, 1
0x14000af22  jz      short loc_14000AF92
0x14000af24  add     r8d, 0FFFFFEC0h
0x14000af2b  lea     ebx, [rax+1]
0x14000af2e  cmp     r8d, 40h ; '@'
0x14000af32  jge     short loc_14000AF7D
0x14000af34  mov     eax, [rdx+4]
0x14000af37  lea     ecx, [rbx+0Fh]
0x14000af3a  mov     r9d, r8d
0x14000af3d  shl     r9d, 5
0x14000af41  test    cl, al
0x14000af43  jz      short loc_14000AF56
0x14000af45  mov     edx, eax
0x14000af47  shr     edx, 5
0x14000af4a  and     edx, 3Fh
0x14000af4d  cmp     edx, r8d
0x14000af50  jnz     short loc_14000AF56
0x14000af52  mov     edx, ebx
0x14000af54  jmp     short loc_14000AF58
0x14000af56  xor     edx, edx
0x14000af58  mov     [r10+10h], edx
0x14000af5c  mov     edx, r9d
0x14000af5f  xor     edx, eax
0x14000af61  and     edx, 7E0h
0x14000af67  xor     edx, eax
0x14000af69  or      edx, ecx
0x14000af6b  lock cmpxchg [rsi+4], edx
0x14000af70  jnz     short loc_14000AF41
0x14000af72  cmp     dword ptr [r10+10h], 0
0x14000af77  jnz     loc_14000B192
0x14000af7d  mov     [r10+8], r11d
0x14000af81  mov     [r10+4], ebx
0x14000af85  mov     dword ptr [r10+0Ch], 0
0x14000af8d  jmp     loc_14000B192
0x14000af92  xor     ecx, ecx
0x14000af94  sub     r11d, 2
0x14000af98  jz      short loc_14000AFC0
0x14000af9a  sub     r11d, 1
0x14000af9e  jz      short loc_14000AFB9
0x14000afa0  sub     r11d, 3
0x14000afa4  jz      short loc_14000AFB2
0x14000afa6  cmp     r11d, 1
0x14000afaa  jnz     short loc_14000AFC5
0x14000afac  lea     ecx, [r11+0Fh]
0x14000afb0  jmp     short loc_14000AFC5
0x14000afb2  mov     ecx, 4
0x14000afb7  jmp     short loc_14000AFC5
0x14000afb9  mov     ecx, 8
0x14000afbe  jmp     short loc_14000AFC5
0x14000afc0  mov     ecx, 2
0x14000afc5  mov     edx, [rdx]
0x14000afc7  mov     ebx, 1
0x14000afcc  xor     eax, eax
0x14000afce  mov     r8d, ecx
0x14000afd1  or      r8d, edx
0x14000afd4  cmp     r8d, edx
0x14000afd7  mov     r9d, r8d
0x14000afda  setz    al
0x14000afdd  or      r9d, ebx
0x14000afe0  cmp     r8d, edx
0x14000afe3  mov     [r10+10h], eax
0x14000afe7  mov     eax, edx
0x14000afe9  cmovz   r9d, r8d
0x14000afed  lock cmpxchg [rsi], r9d
0x14000aff2  jz      short loc_14000AFF8
0x14000aff4  mov     edx, eax
0x14000aff6  jmp     short loc_14000AFCC
0x14000aff8  test    bl, r9b
0x14000affb  jz      short loc_14000B001
0x14000affd  test    bl, dl
0x14000afff  jz      short loc_14000B003
0x14000b001  xor     ebx, ebx
0x14000b003  mov     [r10], ebx
0x14000b006  jmp     loc_14000B192
0x14000b00b  mov     ecx, [rdx]
0x14000b00d  xor     r9d, r9d
0x14000b010  cmp     r11d, 5
0x14000b014  mov     ebx, 1
0x14000b019  setz    r9b
0x14000b01d  mov     eax, ecx
0x14000b01f  mov     dword ptr [r10+4], 0
0x14000b027  or      eax, ebx
0x14000b029  mov     edx, eax
0x14000b02b  shr     edx, 16h
0x14000b02e  and     edx, ebx
0x14000b030  cmp     edx, r9d
0x14000b033  jz      short loc_14000B075
0x14000b035  mov     r8d, eax
0x14000b038  shr     r8d, 0Fh
0x14000b03c  and     r8d, 7Fh
0x14000b040  jbe     short loc_14000B05A
0x14000b042  cmp     r11d, ebx
0x14000b045  mov     [r10+4], r8d
0x14000b049  mov     edx, 5
0x14000b04e  cmovnz  edx, ebx
0x14000b051  and     eax, 0FFC07FFFh
0x14000b056  mov     [r10+8], edx
0x14000b05a  xor     r8d, r8d
0x14000b05d  mov     edx, 400000h
0x14000b062  cmp     r11d, 5
0x14000b066  cmovz   r8d, edx
0x14000b06a  mov     edx, eax
0x14000b06c  btr     edx, 16h
0x14000b070  mov     eax, r8d
0x14000b073  or      eax, edx
0x14000b075  mov     edx, eax
0x14000b077  shr     edx, 0Fh
0x14000b07a  and     edx, 7Fh
0x14000b07d  lea     r8d, [rdx+1]
0x14000b081  cmp     r8d, 7Fh
0x14000b085  ja      short loc_14000B08C
0x14000b087  cmp     r8d, edx
0x14000b08a  jnb     short loc_14000B097
0x14000b08c  mov     r8d, ebx
0x14000b08f  mov     [r10+8], r11d
0x14000b093  mov     [r10+4], edx
0x14000b097  shl     r8d, 0Fh
0x14000b09b  xor     r8d, eax
0x14000b09e  and     r8d, 3F8000h
0x14000b0a5  xor     r8d, eax
0x14000b0a8  mov     eax, ecx
0x14000b0aa  lock cmpxchg [rsi], r8d
0x14000b0af  jz      short loc_14000B0B8
0x14000b0b1  mov     ecx, eax
0x14000b0b3  jmp     loc_14000B01D
0x14000b0b8  not     ecx
0x14000b0ba  and     ecx, ebx
0x14000b0bc  mov     [r10], ecx
0x14000b0bf  jmp     loc_14000B18A
0x14000b0c4  mov     edx, [rdx]
0x14000b0c6  xor     ebp, ebp
0x14000b0c8  lea     ecx, [rbp+4]
0x14000b0cb  cmp     r11d, ecx
0x14000b0ce  lea     ebx, [rcx-3]
0x14000b0d1  setz    bpl
0x14000b0d5  mov     eax, edx
0x14000b0d7  mov     dword ptr [r10+4], 0
0x14000b0df  or      eax, ebx
0x14000b0e1  mov     r8d, eax
0x14000b0e4  shr     r8d, 0Eh
0x14000b0e8  and     r8d, ebx
0x14000b0eb  cmp     r8d, ebp
0x14000b0ee  jz      short loc_14000B137
0x14000b0f0  mov     edi, eax
0x14000b0f2  shr     edi, 5
0x14000b0f5  and     edi, 1FFh
0x14000b0fb  jbe     short loc_14000B119
0x14000b0fd  mov     r8d, r11d
0x14000b100  mov     [r10+4], edi
0x14000b104  neg     r8d
0x14000b107  sbb     r9d, r9d
0x14000b10a  not     r9d
0x14000b10d  and     r9d, ecx
0x14000b110  mov     [r10+8], r9d
0x14000b114  and     eax, 0FFFFC01Fh
0x14000b119  xor     r9d, r9d
0x14000b11c  mov     r8d, 4000h
0x14000b122  cmp     r11d, ecx
0x14000b125  cmovz   r9d, r8d
0x14000b129  mov     r8d, eax
0x14000b12c  btr     r8d, 0Eh
0x14000b131  mov     eax, r9d
0x14000b134  or      eax, r8d
0x14000b137  mov     r8d, eax
0x14000b13a  shr     r8d, 5
0x14000b13e  and     r8d, 1FFh
0x14000b145  lea     r9d, [r8+1]
0x14000b149  cmp     r9d, 1FFh
0x14000b150  ja      short loc_14000B157
0x14000b152  cmp     r9d, r8d
0x14000b155  jnb     short loc_14000B162
0x14000b157  mov     r9d, ebx
0x14000b15a  mov     [r10+8], r11d
0x14000b15e  mov     [r10+4], r8d
0x14000b162  shl     r9d, 5
0x14000b166  xor     r9d, eax
0x14000b169  and     r9d, 3FE0h
0x14000b170  xor     r9d, eax
0x14000b173  mov     eax, edx
0x14000b175  lock cmpxchg [rsi], r9d
0x14000b17a  jz      short loc_14000B183
0x14000b17c  mov     edx, eax
0x14000b17e  jmp     loc_14000B0D5
0x14000b183  not     edx
0x14000b185  and     edx, ebx
0x14000b187  mov     [r10], edx
0x14000b18a  mov     dword ptr [r10+10h], 0
0x14000b192  mov     rax, r10
0x14000b195  pop     rdi
0x14000b196  pop     rsi
0x14000b197  pop     rbp
0x14000b198  pop     rbx
0x14000b199  retn
```

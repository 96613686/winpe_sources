# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000fe80`
- end: `0x18001015a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bc10`

## callees

- `0x18000fe80`

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
0x18000fe80  push    rbx
0x18000fe82  push    rbp
0x18000fe83  push    rsi
0x18000fe84  push    rdi
0x18000fe85  xor     eax, eax
0x18000fe87  xorps   xmm0, xmm0
0x18000fe8a  mov     r11d, r8d
0x18000fe8d  mov     rsi, rdx
0x18000fe90  mov     r10, rcx
0x18000fe93  mov     r9d, r8d
0x18000fe96  movups  xmmword ptr [rcx], xmm0
0x18000fe99  mov     [rcx+10h], rax
0x18000fe9d  test    r8d, r8d
0x18000fea0  jz      loc_180010084
0x18000fea6  sub     r9d, 1
0x18000feaa  jz      loc_18000FFCB
0x18000feb0  sub     r9d, 1
0x18000feb4  jz      loc_18000FF52
0x18000feba  sub     r9d, 1
0x18000febe  jz      loc_18000FF52
0x18000fec4  sub     r9d, 1
0x18000fec8  jz      loc_180010084
0x18000fece  sub     r9d, 1
0x18000fed2  jz      loc_18000FFCB
0x18000fed8  sub     r9d, 1
0x18000fedc  jz      short loc_18000FF52
0x18000fede  cmp     r9d, 1
0x18000fee2  jz      short loc_18000FF52
0x18000fee4  add     r8d, 0FFFFFEC0h
0x18000feeb  lea     ebx, [rax+1]
0x18000feee  cmp     r8d, 40h ; '@'
0x18000fef2  jge     short loc_18000FF3D
0x18000fef4  mov     eax, [rdx+4]
0x18000fef7  lea     ecx, [rbx+0Fh]
0x18000fefa  mov     r9d, r8d
0x18000fefd  shl     r9d, 5
0x18000ff01  test    cl, al
0x18000ff03  jz      short loc_18000FF16
0x18000ff05  mov     edx, eax
0x18000ff07  shr     edx, 5
0x18000ff0a  and     edx, 3Fh
0x18000ff0d  cmp     edx, r8d
0x18000ff10  jnz     short loc_18000FF16
0x18000ff12  mov     edx, ebx
0x18000ff14  jmp     short loc_18000FF18
0x18000ff16  xor     edx, edx
0x18000ff18  mov     [r10+10h], edx
0x18000ff1c  mov     edx, r9d
0x18000ff1f  xor     edx, eax
0x18000ff21  and     edx, 7E0h
0x18000ff27  xor     edx, eax
0x18000ff29  or      edx, ecx
0x18000ff2b  lock cmpxchg [rsi+4], edx
0x18000ff30  jnz     short loc_18000FF01
0x18000ff32  cmp     dword ptr [r10+10h], 0
0x18000ff37  jnz     loc_180010152
0x18000ff3d  mov     [r10+8], r11d
0x18000ff41  mov     [r10+4], ebx
0x18000ff45  mov     dword ptr [r10+0Ch], 0
0x18000ff4d  jmp     loc_180010152
0x18000ff52  xor     ecx, ecx
0x18000ff54  sub     r11d, 2
0x18000ff58  jz      short loc_18000FF80
0x18000ff5a  sub     r11d, 1
0x18000ff5e  jz      short loc_18000FF79
0x18000ff60  sub     r11d, 3
0x18000ff64  jz      short loc_18000FF72
0x18000ff66  cmp     r11d, 1
0x18000ff6a  jnz     short loc_18000FF85
0x18000ff6c  lea     ecx, [r11+0Fh]
0x18000ff70  jmp     short loc_18000FF85
0x18000ff72  mov     ecx, 4
0x18000ff77  jmp     short loc_18000FF85
0x18000ff79  mov     ecx, 8
0x18000ff7e  jmp     short loc_18000FF85
0x18000ff80  mov     ecx, 2
0x18000ff85  mov     edx, [rdx]
0x18000ff87  mov     ebx, 1
0x18000ff8c  xor     eax, eax
0x18000ff8e  mov     r8d, ecx
0x18000ff91  or      r8d, edx
0x18000ff94  cmp     r8d, edx
0x18000ff97  mov     r9d, r8d
0x18000ff9a  setz    al
0x18000ff9d  or      r9d, ebx
0x18000ffa0  cmp     r8d, edx
0x18000ffa3  mov     [r10+10h], eax
0x18000ffa7  mov     eax, edx
0x18000ffa9  cmovz   r9d, r8d
0x18000ffad  lock cmpxchg [rsi], r9d
0x18000ffb2  jz      short loc_18000FFB8
0x18000ffb4  mov     edx, eax
0x18000ffb6  jmp     short loc_18000FF8C
0x18000ffb8  test    bl, r9b
0x18000ffbb  jz      short loc_18000FFC1
0x18000ffbd  test    bl, dl
0x18000ffbf  jz      short loc_18000FFC3
0x18000ffc1  xor     ebx, ebx
0x18000ffc3  mov     [r10], ebx
0x18000ffc6  jmp     loc_180010152
0x18000ffcb  mov     ecx, [rdx]
0x18000ffcd  xor     r9d, r9d
0x18000ffd0  cmp     r11d, 5
0x18000ffd4  mov     ebx, 1
0x18000ffd9  setz    r9b
0x18000ffdd  mov     eax, ecx
0x18000ffdf  mov     dword ptr [r10+4], 0
0x18000ffe7  or      eax, ebx
0x18000ffe9  mov     edx, eax
0x18000ffeb  shr     edx, 16h
0x18000ffee  and     edx, ebx
0x18000fff0  cmp     edx, r9d
0x18000fff3  jz      short loc_180010035
0x18000fff5  mov     r8d, eax
0x18000fff8  shr     r8d, 0Fh
0x18000fffc  and     r8d, 7Fh
0x180010000  jbe     short loc_18001001A
0x180010002  cmp     r11d, ebx
0x180010005  mov     [r10+4], r8d
0x180010009  mov     edx, 5
0x18001000e  cmovnz  edx, ebx
0x180010011  and     eax, 0FFC07FFFh
0x180010016  mov     [r10+8], edx
0x18001001a  xor     r8d, r8d
0x18001001d  mov     edx, 400000h
0x180010022  cmp     r11d, 5
0x180010026  cmovz   r8d, edx
0x18001002a  mov     edx, eax
0x18001002c  btr     edx, 16h
0x180010030  mov     eax, r8d
0x180010033  or      eax, edx
0x180010035  mov     edx, eax
0x180010037  shr     edx, 0Fh
0x18001003a  and     edx, 7Fh
0x18001003d  lea     r8d, [rdx+1]
0x180010041  cmp     r8d, 7Fh
0x180010045  ja      short loc_18001004C
0x180010047  cmp     r8d, edx
0x18001004a  jnb     short loc_180010057
0x18001004c  mov     r8d, ebx
0x18001004f  mov     [r10+8], r11d
0x180010053  mov     [r10+4], edx
0x180010057  shl     r8d, 0Fh
0x18001005b  xor     r8d, eax
0x18001005e  and     r8d, 3F8000h
0x180010065  xor     r8d, eax
0x180010068  mov     eax, ecx
0x18001006a  lock cmpxchg [rsi], r8d
0x18001006f  jz      short loc_180010078
0x180010071  mov     ecx, eax
0x180010073  jmp     loc_18000FFDD
0x180010078  not     ecx
0x18001007a  and     ecx, ebx
0x18001007c  mov     [r10], ecx
0x18001007f  jmp     loc_18001014A
0x180010084  mov     edx, [rdx]
0x180010086  xor     ebp, ebp
0x180010088  lea     ecx, [rbp+4]
0x18001008b  cmp     r11d, ecx
0x18001008e  lea     ebx, [rcx-3]
0x180010091  setz    bpl
0x180010095  mov     eax, edx
0x180010097  mov     dword ptr [r10+4], 0
0x18001009f  or      eax, ebx
0x1800100a1  mov     r8d, eax
0x1800100a4  shr     r8d, 0Eh
0x1800100a8  and     r8d, ebx
0x1800100ab  cmp     r8d, ebp
0x1800100ae  jz      short loc_1800100F7
0x1800100b0  mov     edi, eax
0x1800100b2  shr     edi, 5
0x1800100b5  and     edi, 1FFh
0x1800100bb  jbe     short loc_1800100D9
0x1800100bd  mov     r8d, r11d
0x1800100c0  mov     [r10+4], edi
0x1800100c4  neg     r8d
0x1800100c7  sbb     r9d, r9d
0x1800100ca  not     r9d
0x1800100cd  and     r9d, ecx
0x1800100d0  mov     [r10+8], r9d
0x1800100d4  and     eax, 0FFFFC01Fh
0x1800100d9  xor     r9d, r9d
0x1800100dc  mov     r8d, 4000h
0x1800100e2  cmp     r11d, ecx
0x1800100e5  cmovz   r9d, r8d
0x1800100e9  mov     r8d, eax
0x1800100ec  btr     r8d, 0Eh
0x1800100f1  mov     eax, r9d
0x1800100f4  or      eax, r8d
0x1800100f7  mov     r8d, eax
0x1800100fa  shr     r8d, 5
0x1800100fe  and     r8d, 1FFh
0x180010105  lea     r9d, [r8+1]
0x180010109  cmp     r9d, 1FFh
0x180010110  ja      short loc_180010117
0x180010112  cmp     r9d, r8d
0x180010115  jnb     short loc_180010122
0x180010117  mov     r9d, ebx
0x18001011a  mov     [r10+8], r11d
0x18001011e  mov     [r10+4], r8d
0x180010122  shl     r9d, 5
0x180010126  xor     r9d, eax
0x180010129  and     r9d, 3FE0h
0x180010130  xor     r9d, eax
0x180010133  mov     eax, edx
0x180010135  lock cmpxchg [rsi], r9d
0x18001013a  jz      short loc_180010143
0x18001013c  mov     edx, eax
0x18001013e  jmp     loc_180010095
0x180010143  not     edx
0x180010145  and     edx, ebx
0x180010147  mov     [r10], edx
0x18001014a  mov     dword ptr [r10+10h], 0
0x180010152  mov     rax, r10
0x180010155  pop     rdi
0x180010156  pop     rsi
0x180010157  pop     rbp
0x180010158  pop     rbx
0x180010159  retn
```

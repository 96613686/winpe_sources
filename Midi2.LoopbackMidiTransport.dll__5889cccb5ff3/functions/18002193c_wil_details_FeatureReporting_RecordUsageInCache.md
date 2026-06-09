# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18002193c`
- end: `0x180021c16`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020bdc`

## callees

- `0x18002193c`

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
0x18002193c  push    rbx
0x18002193e  push    rbp
0x18002193f  push    rsi
0x180021940  push    rdi
0x180021941  xor     eax, eax
0x180021943  xorps   xmm0, xmm0
0x180021946  mov     r11d, r8d
0x180021949  mov     rsi, rdx
0x18002194c  mov     r10, rcx
0x18002194f  mov     r9d, r8d
0x180021952  movups  xmmword ptr [rcx], xmm0
0x180021955  mov     [rcx+10h], rax
0x180021959  test    r8d, r8d
0x18002195c  jz      loc_180021B40
0x180021962  sub     r9d, 1
0x180021966  jz      loc_180021A87
0x18002196c  sub     r9d, 1
0x180021970  jz      loc_180021A0E
0x180021976  sub     r9d, 1
0x18002197a  jz      loc_180021A0E
0x180021980  sub     r9d, 1
0x180021984  jz      loc_180021B40
0x18002198a  sub     r9d, 1
0x18002198e  jz      loc_180021A87
0x180021994  sub     r9d, 1
0x180021998  jz      short loc_180021A0E
0x18002199a  cmp     r9d, 1
0x18002199e  jz      short loc_180021A0E
0x1800219a0  add     r8d, 0FFFFFEC0h
0x1800219a7  lea     ebx, [rax+1]
0x1800219aa  cmp     r8d, 40h ; '@'
0x1800219ae  jge     short loc_1800219F9
0x1800219b0  mov     eax, [rdx+4]
0x1800219b3  lea     ecx, [rbx+0Fh]
0x1800219b6  mov     r9d, r8d
0x1800219b9  shl     r9d, 5
0x1800219bd  test    cl, al
0x1800219bf  jz      short loc_1800219D2
0x1800219c1  mov     edx, eax
0x1800219c3  shr     edx, 5
0x1800219c6  and     edx, 3Fh
0x1800219c9  cmp     edx, r8d
0x1800219cc  jnz     short loc_1800219D2
0x1800219ce  mov     edx, ebx
0x1800219d0  jmp     short loc_1800219D4
0x1800219d2  xor     edx, edx
0x1800219d4  mov     [r10+10h], edx
0x1800219d8  mov     edx, r9d
0x1800219db  xor     edx, eax
0x1800219dd  and     edx, 7E0h
0x1800219e3  xor     edx, eax
0x1800219e5  or      edx, ecx
0x1800219e7  lock cmpxchg [rsi+4], edx
0x1800219ec  jnz     short loc_1800219BD
0x1800219ee  cmp     dword ptr [r10+10h], 0
0x1800219f3  jnz     loc_180021C0E
0x1800219f9  mov     [r10+8], r11d
0x1800219fd  mov     [r10+4], ebx
0x180021a01  mov     dword ptr [r10+0Ch], 0
0x180021a09  jmp     loc_180021C0E
0x180021a0e  xor     ecx, ecx
0x180021a10  sub     r11d, 2
0x180021a14  jz      short loc_180021A3C
0x180021a16  sub     r11d, 1
0x180021a1a  jz      short loc_180021A35
0x180021a1c  sub     r11d, 3
0x180021a20  jz      short loc_180021A2E
0x180021a22  cmp     r11d, 1
0x180021a26  jnz     short loc_180021A41
0x180021a28  lea     ecx, [r11+0Fh]
0x180021a2c  jmp     short loc_180021A41
0x180021a2e  mov     ecx, 4
0x180021a33  jmp     short loc_180021A41
0x180021a35  mov     ecx, 8
0x180021a3a  jmp     short loc_180021A41
0x180021a3c  mov     ecx, 2
0x180021a41  mov     edx, [rdx]
0x180021a43  mov     ebx, 1
0x180021a48  xor     eax, eax
0x180021a4a  mov     r8d, ecx
0x180021a4d  or      r8d, edx
0x180021a50  cmp     r8d, edx
0x180021a53  mov     r9d, r8d
0x180021a56  setz    al
0x180021a59  or      r9d, ebx
0x180021a5c  cmp     r8d, edx
0x180021a5f  mov     [r10+10h], eax
0x180021a63  mov     eax, edx
0x180021a65  cmovz   r9d, r8d
0x180021a69  lock cmpxchg [rsi], r9d
0x180021a6e  jz      short loc_180021A74
0x180021a70  mov     edx, eax
0x180021a72  jmp     short loc_180021A48
0x180021a74  test    bl, r9b
0x180021a77  jz      short loc_180021A7D
0x180021a79  test    bl, dl
0x180021a7b  jz      short loc_180021A7F
0x180021a7d  xor     ebx, ebx
0x180021a7f  mov     [r10], ebx
0x180021a82  jmp     loc_180021C0E
0x180021a87  mov     ecx, [rdx]
0x180021a89  xor     r9d, r9d
0x180021a8c  cmp     r11d, 5
0x180021a90  mov     ebx, 1
0x180021a95  setz    r9b
0x180021a99  mov     eax, ecx
0x180021a9b  mov     dword ptr [r10+4], 0
0x180021aa3  or      eax, ebx
0x180021aa5  mov     edx, eax
0x180021aa7  shr     edx, 16h
0x180021aaa  and     edx, ebx
0x180021aac  cmp     edx, r9d
0x180021aaf  jz      short loc_180021AF1
0x180021ab1  mov     r8d, eax
0x180021ab4  shr     r8d, 0Fh
0x180021ab8  and     r8d, 7Fh
0x180021abc  jbe     short loc_180021AD6
0x180021abe  cmp     r11d, ebx
0x180021ac1  mov     [r10+4], r8d
0x180021ac5  mov     edx, 5
0x180021aca  cmovnz  edx, ebx
0x180021acd  and     eax, 0FFC07FFFh
0x180021ad2  mov     [r10+8], edx
0x180021ad6  xor     r8d, r8d
0x180021ad9  mov     edx, 400000h
0x180021ade  cmp     r11d, 5
0x180021ae2  cmovz   r8d, edx
0x180021ae6  mov     edx, eax
0x180021ae8  btr     edx, 16h
0x180021aec  mov     eax, r8d
0x180021aef  or      eax, edx
0x180021af1  mov     edx, eax
0x180021af3  shr     edx, 0Fh
0x180021af6  and     edx, 7Fh
0x180021af9  lea     r8d, [rdx+1]
0x180021afd  cmp     r8d, 7Fh
0x180021b01  ja      short loc_180021B08
0x180021b03  cmp     r8d, edx
0x180021b06  jnb     short loc_180021B13
0x180021b08  mov     r8d, ebx
0x180021b0b  mov     [r10+8], r11d
0x180021b0f  mov     [r10+4], edx
0x180021b13  shl     r8d, 0Fh
0x180021b17  xor     r8d, eax
0x180021b1a  and     r8d, 3F8000h
0x180021b21  xor     r8d, eax
0x180021b24  mov     eax, ecx
0x180021b26  lock cmpxchg [rsi], r8d
0x180021b2b  jz      short loc_180021B34
0x180021b2d  mov     ecx, eax
0x180021b2f  jmp     loc_180021A99
0x180021b34  not     ecx
0x180021b36  and     ecx, ebx
0x180021b38  mov     [r10], ecx
0x180021b3b  jmp     loc_180021C06
0x180021b40  mov     edx, [rdx]
0x180021b42  xor     ebp, ebp
0x180021b44  lea     ecx, [rbp+4]
0x180021b47  cmp     r11d, ecx
0x180021b4a  lea     ebx, [rcx-3]
0x180021b4d  setz    bpl
0x180021b51  mov     eax, edx
0x180021b53  mov     dword ptr [r10+4], 0
0x180021b5b  or      eax, ebx
0x180021b5d  mov     r8d, eax
0x180021b60  shr     r8d, 0Eh
0x180021b64  and     r8d, ebx
0x180021b67  cmp     r8d, ebp
0x180021b6a  jz      short loc_180021BB3
0x180021b6c  mov     edi, eax
0x180021b6e  shr     edi, 5
0x180021b71  and     edi, 1FFh
0x180021b77  jbe     short loc_180021B95
0x180021b79  mov     r8d, r11d
0x180021b7c  mov     [r10+4], edi
0x180021b80  neg     r8d
0x180021b83  sbb     r9d, r9d
0x180021b86  not     r9d
0x180021b89  and     r9d, ecx
0x180021b8c  mov     [r10+8], r9d
0x180021b90  and     eax, 0FFFFC01Fh
0x180021b95  xor     r9d, r9d
0x180021b98  mov     r8d, 4000h
0x180021b9e  cmp     r11d, ecx
0x180021ba1  cmovz   r9d, r8d
0x180021ba5  mov     r8d, eax
0x180021ba8  btr     r8d, 0Eh
0x180021bad  mov     eax, r9d
0x180021bb0  or      eax, r8d
0x180021bb3  mov     r8d, eax
0x180021bb6  shr     r8d, 5
0x180021bba  and     r8d, 1FFh
0x180021bc1  lea     r9d, [r8+1]
0x180021bc5  cmp     r9d, 1FFh
0x180021bcc  ja      short loc_180021BD3
0x180021bce  cmp     r9d, r8d
0x180021bd1  jnb     short loc_180021BDE
0x180021bd3  mov     r9d, ebx
0x180021bd6  mov     [r10+8], r11d
0x180021bda  mov     [r10+4], r8d
0x180021bde  shl     r9d, 5
0x180021be2  xor     r9d, eax
0x180021be5  and     r9d, 3FE0h
0x180021bec  xor     r9d, eax
0x180021bef  mov     eax, edx
0x180021bf1  lock cmpxchg [rsi], r9d
0x180021bf6  jz      short loc_180021BFF
0x180021bf8  mov     edx, eax
0x180021bfa  jmp     loc_180021B51
0x180021bff  not     edx
0x180021c01  and     edx, ebx
0x180021c03  mov     [r10], edx
0x180021c06  mov     dword ptr [r10+10h], 0
0x180021c0e  mov     rax, r10
0x180021c11  pop     rdi
0x180021c12  pop     rsi
0x180021c13  pop     rbp
0x180021c14  pop     rbx
0x180021c15  retn
```

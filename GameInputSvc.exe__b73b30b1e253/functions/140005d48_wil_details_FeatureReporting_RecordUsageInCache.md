# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140005d48`
- end: `0x14000601a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000613c`

## callees

- `0x140005d48`

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
0x140005d48  push    rbx
0x140005d4a  push    rbp
0x140005d4b  push    rsi
0x140005d4c  push    rdi
0x140005d4d  xor     eax, eax
0x140005d4f  xorps   xmm0, xmm0
0x140005d52  mov     r10, rcx
0x140005d55  mov     edi, r9d
0x140005d58  mov     r11d, r8d
0x140005d5b  mov     rsi, rdx
0x140005d5e  movups  xmmword ptr [rcx], xmm0
0x140005d61  mov     [rcx+10h], rax
0x140005d65  mov     ecx, r8d
0x140005d68  test    r8d, r8d
0x140005d6b  jz      loc_140005F44
0x140005d71  sub     ecx, 1
0x140005d74  jz      loc_140005E8B
0x140005d7a  sub     ecx, 1
0x140005d7d  jz      loc_140005E12
0x140005d83  sub     ecx, 1
0x140005d86  jz      loc_140005E12
0x140005d8c  sub     ecx, 1
0x140005d8f  jz      loc_140005F44
0x140005d95  sub     ecx, 1
0x140005d98  jz      loc_140005E8B
0x140005d9e  sub     ecx, 1
0x140005da1  jz      short loc_140005E12
0x140005da3  cmp     ecx, 1
0x140005da6  jz      short loc_140005E12
0x140005da8  add     r8d, 0FFFFFEC0h
0x140005daf  lea     ebx, [rax+1]
0x140005db2  cmp     r8d, 40h ; '@'
0x140005db6  jge     short loc_140005E01
0x140005db8  mov     eax, [rdx+4]
0x140005dbb  lea     ecx, [rbx+0Fh]
0x140005dbe  mov     r9d, r8d
0x140005dc1  shl     r9d, 5
0x140005dc5  test    cl, al
0x140005dc7  jz      short loc_140005DDA
0x140005dc9  mov     edx, eax
0x140005dcb  shr     edx, 5
0x140005dce  and     edx, 3Fh
0x140005dd1  cmp     edx, r8d
0x140005dd4  jnz     short loc_140005DDA
0x140005dd6  mov     edx, ebx
0x140005dd8  jmp     short loc_140005DDC
0x140005dda  xor     edx, edx
0x140005ddc  mov     [r10+10h], edx
0x140005de0  mov     edx, r9d
0x140005de3  xor     edx, eax
0x140005de5  and     edx, 7E0h
0x140005deb  xor     edx, eax
0x140005ded  or      edx, ecx
0x140005def  lock cmpxchg [rsi+4], edx
0x140005df4  jnz     short loc_140005DC5
0x140005df6  cmp     dword ptr [r10+10h], 0
0x140005dfb  jnz     loc_140006012
0x140005e01  mov     [r10+8], r11d
0x140005e05  mov     [r10+4], ebx
0x140005e09  mov     [r10+0Ch], edi
0x140005e0d  jmp     loc_140006012
0x140005e12  xor     ecx, ecx
0x140005e14  sub     r11d, 2
0x140005e18  jz      short loc_140005E40
0x140005e1a  sub     r11d, 1
0x140005e1e  jz      short loc_140005E39
0x140005e20  sub     r11d, 3
0x140005e24  jz      short loc_140005E32
0x140005e26  cmp     r11d, 1
0x140005e2a  jnz     short loc_140005E45
0x140005e2c  lea     ecx, [r11+0Fh]
0x140005e30  jmp     short loc_140005E45
0x140005e32  mov     ecx, 4
0x140005e37  jmp     short loc_140005E45
0x140005e39  mov     ecx, 8
0x140005e3e  jmp     short loc_140005E45
0x140005e40  mov     ecx, 2
0x140005e45  mov     edx, [rdx]
0x140005e47  mov     ebx, 1
0x140005e4c  xor     eax, eax
0x140005e4e  mov     r8d, ecx
0x140005e51  or      r8d, edx
0x140005e54  cmp     r8d, edx
0x140005e57  mov     r9d, r8d
0x140005e5a  setz    al
0x140005e5d  or      r9d, ebx
0x140005e60  cmp     r8d, edx
0x140005e63  mov     [r10+10h], eax
0x140005e67  mov     eax, edx
0x140005e69  cmovz   r9d, r8d
0x140005e6d  lock cmpxchg [rsi], r9d
0x140005e72  jz      short loc_140005E78
0x140005e74  mov     edx, eax
0x140005e76  jmp     short loc_140005E4C
0x140005e78  test    bl, r9b
0x140005e7b  jz      short loc_140005E81
0x140005e7d  test    bl, dl
0x140005e7f  jz      short loc_140005E83
0x140005e81  xor     ebx, ebx
0x140005e83  mov     [r10], ebx
0x140005e86  jmp     loc_140006012
0x140005e8b  mov     ecx, [rdx]
0x140005e8d  xor     r9d, r9d
0x140005e90  cmp     r11d, 5
0x140005e94  mov     ebx, 1
0x140005e99  setz    r9b
0x140005e9d  mov     eax, ecx
0x140005e9f  mov     dword ptr [r10+4], 0
0x140005ea7  or      eax, ebx
0x140005ea9  mov     edx, eax
0x140005eab  shr     edx, 16h
0x140005eae  and     edx, ebx
0x140005eb0  cmp     edx, r9d
0x140005eb3  jz      short loc_140005EF5
0x140005eb5  mov     r8d, eax
0x140005eb8  shr     r8d, 0Fh
0x140005ebc  and     r8d, 7Fh
0x140005ec0  jbe     short loc_140005EDA
0x140005ec2  cmp     r11d, ebx
0x140005ec5  mov     [r10+4], r8d
0x140005ec9  mov     edx, 5
0x140005ece  cmovnz  edx, ebx
0x140005ed1  and     eax, 0FFC07FFFh
0x140005ed6  mov     [r10+8], edx
0x140005eda  xor     r8d, r8d
0x140005edd  mov     edx, 400000h
0x140005ee2  cmp     r11d, 5
0x140005ee6  cmovz   r8d, edx
0x140005eea  mov     edx, eax
0x140005eec  btr     edx, 16h
0x140005ef0  mov     eax, r8d
0x140005ef3  or      eax, edx
0x140005ef5  mov     edx, eax
0x140005ef7  shr     edx, 0Fh
0x140005efa  and     edx, 7Fh
0x140005efd  lea     r8d, [rdx+1]
0x140005f01  cmp     r8d, 7Fh
0x140005f05  ja      short loc_140005F0C
0x140005f07  cmp     r8d, edx
0x140005f0a  jnb     short loc_140005F17
0x140005f0c  mov     r8d, ebx
0x140005f0f  mov     [r10+8], r11d
0x140005f13  mov     [r10+4], edx
0x140005f17  shl     r8d, 0Fh
0x140005f1b  xor     r8d, eax
0x140005f1e  and     r8d, 3F8000h
0x140005f25  xor     r8d, eax
0x140005f28  mov     eax, ecx
0x140005f2a  lock cmpxchg [rsi], r8d
0x140005f2f  jz      short loc_140005F38
0x140005f31  mov     ecx, eax
0x140005f33  jmp     loc_140005E9D
0x140005f38  not     ecx
0x140005f3a  and     ecx, ebx
0x140005f3c  mov     [r10], ecx
0x140005f3f  jmp     loc_14000600A
0x140005f44  mov     edx, [rdx]
0x140005f46  xor     ebp, ebp
0x140005f48  lea     ecx, [rbp+4]
0x140005f4b  cmp     r11d, ecx
0x140005f4e  lea     ebx, [rcx-3]
0x140005f51  setz    bpl
0x140005f55  mov     eax, edx
0x140005f57  mov     dword ptr [r10+4], 0
0x140005f5f  or      eax, ebx
0x140005f61  mov     r8d, eax
0x140005f64  shr     r8d, 0Eh
0x140005f68  and     r8d, ebx
0x140005f6b  cmp     r8d, ebp
0x140005f6e  jz      short loc_140005FB7
0x140005f70  mov     edi, eax
0x140005f72  shr     edi, 5
0x140005f75  and     edi, 1FFh
0x140005f7b  jbe     short loc_140005F99
0x140005f7d  mov     r8d, r11d
0x140005f80  mov     [r10+4], edi
0x140005f84  neg     r8d
0x140005f87  sbb     r9d, r9d
0x140005f8a  not     r9d
0x140005f8d  and     r9d, ecx
0x140005f90  mov     [r10+8], r9d
0x140005f94  and     eax, 0FFFFC01Fh
0x140005f99  xor     r9d, r9d
0x140005f9c  mov     r8d, 4000h
0x140005fa2  cmp     r11d, ecx
0x140005fa5  cmovz   r9d, r8d
0x140005fa9  mov     r8d, eax
0x140005fac  btr     r8d, 0Eh
0x140005fb1  mov     eax, r9d
0x140005fb4  or      eax, r8d
0x140005fb7  mov     r8d, eax
0x140005fba  shr     r8d, 5
0x140005fbe  and     r8d, 1FFh
0x140005fc5  lea     r9d, [r8+1]
0x140005fc9  cmp     r9d, 1FFh
0x140005fd0  ja      short loc_140005FD7
0x140005fd2  cmp     r9d, r8d
0x140005fd5  jnb     short loc_140005FE2
0x140005fd7  mov     r9d, ebx
0x140005fda  mov     [r10+8], r11d
0x140005fde  mov     [r10+4], r8d
0x140005fe2  shl     r9d, 5
0x140005fe6  xor     r9d, eax
0x140005fe9  and     r9d, 3FE0h
0x140005ff0  xor     r9d, eax
0x140005ff3  mov     eax, edx
0x140005ff5  lock cmpxchg [rsi], r9d
0x140005ffa  jz      short loc_140006003
0x140005ffc  mov     edx, eax
0x140005ffe  jmp     loc_140005F55
0x140006003  not     edx
0x140006005  and     edx, ebx
0x140006007  mov     [r10], edx
0x14000600a  mov     dword ptr [r10+10h], 0
0x140006012  mov     rax, r10
0x140006015  pop     rdi
0x140006016  pop     rsi
0x140006017  pop     rbp
0x140006018  pop     rbx
0x140006019  retn
```

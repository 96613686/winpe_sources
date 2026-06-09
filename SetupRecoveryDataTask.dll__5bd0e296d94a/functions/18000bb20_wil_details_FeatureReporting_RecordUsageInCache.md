# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000bb20`
- end: `0x18000bdfa`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008784`

## callees

- `0x18000bb20`

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
0x18000bb20  push    rbx
0x18000bb22  push    rbp
0x18000bb23  push    rsi
0x18000bb24  push    rdi
0x18000bb25  xor     eax, eax
0x18000bb27  xorps   xmm0, xmm0
0x18000bb2a  mov     r11d, r8d
0x18000bb2d  mov     rsi, rdx
0x18000bb30  mov     r10, rcx
0x18000bb33  mov     r9d, r8d
0x18000bb36  movups  xmmword ptr [rcx], xmm0
0x18000bb39  mov     [rcx+10h], rax
0x18000bb3d  test    r8d, r8d
0x18000bb40  jz      loc_18000BD24
0x18000bb46  sub     r9d, 1
0x18000bb4a  jz      loc_18000BC6B
0x18000bb50  sub     r9d, 1
0x18000bb54  jz      loc_18000BBF2
0x18000bb5a  sub     r9d, 1
0x18000bb5e  jz      loc_18000BBF2
0x18000bb64  sub     r9d, 1
0x18000bb68  jz      loc_18000BD24
0x18000bb6e  sub     r9d, 1
0x18000bb72  jz      loc_18000BC6B
0x18000bb78  sub     r9d, 1
0x18000bb7c  jz      short loc_18000BBF2
0x18000bb7e  cmp     r9d, 1
0x18000bb82  jz      short loc_18000BBF2
0x18000bb84  add     r8d, 0FFFFFEC0h
0x18000bb8b  lea     ebx, [rax+1]
0x18000bb8e  cmp     r8d, 40h ; '@'
0x18000bb92  jge     short loc_18000BBDD
0x18000bb94  mov     eax, [rdx+4]
0x18000bb97  lea     ecx, [rbx+0Fh]
0x18000bb9a  mov     r9d, r8d
0x18000bb9d  shl     r9d, 5
0x18000bba1  test    cl, al
0x18000bba3  jz      short loc_18000BBB6
0x18000bba5  mov     edx, eax
0x18000bba7  shr     edx, 5
0x18000bbaa  and     edx, 3Fh
0x18000bbad  cmp     edx, r8d
0x18000bbb0  jnz     short loc_18000BBB6
0x18000bbb2  mov     edx, ebx
0x18000bbb4  jmp     short loc_18000BBB8
0x18000bbb6  xor     edx, edx
0x18000bbb8  mov     [r10+10h], edx
0x18000bbbc  mov     edx, r9d
0x18000bbbf  xor     edx, eax
0x18000bbc1  and     edx, 7E0h
0x18000bbc7  xor     edx, eax
0x18000bbc9  or      edx, ecx
0x18000bbcb  lock cmpxchg [rsi+4], edx
0x18000bbd0  jnz     short loc_18000BBA1
0x18000bbd2  cmp     dword ptr [r10+10h], 0
0x18000bbd7  jnz     loc_18000BDF2
0x18000bbdd  mov     [r10+8], r11d
0x18000bbe1  mov     [r10+4], ebx
0x18000bbe5  mov     dword ptr [r10+0Ch], 0
0x18000bbed  jmp     loc_18000BDF2
0x18000bbf2  xor     ecx, ecx
0x18000bbf4  sub     r11d, 2
0x18000bbf8  jz      short loc_18000BC20
0x18000bbfa  sub     r11d, 1
0x18000bbfe  jz      short loc_18000BC19
0x18000bc00  sub     r11d, 3
0x18000bc04  jz      short loc_18000BC12
0x18000bc06  cmp     r11d, 1
0x18000bc0a  jnz     short loc_18000BC25
0x18000bc0c  lea     ecx, [r11+0Fh]
0x18000bc10  jmp     short loc_18000BC25
0x18000bc12  mov     ecx, 4
0x18000bc17  jmp     short loc_18000BC25
0x18000bc19  mov     ecx, 8
0x18000bc1e  jmp     short loc_18000BC25
0x18000bc20  mov     ecx, 2
0x18000bc25  mov     edx, [rdx]
0x18000bc27  mov     ebx, 1
0x18000bc2c  xor     eax, eax
0x18000bc2e  mov     r8d, ecx
0x18000bc31  or      r8d, edx
0x18000bc34  cmp     r8d, edx
0x18000bc37  mov     r9d, r8d
0x18000bc3a  setz    al
0x18000bc3d  or      r9d, ebx
0x18000bc40  cmp     r8d, edx
0x18000bc43  mov     [r10+10h], eax
0x18000bc47  mov     eax, edx
0x18000bc49  cmovz   r9d, r8d
0x18000bc4d  lock cmpxchg [rsi], r9d
0x18000bc52  jz      short loc_18000BC58
0x18000bc54  mov     edx, eax
0x18000bc56  jmp     short loc_18000BC2C
0x18000bc58  test    bl, r9b
0x18000bc5b  jz      short loc_18000BC61
0x18000bc5d  test    bl, dl
0x18000bc5f  jz      short loc_18000BC63
0x18000bc61  xor     ebx, ebx
0x18000bc63  mov     [r10], ebx
0x18000bc66  jmp     loc_18000BDF2
0x18000bc6b  mov     ecx, [rdx]
0x18000bc6d  xor     r9d, r9d
0x18000bc70  cmp     r11d, 5
0x18000bc74  mov     ebx, 1
0x18000bc79  setz    r9b
0x18000bc7d  mov     eax, ecx
0x18000bc7f  mov     dword ptr [r10+4], 0
0x18000bc87  or      eax, ebx
0x18000bc89  mov     edx, eax
0x18000bc8b  shr     edx, 16h
0x18000bc8e  and     edx, ebx
0x18000bc90  cmp     edx, r9d
0x18000bc93  jz      short loc_18000BCD5
0x18000bc95  mov     r8d, eax
0x18000bc98  shr     r8d, 0Fh
0x18000bc9c  and     r8d, 7Fh
0x18000bca0  jbe     short loc_18000BCBA
0x18000bca2  cmp     r11d, ebx
0x18000bca5  mov     [r10+4], r8d
0x18000bca9  mov     edx, 5
0x18000bcae  cmovnz  edx, ebx
0x18000bcb1  and     eax, 0FFC07FFFh
0x18000bcb6  mov     [r10+8], edx
0x18000bcba  xor     r8d, r8d
0x18000bcbd  mov     edx, 400000h
0x18000bcc2  cmp     r11d, 5
0x18000bcc6  cmovz   r8d, edx
0x18000bcca  mov     edx, eax
0x18000bccc  btr     edx, 16h
0x18000bcd0  mov     eax, r8d
0x18000bcd3  or      eax, edx
0x18000bcd5  mov     edx, eax
0x18000bcd7  shr     edx, 0Fh
0x18000bcda  and     edx, 7Fh
0x18000bcdd  lea     r8d, [rdx+1]
0x18000bce1  cmp     r8d, 7Fh
0x18000bce5  ja      short loc_18000BCEC
0x18000bce7  cmp     r8d, edx
0x18000bcea  jnb     short loc_18000BCF7
0x18000bcec  mov     r8d, ebx
0x18000bcef  mov     [r10+8], r11d
0x18000bcf3  mov     [r10+4], edx
0x18000bcf7  shl     r8d, 0Fh
0x18000bcfb  xor     r8d, eax
0x18000bcfe  and     r8d, 3F8000h
0x18000bd05  xor     r8d, eax
0x18000bd08  mov     eax, ecx
0x18000bd0a  lock cmpxchg [rsi], r8d
0x18000bd0f  jz      short loc_18000BD18
0x18000bd11  mov     ecx, eax
0x18000bd13  jmp     loc_18000BC7D
0x18000bd18  not     ecx
0x18000bd1a  and     ecx, ebx
0x18000bd1c  mov     [r10], ecx
0x18000bd1f  jmp     loc_18000BDEA
0x18000bd24  mov     edx, [rdx]
0x18000bd26  xor     ebp, ebp
0x18000bd28  lea     ecx, [rbp+4]
0x18000bd2b  cmp     r11d, ecx
0x18000bd2e  lea     ebx, [rcx-3]
0x18000bd31  setz    bpl
0x18000bd35  mov     eax, edx
0x18000bd37  mov     dword ptr [r10+4], 0
0x18000bd3f  or      eax, ebx
0x18000bd41  mov     r8d, eax
0x18000bd44  shr     r8d, 0Eh
0x18000bd48  and     r8d, ebx
0x18000bd4b  cmp     r8d, ebp
0x18000bd4e  jz      short loc_18000BD97
0x18000bd50  mov     edi, eax
0x18000bd52  shr     edi, 5
0x18000bd55  and     edi, 1FFh
0x18000bd5b  jbe     short loc_18000BD79
0x18000bd5d  mov     r8d, r11d
0x18000bd60  mov     [r10+4], edi
0x18000bd64  neg     r8d
0x18000bd67  sbb     r9d, r9d
0x18000bd6a  not     r9d
0x18000bd6d  and     r9d, ecx
0x18000bd70  mov     [r10+8], r9d
0x18000bd74  and     eax, 0FFFFC01Fh
0x18000bd79  xor     r9d, r9d
0x18000bd7c  mov     r8d, 4000h
0x18000bd82  cmp     r11d, ecx
0x18000bd85  cmovz   r9d, r8d
0x18000bd89  mov     r8d, eax
0x18000bd8c  btr     r8d, 0Eh
0x18000bd91  mov     eax, r9d
0x18000bd94  or      eax, r8d
0x18000bd97  mov     r8d, eax
0x18000bd9a  shr     r8d, 5
0x18000bd9e  and     r8d, 1FFh
0x18000bda5  lea     r9d, [r8+1]
0x18000bda9  cmp     r9d, 1FFh
0x18000bdb0  ja      short loc_18000BDB7
0x18000bdb2  cmp     r9d, r8d
0x18000bdb5  jnb     short loc_18000BDC2
0x18000bdb7  mov     r9d, ebx
0x18000bdba  mov     [r10+8], r11d
0x18000bdbe  mov     [r10+4], r8d
0x18000bdc2  shl     r9d, 5
0x18000bdc6  xor     r9d, eax
0x18000bdc9  and     r9d, 3FE0h
0x18000bdd0  xor     r9d, eax
0x18000bdd3  mov     eax, edx
0x18000bdd5  lock cmpxchg [rsi], r9d
0x18000bdda  jz      short loc_18000BDE3
0x18000bddc  mov     edx, eax
0x18000bdde  jmp     loc_18000BD35
0x18000bde3  not     edx
0x18000bde5  and     edx, ebx
0x18000bde7  mov     [r10], edx
0x18000bdea  mov     dword ptr [r10+10h], 0
0x18000bdf2  mov     rax, r10
0x18000bdf5  pop     rdi
0x18000bdf6  pop     rsi
0x18000bdf7  pop     rbp
0x18000bdf8  pop     rbx
0x18000bdf9  retn
```

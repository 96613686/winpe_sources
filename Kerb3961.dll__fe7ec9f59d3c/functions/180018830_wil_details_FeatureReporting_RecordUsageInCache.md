# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180018830`
- end: `0x180018b0a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016424`

## callees

- `0x180018830`

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
0x180018830  push    rbx
0x180018832  push    rbp
0x180018833  push    rsi
0x180018834  push    rdi
0x180018835  xor     eax, eax
0x180018837  xorps   xmm0, xmm0
0x18001883a  mov     r11d, r8d
0x18001883d  mov     rsi, rdx
0x180018840  mov     r10, rcx
0x180018843  mov     r9d, r8d
0x180018846  movups  xmmword ptr [rcx], xmm0
0x180018849  mov     [rcx+10h], rax
0x18001884d  test    r8d, r8d
0x180018850  jz      loc_180018A34
0x180018856  sub     r9d, 1
0x18001885a  jz      loc_18001897B
0x180018860  sub     r9d, 1
0x180018864  jz      loc_180018902
0x18001886a  sub     r9d, 1
0x18001886e  jz      loc_180018902
0x180018874  sub     r9d, 1
0x180018878  jz      loc_180018A34
0x18001887e  sub     r9d, 1
0x180018882  jz      loc_18001897B
0x180018888  sub     r9d, 1
0x18001888c  jz      short loc_180018902
0x18001888e  cmp     r9d, 1
0x180018892  jz      short loc_180018902
0x180018894  add     r8d, 0FFFFFEC0h
0x18001889b  lea     ebx, [rax+1]
0x18001889e  cmp     r8d, 40h ; '@'
0x1800188a2  jge     short loc_1800188ED
0x1800188a4  mov     eax, [rdx+4]
0x1800188a7  lea     ecx, [rbx+0Fh]
0x1800188aa  mov     r9d, r8d
0x1800188ad  shl     r9d, 5
0x1800188b1  test    cl, al
0x1800188b3  jz      short loc_1800188C6
0x1800188b5  mov     edx, eax
0x1800188b7  shr     edx, 5
0x1800188ba  and     edx, 3Fh
0x1800188bd  cmp     edx, r8d
0x1800188c0  jnz     short loc_1800188C6
0x1800188c2  mov     edx, ebx
0x1800188c4  jmp     short loc_1800188C8
0x1800188c6  xor     edx, edx
0x1800188c8  mov     [r10+10h], edx
0x1800188cc  mov     edx, r9d
0x1800188cf  xor     edx, eax
0x1800188d1  and     edx, 7E0h
0x1800188d7  xor     edx, eax
0x1800188d9  or      edx, ecx
0x1800188db  lock cmpxchg [rsi+4], edx
0x1800188e0  jnz     short loc_1800188B1
0x1800188e2  cmp     dword ptr [r10+10h], 0
0x1800188e7  jnz     loc_180018B02
0x1800188ed  mov     [r10+8], r11d
0x1800188f1  mov     [r10+4], ebx
0x1800188f5  mov     dword ptr [r10+0Ch], 0
0x1800188fd  jmp     loc_180018B02
0x180018902  xor     ecx, ecx
0x180018904  sub     r11d, 2
0x180018908  jz      short loc_180018930
0x18001890a  sub     r11d, 1
0x18001890e  jz      short loc_180018929
0x180018910  sub     r11d, 3
0x180018914  jz      short loc_180018922
0x180018916  cmp     r11d, 1
0x18001891a  jnz     short loc_180018935
0x18001891c  lea     ecx, [r11+0Fh]
0x180018920  jmp     short loc_180018935
0x180018922  mov     ecx, 4
0x180018927  jmp     short loc_180018935
0x180018929  mov     ecx, 8
0x18001892e  jmp     short loc_180018935
0x180018930  mov     ecx, 2
0x180018935  mov     edx, [rdx]
0x180018937  mov     ebx, 1
0x18001893c  xor     eax, eax
0x18001893e  mov     r8d, ecx
0x180018941  or      r8d, edx
0x180018944  cmp     r8d, edx
0x180018947  mov     r9d, r8d
0x18001894a  setz    al
0x18001894d  or      r9d, ebx
0x180018950  cmp     r8d, edx
0x180018953  mov     [r10+10h], eax
0x180018957  mov     eax, edx
0x180018959  cmovz   r9d, r8d
0x18001895d  lock cmpxchg [rsi], r9d
0x180018962  jz      short loc_180018968
0x180018964  mov     edx, eax
0x180018966  jmp     short loc_18001893C
0x180018968  test    bl, r9b
0x18001896b  jz      short loc_180018971
0x18001896d  test    bl, dl
0x18001896f  jz      short loc_180018973
0x180018971  xor     ebx, ebx
0x180018973  mov     [r10], ebx
0x180018976  jmp     loc_180018B02
0x18001897b  mov     ecx, [rdx]
0x18001897d  xor     r9d, r9d
0x180018980  cmp     r11d, 5
0x180018984  mov     ebx, 1
0x180018989  setz    r9b
0x18001898d  mov     eax, ecx
0x18001898f  mov     dword ptr [r10+4], 0
0x180018997  or      eax, ebx
0x180018999  mov     edx, eax
0x18001899b  shr     edx, 16h
0x18001899e  and     edx, ebx
0x1800189a0  cmp     edx, r9d
0x1800189a3  jz      short loc_1800189E5
0x1800189a5  mov     r8d, eax
0x1800189a8  shr     r8d, 0Fh
0x1800189ac  and     r8d, 7Fh
0x1800189b0  jbe     short loc_1800189CA
0x1800189b2  cmp     r11d, ebx
0x1800189b5  mov     [r10+4], r8d
0x1800189b9  mov     edx, 5
0x1800189be  cmovnz  edx, ebx
0x1800189c1  and     eax, 0FFC07FFFh
0x1800189c6  mov     [r10+8], edx
0x1800189ca  xor     r8d, r8d
0x1800189cd  mov     edx, 400000h
0x1800189d2  cmp     r11d, 5
0x1800189d6  cmovz   r8d, edx
0x1800189da  mov     edx, eax
0x1800189dc  btr     edx, 16h
0x1800189e0  mov     eax, r8d
0x1800189e3  or      eax, edx
0x1800189e5  mov     edx, eax
0x1800189e7  shr     edx, 0Fh
0x1800189ea  and     edx, 7Fh
0x1800189ed  lea     r8d, [rdx+1]
0x1800189f1  cmp     r8d, 7Fh
0x1800189f5  ja      short loc_1800189FC
0x1800189f7  cmp     r8d, edx
0x1800189fa  jnb     short loc_180018A07
0x1800189fc  mov     r8d, ebx
0x1800189ff  mov     [r10+8], r11d
0x180018a03  mov     [r10+4], edx
0x180018a07  shl     r8d, 0Fh
0x180018a0b  xor     r8d, eax
0x180018a0e  and     r8d, 3F8000h
0x180018a15  xor     r8d, eax
0x180018a18  mov     eax, ecx
0x180018a1a  lock cmpxchg [rsi], r8d
0x180018a1f  jz      short loc_180018A28
0x180018a21  mov     ecx, eax
0x180018a23  jmp     loc_18001898D
0x180018a28  not     ecx
0x180018a2a  and     ecx, ebx
0x180018a2c  mov     [r10], ecx
0x180018a2f  jmp     loc_180018AFA
0x180018a34  mov     edx, [rdx]
0x180018a36  xor     ebp, ebp
0x180018a38  lea     ecx, [rbp+4]
0x180018a3b  cmp     r11d, ecx
0x180018a3e  lea     ebx, [rcx-3]
0x180018a41  setz    bpl
0x180018a45  mov     eax, edx
0x180018a47  mov     dword ptr [r10+4], 0
0x180018a4f  or      eax, ebx
0x180018a51  mov     r8d, eax
0x180018a54  shr     r8d, 0Eh
0x180018a58  and     r8d, ebx
0x180018a5b  cmp     r8d, ebp
0x180018a5e  jz      short loc_180018AA7
0x180018a60  mov     edi, eax
0x180018a62  shr     edi, 5
0x180018a65  and     edi, 1FFh
0x180018a6b  jbe     short loc_180018A89
0x180018a6d  mov     r8d, r11d
0x180018a70  mov     [r10+4], edi
0x180018a74  neg     r8d
0x180018a77  sbb     r9d, r9d
0x180018a7a  not     r9d
0x180018a7d  and     r9d, ecx
0x180018a80  mov     [r10+8], r9d
0x180018a84  and     eax, 0FFFFC01Fh
0x180018a89  xor     r9d, r9d
0x180018a8c  mov     r8d, 4000h
0x180018a92  cmp     r11d, ecx
0x180018a95  cmovz   r9d, r8d
0x180018a99  mov     r8d, eax
0x180018a9c  btr     r8d, 0Eh
0x180018aa1  mov     eax, r9d
0x180018aa4  or      eax, r8d
0x180018aa7  mov     r8d, eax
0x180018aaa  shr     r8d, 5
0x180018aae  and     r8d, 1FFh
0x180018ab5  lea     r9d, [r8+1]
0x180018ab9  cmp     r9d, 1FFh
0x180018ac0  ja      short loc_180018AC7
0x180018ac2  cmp     r9d, r8d
0x180018ac5  jnb     short loc_180018AD2
0x180018ac7  mov     r9d, ebx
0x180018aca  mov     [r10+8], r11d
0x180018ace  mov     [r10+4], r8d
0x180018ad2  shl     r9d, 5
0x180018ad6  xor     r9d, eax
0x180018ad9  and     r9d, 3FE0h
0x180018ae0  xor     r9d, eax
0x180018ae3  mov     eax, edx
0x180018ae5  lock cmpxchg [rsi], r9d
0x180018aea  jz      short loc_180018AF3
0x180018aec  mov     edx, eax
0x180018aee  jmp     loc_180018A45
0x180018af3  not     edx
0x180018af5  and     edx, ebx
0x180018af7  mov     [r10], edx
0x180018afa  mov     dword ptr [r10+10h], 0
0x180018b02  mov     rax, r10
0x180018b05  pop     rdi
0x180018b06  pop     rsi
0x180018b07  pop     rbp
0x180018b08  pop     rbx
0x180018b09  retn
```

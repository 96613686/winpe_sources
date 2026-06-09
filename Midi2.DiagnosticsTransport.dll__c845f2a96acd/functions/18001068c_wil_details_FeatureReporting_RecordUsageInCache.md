# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001068c`
- end: `0x180010966`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fd0c`

## callees

- `0x18001068c`

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
0x18001068c  push    rbx
0x18001068e  push    rbp
0x18001068f  push    rsi
0x180010690  push    rdi
0x180010691  xor     eax, eax
0x180010693  xorps   xmm0, xmm0
0x180010696  mov     r11d, r8d
0x180010699  mov     rsi, rdx
0x18001069c  mov     r10, rcx
0x18001069f  mov     r9d, r8d
0x1800106a2  movups  xmmword ptr [rcx], xmm0
0x1800106a5  mov     [rcx+10h], rax
0x1800106a9  test    r8d, r8d
0x1800106ac  jz      loc_180010890
0x1800106b2  sub     r9d, 1
0x1800106b6  jz      loc_1800107D7
0x1800106bc  sub     r9d, 1
0x1800106c0  jz      loc_18001075E
0x1800106c6  sub     r9d, 1
0x1800106ca  jz      loc_18001075E
0x1800106d0  sub     r9d, 1
0x1800106d4  jz      loc_180010890
0x1800106da  sub     r9d, 1
0x1800106de  jz      loc_1800107D7
0x1800106e4  sub     r9d, 1
0x1800106e8  jz      short loc_18001075E
0x1800106ea  cmp     r9d, 1
0x1800106ee  jz      short loc_18001075E
0x1800106f0  add     r8d, 0FFFFFEC0h
0x1800106f7  lea     ebx, [rax+1]
0x1800106fa  cmp     r8d, 40h ; '@'
0x1800106fe  jge     short loc_180010749
0x180010700  mov     eax, [rdx+4]
0x180010703  lea     ecx, [rbx+0Fh]
0x180010706  mov     r9d, r8d
0x180010709  shl     r9d, 5
0x18001070d  test    cl, al
0x18001070f  jz      short loc_180010722
0x180010711  mov     edx, eax
0x180010713  shr     edx, 5
0x180010716  and     edx, 3Fh
0x180010719  cmp     edx, r8d
0x18001071c  jnz     short loc_180010722
0x18001071e  mov     edx, ebx
0x180010720  jmp     short loc_180010724
0x180010722  xor     edx, edx
0x180010724  mov     [r10+10h], edx
0x180010728  mov     edx, r9d
0x18001072b  xor     edx, eax
0x18001072d  and     edx, 7E0h
0x180010733  xor     edx, eax
0x180010735  or      edx, ecx
0x180010737  lock cmpxchg [rsi+4], edx
0x18001073c  jnz     short loc_18001070D
0x18001073e  cmp     dword ptr [r10+10h], 0
0x180010743  jnz     loc_18001095E
0x180010749  mov     [r10+8], r11d
0x18001074d  mov     [r10+4], ebx
0x180010751  mov     dword ptr [r10+0Ch], 0
0x180010759  jmp     loc_18001095E
0x18001075e  xor     ecx, ecx
0x180010760  sub     r11d, 2
0x180010764  jz      short loc_18001078C
0x180010766  sub     r11d, 1
0x18001076a  jz      short loc_180010785
0x18001076c  sub     r11d, 3
0x180010770  jz      short loc_18001077E
0x180010772  cmp     r11d, 1
0x180010776  jnz     short loc_180010791
0x180010778  lea     ecx, [r11+0Fh]
0x18001077c  jmp     short loc_180010791
0x18001077e  mov     ecx, 4
0x180010783  jmp     short loc_180010791
0x180010785  mov     ecx, 8
0x18001078a  jmp     short loc_180010791
0x18001078c  mov     ecx, 2
0x180010791  mov     edx, [rdx]
0x180010793  mov     ebx, 1
0x180010798  xor     eax, eax
0x18001079a  mov     r8d, ecx
0x18001079d  or      r8d, edx
0x1800107a0  cmp     r8d, edx
0x1800107a3  mov     r9d, r8d
0x1800107a6  setz    al
0x1800107a9  or      r9d, ebx
0x1800107ac  cmp     r8d, edx
0x1800107af  mov     [r10+10h], eax
0x1800107b3  mov     eax, edx
0x1800107b5  cmovz   r9d, r8d
0x1800107b9  lock cmpxchg [rsi], r9d
0x1800107be  jz      short loc_1800107C4
0x1800107c0  mov     edx, eax
0x1800107c2  jmp     short loc_180010798
0x1800107c4  test    bl, r9b
0x1800107c7  jz      short loc_1800107CD
0x1800107c9  test    bl, dl
0x1800107cb  jz      short loc_1800107CF
0x1800107cd  xor     ebx, ebx
0x1800107cf  mov     [r10], ebx
0x1800107d2  jmp     loc_18001095E
0x1800107d7  mov     ecx, [rdx]
0x1800107d9  xor     r9d, r9d
0x1800107dc  cmp     r11d, 5
0x1800107e0  mov     ebx, 1
0x1800107e5  setz    r9b
0x1800107e9  mov     eax, ecx
0x1800107eb  mov     dword ptr [r10+4], 0
0x1800107f3  or      eax, ebx
0x1800107f5  mov     edx, eax
0x1800107f7  shr     edx, 16h
0x1800107fa  and     edx, ebx
0x1800107fc  cmp     edx, r9d
0x1800107ff  jz      short loc_180010841
0x180010801  mov     r8d, eax
0x180010804  shr     r8d, 0Fh
0x180010808  and     r8d, 7Fh
0x18001080c  jbe     short loc_180010826
0x18001080e  cmp     r11d, ebx
0x180010811  mov     [r10+4], r8d
0x180010815  mov     edx, 5
0x18001081a  cmovnz  edx, ebx
0x18001081d  and     eax, 0FFC07FFFh
0x180010822  mov     [r10+8], edx
0x180010826  xor     r8d, r8d
0x180010829  mov     edx, 400000h
0x18001082e  cmp     r11d, 5
0x180010832  cmovz   r8d, edx
0x180010836  mov     edx, eax
0x180010838  btr     edx, 16h
0x18001083c  mov     eax, r8d
0x18001083f  or      eax, edx
0x180010841  mov     edx, eax
0x180010843  shr     edx, 0Fh
0x180010846  and     edx, 7Fh
0x180010849  lea     r8d, [rdx+1]
0x18001084d  cmp     r8d, 7Fh
0x180010851  ja      short loc_180010858
0x180010853  cmp     r8d, edx
0x180010856  jnb     short loc_180010863
0x180010858  mov     r8d, ebx
0x18001085b  mov     [r10+8], r11d
0x18001085f  mov     [r10+4], edx
0x180010863  shl     r8d, 0Fh
0x180010867  xor     r8d, eax
0x18001086a  and     r8d, 3F8000h
0x180010871  xor     r8d, eax
0x180010874  mov     eax, ecx
0x180010876  lock cmpxchg [rsi], r8d
0x18001087b  jz      short loc_180010884
0x18001087d  mov     ecx, eax
0x18001087f  jmp     loc_1800107E9
0x180010884  not     ecx
0x180010886  and     ecx, ebx
0x180010888  mov     [r10], ecx
0x18001088b  jmp     loc_180010956
0x180010890  mov     edx, [rdx]
0x180010892  xor     ebp, ebp
0x180010894  lea     ecx, [rbp+4]
0x180010897  cmp     r11d, ecx
0x18001089a  lea     ebx, [rcx-3]
0x18001089d  setz    bpl
0x1800108a1  mov     eax, edx
0x1800108a3  mov     dword ptr [r10+4], 0
0x1800108ab  or      eax, ebx
0x1800108ad  mov     r8d, eax
0x1800108b0  shr     r8d, 0Eh
0x1800108b4  and     r8d, ebx
0x1800108b7  cmp     r8d, ebp
0x1800108ba  jz      short loc_180010903
0x1800108bc  mov     edi, eax
0x1800108be  shr     edi, 5
0x1800108c1  and     edi, 1FFh
0x1800108c7  jbe     short loc_1800108E5
0x1800108c9  mov     r8d, r11d
0x1800108cc  mov     [r10+4], edi
0x1800108d0  neg     r8d
0x1800108d3  sbb     r9d, r9d
0x1800108d6  not     r9d
0x1800108d9  and     r9d, ecx
0x1800108dc  mov     [r10+8], r9d
0x1800108e0  and     eax, 0FFFFC01Fh
0x1800108e5  xor     r9d, r9d
0x1800108e8  mov     r8d, 4000h
0x1800108ee  cmp     r11d, ecx
0x1800108f1  cmovz   r9d, r8d
0x1800108f5  mov     r8d, eax
0x1800108f8  btr     r8d, 0Eh
0x1800108fd  mov     eax, r9d
0x180010900  or      eax, r8d
0x180010903  mov     r8d, eax
0x180010906  shr     r8d, 5
0x18001090a  and     r8d, 1FFh
0x180010911  lea     r9d, [r8+1]
0x180010915  cmp     r9d, 1FFh
0x18001091c  ja      short loc_180010923
0x18001091e  cmp     r9d, r8d
0x180010921  jnb     short loc_18001092E
0x180010923  mov     r9d, ebx
0x180010926  mov     [r10+8], r11d
0x18001092a  mov     [r10+4], r8d
0x18001092e  shl     r9d, 5
0x180010932  xor     r9d, eax
0x180010935  and     r9d, 3FE0h
0x18001093c  xor     r9d, eax
0x18001093f  mov     eax, edx
0x180010941  lock cmpxchg [rsi], r9d
0x180010946  jz      short loc_18001094F
0x180010948  mov     edx, eax
0x18001094a  jmp     loc_1800108A1
0x18001094f  not     edx
0x180010951  and     edx, ebx
0x180010953  mov     [r10], edx
0x180010956  mov     dword ptr [r10+10h], 0
0x18001095e  mov     rax, r10
0x180010961  pop     rdi
0x180010962  pop     rsi
0x180010963  pop     rbp
0x180010964  pop     rbx
0x180010965  retn
```

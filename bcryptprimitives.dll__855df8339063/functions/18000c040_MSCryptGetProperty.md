# MSCryptGetProperty

- ea: `0x18000c040`
- end: `0x18000c7c0`
- name: `MSCryptGetProperty`
- size: `1920`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000afd0`
- `0x18000c860`
- `0x1800667e4`

## callees

- `0x18000c040`
- `0x18000ee60`
- `0x180044eb0`
- `0x180063170`
- `0x180066890`
- `0x18007f771`

## string_xrefs

- `0x18000c098`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c10c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c20e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c2a5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c3b3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c41d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c4d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c52a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c5cf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c78a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000c33a`: `[ BCRYPT_FIPS_SERVICE_INDICATOR]`

## pseudocode

```c
__int64 __fastcall MSCryptGetProperty(__int64 a1, __int64 a2, _OWORD *a3, unsigned int a4, unsigned int *a5, int a6)
{
  unsigned int v10; // ebx
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rax
  const void **v14; // rdx
  __int64 v15; // rcx
  unsigned int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // edx
  int v22; // r8d
  __int64 v23; // rax
  wchar_t *v24; // rcx
  int AlgProperty; // eax
  int v26; // edx
  int v27; // r8d
  _QWORD *v28; // rcx
  const wchar_t *v29; // rdx
  __int64 i; // rcx
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  unsigned int v33; // eax
  char v35; // [rsp+30h] [rbp-48h]

  if ( (a6 & 0xFFFFFF7F) != 0 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        169);
    return v10;
  }
  if ( !a1 || (v11 = *(_DWORD *)(a1 + 4), v11 != 1297306433) && v11 != 1297306443 )
  {
    v10 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        178);
    return v10;
  }
  if ( !a5 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        185);
    return v10;
  }
  v12 = 0;
  while ( *(_WORD *)(a2 + 2 * v12) == aAlgorithmname[v12] && *(_WORD *)(a2 + 2 * v12 + 2) == aAlgorithmname[v12 + 1] )
  {
    v12 += 2;
    if ( v12 == 14 )
    {
      v13 = (unsigned int)*(unsigned __int16 *)(a1 + 8) - 1;
      if ( (unsigned int)v13 >= 9 )
      {
        v10 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)L"AlgorithmName",
            (_DWORD)a3,
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            196);
        return v10;
      }
      v14 = (const void **)&(&off_180084118)[14 * v13];
      v15 = -1;
      while ( *((_WORD *)*v14 + ++v15) != 0 )
        ;
      v17 = 2 * v15 + 2;
      *a5 = v17;
      if ( a3 )
      {
        if ( a4 < v17 )
        {
          v10 = -1073741789;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)v14,
              (_DWORD)a3,
              (unsigned int)"Status",
              35,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
              211);
          return v10;
        }
        memcpy_0(a3, *v14, v17);
      }
      return 0;
    }
  }
  v18 = 0;
  while ( *(_WORD *)(a2 + 2 * v18) == aBlocklength[v18] && *(_WORD *)(a2 + 2 * v18 + 2) == aBlocklength[v18 + 1] )
  {
    v18 += 2;
    if ( v18 == 12 )
    {
      *a5 = 4;
      if ( a3 )
      {
        if ( a4 >= 4 )
        {
          v10 = 0;
          *(_DWORD *)a3 = *(_DWORD *)(a1 + 16);
        }
        else
        {
          v10 = -1073741789;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)L"BlockLength",
              (_DWORD)a3,
              (unsigned int)"Status",
              35,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
              232);
        }
        return v10;
      }
      return 0;
    }
  }
  v19 = -1;
  v20 = -1;
  do
  {
    if ( *(_WORD *)(a2 + 2 * v20 + 2) != aMessageblockle[v20 + 1] )
      break;
    v20 += 2;
    if ( v20 == 19 )
    {
      *a5 = 4;
      if ( a3 )
      {
        if ( a4 >= 4 )
        {
          v10 = 0;
          *(_DWORD *)a3 = *(_DWORD *)(a1 + 20);
        }
        else
        {
          v10 = -1073741789;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              (unsigned int)L"MessageBlockLength",
              (unsigned int)"Status",
              35,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
              254);
        }
        return v10;
      }
      return 0;
    }
  }
  while ( *(_WORD *)(a2 + 2 * v20) == aMessageblockle[v20] );
  while ( *(_WORD *)(a2 + 2 * v19 + 2) == aChainingmode[v19 + 1] )
  {
    v19 += 2;
    if ( v19 == 13 )
    {
      *a5 = 32;
      if ( !a3 )
        return 0;
      if ( a4 >= 0x20 )
      {
        v23 = *(unsigned int *)(a1 + 12);
        if ( (unsigned int)v23 < 6 )
        {
          v10 = 0;
          v24 = rgpszChainModeNameArray[v23];
          *a3 = *(_OWORD *)v24;
          a3[1] = *((_OWORD *)v24 + 1);
        }
        else
        {
          v10 = -1073741816;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)L"ChainingMode",
              (unsigned int)L"MessageBlockLength",
              (unsigned int)"Status",
              8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
              29);
        }
      }
      else
      {
        v10 = -1073741789;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)L"ChainingMode",
            (unsigned int)L"MessageBlockLength",
            (unsigned int)"Status",
            35,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            22);
      }
      return v10;
    }
    if ( *(_WORD *)(a2 + 2 * v19) != aChainingmode[v19] )
      break;
  }
  if ( wcsncmp_0((const wchar_t *)a2, L"[ BCRYPT_FIPS_SERVICE_INDICATOR]", 0x20u) )
  {
    if ( v11 != 1297306433 )
    {
      v29 = L"KeyLength";
      for ( i = 0; i != 10; i += 2 )
      {
        if ( *(_WORD *)(a2 + 2 * i) != aKeylength[i] || *(_WORD *)(a2 + 2 * i + 2) != aKeylength[i + 1] )
        {
          v29 = L"KeyStrength";
          v32 = 0;
          while ( *(_WORD *)(a2 + 2 * v32) == aKeystrength[v32] && *(_WORD *)(a2 + 2 * v32 + 2) == aKeystrength[v32 + 1] )
          {
            v32 += 2;
            if ( v32 == 12 )
            {
              *a5 = 4;
              if ( !a3 )
                return 0;
              if ( a4 < 4 )
              {
                v31 = WPP_GLOBAL_Control;
                v10 = -1073741789;
                goto LABEL_107;
              }
              v10 = 0;
              *(_DWORD *)a3 = *(_DWORD *)(a1 + 24);
              return v10;
            }
          }
          if ( *(_WORD *)a2 != 73 || *(_WORD *)(a2 + 2) != 86 || *(_WORD *)(a2 + 4) )
          {
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (unsigned int)L"KeyStrength",
                v22,
                (unsigned int)"Status",
                187,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                228);
              v31 = WPP_GLOBAL_Control;
            }
            v10 = -1073741637;
            goto LABEL_107;
          }
          v33 = *(_DWORD *)(a1 + 16);
          *a5 = v33;
          if ( !a3 )
            return 0;
          if ( v33 > a4 )
          {
            v31 = WPP_GLOBAL_Control;
            v10 = -1073741789;
            goto LABEL_107;
          }
          memcpy_0(a3, (const void *)(a1 + 40), *(unsigned int *)(a1 + 16));
          return 0;
        }
      }
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( a4 >= 4 )
      {
        *(_DWORD *)a3 = 8 * *(_DWORD *)(a1 + 56);
        return 0;
      }
      else
      {
        v31 = WPP_GLOBAL_Control;
        v10 = -1073741789;
LABEL_107:
        if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            v31[2],
            (_DWORD)v29,
            v22,
            (unsigned int)"Status",
            v10,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            99);
      }
      return v10;
    }
    AlgProperty = MSCryptGetAlgProperty(a1, a2, a3, a4, a5, a6);
    v10 = AlgProperty;
    if ( AlgProperty >= 0 )
      return v10;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v10;
    v35 = 85;
LABEL_73:
    WPP_SF_sDsd(
      v28[2],
      v26,
      v27,
      (unsigned int)"Status",
      AlgProperty,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      v35);
    return v10;
  }
  if ( !a3 )
  {
    *a5 = 4;
    return 0;
  }
  if ( a4 < 4 )
  {
    *a5 = 0;
    v10 = -1073741789;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        v22,
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        56);
    return v10;
  }
  AlgProperty = ApprovedServicesIndicator((wchar_t *)a2);
  v10 = AlgProperty;
  if ( AlgProperty >= 0 )
  {
    *(_DWORD *)a3 = 0;
    *a5 = 4;
    return v10;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v35 = 64;
    goto LABEL_73;
  }
  return v10;
}

```

## disassembly

```asm
0x18000c040  push    rbx
0x18000c042  push    rbp
0x18000c043  push    rsi
0x18000c044  push    rdi
0x18000c045  push    r12
0x18000c047  push    r14
0x18000c049  push    r15
0x18000c04b  sub     rsp, 40h
0x18000c04f  mov     esi, [rsp+78h+arg_28]
0x18000c056  mov     r12d, r9d
0x18000c059  mov     r14, r8
0x18000c05c  mov     rbx, rdx
0x18000c05f  mov     rbp, rcx
0x18000c062  test    esi, 0FFFFFF7Fh
0x18000c068  jz      short loc_18000C0B1
0x18000c06a  mov     ebx, 0C000000Dh
0x18000c06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c076  lea     rdi, WPP_GLOBAL_Control
0x18000c07d  cmp     rcx, rdi
0x18000c080  jz      loc_18000C7AE
0x18000c086  test    byte ptr [rcx+1Ch], 1
0x18000c08a  jz      loc_18000C7AE
0x18000c090  mov     dword ptr [rsp+78h+var_48], 8A9h
0x18000c098  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c09f  mov     [rsp+78h+var_50], rsi
0x18000c0a4  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18000c0ac  jmp     loc_18000C79E
0x18000c0b1  test    rbp, rbp
0x18000c0b4  jz      loc_18000C764
0x18000c0ba  mov     edi, [rcx+4]
0x18000c0bd  cmp     edi, 4D535341h
0x18000c0c3  jz      short loc_18000C0D1
0x18000c0c5  cmp     edi, 4D53534Bh
0x18000c0cb  jnz     loc_18000C764
0x18000c0d1  mov     r15, [rsp+78h+arg_20]
0x18000c0d9  test    r15, r15
0x18000c0dc  jnz     short loc_18000C125
0x18000c0de  mov     ebx, 0C000000Dh
0x18000c0e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0ea  lea     rdi, WPP_GLOBAL_Control
0x18000c0f1  cmp     rcx, rdi
0x18000c0f4  jz      loc_18000C7AE
0x18000c0fa  test    byte ptr [rcx+1Ch], 1
0x18000c0fe  jz      loc_18000C7AE
0x18000c104  mov     dword ptr [rsp+78h+var_48], 8B9h
0x18000c10c  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c113  mov     [rsp+78h+var_50], rsi
0x18000c118  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18000c120  jmp     loc_18000C79E
0x18000c125  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18000c12c  xor     ecx, ecx
0x18000c12e  xchg    ax, ax
0x18000c130  movzx   eax, word ptr [rbx+rcx*2]
0x18000c134  cmp     ax, [rdx+rcx*2]
0x18000c138  jnz     loc_18000C23C
0x18000c13e  movzx   eax, word ptr [rbx+rcx*2+2]
0x18000c143  cmp     ax, [rdx+rcx*2+2]
0x18000c148  jnz     loc_18000C23C
0x18000c14e  add     rcx, 2
0x18000c152  cmp     rcx, 0Eh
0x18000c156  jnz     short loc_18000C130
0x18000c158  movzx   eax, word ptr [rbp+8]
0x18000c15c  dec     eax
0x18000c15e  cmp     eax, 9
0x18000c161  jb      short loc_18000C196
0x18000c163  mov     ebx, 0C0000008h
0x18000c168  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c16f  lea     rdi, WPP_GLOBAL_Control
0x18000c176  cmp     rcx, rdi
0x18000c179  jz      loc_18000C7AE
0x18000c17f  test    byte ptr [rcx+1Ch], 1
0x18000c183  jz      loc_18000C7AE
0x18000c189  mov     dword ptr [rsp+78h+var_48], 8C4h
0x18000c191  jmp     loc_18000C78A
0x18000c196  imul    rcx, rax, 70h ; 'p'
0x18000c19a  lea     rdx, cs:180000000h
0x18000c1a1  lea     rdx, rva off_180084118[rdx]; "RC4" ...
0x18000c1a8  add     rdx, rcx
0x18000c1ab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c1b2  mov     rax, [rdx]
0x18000c1b5  nop     word ptr [rax+rax+00000000h]
0x18000c1c0  cmp     word ptr [rax+rcx*2+2], 0
0x18000c1c6  lea     rcx, [rcx+1]
0x18000c1ca  jnz     short loc_18000C1C0
0x18000c1cc  lea     ecx, ds:2[rcx*2]
0x18000c1d3  mov     [r15], ecx
0x18000c1d6  test    r14, r14
0x18000c1d9  jz      short loc_18000C235
0x18000c1db  cmp     r12d, ecx
0x18000c1de  jnb     short loc_18000C227
0x18000c1e0  mov     ebx, 0C0000023h
0x18000c1e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1ec  lea     rdi, WPP_GLOBAL_Control
0x18000c1f3  cmp     rcx, rdi
0x18000c1f6  jz      loc_18000C7AE
0x18000c1fc  test    byte ptr [rcx+1Ch], 1
0x18000c200  jz      loc_18000C7AE
0x18000c206  mov     dword ptr [rsp+78h+var_48], 8D3h
0x18000c20e  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c215  mov     [rsp+78h+var_50], rsi
0x18000c21a  mov     dword ptr [rsp+78h+var_58], 0C0000023h
0x18000c222  jmp     loc_18000C79E
0x18000c227  mov     rdx, [rdx]; Src
0x18000c22a  mov     r8d, ecx; Size
0x18000c22d  mov     rcx, r14; void *
0x18000c230  call    memcpy_0
0x18000c235  xor     ebx, ebx
0x18000c237  jmp     loc_18000C7AE
0x18000c23c  lea     rdx, aBlocklength; "BlockLength"
0x18000c243  xor     ecx, ecx
0x18000c245  movzx   eax, word ptr [rbx+rcx*2]
0x18000c249  cmp     ax, [rdx+rcx*2]
0x18000c24d  jnz     short loc_18000C2CB
0x18000c24f  movzx   eax, word ptr [rbx+rcx*2+2]
0x18000c254  cmp     ax, [rdx+rcx*2+2]
0x18000c259  jnz     short loc_18000C2CB
0x18000c25b  add     rcx, 2
0x18000c25f  cmp     rcx, 0Ch
0x18000c263  jnz     short loc_18000C245
0x18000c265  mov     dword ptr [r15], 4
0x18000c26c  test    r14, r14
0x18000c26f  jz      short loc_18000C235
0x18000c271  cmp     r12d, 4
0x18000c275  jnb     short loc_18000C2BE
0x18000c277  mov     ebx, 0C0000023h
0x18000c27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c283  lea     rdi, WPP_GLOBAL_Control
0x18000c28a  cmp     rcx, rdi
0x18000c28d  jz      loc_18000C7AE
0x18000c293  test    byte ptr [rcx+1Ch], 1
0x18000c297  jz      loc_18000C7AE
0x18000c29d  mov     dword ptr [rsp+78h+var_48], 8E8h
0x18000c2a5  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c2ac  mov     [rsp+78h+var_50], rsi
0x18000c2b1  mov     dword ptr [rsp+78h+var_58], 0C0000023h
0x18000c2b9  jmp     loc_18000C79E
0x18000c2be  mov     eax, [rbp+10h]
0x18000c2c1  xor     ebx, ebx
0x18000c2c3  mov     [r8], eax
0x18000c2c6  jmp     loc_18000C7AE
0x18000c2cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c2d2  lea     r8, aMessageblockle; "MessageBlockLength"
0x18000c2d9  mov     rdx, rcx
0x18000c2dc  nop     dword ptr [rax+00h]
0x18000c2e0  movzx   eax, word ptr [rbx+rdx*2+2]
0x18000c2e5  cmp     ax, [r8+rdx*2+2]
0x18000c2eb  jnz     short loc_18000C302
0x18000c2ed  add     rdx, 2
0x18000c2f1  cmp     rdx, 13h
0x18000c2f5  jz      short loc_18000C36F
0x18000c2f7  movzx   eax, word ptr [rbx+rdx*2]
0x18000c2fb  cmp     ax, [r8+rdx*2]
0x18000c300  jz      short loc_18000C2E0
0x18000c302  lea     rdx, aChainingmode; "ChainingMode"
0x18000c309  nop     dword ptr [rax+00000000h]
0x18000c310  movzx   eax, word ptr [rbx+rcx*2+2]
0x18000c315  cmp     ax, [rdx+rcx*2+2]
0x18000c31a  jnz     short loc_18000C334
0x18000c31c  add     rcx, 2
0x18000c320  cmp     rcx, 0Dh
0x18000c324  jz      loc_18000C3D9
0x18000c32a  movzx   eax, word ptr [rbx+rcx*2]
0x18000c32e  cmp     ax, [rdx+rcx*2]
0x18000c332  jz      short loc_18000C310
0x18000c334  mov     r8d, 20h ; ' '; MaxCount
0x18000c33a  lea     rdx, aBcryptFipsServ; "[ BCRYPT_FIPS_SERVICE_INDICATOR]"
0x18000c341  mov     rcx, rbx; String1
0x18000c344  call    wcsncmp_0
0x18000c349  test    eax, eax
0x18000c34b  jnz     loc_18000C555
0x18000c351  mov     [rsp+78h+arg_28], eax
0x18000c358  test    r14, r14
0x18000c35b  jnz     loc_18000C497
0x18000c361  mov     dword ptr [r15], 4
0x18000c368  xor     ebx, ebx
0x18000c36a  jmp     loc_18000C7AE
0x18000c36f  mov     dword ptr [r15], 4
0x18000c376  test    r14, r14
0x18000c379  jz      loc_18000C235
0x18000c37f  cmp     r12d, 4
0x18000c383  jnb     short loc_18000C3CC
0x18000c385  mov     ebx, 0C0000023h
0x18000c38a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c391  lea     rdi, WPP_GLOBAL_Control
0x18000c398  cmp     rcx, rdi
0x18000c39b  jz      loc_18000C7AE
0x18000c3a1  test    byte ptr [rcx+1Ch], 1
0x18000c3a5  jz      loc_18000C7AE
0x18000c3ab  mov     dword ptr [rsp+78h+var_48], 8FEh
0x18000c3b3  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c3ba  mov     [rsp+78h+var_50], rsi
0x18000c3bf  mov     dword ptr [rsp+78h+var_58], 0C0000023h
0x18000c3c7  jmp     loc_18000C79E
0x18000c3cc  mov     eax, [rbp+14h]
0x18000c3cf  xor     ebx, ebx
0x18000c3d1  mov     [r14], eax
0x18000c3d4  jmp     loc_18000C7AE
0x18000c3d9  mov     dword ptr [r15], 20h ; ' '
0x18000c3e0  test    r14, r14
0x18000c3e3  jz      loc_18000C235
0x18000c3e9  cmp     r12d, 20h ; ' '
0x18000c3ed  jnb     short loc_18000C436
0x18000c3ef  mov     ebx, 0C0000023h
0x18000c3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3fb  lea     rdi, WPP_GLOBAL_Control
0x18000c402  cmp     rcx, rdi
0x18000c405  jz      loc_18000C7AE
0x18000c40b  test    byte ptr [rcx+1Ch], 1
0x18000c40f  jz      loc_18000C7AE
0x18000c415  mov     dword ptr [rsp+78h+var_48], 916h
0x18000c41d  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c424  mov     [rsp+78h+var_50], rsi
0x18000c429  mov     dword ptr [rsp+78h+var_58], 0C0000023h
0x18000c431  jmp     loc_18000C79E
0x18000c436  mov     eax, [rbp+0Ch]
0x18000c439  cmp     eax, 6
0x18000c43c  jb      short loc_18000C471
0x18000c43e  mov     ebx, 0C0000008h
0x18000c443  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c44a  lea     rdi, WPP_GLOBAL_Control
0x18000c451  cmp     rcx, rdi
0x18000c454  jz      loc_18000C7AE
0x18000c45a  test    byte ptr [rcx+1Ch], 1
0x18000c45e  jz      loc_18000C7AE
0x18000c464  mov     dword ptr [rsp+78h+var_48], 91Dh
0x18000c46c  jmp     loc_18000C78A
0x18000c471  lea     rdx, cs:180000000h
0x18000c478  xor     ebx, ebx
0x18000c47a  mov     rcx, ds:rva rgpszChainModeNameArray[rdx+rax*8]
0x18000c482  movups  xmm0, xmmword ptr [rcx]
0x18000c485  movups  xmmword ptr [r14], xmm0
0x18000c489  movups  xmm1, xmmword ptr [rcx+10h]
0x18000c48d  movups  xmmword ptr [r14+10h], xmm1
0x18000c492  jmp     loc_18000C7AE
0x18000c497  cmp     r12d, 4
0x18000c49b  jnb     short loc_18000C4EB
0x18000c49d  mov     dword ptr [r15], 0
0x18000c4a4  mov     ebx, 0C0000023h
0x18000c4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4b0  lea     rdi, WPP_GLOBAL_Control
0x18000c4b7  cmp     rcx, rdi
0x18000c4ba  jz      loc_18000C7AE
0x18000c4c0  test    byte ptr [rcx+1Ch], 1
0x18000c4c4  jz      loc_18000C7AE
0x18000c4ca  mov     dword ptr [rsp+78h+var_48], 938h
0x18000c4d2  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c4d9  mov     [rsp+78h+var_50], rsi
0x18000c4de  mov     dword ptr [rsp+78h+var_58], 0C0000023h
0x18000c4e6  jmp     loc_18000C79E
0x18000c4eb  lea     rdx, [rsp+78h+arg_28]
0x18000c4f3  mov     rcx, rbx; Source
0x18000c4f6  call    ApprovedServicesIndicator
0x18000c4fb  mov     ebx, eax
0x18000c4fd  test    eax, eax
0x18000c4ff  jns     short loc_18000C53F
0x18000c501  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c508  lea     rdi, WPP_GLOBAL_Control
0x18000c50f  cmp     rcx, rdi
0x18000c512  jz      loc_18000C7AE
0x18000c518  test    byte ptr [rcx+1Ch], 1
0x18000c51c  jz      loc_18000C7AE
0x18000c522  mov     dword ptr [rsp+78h+var_48], 940h
0x18000c52a  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c531  mov     [rsp+78h+var_50], rsi
0x18000c536  mov     dword ptr [rsp+78h+var_58], eax
0x18000c53a  jmp     loc_18000C79E
0x18000c53f  mov     eax, [rsp+78h+arg_28]
0x18000c546  mov     [r14], eax
0x18000c549  mov     dword ptr [r15], 4
0x18000c550  jmp     loc_18000C7AE
0x18000c555  cmp     edi, 4D535341h
0x18000c55b  jnz     short loc_18000C5AF
0x18000c55d  mov     dword ptr [rsp+78h+var_50], esi
0x18000c561  mov     r9d, r12d
0x18000c564  mov     r8, r14
0x18000c567  mov     [rsp+78h+var_58], r15
0x18000c56c  mov     rdx, rbx
0x18000c56f  mov     rcx, rbp
0x18000c572  call    MSCryptGetAlgProperty
0x18000c577  mov     ebx, eax
0x18000c579  test    eax, eax
0x18000c57b  jns     loc_18000C7AE
0x18000c581  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c588  lea     rdi, WPP_GLOBAL_Control
0x18000c58f  cmp     rcx, rdi
0x18000c592  jz      loc_18000C7AE
0x18000c598  test    byte ptr [rcx+1Ch], 1
0x18000c59c  jz      loc_18000C7AE
0x18000c5a2  mov     dword ptr [rsp+78h+var_48], 955h
0x18000c5aa  jmp     loc_18000C52A
0x18000c5af  cmp     edi, 4D53534Bh
0x18000c5b5  jnz     loc_18000C73C
0x18000c5bb  lea     rdx, aKeylength; "KeyLength"
0x18000c5c2  xor     ecx, ecx
0x18000c5c4  movzx   eax, word ptr [rbx+rcx*2]
0x18000c5c8  lea     rdi, WPP_GLOBAL_Control
0x18000c5cf  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c5d6  cmp     ax, [rdx+rcx*2]
0x18000c5da  jnz     short loc_18000C629
0x18000c5dc  movzx   eax, word ptr [rbx+rcx*2+2]
  ... truncated ...
```

# VBSAttestationHashClaimGeneralParams

- ea: `0x140037264`
- end: `0x140037534`
- name: `VBSAttestationHashClaimGeneralParams`
- size: `720`
- prototype: `__int64 __usercall@<rax>(BCRYPT_HASH_HANDLE hHash@<rcx>, PUCHAR, ULONG cbInput, PUCHAR, ULONG, PUCHAR, ULONG, PUCHAR)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003753c`
- `0x1400377b8`

## callees

- `0x140037264`
- `0x1400385f0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x140037292`
- `bcrypt!BCryptHashData` at `0x1400372b5`
- `bcrypt!BCryptHashData` at `0x1400372d6`
- `bcrypt!BCryptHashData` at `0x1400372f7`
- `bcrypt!BCryptHashData` at `0x140037319`
- `bcrypt!BCryptHashData` at `0x14003733e`
- `bcrypt!BCryptHashData` at `0x14003736a`
- `bcrypt!BCryptHashData` at `0x14003738f`
- `bcrypt!BCryptHashData` at `0x1400373c4`
- `bcrypt!BCryptHashData` at `0x14003740a`
- `bcrypt!BCryptHashData` at `0x14003744c`
- `bcrypt!BCryptHashData` at `0x140037470`
- `bcrypt!BCryptHashData` at `0x140037494`
- `bcrypt!BCryptHashData` at `0x1400374b8`
- `bcrypt!BCryptHashData` at `0x1400374dd`
- `bcrypt!BCryptHashData` at `0x140037292`
- `bcrypt!BCryptHashData` at `0x1400372b5`
- `bcrypt!BCryptHashData` at `0x1400372d6`
- `bcrypt!BCryptHashData` at `0x1400372f7`
- `bcrypt!BCryptHashData` at `0x140037319`
- `bcrypt!BCryptHashData` at `0x14003733e`
- `bcrypt!BCryptHashData` at `0x14003736a`
- `bcrypt!BCryptHashData` at `0x14003738f`
- `bcrypt!BCryptHashData` at `0x1400373c4`
- `bcrypt!BCryptHashData` at `0x14003740a`
- `bcrypt!BCryptHashData` at `0x14003744c`
- `bcrypt!BCryptHashData` at `0x140037470`
- `bcrypt!BCryptHashData` at `0x140037494`
- `bcrypt!BCryptHashData` at `0x1400374b8`
- `bcrypt!BCryptHashData` at `0x1400374dd`

## string_xrefs

- `0x14003750c`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationHashClaimGeneralParams(
        BCRYPT_HASH_HANDLE hHash,
        int a2,
        UCHAR *a3,
        int a4,
        PUCHAR a5,
        ULONG cbInput,
        PUCHAR a7,
        ULONG a8,
        PUCHAR a9,
        ULONG a10,
        PUCHAR a11)
{
  NTSTATUS v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rcx
  PUCHAR v17; // rsi
  int v19; // [rsp+48h] [rbp+10h] BYREF
  int pbInput; // [rsp+58h] [rbp+20h] BYREF

  pbInput = a4;
  v19 = a2;
  v13 = BCryptHashData(hHash, (PUCHAR)&v19, 4u, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 63;
LABEL_3:
    v16 = (unsigned int)v13;
LABEL_43:
    DebugTraceError(
      v16,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
      v15);
    return v14;
  }
  v13 = BCryptHashData(hHash, a3, 4u, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 75;
    goto LABEL_3;
  }
  v13 = BCryptHashData(hHash, a3 + 4, 4u, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 86;
    goto LABEL_3;
  }
  v13 = BCryptHashData(hHash, a3 + 8, 4u, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 97;
    goto LABEL_3;
  }
  v13 = BCryptHashData(hHash, a3 + 12, *((_DWORD *)a3 + 2), 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 108;
    goto LABEL_3;
  }
  v13 = BCryptHashData(hHash, (PUCHAR)&pbInput, 4u, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 119;
    goto LABEL_3;
  }
  if ( a5 )
  {
    v13 = BCryptHashData(hHash, a5, cbInput, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 133;
      goto LABEL_3;
    }
  }
  v13 = BCryptHashData(hHash, (PUCHAR)&cbInput, 4u, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 145;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    if ( !a8 )
      goto LABEL_24;
LABEL_41:
    v15 = 169;
    goto LABEL_42;
  }
  if ( !a8 )
    goto LABEL_41;
  v13 = BCryptHashData(hHash, a7, a8, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 159;
    goto LABEL_3;
  }
LABEL_24:
  if ( !a9 )
  {
    if ( !a10 )
      goto LABEL_29;
    goto LABEL_40;
  }
  if ( !a10 )
  {
LABEL_40:
    v15 = 194;
LABEL_42:
    v16 = 3221225701LL;
    v14 = -1073741595;
    goto LABEL_43;
  }
  v13 = BCryptHashData(hHash, a9, a10, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 184;
    goto LABEL_3;
  }
LABEL_29:
  v17 = a11;
  if ( a11 )
  {
    v13 = BCryptHashData(hHash, a11, 4u, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 209;
      goto LABEL_3;
    }
    v13 = BCryptHashData(hHash, v17 + 4, 4u, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 220;
      goto LABEL_3;
    }
    v13 = BCryptHashData(hHash, v17 + 8, 4u, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 231;
      goto LABEL_3;
    }
    v13 = BCryptHashData(hHash, v17 + 12, 4u, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 242;
      goto LABEL_3;
    }
    v13 = BCryptHashData(hHash, v17 + 16, *((_DWORD *)v17 + 2), 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 253;
      goto LABEL_3;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x140037264  mov     rax, rsp
0x140037267  mov     [rax+8], rbx
0x14003726b  mov     [rax+18h], rbp
0x14003726f  mov     [rax+20h], r9d
0x140037273  mov     [rax+10h], edx
0x140037276  push    rsi
0x140037277  push    rdi
0x140037278  push    r14
0x14003727a  sub     rsp, 20h
0x14003727e  xor     r9d, r9d; dwFlags
0x140037281  lea     rdx, [rax+10h]; pbInput
0x140037285  mov     rsi, r8
0x140037288  mov     rdi, rcx
0x14003728b  lea     ebp, [r9+4]
0x14003728f  mov     r8d, ebp; cbInput
0x140037292  call    cs:__imp_BCryptHashData
0x140037298  mov     ebx, eax
0x14003729a  test    eax, eax
0x14003729c  jns     short loc_1400372A9
0x14003729e  lea     r9d, [rbp+3Bh]
0x1400372a2  mov     ecx, eax
0x1400372a4  jmp     loc_14003750C
0x1400372a9  xor     r9d, r9d; dwFlags
0x1400372ac  mov     r8d, ebp; cbInput
0x1400372af  mov     rdx, rsi; pbInput
0x1400372b2  mov     rcx, rdi; hHash
0x1400372b5  call    cs:__imp_BCryptHashData
0x1400372bb  mov     ebx, eax
0x1400372bd  test    eax, eax
0x1400372bf  jns     short loc_1400372C9
0x1400372c1  mov     r9d, 4Bh ; 'K'
0x1400372c7  jmp     short loc_1400372A2
0x1400372c9  lea     rdx, [rsi+4]; pbInput
0x1400372cd  xor     r9d, r9d; dwFlags
0x1400372d0  mov     r8d, ebp; cbInput
0x1400372d3  mov     rcx, rdi; hHash
0x1400372d6  call    cs:__imp_BCryptHashData
0x1400372dc  mov     ebx, eax
0x1400372de  test    eax, eax
0x1400372e0  jns     short loc_1400372EA
0x1400372e2  mov     r9d, 56h ; 'V'
0x1400372e8  jmp     short loc_1400372A2
0x1400372ea  xor     r9d, r9d; dwFlags
0x1400372ed  lea     rdx, [rsi+8]; pbInput
0x1400372f1  mov     r8d, ebp; cbInput
0x1400372f4  mov     rcx, rdi; hHash
0x1400372f7  call    cs:__imp_BCryptHashData
0x1400372fd  mov     ebx, eax
0x1400372ff  test    eax, eax
0x140037301  jns     short loc_14003730B
0x140037303  mov     r9d, 61h ; 'a'
0x140037309  jmp     short loc_1400372A2
0x14003730b  mov     r8d, [rsi+8]; cbInput
0x14003730f  lea     rdx, [rsi+0Ch]; pbInput
0x140037313  xor     r9d, r9d; dwFlags
0x140037316  mov     rcx, rdi; hHash
0x140037319  call    cs:__imp_BCryptHashData
0x14003731f  mov     ebx, eax
0x140037321  test    eax, eax
0x140037323  jns     short loc_140037330
0x140037325  mov     r9d, 6Ch ; 'l'
0x14003732b  jmp     loc_1400372A2
0x140037330  xor     r9d, r9d; dwFlags
0x140037333  lea     rdx, [rsp+38h+pbInput]; pbInput
0x140037338  mov     r8d, ebp; cbInput
0x14003733b  mov     rcx, rdi; hHash
0x14003733e  call    cs:__imp_BCryptHashData
0x140037344  mov     ebx, eax
0x140037346  test    eax, eax
0x140037348  jns     short loc_140037355
0x14003734a  mov     r9d, 77h ; 'w'
0x140037350  jmp     loc_1400372A2
0x140037355  mov     rdx, [rsp+38h+arg_20]; pbInput
0x14003735a  test    rdx, rdx
0x14003735d  jz      short loc_140037381
0x14003735f  mov     r8d, [rsp+38h+cbInput]; cbInput
0x140037364  xor     r9d, r9d; dwFlags
0x140037367  mov     rcx, rdi; hHash
0x14003736a  call    cs:__imp_BCryptHashData
0x140037370  mov     ebx, eax
0x140037372  test    eax, eax
0x140037374  jns     short loc_140037381
0x140037376  mov     r9d, 85h
0x14003737c  jmp     loc_1400372A2
0x140037381  xor     r9d, r9d; dwFlags
0x140037384  lea     rdx, [rsp+38h+cbInput]; pbInput
0x140037389  mov     r8d, ebp; cbInput
0x14003738c  mov     rcx, rdi; hHash
0x14003738f  call    cs:__imp_BCryptHashData
0x140037395  mov     ebx, eax
0x140037397  test    eax, eax
0x140037399  jns     short loc_1400373A6
0x14003739b  mov     r9d, 91h
0x1400373a1  jmp     loc_1400372A2
0x1400373a6  mov     rdx, [rsp+38h+arg_30]; pbInput
0x1400373ab  test    rdx, rdx
0x1400373ae  jz      short loc_1400373DB
0x1400373b0  mov     r8d, [rsp+38h+arg_38]; cbInput
0x1400373b5  test    r8d, r8d
0x1400373b8  jz      loc_1400374FC
0x1400373be  xor     r9d, r9d; dwFlags
0x1400373c1  mov     rcx, rdi; hHash
0x1400373c4  call    cs:__imp_BCryptHashData
0x1400373ca  mov     ebx, eax
0x1400373cc  test    eax, eax
0x1400373ce  jns     short loc_1400373E6
0x1400373d0  mov     r9d, 9Fh
0x1400373d6  jmp     loc_1400372A2
0x1400373db  cmp     [rsp+38h+arg_38], 0
0x1400373e0  jnz     loc_1400374FC
0x1400373e6  mov     rdx, [rsp+38h+arg_40]; pbInput
0x1400373ee  test    rdx, rdx
0x1400373f1  jz      short loc_140037421
0x1400373f3  mov     r8d, [rsp+38h+arg_48]; cbInput
0x1400373fb  test    r8d, r8d
0x1400373fe  jz      loc_1400374F4
0x140037404  xor     r9d, r9d; dwFlags
0x140037407  mov     rcx, rdi; hHash
0x14003740a  call    cs:__imp_BCryptHashData
0x140037410  mov     ebx, eax
0x140037412  test    eax, eax
0x140037414  jns     short loc_14003742F
0x140037416  mov     r9d, 0B8h
0x14003741c  jmp     loc_1400372A2
0x140037421  cmp     [rsp+38h+arg_48], 0
0x140037429  jnz     loc_1400374F4
0x14003742f  mov     rsi, [rsp+38h+arg_50]
0x140037437  test    rsi, rsi
0x14003743a  jz      loc_14003751F
0x140037440  xor     r9d, r9d; dwFlags
0x140037443  mov     r8d, ebp; cbInput
0x140037446  mov     rdx, rsi; pbInput
0x140037449  mov     rcx, rdi; hHash
0x14003744c  call    cs:__imp_BCryptHashData
0x140037452  mov     ebx, eax
0x140037454  test    eax, eax
0x140037456  jns     short loc_140037463
0x140037458  mov     r9d, 0D1h
0x14003745e  jmp     loc_1400372A2
0x140037463  lea     rdx, [rsi+4]; pbInput
0x140037467  xor     r9d, r9d; dwFlags
0x14003746a  mov     r8d, ebp; cbInput
0x14003746d  mov     rcx, rdi; hHash
0x140037470  call    cs:__imp_BCryptHashData
0x140037476  mov     ebx, eax
0x140037478  test    eax, eax
0x14003747a  jns     short loc_140037487
0x14003747c  mov     r9d, 0DCh
0x140037482  jmp     loc_1400372A2
0x140037487  xor     r9d, r9d; dwFlags
0x14003748a  lea     rdx, [rsi+8]; pbInput
0x14003748e  mov     r8d, ebp; cbInput
0x140037491  mov     rcx, rdi; hHash
0x140037494  call    cs:__imp_BCryptHashData
0x14003749a  mov     ebx, eax
0x14003749c  test    eax, eax
0x14003749e  jns     short loc_1400374AB
0x1400374a0  mov     r9d, 0E7h
0x1400374a6  jmp     loc_1400372A2
0x1400374ab  lea     rdx, [rsi+0Ch]; pbInput
0x1400374af  xor     r9d, r9d; dwFlags
0x1400374b2  mov     r8d, ebp; cbInput
0x1400374b5  mov     rcx, rdi; hHash
0x1400374b8  call    cs:__imp_BCryptHashData
0x1400374be  mov     ebx, eax
0x1400374c0  test    eax, eax
0x1400374c2  jns     short loc_1400374CF
0x1400374c4  mov     r9d, 0F2h
0x1400374ca  jmp     loc_1400372A2
0x1400374cf  mov     r8d, [rsi+8]; cbInput
0x1400374d3  lea     rdx, [rsi+10h]; pbInput
0x1400374d7  xor     r9d, r9d; dwFlags
0x1400374da  mov     rcx, rdi; hHash
0x1400374dd  call    cs:__imp_BCryptHashData
0x1400374e3  mov     ebx, eax
0x1400374e5  test    eax, eax
0x1400374e7  jns     short loc_14003751F
0x1400374e9  mov     r9d, 0FDh
0x1400374ef  jmp     loc_1400372A2
0x1400374f4  mov     r9d, 0C2h
0x1400374fa  jmp     short loc_140037502
0x1400374fc  mov     r9d, 0A9h
0x140037502  mov     ecx, 0C00000E5h
0x140037507  mov     ebx, 0C00000E5h
0x14003750c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140037513  lea     rdx, aStatus; "Status"
0x14003751a  call    DebugTraceError
0x14003751f  mov     rbp, [rsp+38h+arg_10]
0x140037524  mov     eax, ebx
0x140037526  mov     rbx, [rsp+38h+arg_0]
0x14003752b  add     rsp, 20h
0x14003752f  pop     r14
0x140037531  pop     rdi
0x140037532  pop     rsi
0x140037533  retn
```

# SipcSectionId::InitializeFromData(unsigned __int64,void const *)

- ea: `0x180029cf8`
- end: `0x180029e6a`
- name: `?InitializeFromData@SipcSectionId@@QEAAJ_KPEBX@Z`
- size: `370`
- prototype: `__int64 __fastcall(PUCHAR pbOutput, ULONG cbInput, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027c80`

## callees

- `0x180029cf8`
- `0x18002bbd0`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180029db2`
- `bcrypt!BCryptDestroyHash` at `0x180029e28`
- `bcrypt!BCryptDestroyHash` at `0x180029db2`
- `bcrypt!BCryptDestroyHash` at `0x180029e28`
- `bcrypt!BCryptHashData` at `0x180029dd8`
- `bcrypt!BCryptHashData` at `0x180029dd8`
- `bcrypt!BCryptCreateHash` at `0x180029d8c`
- `bcrypt!BCryptCreateHash` at `0x180029d8c`
- `bcrypt!BCryptFinishHash` at `0x180029df6`
- `bcrypt!BCryptFinishHash` at `0x180029df6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180029d26`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180029d26`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029d4e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029e47`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029d4e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029e47`

## pseudocode

```c
__int64 __fastcall SipcSectionId::InitializeFromData(PUCHAR pbOutput, ULONG cbInput, PUCHAR pbInput)
{
  NTSTATUS v6; // eax
  BCRYPT_ALG_HANDLE v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  NTSTATUS v11; // eax
  BCRYPT_HASH_HANDLE v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+98h] [rbp+40h] BYREF

  phAlgorithm = 0;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  v7 = phAlgorithm;
  if ( v6 < 0 )
  {
    v8 = v6 | 0x10000000;
    v9 = -2147418113;
    if ( v8 < 0 )
      v9 = v8;
LABEL_4:
    if ( v7 )
      BCryptCloseAlgorithmProvider(v7, 0);
    return v9;
  }
  phHash = 0;
  v11 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  v12 = phHash;
  if ( v11 < 0 || (v11 = BCryptHashData(phHash, pbInput, cbInput, 0), v12 = phHash, v11 < 0) )
  {
LABEL_8:
    v13 = v11 | 0x10000000;
    v9 = -2147418113;
    if ( v13 < 0 )
      v9 = v13;
    if ( v12 )
    {
      BCryptDestroyHash(v12);
      phHash = 0;
    }
    v7 = phAlgorithm;
    goto LABEL_4;
  }
  v11 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v11 < 0 )
  {
    v12 = phHash;
    goto LABEL_8;
  }
  v14 = 0;
  while ( !pbOutput[v14] )
  {
    if ( (unsigned __int64)++v14 >= 0x20 )
    {
      SipcFailFast(2147549183LL);
      JUMPOUT(0x180029E69LL);
    }
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return 0;
}

```

## disassembly

```asm
0x180029cf8  push    rbp
0x180029cfa  push    rbx
0x180029cfb  push    rsi
0x180029cfc  push    rdi
0x180029cfd  mov     rbp, rsp
0x180029d00  sub     rsp, 58h
0x180029d04  mov     rdi, r8
0x180029d07  mov     [rbp+phAlgorithm], 0
0x180029d0f  mov     rsi, rdx
0x180029d12  mov     rbx, rcx
0x180029d15  xor     r8d, r8d; pszImplementation
0x180029d18  lea     rdx, pszAlgId; "SHA256"
0x180029d1f  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180029d23  xor     r9d, r9d; dwFlags
0x180029d26  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180029d2d  nop     dword ptr [rax+rax+00h]
0x180029d32  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180029d36  test    eax, eax
0x180029d38  jns     short loc_180029D61
0x180029d3a  or      eax, 10000000h
0x180029d3f  mov     ebx, 8000FFFFh
0x180029d44  cmovl   ebx, eax
0x180029d47  test    rcx, rcx
0x180029d4a  jz      short loc_180029D5A
0x180029d4c  xor     edx, edx; dwFlags
0x180029d4e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180029d55  nop     dword ptr [rax+rax+00h]
0x180029d5a  mov     eax, ebx
0x180029d5c  jmp     loc_180029E55
0x180029d61  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180029d69  lea     rdx, [rbp+phHash]; phHash
0x180029d6d  mov     [rsp+58h+cbSecret], 0; cbSecret
0x180029d75  xor     r9d, r9d; cbHashObject
0x180029d78  xor     r8d, r8d; pbHashObject
0x180029d7b  mov     [rsp+58h+pbSecret], 0; pbSecret
0x180029d84  mov     [rbp+phHash], 0
0x180029d8c  call    cs:__imp_BCryptCreateHash
0x180029d93  nop     dword ptr [rax+rax+00h]
0x180029d98  mov     rcx, [rbp+phHash]; hHash
0x180029d9c  test    eax, eax
0x180029d9e  jns     short loc_180029DCF
0x180029da0  or      eax, 10000000h
0x180029da5  mov     ebx, 8000FFFFh
0x180029daa  cmovl   ebx, eax
0x180029dad  test    rcx, rcx
0x180029db0  jz      short loc_180029DC6
0x180029db2  call    cs:__imp_BCryptDestroyHash
0x180029db9  nop     dword ptr [rax+rax+00h]
0x180029dbe  mov     [rbp+phHash], 0
0x180029dc6  mov     rcx, [rbp+phAlgorithm]
0x180029dca  jmp     loc_180029D47
0x180029dcf  mov     r8d, esi; cbInput
0x180029dd2  xor     r9d, r9d; dwFlags
0x180029dd5  mov     rdx, rdi; pbInput
0x180029dd8  call    cs:__imp_BCryptHashData
0x180029ddf  nop     dword ptr [rax+rax+00h]
0x180029de4  mov     rcx, [rbp+phHash]; hHash
0x180029de8  test    eax, eax
0x180029dea  js      short loc_180029DA0
0x180029dec  xor     r9d, r9d; dwFlags
0x180029def  mov     rdx, rbx; pbOutput
0x180029df2  lea     r8d, [r9+20h]; cbOutput
0x180029df6  call    cs:__imp_BCryptFinishHash
0x180029dfd  nop     dword ptr [rax+rax+00h]
0x180029e02  test    eax, eax
0x180029e04  jns     short loc_180029E0C
0x180029e06  mov     rcx, [rbp+phHash]
0x180029e0a  jmp     short loc_180029DA0
0x180029e0c  xor     eax, eax
0x180029e0e  cmp     byte ptr [rbx+rax], 0
0x180029e12  jnz     short loc_180029E1F
0x180029e14  inc     rax
0x180029e17  cmp     rax, 20h ; ' '
0x180029e1b  jnb     short loc_180029E5F
0x180029e1d  jmp     short loc_180029E0E
0x180029e1f  mov     rcx, [rbp+phHash]; hHash
0x180029e23  test    rcx, rcx
0x180029e26  jz      short loc_180029E3C
0x180029e28  call    cs:__imp_BCryptDestroyHash
0x180029e2f  nop     dword ptr [rax+rax+00h]
0x180029e34  mov     [rbp+phHash], 0
0x180029e3c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180029e40  test    rcx, rcx
0x180029e43  jz      short loc_180029E53
0x180029e45  xor     edx, edx; dwFlags
0x180029e47  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180029e4e  nop     dword ptr [rax+rax+00h]
0x180029e53  xor     eax, eax
0x180029e55  add     rsp, 58h
0x180029e59  pop     rdi
0x180029e5a  pop     rsi
0x180029e5b  pop     rbx
0x180029e5c  pop     rbp
0x180029e5d  retn
0x180029e5f  mov     ecx, 8000FFFFh
0x180029e64  call    SipcFailFast
```

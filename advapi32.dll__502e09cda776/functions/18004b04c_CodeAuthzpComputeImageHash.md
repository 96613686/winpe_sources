# CodeAuthzpComputeImageHash

- ea: `0x18004b04c`
- end: `0x18004b339`
- name: `CodeAuthzpComputeImageHash`
- size: `749`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018980`

## callees

- `0x18004b04c`
- `0x18004d358`
- `0x1800720b0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18004b151`
- `KERNEL32!HeapAlloc` at `0x18004b151`
- `KERNEL32!GetProcessHeap` at `0x18004b13d`
- `KERNEL32!GetProcessHeap` at `0x18004b2e4`
- `KERNEL32!GetProcessHeap` at `0x18004b13d`
- `KERNEL32!GetProcessHeap` at `0x18004b2e4`
- `KERNEL32!MapViewOfFile` at `0x18004b22c`
- `KERNEL32!MapViewOfFile` at `0x18004b22c`
- `KERNEL32!UnmapViewOfFile` at `0x18004b263`
- `KERNEL32!UnmapViewOfFile` at `0x18004b2b3`
- `KERNEL32!UnmapViewOfFile` at `0x18004b263`
- `KERNEL32!UnmapViewOfFile` at `0x18004b2b3`
- `KERNEL32!HeapFree` at `0x18004b2f8`
- `KERNEL32!HeapFree` at `0x18004b2f8`
- `bcrypt!BCryptDestroyHash` at `0x18004b2c9`
- `bcrypt!BCryptDestroyHash` at `0x18004b2c9`
- `bcrypt!BCryptHashData` at `0x18004b1e3`
- `bcrypt!BCryptHashData` at `0x18004b24e`
- `bcrypt!BCryptHashData` at `0x18004b1e3`
- `bcrypt!BCryptHashData` at `0x18004b24e`
- `bcrypt!BCryptCreateHash` at `0x18004b19c`
- `bcrypt!BCryptCreateHash` at `0x18004b19c`
- `bcrypt!BCryptFinishHash` at `0x18004b28c`
- `bcrypt!BCryptFinishHash` at `0x18004b28c`

## pseudocode

```c
__int64 __fastcall CodeAuthzpComputeImageHash(
        unsigned __int64 pbInput,
        void *a2,
        __int64 a3,
        int a4,
        UCHAR *a5,
        _DWORD *a6)
{
  UCHAR *v6; // rbp
  BCRYPT_ALG_HANDLE v8; // rax
  BCRYPT_ALG_HANDLE *v9; // r15
  UCHAR *v10; // r12
  NTSTATUS v11; // esi
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v14; // rbx
  __int64 v15; // r14
  __int64 v16; // r14
  UCHAR *v17; // rax
  HANDLE v18; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-168h] BYREF
  HANDLE hFileMappingObject; // [rsp+48h] [rbp-160h]
  PUCHAR pbOutput; // [rsp+50h] [rbp-158h]
  _DWORD *v23; // [rsp+58h] [rbp-150h]
  _BYTE v24[256]; // [rsp+60h] [rbp-148h] BYREF

  v6 = (UCHAR *)pbInput;
  pbOutput = a5;
  hFileMappingObject = a2;
  v23 = a6;
  phHash = 0;
  if ( __PAIR128__(pbInput, (unsigned __int64)a2) == 0 || !a3 || !a5 || !a6 )
    return 3221225485LL;
  if ( a4 != 32771 )
  {
    if ( a4 == 32780 )
    {
      v8 = g_AlgSHA256;
      v9 = &g_AlgSHA256;
      goto LABEL_9;
    }
    return 3221225485LL;
  }
  v8 = g_AlgMD5;
  v9 = &g_AlgMD5;
LABEL_9:
  v10 = 0;
  if ( !v8 )
  {
    v11 = SaferpAcquireBCryptAlgorithmProvider(v9);
    if ( v11 < 0 )
      goto LABEL_35;
  }
  if ( *a6 >= *((_DWORD *)v9 + 3) )
  {
    if ( *((_DWORD *)v9 + 2) <= 0x100u )
    {
      v10 = v24;
    }
    else
    {
      v12 = *((_DWORD *)v9 + 2);
      ProcessHeap = GetProcessHeap();
      v10 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v12);
      if ( !v10 )
      {
        v11 = -1073741801;
        goto LABEL_35;
      }
    }
    v11 = BCryptCreateHash(*v9, &phHash, v10, *((_DWORD *)v9 + 2), 0, 0, 0);
    if ( v11 >= 0 )
    {
      v14 = 0;
      if ( v6 )
      {
        while ( 1 )
        {
          v15 = a3 - v14;
          if ( a3 - v14 <= 0 )
            break;
          if ( v15 > 0x4000000 )
            v15 = 0x4000000;
          v11 = BCryptHashData(phHash, v6, v15, 0);
          if ( v11 < 0 )
            goto LABEL_33;
          v6 += v15;
          v14 += v15;
        }
      }
      else
      {
        while ( 1 )
        {
          v6 = 0;
          v16 = a3 - v14;
          if ( a3 - v14 <= 0 )
            break;
          if ( v16 > 0x4000000 )
            v16 = 0x4000000;
          v17 = (UCHAR *)MapViewOfFile(hFileMappingObject, 4u, HIDWORD(v14), v14, v16);
          v6 = v17;
          if ( !v17 )
          {
            v11 = -1073741790;
            goto LABEL_35;
          }
          v11 = BCryptHashData(phHash, v17, v16, 0);
          if ( v11 < 0 )
            goto LABEL_34;
          UnmapViewOfFile(v6);
          v14 += v16;
        }
      }
      v11 = BCryptFinishHash(phHash, pbOutput, *((_DWORD *)v9 + 3), 0);
      if ( v11 >= 0 )
      {
        v11 = 0;
        *v23 = *((_DWORD *)v9 + 3);
      }
LABEL_33:
      if ( v6 )
LABEL_34:
        UnmapViewOfFile(v6);
    }
    goto LABEL_35;
  }
  v11 = -1073741789;
LABEL_35:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v10 )
  {
    if ( v10 != v24 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v10);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004b04c  mov     [rsp+arg_18], rbx
0x18004b051  push    rbp
0x18004b052  push    rsi
0x18004b053  push    rdi
0x18004b054  push    r12
0x18004b056  push    r13
0x18004b058  push    r14
0x18004b05a  push    r15
0x18004b05c  sub     rsp, 170h
0x18004b063  mov     rax, cs:__security_cookie
0x18004b06a  xor     rax, rsp
0x18004b06d  mov     [rsp+1A8h+var_48], rax
0x18004b075  mov     rbx, [rsp+1A8h+arg_28]
0x18004b07d  mov     rbp, rcx
0x18004b080  mov     rcx, [rsp+1A8h+arg_20]
0x18004b088  mov     rdi, r8
0x18004b08b  mov     [rsp+1A8h+pbOutput], rcx
0x18004b090  mov     rax, rdx
0x18004b093  mov     [rsp+1A8h+hFileMappingObject], rdx
0x18004b098  mov     [rsp+1A8h+var_150], rbx
0x18004b09d  mov     [rsp+1A8h+phHash], 0
0x18004b0a6  test    rbp, rbp
0x18004b0a9  jnz     short loc_18004B0B4
0x18004b0ab  test    rax, rax
0x18004b0ae  jz      loc_18004B308
0x18004b0b4  test    rdi, rdi
0x18004b0b7  jz      loc_18004B308
0x18004b0bd  test    rcx, rcx
0x18004b0c0  jz      loc_18004B308
0x18004b0c6  test    rbx, rbx
0x18004b0c9  jz      loc_18004B308
0x18004b0cf  cmp     r9d, 8003h
0x18004b0d6  jnz     short loc_18004B0E8
0x18004b0d8  mov     rax, cs:g_AlgMD5
0x18004b0df  lea     r15, g_AlgMD5
0x18004b0e6  jmp     short loc_18004B103
0x18004b0e8  cmp     r9d, 800Ch
0x18004b0ef  jnz     loc_18004B308
0x18004b0f5  mov     rax, cs:g_AlgSHA256
0x18004b0fc  lea     r15, g_AlgSHA256
0x18004b103  xor     r12d, r12d
0x18004b106  test    rax, rax
0x18004b109  jnz     short loc_18004B11D
0x18004b10b  mov     rcx, r15
0x18004b10e  call    SaferpAcquireBCryptAlgorithmProvider
0x18004b113  mov     esi, eax
0x18004b115  test    eax, eax
0x18004b117  js      loc_18004B2BF
0x18004b11d  mov     eax, [r15+0Ch]
0x18004b121  cmp     [rbx], eax
0x18004b123  jnb     short loc_18004B12F
0x18004b125  mov     esi, 0C0000023h
0x18004b12a  jmp     loc_18004B2BF
0x18004b12f  cmp     dword ptr [r15+8], 100h
0x18004b137  jbe     short loc_18004B16F
0x18004b139  mov     ebx, [r15+8]
0x18004b13d  call    cs:__imp_GetProcessHeap
0x18004b144  nop     dword ptr [rax+rax+00h]
0x18004b149  mov     r8d, ebx; dwBytes
0x18004b14c  xor     edx, edx; dwFlags
0x18004b14e  mov     rcx, rax; hHeap
0x18004b151  call    cs:__imp_HeapAlloc
0x18004b158  nop     dword ptr [rax+rax+00h]
0x18004b15d  mov     r12, rax
0x18004b160  test    rax, rax
0x18004b163  jnz     short loc_18004B174
0x18004b165  mov     esi, 0C0000017h
0x18004b16a  jmp     loc_18004B2BF
0x18004b16f  lea     r12, [rsp+1A8h+var_148]
0x18004b174  mov     r9d, [r15+8]; cbHashObject
0x18004b178  lea     rdx, [rsp+1A8h+phHash]; phHash
0x18004b17d  mov     rcx, [r15]; hAlgorithm
0x18004b180  mov     r8, r12; pbHashObject
0x18004b183  mov     [rsp+1A8h+dwFlags], 0; dwFlags
0x18004b18b  mov     [rsp+1A8h+cbSecret], 0; cbSecret
0x18004b193  mov     [rsp+1A8h+pbSecret], 0; pbSecret
0x18004b19c  call    cs:__imp_BCryptCreateHash
0x18004b1a3  nop     dword ptr [rax+rax+00h]
0x18004b1a8  mov     esi, eax
0x18004b1aa  test    eax, eax
0x18004b1ac  js      loc_18004B2BF
0x18004b1b2  xor     ebx, ebx
0x18004b1b4  mov     r13d, 4000000h
0x18004b1ba  test    rbp, rbp
0x18004b1bd  jz      short loc_18004B201
0x18004b1bf  mov     r14, rdi
0x18004b1c2  sub     r14, rbx
0x18004b1c5  test    r14, r14
0x18004b1c8  jle     loc_18004B27B
0x18004b1ce  mov     rcx, [rsp+1A8h+phHash]; hHash
0x18004b1d3  cmp     r14, r13
0x18004b1d6  mov     rdx, rbp; pbInput
0x18004b1d9  cmovg   r14, r13
0x18004b1dd  xor     r9d, r9d; dwFlags
0x18004b1e0  mov     r8d, r14d; cbInput
0x18004b1e3  call    cs:__imp_BCryptHashData
0x18004b1ea  nop     dword ptr [rax+rax+00h]
0x18004b1ef  mov     esi, eax
0x18004b1f1  test    eax, eax
0x18004b1f3  js      loc_18004B2AB
0x18004b1f9  add     rbp, r14
0x18004b1fc  add     rbx, r14
0x18004b1ff  jmp     short loc_18004B1BF
0x18004b201  mov     r14, rdi
0x18004b204  xor     ebp, ebp
0x18004b206  sub     r14, rbx
0x18004b209  test    r14, r14
0x18004b20c  jle     short loc_18004B27B
0x18004b20e  mov     rcx, [rsp+1A8h+hFileMappingObject]; hFileMappingObject
0x18004b213  lea     edx, [rbp+4]; dwDesiredAccess
0x18004b216  cmp     r14, r13
0x18004b219  mov     r8, rbx
0x18004b21c  mov     r9d, ebx; dwFileOffsetLow
0x18004b21f  cmovg   r14, r13
0x18004b223  shr     r8, 20h; dwFileOffsetHigh
0x18004b227  mov     [rsp+1A8h+pbSecret], r14; dwNumberOfBytesToMap
0x18004b22c  call    cs:__imp_MapViewOfFile
0x18004b233  nop     dword ptr [rax+rax+00h]
0x18004b238  mov     rbp, rax
0x18004b23b  test    rax, rax
0x18004b23e  jz      short loc_18004B274
0x18004b240  mov     rcx, [rsp+1A8h+phHash]; hHash
0x18004b245  mov     r8d, r14d; cbInput
0x18004b248  xor     r9d, r9d; dwFlags
0x18004b24b  mov     rdx, rax; pbInput
0x18004b24e  call    cs:__imp_BCryptHashData
0x18004b255  nop     dword ptr [rax+rax+00h]
0x18004b25a  mov     esi, eax
0x18004b25c  test    eax, eax
0x18004b25e  js      short loc_18004B2B0
0x18004b260  mov     rcx, rbp; lpBaseAddress
0x18004b263  call    cs:__imp_UnmapViewOfFile
0x18004b26a  nop     dword ptr [rax+rax+00h]
0x18004b26f  add     rbx, r14
0x18004b272  jmp     short loc_18004B201
0x18004b274  mov     esi, 0C0000022h
0x18004b279  jmp     short loc_18004B2BF
0x18004b27b  mov     r8d, [r15+0Ch]; cbOutput
0x18004b27f  xor     r9d, r9d; dwFlags
0x18004b282  mov     rdx, [rsp+1A8h+pbOutput]; pbOutput
0x18004b287  mov     rcx, [rsp+1A8h+phHash]; hHash
0x18004b28c  call    cs:__imp_BCryptFinishHash
0x18004b293  nop     dword ptr [rax+rax+00h]
0x18004b298  mov     esi, eax
0x18004b29a  test    eax, eax
0x18004b29c  js      short loc_18004B2AB
0x18004b29e  mov     rcx, [rsp+1A8h+var_150]
0x18004b2a3  xor     esi, esi
0x18004b2a5  mov     eax, [r15+0Ch]
0x18004b2a9  mov     [rcx], eax
0x18004b2ab  test    rbp, rbp
0x18004b2ae  jz      short loc_18004B2BF
0x18004b2b0  mov     rcx, rbp; lpBaseAddress
0x18004b2b3  call    cs:__imp_UnmapViewOfFile
0x18004b2ba  nop     dword ptr [rax+rax+00h]
0x18004b2bf  mov     rcx, [rsp+1A8h+phHash]; hHash
0x18004b2c4  test    rcx, rcx
0x18004b2c7  jz      short loc_18004B2D5
0x18004b2c9  call    cs:__imp_BCryptDestroyHash
0x18004b2d0  nop     dword ptr [rax+rax+00h]
0x18004b2d5  test    r12, r12
0x18004b2d8  jz      short loc_18004B304
0x18004b2da  lea     rax, [rsp+1A8h+var_148]
0x18004b2df  cmp     r12, rax
0x18004b2e2  jz      short loc_18004B304
0x18004b2e4  call    cs:__imp_GetProcessHeap
0x18004b2eb  nop     dword ptr [rax+rax+00h]
0x18004b2f0  mov     r8, r12; lpMem
0x18004b2f3  xor     edx, edx; dwFlags
0x18004b2f5  mov     rcx, rax; hHeap
0x18004b2f8  call    cs:__imp_HeapFree
0x18004b2ff  nop     dword ptr [rax+rax+00h]
0x18004b304  mov     eax, esi
0x18004b306  jmp     short loc_18004B30D
0x18004b308  mov     eax, 0C000000Dh
0x18004b30d  mov     rcx, [rsp+1A8h+var_48]
0x18004b315  xor     rcx, rsp; StackCookie
0x18004b318  call    __security_check_cookie
0x18004b31d  mov     rbx, [rsp+1A8h+arg_18]
0x18004b325  add     rsp, 170h
0x18004b32c  pop     r15
0x18004b32e  pop     r14
0x18004b330  pop     r13
0x18004b332  pop     r12
0x18004b334  pop     rdi
0x18004b335  pop     rsi
0x18004b336  pop     rbp
0x18004b337  retn
```

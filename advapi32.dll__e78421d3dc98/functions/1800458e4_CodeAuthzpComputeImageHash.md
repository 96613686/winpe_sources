# CodeAuthzpComputeImageHash

- ea: `0x1800458e4`
- end: `0x180045b88`
- name: `CodeAuthzpComputeImageHash`
- size: `676`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001333c`

## callees

- `0x1800458e4`
- `0x180047910`
- `0x180065090`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800459e3`
- `KERNEL32!HeapAlloc` at `0x1800459e3`
- `KERNEL32!GetProcessHeap` at `0x1800459d5`
- `KERNEL32!GetProcessHeap` at `0x180045b40`
- `KERNEL32!GetProcessHeap` at `0x1800459d5`
- `KERNEL32!GetProcessHeap` at `0x180045b40`
- `KERNEL32!MapViewOfFile` at `0x180045aac`
- `KERNEL32!MapViewOfFile` at `0x180045aac`
- `KERNEL32!UnmapViewOfFile` at `0x180045ad7`
- `KERNEL32!UnmapViewOfFile` at `0x180045b1b`
- `KERNEL32!UnmapViewOfFile` at `0x180045ad7`
- `KERNEL32!UnmapViewOfFile` at `0x180045b1b`
- `KERNEL32!HeapFree` at `0x180045b4e`
- `KERNEL32!HeapFree` at `0x180045b4e`
- `bcrypt!BCryptDestroyHash` at `0x180045b2b`
- `bcrypt!BCryptDestroyHash` at `0x180045b2b`
- `bcrypt!BCryptHashData` at `0x180045a69`
- `bcrypt!BCryptHashData` at `0x180045ac8`
- `bcrypt!BCryptHashData` at `0x180045a69`
- `bcrypt!BCryptHashData` at `0x180045ac8`
- `bcrypt!BCryptCreateHash` at `0x180045a28`
- `bcrypt!BCryptCreateHash` at `0x180045a28`
- `bcrypt!BCryptFinishHash` at `0x180045afa`
- `bcrypt!BCryptFinishHash` at `0x180045afa`

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
0x1800458e4  mov     [rsp+arg_18], rbx
0x1800458e9  push    rbp
0x1800458ea  push    rsi
0x1800458eb  push    rdi
0x1800458ec  push    r12
0x1800458ee  push    r13
0x1800458f0  push    r14
0x1800458f2  push    r15
0x1800458f4  sub     rsp, 170h
0x1800458fb  mov     rax, cs:__security_cookie
0x180045902  xor     rax, rsp
0x180045905  mov     [rsp+1A8h+var_48], rax
0x18004590d  mov     rbx, [rsp+1A8h+arg_28]
0x180045915  mov     rbp, rcx
0x180045918  mov     rcx, [rsp+1A8h+arg_20]
0x180045920  mov     rdi, r8
0x180045923  mov     [rsp+1A8h+pbOutput], rcx
0x180045928  mov     rax, rdx
0x18004592b  mov     [rsp+1A8h+hFileMappingObject], rdx
0x180045930  mov     [rsp+1A8h+var_150], rbx
0x180045935  mov     [rsp+1A8h+phHash], 0
0x18004593e  test    rbp, rbp
0x180045941  jnz     short loc_18004594C
0x180045943  test    rax, rax
0x180045946  jz      loc_180045B58
0x18004594c  test    rdi, rdi
0x18004594f  jz      loc_180045B58
0x180045955  test    rcx, rcx
0x180045958  jz      loc_180045B58
0x18004595e  test    rbx, rbx
0x180045961  jz      loc_180045B58
0x180045967  cmp     r9d, 8003h
0x18004596e  jnz     short loc_180045980
0x180045970  mov     rax, cs:g_AlgMD5
0x180045977  lea     r15, g_AlgMD5
0x18004597e  jmp     short loc_18004599B
0x180045980  cmp     r9d, 800Ch
0x180045987  jnz     loc_180045B58
0x18004598d  mov     rax, cs:g_AlgSHA256
0x180045994  lea     r15, g_AlgSHA256
0x18004599b  xor     r12d, r12d
0x18004599e  test    rax, rax
0x1800459a1  jnz     short loc_1800459B5
0x1800459a3  mov     rcx, r15
0x1800459a6  call    SaferpAcquireBCryptAlgorithmProvider
0x1800459ab  mov     esi, eax
0x1800459ad  test    eax, eax
0x1800459af  js      loc_180045B21
0x1800459b5  mov     eax, [r15+0Ch]
0x1800459b9  cmp     [rbx], eax
0x1800459bb  jnb     short loc_1800459C7
0x1800459bd  mov     esi, 0C0000023h
0x1800459c2  jmp     loc_180045B21
0x1800459c7  cmp     dword ptr [r15+8], 100h
0x1800459cf  jbe     short loc_1800459FB
0x1800459d1  mov     ebx, [r15+8]
0x1800459d5  call    cs:__imp_GetProcessHeap
0x1800459db  mov     r8d, ebx; dwBytes
0x1800459de  xor     edx, edx; dwFlags
0x1800459e0  mov     rcx, rax; hHeap
0x1800459e3  call    cs:__imp_HeapAlloc
0x1800459e9  mov     r12, rax
0x1800459ec  test    rax, rax
0x1800459ef  jnz     short loc_180045A00
0x1800459f1  mov     esi, 0C0000017h
0x1800459f6  jmp     loc_180045B21
0x1800459fb  lea     r12, [rsp+1A8h+var_148]
0x180045a00  mov     r9d, [r15+8]; cbHashObject
0x180045a04  lea     rdx, [rsp+1A8h+phHash]; phHash
0x180045a09  mov     rcx, [r15]; hAlgorithm
0x180045a0c  mov     r8, r12; pbHashObject
0x180045a0f  mov     [rsp+1A8h+dwFlags], 0; dwFlags
0x180045a17  mov     [rsp+1A8h+cbSecret], 0; cbSecret
0x180045a1f  mov     [rsp+1A8h+pbSecret], 0; pbSecret
0x180045a28  call    cs:__imp_BCryptCreateHash
0x180045a2e  mov     esi, eax
0x180045a30  test    eax, eax
0x180045a32  js      loc_180045B21
0x180045a38  xor     ebx, ebx
0x180045a3a  mov     r13d, 4000000h
0x180045a40  test    rbp, rbp
0x180045a43  jz      short loc_180045A81
0x180045a45  mov     r14, rdi
0x180045a48  sub     r14, rbx
0x180045a4b  test    r14, r14
0x180045a4e  jle     loc_180045AE9
0x180045a54  mov     rcx, [rsp+1A8h+phHash]; hHash
0x180045a59  cmp     r14, r13
0x180045a5c  mov     rdx, rbp; pbInput
0x180045a5f  cmovg   r14, r13
0x180045a63  xor     r9d, r9d; dwFlags
0x180045a66  mov     r8d, r14d; cbInput
0x180045a69  call    cs:__imp_BCryptHashData
0x180045a6f  mov     esi, eax
0x180045a71  test    eax, eax
0x180045a73  js      loc_180045B13
0x180045a79  add     rbp, r14
0x180045a7c  add     rbx, r14
0x180045a7f  jmp     short loc_180045A45
0x180045a81  mov     r14, rdi
0x180045a84  xor     ebp, ebp
0x180045a86  sub     r14, rbx
0x180045a89  test    r14, r14
0x180045a8c  jle     short loc_180045AE9
0x180045a8e  mov     rcx, [rsp+1A8h+hFileMappingObject]; hFileMappingObject
0x180045a93  lea     edx, [rbp+4]; dwDesiredAccess
0x180045a96  cmp     r14, r13
0x180045a99  mov     r8, rbx
0x180045a9c  mov     r9d, ebx; dwFileOffsetLow
0x180045a9f  cmovg   r14, r13
0x180045aa3  shr     r8, 20h; dwFileOffsetHigh
0x180045aa7  mov     [rsp+1A8h+pbSecret], r14; dwNumberOfBytesToMap
0x180045aac  call    cs:__imp_MapViewOfFile
0x180045ab2  mov     rbp, rax
0x180045ab5  test    rax, rax
0x180045ab8  jz      short loc_180045AE2
0x180045aba  mov     rcx, [rsp+1A8h+phHash]; hHash
0x180045abf  mov     r8d, r14d; cbInput
0x180045ac2  xor     r9d, r9d; dwFlags
0x180045ac5  mov     rdx, rax; pbInput
0x180045ac8  call    cs:__imp_BCryptHashData
0x180045ace  mov     esi, eax
0x180045ad0  test    eax, eax
0x180045ad2  js      short loc_180045B18
0x180045ad4  mov     rcx, rbp; lpBaseAddress
0x180045ad7  call    cs:__imp_UnmapViewOfFile
0x180045add  add     rbx, r14
0x180045ae0  jmp     short loc_180045A81
0x180045ae2  mov     esi, 0C0000022h
0x180045ae7  jmp     short loc_180045B21
0x180045ae9  mov     r8d, [r15+0Ch]; cbOutput
0x180045aed  xor     r9d, r9d; dwFlags
0x180045af0  mov     rdx, [rsp+1A8h+pbOutput]; pbOutput
0x180045af5  mov     rcx, [rsp+1A8h+phHash]; hHash
0x180045afa  call    cs:__imp_BCryptFinishHash
0x180045b00  mov     esi, eax
0x180045b02  test    eax, eax
0x180045b04  js      short loc_180045B13
0x180045b06  mov     rcx, [rsp+1A8h+var_150]
0x180045b0b  xor     esi, esi
0x180045b0d  mov     eax, [r15+0Ch]
0x180045b11  mov     [rcx], eax
0x180045b13  test    rbp, rbp
0x180045b16  jz      short loc_180045B21
0x180045b18  mov     rcx, rbp; lpBaseAddress
0x180045b1b  call    cs:__imp_UnmapViewOfFile
0x180045b21  mov     rcx, [rsp+1A8h+phHash]; hHash
0x180045b26  test    rcx, rcx
0x180045b29  jz      short loc_180045B31
0x180045b2b  call    cs:__imp_BCryptDestroyHash
0x180045b31  test    r12, r12
0x180045b34  jz      short loc_180045B54
0x180045b36  lea     rax, [rsp+1A8h+var_148]
0x180045b3b  cmp     r12, rax
0x180045b3e  jz      short loc_180045B54
0x180045b40  call    cs:__imp_GetProcessHeap
0x180045b46  mov     r8, r12; lpMem
0x180045b49  xor     edx, edx; dwFlags
0x180045b4b  mov     rcx, rax; hHeap
0x180045b4e  call    cs:__imp_HeapFree
0x180045b54  mov     eax, esi
0x180045b56  jmp     short loc_180045B5D
0x180045b58  mov     eax, 0C000000Dh
0x180045b5d  mov     rcx, [rsp+1A8h+var_48]
0x180045b65  xor     rcx, rsp; StackCookie
0x180045b68  call    __security_check_cookie
0x180045b6d  mov     rbx, [rsp+1A8h+arg_18]
0x180045b75  add     rsp, 170h
0x180045b7c  pop     r15
0x180045b7e  pop     r14
0x180045b80  pop     r13
0x180045b82  pop     r12
0x180045b84  pop     rdi
0x180045b85  pop     rsi
0x180045b86  pop     rbp
0x180045b87  retn
```

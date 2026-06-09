# ScpSrvVerifyClaimMac

- ea: `0x14007e60c`
- end: `0x14007e86c`
- name: `ScpSrvVerifyClaimMac`
- size: `608`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005d840`

## callees

- `0x14001bd40`
- `0x14001cb6c`
- `0x14007de40`
- `0x14007e60c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x14007e6d0`
- `bcrypt!BCryptCreateHash` at `0x14007e6d0`
- `bcrypt!BCryptHashData` at `0x14007e6f4`
- `bcrypt!BCryptHashData` at `0x14007e718`
- `bcrypt!BCryptHashData` at `0x14007e73c`
- `bcrypt!BCryptHashData` at `0x14007e763`
- `bcrypt!BCryptHashData` at `0x14007e789`
- `bcrypt!BCryptHashData` at `0x14007e7ad`
- `bcrypt!BCryptHashData` at `0x14007e6f4`
- `bcrypt!BCryptHashData` at `0x14007e718`
- `bcrypt!BCryptHashData` at `0x14007e73c`
- `bcrypt!BCryptHashData` at `0x14007e763`
- `bcrypt!BCryptHashData` at `0x14007e789`
- `bcrypt!BCryptHashData` at `0x14007e7ad`
- `bcrypt!BCryptFinishHash` at `0x14007e7cd`
- `bcrypt!BCryptFinishHash` at `0x14007e7cd`
- `bcrypt!BCryptDestroyHash` at `0x14007e838`
- `bcrypt!BCryptDestroyHash` at `0x14007e838`

## pseudocode

```c
__int64 __fastcall ScpSrvVerifyClaimMac(
        __int64 a1,
        UCHAR *a2,
        __int64 a3,
        UCHAR *a4,
        __int64 a5,
        PUCHAR a6,
        __int64 a7,
        PUCHAR a8,
        UCHAR *a9,
        void *Buf1)
{
  ULONG v11; // r12d
  NTSTATUS v12; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-49h] BYREF
  PUCHAR pbInput[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v16; // [rsp+58h] [rbp-31h]
  UCHAR pbOutput[16]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v18; // [rsp+70h] [rbp-19h]

  v11 = a3;
  v16 = a1;
  pbInput[0] = a2;
  if ( !a2 || !a3 || !a4 || *a4 != 4 || !a6 || *a6 != 4 || !a8 || !a9 || !Buf1 )
    return 3221225485LL;
  phHash = 0;
  *(_OWORD *)pbOutput = 0;
  v18 = 0;
  v12 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v12 >= 0 )
  {
    v12 = BCryptHashData(phHash, pbInput[0], v11, 0);
    if ( v12 >= 0 )
    {
      v12 = BCryptHashData(phHash, a4, 0x41u, 0);
      if ( v12 >= 0 )
      {
        v12 = BCryptHashData(phHash, a6, 0x41u, 0);
        if ( v12 >= 0 )
        {
          v12 = BCryptHashData(phHash, a8, 0x20u, 0);
          if ( v12 >= 0 )
          {
            v12 = BCryptHashData(phHash, a9, 0x40u, 0);
            if ( v12 >= 0 )
            {
              v12 = BCryptHashData(phHash, a8 + 32, 0x40u, 0);
              if ( v12 >= 0 )
              {
                v12 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
                if ( v12 >= 0 )
                {
                  pbInput[0] = pbOutput;
                  pbInput[1] = (PUCHAR)32;
                  v12 = MacWithLabel(v16, "connect", pbInput, 1);
                  if ( v12 >= 0 )
                  {
                    if ( memcmp_0(Buf1, pbOutput, 0x20u) )
                      v12 = -1073741823;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14007e60c  push    rbp
0x14007e60e  push    rbx
0x14007e60f  push    rsi
0x14007e610  push    rdi
0x14007e611  push    r12
0x14007e613  push    r13
0x14007e615  push    r14
0x14007e617  lea     rbp, [rsp-7]
0x14007e61c  sub     rsp, 90h
0x14007e623  mov     rax, cs:__security_cookie
0x14007e62a  xor     rax, rsp
0x14007e62d  mov     [rbp+37h+var_40], rax
0x14007e631  mov     rsi, [rbp+37h+arg_28]
0x14007e635  mov     rdi, r9
0x14007e638  mov     r14, [rbp+37h+arg_38]
0x14007e63c  mov     r12, r8
0x14007e63f  mov     r13, [rbp+37h+arg_40]
0x14007e646  mov     [rbp+37h+var_68], rcx
0x14007e64a  xor     ecx, ecx
0x14007e64c  mov     [rbp+37h+pbInput], rdx
0x14007e650  test    rdx, rdx
0x14007e653  jz      loc_14007E848
0x14007e659  test    r8, r8
0x14007e65c  jz      loc_14007E848
0x14007e662  test    r9, r9
0x14007e665  jz      loc_14007E848
0x14007e66b  cmp     byte ptr [r9], 4
0x14007e66f  jnz     loc_14007E848
0x14007e675  test    rsi, rsi
0x14007e678  jz      loc_14007E848
0x14007e67e  cmp     byte ptr [rsi], 4
0x14007e681  jnz     loc_14007E848
0x14007e687  test    r14, r14
0x14007e68a  jz      loc_14007E848
0x14007e690  test    r13, r13
0x14007e693  jz      loc_14007E848
0x14007e699  cmp     [rbp+37h+Buf1], rcx
0x14007e6a0  jz      loc_14007E848
0x14007e6a6  mov     [rsp+0C0h+dwFlags], ecx; dwFlags
0x14007e6aa  lea     rdx, [rbp+37h+phHash]; phHash
0x14007e6ae  mov     [rsp+0C0h+cbSecret], ecx; cbSecret
0x14007e6b2  xorps   xmm0, xmm0
0x14007e6b5  xor     r9d, r9d; cbHashObject
0x14007e6b8  mov     [rbp+37h+phHash], rcx
0x14007e6bc  mov     [rsp+0C0h+pbSecret], rcx; pbSecret
0x14007e6c1  xor     r8d, r8d; pbHashObject
0x14007e6c4  movups  xmmword ptr [rbp+37h+pbOutput], xmm0
0x14007e6c8  lea     ecx, [r9+41h]; hAlgorithm
0x14007e6cc  movups  [rbp+37h+var_50], xmm0
0x14007e6d0  call    cs:__imp_BCryptCreateHash
0x14007e6d7  nop     dword ptr [rax+rax+00h]
0x14007e6dc  mov     ebx, eax
0x14007e6de  test    eax, eax
0x14007e6e0  js      loc_14007E82F
0x14007e6e6  mov     rdx, [rbp+37h+pbInput]; pbInput
0x14007e6ea  mov     r8d, r12d; cbInput
0x14007e6ed  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e6f1  xor     r9d, r9d; dwFlags
0x14007e6f4  call    cs:__imp_BCryptHashData
0x14007e6fb  nop     dword ptr [rax+rax+00h]
0x14007e700  mov     ebx, eax
0x14007e702  test    eax, eax
0x14007e704  js      loc_14007E82F
0x14007e70a  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e70e  xor     r9d, r9d; dwFlags
0x14007e711  mov     rdx, rdi; pbInput
0x14007e714  lea     r8d, [r9+41h]; cbInput
0x14007e718  call    cs:__imp_BCryptHashData
0x14007e71f  nop     dword ptr [rax+rax+00h]
0x14007e724  mov     ebx, eax
0x14007e726  test    eax, eax
0x14007e728  js      loc_14007E82F
0x14007e72e  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e732  xor     r9d, r9d; dwFlags
0x14007e735  mov     rdx, rsi; pbInput
0x14007e738  lea     r8d, [r9+41h]; cbInput
0x14007e73c  call    cs:__imp_BCryptHashData
0x14007e743  nop     dword ptr [rax+rax+00h]
0x14007e748  mov     ebx, eax
0x14007e74a  test    eax, eax
0x14007e74c  js      loc_14007E82F
0x14007e752  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e756  xor     r9d, r9d; dwFlags
0x14007e759  mov     rdx, r14; pbInput
0x14007e75c  lea     edi, [r9+20h]
0x14007e760  mov     r8d, edi; cbInput
0x14007e763  call    cs:__imp_BCryptHashData
0x14007e76a  nop     dword ptr [rax+rax+00h]
0x14007e76f  mov     ebx, eax
0x14007e771  test    eax, eax
0x14007e773  js      loc_14007E82F
0x14007e779  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e77d  lea     esi, [rdi+20h]
0x14007e780  mov     r8d, esi; cbInput
0x14007e783  xor     r9d, r9d; dwFlags
0x14007e786  mov     rdx, r13; pbInput
0x14007e789  call    cs:__imp_BCryptHashData
0x14007e790  nop     dword ptr [rax+rax+00h]
0x14007e795  mov     ebx, eax
0x14007e797  test    eax, eax
0x14007e799  js      loc_14007E82F
0x14007e79f  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e7a3  lea     rdx, [r14+20h]; pbInput
0x14007e7a7  xor     r9d, r9d; dwFlags
0x14007e7aa  mov     r8d, esi; cbInput
0x14007e7ad  call    cs:__imp_BCryptHashData
0x14007e7b4  nop     dword ptr [rax+rax+00h]
0x14007e7b9  mov     ebx, eax
0x14007e7bb  test    eax, eax
0x14007e7bd  js      short loc_14007E82F
0x14007e7bf  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e7c3  lea     rdx, [rbp+37h+pbOutput]; pbOutput
0x14007e7c7  xor     r9d, r9d; dwFlags
0x14007e7ca  mov     r8d, edi; cbOutput
0x14007e7cd  call    cs:__imp_BCryptFinishHash
0x14007e7d4  nop     dword ptr [rax+rax+00h]
0x14007e7d9  mov     ebx, eax
0x14007e7db  test    eax, eax
0x14007e7dd  js      short loc_14007E82F
0x14007e7df  mov     rcx, [rbp+37h+var_68]
0x14007e7e3  lea     rax, [rbp+37h+pbOutput]
0x14007e7e7  mov     [rbp+37h+pbInput], rax
0x14007e7eb  lea     r9d, [rdi-1Fh]
0x14007e7ef  lea     rax, [rbp+37h+pbOutput]
0x14007e7f3  mov     [rbp+37h+var_70], rdi
0x14007e7f7  lea     r8, [rbp+37h+pbInput]
0x14007e7fb  mov     [rsp+0C0h+pbSecret], rax
0x14007e800  lea     rdx, aConnect; "connect"
0x14007e807  call    MacWithLabel
0x14007e80c  mov     ebx, eax
0x14007e80e  test    eax, eax
0x14007e810  js      short loc_14007E82F
0x14007e812  mov     rcx, [rbp+37h+Buf1]; Buf1
0x14007e819  lea     rdx, [rbp+37h+pbOutput]; Buf2
0x14007e81d  mov     r8d, edi; Size
0x14007e820  call    memcmp_0
0x14007e825  test    eax, eax
0x14007e827  mov     ecx, 0C0000001h
0x14007e82c  cmovnz  ebx, ecx
0x14007e82f  mov     rcx, [rbp+37h+phHash]; hHash
0x14007e833  test    rcx, rcx
0x14007e836  jz      short loc_14007E844
0x14007e838  call    cs:__imp_BCryptDestroyHash
0x14007e83f  nop     dword ptr [rax+rax+00h]
0x14007e844  mov     eax, ebx
0x14007e846  jmp     short loc_14007E84D
0x14007e848  mov     eax, 0C000000Dh
0x14007e84d  mov     rcx, [rbp+37h+var_40]
0x14007e851  xor     rcx, rsp; StackCookie
0x14007e854  call    __security_check_cookie
0x14007e859  add     rsp, 90h
0x14007e860  pop     r14
0x14007e862  pop     r13
0x14007e864  pop     r12
0x14007e866  pop     rdi
0x14007e867  pop     rsi
0x14007e868  pop     rbx
0x14007e869  pop     rbp
0x14007e86a  retn
```

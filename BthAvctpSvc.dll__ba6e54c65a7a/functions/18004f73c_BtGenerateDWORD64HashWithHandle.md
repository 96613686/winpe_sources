# BtGenerateDWORD64HashWithHandle

- ea: `0x18004f73c`
- end: `0x18004f8a9`
- name: `BtGenerateDWORD64HashWithHandle`
- size: `365`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004f6c8`

## callees

- `0x180002954`
- `0x18004f73c`
- `0x18004f8b0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18004f847`
- `bcrypt!BCryptFinishHash` at `0x18004f847`
- `bcrypt!BCryptGetProperty` at `0x18004f791`
- `bcrypt!BCryptGetProperty` at `0x18004f816`
- `bcrypt!BCryptGetProperty` at `0x18004f791`
- `bcrypt!BCryptGetProperty` at `0x18004f816`
- `bcrypt!BCryptDestroyHash` at `0x18004f86e`
- `bcrypt!BCryptDestroyHash` at `0x18004f86e`
- `bcrypt!BCryptCreateHash` at `0x18004f7ce`
- `bcrypt!BCryptCreateHash` at `0x18004f7ce`
- `bcrypt!BCryptHashData` at `0x18004f7eb`
- `bcrypt!BCryptHashData` at `0x18004f7eb`

## pseudocode

```c
__int64 __fastcall BtGenerateDWORD64HashWithHandle(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject, _QWORD *a4)
{
  UCHAR *v5; // rdi
  UCHAR *Pool; // rsi
  __int64 v10; // rcx
  NTSTATUS Property; // ebx
  __int64 v12; // rcx
  UCHAR *v13; // rax
  UCHAR v15[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  __int64 v18; // [rsp+50h] [rbp-18h]
  ULONG pbOutput; // [rsp+C8h] [rbp+60h] BYREF

  v5 = 0;
  *a4 = 0;
  phHash = 0;
  Pool = 0;
  pbOutput = 0;
  *(_DWORD *)v15 = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    Pool = (UCHAR *)BthHashingLibAllocatePoolEx(v10, pbOutput);
    if ( !Pool )
    {
LABEL_7:
      Property = -1073741670;
      goto LABEL_10;
    }
    Property = BCryptCreateHash(hObject, &phHash, Pool, pbOutput, 0, 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(hObject, L"HashDigestLength", v15, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          v13 = (UCHAR *)BthHashingLibAllocatePoolEx(v12, *(unsigned int *)v15);
          v5 = v13;
          if ( !v13 )
            goto LABEL_7;
          Property = BCryptFinishHash(phHash, v13, *(ULONG *)v15, 0);
          if ( Property >= 0 )
          {
            LODWORD(v18) = *((_DWORD *)v5 + 1);
            HIDWORD(v18) = *(_DWORD *)v5;
            *a4 = v18;
          }
        }
      }
    }
  }
LABEL_10:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( Pool )
    free(Pool);
  if ( v5 )
    free(v5);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18004f73c  push    rbp
0x18004f73e  push    rbx
0x18004f73f  push    rsi
0x18004f740  push    rdi
0x18004f741  push    r12
0x18004f743  push    r13
0x18004f745  push    r14
0x18004f747  push    r15
0x18004f749  mov     rbp, rsp
0x18004f74c  sub     rsp, 68h
0x18004f750  xor     eax, eax
0x18004f752  mov     r14, r8
0x18004f755  mov     edi, eax
0x18004f757  mov     [r9], rax
0x18004f75a  mov     [rsp+68h+dwFlags], eax; dwFlags
0x18004f75e  lea     r8, [rbp+pbOutput]; pbOutput
0x18004f762  mov     [rbp+phHash], rax
0x18004f766  mov     esi, eax
0x18004f768  mov     [rbp+pbOutput], eax
0x18004f76b  mov     r15, r9
0x18004f76e  mov     dword ptr [rbp+var_28], eax
0x18004f771  lea     r9d, [rdi+4]; cbOutput
0x18004f775  mov     [rbp+var_24], eax
0x18004f778  mov     r12d, edx
0x18004f77b  mov     r13, rcx
0x18004f77e  lea     rax, [rbp+var_24]
0x18004f782  lea     rdx, pszProperty; "ObjectLength"
0x18004f789  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18004f78e  mov     rcx, r14; hObject
0x18004f791  call    cs:__imp_BCryptGetProperty
0x18004f797  mov     ebx, eax
0x18004f799  test    eax, eax
0x18004f79b  js      loc_18004F865
0x18004f7a1  mov     edx, [rbp+pbOutput]
0x18004f7a4  call    BthHashingLibAllocatePoolEx
0x18004f7a9  mov     rsi, rax
0x18004f7ac  xor     eax, eax
0x18004f7ae  test    rsi, rsi
0x18004f7b1  jz      short loc_18004F832
0x18004f7b3  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18004f7b7  lea     rdx, [rbp+phHash]; phHash
0x18004f7bb  mov     [rsp+68h+var_38], eax; dwFlags
0x18004f7bf  mov     r8, rsi; pbHashObject
0x18004f7c2  mov     [rsp+68h+dwFlags], eax; cbSecret
0x18004f7c6  mov     rcx, r14; hAlgorithm
0x18004f7c9  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18004f7ce  call    cs:__imp_BCryptCreateHash
0x18004f7d4  mov     ebx, eax
0x18004f7d6  test    eax, eax
0x18004f7d8  js      loc_18004F865
0x18004f7de  mov     rcx, [rbp+phHash]; hHash
0x18004f7e2  xor     r9d, r9d; dwFlags
0x18004f7e5  mov     r8d, r12d; cbInput
0x18004f7e8  mov     rdx, r13; pbInput
0x18004f7eb  call    cs:__imp_BCryptHashData
0x18004f7f1  mov     ebx, eax
0x18004f7f3  test    eax, eax
0x18004f7f5  js      short loc_18004F865
0x18004f7f7  lea     rax, [rbp+var_24]
0x18004f7fb  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18004f7ff  lea     r9d, [rdi+4]; cbOutput
0x18004f803  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18004f808  lea     r8, [rbp+var_28]; pbOutput
0x18004f80c  mov     rcx, r14; hObject
0x18004f80f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18004f816  call    cs:__imp_BCryptGetProperty
0x18004f81c  mov     ebx, eax
0x18004f81e  test    eax, eax
0x18004f820  js      short loc_18004F865
0x18004f822  mov     edx, dword ptr [rbp+var_28]
0x18004f825  call    BthHashingLibAllocatePoolEx
0x18004f82a  mov     rdi, rax
0x18004f82d  test    rax, rax
0x18004f830  jnz     short loc_18004F839
0x18004f832  mov     ebx, 0C000009Ah
0x18004f837  jmp     short loc_18004F865
0x18004f839  mov     r8d, dword ptr [rbp+var_28]; cbOutput
0x18004f83d  xor     r9d, r9d; dwFlags
0x18004f840  mov     rcx, [rbp+phHash]; hHash
0x18004f844  mov     rdx, rdi; pbOutput
0x18004f847  call    cs:__imp_BCryptFinishHash
0x18004f84d  mov     ebx, eax
0x18004f84f  test    eax, eax
0x18004f851  js      short loc_18004F865
0x18004f853  mov     eax, [rdi+4]
0x18004f856  mov     dword ptr [rbp+var_18], eax
0x18004f859  mov     eax, [rdi]
0x18004f85b  mov     dword ptr [rbp+var_18+4], eax
0x18004f85e  mov     rax, [rbp+var_18]
0x18004f862  mov     [r15], rax
0x18004f865  mov     rcx, [rbp+phHash]; hHash
0x18004f869  test    rcx, rcx
0x18004f86c  jz      short loc_18004F87C
0x18004f86e  call    cs:__imp_BCryptDestroyHash
0x18004f874  mov     [rbp+phHash], 0
0x18004f87c  test    rsi, rsi
0x18004f87f  jz      short loc_18004F889
0x18004f881  mov     rcx, rsi; Block
0x18004f884  call    free
0x18004f889  test    rdi, rdi
0x18004f88c  jz      short loc_18004F896
0x18004f88e  mov     rcx, rdi; Block
0x18004f891  call    free
0x18004f896  mov     eax, ebx
0x18004f898  add     rsp, 68h
0x18004f89c  pop     r15
0x18004f89e  pop     r14
0x18004f8a0  pop     r13
0x18004f8a2  pop     r12
0x18004f8a4  pop     rdi
0x18004f8a5  pop     rsi
0x18004f8a6  pop     rbx
0x18004f8a7  pop     rbp
0x18004f8a8  retn
```

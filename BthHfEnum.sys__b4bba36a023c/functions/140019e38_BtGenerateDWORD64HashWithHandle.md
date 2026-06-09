# BtGenerateDWORD64HashWithHandle

- ea: `0x140019e38`
- end: `0x140019fdc`
- name: `BtGenerateDWORD64HashWithHandle`
- size: `420`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140019db8`

## callees

- `0x140019e38`
- `0x140019fe4`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x140019fa8`
- `ntoskrnl!ExFreePool` at `0x140019fbc`
- `ntoskrnl!ExFreePool` at `0x140019fa8`
- `ntoskrnl!ExFreePool` at `0x140019fbc`
- `ksecdd!BCryptCreateHash` at `0x140019ed4`
- `ksecdd!BCryptCreateHash` at `0x140019ed4`
- `ksecdd!BCryptHashData` at `0x140019ef7`
- `ksecdd!BCryptHashData` at `0x140019ef7`
- `ksecdd!BCryptFinishHash` at `0x140019f5f`
- `ksecdd!BCryptFinishHash` at `0x140019f5f`
- `ksecdd!BCryptGetProperty` at `0x140019e8d`
- `ksecdd!BCryptGetProperty` at `0x140019f28`
- `ksecdd!BCryptGetProperty` at `0x140019e8d`
- `ksecdd!BCryptGetProperty` at `0x140019f28`
- `ksecdd!BCryptDestroyHash` at `0x140019f8c`
- `ksecdd!BCryptDestroyHash` at `0x140019f8c`

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
    ExFreePool(Pool);
  if ( v5 )
    ExFreePool(v5);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140019e38  push    rbp
0x140019e3a  push    rbx
0x140019e3b  push    rsi
0x140019e3c  push    rdi
0x140019e3d  push    r12
0x140019e3f  push    r13
0x140019e41  push    r14
0x140019e43  push    r15
0x140019e45  mov     rbp, rsp
0x140019e48  sub     rsp, 68h
0x140019e4c  xor     eax, eax
0x140019e4e  mov     r14, r8
0x140019e51  mov     edi, eax
0x140019e53  mov     [r9], rax
0x140019e56  mov     [rsp+68h+dwFlags], eax; dwFlags
0x140019e5a  lea     r8, [rbp+pbOutput]; pbOutput
0x140019e5e  mov     [rbp+phHash], rax
0x140019e62  mov     esi, eax
0x140019e64  mov     [rbp+pbOutput], eax
0x140019e67  mov     r15, r9
0x140019e6a  mov     dword ptr [rbp+var_28], eax
0x140019e6d  lea     r9d, [rdi+4]; cbOutput
0x140019e71  mov     [rbp+var_24], eax
0x140019e74  mov     r12d, edx
0x140019e77  mov     r13, rcx
0x140019e7a  lea     rax, [rbp+var_24]
0x140019e7e  lea     rdx, pszProperty; "ObjectLength"
0x140019e85  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140019e8a  mov     rcx, r14; hObject
0x140019e8d  call    cs:__imp_BCryptGetProperty
0x140019e94  nop     dword ptr [rax+rax+00h]
0x140019e99  mov     ebx, eax
0x140019e9b  test    eax, eax
0x140019e9d  js      loc_140019F83
0x140019ea3  mov     edx, [rbp+pbOutput]
0x140019ea6  call    BthHashingLibAllocatePoolEx
0x140019eab  mov     rsi, rax
0x140019eae  xor     eax, eax
0x140019eb0  test    rsi, rsi
0x140019eb3  jz      loc_140019F4A
0x140019eb9  mov     r9d, [rbp+pbOutput]; cbHashObject
0x140019ebd  lea     rdx, [rbp+phHash]; phHash
0x140019ec1  mov     [rsp+68h+var_38], eax; dwFlags
0x140019ec5  mov     r8, rsi; pbHashObject
0x140019ec8  mov     [rsp+68h+dwFlags], eax; cbSecret
0x140019ecc  mov     rcx, r14; hAlgorithm
0x140019ecf  mov     [rsp+68h+pcbResult], rax; pbSecret
0x140019ed4  call    cs:__imp_BCryptCreateHash
0x140019edb  nop     dword ptr [rax+rax+00h]
0x140019ee0  mov     ebx, eax
0x140019ee2  test    eax, eax
0x140019ee4  js      loc_140019F83
0x140019eea  mov     rcx, [rbp+phHash]; hHash
0x140019eee  xor     r9d, r9d; dwFlags
0x140019ef1  mov     r8d, r12d; cbInput
0x140019ef4  mov     rdx, r13; pbInput
0x140019ef7  call    cs:__imp_BCryptHashData
0x140019efe  nop     dword ptr [rax+rax+00h]
0x140019f03  mov     ebx, eax
0x140019f05  test    eax, eax
0x140019f07  js      short loc_140019F83
0x140019f09  lea     rax, [rbp+var_24]
0x140019f0d  mov     [rsp+68h+dwFlags], edi; dwFlags
0x140019f11  lea     r9d, [rdi+4]; cbOutput
0x140019f15  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140019f1a  lea     r8, [rbp+var_28]; pbOutput
0x140019f1e  mov     rcx, r14; hObject
0x140019f21  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140019f28  call    cs:__imp_BCryptGetProperty
0x140019f2f  nop     dword ptr [rax+rax+00h]
0x140019f34  mov     ebx, eax
0x140019f36  test    eax, eax
0x140019f38  js      short loc_140019F83
0x140019f3a  mov     edx, dword ptr [rbp+var_28]
0x140019f3d  call    BthHashingLibAllocatePoolEx
0x140019f42  mov     rdi, rax
0x140019f45  test    rax, rax
0x140019f48  jnz     short loc_140019F51
0x140019f4a  mov     ebx, 0C000009Ah
0x140019f4f  jmp     short loc_140019F83
0x140019f51  mov     r8d, dword ptr [rbp+var_28]; cbOutput
0x140019f55  xor     r9d, r9d; dwFlags
0x140019f58  mov     rcx, [rbp+phHash]; hHash
0x140019f5c  mov     rdx, rdi; pbOutput
0x140019f5f  call    cs:__imp_BCryptFinishHash
0x140019f66  nop     dword ptr [rax+rax+00h]
0x140019f6b  mov     ebx, eax
0x140019f6d  test    eax, eax
0x140019f6f  js      short loc_140019F83
0x140019f71  mov     eax, [rdi+4]
0x140019f74  mov     dword ptr [rbp+var_18], eax
0x140019f77  mov     eax, [rdi]
0x140019f79  mov     dword ptr [rbp+var_18+4], eax
0x140019f7c  mov     rax, [rbp+var_18]
0x140019f80  mov     [r15], rax
0x140019f83  mov     rcx, [rbp+phHash]; hHash
0x140019f87  test    rcx, rcx
0x140019f8a  jz      short loc_140019FA0
0x140019f8c  call    cs:__imp_BCryptDestroyHash
0x140019f93  nop     dword ptr [rax+rax+00h]
0x140019f98  mov     [rbp+phHash], 0
0x140019fa0  test    rsi, rsi
0x140019fa3  jz      short loc_140019FB4
0x140019fa5  mov     rcx, rsi; P
0x140019fa8  call    cs:__imp_ExFreePool
0x140019faf  nop     dword ptr [rax+rax+00h]
0x140019fb4  test    rdi, rdi
0x140019fb7  jz      short loc_140019FC8
0x140019fb9  mov     rcx, rdi; P
0x140019fbc  call    cs:__imp_ExFreePool
0x140019fc3  nop     dword ptr [rax+rax+00h]
0x140019fc8  mov     eax, ebx
0x140019fca  add     rsp, 68h
0x140019fce  pop     r15
0x140019fd0  pop     r14
0x140019fd2  pop     r13
0x140019fd4  pop     r12
0x140019fd6  pop     rdi
0x140019fd7  pop     rsi
0x140019fd8  pop     rbx
0x140019fd9  pop     rbp
0x140019fda  retn
```

# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x18009e5c0`
- end: `0x18009e77b`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `443`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007b00`
- `0x180007c7c`
- `0x180051d48`
- `0x18009e5c0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18009e6d9`
- `bcrypt!BCryptHashData` at `0x18009e6d9`
- `bcrypt!BCryptFinishHash` at `0x18009e6fa`
- `bcrypt!BCryptFinishHash` at `0x18009e6fa`
- `bcrypt!BCryptDestroyHash` at `0x18009e711`
- `bcrypt!BCryptDestroyHash` at `0x18009e711`
- `bcrypt!BCryptCreateHash` at `0x18009e6ba`
- `bcrypt!BCryptCreateHash` at `0x18009e6ba`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009e753`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009e753`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009e626`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009e626`
- `bcrypt!BCryptGetProperty` at `0x18009e65c`
- `bcrypt!BCryptGetProperty` at `0x18009e65c`

## pseudocode

```c
__int64 __fastcall WinPlatformSha1Hash(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a5,
        ULONG a6)
{
  void *v6; // rdi
  ULONG v11; // r9d
  NTSTATUS Property; // ebx
  __int64 v13; // rax
  _BYTE *v14; // rcx
  ULONG cbOutput; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  ULONG pbOutput; // [rsp+A8h] [rbp+48h] BYREF

  v6 = 0;
  phAlgorithm = 0;
  phHash = 0;
  pbOutput = 0;
  cbOutput = 4;
  if ( cbSecret && pbSecret )
    v11 = 8;
  else
    v11 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", v11);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, cbOutput, &cbOutput, 0);
    if ( Property >= 0 )
    {
      v6 = operator new(pbOutput);
      memset_0(v6, 0, pbOutput);
      memset_0(v6, 0, pbOutput);
      Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v6, pbOutput, pbSecret, cbSecret, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( Property >= 0 )
          Property = BCryptFinishHash(phHash, a5, a6, 0);
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v6 )
  {
    v13 = pbOutput;
    v14 = v6;
    if ( pbOutput )
    {
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    operator delete(v6);
  }
  pbOutput = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18009e5c0  mov     [rsp-28h+arg_0], rbx
0x18009e5c5  mov     [rsp-28h+arg_8], rsi
0x18009e5ca  push    rbp
0x18009e5cb  push    rdi
0x18009e5cc  push    r12
0x18009e5ce  push    r14
0x18009e5d0  push    r15
0x18009e5d2  mov     rbp, rsp
0x18009e5d5  sub     rsp, 60h
0x18009e5d9  xor     edi, edi
0x18009e5db  mov     [rbp+phAlgorithm], 0
0x18009e5e3  mov     [rbp+phHash], 0
0x18009e5eb  mov     r14d, r9d
0x18009e5ee  mov     [rbp+pbOutput], edi
0x18009e5f1  mov     rsi, r8
0x18009e5f4  mov     [rbp+cbOutput], 4
0x18009e5fb  mov     r15d, edx
0x18009e5fe  mov     r12, rcx
0x18009e601  test    r9d, r9d
0x18009e604  jz      short loc_18009E611
0x18009e606  test    r8, r8
0x18009e609  jz      short loc_18009E611
0x18009e60b  lea     r9d, [rdi+8]
0x18009e60f  jmp     short loc_18009E614
0x18009e611  xor     r9d, r9d; dwFlags
0x18009e614  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009e61b  lea     rdx, pszAlgId; "SHA1"
0x18009e622  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18009e626  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009e62d  nop     dword ptr [rax+rax+00h]
0x18009e632  mov     ebx, eax
0x18009e634  test    eax, eax
0x18009e636  js      loc_18009E708
0x18009e63c  mov     r9d, [rbp+cbOutput]; cbOutput
0x18009e640  lea     rax, [rbp+cbOutput]
0x18009e644  mov     rcx, [rbp+phAlgorithm]; hObject
0x18009e648  lea     r8, [rbp+pbOutput]; pbOutput
0x18009e64c  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18009e650  lea     rdx, aObjectlength; "ObjectLength"
0x18009e657  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18009e65c  call    cs:__imp_BCryptGetProperty
0x18009e663  nop     dword ptr [rax+rax+00h]
0x18009e668  mov     ebx, eax
0x18009e66a  test    eax, eax
0x18009e66c  js      loc_18009E708
0x18009e672  mov     ecx, [rbp+pbOutput]; Size
0x18009e675  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009e67a  mov     r8d, [rbp+pbOutput]; Size
0x18009e67e  xor     edx, edx; Val
0x18009e680  mov     rcx, rax; void *
0x18009e683  mov     rdi, rax
0x18009e686  call    memset_0
0x18009e68b  mov     r8d, [rbp+pbOutput]; Size
0x18009e68f  xor     edx, edx; Val
0x18009e691  mov     rcx, rdi; void *
0x18009e694  call    memset_0
0x18009e699  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18009e69d  lea     rdx, [rbp+phHash]; phHash
0x18009e6a1  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009e6a5  mov     r8, rdi; pbHashObject
0x18009e6a8  mov     [rsp+60h+var_30], 0; dwFlags
0x18009e6b0  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x18009e6b5  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x18009e6ba  call    cs:__imp_BCryptCreateHash
0x18009e6c1  nop     dword ptr [rax+rax+00h]
0x18009e6c6  mov     ebx, eax
0x18009e6c8  test    eax, eax
0x18009e6ca  js      short loc_18009E708
0x18009e6cc  mov     rcx, [rbp+phHash]; hHash
0x18009e6d0  xor     r9d, r9d; dwFlags
0x18009e6d3  mov     r8d, r15d; cbInput
0x18009e6d6  mov     rdx, r12; pbInput
0x18009e6d9  call    cs:__imp_BCryptHashData
0x18009e6e0  nop     dword ptr [rax+rax+00h]
0x18009e6e5  mov     ebx, eax
0x18009e6e7  test    eax, eax
0x18009e6e9  js      short loc_18009E708
0x18009e6eb  mov     r8d, [rbp+arg_28]; cbOutput
0x18009e6ef  xor     r9d, r9d; dwFlags
0x18009e6f2  mov     rdx, [rbp+arg_20]; pbOutput
0x18009e6f6  mov     rcx, [rbp+phHash]; hHash
0x18009e6fa  call    cs:__imp_BCryptFinishHash
0x18009e701  nop     dword ptr [rax+rax+00h]
0x18009e706  mov     ebx, eax
0x18009e708  mov     rcx, [rbp+phHash]; hHash
0x18009e70c  test    rcx, rcx
0x18009e70f  jz      short loc_18009E71D
0x18009e711  call    cs:__imp_BCryptDestroyHash
0x18009e718  nop     dword ptr [rax+rax+00h]
0x18009e71d  test    rdi, rdi
0x18009e720  jz      short loc_18009E741
0x18009e722  mov     eax, [rbp+pbOutput]
0x18009e725  mov     rcx, rdi
0x18009e728  test    rax, rax
0x18009e72b  jz      short loc_18009E739
0x18009e72d  mov     byte ptr [rcx], 0
0x18009e730  inc     rcx
0x18009e733  sub     rax, 1
0x18009e737  jnz     short loc_18009E72D
0x18009e739  mov     rcx, rdi; Block
0x18009e73c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009e741  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009e745  mov     [rbp+pbOutput], 0
0x18009e74c  test    rcx, rcx
0x18009e74f  jz      short loc_18009E75F
0x18009e751  xor     edx, edx; dwFlags
0x18009e753  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009e75a  nop     dword ptr [rax+rax+00h]
0x18009e75f  lea     r11, [rsp+60h+var_s0]
0x18009e764  mov     eax, ebx
0x18009e766  mov     rbx, [r11+30h]
0x18009e76a  mov     rsi, [r11+38h]
0x18009e76e  mov     rsp, r11
0x18009e771  pop     r15
0x18009e773  pop     r14
0x18009e775  pop     r12
0x18009e777  pop     rdi
0x18009e778  pop     rbp
0x18009e779  retn
```

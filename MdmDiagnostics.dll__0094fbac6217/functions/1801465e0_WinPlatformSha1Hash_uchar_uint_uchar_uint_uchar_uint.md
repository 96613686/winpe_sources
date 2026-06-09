# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x1801465e0`
- end: `0x180146770`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `400`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180018fe4`
- `0x180019024`
- `0x180019fc4`
- `0x1801465e0`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180146676`
- `bcrypt!BCryptGetProperty` at `0x180146676`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180146646`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180146646`
- `bcrypt!BCryptFinishHash` at `0x180146702`
- `bcrypt!BCryptFinishHash` at `0x180146702`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014674f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014674f`
- `bcrypt!BCryptDestroyHash` at `0x180146713`
- `bcrypt!BCryptDestroyHash` at `0x180146713`
- `bcrypt!BCryptHashData` at `0x1801466e7`
- `bcrypt!BCryptHashData` at `0x1801466e7`
- `bcrypt!BCryptCreateHash` at `0x1801466ce`
- `bcrypt!BCryptCreateHash` at `0x1801466ce`

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
0x1801465e0  mov     [rsp-28h+arg_0], rbx
0x1801465e5  mov     [rsp-28h+arg_8], rsi
0x1801465ea  push    rbp
0x1801465eb  push    rdi
0x1801465ec  push    r12
0x1801465ee  push    r14
0x1801465f0  push    r15
0x1801465f2  mov     rbp, rsp
0x1801465f5  sub     rsp, 60h
0x1801465f9  xor     edi, edi
0x1801465fb  mov     [rbp+phAlgorithm], 0
0x180146603  mov     [rbp+phHash], 0
0x18014660b  mov     r14d, r9d
0x18014660e  mov     [rbp+pbOutput], edi
0x180146611  mov     rsi, r8
0x180146614  mov     [rbp+cbOutput], 4
0x18014661b  mov     r15d, edx
0x18014661e  mov     r12, rcx
0x180146621  test    r9d, r9d
0x180146624  jz      short loc_180146631
0x180146626  test    r8, r8
0x180146629  jz      short loc_180146631
0x18014662b  lea     r9d, [rdi+8]
0x18014662f  jmp     short loc_180146634
0x180146631  xor     r9d, r9d; dwFlags
0x180146634  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18014663b  lea     rdx, aSha1_0; "SHA1"
0x180146642  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180146646  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18014664c  mov     ebx, eax
0x18014664e  test    eax, eax
0x180146650  js      loc_18014670A
0x180146656  mov     r9d, [rbp+cbOutput]; cbOutput
0x18014665a  lea     rax, [rbp+cbOutput]
0x18014665e  mov     rcx, [rbp+phAlgorithm]; hObject
0x180146662  lea     r8, [rbp+pbOutput]; pbOutput
0x180146666  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18014666a  lea     rdx, pszProperty; "ObjectLength"
0x180146671  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180146676  call    cs:__imp_BCryptGetProperty
0x18014667c  mov     ebx, eax
0x18014667e  test    eax, eax
0x180146680  js      loc_18014670A
0x180146686  mov     ecx, [rbp+pbOutput]; Size
0x180146689  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18014668e  mov     r8d, [rbp+pbOutput]; Size
0x180146692  xor     edx, edx; Val
0x180146694  mov     rcx, rax; void *
0x180146697  mov     rdi, rax
0x18014669a  call    memset_0
0x18014669f  mov     r8d, [rbp+pbOutput]; Size
0x1801466a3  xor     edx, edx; Val
0x1801466a5  mov     rcx, rdi; void *
0x1801466a8  call    memset_0
0x1801466ad  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1801466b1  lea     rdx, [rbp+phHash]; phHash
0x1801466b5  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801466b9  mov     r8, rdi; pbHashObject
0x1801466bc  mov     [rsp+60h+var_30], 0; dwFlags
0x1801466c4  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x1801466c9  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x1801466ce  call    cs:__imp_BCryptCreateHash
0x1801466d4  mov     ebx, eax
0x1801466d6  test    eax, eax
0x1801466d8  js      short loc_18014670A
0x1801466da  mov     rcx, [rbp+phHash]; hHash
0x1801466de  xor     r9d, r9d; dwFlags
0x1801466e1  mov     r8d, r15d; cbInput
0x1801466e4  mov     rdx, r12; pbInput
0x1801466e7  call    cs:__imp_BCryptHashData
0x1801466ed  mov     ebx, eax
0x1801466ef  test    eax, eax
0x1801466f1  js      short loc_18014670A
0x1801466f3  mov     r8d, [rbp+arg_28]; cbOutput
0x1801466f7  xor     r9d, r9d; dwFlags
0x1801466fa  mov     rdx, [rbp+arg_20]; pbOutput
0x1801466fe  mov     rcx, [rbp+phHash]; hHash
0x180146702  call    cs:__imp_BCryptFinishHash
0x180146708  mov     ebx, eax
0x18014670a  mov     rcx, [rbp+phHash]; hHash
0x18014670e  test    rcx, rcx
0x180146711  jz      short loc_180146719
0x180146713  call    cs:__imp_BCryptDestroyHash
0x180146719  test    rdi, rdi
0x18014671c  jz      short loc_18014673D
0x18014671e  mov     eax, [rbp+pbOutput]
0x180146721  mov     rcx, rdi
0x180146724  test    rax, rax
0x180146727  jz      short loc_180146735
0x180146729  mov     byte ptr [rcx], 0
0x18014672c  inc     rcx
0x18014672f  sub     rax, 1
0x180146733  jnz     short loc_180146729
0x180146735  mov     rcx, rdi; Block
0x180146738  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18014673d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180146741  mov     [rbp+pbOutput], 0
0x180146748  test    rcx, rcx
0x18014674b  jz      short loc_180146755
0x18014674d  xor     edx, edx; dwFlags
0x18014674f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180146755  lea     r11, [rsp+60h+var_s0]
0x18014675a  mov     eax, ebx
0x18014675c  mov     rbx, [r11+30h]
0x180146760  mov     rsi, [r11+38h]
0x180146764  mov     rsp, r11
0x180146767  pop     r15
0x180146769  pop     r14
0x18014676b  pop     r12
0x18014676d  pop     rdi
0x18014676e  pop     rbp
0x18014676f  retn
```

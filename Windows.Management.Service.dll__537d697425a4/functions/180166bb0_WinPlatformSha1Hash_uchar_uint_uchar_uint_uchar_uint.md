# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x180166bb0`
- end: `0x180166d6b`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `443`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bddc`
- `0x18000c2f0`
- `0x18000c504`
- `0x180166bb0`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180166d43`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180166d43`
- `bcrypt!BCryptDestroyHash` at `0x180166d01`
- `bcrypt!BCryptDestroyHash` at `0x180166d01`
- `bcrypt!BCryptFinishHash` at `0x180166cea`
- `bcrypt!BCryptFinishHash` at `0x180166cea`
- `bcrypt!BCryptHashData` at `0x180166cc9`
- `bcrypt!BCryptHashData` at `0x180166cc9`
- `bcrypt!BCryptCreateHash` at `0x180166caa`
- `bcrypt!BCryptCreateHash` at `0x180166caa`
- `bcrypt!BCryptGetProperty` at `0x180166c4c`
- `bcrypt!BCryptGetProperty` at `0x180166c4c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180166c16`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180166c16`

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
0x180166bb0  mov     [rsp-28h+arg_0], rbx
0x180166bb5  mov     [rsp-28h+arg_8], rsi
0x180166bba  push    rbp
0x180166bbb  push    rdi
0x180166bbc  push    r12
0x180166bbe  push    r14
0x180166bc0  push    r15
0x180166bc2  mov     rbp, rsp
0x180166bc5  sub     rsp, 60h
0x180166bc9  xor     edi, edi
0x180166bcb  mov     [rbp+phAlgorithm], 0
0x180166bd3  mov     [rbp+phHash], 0
0x180166bdb  mov     r14d, r9d
0x180166bde  mov     [rbp+pbOutput], edi
0x180166be1  mov     rsi, r8
0x180166be4  mov     [rbp+cbOutput], 4
0x180166beb  mov     r15d, edx
0x180166bee  mov     r12, rcx
0x180166bf1  test    r9d, r9d
0x180166bf4  jz      short loc_180166C01
0x180166bf6  test    r8, r8
0x180166bf9  jz      short loc_180166C01
0x180166bfb  lea     r9d, [rdi+8]
0x180166bff  jmp     short loc_180166C04
0x180166c01  xor     r9d, r9d; dwFlags
0x180166c04  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180166c0b  lea     rdx, pszAlgId; "SHA1"
0x180166c12  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180166c16  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180166c1d  nop     dword ptr [rax+rax+00h]
0x180166c22  mov     ebx, eax
0x180166c24  test    eax, eax
0x180166c26  js      loc_180166CF8
0x180166c2c  mov     r9d, [rbp+cbOutput]; cbOutput
0x180166c30  lea     rax, [rbp+cbOutput]
0x180166c34  mov     rcx, [rbp+phAlgorithm]; hObject
0x180166c38  lea     r8, [rbp+pbOutput]; pbOutput
0x180166c3c  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180166c40  lea     rdx, aObjectlength; "ObjectLength"
0x180166c47  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180166c4c  call    cs:__imp_BCryptGetProperty
0x180166c53  nop     dword ptr [rax+rax+00h]
0x180166c58  mov     ebx, eax
0x180166c5a  test    eax, eax
0x180166c5c  js      loc_180166CF8
0x180166c62  mov     ecx, [rbp+pbOutput]; Size
0x180166c65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180166c6a  mov     r8d, [rbp+pbOutput]; Size
0x180166c6e  xor     edx, edx; Val
0x180166c70  mov     rcx, rax; void *
0x180166c73  mov     rdi, rax
0x180166c76  call    memset_0
0x180166c7b  mov     r8d, [rbp+pbOutput]; Size
0x180166c7f  xor     edx, edx; Val
0x180166c81  mov     rcx, rdi; void *
0x180166c84  call    memset_0
0x180166c89  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180166c8d  lea     rdx, [rbp+phHash]; phHash
0x180166c91  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180166c95  mov     r8, rdi; pbHashObject
0x180166c98  mov     [rsp+60h+var_30], 0; dwFlags
0x180166ca0  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x180166ca5  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x180166caa  call    cs:__imp_BCryptCreateHash
0x180166cb1  nop     dword ptr [rax+rax+00h]
0x180166cb6  mov     ebx, eax
0x180166cb8  test    eax, eax
0x180166cba  js      short loc_180166CF8
0x180166cbc  mov     rcx, [rbp+phHash]; hHash
0x180166cc0  xor     r9d, r9d; dwFlags
0x180166cc3  mov     r8d, r15d; cbInput
0x180166cc6  mov     rdx, r12; pbInput
0x180166cc9  call    cs:__imp_BCryptHashData
0x180166cd0  nop     dword ptr [rax+rax+00h]
0x180166cd5  mov     ebx, eax
0x180166cd7  test    eax, eax
0x180166cd9  js      short loc_180166CF8
0x180166cdb  mov     r8d, [rbp+arg_28]; cbOutput
0x180166cdf  xor     r9d, r9d; dwFlags
0x180166ce2  mov     rdx, [rbp+arg_20]; pbOutput
0x180166ce6  mov     rcx, [rbp+phHash]; hHash
0x180166cea  call    cs:__imp_BCryptFinishHash
0x180166cf1  nop     dword ptr [rax+rax+00h]
0x180166cf6  mov     ebx, eax
0x180166cf8  mov     rcx, [rbp+phHash]; hHash
0x180166cfc  test    rcx, rcx
0x180166cff  jz      short loc_180166D0D
0x180166d01  call    cs:__imp_BCryptDestroyHash
0x180166d08  nop     dword ptr [rax+rax+00h]
0x180166d0d  test    rdi, rdi
0x180166d10  jz      short loc_180166D31
0x180166d12  mov     eax, [rbp+pbOutput]
0x180166d15  mov     rcx, rdi
0x180166d18  test    rax, rax
0x180166d1b  jz      short loc_180166D29
0x180166d1d  mov     byte ptr [rcx], 0
0x180166d20  inc     rcx
0x180166d23  sub     rax, 1
0x180166d27  jnz     short loc_180166D1D
0x180166d29  mov     rcx, rdi; Block
0x180166d2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180166d31  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180166d35  mov     [rbp+pbOutput], 0
0x180166d3c  test    rcx, rcx
0x180166d3f  jz      short loc_180166D4F
0x180166d41  xor     edx, edx; dwFlags
0x180166d43  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180166d4a  nop     dword ptr [rax+rax+00h]
0x180166d4f  lea     r11, [rsp+60h+var_s0]
0x180166d54  mov     eax, ebx
0x180166d56  mov     rbx, [r11+30h]
0x180166d5a  mov     rsi, [r11+38h]
0x180166d5e  mov     rsp, r11
0x180166d61  pop     r15
0x180166d63  pop     r14
0x180166d65  pop     r12
0x180166d67  pop     rdi
0x180166d68  pop     rbp
0x180166d69  retn
```

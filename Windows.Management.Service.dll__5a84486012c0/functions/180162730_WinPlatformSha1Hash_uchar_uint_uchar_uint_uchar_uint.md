# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x180162730`
- end: `0x1801628c0`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `400`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bd0c`
- `0x18000bd74`
- `0x18000c414`
- `0x180162730`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18016289f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18016289f`
- `bcrypt!BCryptDestroyHash` at `0x180162863`
- `bcrypt!BCryptDestroyHash` at `0x180162863`
- `bcrypt!BCryptFinishHash` at `0x180162852`
- `bcrypt!BCryptFinishHash` at `0x180162852`
- `bcrypt!BCryptHashData` at `0x180162837`
- `bcrypt!BCryptHashData` at `0x180162837`
- `bcrypt!BCryptCreateHash` at `0x18016281e`
- `bcrypt!BCryptCreateHash` at `0x18016281e`
- `bcrypt!BCryptGetProperty` at `0x1801627c6`
- `bcrypt!BCryptGetProperty` at `0x1801627c6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180162796`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180162796`

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
0x180162730  mov     [rsp-28h+arg_0], rbx
0x180162735  mov     [rsp-28h+arg_8], rsi
0x18016273a  push    rbp
0x18016273b  push    rdi
0x18016273c  push    r12
0x18016273e  push    r14
0x180162740  push    r15
0x180162742  mov     rbp, rsp
0x180162745  sub     rsp, 60h
0x180162749  xor     edi, edi
0x18016274b  mov     [rbp+phAlgorithm], 0
0x180162753  mov     [rbp+phHash], 0
0x18016275b  mov     r14d, r9d
0x18016275e  mov     [rbp+pbOutput], edi
0x180162761  mov     rsi, r8
0x180162764  mov     [rbp+cbOutput], 4
0x18016276b  mov     r15d, edx
0x18016276e  mov     r12, rcx
0x180162771  test    r9d, r9d
0x180162774  jz      short loc_180162781
0x180162776  test    r8, r8
0x180162779  jz      short loc_180162781
0x18016277b  lea     r9d, [rdi+8]
0x18016277f  jmp     short loc_180162784
0x180162781  xor     r9d, r9d; dwFlags
0x180162784  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18016278b  lea     rdx, pszAlgId; "SHA1"
0x180162792  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180162796  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18016279c  mov     ebx, eax
0x18016279e  test    eax, eax
0x1801627a0  js      loc_18016285A
0x1801627a6  mov     r9d, [rbp+cbOutput]; cbOutput
0x1801627aa  lea     rax, [rbp+cbOutput]
0x1801627ae  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801627b2  lea     r8, [rbp+pbOutput]; pbOutput
0x1801627b6  mov     [rsp+60h+dwFlags], edi; dwFlags
0x1801627ba  lea     rdx, aObjectlength; "ObjectLength"
0x1801627c1  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1801627c6  call    cs:__imp_BCryptGetProperty
0x1801627cc  mov     ebx, eax
0x1801627ce  test    eax, eax
0x1801627d0  js      loc_18016285A
0x1801627d6  mov     ecx, [rbp+pbOutput]; Size
0x1801627d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801627de  mov     r8d, [rbp+pbOutput]; Size
0x1801627e2  xor     edx, edx; Val
0x1801627e4  mov     rcx, rax; void *
0x1801627e7  mov     rdi, rax
0x1801627ea  call    memset_0
0x1801627ef  mov     r8d, [rbp+pbOutput]; Size
0x1801627f3  xor     edx, edx; Val
0x1801627f5  mov     rcx, rdi; void *
0x1801627f8  call    memset_0
0x1801627fd  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180162801  lea     rdx, [rbp+phHash]; phHash
0x180162805  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180162809  mov     r8, rdi; pbHashObject
0x18016280c  mov     [rsp+60h+var_30], 0; dwFlags
0x180162814  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x180162819  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x18016281e  call    cs:__imp_BCryptCreateHash
0x180162824  mov     ebx, eax
0x180162826  test    eax, eax
0x180162828  js      short loc_18016285A
0x18016282a  mov     rcx, [rbp+phHash]; hHash
0x18016282e  xor     r9d, r9d; dwFlags
0x180162831  mov     r8d, r15d; cbInput
0x180162834  mov     rdx, r12; pbInput
0x180162837  call    cs:__imp_BCryptHashData
0x18016283d  mov     ebx, eax
0x18016283f  test    eax, eax
0x180162841  js      short loc_18016285A
0x180162843  mov     r8d, [rbp+arg_28]; cbOutput
0x180162847  xor     r9d, r9d; dwFlags
0x18016284a  mov     rdx, [rbp+arg_20]; pbOutput
0x18016284e  mov     rcx, [rbp+phHash]; hHash
0x180162852  call    cs:__imp_BCryptFinishHash
0x180162858  mov     ebx, eax
0x18016285a  mov     rcx, [rbp+phHash]; hHash
0x18016285e  test    rcx, rcx
0x180162861  jz      short loc_180162869
0x180162863  call    cs:__imp_BCryptDestroyHash
0x180162869  test    rdi, rdi
0x18016286c  jz      short loc_18016288D
0x18016286e  mov     eax, [rbp+pbOutput]
0x180162871  mov     rcx, rdi
0x180162874  test    rax, rax
0x180162877  jz      short loc_180162885
0x180162879  mov     byte ptr [rcx], 0
0x18016287c  inc     rcx
0x18016287f  sub     rax, 1
0x180162883  jnz     short loc_180162879
0x180162885  mov     rcx, rdi; Block
0x180162888  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18016288d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180162891  mov     [rbp+pbOutput], 0
0x180162898  test    rcx, rcx
0x18016289b  jz      short loc_1801628A5
0x18016289d  xor     edx, edx; dwFlags
0x18016289f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801628a5  lea     r11, [rsp+60h+var_s0]
0x1801628aa  mov     eax, ebx
0x1801628ac  mov     rbx, [r11+30h]
0x1801628b0  mov     rsi, [r11+38h]
0x1801628b4  mov     rsp, r11
0x1801628b7  pop     r15
0x1801628b9  pop     r14
0x1801628bb  pop     r12
0x1801628bd  pop     rdi
0x1801628be  pop     rbp
0x1801628bf  retn
```

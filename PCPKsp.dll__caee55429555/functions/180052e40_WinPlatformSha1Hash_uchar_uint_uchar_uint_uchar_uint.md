# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x180052e40`
- end: `0x180053016`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `470`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180052e40`
- `0x1800769e0`
- `0x180076e70`
- `0x18007704c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180052fde`
- `bcrypt!BCryptFinishHash` at `0x180052fde`
- `bcrypt!BCryptCreateHash` at `0x180052f2f`
- `bcrypt!BCryptCreateHash` at `0x180052f2f`
- `bcrypt!BCryptGetProperty` at `0x180052ed5`
- `bcrypt!BCryptGetProperty` at `0x180052ed5`
- `bcrypt!BCryptHashData` at `0x180052fb9`
- `bcrypt!BCryptHashData` at `0x180052fb9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180052f84`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180052f84`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180052e9f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180052e9f`
- `bcrypt!BCryptDestroyHash` at `0x180052ff1`
- `bcrypt!BCryptDestroyHash` at `0x180052ff1`

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
0x180052e40  mov     [rsp-28h+arg_0], rbx
0x180052e45  mov     [rsp-28h+arg_8], rsi
0x180052e4a  push    rbp
0x180052e4b  push    rdi
0x180052e4c  push    r12
0x180052e4e  push    r14
0x180052e50  push    r15
0x180052e52  mov     rbp, rsp
0x180052e55  sub     rsp, 60h
0x180052e59  xor     edi, edi
0x180052e5b  mov     [rbp+phAlgorithm], 0
0x180052e63  mov     [rbp+phHash], 0
0x180052e6b  mov     r14d, r9d
0x180052e6e  mov     [rbp+pbOutput], edi
0x180052e71  mov     rsi, r8
0x180052e74  mov     [rbp+cbOutput], 4
0x180052e7b  mov     r15d, edx
0x180052e7e  mov     r12, rcx
0x180052e81  test    r9d, r9d
0x180052e84  jnz     loc_180053002
0x180052e8a  xor     r9d, r9d; dwFlags
0x180052e8d  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180052e94  lea     rdx, aSha1_0; "SHA1"
0x180052e9b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180052e9f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180052ea6  nop     dword ptr [rax+rax+00h]
0x180052eab  mov     ebx, eax
0x180052ead  test    eax, eax
0x180052eaf  js      loc_180052F41
0x180052eb5  mov     r9d, [rbp+cbOutput]; cbOutput
0x180052eb9  lea     rax, [rbp+cbOutput]
0x180052ebd  mov     rcx, [rbp+phAlgorithm]; hObject
0x180052ec1  lea     r8, [rbp+pbOutput]; pbOutput
0x180052ec5  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180052ec9  lea     rdx, aObjectlength; "ObjectLength"
0x180052ed0  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180052ed5  call    cs:__imp_BCryptGetProperty
0x180052edc  nop     dword ptr [rax+rax+00h]
0x180052ee1  mov     ebx, eax
0x180052ee3  test    eax, eax
0x180052ee5  js      short loc_180052F41
0x180052ee7  mov     ecx, [rbp+pbOutput]; Size
0x180052eea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052eef  mov     r8d, [rbp+pbOutput]; Size
0x180052ef3  xor     edx, edx; Val
0x180052ef5  mov     rcx, rax; void *
0x180052ef8  mov     rdi, rax
0x180052efb  call    memset_0
0x180052f00  mov     r8d, [rbp+pbOutput]; Size
0x180052f04  xor     edx, edx; Val
0x180052f06  mov     rcx, rdi; void *
0x180052f09  call    memset_0
0x180052f0e  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180052f12  lea     rdx, [rbp+phHash]; phHash
0x180052f16  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180052f1a  mov     r8, rdi; pbHashObject
0x180052f1d  mov     [rsp+60h+var_30], 0; dwFlags
0x180052f25  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x180052f2a  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x180052f2f  call    cs:__imp_BCryptCreateHash
0x180052f36  nop     dword ptr [rax+rax+00h]
0x180052f3b  mov     ebx, eax
0x180052f3d  test    eax, eax
0x180052f3f  jns     short loc_180052FAC
0x180052f41  mov     rcx, [rbp+phHash]; hHash
0x180052f45  test    rcx, rcx
0x180052f48  jnz     loc_180052FF1
0x180052f4e  test    rdi, rdi
0x180052f51  jz      short loc_180052F72
0x180052f53  mov     eax, [rbp+pbOutput]
0x180052f56  mov     rcx, rdi
0x180052f59  test    rax, rax
0x180052f5c  jz      short loc_180052F6A
0x180052f5e  mov     byte ptr [rcx], 0
0x180052f61  inc     rcx
0x180052f64  sub     rax, 1
0x180052f68  jnz     short loc_180052F5E
0x180052f6a  mov     rcx, rdi; Block
0x180052f6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052f72  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180052f76  mov     [rbp+pbOutput], 0
0x180052f7d  test    rcx, rcx
0x180052f80  jz      short loc_180052F90
0x180052f82  xor     edx, edx; dwFlags
0x180052f84  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180052f8b  nop     dword ptr [rax+rax+00h]
0x180052f90  lea     r11, [rsp+60h+var_s0]
0x180052f95  mov     eax, ebx
0x180052f97  mov     rbx, [r11+30h]
0x180052f9b  mov     rsi, [r11+38h]
0x180052f9f  mov     rsp, r11
0x180052fa2  pop     r15
0x180052fa4  pop     r14
0x180052fa6  pop     r12
0x180052fa8  pop     rdi
0x180052fa9  pop     rbp
0x180052faa  retn
0x180052fac  mov     rcx, [rbp+phHash]; hHash
0x180052fb0  xor     r9d, r9d; dwFlags
0x180052fb3  mov     r8d, r15d; cbInput
0x180052fb6  mov     rdx, r12; pbInput
0x180052fb9  call    cs:__imp_BCryptHashData
0x180052fc0  nop     dword ptr [rax+rax+00h]
0x180052fc5  mov     ebx, eax
0x180052fc7  test    eax, eax
0x180052fc9  js      loc_180052F41
0x180052fcf  mov     r8d, [rbp+arg_28]; cbOutput
0x180052fd3  xor     r9d, r9d; dwFlags
0x180052fd6  mov     rdx, [rbp+arg_20]; pbOutput
0x180052fda  mov     rcx, [rbp+phHash]; hHash
0x180052fde  call    cs:__imp_BCryptFinishHash
0x180052fe5  nop     dword ptr [rax+rax+00h]
0x180052fea  mov     ebx, eax
0x180052fec  jmp     loc_180052F41
0x180052ff1  call    cs:__imp_BCryptDestroyHash
0x180052ff8  nop     dword ptr [rax+rax+00h]
0x180052ffd  jmp     loc_180052F4E
0x180053002  test    rsi, rsi
0x180053005  jz      loc_180052E8A
0x18005300b  mov     r9d, 8
0x180053011  jmp     loc_180052E8D
```

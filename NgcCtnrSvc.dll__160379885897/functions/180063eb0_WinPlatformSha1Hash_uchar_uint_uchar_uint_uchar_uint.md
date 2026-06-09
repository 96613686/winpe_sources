# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x180063eb0`
- end: `0x18006406b`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `443`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002cdec`
- `0x18002ce54`
- `0x18002d518`
- `0x180063eb0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180063faa`
- `bcrypt!BCryptCreateHash` at `0x180063faa`
- `bcrypt!BCryptHashData` at `0x180063fc9`
- `bcrypt!BCryptHashData` at `0x180063fc9`
- `bcrypt!BCryptFinishHash` at `0x180063fea`
- `bcrypt!BCryptFinishHash` at `0x180063fea`
- `bcrypt!BCryptDestroyHash` at `0x180064001`
- `bcrypt!BCryptDestroyHash` at `0x180064001`
- `bcrypt!BCryptGetProperty` at `0x180063f4c`
- `bcrypt!BCryptGetProperty` at `0x180063f4c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063f16`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063f16`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180064043`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180064043`

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
0x180063eb0  mov     [rsp-28h+arg_0], rbx
0x180063eb5  mov     [rsp-28h+arg_8], rsi
0x180063eba  push    rbp
0x180063ebb  push    rdi
0x180063ebc  push    r12
0x180063ebe  push    r14
0x180063ec0  push    r15
0x180063ec2  mov     rbp, rsp
0x180063ec5  sub     rsp, 60h
0x180063ec9  xor     edi, edi
0x180063ecb  mov     [rbp+phAlgorithm], 0
0x180063ed3  mov     [rbp+phHash], 0
0x180063edb  mov     r14d, r9d
0x180063ede  mov     [rbp+pbOutput], edi
0x180063ee1  mov     rsi, r8
0x180063ee4  mov     [rbp+cbOutput], 4
0x180063eeb  mov     r15d, edx
0x180063eee  mov     r12, rcx
0x180063ef1  test    r9d, r9d
0x180063ef4  jz      short loc_180063F01
0x180063ef6  test    r8, r8
0x180063ef9  jz      short loc_180063F01
0x180063efb  lea     r9d, [rdi+8]
0x180063eff  jmp     short loc_180063F04
0x180063f01  xor     r9d, r9d; dwFlags
0x180063f04  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180063f0b  lea     rdx, aSha1_0; "SHA1"
0x180063f12  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180063f16  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180063f1d  nop     dword ptr [rax+rax+00h]
0x180063f22  mov     ebx, eax
0x180063f24  test    eax, eax
0x180063f26  js      loc_180063FF8
0x180063f2c  mov     r9d, [rbp+cbOutput]; cbOutput
0x180063f30  lea     rax, [rbp+cbOutput]
0x180063f34  mov     rcx, [rbp+phAlgorithm]; hObject
0x180063f38  lea     r8, [rbp+pbOutput]; pbOutput
0x180063f3c  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180063f40  lea     rdx, aObjectlength; "ObjectLength"
0x180063f47  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180063f4c  call    cs:__imp_BCryptGetProperty
0x180063f53  nop     dword ptr [rax+rax+00h]
0x180063f58  mov     ebx, eax
0x180063f5a  test    eax, eax
0x180063f5c  js      loc_180063FF8
0x180063f62  mov     ecx, [rbp+pbOutput]; Size
0x180063f65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063f6a  mov     r8d, [rbp+pbOutput]; Size
0x180063f6e  xor     edx, edx; Val
0x180063f70  mov     rcx, rax; void *
0x180063f73  mov     rdi, rax
0x180063f76  call    memset_0
0x180063f7b  mov     r8d, [rbp+pbOutput]; Size
0x180063f7f  xor     edx, edx; Val
0x180063f81  mov     rcx, rdi; void *
0x180063f84  call    memset_0
0x180063f89  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180063f8d  lea     rdx, [rbp+phHash]; phHash
0x180063f91  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180063f95  mov     r8, rdi; pbHashObject
0x180063f98  mov     [rsp+60h+var_30], 0; dwFlags
0x180063fa0  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x180063fa5  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x180063faa  call    cs:__imp_BCryptCreateHash
0x180063fb1  nop     dword ptr [rax+rax+00h]
0x180063fb6  mov     ebx, eax
0x180063fb8  test    eax, eax
0x180063fba  js      short loc_180063FF8
0x180063fbc  mov     rcx, [rbp+phHash]; hHash
0x180063fc0  xor     r9d, r9d; dwFlags
0x180063fc3  mov     r8d, r15d; cbInput
0x180063fc6  mov     rdx, r12; pbInput
0x180063fc9  call    cs:__imp_BCryptHashData
0x180063fd0  nop     dword ptr [rax+rax+00h]
0x180063fd5  mov     ebx, eax
0x180063fd7  test    eax, eax
0x180063fd9  js      short loc_180063FF8
0x180063fdb  mov     r8d, [rbp+arg_28]; cbOutput
0x180063fdf  xor     r9d, r9d; dwFlags
0x180063fe2  mov     rdx, [rbp+arg_20]; pbOutput
0x180063fe6  mov     rcx, [rbp+phHash]; hHash
0x180063fea  call    cs:__imp_BCryptFinishHash
0x180063ff1  nop     dword ptr [rax+rax+00h]
0x180063ff6  mov     ebx, eax
0x180063ff8  mov     rcx, [rbp+phHash]; hHash
0x180063ffc  test    rcx, rcx
0x180063fff  jz      short loc_18006400D
0x180064001  call    cs:__imp_BCryptDestroyHash
0x180064008  nop     dword ptr [rax+rax+00h]
0x18006400d  test    rdi, rdi
0x180064010  jz      short loc_180064031
0x180064012  mov     eax, [rbp+pbOutput]
0x180064015  mov     rcx, rdi
0x180064018  test    rax, rax
0x18006401b  jz      short loc_180064029
0x18006401d  mov     byte ptr [rcx], 0
0x180064020  inc     rcx
0x180064023  sub     rax, 1
0x180064027  jnz     short loc_18006401D
0x180064029  mov     rcx, rdi; Block
0x18006402c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180064031  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180064035  mov     [rbp+pbOutput], 0
0x18006403c  test    rcx, rcx
0x18006403f  jz      short loc_18006404F
0x180064041  xor     edx, edx; dwFlags
0x180064043  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18006404a  nop     dword ptr [rax+rax+00h]
0x18006404f  lea     r11, [rsp+60h+var_s0]
0x180064054  mov     eax, ebx
0x180064056  mov     rbx, [r11+30h]
0x18006405a  mov     rsi, [r11+38h]
0x18006405e  mov     rsp, r11
0x180064061  pop     r15
0x180064063  pop     r14
0x180064065  pop     r12
0x180064067  pop     rdi
0x180064068  pop     rbp
0x180064069  retn
```

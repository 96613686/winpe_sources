# TpmApiPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x1800751f0`
- end: `0x180075395`
- name: `?TpmApiPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `421`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002d518`
- `0x180074a1c`
- `0x180074a48`
- `0x1800751f0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800752f4`
- `bcrypt!BCryptCreateHash` at `0x1800752f4`
- `bcrypt!BCryptHashData` at `0x180075313`
- `bcrypt!BCryptHashData` at `0x180075313`
- `bcrypt!BCryptFinishHash` at `0x180075334`
- `bcrypt!BCryptFinishHash` at `0x180075334`
- `bcrypt!BCryptDestroyHash` at `0x18007534b`
- `bcrypt!BCryptDestroyHash` at `0x18007534b`
- `bcrypt!BCryptGetProperty` at `0x180075293`
- `bcrypt!BCryptGetProperty` at `0x180075293`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180075259`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180075259`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075379`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075379`

## pseudocode

```c
__int64 __fastcall TpmApiPlatformSha1Hash(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a5,
        ULONG a6)
{
  ULONG v10; // r9d
  NTSTATUS Property; // ebx
  ULONG cbOutput; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-18h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+58h] [rbp-10h] BYREF
  ULONG pbOutput; // [rsp+B8h] [rbp+50h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbHashObject[0] = 0;
  pbOutput = 0;
  cbOutput = 4;
  if ( cbSecret && pbSecret )
    v10 = 8;
  else
    v10 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", v10);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, cbOutput, &cbOutput, 0);
    if ( Property >= 0 )
    {
      if ( (unsigned int)TpmApiCallbackAlloc(-1, pbOutput, pbHashObject) )
      {
        Property = -1073741801;
      }
      else
      {
        memset_0(pbHashObject[0], 0, pbOutput);
        Property = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], pbOutput, pbSecret, cbSecret, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(phHash, pbInput, cbInput, 0);
          if ( Property >= 0 )
            Property = BCryptFinishHash(phHash, a5, a6, 0);
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  TpmApiCallbackFree(-1, pbOutput, pbHashObject[0]);
  pbOutput = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800751f0  push    rbp
0x1800751f2  push    rbx
0x1800751f3  push    rsi
0x1800751f4  push    rdi
0x1800751f5  push    r14
0x1800751f7  push    r15
0x1800751f9  mov     rbp, rsp
0x1800751fc  sub     rsp, 68h
0x180075200  mov     [rbp+phAlgorithm], 0
0x180075208  mov     esi, r9d
0x18007520b  mov     [rbp+phHash], 0
0x180075213  mov     rdi, r8
0x180075216  mov     [rbp+pbHashObject], 0
0x18007521e  mov     r14d, edx
0x180075221  mov     [rbp+pbOutput], 0
0x180075228  mov     r15, rcx
0x18007522b  mov     [rbp+cbOutput], 4
0x180075232  test    r9d, r9d
0x180075235  jz      short loc_180075244
0x180075237  test    r8, r8
0x18007523a  jz      short loc_180075244
0x18007523c  mov     r9d, 8
0x180075242  jmp     short loc_180075247
0x180075244  xor     r9d, r9d; dwFlags
0x180075247  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18007524e  lea     rdx, aSha1_0; "SHA1"
0x180075255  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180075259  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180075260  nop     dword ptr [rax+rax+00h]
0x180075265  mov     ebx, eax
0x180075267  test    eax, eax
0x180075269  js      loc_180075342
0x18007526f  mov     r9d, [rbp+cbOutput]; cbOutput
0x180075273  lea     rax, [rbp+cbOutput]
0x180075277  mov     rcx, [rbp+phAlgorithm]; hObject
0x18007527b  lea     r8, [rbp+pbOutput]; pbOutput
0x18007527f  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180075287  lea     rdx, aObjectlength; "ObjectLength"
0x18007528e  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180075293  call    cs:__imp_BCryptGetProperty
0x18007529a  nop     dword ptr [rax+rax+00h]
0x18007529f  mov     ebx, eax
0x1800752a1  test    eax, eax
0x1800752a3  js      loc_180075342
0x1800752a9  mov     edx, [rbp+pbOutput]
0x1800752ac  lea     r8, [rbp+pbHashObject]
0x1800752b0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800752b4  call    TpmApiCallbackAlloc
0x1800752b9  test    eax, eax
0x1800752bb  jz      short loc_1800752C4
0x1800752bd  mov     ebx, 0C0000017h
0x1800752c2  jmp     short loc_180075342
0x1800752c4  mov     r8d, [rbp+pbOutput]; Size
0x1800752c8  xor     edx, edx; Val
0x1800752ca  mov     rcx, [rbp+pbHashObject]; void *
0x1800752ce  call    memset_0
0x1800752d3  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1800752d7  lea     rdx, [rbp+phHash]; phHash
0x1800752db  mov     r8, [rbp+pbHashObject]; pbHashObject
0x1800752df  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800752e3  mov     [rsp+68h+var_38], 0; dwFlags
0x1800752eb  mov     [rsp+68h+dwFlags], esi; cbSecret
0x1800752ef  mov     [rsp+68h+pcbResult], rdi; pbSecret
0x1800752f4  call    cs:__imp_BCryptCreateHash
0x1800752fb  nop     dword ptr [rax+rax+00h]
0x180075300  mov     ebx, eax
0x180075302  test    eax, eax
0x180075304  js      short loc_180075342
0x180075306  mov     rcx, [rbp+phHash]; hHash
0x18007530a  xor     r9d, r9d; dwFlags
0x18007530d  mov     r8d, r14d; cbInput
0x180075310  mov     rdx, r15; pbInput
0x180075313  call    cs:__imp_BCryptHashData
0x18007531a  nop     dword ptr [rax+rax+00h]
0x18007531f  mov     ebx, eax
0x180075321  test    eax, eax
0x180075323  js      short loc_180075342
0x180075325  mov     r8d, [rbp+arg_28]; cbOutput
0x180075329  xor     r9d, r9d; dwFlags
0x18007532c  mov     rdx, [rbp+arg_20]; pbOutput
0x180075330  mov     rcx, [rbp+phHash]; hHash
0x180075334  call    cs:__imp_BCryptFinishHash
0x18007533b  nop     dword ptr [rax+rax+00h]
0x180075340  mov     ebx, eax
0x180075342  mov     rcx, [rbp+phHash]; hHash
0x180075346  test    rcx, rcx
0x180075349  jz      short loc_180075357
0x18007534b  call    cs:__imp_BCryptDestroyHash
0x180075352  nop     dword ptr [rax+rax+00h]
0x180075357  mov     r8, [rbp+pbHashObject]
0x18007535b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007535f  mov     edx, [rbp+pbOutput]
0x180075362  call    TpmApiCallbackFree
0x180075367  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18007536b  mov     [rbp+pbOutput], 0
0x180075372  test    rcx, rcx
0x180075375  jz      short loc_180075385
0x180075377  xor     edx, edx; dwFlags
0x180075379  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180075380  nop     dword ptr [rax+rax+00h]
0x180075385  mov     eax, ebx
0x180075387  add     rsp, 68h
0x18007538b  pop     r15
0x18007538d  pop     r14
0x18007538f  pop     rdi
0x180075390  pop     rsi
0x180075391  pop     rbx
0x180075392  pop     rbp
0x180075393  retn
```

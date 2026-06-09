# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x1800403f0`
- end: `0x180040580`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `400`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007894`
- `0x180007900`
- `0x1800085d4`
- `0x1800403f0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800404de`
- `bcrypt!BCryptCreateHash` at `0x1800404de`
- `bcrypt!BCryptHashData` at `0x1800404f7`
- `bcrypt!BCryptHashData` at `0x1800404f7`
- `bcrypt!BCryptDestroyHash` at `0x180040523`
- `bcrypt!BCryptDestroyHash` at `0x180040523`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004055f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004055f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180040456`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180040456`
- `bcrypt!BCryptGetProperty` at `0x180040486`
- `bcrypt!BCryptGetProperty` at `0x180040486`
- `bcrypt!BCryptFinishHash` at `0x180040512`
- `bcrypt!BCryptFinishHash` at `0x180040512`

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
0x1800403f0  mov     [rsp-28h+arg_0], rbx
0x1800403f5  mov     [rsp-28h+arg_8], rsi
0x1800403fa  push    rbp
0x1800403fb  push    rdi
0x1800403fc  push    r12
0x1800403fe  push    r14
0x180040400  push    r15
0x180040402  mov     rbp, rsp
0x180040405  sub     rsp, 60h
0x180040409  xor     edi, edi
0x18004040b  mov     [rbp+phAlgorithm], 0
0x180040413  mov     [rbp+phHash], 0
0x18004041b  mov     r14d, r9d
0x18004041e  mov     [rbp+pbOutput], edi
0x180040421  mov     rsi, r8
0x180040424  mov     [rbp+cbOutput], 4
0x18004042b  mov     r15d, edx
0x18004042e  mov     r12, rcx
0x180040431  test    r9d, r9d
0x180040434  jz      short loc_180040441
0x180040436  test    r8, r8
0x180040439  jz      short loc_180040441
0x18004043b  lea     r9d, [rdi+8]
0x18004043f  jmp     short loc_180040444
0x180040441  xor     r9d, r9d; dwFlags
0x180040444  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18004044b  lea     rdx, aSha1; "SHA1"
0x180040452  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180040456  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004045c  mov     ebx, eax
0x18004045e  test    eax, eax
0x180040460  js      loc_18004051A
0x180040466  mov     r9d, [rbp+cbOutput]; cbOutput
0x18004046a  lea     rax, [rbp+cbOutput]
0x18004046e  mov     rcx, [rbp+phAlgorithm]; hObject
0x180040472  lea     r8, [rbp+pbOutput]; pbOutput
0x180040476  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18004047a  lea     rdx, aObjectlength; "ObjectLength"
0x180040481  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180040486  call    cs:__imp_BCryptGetProperty
0x18004048c  mov     ebx, eax
0x18004048e  test    eax, eax
0x180040490  js      loc_18004051A
0x180040496  mov     ecx, [rbp+pbOutput]; Size
0x180040499  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004049e  mov     r8d, [rbp+pbOutput]; Size
0x1800404a2  xor     edx, edx; Val
0x1800404a4  mov     rcx, rax; void *
0x1800404a7  mov     rdi, rax
0x1800404aa  call    memset_0
0x1800404af  mov     r8d, [rbp+pbOutput]; Size
0x1800404b3  xor     edx, edx; Val
0x1800404b5  mov     rcx, rdi; void *
0x1800404b8  call    memset_0
0x1800404bd  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1800404c1  lea     rdx, [rbp+phHash]; phHash
0x1800404c5  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800404c9  mov     r8, rdi; pbHashObject
0x1800404cc  mov     [rsp+60h+var_30], 0; dwFlags
0x1800404d4  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x1800404d9  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x1800404de  call    cs:__imp_BCryptCreateHash
0x1800404e4  mov     ebx, eax
0x1800404e6  test    eax, eax
0x1800404e8  js      short loc_18004051A
0x1800404ea  mov     rcx, [rbp+phHash]; hHash
0x1800404ee  xor     r9d, r9d; dwFlags
0x1800404f1  mov     r8d, r15d; cbInput
0x1800404f4  mov     rdx, r12; pbInput
0x1800404f7  call    cs:__imp_BCryptHashData
0x1800404fd  mov     ebx, eax
0x1800404ff  test    eax, eax
0x180040501  js      short loc_18004051A
0x180040503  mov     r8d, [rbp+arg_28]; cbOutput
0x180040507  xor     r9d, r9d; dwFlags
0x18004050a  mov     rdx, [rbp+arg_20]; pbOutput
0x18004050e  mov     rcx, [rbp+phHash]; hHash
0x180040512  call    cs:__imp_BCryptFinishHash
0x180040518  mov     ebx, eax
0x18004051a  mov     rcx, [rbp+phHash]; hHash
0x18004051e  test    rcx, rcx
0x180040521  jz      short loc_180040529
0x180040523  call    cs:__imp_BCryptDestroyHash
0x180040529  test    rdi, rdi
0x18004052c  jz      short loc_18004054D
0x18004052e  mov     eax, [rbp+pbOutput]
0x180040531  mov     rcx, rdi
0x180040534  test    rax, rax
0x180040537  jz      short loc_180040545
0x180040539  mov     byte ptr [rcx], 0
0x18004053c  inc     rcx
0x18004053f  sub     rax, 1
0x180040543  jnz     short loc_180040539
0x180040545  mov     rcx, rdi; Block
0x180040548  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004054d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180040551  mov     [rbp+pbOutput], 0
0x180040558  test    rcx, rcx
0x18004055b  jz      short loc_180040565
0x18004055d  xor     edx, edx; dwFlags
0x18004055f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180040565  lea     r11, [rsp+60h+var_s0]
0x18004056a  mov     eax, ebx
0x18004056c  mov     rbx, [r11+30h]
0x180040570  mov     rsi, [r11+38h]
0x180040574  mov     rsp, r11
0x180040577  pop     r15
0x180040579  pop     r14
0x18004057b  pop     r12
0x18004057d  pop     rdi
0x18004057e  pop     rbp
0x18004057f  retn
```

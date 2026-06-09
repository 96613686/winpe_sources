# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x1800af1a0`
- end: `0x1800af330`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `400`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18005d2ec`
- `0x18005db30`
- `0x18005dd44`
- `0x1800af1a0`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800af30f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800af30f`
- `bcrypt!BCryptDestroyHash` at `0x1800af2d3`
- `bcrypt!BCryptDestroyHash` at `0x1800af2d3`
- `bcrypt!BCryptFinishHash` at `0x1800af2c2`
- `bcrypt!BCryptFinishHash` at `0x1800af2c2`
- `bcrypt!BCryptGetProperty` at `0x1800af236`
- `bcrypt!BCryptGetProperty` at `0x1800af236`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800af206`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800af206`
- `bcrypt!BCryptHashData` at `0x1800af2a7`
- `bcrypt!BCryptHashData` at `0x1800af2a7`
- `bcrypt!BCryptCreateHash` at `0x1800af28e`
- `bcrypt!BCryptCreateHash` at `0x1800af28e`

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
0x1800af1a0  mov     [rsp-28h+arg_0], rbx
0x1800af1a5  mov     [rsp-28h+arg_8], rsi
0x1800af1aa  push    rbp
0x1800af1ab  push    rdi
0x1800af1ac  push    r12
0x1800af1ae  push    r14
0x1800af1b0  push    r15
0x1800af1b2  mov     rbp, rsp
0x1800af1b5  sub     rsp, 60h
0x1800af1b9  xor     edi, edi
0x1800af1bb  mov     [rbp+phAlgorithm], 0
0x1800af1c3  mov     [rbp+phHash], 0
0x1800af1cb  mov     r14d, r9d
0x1800af1ce  mov     [rbp+pbOutput], edi
0x1800af1d1  mov     rsi, r8
0x1800af1d4  mov     [rbp+cbOutput], 4
0x1800af1db  mov     r15d, edx
0x1800af1de  mov     r12, rcx
0x1800af1e1  test    r9d, r9d
0x1800af1e4  jz      short loc_1800AF1F1
0x1800af1e6  test    r8, r8
0x1800af1e9  jz      short loc_1800AF1F1
0x1800af1eb  lea     r9d, [rdi+8]
0x1800af1ef  jmp     short loc_1800AF1F4
0x1800af1f1  xor     r9d, r9d; dwFlags
0x1800af1f4  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800af1fb  lea     rdx, aSha1_0; "SHA1"
0x1800af202  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800af206  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800af20c  mov     ebx, eax
0x1800af20e  test    eax, eax
0x1800af210  js      loc_1800AF2CA
0x1800af216  mov     r9d, [rbp+cbOutput]; cbOutput
0x1800af21a  lea     rax, [rbp+cbOutput]
0x1800af21e  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800af222  lea     r8, [rbp+pbOutput]; pbOutput
0x1800af226  mov     [rsp+60h+dwFlags], edi; dwFlags
0x1800af22a  lea     rdx, aObjectlength; "ObjectLength"
0x1800af231  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800af236  call    cs:__imp_BCryptGetProperty
0x1800af23c  mov     ebx, eax
0x1800af23e  test    eax, eax
0x1800af240  js      loc_1800AF2CA
0x1800af246  mov     ecx, [rbp+pbOutput]; Size
0x1800af249  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800af24e  mov     r8d, [rbp+pbOutput]; Size
0x1800af252  xor     edx, edx; Val
0x1800af254  mov     rcx, rax; void *
0x1800af257  mov     rdi, rax
0x1800af25a  call    memset_0
0x1800af25f  mov     r8d, [rbp+pbOutput]; Size
0x1800af263  xor     edx, edx; Val
0x1800af265  mov     rcx, rdi; void *
0x1800af268  call    memset_0
0x1800af26d  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1800af271  lea     rdx, [rbp+phHash]; phHash
0x1800af275  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800af279  mov     r8, rdi; pbHashObject
0x1800af27c  mov     [rsp+60h+var_30], 0; dwFlags
0x1800af284  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x1800af289  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x1800af28e  call    cs:__imp_BCryptCreateHash
0x1800af294  mov     ebx, eax
0x1800af296  test    eax, eax
0x1800af298  js      short loc_1800AF2CA
0x1800af29a  mov     rcx, [rbp+phHash]; hHash
0x1800af29e  xor     r9d, r9d; dwFlags
0x1800af2a1  mov     r8d, r15d; cbInput
0x1800af2a4  mov     rdx, r12; pbInput
0x1800af2a7  call    cs:__imp_BCryptHashData
0x1800af2ad  mov     ebx, eax
0x1800af2af  test    eax, eax
0x1800af2b1  js      short loc_1800AF2CA
0x1800af2b3  mov     r8d, [rbp+arg_28]; cbOutput
0x1800af2b7  xor     r9d, r9d; dwFlags
0x1800af2ba  mov     rdx, [rbp+arg_20]; pbOutput
0x1800af2be  mov     rcx, [rbp+phHash]; hHash
0x1800af2c2  call    cs:__imp_BCryptFinishHash
0x1800af2c8  mov     ebx, eax
0x1800af2ca  mov     rcx, [rbp+phHash]; hHash
0x1800af2ce  test    rcx, rcx
0x1800af2d1  jz      short loc_1800AF2D9
0x1800af2d3  call    cs:__imp_BCryptDestroyHash
0x1800af2d9  test    rdi, rdi
0x1800af2dc  jz      short loc_1800AF2FD
0x1800af2de  mov     eax, [rbp+pbOutput]
0x1800af2e1  mov     rcx, rdi
0x1800af2e4  test    rax, rax
0x1800af2e7  jz      short loc_1800AF2F5
0x1800af2e9  mov     byte ptr [rcx], 0
0x1800af2ec  inc     rcx
0x1800af2ef  sub     rax, 1
0x1800af2f3  jnz     short loc_1800AF2E9
0x1800af2f5  mov     rcx, rdi; Block
0x1800af2f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af2fd  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800af301  mov     [rbp+pbOutput], 0
0x1800af308  test    rcx, rcx
0x1800af30b  jz      short loc_1800AF315
0x1800af30d  xor     edx, edx; dwFlags
0x1800af30f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800af315  lea     r11, [rsp+60h+var_s0]
0x1800af31a  mov     eax, ebx
0x1800af31c  mov     rbx, [r11+30h]
0x1800af320  mov     rsi, [r11+38h]
0x1800af324  mov     rsp, r11
0x1800af327  pop     r15
0x1800af329  pop     r14
0x1800af32b  pop     r12
0x1800af32d  pop     rdi
0x1800af32e  pop     rbp
0x1800af32f  retn
```

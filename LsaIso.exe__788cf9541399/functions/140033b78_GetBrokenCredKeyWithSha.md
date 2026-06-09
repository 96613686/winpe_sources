# GetBrokenCredKeyWithSha

- ea: `0x140033b78`
- end: `0x140033dd4`
- name: `GetBrokenCredKeyWithSha`
- size: `604`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140033de0`
- `0x140033e20`

## callees

- `0x140033b78`
- `0x140038d10`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x140033c0b`
- `ntdll!RtlLengthSid` at `0x140033c0b`
- `bcrypt!BCryptFinishHash` at `0x140033c40`
- `bcrypt!BCryptFinishHash` at `0x140033d3e`
- `bcrypt!BCryptFinishHash` at `0x140033c40`
- `bcrypt!BCryptFinishHash` at `0x140033d3e`
- `bcrypt!BCryptDestroyHash` at `0x140033c54`
- `bcrypt!BCryptDestroyHash` at `0x140033d4e`
- `bcrypt!BCryptDestroyHash` at `0x140033d96`
- `bcrypt!BCryptDestroyHash` at `0x140033da5`
- `bcrypt!BCryptDestroyHash` at `0x140033c54`
- `bcrypt!BCryptDestroyHash` at `0x140033d4e`
- `bcrypt!BCryptDestroyHash` at `0x140033d96`
- `bcrypt!BCryptDestroyHash` at `0x140033da5`
- `bcrypt!BCryptHashData` at `0x140033c1e`
- `bcrypt!BCryptHashData` at `0x140033cab`
- `bcrypt!BCryptHashData` at `0x140033cc8`
- `bcrypt!BCryptHashData` at `0x140033ce6`
- `bcrypt!BCryptHashData` at `0x140033d05`
- `bcrypt!BCryptHashData` at `0x140033d23`
- `bcrypt!BCryptHashData` at `0x140033c1e`
- `bcrypt!BCryptHashData` at `0x140033cab`
- `bcrypt!BCryptHashData` at `0x140033cc8`
- `bcrypt!BCryptHashData` at `0x140033ce6`
- `bcrypt!BCryptHashData` at `0x140033d05`
- `bcrypt!BCryptHashData` at `0x140033d23`
- `bcrypt!BCryptCreateHash` at `0x140033bf8`
- `bcrypt!BCryptCreateHash` at `0x140033c89`
- `bcrypt!BCryptCreateHash` at `0x140033bf8`
- `bcrypt!BCryptCreateHash` at `0x140033c89`

## pseudocode

```c
__int64 __fastcall GetBrokenCredKeyWithSha(
        UCHAR *a1,
        int a2,
        __int64 a3,
        ULONG a4,
        UCHAR *pbInput,
        PSID Sid,
        __int64 a7)
{
  NTSTATUS v10; // ebx
  ULONG v11; // eax
  BCRYPT_HASH_HANDLE v12; // rcx
  int v14; // eax
  int v15; // eax
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-61h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-59h] BYREF
  PUCHAR v18; // [rsp+50h] [rbp-51h]
  UCHAR v19[16]; // [rsp+58h] [rbp-49h] BYREF
  _OWORD v20[2]; // [rsp+68h] [rbp-39h] BYREF
  UCHAR pbOutput[16]; // [rsp+88h] [rbp-19h] BYREF
  __int128 v22; // [rsp+98h] [rbp-9h]

  v18 = a1;
  phHash = 0;
  hHash = 0;
  *(_OWORD *)pbOutput = 0;
  v22 = 0;
  *(_OWORD *)v19 = 0;
  memset(v20, 0, sizeof(v20));
  v10 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v10 < 0 )
    goto LABEL_16;
  v11 = RtlLengthSid(Sid);
  v10 = BCryptHashData(phHash, (PUCHAR)Sid, v11, 0);
  if ( v10 < 0 )
    goto LABEL_16;
  v10 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v10 < 0 )
    goto LABEL_16;
  BCryptDestroyHash(phHash);
  phHash = 0;
  v10 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x51, &hHash, 0, 0, 0, 0, 0);
  if ( v10 < 0
    || (v10 = BCryptHashData(hHash, (PUCHAR)"NtlmStrongCredentialKey", 0x18u, 0), v10 < 0)
    || (v10 = BCryptHashData(hHash, pbInput, a4, 0), v10 < 0)
    || (v10 = BCryptHashData(hHash, pbOutput, 0x20u, 0), v10 < 0)
    || (v10 = BCryptHashData(hHash, (PUCHAR)(a3 + 38), 0x10u, 0), v10 < 0)
    || (v10 = BCryptHashData(hHash, v18, 0x14u, 0), v10 < 0)
    || (v10 = BCryptFinishHash(hHash, v19, 0x30u, 0), v10 < 0) )
  {
LABEL_16:
    v12 = hHash;
LABEL_17:
    if ( v12 )
      BCryptDestroyHash(v12);
    goto LABEL_19;
  }
  BCryptDestroyHash(hHash);
  v12 = 0;
  *(_DWORD *)a7 = 20;
  hHash = 0;
  if ( !a2 )
  {
    v15 = DWORD1(v20[1]);
    *(_OWORD *)(a7 + 4) = *(_OWORD *)((char *)v20 + 4);
    *(_DWORD *)(a7 + 20) = v15;
    goto LABEL_17;
  }
  if ( a2 != 1 )
    return 3221225485LL;
  v14 = v20[0];
  *(_OWORD *)(a7 + 4) = *(_OWORD *)v19;
  *(_DWORD *)(a7 + 20) = v14;
LABEL_19:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140033b78  mov     [rsp-8+arg_8], rbx
0x140033b7d  push    rbp
0x140033b7e  push    rsi
0x140033b7f  push    rdi
0x140033b80  push    r12
0x140033b82  push    r13
0x140033b84  push    r14
0x140033b86  push    r15
0x140033b88  lea     rbp, [rsp-0Fh]
0x140033b8d  sub     rsp, 0B0h
0x140033b94  mov     rax, cs:__security_cookie
0x140033b9b  xor     rax, rsp
0x140033b9e  mov     [rbp+3Fh+var_38], rax
0x140033ba2  mov     rdi, [rbp+3Fh+arg_30]
0x140033ba6  xor     eax, eax
0x140033ba8  mov     r12, [rbp+3Fh+pbInput]
0x140033bac  xorps   xmm1, xmm1
0x140033baf  mov     r14, [rbp+3Fh+Sid]
0x140033bb3  xorps   xmm0, xmm0
0x140033bb6  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x140033bba  mov     r15d, r9d
0x140033bbd  mov     r13, r8
0x140033bc0  mov     [rbp+3Fh+var_90], rcx
0x140033bc4  mov     esi, edx
0x140033bc6  mov     [rsp+0E0h+cbSecret], eax; cbSecret
0x140033bca  lea     ecx, [rax+41h]; hAlgorithm
0x140033bcd  mov     [rbp+3Fh+phHash], rax
0x140033bd1  xor     r9d, r9d; cbHashObject
0x140033bd4  mov     [rbp+3Fh+hHash], rax
0x140033bd8  xor     r8d, r8d; pbHashObject
0x140033bdb  mov     [rsp+0E0h+pbSecret], rax; pbSecret
0x140033be0  lea     rdx, [rbp+3Fh+phHash]; phHash
0x140033be4  movups  xmmword ptr [rbp+3Fh+pbOutput], xmm0
0x140033be8  movups  [rbp+3Fh+var_48], xmm0
0x140033bec  movups  xmmword ptr [rbp+3Fh+var_88], xmm1
0x140033bf0  movups  [rbp+3Fh+var_78], xmm1
0x140033bf4  movups  [rbp+3Fh+var_68], xmm1
0x140033bf8  call    cs:__imp_BCryptCreateHash
0x140033bfe  mov     ebx, eax
0x140033c00  test    eax, eax
0x140033c02  js      loc_140033D8D
0x140033c08  mov     rcx, r14; Sid
0x140033c0b  call    cs:__imp_RtlLengthSid
0x140033c11  mov     rcx, [rbp+3Fh+phHash]; hHash
0x140033c15  xor     r9d, r9d; dwFlags
0x140033c18  mov     r8d, eax; cbInput
0x140033c1b  mov     rdx, r14; pbInput
0x140033c1e  call    cs:__imp_BCryptHashData
0x140033c24  mov     ebx, eax
0x140033c26  test    eax, eax
0x140033c28  js      loc_140033D8D
0x140033c2e  mov     rcx, [rbp+3Fh+phHash]; hHash
0x140033c32  lea     rdx, [rbp+3Fh+pbOutput]; pbOutput
0x140033c36  xor     r9d, r9d; dwFlags
0x140033c39  lea     r14d, [r9+20h]
0x140033c3d  mov     r8d, r14d; cbOutput
0x140033c40  call    cs:__imp_BCryptFinishHash
0x140033c46  mov     ebx, eax
0x140033c48  test    eax, eax
0x140033c4a  js      loc_140033D8D
0x140033c50  mov     rcx, [rbp+3Fh+phHash]; hHash
0x140033c54  call    cs:__imp_BCryptDestroyHash
0x140033c5a  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x140033c62  lea     rdx, [rbp+3Fh+hHash]; phHash
0x140033c66  mov     [rsp+0E0h+cbSecret], 0; cbSecret
0x140033c6e  lea     ecx, [r14+31h]; hAlgorithm
0x140033c72  xor     r9d, r9d; cbHashObject
0x140033c75  mov     [rsp+0E0h+pbSecret], 0; pbSecret
0x140033c7e  xor     r8d, r8d; pbHashObject
0x140033c81  mov     [rbp+3Fh+phHash], 0
0x140033c89  call    cs:__imp_BCryptCreateHash
0x140033c8f  mov     ebx, eax
0x140033c91  test    eax, eax
0x140033c93  js      loc_140033D8D
0x140033c99  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033c9d  lea     r8d, [r14-8]; cbInput
0x140033ca1  xor     r9d, r9d; dwFlags
0x140033ca4  lea     rdx, pbInput; "NtlmStrongCredentialKey"
0x140033cab  call    cs:__imp_BCryptHashData
0x140033cb1  mov     ebx, eax
0x140033cb3  test    eax, eax
0x140033cb5  js      loc_140033D8D
0x140033cbb  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033cbf  xor     r9d, r9d; dwFlags
0x140033cc2  mov     r8d, r15d; cbInput
0x140033cc5  mov     rdx, r12; pbInput
0x140033cc8  call    cs:__imp_BCryptHashData
0x140033cce  mov     ebx, eax
0x140033cd0  test    eax, eax
0x140033cd2  js      loc_140033D8D
0x140033cd8  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033cdc  lea     rdx, [rbp+3Fh+pbOutput]; pbInput
0x140033ce0  xor     r9d, r9d; dwFlags
0x140033ce3  mov     r8d, r14d; cbInput
0x140033ce6  call    cs:__imp_BCryptHashData
0x140033cec  mov     ebx, eax
0x140033cee  test    eax, eax
0x140033cf0  js      loc_140033D8D
0x140033cf6  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033cfa  lea     rdx, [r13+26h]; pbInput
0x140033cfe  xor     r9d, r9d; dwFlags
0x140033d01  lea     r8d, [r14-10h]; cbInput
0x140033d05  call    cs:__imp_BCryptHashData
0x140033d0b  mov     ebx, eax
0x140033d0d  test    eax, eax
0x140033d0f  js      short loc_140033D8D
0x140033d11  mov     rdx, [rbp+3Fh+var_90]; pbInput
0x140033d15  xor     r9d, r9d; dwFlags
0x140033d18  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033d1c  lea     r14d, [r9+14h]
0x140033d20  mov     r8d, r14d; cbInput
0x140033d23  call    cs:__imp_BCryptHashData
0x140033d29  mov     ebx, eax
0x140033d2b  test    eax, eax
0x140033d2d  js      short loc_140033D8D
0x140033d2f  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033d33  lea     r8d, [r14+1Ch]; cbOutput
0x140033d37  xor     r9d, r9d; dwFlags
0x140033d3a  lea     rdx, [rbp+3Fh+var_88]; pbOutput
0x140033d3e  call    cs:__imp_BCryptFinishHash
0x140033d44  mov     ebx, eax
0x140033d46  test    eax, eax
0x140033d48  js      short loc_140033D8D
0x140033d4a  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033d4e  call    cs:__imp_BCryptDestroyHash
0x140033d54  xor     ecx, ecx
0x140033d56  mov     [rdi], r14d
0x140033d59  mov     [rbp+3Fh+hHash], rcx
0x140033d5d  test    esi, esi
0x140033d5f  jz      short loc_140033D7D
0x140033d61  cmp     esi, 1
0x140033d64  jz      short loc_140033D6D
0x140033d66  mov     eax, 0C000000Dh
0x140033d6b  jmp     short loc_140033DAD
0x140033d6d  movups  xmm0, xmmword ptr [rbp+3Fh+var_88]
0x140033d71  mov     eax, dword ptr [rbp+3Fh+var_78]
0x140033d74  movups  xmmword ptr [rdi+4], xmm0
0x140033d78  mov     [rdi+14h], eax
0x140033d7b  jmp     short loc_140033D9C
0x140033d7d  movups  xmm0, [rbp+3Fh+var_78+4]
0x140033d81  mov     eax, dword ptr [rbp+3Fh+var_68+4]
0x140033d84  movups  xmmword ptr [rdi+4], xmm0
0x140033d88  mov     [rdi+14h], eax
0x140033d8b  jmp     short loc_140033D91
0x140033d8d  mov     rcx, [rbp+3Fh+hHash]; hHash
0x140033d91  test    rcx, rcx
0x140033d94  jz      short loc_140033D9C
0x140033d96  call    cs:__imp_BCryptDestroyHash
0x140033d9c  mov     rcx, [rbp+3Fh+phHash]; hHash
0x140033da0  test    rcx, rcx
0x140033da3  jz      short loc_140033DAB
0x140033da5  call    cs:__imp_BCryptDestroyHash
0x140033dab  mov     eax, ebx
0x140033dad  mov     rcx, [rbp+3Fh+var_38]
0x140033db1  xor     rcx, rsp; StackCookie
0x140033db4  call    __security_check_cookie
0x140033db9  mov     rbx, [rsp+0E0h+arg_8]
0x140033dc1  add     rsp, 0B0h
0x140033dc8  pop     r15
0x140033dca  pop     r14
0x140033dcc  pop     r13
0x140033dce  pop     r12
0x140033dd0  pop     rdi
0x140033dd1  pop     rsi
0x140033dd2  pop     rbp
0x140033dd3  retn
```

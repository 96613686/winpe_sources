# GetFileHash(wchar_t const *,wchar_t const *,HashProviderProperty,HashProviderProperty *,void *,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x14003b40c`
- end: `0x14003b7b1`
- name: `?GetFileHash@@YAJPEB_W0UHashProviderProperty@@PEAU1@PEAXPEAPEAEPEAK45@Z`
- size: `933`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, BYTE **, DWORD *, BYTE **, DWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400333b4`
- `0x14003b7b8`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14003b2a0`
- `0x14003b40c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b4ea`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b565`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b73c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b76c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b4ea`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b565`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b73c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x14003b76c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x14003b4cd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x14003b548`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x14003b4cd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x14003b548`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14003b52e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14003b755`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14003b785`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14003b52e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14003b755`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x14003b785`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b5d2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b62b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b65e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b6c8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b5d2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b62b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b65e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x14003b6c8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x14003b507`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x14003b583`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x14003b507`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x14003b583`

## pseudocode

```c
__int64 __fastcall GetFileHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        BYTE **a6,
        DWORD *a7,
        BYTE **a8,
        DWORD *a9)
{
  BYTE *v11; // rdi
  BYTE *v12; // rbx
  __int64 v13; // rdx
  unsigned int LastError; // esi
  const char *v15; // r9
  __int64 v16; // rdx
  DWORD v17; // esi
  int v18; // eax
  unsigned __int64 v19; // r9
  HCRYPTHASH v20; // rcx
  HCRYPTHASH v21; // rcx
  BYTE *v22; // rax
  BYTE *v23; // rax
  int dwFlags; // [rsp+20h] [rbp-50h]
  DWORD pdwDataLen; // [rsp+40h] [rbp-30h] BYREF
  DWORD v28; // [rsp+44h] [rbp-2Ch] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-28h] BYREF
  HCRYPTHASH hHash; // [rsp+50h] [rbp-20h] BYREF
  HCRYPTPROV hProv; // [rsp+58h] [rbp-18h] BYREF
  HCRYPTPROV phProv; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v11 = 0;
  phProv = 0;
  v12 = 0;
  hHash = 0;
  hProv = 0;
  phHash = 0;
  pdwDataLen = 0;
  v28 = 0;
  if ( !a6 )
  {
    v13 = 330;
LABEL_10:
    LastError = -2147467261;
LABEL_42:
    v19 = LastError;
    goto LABEL_43;
  }
  if ( !a7 )
  {
    v13 = 331;
    goto LABEL_10;
  }
  *a6 = 0;
  *a7 = 0;
  if ( a4 )
  {
    if ( !a8 )
    {
      v13 = 338;
      goto LABEL_10;
    }
    if ( !a9 )
    {
      v13 = 339;
      goto LABEL_10;
    }
    *a8 = 0;
    *a9 = 0;
  }
  if ( !CryptAcquireContextW(&phProv, 0, 0, *(_DWORD *)a3, 0xF0000040) )
  {
    v16 = 349;
LABEL_46:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v16,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
                  v15);
    goto LABEL_52;
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( !CryptCreateHash(phProv, *(_DWORD *)(a3 + 4), *(_QWORD *)(a3 + 8), 0, &hHash) )
  {
    v16 = 356;
    goto LABEL_46;
  }
  if ( a4 )
  {
    v17 = *(_DWORD *)a4;
    if ( hProv )
      CryptReleaseContext(hProv, 0);
    if ( !CryptAcquireContextW(&hProv, 0, 0, v17, 0xF0000040) )
    {
      v16 = 365;
      goto LABEL_46;
    }
    if ( phHash )
      CryptDestroyHash(phHash);
    if ( !CryptCreateHash(hProv, *(_DWORD *)(a4 + 4), *(_QWORD *)(a4 + 8), 0, &phHash) )
    {
      v16 = 372;
      goto LABEL_46;
    }
  }
  v18 = HashFileData(a1, hHash, phHash);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = (unsigned int)v18;
    v13 = 376;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
      (const char *)v19,
      dwFlags);
    goto LABEL_52;
  }
  v20 = hHash;
  *a7 = 0;
  if ( !CryptGetHashParam(v20, 2u, 0, &pdwDataLen, 0) )
  {
    v16 = 380;
    goto LABEL_46;
  }
  if ( pdwDataLen )
  {
    v11 = (BYTE *)SafeSusAllocArray(pdwDataLen, 1u);
    LastError = v11 == 0 ? 0x8007000E : 0;
    if ( !v11 )
    {
      v13 = 382;
      goto LABEL_42;
    }
  }
  if ( !CryptGetHashParam(hHash, 2u, v11, &pdwDataLen, 0) )
  {
    v16 = 384;
    goto LABEL_46;
  }
  if ( a4 )
  {
    v21 = phHash;
    *a9 = 0;
    if ( !CryptGetHashParam(v21, 2u, 0, &v28, 0) )
    {
      v16 = 391;
      goto LABEL_46;
    }
    if ( v28 )
    {
      v12 = (BYTE *)SafeSusAllocArray(v28, 1u);
      LastError = v12 == 0 ? 0x8007000E : 0;
      if ( !v12 )
      {
        v13 = 393;
        goto LABEL_42;
      }
    }
    if ( !CryptGetHashParam(phHash, 2u, v12, &v28, 0) )
    {
      v16 = 396;
      goto LABEL_46;
    }
  }
  v22 = v11;
  v11 = 0;
  *a6 = v22;
  *a7 = pdwDataLen;
  if ( a8 )
  {
    v23 = v12;
    v12 = 0;
    *a8 = v23;
  }
  if ( a9 )
    *a9 = v28;
  LastError = 0;
LABEL_52:
  if ( v12 )
    SusFree(v12);
  if ( v11 )
    SusFree(v11);
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( hProv )
  {
    CryptReleaseContext(hProv, 0);
    hProv = 0;
  }
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    hHash = 0;
  }
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return LastError;
}

```

## disassembly

```asm
0x14003b40c  mov     [rsp-38h+arg_8], rbx
0x14003b411  push    rbp
0x14003b412  push    rsi
0x14003b413  push    rdi
0x14003b414  push    r12
0x14003b416  push    r13
0x14003b418  push    r14
0x14003b41a  push    r15
0x14003b41c  mov     rbp, rsp
0x14003b41f  sub     rsp, 70h
0x14003b423  mov     rax, cs:__security_cookie
0x14003b42a  xor     rax, rsp
0x14003b42d  mov     [rbp+var_8], rax
0x14003b431  mov     rax, [rbp+arg_28]
0x14003b435  mov     r14, r9
0x14003b438  mov     r13, [rbp+arg_30]
0x14003b43c  mov     rsi, r8
0x14003b43f  mov     r12, [rbp+arg_38]
0x14003b443  mov     r15, [rbp+arg_40]
0x14003b44a  mov     [rbp+var_40], rcx
0x14003b44e  xor     ecx, ecx
0x14003b450  mov     [rbp+var_38], rax
0x14003b454  mov     edi, ecx
0x14003b456  mov     [rbp+phProv], rcx
0x14003b45a  mov     ebx, ecx
0x14003b45c  mov     [rbp+hHash], rcx
0x14003b460  mov     [rbp+hProv], rcx
0x14003b464  mov     [rbp+phHash], rcx
0x14003b468  mov     [rbp+pdwDataLen], ecx
0x14003b46b  mov     [rbp+var_2C], ecx
0x14003b46e  test    rax, rax
0x14003b471  jnz     short loc_14003B47A
0x14003b473  mov     edx, 14Ah
0x14003b478  jmp     short loc_14003B4A8
0x14003b47a  test    r13, r13
0x14003b47d  jnz     short loc_14003B486
0x14003b47f  mov     edx, 14Bh
0x14003b484  jmp     short loc_14003B4A8
0x14003b486  mov     [rax], rcx
0x14003b489  mov     [r13+0], ecx
0x14003b48d  test    r14, r14
0x14003b490  jz      short loc_14003B4B9
0x14003b492  test    r12, r12
0x14003b495  jnz     short loc_14003B49E
0x14003b497  mov     edx, 152h
0x14003b49c  jmp     short loc_14003B4A8
0x14003b49e  test    r15, r15
0x14003b4a1  jnz     short loc_14003B4B2
0x14003b4a3  mov     edx, 153h
0x14003b4a8  mov     esi, 80004003h
0x14003b4ad  jmp     loc_14003B69B
0x14003b4b2  mov     [r12], rcx
0x14003b4b6  mov     [r15], ecx
0x14003b4b9  mov     r9d, [r8]; dwProvType
0x14003b4bc  lea     rcx, [rbp+phProv]; phProv
0x14003b4c0  xor     r8d, r8d; szProvider
0x14003b4c3  mov     [rsp+70h+dwFlags], 0F0000040h; dwFlags
0x14003b4cb  xor     edx, edx; szContainer
0x14003b4cd  call    cs:__imp_CryptAcquireContextW
0x14003b4d3  test    eax, eax
0x14003b4d5  jnz     short loc_14003B4E1
0x14003b4d7  mov     edx, 15Dh
0x14003b4dc  jmp     loc_14003B6D7
0x14003b4e1  mov     rcx, [rbp+hHash]; hHash
0x14003b4e5  test    rcx, rcx
0x14003b4e8  jz      short loc_14003B4F0
0x14003b4ea  call    cs:__imp_CryptDestroyHash
0x14003b4f0  mov     r8, [rsi+8]; hKey
0x14003b4f4  lea     rax, [rbp+hHash]
0x14003b4f8  mov     edx, [rsi+4]; Algid
0x14003b4fb  xor     r9d, r9d; dwFlags
0x14003b4fe  mov     rcx, [rbp+phProv]; hProv
0x14003b502  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x14003b507  call    cs:__imp_CryptCreateHash
0x14003b50d  test    eax, eax
0x14003b50f  jnz     short loc_14003B51B
0x14003b511  mov     edx, 164h
0x14003b516  jmp     loc_14003B6D7
0x14003b51b  test    r14, r14
0x14003b51e  jz      short loc_14003B597
0x14003b520  mov     rcx, [rbp+hProv]; hProv
0x14003b524  mov     esi, [r14]
0x14003b527  test    rcx, rcx
0x14003b52a  jz      short loc_14003B534
0x14003b52c  xor     edx, edx; dwFlags
0x14003b52e  call    cs:__imp_CryptReleaseContext
0x14003b534  mov     r9d, esi; dwProvType
0x14003b537  mov     [rsp+70h+dwFlags], 0F0000040h; dwFlags
0x14003b53f  xor     r8d, r8d; szProvider
0x14003b542  lea     rcx, [rbp+hProv]; phProv
0x14003b546  xor     edx, edx; szContainer
0x14003b548  call    cs:__imp_CryptAcquireContextW
0x14003b54e  test    eax, eax
0x14003b550  jnz     short loc_14003B55C
0x14003b552  mov     edx, 16Dh
0x14003b557  jmp     loc_14003B6D7
0x14003b55c  mov     rcx, [rbp+phHash]; hHash
0x14003b560  test    rcx, rcx
0x14003b563  jz      short loc_14003B56B
0x14003b565  call    cs:__imp_CryptDestroyHash
0x14003b56b  mov     r8, [r14+8]; hKey
0x14003b56f  lea     rax, [rbp+phHash]
0x14003b573  mov     edx, [r14+4]; Algid
0x14003b577  xor     r9d, r9d; dwFlags
0x14003b57a  mov     rcx, [rbp+hProv]; hProv
0x14003b57e  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x14003b583  call    cs:__imp_CryptCreateHash
0x14003b589  test    eax, eax
0x14003b58b  jnz     short loc_14003B597
0x14003b58d  mov     edx, 174h
0x14003b592  jmp     loc_14003B6D7
0x14003b597  mov     r8, [rbp+phHash]
0x14003b59b  mov     rdx, [rbp+hHash]
0x14003b59f  mov     rcx, [rbp+var_40]
0x14003b5a3  call    HashFileData
0x14003b5a8  mov     esi, eax
0x14003b5aa  test    eax, eax
0x14003b5ac  jns     short loc_14003B5BB
0x14003b5ae  mov     r9d, eax
0x14003b5b1  mov     edx, 178h
0x14003b5b6  jmp     loc_14003B69E
0x14003b5bb  mov     rcx, [rbp+hHash]; hHash
0x14003b5bf  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x14003b5c3  xor     r8d, r8d; pbData
0x14003b5c6  mov     [r13+0], ebx
0x14003b5ca  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x14003b5ce  lea     edx, [r8+2]; dwParam
0x14003b5d2  call    cs:__imp_CryptGetHashParam
0x14003b5d8  test    eax, eax
0x14003b5da  jnz     short loc_14003B5E6
0x14003b5dc  mov     edx, 17Ch
0x14003b5e1  jmp     loc_14003B6D7
0x14003b5e6  mov     ecx, [rbp+pdwDataLen]; unsigned __int64
0x14003b5e9  test    rcx, rcx
0x14003b5ec  jz      short loc_14003B617
0x14003b5ee  mov     edx, 1; unsigned __int64
0x14003b5f3  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14003b5f8  mov     rdi, rax
0x14003b5fb  neg     rax
0x14003b5fe  sbb     esi, esi
0x14003b600  not     esi
0x14003b602  and     esi, 8007000Eh
0x14003b608  test    rdi, rdi
0x14003b60b  jnz     short loc_14003B617
0x14003b60d  mov     edx, 17Eh
0x14003b612  jmp     loc_14003B69B
0x14003b617  mov     rcx, [rbp+hHash]; hHash
0x14003b61b  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x14003b61f  mov     r8, rdi; pbData
0x14003b622  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x14003b626  mov     edx, 2; dwParam
0x14003b62b  call    cs:__imp_CryptGetHashParam
0x14003b631  test    eax, eax
0x14003b633  jnz     short loc_14003B63F
0x14003b635  mov     edx, 180h
0x14003b63a  jmp     loc_14003B6D7
0x14003b63f  test    r14, r14
0x14003b642  jz      loc_14003B6EB
0x14003b648  mov     rcx, [rbp+phHash]; hHash
0x14003b64c  lea     r9, [rbp+var_2C]; pdwDataLen
0x14003b650  xor     r8d, r8d; pbData
0x14003b653  mov     [r15], ebx
0x14003b656  mov     [rsp+70h+dwFlags], ebx; int
0x14003b65a  lea     edx, [r8+2]; dwParam
0x14003b65e  call    cs:__imp_CryptGetHashParam
0x14003b664  test    eax, eax
0x14003b666  jnz     short loc_14003B66F
0x14003b668  mov     edx, 187h
0x14003b66d  jmp     short loc_14003B6D7
0x14003b66f  mov     ecx, [rbp+var_2C]; unsigned __int64
0x14003b672  test    rcx, rcx
0x14003b675  jz      short loc_14003B6B0
0x14003b677  mov     edx, 1; unsigned __int64
0x14003b67c  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14003b681  mov     rbx, rax
0x14003b684  neg     rax
0x14003b687  sbb     esi, esi
0x14003b689  not     esi
0x14003b68b  and     esi, 8007000Eh
0x14003b691  test    rbx, rbx
0x14003b694  jnz     short loc_14003B6B0
0x14003b696  mov     edx, 189h; void *
0x14003b69b  mov     r9d, esi; char *
0x14003b69e  mov     rcx, [rbp+38h]; this
0x14003b6a2  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b6ae  jmp     short loc_14003B719
0x14003b6b0  mov     rcx, [rbp+phHash]; hHash
0x14003b6b4  lea     r9, [rbp+var_2C]; pdwDataLen
0x14003b6b8  mov     r8, rbx; pbData
0x14003b6bb  mov     [rsp+70h+dwFlags], 0; dwFlags
0x14003b6c3  mov     edx, 2; dwParam
0x14003b6c8  call    cs:__imp_CryptGetHashParam
0x14003b6ce  test    eax, eax
0x14003b6d0  jnz     short loc_14003B6EB
0x14003b6d2  mov     edx, 18Ch; void *
0x14003b6d7  mov     rcx, [rbp+38h]; this
0x14003b6db  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b6e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003b6e7  mov     esi, eax
0x14003b6e9  jmp     short loc_14003B719
0x14003b6eb  mov     rcx, [rbp+var_38]
0x14003b6ef  mov     rax, rdi
0x14003b6f2  xor     edi, edi
0x14003b6f4  mov     [rcx], rax
0x14003b6f7  mov     eax, [rbp+pdwDataLen]
0x14003b6fa  mov     [r13+0], eax
0x14003b6fe  test    r12, r12
0x14003b701  jz      short loc_14003B70C
0x14003b703  mov     rax, rbx
0x14003b706  xor     ebx, ebx
0x14003b708  mov     [r12], rax
0x14003b70c  test    r15, r15
0x14003b70f  jz      short loc_14003B717
0x14003b711  mov     eax, [rbp+var_2C]
0x14003b714  mov     [r15], eax
0x14003b717  xor     esi, esi
0x14003b719  test    rbx, rbx
0x14003b71c  jz      short loc_14003B726
0x14003b71e  mov     rcx, rbx; lpMem
0x14003b721  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003b726  test    rdi, rdi
0x14003b729  jz      short loc_14003B733
0x14003b72b  mov     rcx, rdi; lpMem
0x14003b72e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003b733  mov     rcx, [rbp+phHash]; hHash
0x14003b737  test    rcx, rcx
0x14003b73a  jz      short loc_14003B74A
0x14003b73c  call    cs:__imp_CryptDestroyHash
0x14003b742  mov     [rbp+phHash], 0
0x14003b74a  mov     rcx, [rbp+hProv]; hProv
0x14003b74e  test    rcx, rcx
0x14003b751  jz      short loc_14003B763
0x14003b753  xor     edx, edx; dwFlags
0x14003b755  call    cs:__imp_CryptReleaseContext
0x14003b75b  mov     [rbp+hProv], 0
0x14003b763  mov     rcx, [rbp+hHash]; hHash
0x14003b767  test    rcx, rcx
0x14003b76a  jz      short loc_14003B77A
0x14003b76c  call    cs:__imp_CryptDestroyHash
0x14003b772  mov     [rbp+hHash], 0
0x14003b77a  mov     rcx, [rbp+phProv]; hProv
0x14003b77e  test    rcx, rcx
0x14003b781  jz      short loc_14003B78B
0x14003b783  xor     edx, edx; dwFlags
0x14003b785  call    cs:__imp_CryptReleaseContext
0x14003b78b  mov     eax, esi
0x14003b78d  mov     rcx, [rbp+var_8]
0x14003b791  xor     rcx, rsp; StackCookie
0x14003b794  call    __security_check_cookie
0x14003b799  mov     rbx, [rsp+70h+arg_8]
0x14003b7a1  add     rsp, 70h
0x14003b7a5  pop     r15
0x14003b7a7  pop     r14
0x14003b7a9  pop     r13
0x14003b7ab  pop     r12
0x14003b7ad  pop     rdi
0x14003b7ae  pop     rsi
0x14003b7af  pop     rbp
0x14003b7b0  retn
```

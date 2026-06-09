# GetFileHash(wchar_t const *,wchar_t const *,HashProviderProperty,HashProviderProperty *,void *,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x18005affc`
- end: `0x18005b3a1`
- name: `?GetFileHash@@YAJPEB_W0UHashProviderProperty@@PEAU1@PEAXPEAPEAEPEAK45@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005b3a8`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dce4`
- `0x18000dd60`
- `0x18005ae90`
- `0x18005affc`
- `0x180061960`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18005b0bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18005b138`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18005b0bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18005b138`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b1c2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b21b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b24e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b2b8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b1c2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b21b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b24e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005b2b8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005b11e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005b345`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005b375`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005b11e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005b345`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005b375`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005b0f7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005b173`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005b0f7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005b173`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b0da`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b155`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b32c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b35c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b0da`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b155`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b32c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005b35c`

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
0x18005affc  mov     [rsp-38h+arg_8], rbx
0x18005b001  push    rbp
0x18005b002  push    rsi
0x18005b003  push    rdi
0x18005b004  push    r12
0x18005b006  push    r13
0x18005b008  push    r14
0x18005b00a  push    r15
0x18005b00c  mov     rbp, rsp
0x18005b00f  sub     rsp, 70h
0x18005b013  mov     rax, cs:__security_cookie
0x18005b01a  xor     rax, rsp
0x18005b01d  mov     [rbp+var_8], rax
0x18005b021  mov     rax, [rbp+arg_28]
0x18005b025  mov     r14, r9
0x18005b028  mov     r13, [rbp+arg_30]
0x18005b02c  mov     rsi, r8
0x18005b02f  mov     r12, [rbp+arg_38]
0x18005b033  mov     r15, [rbp+arg_40]
0x18005b03a  mov     [rbp+var_40], rcx
0x18005b03e  xor     ecx, ecx
0x18005b040  mov     [rbp+var_38], rax
0x18005b044  mov     edi, ecx
0x18005b046  mov     [rbp+phProv], rcx
0x18005b04a  mov     ebx, ecx
0x18005b04c  mov     [rbp+hHash], rcx
0x18005b050  mov     [rbp+hProv], rcx
0x18005b054  mov     [rbp+phHash], rcx
0x18005b058  mov     [rbp+pdwDataLen], ecx
0x18005b05b  mov     [rbp+var_2C], ecx
0x18005b05e  test    rax, rax
0x18005b061  jnz     short loc_18005B06A
0x18005b063  mov     edx, 14Ah
0x18005b068  jmp     short loc_18005B098
0x18005b06a  test    r13, r13
0x18005b06d  jnz     short loc_18005B076
0x18005b06f  mov     edx, 14Bh
0x18005b074  jmp     short loc_18005B098
0x18005b076  mov     [rax], rcx
0x18005b079  mov     [r13+0], ecx
0x18005b07d  test    r14, r14
0x18005b080  jz      short loc_18005B0A9
0x18005b082  test    r12, r12
0x18005b085  jnz     short loc_18005B08E
0x18005b087  mov     edx, 152h
0x18005b08c  jmp     short loc_18005B098
0x18005b08e  test    r15, r15
0x18005b091  jnz     short loc_18005B0A2
0x18005b093  mov     edx, 153h
0x18005b098  mov     esi, 80004003h
0x18005b09d  jmp     loc_18005B28B
0x18005b0a2  mov     [r12], rcx
0x18005b0a6  mov     [r15], ecx
0x18005b0a9  mov     r9d, [r8]; dwProvType
0x18005b0ac  lea     rcx, [rbp+phProv]; phProv
0x18005b0b0  xor     r8d, r8d; szProvider
0x18005b0b3  mov     [rsp+70h+dwFlags], 0F0000040h; dwFlags
0x18005b0bb  xor     edx, edx; szContainer
0x18005b0bd  call    cs:__imp_CryptAcquireContextW
0x18005b0c3  test    eax, eax
0x18005b0c5  jnz     short loc_18005B0D1
0x18005b0c7  mov     edx, 15Dh
0x18005b0cc  jmp     loc_18005B2C7
0x18005b0d1  mov     rcx, [rbp+hHash]; hHash
0x18005b0d5  test    rcx, rcx
0x18005b0d8  jz      short loc_18005B0E0
0x18005b0da  call    cs:__imp_CryptDestroyHash
0x18005b0e0  mov     r8, [rsi+8]; hKey
0x18005b0e4  lea     rax, [rbp+hHash]
0x18005b0e8  mov     edx, [rsi+4]; Algid
0x18005b0eb  xor     r9d, r9d; dwFlags
0x18005b0ee  mov     rcx, [rbp+phProv]; hProv
0x18005b0f2  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x18005b0f7  call    cs:__imp_CryptCreateHash
0x18005b0fd  test    eax, eax
0x18005b0ff  jnz     short loc_18005B10B
0x18005b101  mov     edx, 164h
0x18005b106  jmp     loc_18005B2C7
0x18005b10b  test    r14, r14
0x18005b10e  jz      short loc_18005B187
0x18005b110  mov     rcx, [rbp+hProv]; hProv
0x18005b114  mov     esi, [r14]
0x18005b117  test    rcx, rcx
0x18005b11a  jz      short loc_18005B124
0x18005b11c  xor     edx, edx; dwFlags
0x18005b11e  call    cs:__imp_CryptReleaseContext
0x18005b124  mov     r9d, esi; dwProvType
0x18005b127  mov     [rsp+70h+dwFlags], 0F0000040h; dwFlags
0x18005b12f  xor     r8d, r8d; szProvider
0x18005b132  lea     rcx, [rbp+hProv]; phProv
0x18005b136  xor     edx, edx; szContainer
0x18005b138  call    cs:__imp_CryptAcquireContextW
0x18005b13e  test    eax, eax
0x18005b140  jnz     short loc_18005B14C
0x18005b142  mov     edx, 16Dh
0x18005b147  jmp     loc_18005B2C7
0x18005b14c  mov     rcx, [rbp+phHash]; hHash
0x18005b150  test    rcx, rcx
0x18005b153  jz      short loc_18005B15B
0x18005b155  call    cs:__imp_CryptDestroyHash
0x18005b15b  mov     r8, [r14+8]; hKey
0x18005b15f  lea     rax, [rbp+phHash]
0x18005b163  mov     edx, [r14+4]; Algid
0x18005b167  xor     r9d, r9d; dwFlags
0x18005b16a  mov     rcx, [rbp+hProv]; hProv
0x18005b16e  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x18005b173  call    cs:__imp_CryptCreateHash
0x18005b179  test    eax, eax
0x18005b17b  jnz     short loc_18005B187
0x18005b17d  mov     edx, 174h
0x18005b182  jmp     loc_18005B2C7
0x18005b187  mov     r8, [rbp+phHash]
0x18005b18b  mov     rdx, [rbp+hHash]
0x18005b18f  mov     rcx, [rbp+var_40]
0x18005b193  call    HashFileData
0x18005b198  mov     esi, eax
0x18005b19a  test    eax, eax
0x18005b19c  jns     short loc_18005B1AB
0x18005b19e  mov     r9d, eax
0x18005b1a1  mov     edx, 178h
0x18005b1a6  jmp     loc_18005B28E
0x18005b1ab  mov     rcx, [rbp+hHash]; hHash
0x18005b1af  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18005b1b3  xor     r8d, r8d; pbData
0x18005b1b6  mov     [r13+0], ebx
0x18005b1ba  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x18005b1be  lea     edx, [r8+2]; dwParam
0x18005b1c2  call    cs:__imp_CryptGetHashParam
0x18005b1c8  test    eax, eax
0x18005b1ca  jnz     short loc_18005B1D6
0x18005b1cc  mov     edx, 17Ch
0x18005b1d1  jmp     loc_18005B2C7
0x18005b1d6  mov     ecx, [rbp+pdwDataLen]; unsigned __int64
0x18005b1d9  test    rcx, rcx
0x18005b1dc  jz      short loc_18005B207
0x18005b1de  mov     edx, 1; unsigned __int64
0x18005b1e3  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18005b1e8  mov     rdi, rax
0x18005b1eb  neg     rax
0x18005b1ee  sbb     esi, esi
0x18005b1f0  not     esi
0x18005b1f2  and     esi, 8007000Eh
0x18005b1f8  test    rdi, rdi
0x18005b1fb  jnz     short loc_18005B207
0x18005b1fd  mov     edx, 17Eh
0x18005b202  jmp     loc_18005B28B
0x18005b207  mov     rcx, [rbp+hHash]; hHash
0x18005b20b  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18005b20f  mov     r8, rdi; pbData
0x18005b212  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x18005b216  mov     edx, 2; dwParam
0x18005b21b  call    cs:__imp_CryptGetHashParam
0x18005b221  test    eax, eax
0x18005b223  jnz     short loc_18005B22F
0x18005b225  mov     edx, 180h
0x18005b22a  jmp     loc_18005B2C7
0x18005b22f  test    r14, r14
0x18005b232  jz      loc_18005B2DB
0x18005b238  mov     rcx, [rbp+phHash]; hHash
0x18005b23c  lea     r9, [rbp+var_2C]; pdwDataLen
0x18005b240  xor     r8d, r8d; pbData
0x18005b243  mov     [r15], ebx
0x18005b246  mov     [rsp+70h+dwFlags], ebx; int
0x18005b24a  lea     edx, [r8+2]; dwParam
0x18005b24e  call    cs:__imp_CryptGetHashParam
0x18005b254  test    eax, eax
0x18005b256  jnz     short loc_18005B25F
0x18005b258  mov     edx, 187h
0x18005b25d  jmp     short loc_18005B2C7
0x18005b25f  mov     ecx, [rbp+var_2C]; unsigned __int64
0x18005b262  test    rcx, rcx
0x18005b265  jz      short loc_18005B2A0
0x18005b267  mov     edx, 1; unsigned __int64
0x18005b26c  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18005b271  mov     rbx, rax
0x18005b274  neg     rax
0x18005b277  sbb     esi, esi
0x18005b279  not     esi
0x18005b27b  and     esi, 8007000Eh
0x18005b281  test    rbx, rbx
0x18005b284  jnz     short loc_18005B2A0
0x18005b286  mov     edx, 189h; void *
0x18005b28b  mov     r9d, esi; char *
0x18005b28e  mov     rcx, [rbp+38h]; this
0x18005b292  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005b299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b29e  jmp     short loc_18005B309
0x18005b2a0  mov     rcx, [rbp+phHash]; hHash
0x18005b2a4  lea     r9, [rbp+var_2C]; pdwDataLen
0x18005b2a8  mov     r8, rbx; pbData
0x18005b2ab  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18005b2b3  mov     edx, 2; dwParam
0x18005b2b8  call    cs:__imp_CryptGetHashParam
0x18005b2be  test    eax, eax
0x18005b2c0  jnz     short loc_18005B2DB
0x18005b2c2  mov     edx, 18Ch; void *
0x18005b2c7  mov     rcx, [rbp+38h]; this
0x18005b2cb  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005b2d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005b2d7  mov     esi, eax
0x18005b2d9  jmp     short loc_18005B309
0x18005b2db  mov     rcx, [rbp+var_38]
0x18005b2df  mov     rax, rdi
0x18005b2e2  xor     edi, edi
0x18005b2e4  mov     [rcx], rax
0x18005b2e7  mov     eax, [rbp+pdwDataLen]
0x18005b2ea  mov     [r13+0], eax
0x18005b2ee  test    r12, r12
0x18005b2f1  jz      short loc_18005B2FC
0x18005b2f3  mov     rax, rbx
0x18005b2f6  xor     ebx, ebx
0x18005b2f8  mov     [r12], rax
0x18005b2fc  test    r15, r15
0x18005b2ff  jz      short loc_18005B307
0x18005b301  mov     eax, [rbp+var_2C]
0x18005b304  mov     [r15], eax
0x18005b307  xor     esi, esi
0x18005b309  test    rbx, rbx
0x18005b30c  jz      short loc_18005B316
0x18005b30e  mov     rcx, rbx; lpMem
0x18005b311  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005b316  test    rdi, rdi
0x18005b319  jz      short loc_18005B323
0x18005b31b  mov     rcx, rdi; lpMem
0x18005b31e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005b323  mov     rcx, [rbp+phHash]; hHash
0x18005b327  test    rcx, rcx
0x18005b32a  jz      short loc_18005B33A
0x18005b32c  call    cs:__imp_CryptDestroyHash
0x18005b332  mov     [rbp+phHash], 0
0x18005b33a  mov     rcx, [rbp+hProv]; hProv
0x18005b33e  test    rcx, rcx
0x18005b341  jz      short loc_18005B353
0x18005b343  xor     edx, edx; dwFlags
0x18005b345  call    cs:__imp_CryptReleaseContext
0x18005b34b  mov     [rbp+hProv], 0
0x18005b353  mov     rcx, [rbp+hHash]; hHash
0x18005b357  test    rcx, rcx
0x18005b35a  jz      short loc_18005B36A
0x18005b35c  call    cs:__imp_CryptDestroyHash
0x18005b362  mov     [rbp+hHash], 0
0x18005b36a  mov     rcx, [rbp+phProv]; hProv
0x18005b36e  test    rcx, rcx
0x18005b371  jz      short loc_18005B37B
0x18005b373  xor     edx, edx; dwFlags
0x18005b375  call    cs:__imp_CryptReleaseContext
0x18005b37b  mov     eax, esi
0x18005b37d  mov     rcx, [rbp+var_8]
0x18005b381  xor     rcx, rsp; StackCookie
0x18005b384  call    __security_check_cookie
0x18005b389  mov     rbx, [rsp+70h+arg_8]
0x18005b391  add     rsp, 70h
0x18005b395  pop     r15
0x18005b397  pop     r14
0x18005b399  pop     r13
0x18005b39b  pop     r12
0x18005b39d  pop     rdi
0x18005b39e  pop     rsi
0x18005b39f  pop     rbp
0x18005b3a0  retn
```

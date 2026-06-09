# HMAC::Init(unsigned __int64,uint,uchar *,ulong)

- ea: `0x18005e398`
- end: `0x18005e5a3`
- name: `?Init@HMAC@@QEAAJ_KIPEAEK@Z`
- size: `523`
- prototype: `__int64 __fastcall(HMAC *__hidden this, HCRYPTPROV hProv, ALG_ID Algid, unsigned __int8 *Src, DWORD dwDataLen)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005e310`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x1800522ae`
- `0x18005e398`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005e453`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005e529`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005e56c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005e453`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005e529`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005e56c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005e497`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005e497`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDuplicateHash` at `0x18005e4e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDuplicateHash` at `0x18005e4e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005e3f2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005e4bc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005e3f2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005e4bc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005e426`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005e480`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005e426`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005e480`

## pseudocode

```c
__int64 __fastcall HMAC::Init(HMAC *this, HCRYPTPROV hProv, ALG_ID Algid, unsigned __int8 *Src, DWORD dwDataLen)
{
  HCRYPTHASH *v9; // rbx
  HCRYPTHASH v11; // rcx
  HCRYPTHASH v12; // rcx
  __int64 i; // rax
  unsigned int v14; // ebx
  __int64 j; // rax
  DWORD pdwDataLen[4]; // [rsp+30h] [rbp-41h] BYREF
  BYTE pbData[64]; // [rsp+40h] [rbp-31h] BYREF

  pdwDataLen[0] = 0;
  memset_0(pbData, 0, sizeof(pbData));
  v9 = (HCRYPTHASH *)(this + 2);
  if ( !CryptCreateHash(hProv, Algid, 0, 0, (HCRYPTHASH *)this + 1) )
    return (unsigned int)-2147467259;
  v11 = *v9;
  pdwDataLen[0] = 4;
  if ( !CryptGetHashParam(v11, 4u, (BYTE *)this, pdwDataLen, 0) || *this > 0x14 )
    return (unsigned int)-2147467259;
  if ( dwDataLen <= 0x40 )
  {
    memcpy_0(pbData, Src, dwDataLen);
  }
  else
  {
    if ( !CryptHashData(*v9, Src, dwDataLen, 0) )
      return (unsigned int)-2147467259;
    v12 = *v9;
    pdwDataLen[0] = *this;
    if ( !CryptGetHashParam(v12, 2u, pbData, pdwDataLen, 0)
      || !CryptDestroyHash(*v9)
      || !CryptCreateHash(hProv, Algid, 0, 0, (HCRYPTHASH *)this + 1) )
    {
      return (unsigned int)-2147467259;
    }
  }
  if ( !CryptDuplicateHash(*v9, 0, 0, (HCRYPTHASH *)this + 2) )
    return (unsigned int)-2147467259;
  for ( i = 0; i != 64; i += 16 )
    *(__m128 *)&pbData[i] = _mm_xor_ps((__m128)_mm_loadu_si128((const __m128i *)&pbData[i]), (__m128)_xmm);
  if ( !CryptHashData(*v9, pbData, 0x40u, 0) )
    return (unsigned int)-2147467259;
  v14 = 0;
  for ( j = 0; j != 64; j += 16 )
    *(__m128 *)&pbData[j] = _mm_xor_ps((__m128)_mm_loadu_si128((const __m128i *)&pbData[j]), (__m128)_xmm);
  if ( !CryptHashData(*((_QWORD *)this + 2), pbData, 0x40u, 0) )
    return (unsigned int)-2147467259;
  return v14;
}

```

## disassembly

```asm
0x18005e398  push    rbp
0x18005e39a  push    rbx
0x18005e39b  push    rsi
0x18005e39c  push    rdi
0x18005e39d  push    r14
0x18005e39f  push    r15
0x18005e3a1  lea     rbp, [rsp-27h]
0x18005e3a6  sub     rsp, 98h
0x18005e3ad  mov     rax, cs:__security_cookie
0x18005e3b4  xor     rax, rsp
0x18005e3b7  mov     [rbp+4Fh+var_40], rax
0x18005e3bb  mov     r14, rdx
0x18005e3be  mov     [rbp+4Fh+pdwDataLen], 0
0x18005e3c5  xor     edx, edx; Val
0x18005e3c7  mov     r15d, r8d
0x18005e3ca  mov     rdi, rcx
0x18005e3cd  mov     rsi, r9
0x18005e3d0  lea     rcx, [rbp+4Fh+pbData]; void *
0x18005e3d4  lea     r8d, [rdx+40h]; Size
0x18005e3d8  call    memset_0
0x18005e3dd  lea     rbx, [rdi+8]
0x18005e3e1  xor     r9d, r9d; dwFlags
0x18005e3e4  xor     r8d, r8d; hKey
0x18005e3e7  mov     [rsp+0C0h+phHash], rbx; phHash
0x18005e3ec  mov     edx, r15d; Algid
0x18005e3ef  mov     rcx, r14; hProv
0x18005e3f2  call    cs:__imp_CryptCreateHash
0x18005e3f9  nop     dword ptr [rax+rax+00h]
0x18005e3fe  test    eax, eax
0x18005e400  jnz     short loc_18005E40C
0x18005e402  mov     ecx, 80004005h
0x18005e407  jmp     loc_18005E584
0x18005e40c  mov     rcx, [rbx]; hHash
0x18005e40f  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x18005e413  mov     edx, 4; dwParam
0x18005e418  mov     dword ptr [rsp+0C0h+phHash], 0; dwFlags
0x18005e420  mov     r8, rdi; pbData
0x18005e423  mov     [rbp+4Fh+pdwDataLen], edx
0x18005e426  call    cs:__imp_CryptGetHashParam
0x18005e42d  nop     dword ptr [rax+rax+00h]
0x18005e432  test    eax, eax
0x18005e434  jz      short loc_18005E402
0x18005e436  cmp     dword ptr [rdi], 14h
0x18005e439  ja      short loc_18005E402
0x18005e43b  mov     eax, [rbp+4Fh+dwDataLen]
0x18005e43e  mov     rdx, rsi; Src
0x18005e441  cmp     eax, 40h ; '@'
0x18005e444  jbe     loc_18005E4D1
0x18005e44a  mov     rcx, [rbx]; hHash
0x18005e44d  xor     r9d, r9d; dwFlags
0x18005e450  mov     r8d, eax; dwDataLen
0x18005e453  call    cs:__imp_CryptHashData
0x18005e45a  nop     dword ptr [rax+rax+00h]
0x18005e45f  test    eax, eax
0x18005e461  jz      short loc_18005E402
0x18005e463  mov     eax, [rdi]
0x18005e465  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x18005e469  mov     rcx, [rbx]; hHash
0x18005e46c  lea     r8, [rbp+4Fh+pbData]; pbData
0x18005e470  mov     edx, 2; dwParam
0x18005e475  mov     [rbp+4Fh+pdwDataLen], eax
0x18005e478  mov     dword ptr [rsp+0C0h+phHash], 0; dwFlags
0x18005e480  call    cs:__imp_CryptGetHashParam
0x18005e487  nop     dword ptr [rax+rax+00h]
0x18005e48c  test    eax, eax
0x18005e48e  jz      loc_18005E402
0x18005e494  mov     rcx, [rbx]; hHash
0x18005e497  call    cs:__imp_CryptDestroyHash
0x18005e49e  nop     dword ptr [rax+rax+00h]
0x18005e4a3  test    eax, eax
0x18005e4a5  jz      loc_18005E402
0x18005e4ab  xor     r9d, r9d; dwFlags
0x18005e4ae  mov     [rsp+0C0h+phHash], rbx; phHash
0x18005e4b3  xor     r8d, r8d; hKey
0x18005e4b6  mov     edx, r15d; Algid
0x18005e4b9  mov     rcx, r14; hProv
0x18005e4bc  call    cs:__imp_CryptCreateHash
0x18005e4c3  nop     dword ptr [rax+rax+00h]
0x18005e4c8  test    eax, eax
0x18005e4ca  jnz     short loc_18005E4DD
0x18005e4cc  jmp     loc_18005E402
0x18005e4d1  mov     r8, rax; Size
0x18005e4d4  lea     rcx, [rbp+4Fh+pbData]; void *
0x18005e4d8  call    memcpy_0
0x18005e4dd  mov     rcx, [rbx]; hHash
0x18005e4e0  lea     r9, [rdi+10h]; phHash
0x18005e4e4  xor     r8d, r8d; dwFlags
0x18005e4e7  xor     edx, edx; pdwReserved
0x18005e4e9  call    cs:__imp_CryptDuplicateHash
0x18005e4f0  nop     dword ptr [rax+rax+00h]
0x18005e4f5  test    eax, eax
0x18005e4f7  jz      loc_18005E402
0x18005e4fd  xor     eax, eax
0x18005e4ff  movdqu  xmm0, xmmword ptr [rbp+rax+4Fh+pbData]
0x18005e505  xorps   xmm0, cs:__xmm@36363636363636363636363636363636
0x18005e50c  movdqu  xmmword ptr [rbp+rax+4Fh+pbData], xmm0
0x18005e512  add     rax, 10h
0x18005e516  cmp     rax, 40h ; '@'
0x18005e51a  jnz     short loc_18005E4FF
0x18005e51c  mov     rcx, [rbx]; hHash
0x18005e51f  lea     rdx, [rbp+4Fh+pbData]; pbData
0x18005e523  xor     r9d, r9d; dwFlags
0x18005e526  mov     r8d, eax; dwDataLen
0x18005e529  call    cs:__imp_CryptHashData
0x18005e530  nop     dword ptr [rax+rax+00h]
0x18005e535  test    eax, eax
0x18005e537  jz      loc_18005E402
0x18005e53d  xor     ebx, ebx
0x18005e53f  xor     eax, eax
0x18005e541  movdqu  xmm0, xmmword ptr [rbp+rax+4Fh+pbData]
0x18005e547  xorps   xmm0, cs:__xmm@6a6a6a6a6a6a6a6a6a6a6a6a6a6a6a6a
0x18005e54e  movdqu  xmmword ptr [rbp+rax+4Fh+pbData], xmm0
0x18005e554  add     rax, 10h
0x18005e558  cmp     rax, 40h ; '@'
0x18005e55c  jnz     short loc_18005E541
0x18005e55e  mov     rcx, [rdi+10h]; hHash
0x18005e562  lea     rdx, [rbp+4Fh+pbData]; pbData
0x18005e566  xor     r9d, r9d; dwFlags
0x18005e569  mov     r8d, eax; dwDataLen
0x18005e56c  call    cs:__imp_CryptHashData
0x18005e573  nop     dword ptr [rax+rax+00h]
0x18005e578  mov     ecx, 80004005h
0x18005e57d  test    eax, eax
0x18005e57f  cmovz   ebx, ecx
0x18005e582  mov     ecx, ebx
0x18005e584  mov     eax, ecx
0x18005e586  mov     rcx, [rbp+4Fh+var_40]
0x18005e58a  xor     rcx, rsp; StackCookie
0x18005e58d  call    __security_check_cookie
0x18005e592  add     rsp, 98h
0x18005e599  pop     r15
0x18005e59b  pop     r14
0x18005e59d  pop     rdi
0x18005e59e  pop     rsi
0x18005e59f  pop     rbx
0x18005e5a0  pop     rbp
0x18005e5a1  retn
```

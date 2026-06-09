# CBuildFlightID::FapSha256Truncate32(ushort const *,uchar *,unsigned __int64)

- ea: `0x18002c308`
- end: `0x18002c458`
- name: `?FapSha256Truncate32@CBuildFlightID@@CAJPEBGPEAE_K@Z`
- size: `336`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c01c`

## callees

- `0x180004b80`
- `0x18000cc6c`
- `0x18002c308`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002c388`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002c388`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002c3c7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002c3c7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002c434`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002c434`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002c34a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002c34a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002c40e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002c40e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002c3ea`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002c426`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002c3ea`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002c426`

## string_xrefs

- `0x18002c358`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\buildflightid.cpp`
- `0x18002c396`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\buildflightid.cpp`
- `0x18002c3d8`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\buildflightid.cpp`

## pseudocode

```c
__int64 __fastcall CBuildFlightID::FapSha256Truncate32(BYTE *pbData, unsigned __int8 *a2)
{
  const char *v4; // r9
  const char *v6; // r9
  unsigned int LastError; // ebx
  __int64 v8; // r8
  const char *v9; // r9
  __int64 v10; // rdx
  HCRYPTHASH v11; // rcx
  HCRYPTHASH phHash; // [rsp+30h] [rbp-40h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-38h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-30h] BYREF
  BYTE pbDataa[32]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x40,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\buildflightid.cpp",
             v4);
  phHash = 0;
  if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&pbData[2 * v8] );
    if ( CryptHashData(phHash, pbData, 2 * v8, 0) )
    {
      pdwDataLen = 32;
      if ( CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
      {
        v11 = phHash;
        *(_DWORD *)a2 = *(_DWORD *)pbDataa;
        CryptDestroyHash(v11);
        LastError = 0;
        goto LABEL_13;
      }
      v10 = 90;
    }
    else
    {
      v10 = 82;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\buildflightid.cpp",
                  v9);
    CryptDestroyHash(phHash);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x48,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\buildflightid.cpp",
                  v6);
  }
LABEL_13:
  CryptReleaseContext(phProv, 0);
  return LastError;
}

```

## disassembly

```asm
0x18002c308  mov     [rsp-18h+arg_10], rbx
0x18002c30d  push    rbp
0x18002c30e  push    rsi
0x18002c30f  push    rdi
0x18002c310  mov     rbp, rsp
0x18002c313  sub     rsp, 70h
0x18002c317  mov     rax, cs:__security_cookie
0x18002c31e  xor     rax, rsp
0x18002c321  mov     [rbp+var_8], rax
0x18002c325  xor     esi, esi
0x18002c327  mov     [rsp+70h+dwFlags], 0F0000000h; dwFlags
0x18002c32f  mov     rdi, rdx
0x18002c332  mov     [rbp+phProv], rsi
0x18002c336  mov     rbx, rcx
0x18002c339  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18002c340  xor     edx, edx; szContainer
0x18002c342  lea     rcx, [rbp+phProv]; phProv
0x18002c346  lea     r9d, [rsi+18h]; dwProvType
0x18002c34a  call    cs:__imp_CryptAcquireContextW
0x18002c350  test    eax, eax
0x18002c352  jnz     short loc_18002C36C
0x18002c354  mov     rcx, [rbp+18h]; this
0x18002c358  lea     r8, aOnecoreBaseFli_54; "onecore\\base\\flighting\\flightsetting"...
0x18002c35f  lea     edx, [rsi+40h]; void *
0x18002c362  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c367  jmp     loc_18002C43C
0x18002c36c  mov     rcx, [rbp+phProv]; hProv
0x18002c370  lea     rax, [rbp+phHash]
0x18002c374  xor     r9d, r9d; dwFlags
0x18002c377  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x18002c37c  xor     r8d, r8d; hKey
0x18002c37f  mov     [rbp+phHash], rsi
0x18002c383  mov     edx, 800Ch; Algid
0x18002c388  call    cs:__imp_CryptCreateHash
0x18002c38e  test    eax, eax
0x18002c390  jnz     short loc_18002C3AC
0x18002c392  mov     rcx, [rbp+18h]; this
0x18002c396  lea     r8, aOnecoreBaseFli_54; "onecore\\base\\flighting\\flightsetting"...
0x18002c39d  lea     edx, [rax+48h]; void *
0x18002c3a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c3a5  mov     ebx, eax
0x18002c3a7  jmp     loc_18002C42E
0x18002c3ac  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c3b0  inc     r8
0x18002c3b3  cmp     [rbx+r8*2], si
0x18002c3b8  jnz     short loc_18002C3B0
0x18002c3ba  mov     rcx, [rbp+phHash]; hHash
0x18002c3be  add     r8d, r8d; dwDataLen
0x18002c3c1  xor     r9d, r9d; dwFlags
0x18002c3c4  mov     rdx, rbx; pbData
0x18002c3c7  call    cs:__imp_CryptHashData
0x18002c3cd  test    eax, eax
0x18002c3cf  jnz     short loc_18002C3F2
0x18002c3d1  lea     edx, [rax+52h]; void *
0x18002c3d4  mov     rcx, [rbp+18h]; this
0x18002c3d8  lea     r8, aOnecoreBaseFli_54; "onecore\\base\\flighting\\flightsetting"...
0x18002c3df  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c3e4  mov     rcx, [rbp+phHash]; hHash
0x18002c3e8  mov     ebx, eax
0x18002c3ea  call    cs:__imp_CryptDestroyHash
0x18002c3f0  jmp     short loc_18002C42E
0x18002c3f2  mov     rcx, [rbp+phHash]; hHash
0x18002c3f6  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002c3fa  lea     r8, [rbp+pbData]; pbData
0x18002c3fe  mov     [rbp+pdwDataLen], 20h ; ' '
0x18002c405  mov     edx, 2; dwParam
0x18002c40a  mov     [rsp+70h+dwFlags], esi; dwFlags
0x18002c40e  call    cs:__imp_CryptGetHashParam
0x18002c414  test    eax, eax
0x18002c416  jnz     short loc_18002C41D
0x18002c418  lea     edx, [rax+5Ah]
0x18002c41b  jmp     short loc_18002C3D4
0x18002c41d  mov     eax, dword ptr [rbp+pbData]
0x18002c420  mov     rcx, [rbp+phHash]; hHash
0x18002c424  mov     [rdi], eax
0x18002c426  call    cs:__imp_CryptDestroyHash
0x18002c42c  mov     ebx, esi
0x18002c42e  mov     rcx, [rbp+phProv]; hProv
0x18002c432  xor     edx, edx; dwFlags
0x18002c434  call    cs:__imp_CryptReleaseContext
0x18002c43a  mov     eax, ebx
0x18002c43c  mov     rcx, [rbp+var_8]
0x18002c440  xor     rcx, rsp; StackCookie
0x18002c443  call    __security_check_cookie
0x18002c448  mov     rbx, [rsp+70h+arg_10]
0x18002c450  add     rsp, 70h
0x18002c454  pop     rdi
0x18002c455  pop     rsi
0x18002c456  pop     rbp
0x18002c457  retn
```

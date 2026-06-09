# FlightDriverClientAPI::Sha256Truncate32(ushort const *,uchar *,unsigned __int64)

- ea: `0x180031cfc`
- end: `0x180031e94`
- name: `?Sha256Truncate32@FlightDriverClientAPI@@CAJPEBGPEAE_K@Z`
- size: `408`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800304a4`

## callees

- `0x180004b80`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180031cfc`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180031db3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180031db3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180031df4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180031df4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180031e70`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180031e70`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180031d73`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180031d73`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180031e48`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180031e48`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180031e19`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180031e62`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180031e19`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180031e62`

## string_xrefs

- `0x180031d2f`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180031d81`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180031dc1`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180031e07`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`

## pseudocode

```c
__int64 __fastcall FlightDriverClientAPI::Sha256Truncate32(BYTE *pbData, unsigned __int8 *a2)
{
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  const char *v6; // r9
  const char *v8; // r9
  __int64 v9; // r8
  const char *v10; // r9
  __int64 v11; // rdx
  HCRYPTHASH v12; // rcx
  int dwFlags; // [rsp+20h] [rbp-50h]
  HCRYPTHASH phHash; // [rsp+30h] [rbp-40h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-38h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-30h] BYREF
  BYTE pbDataa[16]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v18; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( pbData )
  {
    if ( !a2 )
    {
      v4 = 712;
      goto LABEL_3;
    }
    phProv = 0;
    if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2D0,
               (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
               v6);
    phHash = 0;
    if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)&pbData[2 * v9] );
      if ( CryptHashData(phHash, pbData, 2 * v9, 0) )
      {
        pdwDataLen = 32;
        *(_OWORD *)pbDataa = 0;
        v18 = 0;
        if ( CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
        {
          v12 = phHash;
          *(_DWORD *)a2 = *(_DWORD *)pbDataa;
          CryptDestroyHash(v12);
          LastError = 0;
          goto LABEL_18;
        }
        v11 = 748;
      }
      else
      {
        v11 = 739;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v11,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
                    v10);
      CryptDestroyHash(phHash);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2D8,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
                    v8);
    }
LABEL_18:
    CryptReleaseContext(phProv, 0);
    return LastError;
  }
  v4 = 711;
LABEL_3:
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
    (const char *)0x80070057LL,
    dwFlags);
  return LastError;
}

```

## disassembly

```asm
0x180031cfc  mov     [rsp-18h+arg_10], rbx
0x180031d01  push    rbp
0x180031d02  push    rsi
0x180031d03  push    rdi
0x180031d04  mov     rbp, rsp
0x180031d07  sub     rsp, 70h
0x180031d0b  mov     rax, cs:__security_cookie
0x180031d12  xor     rax, rsp
0x180031d15  mov     [rbp+var_8], rax
0x180031d19  xor     esi, esi
0x180031d1b  mov     rdi, rdx
0x180031d1e  mov     rbx, rcx
0x180031d21  test    rcx, rcx
0x180031d24  jnz     short loc_180031D48
0x180031d26  mov     edx, 2C7h; void *
0x180031d2b  mov     rcx, [rbp+18h]; this
0x180031d2f  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031d36  mov     ebx, 80070057h
0x180031d3b  mov     r9d, ebx; char *
0x180031d3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d43  jmp     loc_180031E76
0x180031d48  test    rdi, rdi
0x180031d4b  jnz     short loc_180031D54
0x180031d4d  mov     edx, 2C8h
0x180031d52  jmp     short loc_180031D2B
0x180031d54  mov     r9d, 18h; dwProvType
0x180031d5a  mov     [rbp+phProv], rsi
0x180031d5e  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180031d65  mov     [rsp+70h+dwFlags], 0F0000000h; dwFlags
0x180031d6d  xor     edx, edx; szContainer
0x180031d6f  lea     rcx, [rbp+phProv]; phProv
0x180031d73  call    cs:__imp_CryptAcquireContextW
0x180031d79  test    eax, eax
0x180031d7b  jnz     short loc_180031D97
0x180031d7d  mov     rcx, [rbp+18h]; this
0x180031d81  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031d88  mov     edx, 2D0h; void *
0x180031d8d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031d92  jmp     loc_180031E78
0x180031d97  mov     rcx, [rbp+phProv]; hProv
0x180031d9b  lea     rax, [rbp+phHash]
0x180031d9f  xor     r9d, r9d; dwFlags
0x180031da2  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x180031da7  xor     r8d, r8d; hKey
0x180031daa  mov     [rbp+phHash], rsi
0x180031dae  mov     edx, 800Ch; Algid
0x180031db3  call    cs:__imp_CryptCreateHash
0x180031db9  test    eax, eax
0x180031dbb  jnz     short loc_180031DD9
0x180031dbd  mov     rcx, [rbp+18h]; this
0x180031dc1  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031dc8  mov     edx, 2D8h; void *
0x180031dcd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031dd2  mov     ebx, eax
0x180031dd4  jmp     loc_180031E6A
0x180031dd9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031ddd  inc     r8
0x180031de0  cmp     [rbx+r8*2], si
0x180031de5  jnz     short loc_180031DDD
0x180031de7  mov     rcx, [rbp+phHash]; hHash
0x180031deb  add     r8d, r8d; dwDataLen
0x180031dee  xor     r9d, r9d; dwFlags
0x180031df1  mov     rdx, rbx; pbData
0x180031df4  call    cs:__imp_CryptHashData
0x180031dfa  test    eax, eax
0x180031dfc  jnz     short loc_180031E21
0x180031dfe  mov     edx, 2E3h; void *
0x180031e03  mov     rcx, [rbp+18h]; this
0x180031e07  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031e0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031e13  mov     rcx, [rbp+phHash]; hHash
0x180031e17  mov     ebx, eax
0x180031e19  call    cs:__imp_CryptDestroyHash
0x180031e1f  jmp     short loc_180031E6A
0x180031e21  mov     rcx, [rbp+phHash]; hHash
0x180031e25  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180031e29  xorps   xmm0, xmm0
0x180031e2c  mov     [rbp+pdwDataLen], 20h ; ' '
0x180031e33  lea     r8, [rbp+pbData]; pbData
0x180031e37  mov     [rsp+70h+dwFlags], esi; dwFlags
0x180031e3b  mov     edx, 2; dwParam
0x180031e40  movups  xmmword ptr [rbp+pbData], xmm0
0x180031e44  movups  [rbp+var_18], xmm0
0x180031e48  call    cs:__imp_CryptGetHashParam
0x180031e4e  test    eax, eax
0x180031e50  jnz     short loc_180031E59
0x180031e52  mov     edx, 2ECh
0x180031e57  jmp     short loc_180031E03
0x180031e59  mov     eax, dword ptr [rbp+pbData]
0x180031e5c  mov     rcx, [rbp+phHash]; hHash
0x180031e60  mov     [rdi], eax
0x180031e62  call    cs:__imp_CryptDestroyHash
0x180031e68  mov     ebx, esi
0x180031e6a  mov     rcx, [rbp+phProv]; hProv
0x180031e6e  xor     edx, edx; dwFlags
0x180031e70  call    cs:__imp_CryptReleaseContext
0x180031e76  mov     eax, ebx
0x180031e78  mov     rcx, [rbp+var_8]
0x180031e7c  xor     rcx, rsp; StackCookie
0x180031e7f  call    __security_check_cookie
0x180031e84  mov     rbx, [rsp+70h+arg_10]
0x180031e8c  add     rsp, 70h
0x180031e90  pop     rdi
0x180031e91  pop     rsi
0x180031e92  pop     rbp
0x180031e93  retn
```

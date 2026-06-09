# FlightSettingsAPICommon::ComputeBufferHashString(uchar const *,ulong,ushort * *)

- ea: `0x180088cf8`
- end: `0x180088ed6`
- name: `?ComputeBufferHashString@FlightSettingsAPICommon@@CAJPEBEKPEAPEAG@Z`
- size: `478`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180088edc`
- `0x1800beeb4`

## callees

- `0x180004b80`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001f01c`
- `0x1800855bc`
- `0x1800855fc`
- `0x180088cf8`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180088d92`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180088d92`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180088dce`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180088dce`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180088d4c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180088d4c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180088dff`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180088dff`

## string_xrefs

- `0x180088d5a`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x180088da5`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x180088e53`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`

## pseudocode

```c
__int64 __fastcall FlightSettingsAPICommon::ComputeBufferHashString(
        BYTE *pbData,
        DWORD dwDataLen,
        unsigned __int16 **a3)
{
  const char *v6; // r9
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rbx
  int v11; // eax
  int v12; // edi
  int dwFlags; // [rsp+20h] [rbp-29h]
  HCRYPTHASH phHash; // [rsp+30h] [rbp-19h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-11h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-9h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-1h] BYREF
  __int64 v19; // [rsp+50h] [rbp+7h]
  __int64 v20; // [rsp+58h] [rbp+Fh]
  BYTE pbDataa[32]; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a3 = 0;
  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000040) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x250,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
                  v6);
    goto LABEL_16;
  }
  phHash = 0;
  if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
  {
    v9 = 595;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
                  v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
    goto LABEL_16;
  }
  if ( !CryptHashData(phHash, pbData, dwDataLen, 0) )
  {
    v9 = 597;
    goto LABEL_5;
  }
  pdwDataLen = 32;
  if ( !CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
  {
    v9 = 604;
    goto LABEL_5;
  }
  v18 = 0;
  v10 = 0;
  v19 = 0;
  v20 = 0;
  while ( (unsigned int)v10 < pdwDataLen )
  {
    v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
            &v18,
            L"%02x",
            pbDataa[v10]);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x262,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
        (const char *)(unsigned int)v11,
        dwFlags);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
      LastError = v12;
      goto LABEL_16;
    }
    v10 = (unsigned int)(v10 + 1);
  }
  *a3 = v18;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
  LastError = 0;
LABEL_16:
  __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
  return LastError;
}

```

## disassembly

```asm
0x180088cf8  mov     [rsp-8+arg_18], rbx
0x180088cfd  push    rbp
0x180088cfe  push    rsi
0x180088cff  push    rdi
0x180088d00  lea     rbp, [rsp-47h]
0x180088d05  sub     rsp, 90h
0x180088d0c  mov     rax, cs:__security_cookie
0x180088d13  xor     rax, rsp
0x180088d16  mov     [rbp+57h+var_20], rax
0x180088d1a  mov     rsi, r8
0x180088d1d  mov     qword ptr [r8], 0
0x180088d24  mov     edi, edx
0x180088d26  mov     [rbp+57h+phProv], 0
0x180088d2e  mov     rbx, rcx
0x180088d31  mov     [rsp+0A0h+dwFlags], 0F0000040h; dwFlags
0x180088d39  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180088d40  xor     edx, edx; szContainer
0x180088d42  lea     rcx, [rbp+57h+phProv]; phProv
0x180088d46  mov     r9d, 18h; dwProvType
0x180088d4c  call    cs:__imp_CryptAcquireContextW
0x180088d52  test    eax, eax
0x180088d54  jnz     short loc_180088D72
0x180088d56  mov     rcx, [rbp+5Fh]; this
0x180088d5a  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x180088d61  mov     edx, 250h; void *
0x180088d66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180088d6b  mov     ebx, eax
0x180088d6d  jmp     loc_180088EAC
0x180088d72  mov     rcx, [rbp+57h+phProv]; hProv
0x180088d76  lea     rax, [rbp+57h+phHash]
0x180088d7a  xor     r9d, r9d; dwFlags
0x180088d7d  mov     qword ptr [rsp+0A0h+dwFlags], rax; phHash
0x180088d82  xor     r8d, r8d; hKey
0x180088d85  mov     [rbp+57h+phHash], 0
0x180088d8d  mov     edx, 800Ch; Algid
0x180088d92  call    cs:__imp_CryptCreateHash
0x180088d98  test    eax, eax
0x180088d9a  jnz     short loc_180088DC1
0x180088d9c  mov     edx, 253h; void *
0x180088da1  mov     rcx, [rbp+5Fh]; this
0x180088da5  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x180088dac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180088db1  lea     rcx, [rbp+57h+phHash]
0x180088db5  mov     ebx, eax
0x180088db7  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180088dbc  jmp     loc_180088EAC
0x180088dc1  mov     rcx, [rbp+57h+phHash]; hHash
0x180088dc5  xor     r9d, r9d; dwFlags
0x180088dc8  mov     r8d, edi; dwDataLen
0x180088dcb  mov     rdx, rbx; pbData
0x180088dce  call    cs:__imp_CryptHashData
0x180088dd4  test    eax, eax
0x180088dd6  jnz     short loc_180088DDF
0x180088dd8  mov     edx, 255h
0x180088ddd  jmp     short loc_180088DA1
0x180088ddf  mov     rcx, [rbp+57h+phHash]; hHash
0x180088de3  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180088de7  lea     r8, [rbp+57h+pbData]; pbData
0x180088deb  mov     [rbp+57h+pdwDataLen], 20h ; ' '
0x180088df2  mov     edx, 2; dwParam
0x180088df7  mov     [rsp+0A0h+dwFlags], 0; int
0x180088dff  call    cs:__imp_CryptGetHashParam
0x180088e05  test    eax, eax
0x180088e07  jnz     short loc_180088E10
0x180088e09  mov     edx, 25Ch
0x180088e0e  jmp     short loc_180088DA1
0x180088e10  mov     [rbp+57h+var_58], 0
0x180088e18  xor     ebx, ebx
0x180088e1a  mov     [rbp+57h+var_50], 0
0x180088e22  mov     [rbp+57h+var_48], 0
0x180088e2a  lea     rcx, [rbp+57h+var_58]
0x180088e2e  cmp     ebx, [rbp+57h+pdwDataLen]
0x180088e31  jnb     short loc_180088E7D
0x180088e33  movzx   r8d, [rbp+rbx+57h+pbData]
0x180088e39  lea     rdx, a02x; "%02x"
0x180088e40  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180088e45  mov     edi, eax
0x180088e47  test    eax, eax
0x180088e49  js      short loc_180088E4F
0x180088e4b  inc     ebx
0x180088e4d  jmp     short loc_180088E2A
0x180088e4f  mov     rcx, [rbp+5Fh]; this
0x180088e53  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x180088e5a  mov     r9d, edi; char *
0x180088e5d  mov     edx, 262h; void *
0x180088e62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088e67  lea     rcx, [rbp+57h+var_58]
0x180088e6b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180088e70  lea     rcx, [rbp+57h+phHash]
0x180088e74  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180088e79  mov     ebx, edi
0x180088e7b  jmp     short loc_180088EAC
0x180088e7d  mov     rax, [rbp+57h+var_58]
0x180088e81  mov     [rsi], rax
0x180088e84  mov     [rbp+57h+var_58], 0
0x180088e8c  mov     [rbp+57h+var_48], 0
0x180088e94  mov     [rbp+57h+var_50], 0
0x180088e9c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180088ea1  lea     rcx, [rbp+57h+phHash]
0x180088ea5  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180088eaa  xor     ebx, ebx
0x180088eac  lea     rcx, [rbp+57h+phProv]
0x180088eb0  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180088eb5  mov     eax, ebx
0x180088eb7  mov     rcx, [rbp+57h+var_20]
0x180088ebb  xor     rcx, rsp; StackCookie
0x180088ebe  call    __security_check_cookie
0x180088ec3  mov     rbx, [rsp+0A0h+arg_18]
0x180088ecb  add     rsp, 90h
0x180088ed2  pop     rdi
0x180088ed3  pop     rsi
0x180088ed4  pop     rbp
0x180088ed5  retn
```

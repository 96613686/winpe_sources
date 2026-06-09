# PluginGetUvKeyName

- ea: `0x180042ebc`
- end: `0x18004330f`
- name: `PluginGetUvKeyName`
- size: `1107`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022718`
- `0x18004177c`

## callees

- `0x18000c050`
- `0x180017a88`
- `0x1800328b8`
- `0x180036da4`
- `0x18003a9e8`
- `0x180042df8`
- `0x180042ebc`
- `0x18004349c`
- `0x180043a94`
- `0x1800467e0`
- `0x18005e500`
- `0x1800859d8`
- `0x18010bfa8`
- `0x18011c42c`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043023`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004323f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043023`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004323f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043197`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043197`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042f7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042f7e`
- `bcrypt!BCryptGenRandom` at `0x18004304f`
- `bcrypt!BCryptGenRandom` at `0x18004304f`
- `RPCRT4!UuidToStringW` at `0x1800430a5`
- `RPCRT4!UuidToStringW` at `0x1800430a5`
- `cryptngc!NgcGetUserIdKeyName` at `0x180043276`
- `cryptngc!NgcGetUserIdKeyName` at `0x180043276`

## string_xrefs

- `0x180042f02`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180042f36`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180042fab`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180043064`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800430ba`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180043124`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800431ac`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x18004328d`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180043245`: `PluginUvKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall PluginGetUvKeyName(__int64 a1, const WCHAR *a2, __int64 a3)
{
  const char *v6; // r9
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v8; // ebx
  HKEY *v10; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  int UserIdKeyName; // eax
  unsigned int v19; // ebx
  int phkResult; // [rsp+20h] [rbp-A8h]
  int phkResulta; // [rsp+20h] [rbp-A8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A8h]
  unsigned int phkResultc; // [rsp+20h] [rbp-A8h]
  int phkResultd; // [rsp+20h] [rbp-A8h]
  DWORD pcbData; // [rsp+40h] [rbp-88h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-78h] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-70h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-68h] BYREF
  PVOID pvData[3]; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v31[3]; // [rsp+80h] [rbp-48h] BYREF
  UCHAR pbBuffer[16]; // [rsp+98h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      v6);
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, (__int64)&hKey);
  v8 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v8;
  }
  hkey = 0;
  v10 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  if ( RegOpenKeyExW(hKey, a2, 0, 0xF003Fu, v10) == 2 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)0x80090011LL,
        phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2148073489LL;
  }
  else
  {
    pcbData = 0;
    if ( RegGetValueW(hkey, 0, L"UvKeyId", 2u, 0, 0, &pcbData) )
    {
      *(_OWORD *)pbBuffer = 0;
      v11 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
      if ( v11 < 0 )
      {
        v12 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x30,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
                (const char *)(unsigned int)v11,
                phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v12;
      }
      StringUuid = 0;
      v13 = UuidToStringW((const UUID *)pbBuffer, &StringUuid);
      if ( v13 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x33,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
                (const char *)v13,
                phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v14;
      }
      v15 = -1;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpData,
        StringUuid,
        -1);
      if ( !lpData )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)0x8007000ELL,
          phkResultb);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpData);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942414LL;
      }
      do
        ++v15;
      while ( *(_WORD *)&lpData[2 * v15] );
      pcbData = 2 * v15 + 2;
      v16 = RegSetValueExW(hkey, L"UvKeyId", 0, 1u, lpData, pcbData);
      if ( v16 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x3B,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
                (const char *)v16,
                phkResultc);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpData);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v17;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpData);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
    }
    std::vector<unsigned short>::vector<unsigned short>(pvData, (unsigned __int64)pcbData >> 1);
    RegGetValueW(hkey, 0, L"UvKeyId", 2u, 0, pvData[0], &pcbData);
    v31[0] = L"PluginUvKey";
    v31[1] = 0;
    v31[2] = pvData[0];
    UserIdKeyName = NgcGetUserIdKeyName(v31, 0, a3);
    v19 = UserIdKeyName;
    if ( UserIdKeyName >= 0 )
    {
      std::vector<unsigned short>::_Tidy(pvData);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)UserIdKeyName,
        phkResultd);
      std::vector<unsigned short>::_Tidy(pvData);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v19;
    }
  }
}

```

## disassembly

```asm
0x180042ebc  mov     [rsp+arg_18], rbx
0x180042ec1  push    rsi
0x180042ec2  push    rdi
0x180042ec3  push    r14
0x180042ec5  sub     rsp, 0B0h
0x180042ecc  mov     rax, cs:__security_cookie
0x180042ed3  xor     rax, rsp
0x180042ed6  mov     [rsp+0C8h+var_20], rax
0x180042ede  mov     rsi, r8
0x180042ee1  mov     rdi, rdx
0x180042ee4  mov     rbx, rcx
0x180042ee7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180042eee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180042ef3  mov     rcx, [rsp+0C8h]; this
0x180042efb  xor     r14d, r14d
0x180042efe  test    al, al
0x180042f00  jz      short loc_180042F13
0x180042f02  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180042f09  lea     edx, [r14+17h]; void *
0x180042f0d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180042f13  mov     [rsp+0C8h+hKey], r14
0x180042f18  lea     rdx, [rsp+0C8h+hKey]
0x180042f1d  mov     rcx, rbx
0x180042f20  call    GetUserPluginAuthenticatorsRegKey
0x180042f25  mov     ebx, eax
0x180042f27  test    eax, eax
0x180042f29  jns     short loc_180042F59
0x180042f2b  mov     rcx, [rsp+0C8h]; this
0x180042f33  mov     r9d, eax; char *
0x180042f36  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180042f3d  mov     edx, 1Ah; void *
0x180042f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042f47  nop
0x180042f48  lea     rcx, [rsp+0C8h+hKey]
0x180042f4d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042f52  mov     eax, ebx
0x180042f54  jmp     loc_1800432EA
0x180042f59  mov     [rsp+0C8h+hkey], r14
0x180042f5e  lea     rcx, [rsp+0C8h+hkey]
0x180042f63  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180042f68  mov     [rsp+0C8h+phkResult], rax; int
0x180042f6d  mov     r9d, 0F003Fh; samDesired
0x180042f73  xor     r8d, r8d; ulOptions
0x180042f76  mov     rdx, rdi; lpSubKey
0x180042f79  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180042f7e  call    cs:__imp_RegOpenKeyExW
0x180042f84  mov     edi, 2
0x180042f89  cmp     eax, edi
0x180042f8b  jnz     short loc_180042FF9
0x180042f8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180042f94  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180042f99  test    al, al
0x180042f9b  jz      short loc_180042FDA
0x180042f9d  mov     rcx, [rsp+0C8h]; this
0x180042fa5  mov     r9d, 80090011h; char *
0x180042fab  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180042fb2  lea     edx, [rdi+20h]; void *
0x180042fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042fba  nop
0x180042fbb  lea     rcx, [rsp+0C8h+hkey]
0x180042fc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042fc5  nop
0x180042fc6  lea     rcx, [rsp+0C8h+hKey]
0x180042fcb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042fd0  mov     eax, 80090011h
0x180042fd5  jmp     loc_1800432EA
0x180042fda  lea     rcx, [rsp+0C8h+hkey]
0x180042fdf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042fe4  nop
0x180042fe5  lea     rcx, [rsp+0C8h+hKey]
0x180042fea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042fef  mov     eax, 80090011h
0x180042ff4  jmp     loc_1800432EA
0x180042ff9  mov     [rsp+0C8h+var_88], r14d
0x180042ffe  lea     rax, [rsp+0C8h+var_88]
0x180043003  mov     [rsp+0C8h+pcbData], rax; pcbData
0x180043008  mov     [rsp+0C8h+pvData], r14; pvData
0x18004300d  mov     [rsp+0C8h+phkResult], r14; int
0x180043012  mov     r9d, edi; dwFlags
0x180043015  lea     r8, aUvkeyid; "UvKeyId"
0x18004301c  xor     edx, edx; lpSubKey
0x18004301e  mov     rcx, [rsp+0C8h+hkey]; hkey
0x180043023  call    cs:__imp_RegGetValueW
0x180043029  test    eax, eax
0x18004302b  jz      loc_180043204
0x180043031  xorps   xmm0, xmm0
0x180043034  movups  xmmword ptr [rsp+0C8h+pbBuffer], xmm0
0x18004303c  mov     r9d, edi; dwFlags
0x18004303f  mov     r8d, 10h; cbBuffer
0x180043045  lea     rdx, [rsp+0C8h+pbBuffer]; pbBuffer
0x18004304d  xor     ecx, ecx; hAlgorithm
0x18004304f  call    cs:__imp_BCryptGenRandom
0x180043055  test    eax, eax
0x180043057  jns     short loc_180043093
0x180043059  mov     rcx, [rsp+0C8h]; this
0x180043061  mov     r9d, eax; char *
0x180043064  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004306b  mov     edx, 30h ; '0'; void *
0x180043070  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180043075  mov     ebx, eax
0x180043077  lea     rcx, [rsp+0C8h+hkey]
0x18004307c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043081  nop
0x180043082  lea     rcx, [rsp+0C8h+hKey]
0x180043087  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004308c  mov     eax, ebx
0x18004308e  jmp     loc_1800432EA
0x180043093  mov     [rsp+0C8h+StringUuid], r14
0x180043098  lea     rdx, [rsp+0C8h+StringUuid]; StringUuid
0x18004309d  lea     rcx, [rsp+0C8h+pbBuffer]; Uuid
0x1800430a5  call    cs:__imp_UuidToStringW
0x1800430ab  test    eax, eax
0x1800430ad  jz      short loc_1800430F4
0x1800430af  mov     rcx, [rsp+0C8h]; this
0x1800430b7  mov     r9d, eax; char *
0x1800430ba  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800430c1  mov     edx, 33h ; '3'; void *
0x1800430c6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800430cb  mov     ebx, eax
0x1800430cd  lea     rcx, [rsp+0C8h+StringUuid]
0x1800430d2  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800430d7  nop
0x1800430d8  lea     rcx, [rsp+0C8h+hkey]
0x1800430dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800430e2  nop
0x1800430e3  lea     rcx, [rsp+0C8h+hKey]
0x1800430e8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800430ed  mov     eax, ebx
0x1800430ef  jmp     loc_1800432EA
0x1800430f4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800430f8  mov     r8, rbx
0x1800430fb  mov     rdx, [rsp+0C8h+StringUuid]
0x180043100  lea     rcx, [rsp+0C8h+lpData]
0x180043105  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004310a  mov     rax, [rsp+0C8h+lpData]
0x18004310f  test    rax, rax
0x180043112  jnz     short loc_180043164
0x180043114  mov     rcx, [rsp+0C8h]; this
0x18004311c  mov     ebx, 8007000Eh
0x180043121  mov     r9d, ebx; char *
0x180043124  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004312b  lea     edx, [rax+37h]; void *
0x18004312e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043133  lea     rcx, [rsp+0C8h+lpData]
0x180043138  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004313d  lea     rcx, [rsp+0C8h+StringUuid]
0x180043142  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043147  nop
0x180043148  lea     rcx, [rsp+0C8h+hkey]
0x18004314d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043152  nop
0x180043153  lea     rcx, [rsp+0C8h+hKey]
0x180043158  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004315d  mov     eax, ebx
0x18004315f  jmp     loc_1800432EA
0x180043164  inc     rbx
0x180043167  cmp     [rax+rbx*2], r14w
0x18004316c  jnz     short loc_180043164
0x18004316e  lea     edx, ds:2[rbx*2]
0x180043175  mov     [rsp+0C8h+var_88], edx
0x180043179  mov     dword ptr [rsp+0C8h+pvData], edx; cbData
0x18004317d  mov     [rsp+0C8h+phkResult], rax; unsigned int
0x180043182  mov     r9d, 1; dwType
0x180043188  xor     r8d, r8d; Reserved
0x18004318b  lea     rdx, aUvkeyid; "UvKeyId"
0x180043192  mov     rcx, [rsp+0C8h+hkey]; hKey
0x180043197  call    cs:__imp_RegSetValueExW
0x18004319d  test    eax, eax
0x18004319f  jz      short loc_1800431F0
0x1800431a1  mov     rcx, [rsp+0C8h]; this
0x1800431a9  mov     r9d, eax; char *
0x1800431ac  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800431b3  mov     edx, 3Bh ; ';'; void *
0x1800431b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800431bd  mov     ebx, eax
0x1800431bf  lea     rcx, [rsp+0C8h+lpData]
0x1800431c4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800431c9  lea     rcx, [rsp+0C8h+StringUuid]
0x1800431ce  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800431d3  nop
0x1800431d4  lea     rcx, [rsp+0C8h+hkey]
0x1800431d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800431de  nop
0x1800431df  lea     rcx, [rsp+0C8h+hKey]
0x1800431e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800431e9  mov     eax, ebx
0x1800431eb  jmp     loc_1800432EA
0x1800431f0  lea     rcx, [rsp+0C8h+lpData]
0x1800431f5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800431fa  lea     rcx, [rsp+0C8h+StringUuid]
0x1800431ff  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043204  mov     edx, [rsp+0C8h+var_88]
0x180043208  shr     rdx, 1
0x18004320b  lea     rcx, [rsp+0C8h+var_60]
0x180043210  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180043215  lea     rax, [rsp+0C8h+var_88]
0x18004321a  mov     [rsp+0C8h+pcbData], rax; pcbData
0x18004321f  mov     rax, [rsp+0C8h+var_60]
0x180043224  mov     [rsp+0C8h+pvData], rax; pvData
0x180043229  mov     [rsp+0C8h+phkResult], r14; int
0x18004322e  mov     r9d, edi; dwFlags
0x180043231  lea     r8, aUvkeyid; "UvKeyId"
0x180043238  xor     edx, edx; lpSubKey
0x18004323a  mov     rcx, [rsp+0C8h+hkey]; hkey
0x18004323f  call    cs:__imp_RegGetValueW
0x180043245  lea     rax, aPluginuvkey; "PluginUvKey"
0x18004324c  mov     [rsp+0C8h+var_48], rax
0x180043254  mov     [rsp+0C8h+var_40], r14
0x18004325c  mov     rax, [rsp+0C8h+var_60]
0x180043261  mov     [rsp+0C8h+var_38], rax
0x180043269  mov     r8, rsi
0x18004326c  xor     edx, edx
0x18004326e  lea     rcx, [rsp+0C8h+var_48]
0x180043276  call    cs:__imp_NgcGetUserIdKeyName
0x18004327c  mov     ebx, eax
0x18004327e  test    eax, eax
0x180043280  jns     short loc_1800432C2
0x180043282  mov     rcx, [rsp+0C8h]; this
0x18004328a  mov     r9d, eax; char *
0x18004328d  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180043294  mov     edx, 43h ; 'C'; void *
0x180043299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004329e  lea     rcx, [rsp+0C8h+var_60]
0x1800432a3  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800432a8  nop
0x1800432a9  lea     rcx, [rsp+0C8h+hkey]
0x1800432ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800432b3  nop
0x1800432b4  lea     rcx, [rsp+0C8h+hKey]
0x1800432b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800432be  mov     eax, ebx
0x1800432c0  jmp     short loc_1800432EA
0x1800432c2  lea     rcx, [rsp+0C8h+var_60]
0x1800432c7  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800432cc  nop
0x1800432cd  lea     rcx, [rsp+0C8h+hkey]
0x1800432d2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800432d7  nop
0x1800432d8  lea     rcx, [rsp+0C8h+hKey]
0x1800432dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800432e2  xor     eax, eax
0x1800432e4  jmp     short loc_1800432EA
0x1800432e6  mov     eax, [rsp+0C8h+var_88]
0x1800432ea  mov     rcx, [rsp+0C8h+var_20]
0x1800432f2  xor     rcx, rsp; StackCookie
0x1800432f5  call    __security_check_cookie
0x1800432fa  mov     rbx, [rsp+0C8h+arg_18]
0x180043302  add     rsp, 0B0h
0x180043309  pop     r14
0x18004330b  pop     rdi
0x18004330c  pop     rsi
0x18004330d  retn
```

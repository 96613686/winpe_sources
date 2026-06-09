# PluginDeleteInternalUvKey(HKEY__ *,void * const)

- ea: `0x180043f84`
- end: `0x1800441bd`
- name: `?PluginDeleteInternalUvKey@@YAJPEAUHKEY__@@QEAX@Z`
- size: `569`
- prototype: `__int64 __fastcall(HKEY hKey, void *const)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180122144`

## callees

- `0x180017764`
- `0x180017a88`
- `0x18001ee7c`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x1800328b8`
- `0x180036da4`
- `0x180043948`
- `0x180043a18`
- `0x180043ab4`
- `0x180043f84`
- `0x1800441c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044009`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044009`
- `ncrypt!NCryptOpenKey` at `0x180044131`
- `ncrypt!NCryptOpenKey` at `0x180044131`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800440ad`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800440ad`
- `ncrypt!NCryptDeleteKey` at `0x180044159`
- `ncrypt!NCryptDeleteKey` at `0x180044159`
- `cryptngc!NgcGetUserIdKeyName` at `0x18004406a`
- `cryptngc!NgcGetUserIdKeyName` at `0x18004406a`

## string_xrefs

- `0x180043fe4`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180044017`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180044078`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800440bb`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800440eb`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x18004413f`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180044167`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180044032`: `PluginUvKey`

## pseudocode

```c
__int64 __fastcall PluginDeleteInternalUvKey(NCRYPT_KEY_HANDLE hKey, void *const a2)
{
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // esi
  unsigned int v7; // ebx
  unsigned int v8; // eax
  int UserIdKeyName; // eax
  SECURITY_STATUS v10; // eax
  int v11; // eax
  const WCHAR *v12; // rbx
  SECURITY_STATUS v13; // eax
  SECURITY_STATUS v14; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-40h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-40h]
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v20[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp+20h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+90h] [rbp+30h] BYREF
  LPCWSTR pszKeyName; // [rsp+98h] [rbp+38h] BYREF

  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  phKey = hKey;
  dwFlags = 268435462;
  v5 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
         &phKey,
         v4,
         L"UvKeyId",
         &v18);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = RegDeleteValueW((HKEY)hKey, L"UvKeyId");
    if ( v8 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1D6,
             (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
             (const char *)v8,
             0x10000006u);
    }
    else
    {
      v20[1] = 0;
      v20[0] = L"PluginUvKey";
      v20[2] = v18;
      pszKeyName = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszKeyName,
        0);
      UserIdKeyName = NgcGetUserIdKeyName(v20, 0, &pszKeyName);
      if ( UserIdKeyName < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)UserIdKeyName,
          268435462);
      phProvider = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &phProvider,
        0);
      v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1E2,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v10,
          dwFlags);
      v19 = -1;
      v11 = wil::impersonate_token_nothrow(a2);
      if ( v11 >= 0 )
      {
        v12 = pszKeyName;
        phKey = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &phKey,
          0);
        v13 = NCryptOpenKey(phProvider, &phKey, v12, 0, 0);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1EA,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
            (const char *)(unsigned int)v13,
            dwFlagsa);
        v14 = NCryptDeleteKey(phKey, 0);
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1EC,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
            (const char *)(unsigned int)v14,
            dwFlagsa);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1E5,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v11,
          dwFlags);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v19);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      v7 = 0;
    }
  }
  else
  {
    v7 = -2147024894;
    if ( v5 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v5,
        268435462);
      v7 = v6;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  return v7;
}

```

## disassembly

```asm
0x180043f84  mov     [rsp-18h+arg_8], rbx
0x180043f89  push    rbp
0x180043f8a  push    rsi
0x180043f8b  push    r14
0x180043f8d  mov     rbp, rsp
0x180043f90  sub     rsp, 60h
0x180043f94  mov     r14, rdx
0x180043f97  mov     [rbp+var_30], 0
0x180043f9f  mov     rbx, rcx
0x180043fa2  xor     edx, edx
0x180043fa4  lea     rcx, [rbp+var_30]
0x180043fa8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180043fad  lea     r9, [rbp+var_30]
0x180043fb1  mov     [rbp+phKey], rbx
0x180043fb5  lea     r8, aUvkeyid; "UvKeyId"
0x180043fbc  mov     [rsp+60h+dwFlags], 10000006h; int
0x180043fc4  lea     rcx, [rbp+phKey]
0x180043fc8  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x180043fcd  mov     esi, eax
0x180043fcf  test    eax, eax
0x180043fd1  jns     short loc_180043FFF
0x180043fd3  mov     ebx, 80070002h
0x180043fd8  cmp     eax, ebx
0x180043fda  jz      loc_1800441A1
0x180043fe0  mov     rcx, [rbp+18h]; this
0x180043fe4  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180043feb  mov     r9d, eax; char *
0x180043fee  mov     edx, 1D4h; void *
0x180043ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043ff8  mov     ebx, esi
0x180043ffa  jmp     loc_1800441A1
0x180043fff  lea     rdx, aUvkeyid; "UvKeyId"
0x180044006  mov     rcx, rbx; hKey
0x180044009  call    cs:__imp_RegDeleteValueW
0x18004400f  test    eax, eax
0x180044011  jz      short loc_180044032
0x180044013  mov     rcx, [rbp+18h]; this
0x180044017  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004401e  mov     r9d, eax; char *
0x180044021  mov     edx, 1D6h; void *
0x180044026  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004402b  mov     ebx, eax
0x18004402d  jmp     loc_1800441A1
0x180044032  lea     rax, aPluginuvkey; "PluginUvKey"
0x180044039  mov     [rbp+var_18], 0
0x180044041  mov     [rbp+var_20], rax
0x180044045  lea     rcx, [rbp+pszKeyName]
0x180044049  mov     rax, [rbp+var_30]
0x18004404d  xor     edx, edx
0x18004404f  mov     [rbp+var_10], rax
0x180044053  mov     [rbp+pszKeyName], 0
0x18004405b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180044060  lea     r8, [rbp+pszKeyName]
0x180044064  xor     edx, edx
0x180044066  lea     rcx, [rbp+var_20]
0x18004406a  call    cs:__imp_NgcGetUserIdKeyName
0x180044070  test    eax, eax
0x180044072  jns     short loc_18004408C
0x180044074  mov     rcx, [rbp+18h]; this
0x180044078  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004407f  mov     r9d, eax; char *
0x180044082  mov     edx, 1DFh; void *
0x180044087  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004408c  xor     edx, edx
0x18004408e  mov     [rbp+phProvider], 0
0x180044096  lea     rcx, [rbp+phProvider]
0x18004409a  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004409f  xor     r8d, r8d; dwFlags
0x1800440a2  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x1800440a9  lea     rcx, [rbp+phProvider]; phProvider
0x1800440ad  call    cs:__imp_NCryptOpenStorageProvider
0x1800440b3  test    eax, eax
0x1800440b5  jns     short loc_1800440CF
0x1800440b7  mov     rcx, [rbp+18h]; this
0x1800440bb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800440c2  mov     r9d, eax; char *
0x1800440c5  mov     edx, 1E2h; void *
0x1800440ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800440cf  lea     rdx, [rbp+var_28]
0x1800440d3  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x1800440db  mov     rcx, r14; Token
0x1800440de  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800440e3  test    eax, eax
0x1800440e5  jns     short loc_180044104
0x1800440e7  mov     rcx, [rbp+18h]; this
0x1800440eb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800440f2  mov     r9d, eax; char *
0x1800440f5  mov     edx, 1E5h; void *
0x1800440fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800440ff  jmp     loc_180044184
0x180044104  mov     rbx, [rbp+pszKeyName]
0x180044108  lea     rcx, [rbp+phKey]
0x18004410c  xor     edx, edx
0x18004410e  mov     [rbp+phKey], 0
0x180044116  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004411b  mov     rcx, [rbp+phProvider]; hProvider
0x18004411f  lea     rdx, [rbp+phKey]; phKey
0x180044123  xor     r9d, r9d; dwLegacyKeySpec
0x180044126  mov     [rsp+60h+dwFlags], 0; int
0x18004412e  mov     r8, rbx; pszKeyName
0x180044131  call    cs:__imp_NCryptOpenKey
0x180044137  test    eax, eax
0x180044139  jns     short loc_180044153
0x18004413b  mov     rcx, [rbp+18h]; this
0x18004413f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180044146  mov     r9d, eax; char *
0x180044149  mov     edx, 1EAh; void *
0x18004414e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044153  mov     rcx, [rbp+phKey]; hKey
0x180044157  xor     edx, edx; dwFlags
0x180044159  call    cs:__imp_NCryptDeleteKey
0x18004415f  test    eax, eax
0x180044161  jns     short loc_18004417B
0x180044163  mov     rcx, [rbp+18h]; this
0x180044167  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004416e  mov     r9d, eax; char *
0x180044171  mov     edx, 1ECh; void *
0x180044176  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004417b  lea     rcx, [rbp+phKey]
0x18004417f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180044184  lea     rcx, [rbp+var_28]
0x180044188  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18004418d  lea     rcx, [rbp+phProvider]
0x180044191  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180044196  lea     rcx, [rbp+pszKeyName]
0x18004419a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004419f  xor     ebx, ebx
0x1800441a1  lea     rcx, [rbp+var_30]
0x1800441a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800441aa  mov     eax, ebx
0x1800441ac  mov     rbx, [rsp+60h+arg_8]
0x1800441b4  add     rsp, 60h
0x1800441b8  pop     r14
0x1800441ba  pop     rsi
0x1800441bb  pop     rbp
0x1800441bc  retn
```

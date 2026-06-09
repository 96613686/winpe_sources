# CtapPluginDeleteUvKeyOld

- ea: `0x18004177c`
- end: `0x18004197f`
- name: `CtapPluginDeleteUvKeyOld`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043ad4`
- `0x180118b14`

## callees

- `0x180017764`
- `0x180017a88`
- `0x18001ee7c`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x180036da4`
- `0x18004177c`
- `0x180042ebc`
- `0x180043318`
- `0x1800467e0`
- `0x18005e500`
- `0x18006f750`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800418ef`
- `ncrypt!NCryptOpenKey` at `0x1800418ef`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004186e`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004186e`
- `ncrypt!NCryptDeleteKey` at `0x180041919`
- `ncrypt!NCryptDeleteKey` at `0x180041919`

## string_xrefs

- `0x1800417a6`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800417eb`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180041827`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180041882`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180041901`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x18004192b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CtapPluginDeleteUvKeyOld(__int64 a1, __int64 a2)
{
  const char *v4; // r9
  int UvKeyName; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  unsigned int v10; // ebx
  SECURITY_STATUS v11; // eax
  unsigned int v12; // ebx
  const WCHAR *v13; // rbx
  SECURITY_STATUS v14; // eax
  SECURITY_STATUS v15; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-28h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-28h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+30h] [rbp-18h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPCWSTR pszKeyName; // [rsp+60h] [rbp+18h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        v4);
    pszKeyName = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszKeyName,
      0);
    UvKeyName = PluginGetUvKeyName(a1, a2, &pszKeyName);
    v6 = UvKeyName;
    if ( UvKeyName >= 0 )
    {
      v9 = PluginDeleteUvKeyName(a1, a2);
      v10 = v9;
      if ( v9 >= 0 )
      {
        phProvider = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &phProvider,
          0);
        v11 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
        v12 = v11;
        if ( v11 >= 0 )
        {
          wil::impersonate_token(v19, a1);
          phKey = 0;
          v13 = pszKeyName;
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
            &phKey,
            0);
          v14 = NCryptOpenKey(phProvider, &phKey, v13, 0, 0);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x218,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
              (const char *)(unsigned int)v14,
              dwFlagsa);
          v15 = NCryptDeleteKey(phKey, 0);
          if ( v15 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x21A,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
              (const char *)(unsigned int)v15,
              dwFlagsa);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v19);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20F,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
            (const char *)(unsigned int)v11,
            dwFlags);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
          result = v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20C,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v9,
          dwFlags);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
        result = v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20A,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)UvKeyName,
        dwFlags);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x21E,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18004177c  mov     [rsp+arg_0], rbx
0x180041781  mov     [rsp+arg_8], rsi
0x180041786  push    rdi
0x180041787  sub     rsp, 40h
0x18004178b  mov     rsi, rdx
0x18004178e  mov     rdi, rcx
0x180041791  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180041798  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18004179d  mov     rcx, [rsp+48h]; this
0x1800417a2  test    al, al
0x1800417a4  jz      short loc_1800417B8
0x1800417a6  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800417ad  mov     edx, 207h; void *
0x1800417b2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800417b8  mov     [rsp+48h+pszKeyName], 0
0x1800417c1  xor     edx, edx
0x1800417c3  lea     rcx, [rsp+48h+pszKeyName]
0x1800417c8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800417cd  lea     r8, [rsp+48h+pszKeyName]
0x1800417d2  mov     rdx, rsi
0x1800417d5  mov     rcx, rdi
0x1800417d8  call    PluginGetUvKeyName
0x1800417dd  mov     ebx, eax
0x1800417df  test    eax, eax
0x1800417e1  jns     short loc_18004180E
0x1800417e3  mov     rcx, [rsp+48h]; this
0x1800417e8  mov     r9d, eax; char *
0x1800417eb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800417f2  mov     edx, 20Ah; void *
0x1800417f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800417fc  nop
0x1800417fd  lea     rcx, [rsp+48h+pszKeyName]
0x180041802  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180041807  mov     eax, ebx
0x180041809  jmp     loc_18004196E
0x18004180e  mov     rdx, rsi
0x180041811  mov     rcx, rdi
0x180041814  call    PluginDeleteUvKeyName
0x180041819  mov     ebx, eax
0x18004181b  test    eax, eax
0x18004181d  jns     short loc_18004184A
0x18004181f  mov     rcx, [rsp+48h]; this
0x180041824  mov     r9d, eax; char *
0x180041827  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004182e  mov     edx, 20Ch; void *
0x180041833  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041838  nop
0x180041839  lea     rcx, [rsp+48h+pszKeyName]
0x18004183e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180041843  mov     eax, ebx
0x180041845  jmp     loc_18004196E
0x18004184a  mov     [rsp+48h+phProvider], 0
0x180041853  xor     edx, edx
0x180041855  lea     rcx, [rsp+48h+phProvider]
0x18004185a  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004185f  xor     r8d, r8d; dwFlags
0x180041862  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180041869  lea     rcx, [rsp+48h+phProvider]; phProvider
0x18004186e  call    cs:__imp_NCryptOpenStorageProvider
0x180041874  mov     ebx, eax
0x180041876  test    eax, eax
0x180041878  jns     short loc_1800418B0
0x18004187a  mov     rcx, [rsp+48h]; this
0x18004187f  mov     r9d, eax; char *
0x180041882  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180041889  mov     edx, 20Fh; void *
0x18004188e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041893  nop
0x180041894  lea     rcx, [rsp+48h+phProvider]
0x180041899  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004189e  nop
0x18004189f  lea     rcx, [rsp+48h+pszKeyName]
0x1800418a4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800418a9  mov     eax, ebx
0x1800418ab  jmp     loc_18004196E
0x1800418b0  mov     rdx, rdi
0x1800418b3  lea     rcx, [rsp+48h+var_10]
0x1800418b8  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1800418bd  mov     [rsp+48h+phKey], 0
0x1800418c6  mov     rbx, [rsp+48h+pszKeyName]
0x1800418cb  xor     edx, edx
0x1800418cd  lea     rcx, [rsp+48h+phKey]
0x1800418d2  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800418d7  mov     [rsp+48h+dwFlags], 0; int
0x1800418df  xor     r9d, r9d; dwLegacyKeySpec
0x1800418e2  mov     r8, rbx; pszKeyName
0x1800418e5  lea     rdx, [rsp+48h+phKey]; phKey
0x1800418ea  mov     rcx, [rsp+48h+phProvider]; hProvider
0x1800418ef  call    cs:__imp_NCryptOpenKey
0x1800418f5  mov     rcx, [rsp+48h]; this
0x1800418fa  test    eax, eax
0x1800418fc  jns     short loc_180041912
0x1800418fe  mov     r9d, eax; char *
0x180041901  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180041908  mov     edx, 218h; void *
0x18004190d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041912  xor     edx, edx; dwFlags
0x180041914  mov     rcx, [rsp+48h+phKey]; hKey
0x180041919  call    cs:__imp_NCryptDeleteKey
0x18004191f  mov     rcx, [rsp+48h]; this
0x180041924  test    eax, eax
0x180041926  jns     short loc_18004193C
0x180041928  mov     r9d, eax; char *
0x18004192b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180041932  mov     edx, 21Ah; void *
0x180041937  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004193c  lea     rcx, [rsp+48h+phKey]
0x180041941  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180041946  lea     rcx, [rsp+48h+var_10]
0x18004194b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180041950  nop
0x180041951  lea     rcx, [rsp+48h+phProvider]
0x180041956  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004195b  nop
0x18004195c  lea     rcx, [rsp+48h+pszKeyName]
0x180041961  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180041966  xor     eax, eax
0x180041968  jmp     short loc_18004196E
0x18004196a  mov     eax, dword ptr [rsp+48h+pszKeyName]
0x18004196e  mov     rbx, [rsp+48h+arg_0]
0x180041973  mov     rsi, [rsp+48h+arg_8]
0x180041978  add     rsp, 40h
0x18004197c  pop     rdi
0x18004197d  retn
```

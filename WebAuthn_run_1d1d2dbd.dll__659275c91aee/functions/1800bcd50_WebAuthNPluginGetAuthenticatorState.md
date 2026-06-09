# WebAuthNPluginGetAuthenticatorState

- ea: `0x1800bcd50`
- end: `0x1800bd054`
- name: `WebAuthNPluginGetAuthenticatorState`
- size: `772`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180031708`
- `0x180036da4`
- `0x1800467e0`
- `0x18004685c`
- `0x1800537a4`
- `0x1800b31fc`
- `0x1800b73c4`
- `0x1800bc230`
- `0x1800bc390`
- `0x1800bcd50`
- `0x18013c090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bcebe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bcfc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bcebe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bcfc9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bcdd7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bcdd7`

## string_xrefs

- `0x1800bcda1`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bcdf1`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bce4f`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bcea0`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bcef7`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bcf2c`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bcf6b`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bcf9d`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd016`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall WebAuthNPluginGetAuthenticatorState(GUID *rguid, _DWORD *a2)
{
  int AuthenticatorList; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rbx
  __int64 i; // rdi
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rbx
  void *v14; // rcx
  void *v15[2]; // [rsp+20h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
  {
    if ( a2 )
    {
      memset_0(sz, 0, sizeof(sz));
      if ( StringFromGUID2(rguid, sz, 40) )
      {
        v15[0] = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        {
          wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::reset(
            v15,
            0);
          AuthenticatorList = WebAuthNPluginGetAuthenticatorList(0, v15);
          v6 = AuthenticatorList;
          if ( AuthenticatorList >= 0 )
          {
            v7 = v15[0];
            if ( v15[0] )
            {
              for ( i = 0; (unsigned int)i < *(_DWORD *)v7; i = (unsigned int)(i + 1) )
              {
                v9 = *(_QWORD *)(v7[1] + 8 * i);
                if ( v9 )
                {
                  if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v9 + 8), sz) )
                  {
                    _mm_lfence();
                    *a2 = *(_DWORD *)(*(_QWORD *)(v7[1] + 8 * i) + 32LL);
                    wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(v15);
                    return 0;
                  }
                }
                else
                {
                  wil::details::in1diag3::Log_Hr(
                    retaddr,
                    (void *)0x9C5,
                    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                    (const char *)0x8000FFFFLL,
                    (int)v15[0]);
                }
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9CF,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                (const char *)0x80090011LL,
                (int)v15[0]);
              wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(v15);
              return 2148073489LL;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9BE,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                (const char *)0x80090027LL,
                0);
              wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(v15);
              return 2148073511LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9BD,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)(unsigned int)AuthenticatorList,
              (int)v15[0]);
            wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(v15);
            return v6;
          }
        }
        else
        {
          v10 = WebAuthNPluginGetAuthenticatorList(0, v15);
          v11 = v10;
          if ( v10 >= 0 )
          {
            v12 = v15[0];
            if ( v15[0] )
            {
              v13 = 0;
              while ( (unsigned int)v13 < *(_DWORD *)v12 )
              {
                if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(*(_QWORD *)(v12[1] + 8 * v13) + 8LL), sz) )
                {
                  _mm_lfence();
                  v14 = v15[0];
                  *a2 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v15[0] + 1) + 8 * v13) + 32LL);
                  WebAuthNPluginFreeAuthenticatorList(v14);
                  return 0;
                }
                v13 = (unsigned int)(v13 + 1);
                v12 = v15[0];
              }
              WebAuthNPluginFreeAuthenticatorList(v12);
              return 2148073489LL;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9D5,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                (const char *)0x80090027LL,
                0);
              return 2148073511LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9D4,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)(unsigned int)v10,
              (int)v15[0]);
            return v11;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9B7,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          (int)v15[0]);
        return 2148073511LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B1,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090027LL,
        (int)v15[0]);
      return 2148073511LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B0,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      (int)v15[0]);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800bcd50  mov     [rsp+arg_10], rbx
0x1800bcd55  push    rsi
0x1800bcd56  push    rdi
0x1800bcd57  push    r14
0x1800bcd59  sub     rsp, 90h
0x1800bcd60  mov     rax, cs:__security_cookie
0x1800bcd67  xor     rax, rsp
0x1800bcd6a  mov     [rsp+0A8h+var_28], rax
0x1800bcd72  mov     rsi, rdx
0x1800bcd75  mov     rbx, rcx
0x1800bcd78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bcd7f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bcd84  test    al, al
0x1800bcd86  jz      loc_1800BD006
0x1800bcd8c  test    rsi, rsi
0x1800bcd8f  jnz     short loc_1800BCDB9
0x1800bcd91  mov     rcx, [rsp+0A8h]; this
0x1800bcd99  mov     ebx, 80090027h
0x1800bcd9e  mov     r9d, ebx; char *
0x1800bcda1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bcda8  mov     edx, 9B1h; void *
0x1800bcdad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcdb2  mov     eax, ebx
0x1800bcdb4  jmp     loc_1800BD02F
0x1800bcdb9  xor     edx, edx; Val
0x1800bcdbb  lea     r8d, [rdx+50h]; Size
0x1800bcdbf  lea     rcx, [rsp+0A8h+sz]; void *
0x1800bcdc4  call    memset_0
0x1800bcdc9  mov     r8d, 28h ; '('; cchMax
0x1800bcdcf  lea     rdx, [rsp+0A8h+sz]; lpsz
0x1800bcdd4  mov     rcx, rbx; rguid
0x1800bcdd7  call    cs:__imp_StringFromGUID2
0x1800bcddd  test    eax, eax
0x1800bcddf  jnz     short loc_1800BCE09
0x1800bcde1  mov     rcx, [rsp+0A8h]; this
0x1800bcde9  mov     ebx, 80090027h
0x1800bcdee  mov     r9d, ebx; char *
0x1800bcdf1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bcdf8  mov     edx, 9B7h; void *
0x1800bcdfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bce02  mov     eax, ebx
0x1800bce04  jmp     loc_1800BD02F
0x1800bce09  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bce10  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bce15  mov     [rsp+0A8h+var_88], 0; int
0x1800bce1e  test    al, al
0x1800bce20  jz      loc_1800BCF4E
0x1800bce26  xor     edx, edx
0x1800bce28  lea     rcx, [rsp+0A8h+var_88]
0x1800bce2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@P6AXPEAU1@@Z$1?WebAuthNPluginFreeAuthenticatorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@@Z; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::reset(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *)
0x1800bce32  lea     rdx, [rsp+0A8h+var_88]
0x1800bce37  xor     ecx, ecx
0x1800bce39  call    WebAuthNPluginGetAuthenticatorList
0x1800bce3e  mov     ebx, eax
0x1800bce40  test    eax, eax
0x1800bce42  jns     short loc_1800BCE71
0x1800bce44  mov     rcx, [rsp+0A8h]; this
0x1800bce4c  mov     r9d, eax; char *
0x1800bce4f  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bce56  mov     edx, 9BDh; void *
0x1800bce5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bce60  lea     rcx, [rsp+0A8h+var_88]
0x1800bce65  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@P6AXPEAU1@@Z$1?WebAuthNPluginFreeAuthenticatorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(void)
0x1800bce6a  mov     eax, ebx
0x1800bce6c  jmp     loc_1800BD02F
0x1800bce71  mov     rbx, [rsp+0A8h+var_88]
0x1800bce76  test    rbx, rbx
0x1800bce79  jz      loc_1800BCF1C
0x1800bce7f  xor     edi, edi
0x1800bce81  cmp     edi, [rbx]
0x1800bce83  jnb     short loc_1800BCEE9
0x1800bce85  mov     rax, [rbx+8]
0x1800bce89  mov     rcx, [rax+rdi*8]
0x1800bce8d  test    rcx, rcx
0x1800bce90  jnz     short loc_1800BCEB5
0x1800bce92  mov     rcx, [rsp+0A8h]; this
0x1800bce9a  mov     r9d, 8000FFFFh; char *
0x1800bcea0  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bcea7  mov     edx, 9C5h; void *
0x1800bceac  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800bceb1  inc     edi
0x1800bceb3  jmp     short loc_1800BCE81
0x1800bceb5  lea     rdx, [rsp+0A8h+sz]
0x1800bceba  mov     rcx, [rcx+8]
0x1800bcebe  call    cs:__imp__o__wcsicmp
0x1800bcec4  test    eax, eax
0x1800bcec6  jnz     short loc_1800BCEB1
0x1800bcec8  lfence
0x1800bcecb  mov     rax, [rbx+8]
0x1800bcecf  mov     rcx, [rax+rdi*8]
0x1800bced3  mov     eax, [rcx+20h]
0x1800bced6  mov     [rsi], eax
0x1800bced8  lea     rcx, [rsp+0A8h+var_88]
0x1800bcedd  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@P6AXPEAU1@@Z$1?WebAuthNPluginFreeAuthenticatorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(void)
0x1800bcee2  xor     eax, eax
0x1800bcee4  jmp     loc_1800BD02F
0x1800bcee9  mov     rcx, [rsp+0A8h]; this
0x1800bcef1  mov     r9d, 80090011h; char *
0x1800bcef7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bcefe  mov     edx, 9CFh; void *
0x1800bcf03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcf08  lea     rcx, [rsp+0A8h+var_88]
0x1800bcf0d  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@P6AXPEAU1@@Z$1?WebAuthNPluginFreeAuthenticatorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(void)
0x1800bcf12  mov     eax, 80090011h
0x1800bcf17  jmp     loc_1800BD02F
0x1800bcf1c  mov     rcx, [rsp+0A8h]; this
0x1800bcf24  mov     ebx, 80090027h
0x1800bcf29  mov     r9d, ebx; char *
0x1800bcf2c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bcf33  mov     edx, 9BEh; void *
0x1800bcf38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcf3d  lea     rcx, [rsp+0A8h+var_88]
0x1800bcf42  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@P6AXPEAU1@@Z$1?WebAuthNPluginFreeAuthenticatorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(void)
0x1800bcf47  mov     eax, ebx
0x1800bcf49  jmp     loc_1800BD02F
0x1800bcf4e  lea     rdx, [rsp+0A8h+var_88]
0x1800bcf53  xor     ecx, ecx
0x1800bcf55  call    WebAuthNPluginGetAuthenticatorList
0x1800bcf5a  mov     ebx, eax
0x1800bcf5c  test    eax, eax
0x1800bcf5e  jns     short loc_1800BCF83
0x1800bcf60  mov     rcx, [rsp+0A8h]; this
0x1800bcf68  mov     r9d, eax; char *
0x1800bcf6b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bcf72  mov     edx, 9D4h; void *
0x1800bcf77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcf7c  mov     eax, ebx
0x1800bcf7e  jmp     loc_1800BD02F
0x1800bcf83  mov     rcx, [rsp+0A8h+var_88]; void *
0x1800bcf88  test    rcx, rcx
0x1800bcf8b  jnz     short loc_1800BCFB2
0x1800bcf8d  mov     rcx, [rsp+0A8h]; this
0x1800bcf95  mov     ebx, 80090027h
0x1800bcf9a  mov     r9d, ebx; char *
0x1800bcf9d  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bcfa4  mov     edx, 9D5h; void *
0x1800bcfa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcfae  mov     eax, ebx
0x1800bcfb0  jmp     short loc_1800BD02F
0x1800bcfb2  xor     ebx, ebx
0x1800bcfb4  cmp     ebx, [rcx]
0x1800bcfb6  jnb     short loc_1800BCFFA
0x1800bcfb8  mov     rax, [rcx+8]
0x1800bcfbc  mov     rcx, [rax+rbx*8]
0x1800bcfc0  lea     rdx, [rsp+0A8h+sz]
0x1800bcfc5  mov     rcx, [rcx+8]
0x1800bcfc9  call    cs:__imp__o__wcsicmp
0x1800bcfcf  test    eax, eax
0x1800bcfd1  jnz     short loc_1800BCFF1
0x1800bcfd3  lfence
0x1800bcfd6  mov     rcx, [rsp+0A8h+var_88]; void *
0x1800bcfdb  mov     rax, [rcx+8]
0x1800bcfdf  mov     rdx, [rax+rbx*8]
0x1800bcfe3  mov     eax, [rdx+20h]
0x1800bcfe6  mov     [rsi], eax
0x1800bcfe8  call    WebAuthNPluginFreeAuthenticatorList
0x1800bcfed  xor     eax, eax
0x1800bcfef  jmp     short loc_1800BD02F
0x1800bcff1  inc     ebx
0x1800bcff3  mov     rcx, [rsp+0A8h+var_88]
0x1800bcff8  jmp     short loc_1800BCFB4
0x1800bcffa  call    WebAuthNPluginFreeAuthenticatorList
0x1800bcfff  mov     eax, 80090011h
0x1800bd004  jmp     short loc_1800BD02F
0x1800bd006  mov     rcx, [rsp+0A8h]; this
0x1800bd00e  mov     ebx, 80004001h
0x1800bd013  mov     r9d, ebx; char *
0x1800bd016  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd01d  mov     edx, 9B0h; void *
0x1800bd022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd027  mov     eax, ebx
0x1800bd029  jmp     short loc_1800BD02F
0x1800bd02b  mov     eax, dword ptr [rsp+0A8h+var_88]
0x1800bd02f  mov     rcx, [rsp+0A8h+var_28]
0x1800bd037  xor     rcx, rsp; StackCookie
0x1800bd03a  call    __security_check_cookie
0x1800bd03f  mov     rbx, [rsp+0A8h+arg_10]
0x1800bd047  add     rsp, 90h
0x1800bd04e  pop     r14
0x1800bd050  pop     rdi
0x1800bd051  pop     rsi
0x1800bd052  retn
```

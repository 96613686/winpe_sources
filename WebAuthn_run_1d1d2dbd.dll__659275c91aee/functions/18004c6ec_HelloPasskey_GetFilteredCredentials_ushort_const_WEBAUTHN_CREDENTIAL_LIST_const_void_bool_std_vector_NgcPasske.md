# HelloPasskey::GetFilteredCredentials(ushort const *,_WEBAUTHN_CREDENTIAL_LIST const *,void *,bool,std::vector<NgcPasskeys::WebAuthnAccountCredential,std::allocator<NgcPasskeys::WebAuthnAccountCredential>> &)

- ea: `0x18004c6ec`
- end: `0x18004cae3`
- name: `?GetFilteredCredentials@HelloPasskey@@YAJPEBGPEBU_WEBAUTHN_CREDENTIAL_LIST@@PEAX_NAEAV?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@@Z`
- size: `1015`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003298c`
- `0x1800350f4`

## callees

- `0x18001687c`
- `0x18001cd78`
- `0x18001ee7c`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x1800350b4`
- `0x180036448`
- `0x180036da4`
- `0x180047464`
- `0x18004c6ec`
- `0x180062fcc`
- `0x18006f750`
- `0x18007d208`
- `0x18007d244`
- `0x18007d3a4`
- `0x18007d7c4`
- `0x18007da80`
- `0x1800c69f8`
- `0x180134b18`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004caae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004caae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca98`
- `ncrypt!NCryptFinalizeKey` at `0x18004c81e`
- `ncrypt!NCryptFinalizeKey` at `0x18004c81e`
- `ncrypt!NCryptCreatePersistedKey` at `0x18004c7b8`
- `ncrypt!NCryptCreatePersistedKey` at `0x18004c7b8`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004c76b`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004c76b`
- `ncrypt!NCryptSetProperty` at `0x18004c7f7`
- `ncrypt!NCryptSetProperty` at `0x18004c7f7`
- `ncrypt!NCryptDeleteKey` at `0x18004c859`
- `ncrypt!NCryptDeleteKey` at `0x18004c859`

## string_xrefs

- `0x18004c7ec`: `NgcCacheType`
- `0x18004c73b`: `onecore\ds\security\fido\webauthn\dll\webauthnpasskeys.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall HelloPasskey::GetFilteredCredentials(
        __int64 a1,
        struct _WEBAUTHN_CREDENTIAL_LIST *a2,
        __int64 a3,
        char a4,
        __int64 *a5)
{
  __int64 *v9; // rbx
  SECURITY_STATUS v10; // eax
  SECURITY_STATUS v11; // eax
  SECURITY_STATUS v12; // eax
  const char *v13; // rdi
  SECURITY_STATUS v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  signed int v17; // edi
  HLOCAL v18; // rcx
  bool v19; // zf
  __int64 *v21; // rdi
  __int64 v22; // rax
  void *v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // r14
  __int64 *v26; // rdi
  void *v27; // rcx
  HLOCAL v28; // rcx
  int dwLegacyKeySpec; // [rsp+20h] [rbp-A1h]
  int dwLegacyKeySpeca; // [rsp+20h] [rbp-A1h]
  int dwLegacyKeySpecb; // [rsp+20h] [rbp-A1h]
  HLOCAL hMem; // [rsp+40h] [rbp-81h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-79h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-71h] BYREF
  __int64 *v35; // [rsp+58h] [rbp-69h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp-61h] BYREF
  int v37[2]; // [rsp+68h] [rbp-59h] BYREF
  char v38; // [rsp+70h] [rbp-51h]
  unsigned int v39; // [rsp+80h] [rbp-41h]
  _BYTE v40[8]; // [rsp+88h] [rbp-39h] BYREF
  _BYTE v41[8]; // [rsp+90h] [rbp-31h] BYREF
  __int64 v42; // [rsp+98h] [rbp-29h] BYREF
  __int128 v43; // [rsp+A0h] [rbp-21h]
  _QWORD v44[12]; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]
  unsigned int pbInput; // [rsp+138h] [rbp+77h] BYREF

  winrt::create_instance<ISyncedPasskeyAuthenticator>(&v35, &winrt::impl::guid_v<SyncedPasskeyAuthenticator>);
  v9 = v35;
  WebAuthNCom::AllowImpersonationCom(v35);
  wil::impersonate_token(v40, a3);
  if ( a4 )
  {
    phProvider = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phProvider,
      0);
    v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
        (const char *)(unsigned int)v10,
        dwLegacyKeySpec);
    phKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phKey,
      0);
    v11 = NCryptCreatePersistedKey(phProvider, &phKey, L"ECDSA_P256", L"//NgcPasskey//DummyKey", 0, 0);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
        (const char *)(unsigned int)v11,
        dwLegacyKeySpeca);
    pbInput = 2;
    v12 = NCryptSetProperty(phKey, L"NgcCacheType", (PBYTE)&pbInput, 4u, 0);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
        (const char *)(unsigned int)v12,
        dwLegacyKeySpecb);
    v13 = (const char *)(unsigned int)NCryptFinalizeKey(phKey, 0x40u);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
      v13,
      1,
      0x80090022);
    if ( (int)v13 < 0 )
    {
      if ( (_DWORD)v13 == -2146893790 )
      {
        v21 = a5;
        if ( *a5 != a5[1] )
        {
          std::_Destroy_range<std::allocator<NgcPasskeys::WebAuthnAccountCredential>>((NgcPasskeys::WebAuthnAccountCredential *)*a5);
          v21[1] = *v21;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v40);
        if ( v9 )
          winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v35);
        return 2148073506LL;
      }
    }
    else
    {
      v14 = NCryptDeleteKey(phKey, 0);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
          (const char *)(unsigned int)v14,
          dwLegacyKeySpec);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  }
  hMem = 0;
  pbInput = 0;
  phProvider = (NCRYPT_PROV_HANDLE)&hMem;
  *(_QWORD *)v37 = 0;
  v38 = 1;
  v15 = CtapCborEncodeCredentialList(a2);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&phProvider);
  if ( v15 )
  {
    v16 = CtapCborErrorToWin32Error(v15);
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( v17 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
        (const char *)(unsigned int)v17,
        dwLegacyKeySpec);
LABEL_17:
    v18 = hMem;
    v19 = hMem == 0;
    hMem = 0;
    if ( !v19 )
      LocalFree(v18);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v40);
    if ( v9 )
      winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v35);
    return (unsigned int)v17;
  }
  pv = 0;
  v39 = 0;
  v22 = *v9;
  phProvider = (NCRYPT_PROV_HANDLE)&pv;
  *(_QWORD *)v37 = 0;
  v38 = 1;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, HLOCAL, _QWORD))(v22 + 56))(v9, a1, hMem, pbInput);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&phProvider);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
      (const char *)(unsigned int)v17,
      (int)v37);
    v23 = pv;
    pv = 0;
    if ( v23 )
      CoTaskMemFree(v23);
    goto LABEL_17;
  }
  std::vector<unsigned char>::vector<unsigned char>(v44, pv, (char *)pv + v39);
  phProvider = v44[0];
  *(_QWORD *)v37 = v44[1] - v44[0];
  NgcPasskeys::WebAuthnAccountCredentialList::FromCbor(v41, &phProvider);
  v24 = v43;
  v25 = v42;
  if ( v42 != (_QWORD)v43 )
  {
    v26 = a5;
    if ( a5 != &v42 )
    {
      std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(a5);
      *v26 = v25;
      v26[1] = v24;
      v26[2] = *((_QWORD *)&v43 + 1);
      v42 = 0;
      v43 = 0;
    }
  }
  std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(&v42);
  std::vector<unsigned char>::_Tidy(v44);
  v27 = pv;
  v19 = pv == 0;
  pv = 0;
  if ( !v19 )
    CoTaskMemFree(v27);
  v28 = hMem;
  v19 = hMem == 0;
  hMem = 0;
  if ( !v19 )
    LocalFree(v28);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v40);
  if ( v9 )
    winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v35);
  return 0;
}

```

## disassembly

```asm
0x18004c6ec  push    rbp
0x18004c6ee  push    rbx
0x18004c6ef  push    rsi
0x18004c6f0  push    rdi
0x18004c6f1  push    r12
0x18004c6f3  push    r13
0x18004c6f5  push    r14
0x18004c6f7  push    r15
0x18004c6f9  lea     rbp, [rsp-17h]
0x18004c6fe  sub     rsp, 0D8h
0x18004c705  mov     sil, r9b
0x18004c708  mov     rdi, r8
0x18004c70b  mov     r14, rdx
0x18004c70e  mov     r15, rcx
0x18004c711  lea     rdx, ??$guid_v@VSyncedPasskeyAuthenticator@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<SyncedPasskeyAuthenticator>
0x18004c718  lea     rcx, [rbp+4Fh+var_B8]
0x18004c71c  call    ??$create_instance@UISyncedPasskeyAuthenticator@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x18004c721  nop
0x18004c722  mov     rbx, [rbp+4Fh+var_B8]
0x18004c726  mov     rcx, rbx
0x18004c729  call    WebAuthNCom__AllowImpersonationCom
0x18004c72e  mov     rdx, rdi
0x18004c731  lea     rcx, [rbp+4Fh+var_88]
0x18004c735  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18004c73a  nop
0x18004c73b  lea     r13, aOnecoreDsSecur_13; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004c742  xor     r12d, r12d
0x18004c745  test    sil, sil
0x18004c748  jz      loc_18004C889
0x18004c74e  mov     [rbp+4Fh+phProvider], r12
0x18004c752  xor     edx, edx
0x18004c754  lea     rcx, [rbp+4Fh+phProvider]
0x18004c758  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004c75d  xor     r8d, r8d; dwFlags
0x18004c760  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18004c767  lea     rcx, [rbp+4Fh+phProvider]; phProvider
0x18004c76b  call    cs:__imp_NCryptOpenStorageProvider
0x18004c771  mov     rcx, [rbp+57h]; this
0x18004c775  test    eax, eax
0x18004c777  jns     short loc_18004C789
0x18004c779  mov     r9d, eax; char *
0x18004c77c  mov     r8, r13; unsigned int
0x18004c77f  mov     edx, 0A1h; void *
0x18004c784  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c789  mov     [rbp+4Fh+phKey], r12
0x18004c78d  xor     edx, edx
0x18004c78f  lea     rcx, [rbp+4Fh+phKey]
0x18004c793  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004c798  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x18004c79d  mov     [rsp+110h+dwLegacyKeySpec], r12d; int
0x18004c7a2  lea     r9, pszKeyName; "//NgcPasskey//DummyKey"
0x18004c7a9  lea     r8, pszAlgId; "ECDSA_P256"
0x18004c7b0  lea     rdx, [rbp+4Fh+phKey]; phKey
0x18004c7b4  mov     rcx, [rbp+4Fh+phProvider]; hProvider
0x18004c7b8  call    cs:__imp_NCryptCreatePersistedKey
0x18004c7be  mov     rcx, [rbp+57h]; this
0x18004c7c2  test    eax, eax
0x18004c7c4  jns     short loc_18004C7D6
0x18004c7c6  mov     r9d, eax; char *
0x18004c7c9  mov     r8, r13; unsigned int
0x18004c7cc  mov     edx, 0A3h; void *
0x18004c7d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c7d6  mov     [rbp+4Fh+pbInput], 2
0x18004c7dd  mov     [rsp+110h+dwLegacyKeySpec], r12d; int
0x18004c7e2  mov     r9d, 4; cbInput
0x18004c7e8  lea     r8, [rbp+4Fh+pbInput]; pbInput
0x18004c7ec  lea     rdx, aNgccachetype; "NgcCacheType"
0x18004c7f3  mov     rcx, [rbp+4Fh+phKey]; hObject
0x18004c7f7  call    cs:__imp_NCryptSetProperty
0x18004c7fd  mov     rcx, [rbp+57h]; this
0x18004c801  test    eax, eax
0x18004c803  jns     short loc_18004C815
0x18004c805  mov     r9d, eax; char *
0x18004c808  mov     r8, r13; unsigned int
0x18004c80b  mov     edx, 0A5h; void *
0x18004c810  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c815  mov     edx, 40h ; '@'; dwFlags
0x18004c81a  mov     rcx, [rbp+4Fh+phKey]; hKey
0x18004c81e  call    cs:__imp_NCryptFinalizeKey
0x18004c824  mov     edi, eax
0x18004c826  mov     rcx, [rbp+57h]; this
0x18004c82a  mov     esi, 80090022h
0x18004c82f  mov     [rsp+110h+dwFlags], esi; unsigned int
0x18004c833  mov     [rsp+110h+dwLegacyKeySpec], 1; int
0x18004c83b  mov     r9d, eax; char *
0x18004c83e  mov     r8, r13; unsigned int
0x18004c841  mov     edx, 0A7h; void *
0x18004c846  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18004c84b  test    edi, edi
0x18004c84d  js      loc_18004C92A
0x18004c853  xor     edx, edx; dwFlags
0x18004c855  mov     rcx, [rbp+4Fh+phKey]; hKey
0x18004c859  call    cs:__imp_NCryptDeleteKey
0x18004c85f  mov     rcx, [rbp+57h]; this
0x18004c863  test    eax, eax
0x18004c865  jns     short loc_18004C877
0x18004c867  mov     r9d, eax; char *
0x18004c86a  mov     r8, r13; unsigned int
0x18004c86d  mov     edx, 0AAh; void *
0x18004c872  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c877  lea     rcx, [rbp+4Fh+phKey]
0x18004c87b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004c880  lea     rcx, [rbp+4Fh+phProvider]
0x18004c884  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004c889  mov     [rsp+110h+hMem], r12
0x18004c88e  mov     [rbp+4Fh+pbInput], r12d
0x18004c892  lea     rax, [rsp+110h+hMem]
0x18004c897  mov     [rbp+4Fh+phProvider], rax
0x18004c89b  mov     qword ptr [rbp+4Fh+var_A8], r12
0x18004c89f  mov     [rbp+4Fh+var_A0], 1
0x18004c8a3  lea     r8, [rbp+4Fh+var_A8]
0x18004c8a7  lea     rdx, [rbp+4Fh+pbInput]
0x18004c8ab  mov     rcx, r14; struct _WEBAUTHN_CREDENTIAL_LIST *
0x18004c8ae  call    CtapCborEncodeCredentialList
0x18004c8b3  mov     edi, eax
0x18004c8b5  lea     rcx, [rbp+4Fh+phProvider]
0x18004c8b9  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004c8be  test    edi, edi
0x18004c8c0  jz      loc_18004C980
0x18004c8c6  mov     ecx, edi
0x18004c8c8  call    CtapCborErrorToWin32Error
0x18004c8cd  mov     edi, eax
0x18004c8cf  test    eax, eax
0x18004c8d1  jle     short loc_18004C8DC
0x18004c8d3  movzx   edi, ax
0x18004c8d6  or      edi, 80070000h
0x18004c8dc  test    edi, edi
0x18004c8de  jns     short loc_18004C8F5
0x18004c8e0  mov     rcx, [rbp+57h]; this
0x18004c8e4  mov     r9d, edi; char *
0x18004c8e7  mov     r8, r13; unsigned int
0x18004c8ea  mov     edx, 0B7h; void *
0x18004c8ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c8f4  nop
0x18004c8f5  mov     rcx, [rsp+110h+hMem]; hMem
0x18004c8fa  test    rcx, rcx
0x18004c8fd  mov     [rsp+110h+hMem], r12
0x18004c902  jz      short loc_18004C90B
0x18004c904  call    cs:__imp_LocalFree
0x18004c90a  nop
0x18004c90b  lea     rcx, [rbp+4Fh+var_88]
0x18004c90f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18004c914  nop
0x18004c915  test    rbx, rbx
0x18004c918  jz      short loc_18004C923
0x18004c91a  lea     rcx, [rbp+4Fh+var_B8]
0x18004c91e  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x18004c923  mov     eax, edi
0x18004c925  jmp     loc_18004CACF
0x18004c92a  cmp     edi, esi
0x18004c92c  jnz     loc_18004C877
0x18004c932  mov     rdi, [rbp+4Fh+arg_20]
0x18004c936  mov     rdx, [rdi+8]
0x18004c93a  cmp     [rdi], rdx
0x18004c93d  jz      short loc_18004C94E
0x18004c93f  mov     rcx, [rdi]; this
0x18004c942  call    ??$_Destroy_range@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@YAXPEAUWebAuthnAccountCredential@NgcPasskeys@@QEAU12@AEAV?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@0@@Z; std::_Destroy_range<std::allocator<NgcPasskeys::WebAuthnAccountCredential>>(NgcPasskeys::WebAuthnAccountCredential *,NgcPasskeys::WebAuthnAccountCredential * const,std::allocator<NgcPasskeys::WebAuthnAccountCredential> &)
0x18004c947  mov     rax, [rdi]
0x18004c94a  mov     [rdi+8], rax
0x18004c94e  lea     rcx, [rbp+4Fh+phKey]
0x18004c952  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004c957  lea     rcx, [rbp+4Fh+phProvider]
0x18004c95b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004c960  nop
0x18004c961  lea     rcx, [rbp+4Fh+var_88]
0x18004c965  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18004c96a  nop
0x18004c96b  test    rbx, rbx
0x18004c96e  jz      short loc_18004C979
0x18004c970  lea     rcx, [rbp+4Fh+var_B8]
0x18004c974  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x18004c979  mov     eax, esi
0x18004c97b  jmp     loc_18004CACF
0x18004c980  mov     [rbp+4Fh+pv], r12
0x18004c984  mov     [rbp+4Fh+var_90], r12d
0x18004c988  mov     rax, [rbx]
0x18004c98b  lea     rcx, [rbp+4Fh+pv]
0x18004c98f  mov     [rbp+4Fh+phProvider], rcx
0x18004c993  mov     qword ptr [rbp+4Fh+var_A8], r12
0x18004c997  mov     [rbp+4Fh+var_A0], 1
0x18004c99b  lea     rcx, [rbp+4Fh+var_90]
0x18004c99f  mov     qword ptr [rsp+110h+dwFlags], rcx
0x18004c9a4  lea     rcx, [rbp+4Fh+var_A8]
0x18004c9a8  mov     qword ptr [rsp+110h+dwLegacyKeySpec], rcx; int
0x18004c9ad  mov     r9d, [rbp+4Fh+pbInput]
0x18004c9b1  mov     r8, [rsp+110h+hMem]
0x18004c9b6  mov     rdx, r15
0x18004c9b9  mov     rcx, rbx
0x18004c9bc  mov     rax, [rax+38h]
0x18004c9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9c5  mov     edi, eax
0x18004c9c7  lea     rcx, [rbp+4Fh+phProvider]
0x18004c9cb  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18004c9d0  test    edi, edi
0x18004c9d2  jns     short loc_18004CA05
0x18004c9d4  mov     rcx, [rbp+57h]; this
0x18004c9d8  mov     r9d, edi; char *
0x18004c9db  mov     r8, r13; unsigned int
0x18004c9de  mov     edx, 0BCh; void *
0x18004c9e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c9e8  nop
0x18004c9e9  mov     rcx, [rbp+4Fh+pv]; pv
0x18004c9ed  mov     [rbp+4Fh+pv], r12
0x18004c9f1  test    rcx, rcx
0x18004c9f4  jz      loc_18004C8F5
0x18004c9fa  call    cs:__imp_CoTaskMemFree
0x18004ca00  jmp     loc_18004C8F5
0x18004ca05  mov     r8d, [rbp+4Fh+var_90]
0x18004ca09  mov     rdx, [rbp+4Fh+pv]
0x18004ca0d  add     r8, rdx
0x18004ca10  lea     rcx, [rbp+4Fh+var_60]
0x18004ca14  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18004ca19  nop
0x18004ca1a  mov     rcx, [rbp+4Fh+var_60]
0x18004ca1e  mov     [rbp+4Fh+phProvider], rcx
0x18004ca22  mov     rax, [rbp+4Fh+var_58]
0x18004ca26  sub     rax, rcx
0x18004ca29  mov     qword ptr [rbp+4Fh+var_A8], rax
0x18004ca2d  lea     rdx, [rbp+4Fh+phProvider]
0x18004ca31  lea     rcx, [rbp+4Fh+var_80]
0x18004ca35  call    ?FromCbor@WebAuthnAccountCredentialList@NgcPasskeys@@SA?AU12@V?$span@$$CBE$0?0@std@@@Z; NgcPasskeys::WebAuthnAccountCredentialList::FromCbor(std::span<uchar const,-1>)
0x18004ca3a  mov     rsi, qword ptr [rbp+4Fh+var_70]
0x18004ca3e  mov     r14, [rbp+4Fh+var_78]
0x18004ca42  cmp     r14, rsi
0x18004ca45  jz      short loc_18004CA77
0x18004ca47  lea     rax, [rbp+4Fh+var_78]
0x18004ca4b  mov     rdi, [rbp+4Fh+arg_20]
0x18004ca4f  cmp     rdi, rax
0x18004ca52  jz      short loc_18004CA77
0x18004ca54  mov     rcx, rdi
0x18004ca57  call    ?_Tidy@?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@AEAAXXZ; std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(void)
0x18004ca5c  mov     [rdi], r14
0x18004ca5f  mov     [rdi+8], rsi
0x18004ca63  mov     rax, qword ptr [rbp+4Fh+var_70+8]
0x18004ca67  mov     [rdi+10h], rax
0x18004ca6b  mov     [rbp+4Fh+var_78], r12
0x18004ca6f  xorps   xmm0, xmm0
0x18004ca72  movdqu  [rbp+4Fh+var_70], xmm0
0x18004ca77  lea     rcx, [rbp+4Fh+var_78]
0x18004ca7b  call    ?_Tidy@?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@AEAAXXZ; std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(void)
0x18004ca80  nop
0x18004ca81  lea     rcx, [rbp+4Fh+var_60]
0x18004ca85  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004ca8a  nop
0x18004ca8b  mov     rcx, [rbp+4Fh+pv]; pv
0x18004ca8f  test    rcx, rcx
0x18004ca92  mov     [rbp+4Fh+pv], r12
0x18004ca96  jz      short loc_18004CA9F
0x18004ca98  call    cs:__imp_CoTaskMemFree
0x18004ca9e  nop
0x18004ca9f  mov     rcx, [rsp+110h+hMem]; hMem
0x18004caa4  test    rcx, rcx
0x18004caa7  mov     [rsp+110h+hMem], r12
0x18004caac  jz      short loc_18004CAB5
0x18004caae  call    cs:__imp_LocalFree
0x18004cab4  nop
0x18004cab5  lea     rcx, [rbp+4Fh+var_88]
0x18004cab9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18004cabe  nop
0x18004cabf  test    rbx, rbx
0x18004cac2  jz      short loc_18004CACD
0x18004cac4  lea     rcx, [rbp+4Fh+var_B8]
0x18004cac8  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x18004cacd  xor     eax, eax
0x18004cacf  add     rsp, 0D8h
0x18004cad6  pop     r15
0x18004cad8  pop     r14
0x18004cada  pop     r13
0x18004cadc  pop     r12
0x18004cade  pop     rdi
0x18004cadf  pop     rsi
0x18004cae0  pop     rbx
0x18004cae1  pop     rbp
0x18004cae2  retn
```

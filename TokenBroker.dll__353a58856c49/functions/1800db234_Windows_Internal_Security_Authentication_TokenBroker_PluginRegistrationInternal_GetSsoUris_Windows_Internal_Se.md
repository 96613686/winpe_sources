# Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetSsoUris(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Foundation::Collections::IVectorView<Windows::Foundation::Uri *> * *)

- ea: `0x1800db234`
- end: `0x1800db394`
- name: `?GetSsoUris@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAU?$IVectorView@PEAVUri@Foundation@Windows@@@Collections@Foundation@6@@Z`
- size: `352`
- prototype: `__int64 __fastcall(struct Windows::Internal::Security::Authentication::Web::CallerContext *this, struct Windows::Security::Credentials::IWebAccountProvider *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012b80`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800228e0`
- `0x180031cf8`
- `0x18004fdbc`
- `0x1800db234`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db2c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db2d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db2e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db2c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db2d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db2e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db383`

## string_xrefs

- `0x1800db2a6`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`
- `0x1800db340`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetSsoUris(
        struct Windows::Internal::Security::Authentication::Web::CallerContext *this,
        __int64 (__fastcall ***a2)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        __int64 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  HSTRING v9; // rbx
  int v10; // edi
  __int64 v11; // rdx
  HSTRING v12; // [rsp+20h] [rbp-28h] BYREF
  HSTRING v13; // [rsp+28h] [rbp-20h] BYREF
  HSTRING string; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v16; // [rsp+88h] [rbp+40h] BYREF

  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      byte_18015119B,
      0,
      0);
  v13 = 0;
  v12 = 0;
  string = 0;
  v6 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
         a2,
         &v13,
         &v12,
         &string);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
      (const char *)(unsigned int)v6,
      (int)v12);
    if ( string )
      WindowsDeleteString(string);
    if ( v12 )
      WindowsDeleteString(v12);
    if ( v13 )
      WindowsDeleteString(v13);
    return v7;
  }
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  v9 = string;
  v10 = Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(
          string,
          this,
          &v16);
  if ( v10 < 0 )
  {
    v11 = 494;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
      (const char *)(unsigned int)v10,
      (int)v12);
    goto LABEL_16;
  }
  v10 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, __int64))(*(_QWORD *)v16 + 104LL))(
          v16,
          a3);
  if ( v10 < 0 )
  {
    v11 = 496;
    goto LABEL_15;
  }
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  if ( v9 )
    WindowsDeleteString(v9);
  if ( v12 )
    WindowsDeleteString(v12);
  if ( v13 )
    WindowsDeleteString(v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800db234  push    rbp
0x1800db236  push    rbx
0x1800db237  push    rsi
0x1800db238  push    rdi
0x1800db239  mov     rbp, rsp
0x1800db23c  sub     rsp, 48h
0x1800db240  mov     rsi, r8
0x1800db243  mov     rbx, rdx
0x1800db246  mov     rdi, rcx
0x1800db249  mov     eax, cs:dword_180175000
0x1800db24f  cmp     eax, 4
0x1800db252  jbe     short loc_1800DB26D
0x1800db254  xor     r9d, r9d
0x1800db257  xor     r8d, r8d
0x1800db25a  lea     rdx, byte_18015119B
0x1800db261  lea     rcx, dword_180175000
0x1800db268  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800db26d  mov     [rbp+var_20], 0
0x1800db275  mov     [rbp+var_28], 0
0x1800db27d  mov     [rbp+string], 0
0x1800db285  lea     r9, [rbp+string]; struct Windows::Internal::String *
0x1800db289  lea     r8, [rbp+var_28]; struct Windows::Internal::String *
0x1800db28d  lea     rdx, [rbp+var_20]; struct Windows::Internal::String *
0x1800db291  mov     rcx, rbx; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800db294  call    ?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAVString@56@11@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::String &)
0x1800db299  mov     ebx, eax
0x1800db29b  test    eax, eax
0x1800db29d  jns     short loc_1800DB2EE
0x1800db29f  mov     rcx, [rbp+20h]; this
0x1800db2a3  mov     r9d, eax; char *
0x1800db2a6  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800db2ad  mov     edx, 1EAh; void *
0x1800db2b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db2b7  nop
0x1800db2b8  mov     rcx, [rbp+string]; string
0x1800db2bc  test    rcx, rcx
0x1800db2bf  jz      short loc_1800DB2C8
0x1800db2c1  call    cs:__imp_WindowsDeleteString
0x1800db2c7  nop
0x1800db2c8  mov     rcx, [rbp+var_28]; string
0x1800db2cc  test    rcx, rcx
0x1800db2cf  jz      short loc_1800DB2D8
0x1800db2d1  call    cs:__imp_WindowsDeleteString
0x1800db2d7  nop
0x1800db2d8  mov     rcx, [rbp+var_20]; string
0x1800db2dc  test    rcx, rcx
0x1800db2df  jz      short loc_1800DB2E7
0x1800db2e1  call    cs:__imp_WindowsDeleteString
0x1800db2e7  mov     eax, ebx
0x1800db2e9  jmp     loc_1800DB38B
0x1800db2ee  mov     [rbp+arg_18], 0
0x1800db2f6  lea     rcx, [rbp+arg_18]
0x1800db2fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800db2ff  lea     r8, [rbp+arg_18]; struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **
0x1800db303  mov     rdx, rdi; this
0x1800db306  mov     rbx, [rbp+string]
0x1800db30a  mov     rcx, rbx; HSTRING
0x1800db30d  call    ?GetFromId@CWamProviderRegistrationInternal@Web@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@AEAVCallerContext@23456@PEAPEAUIWamProviderRegistrationInformation@23456@@Z; Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(HSTRING__ *,Windows::Internal::Security::Authentication::Web::CallerContext &,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)
0x1800db312  mov     edi, eax
0x1800db314  test    eax, eax
0x1800db316  jns     short loc_1800DB31F
0x1800db318  mov     edx, 1EEh
0x1800db31d  jmp     short loc_1800DB33D
0x1800db31f  mov     rcx, [rbp+arg_18]
0x1800db323  mov     rax, [rcx]
0x1800db326  mov     rdx, rsi
0x1800db329  mov     rax, [rax+68h]
0x1800db32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db332  mov     edi, eax
0x1800db334  test    eax, eax
0x1800db336  jns     short loc_1800DB351
0x1800db338  mov     edx, 1F0h; void *
0x1800db33d  mov     r9d, edi; char *
0x1800db340  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800db347  mov     rcx, [rbp+20h]; this
0x1800db34b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db350  nop
0x1800db351  lea     rcx, [rbp+arg_18]
0x1800db355  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800db35a  nop
0x1800db35b  test    rbx, rbx
0x1800db35e  jz      short loc_1800DB36A
0x1800db360  mov     rcx, rbx; string
0x1800db363  call    cs:__imp_WindowsDeleteString
0x1800db369  nop
0x1800db36a  mov     rcx, [rbp+var_28]; string
0x1800db36e  test    rcx, rcx
0x1800db371  jz      short loc_1800DB37A
0x1800db373  call    cs:__imp_WindowsDeleteString
0x1800db379  nop
0x1800db37a  mov     rcx, [rbp+var_20]; string
0x1800db37e  test    rcx, rcx
0x1800db381  jz      short loc_1800DB389
0x1800db383  call    cs:__imp_WindowsDeleteString
0x1800db389  mov     eax, edi
0x1800db38b  add     rsp, 48h
0x1800db38f  pop     rdi
0x1800db390  pop     rsi
0x1800db391  pop     rbx
0x1800db392  pop     rbp
0x1800db393  retn
```

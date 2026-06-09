# AddProviderPropertyToCacheEntry(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter &)

- ea: `0x180109a4c`
- end: `0x180109c78`
- name: `?AddProviderPropertyToCacheEntry@@YAJPEAUIWebAccountProvider@Credentials@Security@Windows@@AEAVJsonObjectWriter@TokenBroker@Authentication@3Internal@4@@Z`
- size: `556`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010c9e8`

## callees

- `0x18000bd40`
- `0x18002d940`
- `0x180031cf8`
- `0x18003acd0`
- `0x18004cc00`
- `0x18004e750`
- `0x18004fdbc`
- `0x180063ff0`
- `0x180079548`
- `0x18008e690`
- `0x180109a4c`
- `0x180113810`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109afc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109c51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109afc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109c51`

## string_xrefs

- `0x180109ae1`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x180109b7a`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x180109bd7`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x180109c2e`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AddProviderPropertyToCacheEntry(
        __int64 (__fastcall ***a1)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *this)
{
  int v4; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v7; // rbx
  int PluginPFN; // eax
  int v9; // eax
  HSTRING v10; // rbx
  int v11; // edi
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-29h]
  HSTRING v14; // [rsp+30h] [rbp-19h] BYREF
  HSTRING string; // [rsp+38h] [rbp-11h] BYREF
  HSTRING v16; // [rsp+40h] [rbp-9h] BYREF
  int v17; // [rsp+48h] [rbp-1h] BYREF
  char v18; // [rsp+4Ch] [rbp+3h]
  __int128 v19; // [rsp+50h] [rbp+7h]
  _QWORD v20[4]; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &byte_180157947,
      0,
      0);
  v14 = 0;
  if ( Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsSystemProvider((struct Windows::Security::Credentials::IWebAccountProvider *)a1) )
  {
    v16 = 0;
    string = 0;
    v4 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
           a1,
           &v16,
           &string,
           &v14);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A2,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)v4,
        v13);
      if ( string )
        WindowsDeleteString(string);
      if ( v16 )
        WindowsDeleteString(v16);
      goto LABEL_9;
    }
    v7 = L"ProviderRealId";
    if ( string )
      WindowsDeleteString(string);
    if ( v16 )
      WindowsDeleteString(v16);
  }
  else
  {
    WindowsDeleteString(0);
    v14 = 0;
    PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
                  (struct Windows::Security::Credentials::IWebAccountProvider *)a1,
                  &v14);
    v5 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A7,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)PluginPFN,
        v13);
LABEL_9:
      if ( v14 )
        WindowsDeleteString(v14);
      return v5;
    }
    v7 = L"ProviderPfn";
  }
  v17 = 5;
  v18 = 0;
  v19 = 0;
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v20, v7);
  LOBYTE(v13) = 0;
  v9 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v17, 0, v20[0], 0);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B0,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v9,
      v13);
    Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v17);
    goto LABEL_9;
  }
  v10 = v14;
  v11 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v17,
          v14);
  if ( v11 < 0 )
  {
    v12 = 1457;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v11,
      v13);
    goto LABEL_26;
  }
  v11 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
          this,
          (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v17);
  if ( v11 < 0 )
  {
    v12 = 1458;
    goto LABEL_25;
  }
LABEL_26:
  Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v17);
  if ( v10 )
    WindowsDeleteString(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180109a4c  mov     [rsp-8+arg_10], rbx
0x180109a51  push    rbp
0x180109a52  push    rsi
0x180109a53  push    rdi
0x180109a54  lea     rbp, [rsp-47h]
0x180109a59  sub     rsp, 90h
0x180109a60  mov     rax, cs:__security_cookie
0x180109a67  xor     rax, rsp
0x180109a6a  mov     [rbp+57h+var_20], rax
0x180109a6e  mov     rsi, rdx
0x180109a71  mov     rbx, rcx
0x180109a74  mov     eax, cs:dword_180175000
0x180109a7a  cmp     eax, 4
0x180109a7d  jbe     short loc_180109A98
0x180109a7f  xor     r9d, r9d
0x180109a82  xor     r8d, r8d
0x180109a85  lea     rdx, byte_180157947
0x180109a8c  lea     rcx, dword_180175000
0x180109a93  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180109a98  mov     rcx, rbx; struct Windows::Security::Credentials::IWebAccountProvider *
0x180109a9b  call    ?IsSystemProvider@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA_NPEAUIWebAccountProvider@Credentials@46@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsSystemProvider(Windows::Security::Credentials::IWebAccountProvider *)
0x180109aa0  mov     [rbp+57h+var_70], 0
0x180109aa8  test    al, al
0x180109aaa  jz      loc_180109B51
0x180109ab0  mov     [rbp+57h+var_60], 0
0x180109ab8  mov     [rbp+57h+string], 0
0x180109ac0  lea     r9, [rbp+57h+var_70]; struct Windows::Internal::String *
0x180109ac4  lea     r8, [rbp+57h+string]; struct Windows::Internal::String *
0x180109ac8  lea     rdx, [rbp+57h+var_60]; struct Windows::Internal::String *
0x180109acc  mov     rcx, rbx; struct Windows::Security::Credentials::IWebAccountProvider *
0x180109acf  call    ?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAVString@56@11@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::String &)
0x180109ad4  mov     ebx, eax
0x180109ad6  test    eax, eax
0x180109ad8  jns     short loc_180109B29
0x180109ada  mov     rcx, [rbp+5Fh]; this
0x180109ade  mov     r9d, eax; char *
0x180109ae1  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180109ae8  mov     edx, 5A2h; void *
0x180109aed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109af2  nop
0x180109af3  mov     rcx, [rbp+57h+string]; string
0x180109af7  test    rcx, rcx
0x180109afa  jz      short loc_180109B03
0x180109afc  call    cs:__imp_WindowsDeleteString
0x180109b02  nop
0x180109b03  mov     rcx, [rbp+57h+var_60]; string
0x180109b07  test    rcx, rcx
0x180109b0a  jz      short loc_180109B13
0x180109b0c  call    cs:__imp_WindowsDeleteString
0x180109b12  nop
0x180109b13  mov     rcx, [rbp+57h+var_70]; string
0x180109b17  test    rcx, rcx
0x180109b1a  jz      short loc_180109B22
0x180109b1c  call    cs:__imp_WindowsDeleteString
0x180109b22  mov     eax, ebx
0x180109b24  jmp     loc_180109C59
0x180109b29  lea     rbx, aProviderrealid; "ProviderRealId"
0x180109b30  mov     rcx, [rbp+57h+string]; string
0x180109b34  test    rcx, rcx
0x180109b37  jz      short loc_180109B40
0x180109b39  call    cs:__imp_WindowsDeleteString
0x180109b3f  nop
0x180109b40  mov     rcx, [rbp+57h+var_60]; string
0x180109b44  test    rcx, rcx
0x180109b47  jz      short loc_180109B94
0x180109b49  call    cs:__imp_WindowsDeleteString
0x180109b4f  jmp     short loc_180109B94
0x180109b51  xor     ecx, ecx; string
0x180109b53  call    cs:__imp_WindowsDeleteString
0x180109b59  mov     [rbp+57h+var_70], 0
0x180109b61  lea     rdx, [rbp+57h+var_70]; HSTRING *
0x180109b65  mov     rcx, rbx; struct Windows::Security::Credentials::IWebAccountProvider *
0x180109b68  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x180109b6d  mov     ebx, eax
0x180109b6f  test    eax, eax
0x180109b71  jns     short loc_180109B8D
0x180109b73  mov     rcx, [rbp+5Fh]; this
0x180109b77  mov     r9d, eax; char *
0x180109b7a  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180109b81  mov     edx, 5A7h; void *
0x180109b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109b8b  jmp     short loc_180109B13
0x180109b8d  lea     rbx, aProviderpfn; "ProviderPfn"
0x180109b94  mov     [rbp+57h+var_58], 5
0x180109b9b  mov     [rbp+57h+var_54], 0
0x180109b9f  xorps   xmm0, xmm0
0x180109ba2  movdqu  [rbp+57h+var_50], xmm0
0x180109ba7  mov     rdx, rbx; unsigned __int16 *
0x180109baa  lea     rcx, [rbp+57h+var_40]; this
0x180109bae  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180109bb3  mov     byte ptr [rsp+0A0h+var_80], 0; int
0x180109bb8  xor     r9d, r9d
0x180109bbb  mov     r8, [rbp+57h+var_40]
0x180109bbf  xor     edx, edx
0x180109bc1  lea     rcx, [rbp+57h+var_58]
0x180109bc5  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x180109bca  mov     ebx, eax
0x180109bcc  test    eax, eax
0x180109bce  jns     short loc_180109BF7
0x180109bd0  mov     rcx, [rbp+5Fh]; this
0x180109bd4  mov     r9d, eax; char *
0x180109bd7  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180109bde  mov     edx, 5B0h; void *
0x180109be3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109be8  nop
0x180109be9  lea     rcx, [rbp+57h+var_58]; this
0x180109bed  call    ??1JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty(void)
0x180109bf2  jmp     loc_180109B13
0x180109bf7  mov     rbx, [rbp+57h+var_70]
0x180109bfb  mov     rdx, rbx; HSTRING
0x180109bfe  lea     rcx, [rbp+57h+var_58]; this
0x180109c02  call    ?SetSingleStringValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(HSTRING__ *)
0x180109c07  mov     edi, eax
0x180109c09  test    eax, eax
0x180109c0b  jns     short loc_180109C14
0x180109c0d  mov     edx, 5B1h
0x180109c12  jmp     short loc_180109C2B
0x180109c14  lea     rdx, [rbp+57h+var_58]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x180109c18  mov     rcx, rsi; this
0x180109c1b  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x180109c20  mov     edi, eax
0x180109c22  test    eax, eax
0x180109c24  jns     short loc_180109C3F
0x180109c26  mov     edx, 5B2h; void *
0x180109c2b  mov     r9d, edi; char *
0x180109c2e  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180109c35  mov     rcx, [rbp+5Fh]; this
0x180109c39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c3e  nop
0x180109c3f  lea     rcx, [rbp+57h+var_58]; this
0x180109c43  call    ??1JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty(void)
0x180109c48  nop
0x180109c49  test    rbx, rbx
0x180109c4c  jz      short loc_180109C57
0x180109c4e  mov     rcx, rbx; string
0x180109c51  call    cs:__imp_WindowsDeleteString
0x180109c57  mov     eax, edi
0x180109c59  mov     rcx, [rbp+57h+var_20]
0x180109c5d  xor     rcx, rsp; StackCookie
0x180109c60  call    __security_check_cookie
0x180109c65  mov     rbx, [rsp+0A0h+arg_10]
0x180109c6d  add     rsp, 90h
0x180109c74  pop     rdi
0x180109c75  pop     rsi
0x180109c76  pop     rbp
0x180109c77  retn
```

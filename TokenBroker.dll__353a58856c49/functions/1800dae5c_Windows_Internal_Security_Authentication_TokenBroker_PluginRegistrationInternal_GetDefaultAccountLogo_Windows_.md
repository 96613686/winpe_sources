# Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetDefaultAccountLogo(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)

- ea: `0x1800dae5c`
- end: `0x1800db09f`
- name: `?GetDefaultAccountLogo@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(struct Windows::Internal::Security::Authentication::Web::CallerContext *this, struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800845d0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800228e0`
- `0x180031cf8`
- `0x180040980`
- `0x1800426b0`
- `0x1800dae5c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db01e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db01e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daeee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daeee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800daf24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800daf24`

## string_xrefs

- `0x1800daeb3`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`
- `0x1800dafaa`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`
- `0x1800dafea`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetDefaultAccountLogo(
        struct Windows::Internal::Security::Authentication::Web::CallerContext *this,
        __int64 (__fastcall ***a2)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        HSTRING *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  HSTRING v8; // rdi
  HSTRING v9; // rbx
  HSTRING v10; // rsi
  PCWSTR v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  unsigned int v16; // r14d
  int v17; // eax
  int v18; // r9d
  int v19; // [rsp+20h] [rbp-39h]
  HSTRING v20; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v21; // [rsp+48h] [rbp-11h] BYREF
  HSTRING v22; // [rsp+50h] [rbp-9h] BYREF
  HSTRING string; // [rsp+58h] [rbp-1h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp+7h] BYREF
  PCWSTR v25; // [rsp+68h] [rbp+Fh] BYREF
  int v26[2]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v28; // [rsp+D8h] [rbp+7Fh] BYREF

  v21 = 0;
  v22 = 0;
  string = 0;
  v5 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
         a2,
         &v21,
         &v22,
         &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = v21;
    v9 = v22;
    v10 = string;
    if ( (unsigned int)dword_180175000 > 4 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( WindowsIsStringEmpty(v9) )
        v11 = L"NULL";
      else
        v11 = WindowsGetStringRawBuffer(v9, 0);
      v25 = v11;
      *(_QWORD *)v26 = WindowsGetStringRawBuffer(v8, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)byte_1801512BD,
        v13,
        v14,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&StringRawBuffer);
    }
    v28 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v15 = Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(v10, this, &v28);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v20 = 0;
      v17 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING *))(*(_QWORD *)v28 + 72LL))(
              v28,
              &v20);
      v16 = v17;
      if ( v17 >= 0 )
      {
        if ( (unsigned int)dword_180175000 > 5 )
        {
          *(_QWORD *)v26 = WindowsGetStringRawBuffer(v20, 0);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_180175000,
            (unsigned int)byte_1801511F9,
            0,
            v18,
            (__int64)v26);
        }
        *a3 = v20;
        v20 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
          (const char *)(unsigned int)v17,
          v19);
        if ( v20 )
          WindowsDeleteString(v20);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
        (const char *)(unsigned int)v15,
        v19);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    if ( v10 )
      WindowsDeleteString(v10);
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v8 )
      WindowsDeleteString(v8);
    return v16;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
      (const char *)(unsigned int)v5,
      v19);
    if ( string )
      WindowsDeleteString(string);
    if ( v22 )
      WindowsDeleteString(v22);
    if ( v21 )
      WindowsDeleteString(v21);
    return v6;
  }
}

```

## disassembly

```asm
0x1800dae5c  push    rbp
0x1800dae5e  push    rbx
0x1800dae5f  push    rsi
0x1800dae60  push    rdi
0x1800dae61  push    r14
0x1800dae63  push    r15
0x1800dae65  lea     rbp, [rsp-2Fh]
0x1800dae6a  sub     rsp, 88h
0x1800dae71  mov     r15, r8
0x1800dae74  mov     rax, rdx
0x1800dae77  mov     r14, rcx
0x1800dae7a  mov     [rbp+57h+var_68], 0
0x1800dae82  mov     [rbp+57h+var_60], 0
0x1800dae8a  mov     [rbp+57h+string], 0
0x1800dae92  lea     r9, [rbp+57h+string]; struct Windows::Internal::String *
0x1800dae96  lea     r8, [rbp+57h+var_60]; struct Windows::Internal::String *
0x1800dae9a  lea     rdx, [rbp+57h+var_68]; struct Windows::Internal::String *
0x1800dae9e  mov     rcx, rax; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800daea1  call    ?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAVString@56@11@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::String &)
0x1800daea6  mov     ebx, eax
0x1800daea8  test    eax, eax
0x1800daeaa  jns     short loc_1800DAEFB
0x1800daeac  mov     rcx, [rbp+5Fh]; this
0x1800daeb0  mov     r9d, eax; char *
0x1800daeb3  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800daeba  mov     edx, 0E9h; void *
0x1800daebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800daec4  nop
0x1800daec5  mov     rcx, [rbp+57h+string]; string
0x1800daec9  test    rcx, rcx
0x1800daecc  jz      short loc_1800DAED5
0x1800daece  call    cs:__imp_WindowsDeleteString
0x1800daed4  nop
0x1800daed5  mov     rcx, [rbp+57h+var_60]; string
0x1800daed9  test    rcx, rcx
0x1800daedc  jz      short loc_1800DAEE5
0x1800daede  call    cs:__imp_WindowsDeleteString
0x1800daee4  nop
0x1800daee5  mov     rcx, [rbp+57h+var_68]; string
0x1800daee9  test    rcx, rcx
0x1800daeec  jz      short loc_1800DAEF4
0x1800daeee  call    cs:__imp_WindowsDeleteString
0x1800daef4  mov     eax, ebx
0x1800daef6  jmp     loc_1800DB08F
0x1800daefb  mov     eax, cs:dword_180175000
0x1800daf01  mov     rdi, [rbp+57h+var_68]
0x1800daf05  mov     rbx, [rbp+57h+var_60]
0x1800daf09  mov     rsi, [rbp+57h+string]
0x1800daf0d  cmp     eax, 4
0x1800daf10  jbe     short loc_1800DAF7C
0x1800daf12  xor     edx, edx; length
0x1800daf14  mov     rcx, rsi; string
0x1800daf17  call    cs:__imp_WindowsGetStringRawBuffer
0x1800daf1d  mov     [rbp+57h+var_50], rax
0x1800daf21  mov     rcx, rbx; string
0x1800daf24  call    cs:__imp_WindowsIsStringEmpty
0x1800daf2a  test    eax, eax
0x1800daf2c  jz      short loc_1800DAF37
0x1800daf2e  lea     rax, aNull_1; "NULL"
0x1800daf35  jmp     short loc_1800DAF42
0x1800daf37  xor     edx, edx; length
0x1800daf39  mov     rcx, rbx; string
0x1800daf3c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800daf42  mov     [rbp+57h+var_48], rax
0x1800daf46  xor     edx, edx; length
0x1800daf48  mov     rcx, rdi; string
0x1800daf4b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800daf51  mov     qword ptr [rbp+57h+var_40], rax
0x1800daf55  lea     rax, [rbp+57h+var_50]
0x1800daf59  mov     [rsp+0B0h+var_80], rax
0x1800daf5e  lea     rax, [rbp+57h+var_48]
0x1800daf62  mov     [rsp+0B0h+var_88], rax
0x1800daf67  lea     rax, [rbp+57h+var_40]
0x1800daf6b  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800daf70  lea     rdx, byte_1801512BD
0x1800daf77  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800daf7c  mov     [rbp+57h+arg_18], 0
0x1800daf84  lea     rcx, [rbp+57h+arg_18]
0x1800daf88  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800daf8d  lea     r8, [rbp+57h+arg_18]; struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **
0x1800daf91  mov     rdx, r14; this
0x1800daf94  mov     rcx, rsi; HSTRING
0x1800daf97  call    ?GetFromId@CWamProviderRegistrationInternal@Web@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@AEAVCallerContext@23456@PEAPEAUIWamProviderRegistrationInformation@23456@@Z; Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(HSTRING__ *,Windows::Internal::Security::Authentication::Web::CallerContext &,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)
0x1800daf9c  mov     r14d, eax
0x1800daf9f  test    eax, eax
0x1800dafa1  jns     short loc_1800DAFC0
0x1800dafa3  mov     rcx, [rbp+5Fh]; this
0x1800dafa7  mov     r9d, eax; char *
0x1800dafaa  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dafb1  mov     edx, 0FDh; void *
0x1800dafb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dafbb  jmp     loc_1800DB056
0x1800dafc0  mov     [rbp+57h+var_70], 0
0x1800dafc8  mov     rcx, [rbp+57h+arg_18]
0x1800dafcc  mov     rax, [rcx]
0x1800dafcf  lea     rdx, [rbp+57h+var_70]
0x1800dafd3  mov     rax, [rax+48h]
0x1800dafd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dafdc  mov     r14d, eax
0x1800dafdf  test    eax, eax
0x1800dafe1  jns     short loc_1800DB00D
0x1800dafe3  mov     rcx, [rbp+5Fh]; this
0x1800dafe7  mov     r9d, eax; char *
0x1800dafea  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800daff1  mov     edx, 100h; void *
0x1800daff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800daffb  nop
0x1800daffc  mov     rcx, [rbp+57h+var_70]; string
0x1800db000  test    rcx, rcx
0x1800db003  jz      short loc_1800DB056
0x1800db005  call    cs:__imp_WindowsDeleteString
0x1800db00b  jmp     short loc_1800DB056
0x1800db00d  mov     eax, cs:dword_180175000
0x1800db013  cmp     eax, 5
0x1800db016  jbe     short loc_1800DB047
0x1800db018  xor     edx, edx; length
0x1800db01a  mov     rcx, [rbp+57h+var_70]; string
0x1800db01e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db024  mov     qword ptr [rbp+57h+var_40], rax
0x1800db028  lea     rax, [rbp+57h+var_40]
0x1800db02c  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800db031  xor     r8d, r8d
0x1800db034  lea     rdx, byte_1801511F9
0x1800db03b  lea     rcx, dword_180175000
0x1800db042  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800db047  mov     rax, [rbp+57h+var_70]
0x1800db04b  mov     [r15], rax
0x1800db04e  mov     [rbp+57h+var_70], 0
0x1800db056  lea     rcx, [rbp+57h+arg_18]
0x1800db05a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800db05f  nop
0x1800db060  test    rsi, rsi
0x1800db063  jz      short loc_1800DB06F
0x1800db065  mov     rcx, rsi; string
0x1800db068  call    cs:__imp_WindowsDeleteString
0x1800db06e  nop
0x1800db06f  test    rbx, rbx
0x1800db072  jz      short loc_1800DB07E
0x1800db074  mov     rcx, rbx; string
0x1800db077  call    cs:__imp_WindowsDeleteString
0x1800db07d  nop
0x1800db07e  test    rdi, rdi
0x1800db081  jz      short loc_1800DB08C
0x1800db083  mov     rcx, rdi; string
0x1800db086  call    cs:__imp_WindowsDeleteString
0x1800db08c  mov     eax, r14d
0x1800db08f  add     rsp, 88h
0x1800db096  pop     r15
0x1800db098  pop     r14
0x1800db09a  pop     rdi
0x1800db09b  pop     rsi
0x1800db09c  pop     rbx
0x1800db09d  pop     rbp
0x1800db09e  retn
```

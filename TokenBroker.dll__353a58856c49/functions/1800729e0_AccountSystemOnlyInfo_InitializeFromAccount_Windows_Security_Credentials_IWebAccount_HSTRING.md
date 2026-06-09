# AccountSystemOnlyInfo::InitializeFromAccount(Windows::Security::Credentials::IWebAccount *,HSTRING__ *)

- ea: `0x1800729e0`
- end: `0x180072cc7`
- name: `?InitializeFromAccount@AccountSystemOnlyInfo@@QEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEAUHSTRING__@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(AccountSystemOnlyInfo *__hidden this, struct Windows::Security::Credentials::IWebAccount *, HSTRING)`
- caller_count: `6`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063184`
- `0x1800743a0`
- `0x18010e6c4`
- `0x18010e9f0`
- `0x18010ffac`
- `0x180110268`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180010a70`
- `0x18002a3e0`
- `0x180035880`
- `0x18003ffa0`
- `0x1800454f0`
- `0x18004c014`
- `0x18004fdbc`
- `0x180051dd0`
- `0x180063ff0`
- `0x1800729e0`
- `0x180072cd0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072be9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072be9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072a7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072a7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c9c`

## string_xrefs

- `0x180072a51`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072aa6`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072b04`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072b4b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072c08`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072c42`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AccountSystemOnlyInfo::InitializeFromAccount(
        AccountSystemOnlyInfo *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        HSTRING a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  __int64 (__fastcall *v10)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v11; // eax
  int PluginPFN; // eax
  HSTRING v13; // rbx
  unsigned __int16 *StringRawBuffer; // rax
  int v15; // eax
  int v16; // edi
  int v17; // eax
  int *v19; // [rsp+20h] [rbp-89h]
  __int64 v20; // [rsp+30h] [rbp-79h] BYREF
  __int64 (__fastcall ***v21[2])(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-71h] BYREF
  int v22[2]; // [rsp+48h] [rbp-61h] BYREF
  HLOCAL v23; // [rsp+50h] [rbp-59h] BYREF
  int v24; // [rsp+58h] [rbp-51h]
  __int128 v25; // [rsp+60h] [rbp-49h]
  __int64 v26; // [rsp+70h] [rbp-39h]
  _BYTE v27[128]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  struct Windows::Security::Credentials::IWebAccountProvider *v29; // [rsp+118h] [rbp+6Fh] BYREF
  HSTRING string; // [rsp+120h] [rbp+77h] BYREF
  HSTRING v31; // [rsp+128h] [rbp+7Fh] BYREF

  string = a3;
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &word_180158F3E,
      0,
      0);
  v21[0] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v21);
  v20 = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
         v21,
         (__int64)&v20);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v5,
      (int)v19);
    goto LABEL_28;
  }
  string = 0;
  v7 = v20;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(v7, &string);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v9,
      (int)v19);
    goto LABEL_7;
  }
  v29 = 0;
  v10 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v11 = v10(a2, &v29);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x269,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v11,
      (int)v19);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
LABEL_7:
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_28;
  }
  WindowsDeleteString(0);
  v31 = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
                (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v29,
                &v31);
  v6 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)PluginPFN,
      (int)v19);
    if ( v31 )
      WindowsDeleteString(v31);
    goto LABEL_11;
  }
  v13 = v31;
  if ( (unsigned int)dword_180175000 > 5 )
  {
    v21[1] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))WindowsGetStringRawBuffer(v31, 0);
    *(_QWORD *)v22 = WindowsGetStringRawBuffer(string, 0);
    v19 = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      &dword_180175000,
      word_180158EE2,
      0);
  }
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
  v15 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(
          &v23,
          StringRawBuffer);
  v16 = v15;
  if ( v15 >= 0 )
  {
    AccountSystemOnlyInfo::AccountSystemOnlyInfo((AccountSystemOnlyInfo *)v27);
    v17 = AccountSystemOnlyInfo::InitializeFromAccountId(
            (AccountSystemOnlyInfo *)v27,
            (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v23,
            v13);
    v16 = v17;
    if ( v17 >= 0 )
      v16 = AccountSystemOnlyInfo::InitializeFromAccountId(
              this,
              (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v23,
              v13);
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x284,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v17,
        (int)v19);
    AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)v27);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x281,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v15,
      (int)v19);
  }
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v23);
  if ( v13 )
    WindowsDeleteString(v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  if ( string )
    WindowsDeleteString(string);
  v6 = v16;
LABEL_28:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  return v6;
}

```

## disassembly

```asm
0x1800729e0  mov     [rsp-8+string], r8
0x1800729e5  push    rbp
0x1800729e6  push    rbx
0x1800729e7  push    rsi
0x1800729e8  push    rdi
0x1800729e9  push    r14
0x1800729eb  lea     rbp, [rsp-37h]
0x1800729f0  sub     rsp, 0E0h
0x1800729f7  mov     rsi, rdx
0x1800729fa  mov     r14, rcx
0x1800729fd  mov     eax, cs:dword_180175000
0x180072a03  cmp     eax, 4
0x180072a06  jbe     short loc_180072A21
0x180072a08  xor     r9d, r9d
0x180072a0b  xor     r8d, r8d
0x180072a0e  lea     rdx, word_180158F3E
0x180072a15  lea     rcx, dword_180175000
0x180072a1c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180072a21  mov     [rbp+57h+var_C8], rsi
0x180072a25  lea     rcx, [rbp+57h+var_C8]
0x180072a29  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180072a2e  nop
0x180072a2f  mov     [rbp+57h+var_D0], 0
0x180072a37  lea     rdx, [rbp+57h+var_D0]
0x180072a3b  lea     rcx, [rbp+57h+var_C8]
0x180072a3f  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x180072a44  mov     ebx, eax
0x180072a46  test    eax, eax
0x180072a48  jns     short loc_180072A67
0x180072a4a  mov     rcx, [rbp+5Fh]; this
0x180072a4e  mov     r9d, eax; char *
0x180072a51  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072a58  mov     edx, 261h; void *
0x180072a5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072a62  jmp     loc_180072CA4
0x180072a67  mov     [rbp+57h+string], 0
0x180072a6f  mov     rdi, [rbp+57h+var_D0]
0x180072a73  mov     rax, [rdi]
0x180072a76  mov     rbx, [rax+30h]
0x180072a7a  xor     ecx, ecx; string
0x180072a7c  call    cs:__imp_WindowsDeleteString
0x180072a82  mov     [rbp+57h+string], 0
0x180072a8a  lea     rdx, [rbp+57h+string]
0x180072a8e  mov     rcx, rdi
0x180072a91  mov     rax, rbx
0x180072a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a99  mov     ebx, eax
0x180072a9b  test    eax, eax
0x180072a9d  jns     short loc_180072AD0
0x180072a9f  mov     rcx, [rbp+5Fh]; this
0x180072aa3  mov     r9d, eax; char *
0x180072aa6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072aad  mov     edx, 265h; void *
0x180072ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072ab7  nop
0x180072ab8  mov     rcx, [rbp+57h+string]; string
0x180072abc  test    rcx, rcx
0x180072abf  jz      loc_180072CA4
0x180072ac5  call    cs:__imp_WindowsDeleteString
0x180072acb  jmp     loc_180072CA4
0x180072ad0  mov     [rbp+57h+arg_8], 0
0x180072ad8  mov     rax, [rsi]
0x180072adb  mov     rbx, [rax+30h]
0x180072adf  lea     rcx, [rbp+57h+arg_8]
0x180072ae3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072ae8  lea     rdx, [rbp+57h+arg_8]
0x180072aec  mov     rcx, rsi
0x180072aef  mov     rax, rbx
0x180072af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072af7  mov     ebx, eax
0x180072af9  test    eax, eax
0x180072afb  jns     short loc_180072B21
0x180072afd  mov     rcx, [rbp+5Fh]; this
0x180072b01  mov     r9d, eax; char *
0x180072b04  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072b0b  mov     edx, 269h; void *
0x180072b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072b15  nop
0x180072b16  lea     rcx, [rbp+57h+arg_8]
0x180072b1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072b1f  jmp     short loc_180072AB8
0x180072b21  xor     ecx, ecx; string
0x180072b23  call    cs:__imp_WindowsDeleteString
0x180072b29  mov     [rbp+57h+arg_18], 0
0x180072b31  lea     rdx, [rbp+57h+arg_18]; HSTRING *
0x180072b35  mov     rcx, [rbp+57h+arg_8]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180072b39  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x180072b3e  mov     ebx, eax
0x180072b40  test    eax, eax
0x180072b42  jns     short loc_180072B6E
0x180072b44  mov     rcx, [rbp+5Fh]; this
0x180072b48  mov     r9d, eax; char *
0x180072b4b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072b52  mov     edx, 26Fh; void *
0x180072b57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072b5c  nop
0x180072b5d  mov     rcx, [rbp+57h+arg_18]; string
0x180072b61  test    rcx, rcx
0x180072b64  jz      short loc_180072B16
0x180072b66  call    cs:__imp_WindowsDeleteString
0x180072b6c  jmp     short loc_180072B16
0x180072b6e  mov     eax, cs:dword_180175000
0x180072b74  mov     rbx, [rbp+57h+arg_18]
0x180072b78  cmp     eax, 5
0x180072b7b  jbe     short loc_180072BC4
0x180072b7d  xor     edx, edx; length
0x180072b7f  mov     rcx, rbx; string
0x180072b82  call    cs:__imp_WindowsGetStringRawBuffer
0x180072b88  mov     [rbp+57h+var_C0], rax
0x180072b8c  xor     edx, edx; length
0x180072b8e  mov     rcx, [rbp+57h+string]; string
0x180072b92  call    cs:__imp_WindowsGetStringRawBuffer
0x180072b98  mov     qword ptr [rbp+57h+var_B8], rax
0x180072b9c  lea     rax, [rbp+57h+var_C0]
0x180072ba0  mov     [rsp+100h+var_D8], rax
0x180072ba5  lea     rax, [rbp+57h+var_B8]
0x180072ba9  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180072bae  xor     r8d, r8d
0x180072bb1  lea     rdx, word_180158EE2
0x180072bb8  lea     rcx, dword_180175000
0x180072bbf  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180072bc4  mov     [rbp+57h+var_B0], 0
0x180072bcc  mov     [rbp+57h+var_A8], 0
0x180072bd3  xorps   xmm0, xmm0
0x180072bd6  movdqu  [rbp+57h+var_A0], xmm0
0x180072bdb  mov     [rbp+57h+var_90], 0
0x180072be3  xor     edx, edx; length
0x180072be5  mov     rcx, [rbp+57h+string]; string
0x180072be9  call    cs:__imp_WindowsGetStringRawBuffer
0x180072bef  mov     rdx, rax; unsigned __int16 *
0x180072bf2  lea     rcx, [rbp+57h+var_B0]; this
0x180072bf6  call    ?InitializeFromStringId@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(ushort const *)
0x180072bfb  mov     edi, eax
0x180072bfd  test    eax, eax
0x180072bff  jns     short loc_180072C1B
0x180072c01  mov     rcx, [rbp+5Fh]; this
0x180072c05  mov     r9d, eax; char *
0x180072c08  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072c0f  mov     edx, 281h; void *
0x180072c14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072c19  jmp     short loc_180072C70
0x180072c1b  lea     rcx, [rbp+57h+var_80]; this
0x180072c1f  call    ??0AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::AccountSystemOnlyInfo(void)
0x180072c24  nop
0x180072c25  mov     r8, rbx; HSTRING
0x180072c28  lea     rdx, [rbp+57h+var_B0]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x180072c2c  lea     rcx, [rbp+57h+var_80]; this
0x180072c30  call    ?InitializeFromAccountId@AccountSystemOnlyInfo@@QEAAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@@Z; AccountSystemOnlyInfo::InitializeFromAccountId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ *)
0x180072c35  mov     edi, eax
0x180072c37  test    eax, eax
0x180072c39  jns     short loc_180072C55
0x180072c3b  mov     rcx, [rbp+5Fh]; this
0x180072c3f  mov     r9d, eax; char *
0x180072c42  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072c49  mov     edx, 284h; void *
0x180072c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072c53  jmp     short loc_180072C66
0x180072c55  mov     r8, rbx; HSTRING
0x180072c58  lea     rdx, [rbp+57h+var_B0]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x180072c5c  mov     rcx, r14; this
0x180072c5f  call    ?InitializeFromAccountId@AccountSystemOnlyInfo@@QEAAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@@Z; AccountSystemOnlyInfo::InitializeFromAccountId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ *)
0x180072c64  mov     edi, eax
0x180072c66  lea     rcx, [rbp+57h+var_80]; this
0x180072c6a  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x180072c6f  nop
0x180072c70  lea     rcx, [rbp+57h+var_B0]; this
0x180072c74  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x180072c79  nop
0x180072c7a  test    rbx, rbx
0x180072c7d  jz      short loc_180072C89
0x180072c7f  mov     rcx, rbx; string
0x180072c82  call    cs:__imp_WindowsDeleteString
0x180072c88  nop
0x180072c89  lea     rcx, [rbp+57h+arg_8]
0x180072c8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072c92  nop
0x180072c93  mov     rcx, [rbp+57h+string]; string
0x180072c97  test    rcx, rcx
0x180072c9a  jz      short loc_180072CA2
0x180072c9c  call    cs:__imp_WindowsDeleteString
0x180072ca2  mov     ebx, edi
0x180072ca4  lea     rcx, [rbp+57h+var_D0]
0x180072ca8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072cad  nop
0x180072cae  lea     rcx, [rbp+57h+var_C8]
0x180072cb2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072cb7  mov     eax, ebx
0x180072cb9  add     rsp, 0E0h
0x180072cc0  pop     r14
0x180072cc2  pop     rdi
0x180072cc3  pop     rsi
0x180072cc4  pop     rbx
0x180072cc5  pop     rbp
0x180072cc6  retn
```

# ClearCachedTokenResponsesForAccount(HSTRING__ *,Windows::Security::Credentials::IWebAccount *)

- ea: `0x180070390`
- end: `0x18007065a`
- name: `?ClearCachedTokenResponsesForAccount@@YAJPEAUHSTRING__@@PEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `714`
- prototype: `__int64 __fastcall(HSTRING, struct Windows::Security::Credentials::IWebAccount *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c2180`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180037174`
- `0x180040980`
- `0x18004e850`
- `0x18004fdbc`
- `0x18005a898`
- `0x180063ff0`
- `0x180070390`
- `0x180071428`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070479`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007053e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070479`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007053e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007045a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007061f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007045a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007061f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070638`

## string_xrefs

- `0x180070403`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18007043b`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x1800704d8`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x180070517`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x180070591`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ClearCachedTokenResponsesForAccount(
        HSTRING a1,
        struct Windows::Security::Credentials::IWebAccount *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  int PluginPFN; // eax
  HSTRING v8; // rbx
  int v9; // r9d
  __int64 (__fastcall *v10)(struct Windows::Security::Credentials::IWebAccount *, GUID *, __int64 *); // rdi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  int v14; // r9d
  int AllObjectIdsForType; // eax
  struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **i; // rsi
  struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **v17; // r14
  int v18; // eax
  int v19; // r9d
  int v20; // r15d
  int v22; // [rsp+20h] [rbp-40h]
  struct Windows::Security::Credentials::IWebAccountProvider *v23; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  __int128 v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  PCWSTR StringRawBuffer; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v29; // [rsp+B0h] [rbp+50h] BYREF
  HSTRING v30; // [rsp+B8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &dword_18015735C,
      0,
      0);
  v23 = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v5 = v4(a2, &v23);
  v6 = v5;
  if ( v5 >= 0 )
  {
    string = 0;
    PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(v23, &string);
    v6 = PluginPFN;
    if ( PluginPFN >= 0 )
    {
      v8 = string;
      if ( (unsigned int)dword_180175000 > 5 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_180175000,
          (unsigned int)&byte_1801574BF,
          0,
          v9,
          (__int64)&StringRawBuffer);
      }
      v29 = 0;
      v10 = **(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccount *, GUID *, __int64 *))a2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v11 = v10(a2, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v29);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v30 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 48LL))(v29, &v30);
        v12 = v13;
        if ( v13 >= 0 )
        {
          if ( (unsigned int)dword_180175000 > 5 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v30, 0);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (unsigned int)&dword_180175000,
              (unsigned int)&byte_180157467,
              0,
              v14,
              (__int64)&StringRawBuffer);
          }
          v25 = 0;
          v26 = 0;
          AllObjectIdsForType = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetAllObjectIdsForType(
                                  2,
                                  a1,
                                  &v25);
          v12 = AllObjectIdsForType;
          if ( AllObjectIdsForType >= 0 )
          {
            v17 = (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **)*((_QWORD *)&v25 + 1);
            for ( i = (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **)v25;
                  i != v17;
                  i += 2 )
            {
              v18 = DeleteCacheEntryIfAccountMatch(a1, v8, v30, v23, *i);
              v20 = v18;
              if ( v18 < 0 )
              {
                if ( (unsigned int)dword_180175000 > 2 )
                {
                  LODWORD(StringRawBuffer) = v18;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                    (unsigned int)&dword_180175000,
                    (unsigned int)word_180157422,
                    0,
                    v19,
                    (__int64)&StringRawBuffer);
                }
                if ( v12 >= 0 )
                  v12 = v20;
              }
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA5E,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
              (const char *)(unsigned int)AllObjectIdsForType,
              v22);
          }
          std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Tidy(&v25);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA4C,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
            (const char *)(unsigned int)v13,
            v22);
        }
        if ( v30 )
          WindowsDeleteString(v30);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4A,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v11,
          v22);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      if ( v8 )
        WindowsDeleteString(v8);
      v6 = v12;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)PluginPFN,
        v22);
      if ( string )
        WindowsDeleteString(string);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v5,
      v22);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  return v6;
}

```

## disassembly

```asm
0x180070390  push    rbp
0x180070392  push    rbx
0x180070393  push    rsi
0x180070394  push    rdi
0x180070395  push    r12
0x180070397  push    r14
0x180070399  push    r15
0x18007039b  mov     rbp, rsp
0x18007039e  sub     rsp, 60h
0x1800703a2  mov     rsi, rdx
0x1800703a5  mov     r12, rcx
0x1800703a8  mov     eax, cs:dword_180175000
0x1800703ae  lea     r14, dword_180175000
0x1800703b5  cmp     eax, 4
0x1800703b8  jbe     short loc_1800703CF
0x1800703ba  xor     r9d, r9d
0x1800703bd  xor     r8d, r8d
0x1800703c0  lea     rdx, dword_18015735C
0x1800703c7  mov     rcx, r14
0x1800703ca  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800703cf  mov     [rbp+var_30], 0
0x1800703d7  mov     rax, [rsi]
0x1800703da  mov     rbx, [rax+30h]
0x1800703de  lea     rcx, [rbp+var_30]
0x1800703e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800703e7  lea     rdx, [rbp+var_30]
0x1800703eb  mov     rcx, rsi
0x1800703ee  mov     rax, rbx
0x1800703f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800703f6  mov     ebx, eax
0x1800703f8  test    eax, eax
0x1800703fa  jns     short loc_180070419
0x1800703fc  mov     rcx, [rbp+38h]; this
0x180070400  mov     r9d, eax; char *
0x180070403  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007040a  mov     edx, 0A3Ch; void *
0x18007040f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070414  jmp     loc_180070640
0x180070419  mov     [rbp+string], 0
0x180070421  lea     rdx, [rbp+string]; HSTRING *
0x180070425  mov     rcx, [rbp+var_30]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180070429  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18007042e  mov     ebx, eax
0x180070430  test    eax, eax
0x180070432  jns     short loc_180070465
0x180070434  mov     rcx, [rbp+38h]; this
0x180070438  mov     r9d, eax; char *
0x18007043b  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180070442  mov     edx, 0A3Eh; void *
0x180070447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007044c  nop
0x18007044d  mov     rcx, [rbp+string]; string
0x180070451  test    rcx, rcx
0x180070454  jz      loc_180070640
0x18007045a  call    cs:__imp_WindowsDeleteString
0x180070460  jmp     loc_180070640
0x180070465  mov     eax, cs:dword_180175000
0x18007046b  mov     rbx, [rbp+string]
0x18007046f  cmp     eax, 5
0x180070472  jbe     short loc_18007049E
0x180070474  xor     edx, edx; length
0x180070476  mov     rcx, rbx; string
0x180070479  call    cs:__imp_WindowsGetStringRawBuffer
0x18007047f  mov     [rbp+arg_8], rax
0x180070483  lea     rax, [rbp+arg_8]
0x180070487  mov     qword ptr [rsp+60h+var_40], rax; int
0x18007048c  xor     r8d, r8d
0x18007048f  lea     rdx, byte_1801574BF
0x180070496  mov     rcx, r14
0x180070499  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007049e  mov     [rbp+arg_10], 0
0x1800704a6  mov     rax, [rsi]
0x1800704a9  mov     rdi, [rax]
0x1800704ac  lea     rcx, [rbp+arg_10]
0x1800704b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800704b5  lea     r8, [rbp+arg_10]
0x1800704b9  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x1800704c0  mov     rcx, rsi
0x1800704c3  mov     rax, rdi
0x1800704c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800704cb  mov     edi, eax
0x1800704cd  test    eax, eax
0x1800704cf  jns     short loc_1800704EE
0x1800704d1  mov     rcx, [rbp+38h]; this
0x1800704d5  mov     r9d, eax; char *
0x1800704d8  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800704df  mov     edx, 0A4Ah; void *
0x1800704e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800704e9  jmp     loc_180070626
0x1800704ee  mov     [rbp+arg_18], 0
0x1800704f6  mov     rcx, [rbp+arg_10]
0x1800704fa  mov     rax, [rcx]
0x1800704fd  lea     rdx, [rbp+arg_18]
0x180070501  mov     rax, [rax+30h]
0x180070505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007050a  mov     edi, eax
0x18007050c  test    eax, eax
0x18007050e  jns     short loc_18007052D
0x180070510  mov     rcx, [rbp+38h]; this
0x180070514  mov     r9d, eax; char *
0x180070517  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007051e  mov     edx, 0A4Ch; void *
0x180070523  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070528  jmp     loc_180070616
0x18007052d  mov     eax, cs:dword_180175000
0x180070533  cmp     eax, 5
0x180070536  jbe     short loc_180070563
0x180070538  xor     edx, edx; length
0x18007053a  mov     rcx, [rbp+arg_18]; string
0x18007053e  call    cs:__imp_WindowsGetStringRawBuffer
0x180070544  mov     [rbp+arg_8], rax
0x180070548  lea     rax, [rbp+arg_8]
0x18007054c  mov     qword ptr [rsp+60h+var_40], rax; int
0x180070551  xor     r8d, r8d
0x180070554  lea     rdx, byte_180157467
0x18007055b  mov     rcx, r14
0x18007055e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180070563  xorps   xmm0, xmm0
0x180070566  movdqu  [rbp+var_20], xmm0
0x18007056b  mov     [rbp+var_10], 0
0x180070573  lea     r8, [rbp+var_20]
0x180070577  mov     rdx, r12
0x18007057a  mov     ecx, 2
0x18007057f  call    ?GetAllObjectIdsForType@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@QEAUHSTRING__@@AEAV?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetAllObjectIdsForType(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>> &)
0x180070584  mov     edi, eax
0x180070586  test    eax, eax
0x180070588  jns     short loc_1800705A4
0x18007058a  mov     rcx, [rbp+38h]; this
0x18007058e  mov     r9d, eax; char *
0x180070591  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180070598  mov     edx, 0A5Eh; void *
0x18007059d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800705a2  jmp     short loc_18007060C
0x1800705a4  mov     rsi, qword ptr [rbp+var_20]
0x1800705a8  mov     r14, qword ptr [rbp+var_20+8]
0x1800705ac  jmp     short loc_180070607
0x1800705ae  mov     rax, [rsi]
0x1800705b1  mov     qword ptr [rsp+60h+var_40], rax; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x1800705b6  mov     r9, [rbp+var_30]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800705ba  mov     r8, [rbp+arg_18]; HSTRING
0x1800705be  mov     rdx, rbx; HSTRING
0x1800705c1  mov     rcx, r12; HSTRING
0x1800705c4  call    ?DeleteCacheEntryIfAccountMatch@@YAJPEAUHSTRING__@@00PEAUIWebAccountProvider@Credentials@Security@Windows@@AEAVStoredObjectId@TokenBroker@Authentication@4Internal@5@@Z; DeleteCacheEntryIfAccountMatch(HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &)
0x1800705c9  mov     r15d, eax
0x1800705cc  test    eax, eax
0x1800705ce  jns     short loc_180070603
0x1800705d0  mov     ecx, cs:dword_180175000
0x1800705d6  cmp     ecx, 2
0x1800705d9  jbe     short loc_1800705FD
0x1800705db  mov     dword ptr [rbp+arg_8], eax
0x1800705de  lea     rax, [rbp+arg_8]
0x1800705e2  mov     qword ptr [rsp+60h+var_40], rax
0x1800705e7  xor     r8d, r8d
0x1800705ea  lea     rdx, word_180157422
0x1800705f1  lea     rcx, dword_180175000
0x1800705f8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800705fd  test    edi, edi
0x1800705ff  cmovns  edi, r15d
0x180070603  add     rsi, 10h
0x180070607  cmp     rsi, r14
0x18007060a  jnz     short loc_1800705AE
0x18007060c  lea     rcx, [rbp+var_20]
0x180070610  call    ?_Tidy@?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Tidy(void)
0x180070615  nop
0x180070616  mov     rcx, [rbp+arg_18]; string
0x18007061a  test    rcx, rcx
0x18007061d  jz      short loc_180070626
0x18007061f  call    cs:__imp_WindowsDeleteString
0x180070625  nop
0x180070626  lea     rcx, [rbp+arg_10]
0x18007062a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007062f  nop
0x180070630  test    rbx, rbx
0x180070633  jz      short loc_18007063E
0x180070635  mov     rcx, rbx; string
0x180070638  call    cs:__imp_WindowsDeleteString
0x18007063e  mov     ebx, edi
0x180070640  lea     rcx, [rbp+var_30]
0x180070644  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070649  mov     eax, ebx
0x18007064b  add     rsp, 60h
0x18007064f  pop     r15
0x180070651  pop     r14
0x180070653  pop     r12
0x180070655  pop     rdi
0x180070656  pop     rsi
0x180070657  pop     rbx
0x180070658  pop     rbp
0x180070659  retn
```

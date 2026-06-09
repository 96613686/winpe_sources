# CopilotCapabilityUsageHistoryServer::GetRecentActivityRecords(HSTRING__ * *)

- ea: `0x180091680`
- end: `0x18009188c`
- name: `?GetRecentActivityRecords@CopilotCapabilityUsageHistoryServer@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `524`
- prototype: `int(CopilotCapabilityUsageHistoryServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800094c0`
- `0x18001f5f4`
- `0x18002392c`
- `0x180036294`
- `0x18003af38`
- `0x180045f78`
- `0x180063424`
- `0x180063470`
- `0x180091680`
- `0x1800b2ddc`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091771`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800917d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091771`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800917d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800917a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800917a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800917bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800917bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CopilotCapabilityUsageHistoryServer::GetRecentActivityRecords(
        CopilotCapabilityUsageHistoryServer *this,
        HSTRING *a2)
{
  __int64 *v4; // rax
  int v5; // eax
  __int64 RecordStubsFromUsageHistoryTables; // rax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  HRESULT v14; // eax
  const char *v15; // r9
  __int64 result; // rax
  int v17; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+20h] [rbp-58h]
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+38h] [rbp-40h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-38h] BYREF
  HSTRING v22[4]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\copilotcapabilityusagehistoryserver.cpp",
        (const char *)0x80004003LL,
        v17);
    v21 = 0;
    v4 = (__int64 *)Windows::Internal::StringReference::StringReference(v22, (const unsigned __int16 (*)[29])a2);
    v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v4, &v21);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\copilotcapabilityusagehistoryserver.cpp",
        (const char *)(unsigned int)v5,
        v17);
    RecordStubsFromUsageHistoryTables = Windows::Internal::CapabilityAccess::Private::SQL::GetRecordStubsFromUsageHistoryTables(
                                          (unsigned int)v22,
                                          (int)this + 32,
                                          (int)this + 64,
                                          10000,
                                          *((_DWORD *)this + 24));
    Windows::Internal::CapabilityAccess::Private::FormatRecentActivityRecords(RecordStubsFromUsageHistoryTables, &v21);
    std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub>::_Tidy(v22);
    v20 = 0;
    v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v21;
    v8 = **v21;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v9 = v8(v7, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v20);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\copilotcapabilityusagehistoryserver.cpp",
        (const char *)(unsigned int)v9,
        v18);
    string = 0;
    v10 = v20;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, &string);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\copilotcapabilityusagehistoryserver.cpp",
        (const char *)(unsigned int)v12,
        v18);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v22, StringRawBuffer);
    v14 = WindowsDuplicateString(v22[0], a2);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\copilotcapabilityusagehistoryserver.cpp",
        (const char *)(unsigned int)v14,
        v18);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x36,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\copilotcapabilityusagehistoryserver.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180091680  mov     [rsp+arg_10], rbx
0x180091685  mov     [rsp+arg_18], rsi
0x18009168a  push    rdi
0x18009168b  sub     rsp, 70h
0x18009168f  mov     rax, cs:__security_cookie
0x180091696  xor     rax, rsp
0x180091699  mov     [rsp+78h+var_10], rax
0x18009169e  mov     rsi, rdx
0x1800916a1  mov     rbx, rcx
0x1800916a4  mov     rcx, [rsp+78h]; this
0x1800916a9  test    rdx, rdx
0x1800916ac  jz      loc_180091822
0x1800916b2  mov     [rsp+78h+var_38], 0
0x1800916bb  lea     rcx, [rsp+78h+var_30]; string
0x1800916c0  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800916c5  lea     rdx, [rsp+78h+var_38]
0x1800916ca  mov     rcx, [rax]
0x1800916cd  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800916d2  mov     rcx, [rsp+78h]; this
0x1800916d7  test    eax, eax
0x1800916d9  js      loc_180091838
0x1800916df  lea     r8, [rbx+40h]
0x1800916e3  lea     rdx, [rbx+20h]
0x1800916e7  mov     eax, [rbx+60h]
0x1800916ea  mov     [rsp+78h+var_58], eax; int
0x1800916ee  mov     r9d, 2710h
0x1800916f4  lea     rcx, [rsp+78h+var_30]
0x1800916f9  call    ?GetRecordStubsFromUsageHistoryTables@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0II@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetRecordStubsFromUsageHistoryTables(std::wstring const &,std::wstring const &,uint,uint)
0x1800916fe  nop
0x1800916ff  lea     rdx, [rsp+78h+var_38]
0x180091704  mov     rcx, rax
0x180091707  call    ?FormatRecentActivityRecords@Private@CapabilityAccess@Internal@Windows@@YAXAEBV?$vector@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; Windows::Internal::CapabilityAccess::Private::FormatRecentActivityRecords(std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18009170c  nop
0x18009170d  lea     rcx, [rsp+78h+var_30]
0x180091712  call    ?_Tidy@?$vector@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub>::_Tidy(void)
0x180091717  mov     [rsp+78h+var_40], 0
0x180091720  mov     rbx, [rsp+78h+var_38]
0x180091725  mov     rax, [rbx]
0x180091728  mov     rdi, [rax]
0x18009172b  lea     rcx, [rsp+78h+var_40]
0x180091730  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180091735  lea     r8, [rsp+78h+var_40]
0x18009173a  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180091741  mov     rcx, rbx
0x180091744  mov     rax, rdi
0x180091747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009174c  nop
0x18009174d  mov     rcx, [rsp+78h]; this
0x180091752  test    eax, eax
0x180091754  js      loc_18009184D
0x18009175a  mov     [rsp+78h+string], 0
0x180091763  mov     rdi, [rsp+78h+var_40]
0x180091768  mov     rax, [rdi]
0x18009176b  mov     rbx, [rax+38h]
0x18009176f  xor     ecx, ecx; string
0x180091771  call    cs:__imp_WindowsDeleteString
0x180091777  mov     [rsp+78h+string], 0
0x180091780  lea     rdx, [rsp+78h+string]
0x180091785  mov     rcx, rdi
0x180091788  mov     rax, rbx
0x18009178b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091790  mov     rcx, [rsp+78h]; this
0x180091795  test    eax, eax
0x180091797  js      loc_180091862
0x18009179d  xor     edx, edx; length
0x18009179f  mov     rcx, [rsp+78h+string]; string
0x1800917a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800917aa  mov     rdx, rax; unsigned __int16 *
0x1800917ad  lea     rcx, [rsp+78h+var_30]; this
0x1800917b2  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800917b7  mov     rdx, rsi; newString
0x1800917ba  mov     rcx, [rsp+78h+var_30]; string
0x1800917bf  call    cs:__imp_WindowsDuplicateString
0x1800917c5  mov     rcx, [rsp+78h]; this
0x1800917ca  test    eax, eax
0x1800917cc  js      loc_180091876
0x1800917d2  mov     rcx, [rsp+78h+string]; string
0x1800917d7  call    cs:__imp_WindowsDeleteString
0x1800917dd  mov     [rsp+78h+string], 0
0x1800917e6  lea     rcx, [rsp+78h+var_40]
0x1800917eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800917f0  nop
0x1800917f1  lea     rcx, [rsp+78h+var_38]
0x1800917f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800917fb  xor     eax, eax
0x1800917fd  jmp     short loc_180091803
0x1800917ff  mov     eax, dword ptr [rsp+78h+string]
0x180091803  mov     rcx, [rsp+78h+var_10]
0x180091808  xor     rcx, rsp; StackCookie
0x18009180b  call    __security_check_cookie
0x180091810  lea     r11, [rsp+78h+var_8]
0x180091815  mov     rbx, [r11+20h]
0x180091819  mov     rsi, [r11+28h]
0x18009181d  mov     rsp, r11
0x180091820  pop     rdi
0x180091821  retn
0x180091822  mov     r9d, 80004003h; char *
0x180091828  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18009182f  lea     edx, [rsi+23h]; void *
0x180091832  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180091838  mov     r9d, eax; char *
0x18009183b  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180091842  mov     edx, 26h ; '&'; void *
0x180091847  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009184d  mov     r9d, eax; char *
0x180091850  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180091857  mov     edx, 2Dh ; '-'; void *
0x18009185c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180091862  mov     r9d, eax; char *
0x180091865  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18009186c  mov     edx, 30h ; '0'; void *
0x180091871  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180091876  mov     r9d, eax; char *
0x180091879  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180091880  mov     edx, 32h ; '2'; void *
0x180091885  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

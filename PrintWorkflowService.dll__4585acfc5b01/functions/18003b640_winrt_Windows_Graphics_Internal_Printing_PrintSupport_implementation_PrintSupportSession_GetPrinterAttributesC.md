# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::GetPrinterAttributesCache(void)

- ea: `0x18003b640`
- end: `0x18003b88d`
- name: `?GetPrinterAttributesCache@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA?AUIBuffer@Streams@Storage@78@XZ`
- size: `589`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c180`

## callees

- `0x180001314`
- `0x180003ca0`
- `0x180010b0c`
- `0x180012754`
- `0x1800127a4`
- `0x180012820`
- `0x1800129dc`
- `0x1800213ac`
- `0x180023664`
- `0x1800387b4`
- `0x18003a2bc`
- `0x18003b640`
- `0x18003cd4c`
- `0x1800403b4`
- `0x1800405a0`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003b6be`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003b6be`
- `ntdll!RtlIsMultiSessionSku` at `0x18003b6f4`
- `ntdll!RtlIsMultiSessionSku` at `0x18003b6f4`
- `WINSPOOL!OpenPrinterW` at `0x18003b77b`
- `WINSPOOL!OpenPrinterW` at `0x18003b77b`
- `Print.PrintSupport.Source!IsPrinterConnection` at `0x18003b72c`
- `Print.PrintSupport.Source!IsPrinterConnection` at `0x18003b72c`

## string_xrefs

- `0x18003b7c3`: `OneCoreUap\Internal\Printscan\inc\ippprinterattributescache.hxx`
- `0x18003b73d`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`
- `0x18003b860`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`
- `0x18003b878`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::GetPrinterAttributesCache(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // eax
  char v5; // al
  const unsigned __int16 *v6; // rax
  int v7; // eax
  WCHAR *v8; // rax
  const char *v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  int v13; // [rsp+20h] [rbp-29h] BYREF
  HANDLE phPrinter; // [rsp+28h] [rbp-21h] BYREF
  __int64 v15; // [rsp+30h] [rbp-19h] BYREF
  int v16; // [rsp+38h] [rbp-11h]
  __int128 v17; // [rsp+40h] [rbp-9h] BYREF
  __int64 v18; // [rsp+50h] [rbp+7h]
  _BYTE v19[8]; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  phPrinter = a2;
  if ( !winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::IsSessionActive(*(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler **)(a1 + 544)) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
      (const char *)0x8000000ELL,
      v13);
  if ( (unsigned int)dword_180083000 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180083000,
      &byte_180073C57,
      0);
  if ( `Details::GetDeviceFamily'::`2'::s_hasChecked )
  {
    v4 = `Details::GetDeviceFamily'::`2'::s_platform;
  }
  else
  {
    LODWORD(phPrinter) = 0;
    RtlGetDeviceFamilyInfoEnum(0, &phPrinter, 0);
    v4 = (int)phPrinter;
    `Details::GetDeviceFamily'::`2'::s_platform = (int)phPrinter;
    `Details::GetDeviceFamily'::`2'::s_hasChecked = 1;
  }
  if ( v4 != 3 && v4 != 9 )
  {
    if ( v4 != 6 )
      goto LABEL_17;
    if ( `Details::GetIsMultiSessionSku'::`2'::s_hasChecked )
    {
      v5 = `Details::GetIsMultiSessionSku'::`2'::s_isMultiSession;
    }
    else
    {
      v5 = (unsigned __int8)RtlIsMultiSessionSku() != 0;
      `Details::GetIsMultiSessionSku'::`2'::s_isMultiSession = v5;
      `Details::GetIsMultiSessionSku'::`2'::s_hasChecked = 1;
    }
    if ( !v5 )
      goto LABEL_17;
  }
  LOBYTE(v13) = 0;
  v6 = winrt::hstring::c_str((winrt::hstring *)(a1 + 88));
  v7 = IsPrinterConnection(v6, &v13);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
      (const char *)(unsigned int)v7,
      v13);
  if ( !(_BYTE)v13 )
  {
    phPrinter = 0;
    v8 = (WCHAR *)winrt::hstring::c_str((winrt::hstring *)(a1 + 88));
    if ( !OpenPrinterW(v8, &phPrinter, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x30C,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
        v9);
    PrintCore::IppPrinterAttributesCache::IppPrinterAttributesCache(
      (PrintCore::IppPrinterAttributesCache *)v19,
      phPrinter);
    v17 = 0;
    v18 = 0;
    v11 = PrintCore::IppPrinterAttributesCache::_FileToBuffer(v10, (__int64)v20, (LPVOID *)&v17);
    if ( v11 >= 0 )
    {
      if ( (unsigned int)dword_180083000 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_180083000,
          qword_180073C90,
          0);
      v15 = v17;
      v16 = DWORD2(v17) - v17;
      winrt::Windows::Security::Cryptography::CryptographicBuffer::CreateFromByteArray(a2, &v15);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\ippprinterattributescache.hxx",
        (const char *)(unsigned int)v11,
        v13);
      *a2 = 0;
    }
    std::vector<unsigned char>::_Tidy(&v17);
    std::wstring::_Tidy_deallocate(v20);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
  }
  else
  {
LABEL_17:
    *a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18003b640  mov     [rsp-8+arg_10], rbx
0x18003b645  push    rbp
0x18003b646  push    rsi
0x18003b647  push    rdi
0x18003b648  lea     rbp, [rsp-47h]
0x18003b64d  sub     rsp, 90h
0x18003b654  mov     rax, cs:__security_cookie
0x18003b65b  xor     rax, rsp
0x18003b65e  mov     [rbp+57h+var_18], rax
0x18003b662  mov     rbx, rdx
0x18003b665  mov     rsi, rcx
0x18003b668  mov     [rbp+57h+phPrinter], rdx
0x18003b66c  mov     rdi, [rbp+5Fh]
0x18003b670  mov     rcx, [rcx+220h]; this
0x18003b677  call    ?IsSessionActive@SessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA_NXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::IsSessionActive(void)
0x18003b67c  test    al, al
0x18003b67e  jz      loc_18003B872
0x18003b684  mov     eax, cs:dword_180083000
0x18003b68a  cmp     eax, 5
0x18003b68d  jbe     short loc_18003B6A5
0x18003b68f  xor     r8d, r8d
0x18003b692  lea     rdx, byte_180073C57
0x18003b699  lea     rcx, dword_180083000
0x18003b6a0  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003b6a5  cmp     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, 0; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18003b6ac  jnz     short loc_18003B6D6
0x18003b6ae  mov     dword ptr [rbp+57h+phPrinter], 0
0x18003b6b5  xor     r8d, r8d
0x18003b6b8  lea     rdx, [rbp+57h+phPrinter]
0x18003b6bc  xor     ecx, ecx
0x18003b6be  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003b6c4  mov     eax, dword ptr [rbp+57h+phPrinter]
0x18003b6c7  mov     cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA, eax; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18003b6cd  mov     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, 1; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18003b6d4  jmp     short loc_18003B6DC
0x18003b6d6  mov     eax, cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18003b6dc  cmp     eax, 3
0x18003b6df  jz      short loc_18003B718
0x18003b6e1  cmp     eax, 9
0x18003b6e4  jz      short loc_18003B718
0x18003b6e6  cmp     eax, 6
0x18003b6e9  jnz     short loc_18003B754
0x18003b6eb  cmp     cs:?s_hasChecked@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA, 0; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_hasChecked
0x18003b6f2  jnz     short loc_18003B70E
0x18003b6f4  call    cs:__imp_RtlIsMultiSessionSku
0x18003b6fa  test    al, al
0x18003b6fc  setnz   al
0x18003b6ff  mov     cs:?s_isMultiSession@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA, al; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_isMultiSession
0x18003b705  mov     cs:?s_hasChecked@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA, 1; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_hasChecked
0x18003b70c  jmp     short loc_18003B714
0x18003b70e  mov     al, cs:?s_isMultiSession@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_isMultiSession
0x18003b714  test    al, al
0x18003b716  jz      short loc_18003B754
0x18003b718  mov     byte ptr [rbp+57h+var_80], 0
0x18003b71c  lea     rcx, [rsi+58h]; this
0x18003b720  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18003b725  mov     rcx, rax
0x18003b728  lea     rdx, [rbp+57h+var_80]
0x18003b72c  call    cs:__imp_IsPrinterConnection
0x18003b732  mov     rcx, [rbp+5Fh]; this
0x18003b736  test    eax, eax
0x18003b738  jns     short loc_18003B74E
0x18003b73a  mov     r9d, eax; char *
0x18003b73d  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003b744  mov     edx, 302h; void *
0x18003b749  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b74e  cmp     byte ptr [rbp+57h+var_80], 0
0x18003b752  jz      short loc_18003B760
0x18003b754  mov     qword ptr [rbx], 0
0x18003b75b  jmp     loc_18003B83E
0x18003b760  mov     [rbp+57h+phPrinter], 0
0x18003b768  lea     rcx, [rsi+58h]; this
0x18003b76c  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18003b771  xor     r8d, r8d; pDefault
0x18003b774  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x18003b778  mov     rcx, rax; pPrinterName
0x18003b77b  call    cs:__imp_OpenPrinterW
0x18003b781  mov     rcx, [rbp+5Fh]; this
0x18003b785  test    eax, eax
0x18003b787  jz      loc_18003B860
0x18003b78d  mov     rdx, [rbp+57h+phPrinter]; void *
0x18003b791  lea     rcx, [rbp+57h+var_40]; this
0x18003b795  call    ??0IppPrinterAttributesCache@PrintCore@@QEAA@PEAX@Z; PrintCore::IppPrinterAttributesCache::IppPrinterAttributesCache(void *)
0x18003b79a  nop
0x18003b79b  xorps   xmm0, xmm0
0x18003b79e  movdqu  [rbp+57h+var_60], xmm0
0x18003b7a3  mov     [rbp+57h+var_50], 0
0x18003b7ab  lea     r8, [rbp+57h+var_60]
0x18003b7af  lea     rdx, [rbp+57h+var_38]
0x18003b7b3  call    ?_FileToBuffer@IppPrinterAttributesCache@PrintCore@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; PrintCore::IppPrinterAttributesCache::_FileToBuffer(std::wstring const &,std::vector<uchar> &)
0x18003b7b8  test    eax, eax
0x18003b7ba  jns     short loc_18003B7DD
0x18003b7bc  mov     rcx, [rbp+5Fh]; this
0x18003b7c0  mov     r9d, eax; char *
0x18003b7c3  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\i"...
0x18003b7ca  mov     edx, 1Eh; void *
0x18003b7cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b7d4  mov     qword ptr [rbx], 0
0x18003b7db  jmp     short loc_18003B821
0x18003b7dd  mov     eax, cs:dword_180083000
0x18003b7e3  cmp     eax, 5
0x18003b7e6  jbe     short loc_18003B7FE
0x18003b7e8  xor     r8d, r8d
0x18003b7eb  lea     rdx, qword_180073C90
0x18003b7f2  lea     rcx, dword_180083000
0x18003b7f9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003b7fe  mov     rcx, qword ptr [rbp+57h+var_60]
0x18003b802  mov     [rbp+57h+var_70], rcx
0x18003b806  mov     eax, dword ptr [rbp+57h+var_60+8]
0x18003b809  sub     eax, ecx
0x18003b80b  mov     [rbp+57h+var_68], eax
0x18003b80e  mov     eax, [rbp+57h+var_64]
0x18003b811  mov     [rbp+57h+var_64], eax
0x18003b814  lea     rdx, [rbp+57h+var_70]
0x18003b818  mov     rcx, rbx
0x18003b81b  call    ?CreateFromByteArray@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@U?$array_view@$$CBE@5@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::CreateFromByteArray(winrt::array_view<uchar const>)
0x18003b820  nop
0x18003b821  lea     rcx, [rbp+57h+var_60]
0x18003b825  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003b82a  nop
0x18003b82b  lea     rcx, [rbp+57h+var_38]
0x18003b82f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b834  nop
0x18003b835  lea     rcx, [rbp+57h+phPrinter]
0x18003b839  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003b83e  mov     rax, rbx
0x18003b841  mov     rcx, [rbp+57h+var_18]
0x18003b845  xor     rcx, rsp; StackCookie
0x18003b848  call    __security_check_cookie
0x18003b84d  mov     rbx, [rsp+0A0h+arg_10]
0x18003b855  add     rsp, 90h
0x18003b85c  pop     rdi
0x18003b85d  pop     rsi
0x18003b85e  pop     rbp
0x18003b85f  retn
0x18003b860  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003b867  mov     edx, 30Ch; void *
0x18003b86c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003b872  mov     r9d, 8000000Eh; char *
0x18003b878  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003b87f  mov     edx, 2F9h; void *
0x18003b884  mov     rcx, rdi; this
0x18003b887  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort(VirtualMon::VirtualPrinterInfo const &)

- ea: `0x18003666c`
- end: `0x18003682b`
- name: `?CreateVirtualMonPort@VirtualPrinterInstaller@VirtualMon@@AEAAJAEBUVirtualPrinterInfo@2@@Z`
- size: `447`
- prototype: `__int64 __fastcall(VirtualMon::VirtualPrinterInstaller *__hidden this, const struct VirtualMon::VirtualPrinterInfo *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x1800362f8`
- `0x180036ca0`

## callees

- `0x18000fa2c`
- `0x18000fb60`
- `0x1800182ec`
- `0x18001cfb4`
- `0x18002f194`
- `0x18003666c`
- `0x180037388`
- `0x180037f28`
- `0x180038174`

## import_xrefs

- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x1800366c9`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x1800366c9`
- `ext-ms-win-printer-winspool-l1-1-4!XcvDataW` at `0x180036745`
- `ext-ms-win-printer-winspool-l1-1-4!XcvDataW` at `0x180036745`

## string_xrefs

- `0x180036739`: `CreatePort`
- `0x1800367f0`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036804`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036818`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x18003668f`: `VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort`
- `0x18003675f`: `VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort(
        VirtualMon::VirtualPrinterInstaller *this,
        const struct VirtualMon::VirtualPrinterInfo *a2)
{
  const struct VirtualMon::VirtualPrinterInfo *v2; // rbx
  const struct VirtualMon::VirtualPrinterInfo *v3; // r8
  const char *v4; // r9
  BYTE *v5; // rax
  int v6; // r9d
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  __int64 result; // rax
  char v11; // al
  int pOutputData; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pdwStatus; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbOutputNeeded; // [rsp+68h] [rbp+10h] BYREF
  HANDLE phPrinter; // [rsp+70h] [rbp+18h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h] BYREF

  v2 = a2;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v3 = a2;
  else
    v3 = *(const struct VirtualMon::VirtualPrinterInfo **)a2;
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort",
    L"PortName: %ws",
    v3);
  try
  {
    VirtualMon::VirtualPrinterJsonHelper::Serialize();
    phPrinter = 0;
    if ( !OpenPrinterW((LPWSTR)L",XcvMonitor Virtual Port Monitor", &phPrinter, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
        v4);
    pcbOutputNeeded = 0;
    pdwStatus = 0;
    v5 = (BYTE *)winrt::hstring::c_str((winrt::hstring *)&v17);
    if ( !XcvDataW(phPrinter, L"CreatePort", v5, 2 * v6 + 2, 0, 0, &pcbOutputNeeded, &pdwStatus) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
        v7);
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort",
      L"XcvData rc: %d",
      pdwStatus);
    v8 = (const char *)pdwStatus;
    if ( pdwStatus == 183 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
      result = 2147942583LL;
    }
    else
    {
      if ( pdwStatus )
      {
        v11 = 0;
        if ( (int)pdwStatus > 0 )
          v8 = (const char *)((unsigned __int16)pdwStatus | 0x80070000);
      }
      else
      {
        v11 = 1;
      }
      if ( !v11 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
          v8,
          pOutputData);
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(const struct VirtualMon::VirtualPrinterInfo **)v2;
      VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort(retaddr, (const unsigned __int16 *)v2);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC0,
                           (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18003666c  push    rbx
0x18003666e  push    rdi
0x18003666f  sub     rsp, 48h
0x180036673  mov     rbx, rdx
0x180036676  mov     rdi, rcx
0x180036679  cmp     qword ptr [rdx+18h], 7
0x18003667e  jbe     short loc_180036685
0x180036680  mov     r8, [rdx]
0x180036683  jmp     short loc_180036688
0x180036685  mov     r8, rbx
0x180036688  lea     rdx, aPortnameWs; "PortName: %ws"
0x18003668f  lea     rcx, aVirtualmonVirt_5; "VirtualMon::VirtualPrinterInstaller::Cr"...
0x180036696  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003669b  mov     r8, rdi
0x18003669e  mov     rdx, rbx
0x1800366a1  lea     rcx, [rsp+58h+arg_18]
0x1800366a6  call    ?Serialize@VirtualPrinterJsonHelper@VirtualMon@@SA?AUhstring@winrt@@AEBUVirtualPrinterInfo@2@AEBUVirtualPrinterAppInfo@2@@Z; VirtualMon::VirtualPrinterJsonHelper::Serialize(VirtualMon::VirtualPrinterInfo const &,VirtualMon::VirtualPrinterAppInfo const &)
0x1800366ab  nop
0x1800366ac  mov     [rsp+58h+phPrinter], 0
0x1800366b5  mov     rdi, [rsp+58h]
0x1800366ba  xor     r8d, r8d; pDefault
0x1800366bd  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x1800366c2  lea     rcx, pPrinterName; ",XcvMonitor Virtual Port Monitor"
0x1800366c9  call    cs:__imp_OpenPrinterW
0x1800366cf  test    eax, eax
0x1800366d1  jz      loc_1800367F0
0x1800366d7  mov     [rsp+58h+arg_8], 0
0x1800366df  mov     [rsp+58h+arg_0], 0
0x1800366e7  mov     rax, [rsp+58h+arg_18]
0x1800366ec  test    rax, rax
0x1800366ef  jz      short loc_1800366F7
0x1800366f1  mov     r9d, [rax+4]
0x1800366f5  jmp     short loc_1800366FA
0x1800366f7  xor     r9d, r9d
0x1800366fa  lea     rcx, [rsp+58h+arg_18]; this
0x1800366ff  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180036704  mov     rdi, [rsp+58h]
0x180036709  lea     r9d, ds:2[r9*2]; cbInputData
0x180036711  lea     rcx, [rsp+58h+arg_0]
0x180036716  mov     [rsp+58h+pdwStatus], rcx; pdwStatus
0x18003671b  lea     rcx, [rsp+58h+arg_8]
0x180036720  mov     [rsp+58h+pcbOutputNeeded], rcx; pcbOutputNeeded
0x180036725  mov     [rsp+58h+cbOutputData], 0; cbOutputData
0x18003672d  mov     [rsp+58h+pOutputData], 0; int
0x180036736  mov     r8, rax; pInputData
0x180036739  lea     rdx, pszDataName; "CreatePort"
0x180036740  mov     rcx, [rsp+58h+phPrinter]; hXcv
0x180036745  call    cs:__imp_XcvDataW
0x18003674b  test    eax, eax
0x18003674d  jz      loc_180036804
0x180036753  mov     r8d, [rsp+58h+arg_0]
0x180036758  lea     rdx, aXcvdataRcD; "XcvData rc: %d"
0x18003675f  lea     rcx, aVirtualmonVirt_5; "VirtualMon::VirtualPrinterInstaller::Cr"...
0x180036766  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003676b  mov     r9d, [rsp+58h+arg_0]
0x180036770  cmp     r9d, 0B7h
0x180036777  jnz     short loc_180036795
0x180036779  lea     rcx, [rsp+58h+phPrinter]
0x18003677e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180036783  nop
0x180036784  lea     rcx, [rsp+58h+arg_18]
0x180036789  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003678e  mov     eax, 800700B7h
0x180036793  jmp     short loc_1800367E9
0x180036795  test    r9d, r9d
0x180036798  jnz     short loc_18003679E
0x18003679a  mov     al, 1
0x18003679c  jmp     short loc_1800367B0
0x18003679e  xor     al, al
0x1800367a0  test    r9d, r9d
0x1800367a3  jle     short loc_1800367B0
0x1800367a5  movzx   r9d, r9w
0x1800367a9  or      r9d, 80070000h; char *
0x1800367b0  mov     rcx, [rsp+58h]; this
0x1800367b5  test    al, al
0x1800367b7  jz      short loc_180036818
0x1800367b9  cmp     qword ptr [rbx+18h], 7
0x1800367be  jbe     short loc_1800367C3
0x1800367c0  mov     rbx, [rbx]
0x1800367c3  mov     rdx, rbx; unsigned __int16 *
0x1800367c6  call    ?ValidateVirtualPrinterPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG@Z; VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort(ushort const *)
0x1800367cb  nop
0x1800367cc  lea     rcx, [rsp+58h+phPrinter]
0x1800367d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800367d6  nop
0x1800367d7  lea     rcx, [rsp+58h+arg_18]
0x1800367dc  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800367e1  xor     eax, eax
0x1800367e3  jmp     short loc_1800367E9
0x1800367e5  mov     eax, [rsp+58h+arg_0]
0x1800367e9  add     rsp, 48h
0x1800367ed  pop     rdi
0x1800367ee  pop     rbx
0x1800367ef  retn
0x1800367f0  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800367f7  mov     edx, 0AEh; void *
0x1800367fc  mov     rcx, rdi; this
0x1800367ff  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180036804  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x18003680b  mov     edx, 0B4h; void *
0x180036810  mov     rcx, rdi; this
0x180036813  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180036818  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x18003681f  mov     edx, 0B9h; void *
0x180036824  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

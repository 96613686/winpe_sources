# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetPrinterDeviceId(void *)

- ea: `0x1800229ac`
- end: `0x180022b3e`
- name: `?_GetPrinterDeviceId@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002250c`

## callees

- `0x180002d40`
- `0x18000fa2c`
- `0x180012498`
- `0x1800182cc`
- `0x18001d058`
- `0x18001d0e4`
- `0x1800229ac`
- `0x1800232bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180022aa9`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180022aa9`
- `Print.PrintSupport.Source!GetDeviceContainerIdByPrinterName` at `0x180022adc`
- `Print.PrintSupport.Source!GetDeviceContainerIdByPrinterName` at `0x180022adc`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x180022a6c`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x180022a6c`
- `IppCommon!IsIppPrinterConnection` at `0x1800229ef`
- `IppCommon!IsIppPrinterConnection` at `0x1800229ef`

## string_xrefs

- `0x180022a08`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022a85`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022af6`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022aaf`: `StringFromCLSID failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetPrinterDeviceId(
        __int64 a1,
        __int64 a2,
        void *a3)
{
  winrt::hstring *v5; // rdi
  const unsigned __int16 *v6; // rax
  unsigned int v7; // eax
  DWORD PrinterData; // eax
  unsigned int v9; // eax
  const unsigned __int16 *v10; // rax
  unsigned int DeviceContainerIdByPrinterName; // eax
  const char *nSize; // [rsp+28h] [rbp-58h]
  const char *nSizea; // [rsp+28h] [rbp-58h]
  const char *nSizeb; // [rsp+28h] [rbp-58h]
  const char *nSizec; // [rsp+28h] [rbp-58h]
  _BYTE v17[8]; // [rsp+40h] [rbp-40h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-38h] BYREF
  DWORD pcbNeeded; // [rsp+50h] [rbp-30h] BYREF
  DWORD pType[4]; // [rsp+58h] [rbp-28h] BYREF
  BYTE pData[16]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_QWORD *)pType = a2;
  v17[0] = 0;
  v5 = (winrt::hstring *)(a1 + 24);
  v6 = winrt::hstring::c_str((winrt::hstring *)(a1 + 24));
  v7 = IsIppPrinterConnection(v6, 0, v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3E5,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)v7,
    (int)"IsIppPrinterConnection failed!",
    nSize);
  lpsz = 0;
  if ( v17[0] )
  {
    pType[0] = 0;
    *(_OWORD *)pData = 0;
    pcbNeeded = 16;
    PrinterData = GetPrinterDataExW(a3, L"PnPData", L"DeviceContainerId", pType, pData, 0x10u, &pcbNeeded);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x3F0,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)PrinterData,
      (unsigned int)"GetPrinterDataEx for Device Container Id failed!",
      nSizeb);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v9 = StringFromCLSID((const IID *const)pData, &lpsz);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x3F1,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)v9,
      (int)"StringFromCLSID failed!",
      nSizec);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v10 = winrt::hstring::c_str(v5);
    DeviceContainerIdByPrinterName = GetDeviceContainerIdByPrinterName(v10, &lpsz);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)DeviceContainerIdByPrinterName,
      (int)"GetDeviceContainerIdByPrinterName failed!",
      nSizea);
  }
  std::wstring::wstring(a2, (__int64)lpsz);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpsz);
  return a2;
}

```

## disassembly

```asm
0x1800229ac  mov     [rsp-18h+arg_18], rbx
0x1800229b1  push    rbp
0x1800229b2  push    rsi
0x1800229b3  push    rdi
0x1800229b4  mov     rbp, rsp
0x1800229b7  sub     rsp, 80h
0x1800229be  mov     rax, cs:__security_cookie
0x1800229c5  xor     rax, rsp
0x1800229c8  mov     [rbp+var_8], rax
0x1800229cc  mov     rsi, r8
0x1800229cf  mov     rbx, rdx
0x1800229d2  mov     qword ptr [rbp+pType], rdx
0x1800229d6  mov     [rbp+var_40], 0
0x1800229da  lea     rdi, [rcx+18h]
0x1800229de  mov     rcx, rdi; this
0x1800229e1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800229e6  mov     rcx, rax
0x1800229e9  lea     r8, [rbp+var_40]
0x1800229ed  xor     edx, edx
0x1800229ef  call    cs:__imp_IsIppPrinterConnection
0x1800229f5  mov     rcx, [rbp+18h]; this
0x1800229f9  lea     rdx, aIsippprinterco_0; "IsIppPrinterConnection failed!"
0x180022a00  mov     [rsp+80h+pData], rdx; int
0x180022a05  mov     r9d, eax; char *
0x180022a08  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022a0f  mov     edx, 3E5h; void *
0x180022a14  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180022a19  mov     [rbp+lpsz], 0
0x180022a21  cmp     [rbp+var_40], 0
0x180022a25  jz      loc_180022AC2
0x180022a2b  mov     [rbp+pType], 0
0x180022a32  xorps   xmm0, xmm0
0x180022a35  movups  xmmword ptr [rbp+var_18], xmm0
0x180022a39  mov     ecx, 10h
0x180022a3e  mov     [rbp+var_30], ecx
0x180022a41  lea     rax, [rbp+var_30]
0x180022a45  mov     [rsp+80h+pcbNeeded], rax; pcbNeeded
0x180022a4a  mov     dword ptr [rsp+80h+nSize], ecx; char *
0x180022a4e  lea     rax, [rbp+var_18]
0x180022a52  mov     [rsp+80h+pData], rax; pData
0x180022a57  lea     r9, [rbp+pType]; pType
0x180022a5b  lea     r8, aDevicecontaine; "DeviceContainerId"
0x180022a62  lea     rdx, aPnpdata; "PnPData"
0x180022a69  mov     rcx, rsi; hPrinter
0x180022a6c  call    cs:__imp_GetPrinterDataExW
0x180022a72  mov     r9d, eax; char *
0x180022a75  mov     rcx, [rbp+18h]; this
0x180022a79  lea     rax, aGetprinterdata_0; "GetPrinterDataEx for Device Container I"...
0x180022a80  mov     [rsp+80h+pData], rax; unsigned int
0x180022a85  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022a8c  mov     edx, 3F0h; void *
0x180022a91  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180022a96  xor     edx, edx
0x180022a98  lea     rcx, [rbp+lpsz]
0x180022a9c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022aa1  lea     rdx, [rbp+lpsz]; lplpsz
0x180022aa5  lea     rcx, [rbp+var_18]; rclsid
0x180022aa9  call    cs:__imp_StringFromCLSID
0x180022aaf  lea     rdx, aStringfromclsi; "StringFromCLSID failed!"
0x180022ab6  mov     [rsp+80h+pData], rdx
0x180022abb  mov     edx, 3F1h
0x180022ac0  jmp     short loc_180022AF3
0x180022ac2  xor     edx, edx
0x180022ac4  lea     rcx, [rbp+lpsz]
0x180022ac8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022acd  mov     rcx, rdi; this
0x180022ad0  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180022ad5  lea     rdx, [rbp+lpsz]
0x180022ad9  mov     rcx, rax
0x180022adc  call    cs:__imp_GetDeviceContainerIdByPrinterName
0x180022ae2  lea     rdx, aGetdeviceconta_0; "GetDeviceContainerIdByPrinterName faile"...
0x180022ae9  mov     [rsp+80h+pData], rdx; int
0x180022aee  mov     edx, 3F5h; void *
0x180022af3  mov     r9d, eax; char *
0x180022af6  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022afd  mov     rcx, [rbp+18h]; this
0x180022b01  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180022b06  mov     rdx, [rbp+lpsz]
0x180022b0a  mov     rcx, rbx
0x180022b0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022b12  nop
0x180022b13  lea     rcx, [rbp+lpsz]
0x180022b17  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180022b1c  mov     rax, rbx
0x180022b1f  mov     rcx, [rbp+var_8]
0x180022b23  xor     rcx, rsp; StackCookie
0x180022b26  call    __security_check_cookie
0x180022b2b  mov     rbx, [rsp+80h+arg_18]
0x180022b33  add     rsp, 80h
0x180022b3a  pop     rdi
0x180022b3b  pop     rsi
0x180022b3c  pop     rbp
0x180022b3d  retn
```

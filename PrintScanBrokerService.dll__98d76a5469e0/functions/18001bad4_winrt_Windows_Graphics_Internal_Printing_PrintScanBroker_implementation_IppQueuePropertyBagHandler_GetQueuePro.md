# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::GetQueuePropertyBag(void)

- ea: `0x18001bad4`
- end: `0x18001bdeb`
- name: `?GetQueuePropertyBag@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@QEAA?AUValueSet@Collections@Foundation@78@XZ`
- size: `791`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ba80`

## callees

- `0x180002d40`
- `0x18000792c`
- `0x18000f8a8`
- `0x18000fa2c`
- `0x18000fb60`
- `0x180010ef0`
- `0x1800182ec`
- `0x18001bad4`
- `0x18001cf40`
- `0x18001cfb4`
- `0x18001d0e4`
- `0x18001f5fc`
- `0x18002250c`
- `0x180022b44`
- `0x180022dac`
- `0x180022ef0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bd8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bd8e`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x18001bbbe`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x18001bcaa`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x18001bbbe`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x18001bcaa`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18001bb59`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18001bb59`

## string_xrefs

- `0x18001bb7c`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001bcc7`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001bdbe`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001bdd9`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001bb6c`: `Failed to open printer`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::GetQueuePropertyBag(
        winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *a1,
        __int64 a2)
{
  __int64 v2; // r14
  winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *v3; // rdi
  char v4; // si
  WCHAR *v5; // rax
  BOOL v6; // eax
  signed int PrinterData; // eax
  bool v8; // cc
  char v9; // cl
  BYTE *v10; // rcx
  DWORD v11; // eax
  LPBYTE *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  __int64 v16; // [rsp+0h] [rbp-E8h] BYREF
  LPBYTE pData; // [rsp+20h] [rbp-C8h]
  const char *nSize; // [rsp+28h] [rbp-C0h]
  bool v19; // [rsp+40h] [rbp-A8h] BYREF
  DWORD pcbNeeded; // [rsp+44h] [rbp-A4h] BYREF
  DWORD pType; // [rsp+48h] [rbp-A0h] BYREF
  HANDLE phPrinter; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v23[16]; // [rsp+58h] [rbp-90h] BYREF
  winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *v24; // [rsp+68h] [rbp-80h]
  __int64 v25; // [rsp+70h] [rbp-78h]
  _PRINTER_DEFAULTSW pDefault; // [rsp+78h] [rbp-70h] BYREF
  bool *v27; // [rsp+90h] [rbp-58h]
  char v28; // [rsp+98h] [rbp-50h]
  LPBYTE v29[2]; // [rsp+A0h] [rbp-48h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v2 = a2;
  v3 = a1;
  v24 = a1;
  v25 = a2;
  v19 = winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ImpersonateUserIfNeeded(a1);
  v27 = &v19;
  v4 = 1;
  v28 = 1;
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 64;
  phPrinter = 0;
  v5 = (WCHAR *)winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *)((char *)v3 + 24));
  v6 = OpenPrinterW(v5, &phPrinter, &pDefault);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x4E,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)v6,
    (bool)"Failed to open printer",
    nSize);
  pType = 0;
  pcbNeeded = 0;
  PrinterData = GetPrinterDataExW(phPrinter, L"PrinterDriverData", L"IppQueuePropertyBag", &pType, 0, 0, &pcbNeeded);
  if ( PrinterData == 2 || !pcbNeeded )
  {
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetDefaultQueuePropertyBag(
      v3,
      v23,
      phPrinter);
    try
    {
      winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_PropertyBagAccessCheck(v3);
      winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_InternalSetQueuePropertyBag(
        v3,
        0,
        (const struct winrt::hstring *)v23);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(retaddr, &v16, v13, v14);
      v3 = v24;
      v2 = v25;
    }
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertJsonToValueSet(
      v3,
      v2,
      v23);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v23);
  }
  else
  {
    if ( PrinterData == 234 || (v8 = PrinterData <= 0, v9 = 1, !PrinterData) )
    {
      v9 = 0;
      v8 = PrinterData <= 0;
    }
    if ( !v8 )
      PrinterData = (unsigned __int16)PrinterData | 0x80070000;
    if ( v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
        (const char *)(unsigned int)PrinterData,
        (int)pData);
    if ( pType == 1 || pType == 7 )
      v4 = 0;
    if ( v4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
        (const char *)0x8007139FLL,
        (int)pData);
    *(_OWORD *)v29 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v29[0]) = 0;
    std::wstring::resize(v29, (unsigned __int64)pcbNeeded >> 1);
    v10 = (BYTE *)v29;
    if ( si128.m128i_i64[1] > 7uLL )
      v10 = v29[0];
    v11 = GetPrinterDataExW(
            phPrinter,
            L"PrinterDriverData",
            L"IppQueuePropertyBag",
            &pType,
            v10,
            2 * si128.m128i_i32[0],
            &pcbNeeded);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)v11,
      (unsigned int)"Failed to retrieve IPP Queue Property Bag!",
      nSize);
    v12 = v29;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = (LPBYTE *)v29[0];
    winrt::hstring::hstring((winrt::hstring *)v23, (const unsigned __int16 *)v12);
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertJsonToValueSet(
      v3,
      v2,
      v23);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v23);
    std::wstring::_Tidy_deallocate(v29);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
  if ( v19 )
    RevertToSelf();
  return v2;
}

```

## disassembly

```asm
0x18001bad4  mov     [rsp+arg_10], rbx
0x18001bad9  push    rsi
0x18001bada  push    rdi
0x18001badb  push    r14
0x18001badd  sub     rsp, 0D0h
0x18001bae4  mov     rax, cs:__security_cookie
0x18001baeb  xor     rax, rsp
0x18001baee  mov     [rsp+0E8h+var_28], rax
0x18001baf6  mov     r14, rdx
0x18001baf9  mov     rdi, rcx
0x18001bafc  mov     [rsp+0E8h+var_80], rcx
0x18001bb01  mov     [rsp+0E8h+var_78], rdx
0x18001bb06  xor     ebx, ebx
0x18001bb08  call    ?_ImpersonateUserIfNeeded@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA_NXZ; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ImpersonateUserIfNeeded(void)
0x18001bb0d  mov     [rsp+0E8h+var_A8], al
0x18001bb11  lea     rax, [rsp+0E8h+var_A8]
0x18001bb16  mov     [rsp+0E8h+var_58], rax
0x18001bb1e  lea     esi, [rbx+1]
0x18001bb21  mov     [rsp+0E8h+var_50], sil
0x18001bb29  xorps   xmm0, xmm0
0x18001bb2c  movdqu  xmmword ptr [rsp+0E8h+pDefault.pDatatype], xmm0
0x18001bb32  mov     qword ptr [rsp+0E8h+pDefault.DesiredAccess], 40h ; '@'
0x18001bb3e  mov     [rsp+0E8h+phPrinter], rbx
0x18001bb43  lea     rcx, [rdi+18h]; this
0x18001bb47  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18001bb4c  lea     r8, [rsp+0E8h+pDefault]; pDefault
0x18001bb51  lea     rdx, [rsp+0E8h+phPrinter]; phPrinter
0x18001bb56  mov     rcx, rax; pPrinterName
0x18001bb59  call    cs:__imp_OpenPrinterW
0x18001bb5f  test    eax, eax
0x18001bb61  setnz   al
0x18001bb64  mov     rcx, [rsp+0E8h]; this
0x18001bb6c  lea     rdx, aFailedToOpenPr; "Failed to open printer"
0x18001bb73  mov     [rsp+0E8h+pData], rdx; bool
0x18001bb78  movzx   r9d, al; char *
0x18001bb7c  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001bb83  lea     edx, [rbx+4Eh]; void *
0x18001bb86  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18001bb8b  mov     [rsp+0E8h+pType], ebx
0x18001bb8f  mov     [rsp+0E8h+var_A4], ebx
0x18001bb93  lea     rax, [rsp+0E8h+var_A4]
0x18001bb98  mov     [rsp+0E8h+pcbNeeded], rax; pcbNeeded
0x18001bb9d  mov     dword ptr [rsp+0E8h+nSize], ebx; nSize
0x18001bba1  mov     [rsp+0E8h+pData], rbx; int
0x18001bba6  lea     r9, [rsp+0E8h+pType]; pType
0x18001bbab  lea     r8, pValueName; "IppQueuePropertyBag"
0x18001bbb2  lea     rdx, pKeyName; "PrinterDriverData"
0x18001bbb9  mov     rcx, [rsp+0E8h+phPrinter]; hPrinter
0x18001bbbe  call    cs:__imp_GetPrinterDataExW
0x18001bbc4  cmp     eax, 2
0x18001bbc7  jz      loc_18001BD28
0x18001bbcd  cmp     [rsp+0E8h+var_A4], ebx
0x18001bbd1  jz      loc_18001BD28
0x18001bbd7  cmp     eax, 0EAh
0x18001bbdc  jz      short loc_18001BBE5
0x18001bbde  test    eax, eax
0x18001bbe0  mov     cl, sil
0x18001bbe3  jnz     short loc_18001BBE9
0x18001bbe5  mov     cl, bl
0x18001bbe7  test    eax, eax
0x18001bbe9  jle     short loc_18001BBF3
0x18001bbeb  movzx   eax, ax
0x18001bbee  or      eax, 80070000h
0x18001bbf3  mov     r10, [rsp+0E8h]
0x18001bbfb  test    cl, cl
0x18001bbfd  jnz     loc_18001BDBB
0x18001bc03  cmp     [rsp+0E8h+pType], esi
0x18001bc07  jz      short loc_18001BC10
0x18001bc09  cmp     [rsp+0E8h+pType], 7
0x18001bc0e  jnz     short loc_18001BC13
0x18001bc10  mov     sil, bl
0x18001bc13  mov     rcx, [rsp+0E8h]; this
0x18001bc1b  test    sil, sil
0x18001bc1e  jnz     loc_18001BDD3
0x18001bc24  xorps   xmm0, xmm0
0x18001bc27  movups  xmmword ptr [rsp+0E8h+var_48], xmm0
0x18001bc2f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001bc37  movdqu  [rsp+0E8h+var_38], xmm1
0x18001bc40  mov     word ptr [rsp+0E8h+var_48], bx
0x18001bc48  mov     edx, [rsp+0E8h+var_A4]
0x18001bc4c  shr     rdx, 1
0x18001bc4f  lea     rcx, [rsp+0E8h+var_48]
0x18001bc57  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001bc5c  mov     eax, dword ptr [rsp+0E8h+var_38]
0x18001bc63  lea     rcx, [rsp+0E8h+var_48]
0x18001bc6b  cmp     qword ptr [rsp+0E8h+var_38+8], 7
0x18001bc74  cmova   rcx, [rsp+0E8h+var_48]
0x18001bc7d  add     eax, eax
0x18001bc7f  lea     r9, [rsp+0E8h+var_A4]
0x18001bc84  mov     [rsp+0E8h+pcbNeeded], r9; pcbNeeded
0x18001bc89  mov     dword ptr [rsp+0E8h+nSize], eax; char *
0x18001bc8d  mov     [rsp+0E8h+pData], rcx; pData
0x18001bc92  lea     r9, [rsp+0E8h+pType]; pType
0x18001bc97  lea     r8, pValueName; "IppQueuePropertyBag"
0x18001bc9e  lea     rdx, pKeyName; "PrinterDriverData"
0x18001bca5  mov     rcx, [rsp+0E8h+phPrinter]; hPrinter
0x18001bcaa  call    cs:__imp_GetPrinterDataExW
0x18001bcb0  mov     r9d, eax; char *
0x18001bcb3  mov     rcx, [rsp+0E8h]; this
0x18001bcbb  lea     rax, aFailedToRetrie_0; "Failed to retrieve IPP Queue Property B"...
0x18001bcc2  mov     [rsp+0E8h+pData], rax; unsigned int
0x18001bcc7  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001bcce  mov     edx, 67h ; 'g'; void *
0x18001bcd3  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18001bcd8  lea     rdx, [rsp+0E8h+var_48]
0x18001bce0  cmp     qword ptr [rsp+0E8h+var_38+8], 7
0x18001bce9  cmova   rdx, [rsp+0E8h+var_48]; unsigned __int16 *
0x18001bcf2  lea     rcx, [rsp+0E8h+var_90]; this
0x18001bcf7  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18001bcfc  nop
0x18001bcfd  lea     r8, [rsp+0E8h+var_90]
0x18001bd02  mov     rdx, r14
0x18001bd05  mov     rcx, rdi
0x18001bd08  call    ?_ConvertJsonToValueSet@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUValueSet@Collections@Foundation@78@AEBUhstring@8@@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertJsonToValueSet(winrt::hstring const &)
0x18001bd0d  nop
0x18001bd0e  lea     rcx, [rsp+0E8h+var_90]
0x18001bd13  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001bd18  nop
0x18001bd19  lea     rcx, [rsp+0E8h+var_48]
0x18001bd21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bd26  jmp     short loc_18001BD7D
0x18001bd28  mov     r8, [rsp+0E8h+phPrinter]
0x18001bd2d  lea     rdx, [rsp+0E8h+var_90]
0x18001bd32  mov     rcx, rdi
0x18001bd35  call    ?_GetDefaultQueuePropertyBag@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUhstring@8@PEAX@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetDefaultQueuePropertyBag(void *)
0x18001bd3a  nop
0x18001bd3b  mov     rcx, rdi; this
0x18001bd3e  call    ?_PropertyBagAccessCheck@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_PropertyBagAccessCheck(void)
0x18001bd43  lea     r8, [rsp+0E8h+var_90]; struct winrt::hstring *
0x18001bd48  xor     edx, edx; void *
0x18001bd4a  mov     rcx, rdi; this
0x18001bd4d  call    ?_InternalSetQueuePropertyBag@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXPEAXAEBUhstring@8@@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_InternalSetQueuePropertyBag(void *,winrt::hstring const &)
0x18001bd52  nop
0x18001bd53  jmp     short loc_18001BD61
0x18001bd55  xor     ebx, ebx
0x18001bd57  mov     rdi, [rsp+0E8h+var_80]
0x18001bd5c  mov     r14, [rsp+0E8h+var_78]
0x18001bd61  lea     r8, [rsp+0E8h+var_90]
0x18001bd66  mov     rdx, r14
0x18001bd69  mov     rcx, rdi
0x18001bd6c  call    ?_ConvertJsonToValueSet@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUValueSet@Collections@Foundation@78@AEBUhstring@8@@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertJsonToValueSet(winrt::hstring const &)
0x18001bd71  nop
0x18001bd72  lea     rcx, [rsp+0E8h+var_90]
0x18001bd77  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001bd7c  nop
0x18001bd7d  lea     rcx, [rsp+0E8h+phPrinter]
0x18001bd82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001bd87  nop
0x18001bd88  cmp     [rsp+0E8h+var_A8], bl
0x18001bd8c  jz      short loc_18001BD94
0x18001bd8e  call    cs:__imp_RevertToSelf
0x18001bd94  mov     rax, r14
0x18001bd97  mov     rcx, [rsp+0E8h+var_28]
0x18001bd9f  xor     rcx, rsp; StackCookie
0x18001bda2  call    __security_check_cookie
0x18001bda7  mov     rbx, [rsp+0E8h+arg_10]
0x18001bdaf  add     rsp, 0D0h
0x18001bdb6  pop     r14
0x18001bdb8  pop     rdi
0x18001bdb9  pop     rsi
0x18001bdba  retn
0x18001bdbb  mov     r9d, eax; char *
0x18001bdbe  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001bdc5  mov     edx, 62h ; 'b'; void *
0x18001bdca  mov     rcx, r10; this
0x18001bdcd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001bdd3  mov     r9d, 8007139Fh; char *
0x18001bdd9  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001bde0  mov     edx, 63h ; 'c'; void *
0x18001bde5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

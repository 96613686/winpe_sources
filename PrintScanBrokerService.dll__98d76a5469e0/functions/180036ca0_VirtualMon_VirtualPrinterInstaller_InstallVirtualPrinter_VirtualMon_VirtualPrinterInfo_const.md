# VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter(VirtualMon::VirtualPrinterInfo const &)

- ea: `0x180036ca0`
- end: `0x180036ff3`
- name: `?InstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@QEAAJAEBUVirtualPrinterInfo@2@@Z`
- size: `851`
- prototype: `__int64 __fastcall(VirtualMon::VirtualPrinterInstaller *__hidden this, const struct VirtualMon::VirtualPrinterInfo *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update`

## callers

- `0x1800293fc`

## callees

- `0x180002d40`
- `0x180003254`
- `0x180007a28`
- `0x1800080f8`
- `0x18000876c`
- `0x18000f8a8`
- `0x1800182ec`
- `0x18001cfb4`
- `0x18002f194`
- `0x180032dfc`
- `0x180032ecc`
- `0x1800362f8`
- `0x18003666c`
- `0x180036a34`
- `0x180036ca0`
- `0x180038174`
- `0x180041658`
- `0x180041788`
- `0x180041b34`
- `0x180041e24`
- `0x180041fe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e86`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180036e78`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180036ee8`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180036e78`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180036ee8`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x180036db8`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x180036db8`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180036dec`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180036dec`

## string_xrefs

- `0x180036ccf`: `VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter`
- `0x180036d95`: `VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter`
- `0x180036f82`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036f99`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036fb3`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036fca`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036fdf`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter(
        VirtualMon::VirtualPrinterInstaller *this,
        const struct VirtualMon::VirtualPrinterInfo *a2)
{
  __int64 v4; // rax
  LPWSTR *v5; // r8
  WCHAR *v6; // rcx
  const char *v7; // r9
  unsigned int VirtualMonPort; // eax
  signed int LastError; // eax
  char v11; // cl
  void *v12; // rbx
  const char *v13; // r9
  const struct VirtualMon::VirtualPrinterInfo *v14; // rcx
  const struct VirtualMon::VirtualPrinterInfo *v15; // rax
  signed __int64 v16; // rcx
  int v17; // r8d
  int v18; // edx
  const char *v19; // r9
  __int64 result; // rax
  int pcbNeeded; // [rsp+20h] [rbp-A8h]
  int pcbNeededa; // [rsp+20h] [rbp-A8h]
  DWORD cbBuf; // [rsp+30h] [rbp-98h] BYREF
  HANDLE hPrinter; // [rsp+38h] [rbp-90h] BYREF
  void *v25; // [rsp+40h] [rbp-88h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+48h] [rbp-80h] BYREF
  LPWSTR pPrinterName[3]; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v28; // [rsp+78h] [rbp-50h]
  _BYTE v29[32]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo("VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter", L"Entered.");
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo("VirtualMon::VirtualPrinterInfoValidator::Validate", L"Entered.");
  try
  {
    VirtualMon::VirtualPrinterInfoValidator::ValidatePdcFile(a2);
    VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile(a2);
    VirtualMon::VirtualPrinterInfoValidator::ValidatePreferredInputFormat((char *)a2 + 288);
    VirtualMon::VirtualPrinterInfoValidator::ValidateOutputFileTypes((char *)a2 + 320);
    VirtualMon::VirtualPrinterInfoValidator::ValidateSupportedInputFormats((char *)a2 + 352);
    hPrinter = 0;
    *(_OWORD *)&pDefault.pDatatype = 0;
    *(&pDefault.DesiredAccess + 1) = 0;
    pDefault.DesiredAccess = 983052;
    v4 = std::operator+<unsigned short>(v29, (char *)this + 128, L":");
    std::operator+<unsigned short>(pPrinterName, v4, (char *)a2 + 64);
    std::wstring::_Tidy_deallocate(v29);
    v5 = pPrinterName;
    if ( v28 > 7 )
      v5 = (LPWSTR *)pPrinterName[0];
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter",
      L"PrinterName: %ws",
      v5);
    hPrinter = 0;
    v6 = (WCHAR *)pPrinterName;
    if ( v28 > 7 )
      v6 = pPrinterName[0];
    if ( !OpenPrinterW(v6, &hPrinter, &pDefault) )
    {
      if ( GetLastError() != 1801 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x27,
          (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
          v7);
      VirtualMonPort = VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort(this, a2);
      if ( VirtualMonPort && VirtualMonPort != -2147024713 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
          (const char *)VirtualMonPort,
          pcbNeeded);
      VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter((__int64)this, (_QWORD *)a2 + 8, a2);
LABEL_30:
      std::wstring::_Tidy_deallocate(pPrinterName);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPrinter);
      return 0;
    }
    cbBuf = 0;
    if ( GetPrinterW(hPrinter, 2u, 0, 0, &cbBuf) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
        (const char *)0x8000FFFFLL,
        pcbNeededa);
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v11 = 0;
    }
    else
    {
      v11 = 1;
      if ( LastError <= 0 )
      {
LABEL_19:
        if ( v11 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
            (const char *)(unsigned int)LastError,
            pcbNeededa);
        v12 = operator new[](cbBuf);
        v25 = v12;
        if ( !GetPrinterW(hPrinter, 2u, (LPBYTE)v12, cbBuf, &cbBuf) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x38,
            (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
            v13);
        if ( *((_QWORD *)a2 + 3) <= 7u )
          v14 = a2;
        else
          v14 = *(const struct VirtualMon::VirtualPrinterInfo **)a2;
        v15 = (const struct VirtualMon::VirtualPrinterInfo *)*((_QWORD *)v12 + 3);
        v16 = v14 - v15;
        do
        {
          v17 = *(unsigned __int16 *)((char *)v15 + v16);
          v18 = *(unsigned __int16 *)v15 - v17;
          if ( v18 )
            break;
          v15 = (const struct VirtualMon::VirtualPrinterInfo *)((char *)v15 + 2);
        }
        while ( v17 );
        if ( v18 )
          VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort(this, *((const unsigned __int16 **)v12 + 1), a2);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v25);
        goto LABEL_30;
      }
    }
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x44,
                           (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x180036ca0  mov     [rsp+arg_10], rbx
0x180036ca5  push    rsi
0x180036ca6  push    rdi
0x180036ca7  push    r14
0x180036ca9  sub     rsp, 0B0h
0x180036cb0  mov     rax, cs:__security_cookie
0x180036cb7  xor     rax, rsp
0x180036cba  mov     [rsp+0C8h+var_28], rax
0x180036cc2  mov     rdi, rdx
0x180036cc5  mov     rsi, rcx
0x180036cc8  lea     rdx, aEntered; "Entered."
0x180036ccf  lea     rcx, aVirtualmonVirt_1; "VirtualMon::VirtualPrinterInstaller::In"...
0x180036cd6  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180036cdb  lea     rdx, aEntered; "Entered."
0x180036ce2  lea     rcx, aVirtualmonVirt; "VirtualMon::VirtualPrinterInfoValidator"...
0x180036ce9  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180036cee  mov     rcx, rdi; struct VirtualMon::VirtualPrinterInfo *
0x180036cf1  call    ?ValidatePdcFile@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBUVirtualPrinterInfo@2@@Z; VirtualMon::VirtualPrinterInfoValidator::ValidatePdcFile(VirtualMon::VirtualPrinterInfo const &)
0x180036cf6  mov     rcx, rdi; struct VirtualMon::VirtualPrinterInfo *
0x180036cf9  call    ?ValidatePdrFile@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBUVirtualPrinterInfo@2@@Z; VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile(VirtualMon::VirtualPrinterInfo const &)
0x180036cfe  lea     rcx, [rdi+120h]
0x180036d05  call    ?ValidatePreferredInputFormat@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VirtualMon::VirtualPrinterInfoValidator::ValidatePreferredInputFormat(std::wstring const &)
0x180036d0a  lea     rcx, [rdi+140h]
0x180036d11  call    ?ValidateOutputFileTypes@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VirtualMon::VirtualPrinterInfoValidator::ValidateOutputFileTypes(std::wstring const &)
0x180036d16  lea     rcx, [rdi+160h]
0x180036d1d  call    ?ValidateSupportedInputFormats@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; VirtualMon::VirtualPrinterInfoValidator::ValidateSupportedInputFormats(std::map<std::wstring,std::wstring> const &)
0x180036d22  mov     [rsp+0C8h+hPrinter], 0
0x180036d2b  xorps   xmm0, xmm0
0x180036d2e  xor     eax, eax
0x180036d30  movups  xmmword ptr [rsp+0C8h+pDefault.pDatatype], xmm0
0x180036d35  mov     qword ptr [rsp+0C8h+pDefault.DesiredAccess], rax
0x180036d3a  mov     [rsp+0C8h+pDefault.DesiredAccess], 0F000Ch
0x180036d42  lea     rdx, [rsi+80h]
0x180036d49  lea     r8, asc_18004E4AC; ":"
0x180036d50  lea     rcx, [rsp+0C8h+var_48]
0x180036d58  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180036d5d  nop
0x180036d5e  lea     r8, [rdi+40h]
0x180036d62  mov     rdx, rax
0x180036d65  lea     rcx, [rsp+0C8h+pPrinterName]
0x180036d6a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180036d6f  nop
0x180036d70  lea     rcx, [rsp+0C8h+var_48]
0x180036d78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036d7d  lea     r8, [rsp+0C8h+pPrinterName]
0x180036d82  cmp     [rsp+0C8h+var_50], 7
0x180036d88  cmova   r8, [rsp+0C8h+pPrinterName]
0x180036d8e  lea     rdx, aPrinternameWs; "PrinterName: %ws"
0x180036d95  lea     rcx, aVirtualmonVirt_1; "VirtualMon::VirtualPrinterInstaller::In"...
0x180036d9c  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180036da1  mov     r14, [rsp+0C8h+hPrinter]
0x180036da6  test    r14, r14
0x180036da9  jz      short loc_180036DC8
0x180036dab  lea     rcx, [rsp+0C8h+cbBuf]; this
0x180036db0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036db5  mov     rcx, r14; hPrinter
0x180036db8  call    cs:__imp_ClosePrinter
0x180036dbe  lea     rcx, [rsp+0C8h+cbBuf]; this
0x180036dc3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036dc8  mov     [rsp+0C8h+hPrinter], 0
0x180036dd1  lea     rcx, [rsp+0C8h+pPrinterName]
0x180036dd6  cmp     [rsp+0C8h+var_50], 7
0x180036ddc  cmova   rcx, [rsp+0C8h+pPrinterName]; pPrinterName
0x180036de2  lea     r8, [rsp+0C8h+pDefault]; pDefault
0x180036de7  lea     rdx, [rsp+0C8h+hPrinter]; phPrinter
0x180036dec  call    cs:__imp_OpenPrinterW
0x180036df2  test    eax, eax
0x180036df4  jnz     short loc_180036E4F
0x180036df6  mov     r14, [rsp+0C8h]
0x180036dfe  call    cs:__imp_GetLastError
0x180036e04  cmp     eax, 709h
0x180036e09  jnz     loc_180036F82
0x180036e0f  mov     rdx, rdi; struct VirtualMon::VirtualPrinterInfo *
0x180036e12  mov     rcx, rsi; this
0x180036e15  call    ?CreateVirtualMonPort@VirtualPrinterInstaller@VirtualMon@@AEAAJAEBUVirtualPrinterInfo@2@@Z; VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort(VirtualMon::VirtualPrinterInfo const &)
0x180036e1a  test    eax, eax
0x180036e1c  jz      short loc_180036E29
0x180036e1e  cmp     eax, 800700B7h
0x180036e23  jz      short loc_180036E29
0x180036e25  xor     cl, cl
0x180036e27  jmp     short loc_180036E2B
0x180036e29  mov     cl, 1
0x180036e2b  mov     r10, [rsp+0C8h]
0x180036e33  test    cl, cl
0x180036e35  jz      loc_180036F96
0x180036e3b  mov     r8, rdi
0x180036e3e  lea     rdx, [rdi+40h]
0x180036e42  mov     rcx, rsi
0x180036e45  call    ?InstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter(std::wstring const &,std::wstring const &)
0x180036e4a  jmp     loc_180036F41
0x180036e4f  mov     [rsp+0C8h+cbBuf], 0
0x180036e57  mov     rbx, [rsp+0C8h]
0x180036e5f  lea     rax, [rsp+0C8h+cbBuf]
0x180036e64  mov     qword ptr [rsp+0C8h+pcbNeeded], rax; int
0x180036e69  xor     r9d, r9d; cbBuf
0x180036e6c  xor     r8d, r8d; pPrinter
0x180036e6f  lea     edx, [r9+2]; Level
0x180036e73  mov     rcx, [rsp+0C8h+hPrinter]; hPrinter
0x180036e78  call    cs:__imp_GetPrinterW
0x180036e7e  test    eax, eax
0x180036e80  jnz     loc_180036FAD
0x180036e86  call    cs:__imp_GetLastError
0x180036e8c  cmp     eax, 7Ah ; 'z'
0x180036e8f  jnz     short loc_180036E95
0x180036e91  xor     cl, cl
0x180036e93  jmp     short loc_180036E9B
0x180036e95  mov     cl, 1
0x180036e97  test    eax, eax
0x180036e99  jle     short loc_180036EA3
0x180036e9b  movzx   eax, ax
0x180036e9e  or      eax, 80070000h
0x180036ea3  mov     r10, [rsp+0C8h]
0x180036eab  test    cl, cl
0x180036ead  jnz     loc_180036FC7
0x180036eb3  mov     ecx, [rsp+0C8h+cbBuf]; unsigned __int64
0x180036eb7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180036ebc  mov     rbx, rax
0x180036ebf  mov     [rsp+0C8h+var_88], rax
0x180036ec4  mov     r14, [rsp+0C8h]
0x180036ecc  lea     rax, [rsp+0C8h+cbBuf]
0x180036ed1  mov     qword ptr [rsp+0C8h+pcbNeeded], rax; pcbNeeded
0x180036ed6  mov     r9d, [rsp+0C8h+cbBuf]; cbBuf
0x180036edb  mov     r8, rbx; pPrinter
0x180036ede  mov     edx, 2; Level
0x180036ee3  mov     rcx, [rsp+0C8h+hPrinter]; hPrinter
0x180036ee8  call    cs:__imp_GetPrinterW
0x180036eee  test    eax, eax
0x180036ef0  jz      loc_180036FDF
0x180036ef6  cmp     qword ptr [rdi+18h], 7
0x180036efb  jbe     short loc_180036F02
0x180036efd  mov     rcx, [rdi]
0x180036f00  jmp     short loc_180036F05
0x180036f02  mov     rcx, rdi
0x180036f05  mov     rax, [rbx+18h]
0x180036f09  sub     rcx, rax
0x180036f0c  movzx   edx, word ptr [rax]
0x180036f0f  movzx   r8d, word ptr [rax+rcx]
0x180036f14  sub     edx, r8d
0x180036f17  jnz     short loc_180036F22
0x180036f19  add     rax, 2
0x180036f1d  test    r8d, r8d
0x180036f20  jnz     short loc_180036F0C
0x180036f22  test    edx, edx
0x180036f24  jz      short loc_180036F36
0x180036f26  mov     r8, rdi; struct VirtualMon::VirtualPrinterInfo *
0x180036f29  mov     rdx, [rbx+8]; unsigned __int16 *
0x180036f2d  mov     rcx, rsi; this
0x180036f30  call    ?ChangeVirtualPrinterPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBGAEBUVirtualPrinterInfo@2@@Z; VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort(ushort const *,VirtualMon::VirtualPrinterInfo const &)
0x180036f35  nop
0x180036f36  lea     rcx, [rsp+0C8h+var_88]
0x180036f3b  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180036f40  nop
0x180036f41  lea     rcx, [rsp+0C8h+pPrinterName]
0x180036f46  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036f4b  nop
0x180036f4c  lea     rcx, [rsp+0C8h+hPrinter]
0x180036f51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180036f56  xor     eax, eax
0x180036f58  jmp     short loc_180036F5E
0x180036f5a  mov     eax, [rsp+0C8h+cbBuf]
0x180036f5e  mov     rcx, [rsp+0C8h+var_28]
0x180036f66  xor     rcx, rsp; StackCookie
0x180036f69  call    __security_check_cookie
0x180036f6e  mov     rbx, [rsp+0C8h+arg_10]
0x180036f76  add     rsp, 0B0h
0x180036f7d  pop     r14
0x180036f7f  pop     rdi
0x180036f80  pop     rsi
0x180036f81  retn
0x180036f82  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036f89  mov     edx, 27h ; '''; void *
0x180036f8e  mov     rcx, r14; this
0x180036f91  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180036f96  mov     r9d, eax; char *
0x180036f99  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036fa0  mov     edx, 2Bh ; '+'; void *
0x180036fa5  mov     rcx, r10; this
0x180036fa8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036fad  mov     r9d, 8000FFFFh; char *
0x180036fb3  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036fba  mov     edx, 32h ; '2'; void *
0x180036fbf  mov     rcx, rbx; this
0x180036fc2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036fc7  mov     r9d, eax; char *
0x180036fca  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036fd1  mov     edx, 34h ; '4'; void *
0x180036fd6  mov     rcx, r10; this
0x180036fd9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036fdf  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036fe6  lea     edx, [rax+38h]; void *
0x180036fe9  mov     rcx, r14; this
0x180036fec  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

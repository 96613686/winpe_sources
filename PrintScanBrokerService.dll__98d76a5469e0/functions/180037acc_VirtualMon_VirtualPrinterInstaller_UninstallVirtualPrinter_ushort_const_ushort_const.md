# VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(ushort const *,ushort const *)

- ea: `0x180037acc`
- end: `0x180037c71`
- name: `?UninstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG0@Z`
- size: `421`
- prototype: `void __fastcall(VirtualMon::VirtualPrinterInstaller *__hidden this, LPWSTR pPrinterName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180037c78`

## callees

- `0x1800182ec`
- `0x18001cfb4`
- `0x18002f194`
- `0x180037210`
- `0x180037acc`
- `0x180038174`

## import_xrefs

- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180037b47`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180037b47`
- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x180037b6d`
- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x180037b93`
- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x180037b6d`
- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x180037b93`
- `ext-ms-win-printer-winspool-l1-1-4!DeletePrinter` at `0x180037bae`
- `ext-ms-win-printer-winspool-l1-1-4!DeletePrinter` at `0x180037bae`

## string_xrefs

- `0x180037bed`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037c08`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037c20`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037c32`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037c47`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037c5c`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037aeb`: `VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter`
- `0x180037bbf`: `VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter`
- `0x180037bb8`: `DeletePrinter succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(
        VirtualMon::VirtualPrinterInstaller *this,
        LPWSTR pPrinterName,
        BYTE *a3)
{
  const char *v6; // r9
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE phPrinter; // [rsp+80h] [rbp+18h] BYREF

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter",
    L"PrinterName: %ws, PortName: %ws",
    pPrinterName,
    a3);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      (const char *)0x80070057LL,
      (int)pDefault.pDatatype);
  if ( !pPrinterName )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      (const char *)0x80070057LL,
      (int)pDefault.pDatatype);
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(&pDefault.DesiredAccess + 1) = 0;
  pDefault.DesiredAccess = 983052;
  phPrinter = 0;
  if ( !OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      v6);
  if ( !SetPrinterW(phPrinter, 0, 0, 1u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      v7);
  if ( !SetPrinterW(phPrinter, 0, 0, 3u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      v8);
  if ( !DeletePrinter(phPrinter) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      v9);
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter",
    L"DeletePrinter succeeded");
  VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(this, a3);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
}

```

## disassembly

```asm
0x180037acc  push    rbx
0x180037ace  push    rbp
0x180037acf  push    rsi
0x180037ad0  push    rdi
0x180037ad1  sub     rsp, 48h
0x180037ad5  mov     rsi, r8
0x180037ad8  mov     rbx, rdx
0x180037adb  mov     rbp, rcx
0x180037ade  mov     r9, r8
0x180037ae1  mov     r8, rdx
0x180037ae4  lea     rdx, aPrinternameWsP; "PrinterName: %ws, PortName: %ws"
0x180037aeb  lea     rcx, aVirtualmonVirt_0; "VirtualMon::VirtualPrinterInstaller::Un"...
0x180037af2  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037af7  mov     rcx, [rsp+68h]; this
0x180037afc  test    rsi, rsi
0x180037aff  jz      loc_180037C02
0x180037b05  mov     rcx, [rsp+68h]; this
0x180037b0a  test    rbx, rbx
0x180037b0d  jz      loc_180037C1A
0x180037b13  xorps   xmm0, xmm0
0x180037b16  xor     eax, eax
0x180037b18  movups  xmmword ptr [rsp+68h+pDefault.pDatatype], xmm0
0x180037b1d  mov     qword ptr [rsp+68h+pDefault.DesiredAccess], rax
0x180037b22  mov     [rsp+68h+pDefault.DesiredAccess], 0F000Ch
0x180037b2a  mov     [rsp+68h+phPrinter], rax
0x180037b32  mov     rdi, [rsp+68h]
0x180037b37  lea     r8, [rsp+68h+pDefault]; pDefault
0x180037b3c  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x180037b44  mov     rcx, rbx; pPrinterName
0x180037b47  call    cs:__imp_OpenPrinterW
0x180037b4d  test    eax, eax
0x180037b4f  jz      loc_180037C32
0x180037b55  mov     rbx, [rsp+68h]
0x180037b5a  mov     r9d, 1; Command
0x180037b60  xor     r8d, r8d; pPrinter
0x180037b63  xor     edx, edx; Level
0x180037b65  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x180037b6d  call    cs:__imp_SetPrinterW
0x180037b73  test    eax, eax
0x180037b75  jz      loc_180037C47
0x180037b7b  mov     rbx, [rsp+68h]
0x180037b80  mov     r9d, 3; Command
0x180037b86  xor     r8d, r8d; pPrinter
0x180037b89  xor     edx, edx; Level
0x180037b8b  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x180037b93  call    cs:__imp_SetPrinterW
0x180037b99  test    eax, eax
0x180037b9b  jz      loc_180037C5C
0x180037ba1  mov     rbx, [rsp+68h]
0x180037ba6  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x180037bae  call    cs:__imp_DeletePrinter
0x180037bb4  test    eax, eax
0x180037bb6  jz      short loc_180037BED
0x180037bb8  lea     rdx, aDeleteprinterS; "DeletePrinter succeeded"
0x180037bbf  lea     rcx, aVirtualmonVirt_0; "VirtualMon::VirtualPrinterInstaller::Un"...
0x180037bc6  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037bcb  mov     rdx, rsi; unsigned __int16 *
0x180037bce  mov     rcx, rbp; this
0x180037bd1  call    ?RemoveVirtualMonPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG@Z; VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(ushort const *)
0x180037bd6  nop
0x180037bd7  lea     rcx, [rsp+68h+phPrinter]
0x180037bdf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037be4  add     rsp, 48h
0x180037be8  pop     rdi
0x180037be9  pop     rsi
0x180037bea  pop     rbp
0x180037beb  pop     rbx
0x180037bec  retn
0x180037bed  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180037bf4  mov     edx, 0F2h; void *
0x180037bf9  mov     rcx, rbx; this
0x180037bfc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180037c02  mov     r9d, 80070057h; char *
0x180037c08  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180037c0f  mov     edx, 0E7h; void *
0x180037c14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037c1a  mov     r9d, 80070057h; char *
0x180037c20  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180037c27  mov     edx, 0E8h; void *
0x180037c2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037c32  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180037c39  mov     edx, 0EEh; void *
0x180037c3e  mov     rcx, rdi; this
0x180037c41  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180037c47  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180037c4e  mov     edx, 0F0h; void *
0x180037c53  mov     rcx, rbx; this
0x180037c56  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180037c5c  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180037c63  mov     edx, 0F1h; void *
0x180037c68  mov     rcx, rbx; this
0x180037c6b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

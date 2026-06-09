# VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(ushort const *)

- ea: `0x180037210`
- end: `0x180037380`
- name: `?RemoveVirtualMonPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG@Z`
- size: `368`
- prototype: `void __fastcall(VirtualMon::VirtualPrinterInstaller *this, BYTE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800362f8`
- `0x180037acc`

## callees

- `0x1800182ec`
- `0x18001cfb4`
- `0x18002f194`
- `0x180037020`
- `0x180037210`
- `0x180038174`

## import_xrefs

- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18003727d`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18003727d`
- `ext-ms-win-printer-winspool-l1-1-4!XcvDataW` at `0x1800372da`
- `ext-ms-win-printer-winspool-l1-1-4!XcvDataW` at `0x1800372da`

## string_xrefs

- `0x1800372ce`: `RemovePort`
- `0x180037344`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037356`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x18003736b`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x18003722f`: `VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort`
- `0x180037253`: `VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort`
- `0x1800372f4`: `VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort`
- `0x18003724c`: `Port is in use. Cannot remove port.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(
        VirtualMon::VirtualPrinterInstaller *this,
        BYTE *a2)
{
  const char *v4; // r9
  __int64 v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  char v8; // al
  int pOutputData; // [rsp+20h] [rbp-38h]
  HANDLE phPrinter[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pdwStatus; // [rsp+70h] [rbp+18h] BYREF
  DWORD pcbOutputNeeded; // [rsp+78h] [rbp+20h] BYREF

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort",
    L"PortName: %ws",
    a2);
  if ( VirtualMon::VirtualPrinterInstaller::IsPortInUse(this, (const unsigned __int16 *)a2) )
  {
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort",
      L"Port is in use. Cannot remove port.");
  }
  else
  {
    phPrinter[0] = 0;
    if ( !OpenPrinterW((LPWSTR)L",XcvMonitor Virtual Port Monitor", phPrinter, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
        v4);
    pcbOutputNeeded = 0;
    pdwStatus = 0;
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&a2[2 * v5] );
    if ( !XcvDataW(phPrinter[0], L"RemovePort", a2, 2 * v5 + 2, 0, 0, &pcbOutputNeeded, &pdwStatus) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
        v6);
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort",
      L"XcvData rc: %d",
      pdwStatus);
    v7 = (const char *)pdwStatus;
    if ( pdwStatus )
    {
      v8 = 0;
      if ( (int)pdwStatus > 0 )
        v7 = (const char *)((unsigned __int16)pdwStatus | 0x80070000);
    }
    else
    {
      v8 = 1;
    }
    if ( !v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
        v7,
        pOutputData);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(phPrinter);
  }
}

```

## disassembly

```asm
0x180037210  mov     [rsp+arg_0], rbx
0x180037215  mov     [rsp+arg_8], rsi
0x18003721a  push    rdi
0x18003721b  sub     rsp, 50h
0x18003721f  mov     rdi, rdx
0x180037222  mov     rbx, rcx
0x180037225  mov     r8, rdx
0x180037228  lea     rdx, aPortnameWs; "PortName: %ws"
0x18003722f  lea     rcx, aVirtualmonVirt_9; "VirtualMon::VirtualPrinterInstaller::Re"...
0x180037236  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003723b  mov     rdx, rdi; unsigned __int16 *
0x18003723e  mov     rcx, rbx; this
0x180037241  call    ?IsPortInUse@VirtualPrinterInstaller@VirtualMon@@AEAA_NPEBG@Z; VirtualMon::VirtualPrinterInstaller::IsPortInUse(ushort const *)
0x180037246  xor     esi, esi
0x180037248  test    al, al
0x18003724a  jz      short loc_180037264
0x18003724c  lea     rdx, aPortIsInUseCan; "Port is in use. Cannot remove port."
0x180037253  lea     rcx, aVirtualmonVirt_9; "VirtualMon::VirtualPrinterInstaller::Re"...
0x18003725a  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003725f  jmp     loc_180037334
0x180037264  mov     [rsp+58h+phPrinter], rsi
0x180037269  mov     rbx, [rsp+58h]
0x18003726e  xor     r8d, r8d; pDefault
0x180037271  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x180037276  lea     rcx, pPrinterName; ",XcvMonitor Virtual Port Monitor"
0x18003727d  call    cs:__imp_OpenPrinterW
0x180037283  test    eax, eax
0x180037285  jz      loc_180037356
0x18003728b  mov     [rsp+58h+arg_18], esi
0x18003728f  mov     [rsp+58h+arg_10], esi
0x180037293  or      r9, 0FFFFFFFFFFFFFFFFh
0x180037297  inc     r9
0x18003729a  cmp     [rdi+r9*2], si
0x18003729f  jnz     short loc_180037297
0x1800372a1  mov     rbx, [rsp+58h]
0x1800372a6  lea     r9d, ds:2[r9*2]; cbInputData
0x1800372ae  lea     rax, [rsp+58h+arg_10]
0x1800372b3  mov     [rsp+58h+pdwStatus], rax; pdwStatus
0x1800372b8  lea     rax, [rsp+58h+arg_18]
0x1800372bd  mov     [rsp+58h+pcbOutputNeeded], rax; pcbOutputNeeded
0x1800372c2  mov     [rsp+58h+cbOutputData], esi; cbOutputData
0x1800372c6  mov     [rsp+58h+pOutputData], rsi; int
0x1800372cb  mov     r8, rdi; pInputData
0x1800372ce  lea     rdx, aRemoveport; "RemovePort"
0x1800372d5  mov     rcx, [rsp+58h+phPrinter]; hXcv
0x1800372da  call    cs:__imp_XcvDataW
0x1800372e0  test    eax, eax
0x1800372e2  jz      loc_18003736B
0x1800372e8  mov     r8d, [rsp+58h+arg_10]
0x1800372ed  lea     rdx, aXcvdataRcD; "XcvData rc: %d"
0x1800372f4  lea     rcx, aVirtualmonVirt_9; "VirtualMon::VirtualPrinterInstaller::Re"...
0x1800372fb  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037300  mov     r9d, [rsp+58h+arg_10]
0x180037305  test    r9d, r9d
0x180037308  jnz     short loc_18003730E
0x18003730a  mov     al, 1
0x18003730c  jmp     short loc_180037321
0x18003730e  mov     al, sil
0x180037311  test    r9d, r9d
0x180037314  jle     short loc_180037321
0x180037316  movzx   r9d, r9w
0x18003731a  or      r9d, 80070000h; char *
0x180037321  mov     rcx, [rsp+58h]; this
0x180037326  test    al, al
0x180037328  jz      short loc_180037344
0x18003732a  lea     rcx, [rsp+58h+phPrinter]
0x18003732f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037334  mov     rbx, [rsp+58h+arg_0]
0x180037339  mov     rsi, [rsp+58h+arg_8]
0x18003733e  add     rsp, 50h
0x180037342  pop     rdi
0x180037343  retn
0x180037344  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x18003734b  mov     edx, 14Ch; void *
0x180037350  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037356  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x18003735d  mov     edx, 13Bh; void *
0x180037362  mov     rcx, rbx; this
0x180037365  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003736b  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180037372  mov     edx, 148h; void *
0x180037377  mov     rcx, rbx; this
0x18003737a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

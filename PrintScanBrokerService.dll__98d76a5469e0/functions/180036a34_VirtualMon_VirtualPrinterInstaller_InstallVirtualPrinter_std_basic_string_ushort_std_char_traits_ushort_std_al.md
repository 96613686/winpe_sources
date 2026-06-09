# VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180036a34`
- end: `0x180036c99`
- name: `?InstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `613`
- prototype: `void __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180036ca0`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000e5f4`
- `0x1800182ec`
- `0x18001cfb4`
- `0x18002f1d4`
- `0x18003292c`
- `0x1800361d0`
- `0x1800362c4`
- `0x18003664c`
- `0x180036a34`
- `0x1800380cc`
- `0x180038174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036b7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036b7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036b6b`
- `ext-ms-win-printer-winspool-l1-1-4!AddPrinterW` at `0x180036ba3`
- `ext-ms-win-printer-winspool-l1-1-4!AddPrinterW` at `0x180036ba3`
- `ext-ms-win-printer-winspool-l1-1-2!SetPrinterDataW` at `0x180036c13`
- `ext-ms-win-printer-winspool-l1-1-2!SetPrinterDataW` at `0x180036c13`

## string_xrefs

- `0x180036a8a`: `VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter`
- `0x180036bc6`: `VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter`
- `0x180036c2b`: `VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter`
- `0x180036be8`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036c72`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036c87`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036c09`: `VirtualPrinterInstallComplete`
- `0x180036c24`: `Printer Installed successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  _QWORD *v6; // r9
  _QWORD *v7; // r8
  _QWORD *v8; // rax
  int v9; // eax
  void *v10; // rdx
  HANDLE CurrentThread; // rax
  Common::AutoNoImpersonateDuringScope *v12; // rcx
  HANDLE v13; // rbx
  DWORD LastError; // eax
  DWORD v15; // eax
  int cbData; // [rsp+20h] [rbp-E0h]
  unsigned int cbDataa; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  BYTE pData[8]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE pPrinter[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v22; // [rsp+58h] [rbp-A8h]
  _QWORD *v23; // [rsp+68h] [rbp-98h]
  const wchar_t *v24; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v25; // [rsp+A8h] [rbp-58h]
  int v26; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v27[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v3 = a3;
  v4 = a2;
  if ( a3[3] <= 7u )
    v6 = a3;
  else
    v6 = (_QWORD *)*a3;
  if ( a2[3] <= 7u )
    v7 = a2;
  else
    v7 = (_QWORD *)*a2;
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter",
    L"PrinterName: %ws, PortName: %ws",
    v7,
    v6);
  TokenHandle = 0;
  memset_0(pPrinter, 0, 0x88u);
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  v22 = v4;
  v24 = L"Microsoft Virtual Print Class Driver";
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  v23 = v3;
  v26 |= 0x400040u;
  memset_0(v27, 0, 0x208u);
  v8 = (_QWORD *)(a1 + 128);
  if ( *(_QWORD *)(a1 + 152) > 7u )
    v8 = (_QWORD *)*v8;
  v9 = StringCchPrintfW(v27, 0x104u, L"%ws%ws%wc", L"{CCF68DDA-0A57-4224-BF2E-94463CFA4E6D}", v8, 59);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      (const char *)(unsigned int)v9,
      cbData);
  v25 = v27;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    Common::CloseHandleHelper((Common *)TokenHandle, v10);
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
      Common::AutoNoImpersonateDuringScope::ChangeThreadToken(v12, 0);
    else
      GetLastError();
  }
  v13 = AddPrinterW(0, 2u, pPrinter);
  v20[0] = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
    VirtualPrintDEHTelemetry::WriteDbgTraceError(
      "VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter",
      L"AddPrinter Failed: rc - %d",
      LastError);
  }
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    retaddr,
    218,
    "onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
    v13,
    "AddPrinter failed!");
  *(_DWORD *)pData = 1;
  v15 = SetPrinterDataW(v13, (LPWSTR)L"VirtualPrinterInstallComplete", 4u, pData, 4u);
  if ( v15 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      (const char *)v15,
      cbDataa);
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter",
    L"Printer Installed successfully");
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v20);
  Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
}

```

## disassembly

```asm
0x180036a34  mov     [rsp-8+arg_18], rbx
0x180036a39  push    rbp
0x180036a3a  push    rsi
0x180036a3b  push    rdi
0x180036a3c  lea     rbp, [rsp-200h]
0x180036a44  sub     rsp, 300h
0x180036a4b  mov     rax, cs:__security_cookie
0x180036a52  xor     rax, rsp
0x180036a55  mov     [rbp+210h+var_20], rax
0x180036a5c  mov     rbx, r8
0x180036a5f  mov     rdi, rdx
0x180036a62  mov     rsi, rcx
0x180036a65  cmp     qword ptr [r8+18h], 7
0x180036a6a  jbe     short loc_180036A71
0x180036a6c  mov     r9, [r8]
0x180036a6f  jmp     short loc_180036A74
0x180036a71  mov     r9, rbx
0x180036a74  cmp     qword ptr [rdx+18h], 7
0x180036a79  jbe     short loc_180036A80
0x180036a7b  mov     r8, [rdx]
0x180036a7e  jmp     short loc_180036A83
0x180036a80  mov     r8, rdi
0x180036a83  lea     rdx, aPrinternameWsP; "PrinterName: %ws, PortName: %ws"
0x180036a8a  lea     rcx, aVirtualmonVirt_1; "VirtualMon::VirtualPrinterInstaller::In"...
0x180036a91  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180036a96  mov     [rsp+310h+TokenHandle], 0
0x180036a9f  xor     edx, edx; Val
0x180036aa1  mov     r8d, 88h; Size
0x180036aa7  lea     rcx, [rsp+310h+pPrinter]; void *
0x180036aac  call    memset_0
0x180036ab1  cmp     qword ptr [rdi+18h], 7
0x180036ab6  jbe     short loc_180036ABB
0x180036ab8  mov     rdi, [rdi]
0x180036abb  mov     [rsp+310h+var_2B8], rdi
0x180036ac0  lea     rax, aMicrosoftVirtu; "Microsoft Virtual Print Class Driver"
0x180036ac7  mov     [rsp+310h+var_2A0], rax
0x180036acc  cmp     qword ptr [rbx+18h], 7
0x180036ad1  jbe     short loc_180036AD6
0x180036ad3  mov     rbx, [rbx]
0x180036ad6  mov     [rsp+310h+var_2A8], rbx
0x180036adb  or      [rbp+210h+var_258], 400040h
0x180036ae2  xor     edx, edx; Val
0x180036ae4  mov     r8d, 208h; Size
0x180036aea  lea     rcx, [rbp+210h+var_230]; void *
0x180036aee  call    memset_0
0x180036af3  lea     rax, [rsi+80h]
0x180036afa  cmp     qword ptr [rax+18h], 7
0x180036aff  jbe     short loc_180036B04
0x180036b01  mov     rax, [rax]
0x180036b04  mov     [rsp+310h+var_2E8], 3Bh ; ';'
0x180036b0c  mov     qword ptr [rsp+310h+cbData], rax; int
0x180036b11  lea     r9, aCcf68dda0a5742; "{CCF68DDA-0A57-4224-BF2E-94463CFA4E6D}"
0x180036b18  lea     r8, aWsWsWc; "%ws%ws%wc"
0x180036b1f  mov     edx, 104h; unsigned __int64
0x180036b24  lea     rcx, [rbp+210h+var_230]; unsigned __int16 *
0x180036b28  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036b2d  mov     rcx, [rbp+218h]; this
0x180036b34  test    eax, eax
0x180036b36  js      loc_180036C84
0x180036b3c  lea     rax, [rbp+210h+var_230]
0x180036b40  mov     [rbp+210h+var_268], rax
0x180036b44  mov     eax, gs:179Ch
0x180036b4c  mov     esi, 1
0x180036b51  lea     edi, [rsi+3]
0x180036b54  test    eax, eax
0x180036b56  jz      short loc_180036B97
0x180036b58  mov     rcx, [rsp+310h+TokenHandle]; this
0x180036b5d  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x180036b62  mov     [rsp+310h+TokenHandle], 0
0x180036b6b  call    cs:__imp_GetCurrentThread
0x180036b71  lea     r9, [rsp+310h+TokenHandle]; TokenHandle
0x180036b76  mov     r8d, esi; OpenAsSelf
0x180036b79  mov     edx, edi; DesiredAccess
0x180036b7b  mov     rcx, rax; ThreadHandle
0x180036b7e  call    cs:__imp_OpenThreadToken
0x180036b84  test    eax, eax
0x180036b86  jz      short loc_180036B91
0x180036b88  xor     edx, edx; void *
0x180036b8a  call    ?ChangeThreadToken@AutoNoImpersonateDuringScope@Common@@AEAAJPEAX@Z; Common::AutoNoImpersonateDuringScope::ChangeThreadToken(void *)
0x180036b8f  jmp     short loc_180036B97
0x180036b91  call    cs:__imp_GetLastError
0x180036b97  lea     r8, [rsp+310h+pPrinter]; pPrinter
0x180036b9c  mov     edx, 2; Level
0x180036ba1  xor     ecx, ecx; pName
0x180036ba3  call    cs:__imp_AddPrinterW
0x180036ba9  mov     rbx, rax
0x180036bac  mov     [rsp+310h+var_2D0], rax
0x180036bb1  test    rax, rax
0x180036bb4  jnz     short loc_180036BD2
0x180036bb6  call    cs:__imp_GetLastError
0x180036bbc  mov     r8d, eax
0x180036bbf  lea     rdx, aAddprinterFail_0; "AddPrinter Failed: rc - %d"
0x180036bc6  lea     rcx, aVirtualmonVirt_1; "VirtualMon::VirtualPrinterInstaller::In"...
0x180036bcd  call    ?WriteDbgTraceError@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180036bd2  mov     rcx, [rbp+218h]
0x180036bd9  lea     rax, aAddprinterFail; "AddPrinter failed!"
0x180036be0  mov     qword ptr [rsp+310h+cbData], rax
0x180036be5  mov     r9, rbx
0x180036be8  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036bef  mov     edx, 0DAh
0x180036bf4  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x180036bf9  mov     dword ptr [rsp+310h+pData], esi
0x180036bfd  mov     [rsp+310h+cbData], edi; unsigned int
0x180036c01  lea     r9, [rsp+310h+pData]; pData
0x180036c06  mov     r8d, edi; Type
0x180036c09  lea     rdx, aVirtualprinter_0; "VirtualPrinterInstallComplete"
0x180036c10  mov     rcx, rbx; hPrinter
0x180036c13  call    cs:__imp_SetPrinterDataW
0x180036c19  mov     rcx, [rbp+218h]; this
0x180036c20  test    eax, eax
0x180036c22  jnz     short loc_180036C6F
0x180036c24  lea     rdx, aPrinterInstall; "Printer Installed successfully"
0x180036c2b  lea     rcx, aVirtualmonVirt_1; "VirtualMon::VirtualPrinterInstaller::In"...
0x180036c32  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180036c37  nop
0x180036c38  lea     rcx, [rsp+310h+var_2D0]
0x180036c3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180036c42  nop
0x180036c43  lea     rcx, [rsp+310h+TokenHandle]; this
0x180036c48  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x180036c4d  mov     rcx, [rbp+210h+var_20]
0x180036c54  xor     rcx, rsp; StackCookie
0x180036c57  call    __security_check_cookie
0x180036c5c  mov     rbx, [rsp+310h+arg_18]
0x180036c64  add     rsp, 300h
0x180036c6b  pop     rdi
0x180036c6c  pop     rsi
0x180036c6d  pop     rbp
0x180036c6e  retn
0x180036c6f  mov     r9d, eax; char *
0x180036c72  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036c79  mov     edx, 0DDh; void *
0x180036c7e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180036c84  mov     r9d, eax; char *
0x180036c87  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036c8e  mov     edx, 0CFh; void *
0x180036c93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

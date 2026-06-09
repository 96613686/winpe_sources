# PTUtils::SaveUserModePrintTicket(ushort const *,IStream *)

- ea: `0x18002d75c`
- end: `0x18002d823`
- name: `?SaveUserModePrintTicket@PTUtils@@YAXPEBGPEAUIStream@@@Z`
- size: `199`
- prototype: `void __fastcall(PCWSTR pszPrinterName, IStream *pPrintTicket, struct IStream *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002d830`

## callees

- `0x1800213ac`
- `0x180023664`
- `0x18002d3f4`
- `0x18002d590`
- `0x18002d75c`
- `0x18002d8f0`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x18002d7a3`
- `WINSPOOL!OpenPrinterW` at `0x18002d7a3`
- `WINSPOOL!SetPrinterW` at `0x18002d7c8`
- `WINSPOOL!SetPrinterW` at `0x18002d7c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PTUtils::SaveUserModePrintTicket(WCHAR *pszPrinterName, IStream *pPrintTicket, struct IStream *a3)
{
  const char *v4; // r9
  unsigned int v5; // eax
  const char *v6; // [rsp+28h] [rbp-28h]
  BYTE pPrinter[8]; // [rsp+30h] [rbp-20h] BYREF
  _PRINTER_DEFAULTSW pDefault; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HANDLE phPrinter; // [rsp+70h] [rbp+20h] BYREF
  PDEVMODE ppDevmode; // [rsp+78h] [rbp+28h] BYREF

  *(_OWORD *)&pDefault.pDatatype = 0;
  *(&pDefault.DesiredAccess + 1) = 0;
  pDefault.DesiredAccess = 8;
  PTUtils::ConvertPrintTicketToDevMode(&ppDevmode, pszPrinterName, pPrintTicket);
  phPrinter = 0;
  if ( !OpenPrinterW(pszPrinterName, &phPrinter, &pDefault) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\PrintTicketUtils.h",
      v4);
  *(_QWORD *)pPrinter = ppDevmode;
  v5 = SetPrinterW(phPrinter, 9u, pPrinter, 0);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x84,
    (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\PrintTicketUtils.h",
    (const char *)v5,
    (__int64)"SetPrinter failed for user mode print ticket",
    v6);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
  wil::details::unique_storage<wil::details::resource_policy<_devicemodeW *,long (*)(void *),&long PTReleaseMemory(void *),wistd::integral_constant<unsigned __int64,0>,_devicemodeW *,_devicemodeW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_devicemodeW *,long (*)(void *),&long PTReleaseMemory(void *),wistd::integral_constant<unsigned __int64,0>,_devicemodeW *,_devicemodeW *,0,std::nullptr_t>>(&ppDevmode);
}

```

## disassembly

```asm
0x18002d75c  mov     [rsp-8+arg_0], rbx
0x18002d761  push    rbp
0x18002d762  mov     rbp, rsp
0x18002d765  sub     rsp, 50h
0x18002d769  mov     rbx, rcx
0x18002d76c  xorps   xmm0, xmm0
0x18002d76f  xor     eax, eax
0x18002d771  movups  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18002d775  mov     qword ptr [rbp+pDefault.DesiredAccess], rax
0x18002d779  mov     [rbp+pDefault.DesiredAccess], 8
0x18002d780  mov     r8, rdx; pPrintTicket
0x18002d783  mov     rdx, rcx; pszPrinterName
0x18002d786  lea     rcx, [rbp+ppDevmode]; ppDevmode
0x18002d78a  call    ?ConvertPrintTicketToDevMode@PTUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_devicemodeW@@P6AJPEAX@Z$1?PTReleaseMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGPEAUIStream@@@Z; PTUtils::ConvertPrintTicketToDevMode(ushort const *,IStream *)
0x18002d78f  nop
0x18002d790  mov     [rbp+phPrinter], 0
0x18002d798  lea     r8, [rbp+pDefault]; pDefault
0x18002d79c  lea     rdx, [rbp+phPrinter]; phPrinter
0x18002d7a0  mov     rcx, rbx; pPrinterName
0x18002d7a3  call    cs:__imp_OpenPrinterW
0x18002d7a9  mov     rcx, [rbp+8]; this
0x18002d7ad  test    eax, eax
0x18002d7af  jz      short loc_18002D811
0x18002d7b1  mov     rax, [rbp+ppDevmode]
0x18002d7b5  mov     qword ptr [rbp+pPrinter], rax
0x18002d7b9  xor     r9d, r9d; Command
0x18002d7bc  lea     r8, [rbp+pPrinter]; pPrinter
0x18002d7c0  lea     edx, [r9+9]; Level
0x18002d7c4  mov     rcx, [rbp+phPrinter]; hPrinter
0x18002d7c8  call    cs:__imp_SetPrinterW
0x18002d7ce  mov     rcx, [rbp+8]; this
0x18002d7d2  lea     rdx, aSetprinterFail; "SetPrinter failed for user mode print t"...
0x18002d7d9  mov     [rsp+50h+var_30], rdx; __int64
0x18002d7de  mov     r9d, eax; char *
0x18002d7e1  lea     r8, aOnecoreuapPrin_31; "onecoreuap\\printscan\\print\\workflow"...
0x18002d7e8  mov     edx, 84h; void *
0x18002d7ed  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18002d7f2  nop
0x18002d7f3  lea     rcx, [rbp+phPrinter]
0x18002d7f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d7fc  nop
0x18002d7fd  lea     rcx, [rbp+ppDevmode]
0x18002d801  call    ??1?$unique_storage@U?$resource_policy@PEAU_devicemodeW@@P6AJPEAX@Z$1?PTReleaseMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_devicemodeW *,long (*)(void *),&PTReleaseMemory(void *),wistd::integral_constant<unsigned __int64,0>,_devicemodeW *,_devicemodeW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_devicemodeW *,long (*)(void *),&PTReleaseMemory(void *),wistd::integral_constant<unsigned __int64,0>,_devicemodeW *,_devicemodeW *,0,std::nullptr_t>>(void)
0x18002d806  mov     rbx, [rsp+50h+arg_0]
0x18002d80b  add     rsp, 50h
0x18002d80f  pop     rbp
0x18002d810  retn
0x18002d811  lea     r8, aOnecoreuapPrin_31; "onecoreuap\\printscan\\print\\workflow"...
0x18002d818  mov     edx, 7Eh ; '~'; void *
0x18002d81d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

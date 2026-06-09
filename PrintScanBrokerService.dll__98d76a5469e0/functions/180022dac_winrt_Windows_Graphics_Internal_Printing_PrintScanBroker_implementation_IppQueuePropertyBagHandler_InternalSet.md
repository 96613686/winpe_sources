# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_InternalSetQueuePropertyBag(void *,winrt::hstring const &)

- ea: `0x180022dac`
- end: `0x180022eea`
- name: `?_InternalSetQueuePropertyBag@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXPEAXAEBUhstring@8@@Z`
- size: `318`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *this, void *, const struct winrt::hstring *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bad4`
- `0x18001cce4`

## callees

- `0x18000fa2c`
- `0x1800182ec`
- `0x18001cf40`
- `0x18001cfd4`
- `0x18001d0e4`
- `0x180022dac`

## import_xrefs

- `ext-ms-win-printer-winspool-l1-1-1!SetPrinterDataExW` at `0x180022ea9`
- `ext-ms-win-printer-winspool-l1-1-1!SetPrinterDataExW` at `0x180022ea9`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180022df5`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180022df5`

## string_xrefs

- `0x180022e15`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022e63`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022ec3`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022e05`: `Failed to open printer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_InternalSetQueuePropertyBag(
        winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *this,
        void *a2,
        const struct winrt::hstring *a3)
{
  HANDLE v4; // rdi
  WCHAR *v5; // rax
  BOOL v6; // eax
  unsigned int v7; // ecx
  BYTE *pData; // rax
  int v9; // edx
  DWORD v10; // eax
  const char *cbData; // [rsp+28h] [rbp-30h]
  const char *cbDataa; // [rsp+28h] [rbp-30h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE phPrinter; // [rsp+68h] [rbp+10h] BYREF

  v4 = a2;
  phPrinter = 0;
  if ( !a2 )
  {
    *(_OWORD *)&pDefault.pDatatype = 0;
    *(_QWORD *)&pDefault.DesiredAccess = 983052;
    phPrinter = 0;
    v5 = (WCHAR *)winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *)((char *)this + 24));
    v6 = OpenPrinterW(v5, &phPrinter, &pDefault);
    wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)v6,
      (bool)"Failed to open printer",
      cbData);
    v4 = phPrinter;
  }
  if ( *(_QWORD *)a3 )
    v7 = *(_DWORD *)(*(_QWORD *)a3 + 4LL);
  else
    v7 = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xB3,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)0x80070057LL,
    2 * (unsigned __int64)v7 > 0x100000,
    (bool)"IPP Queue Property Bag size exceeds the maximum allowed size!",
    (const char *)pDefault.pDatatype,
    pDefault.pDevMode,
    *(_QWORD *)&pDefault.DesiredAccess);
  pData = (BYTE *)winrt::hstring::c_str(a3);
  v10 = SetPrinterDataExW(v4, L"PrinterDriverData", L"IppQueuePropertyBag", 1u, pData, 2 * v9);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)v10,
    (unsigned int)"Failed to set the IPP Queue Property Bag!",
    cbDataa);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
}

```

## disassembly

```asm
0x180022dac  mov     rax, rsp
0x180022daf  mov     [rax+8], rbx
0x180022db3  push    rdi
0x180022db4  sub     rsp, 50h
0x180022db8  mov     rbx, r8
0x180022dbb  mov     rdi, rdx
0x180022dbe  mov     qword ptr [rax+10h], 0
0x180022dc6  test    rdx, rdx
0x180022dc9  jnz     short loc_180022E2B
0x180022dcb  xorps   xmm0, xmm0
0x180022dce  movdqu  xmmword ptr [rax-28h], xmm0
0x180022dd3  mov     qword ptr [rax-18h], 0F000Ch
0x180022ddb  mov     [rax+10h], rdx
0x180022ddf  add     rcx, 18h; this
0x180022de3  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180022de8  lea     r8, [rsp+58h+pDefault]; pDefault
0x180022ded  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x180022df2  mov     rcx, rax; pPrinterName
0x180022df5  call    cs:__imp_OpenPrinterW
0x180022dfb  test    eax, eax
0x180022dfd  setnz   al
0x180022e00  mov     rcx, [rsp+58h]; this
0x180022e05  lea     rdx, aFailedToOpenPr; "Failed to open printer"
0x180022e0c  mov     [rsp+58h+pData], rdx; bool
0x180022e11  movzx   r9d, al; char *
0x180022e15  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022e1c  mov     edx, 0AFh; void *
0x180022e21  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180022e26  mov     rdi, [rsp+58h+phPrinter]
0x180022e2b  mov     rax, [rbx]
0x180022e2e  test    rax, rax
0x180022e31  jz      short loc_180022E38
0x180022e33  mov     ecx, [rax+4]
0x180022e36  jmp     short loc_180022E3A
0x180022e38  xor     ecx, ecx
0x180022e3a  mov     eax, ecx
0x180022e3c  add     rax, rax
0x180022e3f  cmp     rax, 100000h
0x180022e45  setnbe  al
0x180022e48  mov     rcx, [rsp+58h]; this
0x180022e4d  lea     rdx, aIppQueueProper; "IPP Queue Property Bag size exceeds the"...
0x180022e54  mov     qword ptr [rsp+58h+cbData], rdx; bool
0x180022e59  mov     byte ptr [rsp+58h+pData], al; char
0x180022e5d  mov     r9d, 80070057h; char *
0x180022e63  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022e6a  mov     edx, 0B3h; void *
0x180022e6f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180022e74  mov     rdx, [rbx]
0x180022e77  test    rdx, rdx
0x180022e7a  jz      short loc_180022E7F
0x180022e7c  mov     edx, [rdx+4]
0x180022e7f  mov     rcx, rbx; this
0x180022e82  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180022e87  add     edx, edx
0x180022e89  mov     [rsp+58h+cbData], edx; char *
0x180022e8d  mov     [rsp+58h+pData], rax; pData
0x180022e92  mov     r9d, 1; Type
0x180022e98  lea     r8, pValueName; "IppQueuePropertyBag"
0x180022e9f  lea     rdx, pKeyName; "PrinterDriverData"
0x180022ea6  mov     rcx, rdi; hPrinter
0x180022ea9  call    cs:__imp_SetPrinterDataExW
0x180022eaf  mov     r9d, eax; char *
0x180022eb2  mov     rcx, [rsp+58h]; this
0x180022eb7  lea     rax, aFailedToSetThe; "Failed to set the IPP Queue Property Ba"...
0x180022ebe  mov     [rsp+58h+pData], rax; unsigned int
0x180022ec3  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022eca  mov     edx, 0B4h; void *
0x180022ecf  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180022ed4  nop
0x180022ed5  lea     rcx, [rsp+58h+phPrinter]
0x180022eda  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022edf  mov     rbx, [rsp+58h+arg_0]
0x180022ee4  add     rsp, 50h
0x180022ee8  pop     rdi
0x180022ee9  retn
```

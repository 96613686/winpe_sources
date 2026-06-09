# PTUtils::ConvertPrintTicketToDevMode(ushort const *,IStream *)

- ea: `0x18002d590`
- end: `0x18002d693`
- name: `?ConvertPrintTicketToDevMode@PTUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_devicemodeW@@P6AJPEAX@Z$1?PTReleaseMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGPEAUIStream@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(PDEVMODE *ppDevmode, PCWSTR pszPrinterName, IStream *pPrintTicket)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002d75c`

## callees

- `0x1800127a4`
- `0x18002d3b4`
- `0x18002d3d4`
- `0x18002d590`
- `0x18002d8a0`

## import_xrefs

- `ext-ms-win-printer-prntvpt-l1-1-0!PTOpenProvider` at `0x18002d5cb`
- `ext-ms-win-printer-prntvpt-l1-1-0!PTOpenProvider` at `0x18002d5cb`
- `ext-ms-win-printer-prntvpt-l1-1-1!PTConvertPrintTicketToDevMode` at `0x18002d622`
- `ext-ms-win-printer-prntvpt-l1-1-1!PTConvertPrintTicketToDevMode` at `0x18002d622`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PDEVMODE *__fastcall PTUtils::ConvertPrintTicketToDevMode(
        PDEVMODE *ppDevmode,
        PCWSTR pszPrinterName,
        IStream *pPrintTicket)
{
  HRESULT v5; // eax
  unsigned int v6; // eax
  int pcbDevmode; // [rsp+20h] [rbp-40h]
  HPTPROVIDER phProvider; // [rsp+48h] [rbp-18h] BYREF
  BSTR pbstrErrorMessage[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  ULONG v12; // [rsp+88h] [rbp+28h] BYREF

  phProvider = 0;
  v5 = PTOpenProvider(pszPrinterName, 1u, &phProvider);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\PrintTicketUtils.h",
      (const char *)(unsigned int)v5,
      pcbDevmode);
  v12 = 0;
  pbstrErrorMessage[0] = 0;
  *ppDevmode = 0;
  v6 = PTConvertPrintTicketToDevMode(
         phProvider,
         pPrintTicket,
         kPrinterDefaultDevmode,
         kPTJobScope,
         &v12,
         ppDevmode,
         pbstrErrorMessage);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x73,
    (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\PrintTicketUtils.h",
    (const char *)v6,
    (__int64)"Error converting DevMode to PrintTicket: %ws",
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pbstrErrorMessage);
  wil::details::unique_storage<wil::details::resource_policy<HPTPROVIDER__ *,long (*)(HPTPROVIDER__ *),&long PTCloseProvider(HPTPROVIDER__ *),wistd::integral_constant<unsigned __int64,0>,HPTPROVIDER__ *,HPTPROVIDER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HPTPROVIDER__ *,long (*)(HPTPROVIDER__ *),&long PTCloseProvider(HPTPROVIDER__ *),wistd::integral_constant<unsigned __int64,0>,HPTPROVIDER__ *,HPTPROVIDER__ *,0,std::nullptr_t>>(&phProvider);
  return ppDevmode;
}

```

## disassembly

```asm
0x18002d590  mov     [rsp-8+arg_8], rbx
0x18002d595  mov     [rsp-8+arg_10], rdi
0x18002d59a  mov     [rsp-8+arg_0], rcx
0x18002d59f  push    rbp
0x18002d5a0  mov     rbp, rsp
0x18002d5a3  sub     rsp, 60h
0x18002d5a7  mov     rdi, r8
0x18002d5aa  mov     rax, rdx
0x18002d5ad  mov     rbx, rcx
0x18002d5b0  mov     [rbp+var_20], 0
0x18002d5b7  mov     [rbp+phProvider], 0
0x18002d5bf  lea     r8, [rbp+phProvider]; phProvider
0x18002d5c3  mov     edx, 1; dwVersion
0x18002d5c8  mov     rcx, rax; pszPrinterName
0x18002d5cb  call    cs:__imp_PTOpenProvider
0x18002d5d1  mov     rcx, [rbp+8]; this
0x18002d5d5  test    eax, eax
0x18002d5d7  js      loc_18002D67E
0x18002d5dd  mov     [rbp+var_20], 1
0x18002d5e4  mov     [rbp+arg_18], 0
0x18002d5eb  mov     [rbp+var_10], 0
0x18002d5f3  mov     qword ptr [rbx], 0
0x18002d5fa  lea     rax, [rbp+var_10]
0x18002d5fe  mov     [rsp+60h+pbstrErrorMessage], rax; pbstrErrorMessage
0x18002d603  mov     [rsp+60h+ppDevmode], rbx; ppDevmode
0x18002d608  lea     rax, [rbp+arg_18]
0x18002d60c  mov     [rsp+60h+pcbDevmode], rax; pcbDevmode
0x18002d611  mov     r9d, 2; scope
0x18002d617  lea     r8d, [r9-1]; baseDevmodeType
0x18002d61b  mov     rdx, rdi; pPrintTicket
0x18002d61e  mov     rcx, [rbp+phProvider]; hProvider
0x18002d622  call    cs:__imp_PTConvertPrintTicketToDevMode
0x18002d628  mov     rcx, [rbp+8]; this
0x18002d62c  mov     [rsp+60h+ppDevmode], 0; char *
0x18002d635  lea     rdx, aErrorConvertin; "Error converting DevMode to PrintTicket"...
0x18002d63c  mov     [rsp+60h+pcbDevmode], rdx; __int64
0x18002d641  mov     r9d, eax; char *
0x18002d644  lea     r8, aOnecoreuapPrin_31; "onecoreuap\\printscan\\print\\workflow"...
0x18002d64b  mov     edx, 73h ; 's'; void *
0x18002d650  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002d655  nop
0x18002d656  lea     rcx, [rbp+var_10]
0x18002d65a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d65f  nop
0x18002d660  lea     rcx, [rbp+phProvider]
0x18002d664  call    ??1?$unique_storage@U?$resource_policy@PEAUHPTPROVIDER__@@P6AJPEAU1@@Z$1?PTCloseProvider@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HPTPROVIDER__ *,long (*)(HPTPROVIDER__ *),&PTCloseProvider(HPTPROVIDER__ *),wistd::integral_constant<unsigned __int64,0>,HPTPROVIDER__ *,HPTPROVIDER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HPTPROVIDER__ *,long (*)(HPTPROVIDER__ *),&PTCloseProvider(HPTPROVIDER__ *),wistd::integral_constant<unsigned __int64,0>,HPTPROVIDER__ *,HPTPROVIDER__ *,0,std::nullptr_t>>(void)
0x18002d669  mov     rax, rbx
0x18002d66c  lea     r11, [rsp+60h+var_s0]
0x18002d671  mov     rbx, [r11+18h]
0x18002d675  mov     rdi, [r11+20h]
0x18002d679  mov     rsp, r11
0x18002d67c  pop     rbp
0x18002d67d  retn
0x18002d67e  mov     r9d, eax; char *
0x18002d681  lea     r8, aOnecoreuapPrin_31; "onecoreuap\\printscan\\print\\workflow"...
0x18002d688  mov     edx, 6Dh ; 'm'; void *
0x18002d68d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

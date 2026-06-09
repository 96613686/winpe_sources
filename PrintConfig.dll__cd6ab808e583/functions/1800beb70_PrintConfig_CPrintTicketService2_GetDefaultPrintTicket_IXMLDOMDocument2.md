# PrintConfig::CPrintTicketService2::GetDefaultPrintTicket(IXMLDOMDocument2 * *)

- ea: `0x1800beb70`
- end: `0x1800bed67`
- name: `?GetDefaultPrintTicket@CPrintTicketService2@PrintConfig@@UEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(PrintConfig::CPrintTicketService2 *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18000e420`
- `0x18000f6a0`
- `0x1800beb70`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800bebd9`
- `KERNEL32!GetLastError` at `0x1800bec1d`
- `KERNEL32!GetLastError` at `0x1800bec28`
- `KERNEL32!GetLastError` at `0x1800bec70`
- `KERNEL32!GetLastError` at `0x1800bebd9`
- `KERNEL32!GetLastError` at `0x1800bec1d`
- `KERNEL32!GetLastError` at `0x1800bec28`
- `KERNEL32!GetLastError` at `0x1800bec70`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bed19`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bed19`
- `ole32!CreateStreamOnHGlobal` at `0x1800becbb`
- `ole32!CreateStreamOnHGlobal` at `0x1800becbb`
- `WINSPOOL!GetPrinterW` at `0x1800bec0c`
- `WINSPOOL!GetPrinterW` at `0x1800bec66`
- `WINSPOOL!GetPrinterW` at `0x1800bec0c`
- `WINSPOOL!GetPrinterW` at `0x1800bec66`
- `WINSPOOL!OpenPrinter2W` at `0x1800bebcf`
- `WINSPOOL!OpenPrinter2W` at `0x1800bebcf`
- `WINSPOOL!ClosePrinter` at `0x1800bed28`
- `WINSPOOL!ClosePrinter` at `0x1800bed28`
- `prntvpt!__imp_PTOpenProvider` at `0x1800bec9c`
- `prntvpt!__imp_PTOpenProvider` at `0x1800bec9c`
- `prntvpt!__imp_PTCloseProvider` at `0x1800bed37`
- `prntvpt!__imp_PTCloseProvider` at `0x1800bed37`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1800becea`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1800becea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrintConfig::CPrintTicketService2::GetDefaultPrintTicket(
        PrintConfig::CPrintTicketService2 *this,
        struct IXMLDOMDocument2 **a2)
{
  int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  LPBYTE v7; // rdi
  LPSTREAM ppstm; // [rsp+30h] [rbp-30h] BYREF
  HPTPROVIDER phProvider[2]; // [rsp+38h] [rbp-28h] BYREF
  LPBYTE pPrinter; // [rsp+48h] [rbp-18h] BYREF
  int v11; // [rsp+50h] [rbp-10h]
  DWORD pcbNeeded; // [rsp+88h] [rbp+28h] BYREF
  LPCWSTR pPrinterName; // [rsp+90h] [rbp+30h] BYREF
  HANDLE phPrinter; // [rsp+98h] [rbp+38h] BYREF

  phProvider[1] = (HPTPROVIDER)-2LL;
  if ( !a2 )
    return 2147500035LL;
  pPrinterName = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)this + 8) + 64LL))(
         *((_QWORD *)this + 8),
         &pPrinterName);
  phPrinter = 0;
  if ( v3 >= 0 && !OpenPrinter2W(pPrinterName, &phPrinter, 0, 0) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  pcbNeeded = 0;
  if ( v3 >= 0 )
  {
    if ( GetPrinterW(phPrinter, 2u, 0, 0, &pcbNeeded) )
    {
      v3 = -2147418113;
    }
    else if ( GetLastError() != 122 )
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
    }
  }
  std::vector<unsigned char>::vector<unsigned char>(&pPrinter, pcbNeeded);
  if ( v3 >= 0 && !GetPrinterW(phPrinter, 2u, pPrinter, v11 - (_DWORD)pPrinter, &pcbNeeded) )
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
  }
  v7 = 0;
  phProvider[0] = 0;
  if ( v3 >= 0 )
  {
    v7 = pPrinter;
    v3 = PTOpenProvider(pPrinterName, 1u, phProvider);
  }
  ppstm = 0;
  if ( v3 >= 0 )
  {
    v3 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v3 >= 0 )
    {
      v3 = PTConvertDevModeToPrintTicket(
             phProvider[0],
             *(unsigned __int16 *)(*((_QWORD *)v7 + 7) + 68LL) + *(unsigned __int16 *)(*((_QWORD *)v7 + 7) + 70LL),
             *((PDEVMODE *)v7 + 7),
             kPTJobScope,
             ppstm);
      if ( v3 >= 0 )
        v3 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
    }
  }
  if ( pPrinterName )
    SysFreeString((BSTR)pPrinterName);
  if ( phPrinter )
    ClosePrinter(phPrinter);
  if ( phProvider[0] )
    PTCloseProvider(phProvider[0]);
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  std::vector<char>::~vector<char>(&pPrinter);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800beb70  push    rbp
0x1800beb72  push    rbx
0x1800beb73  push    rdi
0x1800beb74  mov     rbp, rsp
0x1800beb77  sub     rsp, 60h
0x1800beb7b  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1800beb83  test    rdx, rdx
0x1800beb86  jnz     short loc_1800BEB92
0x1800beb88  mov     eax, 80004003h
0x1800beb8d  jmp     loc_1800BED5F
0x1800beb92  mov     [rbp+pPrinterName], 0
0x1800beb9a  mov     rcx, [rcx+40h]
0x1800beb9e  mov     rax, [rcx]
0x1800beba1  lea     rdx, [rbp+pPrinterName]
0x1800beba5  mov     rax, [rax+40h]
0x1800beba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bebae  mov     ebx, eax
0x1800bebb0  mov     [rbp+phPrinter], 0
0x1800bebb8  mov     edi, 80070000h
0x1800bebbd  test    eax, eax
0x1800bebbf  js      short loc_1800BEBEA
0x1800bebc1  xor     r9d, r9d; pOptions
0x1800bebc4  xor     r8d, r8d; pDefault
0x1800bebc7  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800bebcb  mov     rcx, [rbp+pPrinterName]; pPrinterName
0x1800bebcf  call    cs:__imp_OpenPrinter2W
0x1800bebd5  test    eax, eax
0x1800bebd7  jnz     short loc_1800BEBEA
0x1800bebd9  call    cs:__imp_GetLastError
0x1800bebdf  mov     ebx, eax
0x1800bebe1  test    eax, eax
0x1800bebe3  jle     short loc_1800BEBEA
0x1800bebe5  movzx   ebx, ax
0x1800bebe8  or      ebx, edi
0x1800bebea  mov     [rbp+arg_8], 0
0x1800bebf1  test    ebx, ebx
0x1800bebf3  js      short loc_1800BEC39
0x1800bebf5  lea     rax, [rbp+arg_8]
0x1800bebf9  mov     [rsp+60h+pcbNeeded], rax; pcbNeeded
0x1800bebfe  xor     r9d, r9d; cbBuf
0x1800bec01  xor     r8d, r8d; pPrinter
0x1800bec04  lea     edx, [r9+2]; Level
0x1800bec08  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800bec0c  call    cs:__imp_GetPrinterW
0x1800bec12  test    eax, eax
0x1800bec14  jz      short loc_1800BEC1D
0x1800bec16  mov     ebx, 8000FFFFh
0x1800bec1b  jmp     short loc_1800BEC39
0x1800bec1d  call    cs:__imp_GetLastError
0x1800bec23  cmp     eax, 7Ah ; 'z'
0x1800bec26  jz      short loc_1800BEC39
0x1800bec28  call    cs:__imp_GetLastError
0x1800bec2e  mov     ebx, eax
0x1800bec30  test    eax, eax
0x1800bec32  jle     short loc_1800BEC39
0x1800bec34  movzx   ebx, ax
0x1800bec37  or      ebx, edi
0x1800bec39  mov     edx, [rbp+arg_8]
0x1800bec3c  lea     rcx, [rbp+pPrinter]
0x1800bec40  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800bec45  test    ebx, ebx
0x1800bec47  js      short loc_1800BEC81
0x1800bec49  mov     r8, [rbp+pPrinter]; pPrinter
0x1800bec4d  mov     r9d, [rbp+var_10]
0x1800bec51  sub     r9d, r8d; cbBuf
0x1800bec54  lea     rax, [rbp+arg_8]
0x1800bec58  mov     [rsp+60h+pcbNeeded], rax; pcbNeeded
0x1800bec5d  mov     edx, 2; Level
0x1800bec62  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800bec66  call    cs:__imp_GetPrinterW
0x1800bec6c  test    eax, eax
0x1800bec6e  jnz     short loc_1800BEC81
0x1800bec70  call    cs:__imp_GetLastError
0x1800bec76  mov     ebx, eax
0x1800bec78  test    eax, eax
0x1800bec7a  jle     short loc_1800BEC81
0x1800bec7c  movzx   ebx, ax
0x1800bec7f  or      ebx, edi
0x1800bec81  xor     edi, edi
0x1800bec83  mov     [rbp+phProvider], rdi
0x1800bec87  test    ebx, ebx
0x1800bec89  js      short loc_1800BECA4
0x1800bec8b  mov     rdi, [rbp+pPrinter]
0x1800bec8f  lea     r8, [rbp+phProvider]; phProvider
0x1800bec93  mov     edx, 1; dwVersion
0x1800bec98  mov     rcx, [rbp+pPrinterName]; pszPrinterName
0x1800bec9c  call    cs:__imp_PTOpenProvider
0x1800beca2  mov     ebx, eax
0x1800beca4  mov     [rbp+ppstm], 0
0x1800becac  test    ebx, ebx
0x1800becae  js      short loc_1800BED10
0x1800becb0  lea     r8, [rbp+ppstm]; ppstm
0x1800becb4  mov     edx, 1; fDeleteOnRelease
0x1800becb9  xor     ecx, ecx; hGlobal
0x1800becbb  call    cs:__imp_CreateStreamOnHGlobal
0x1800becc1  mov     ebx, eax
0x1800becc3  test    eax, eax
0x1800becc5  js      short loc_1800BED10
0x1800becc7  mov     r10, [rbp+ppstm]
0x1800beccb  mov     r8, [rdi+38h]; pDevmode
0x1800beccf  movzx   edx, word ptr [r8+46h]
0x1800becd4  movzx   eax, word ptr [r8+44h]
0x1800becd9  add     edx, eax; cbDevmode
0x1800becdb  mov     [rsp+60h+pcbNeeded], r10; pPrintTicket
0x1800bece0  mov     r9d, 2; scope
0x1800bece6  mov     rcx, [rbp+phProvider]; hProvider
0x1800becea  call    cs:__imp_PTConvertDevModeToPrintTicket
0x1800becf0  mov     ebx, eax
0x1800becf2  test    eax, eax
0x1800becf4  js      short loc_1800BED10
0x1800becf6  mov     rcx, [rbp+ppstm]
0x1800becfa  xor     edx, edx
0x1800becfc  mov     rax, [rcx]
0x1800becff  xor     r9d, r9d
0x1800bed02  xor     r8d, r8d
0x1800bed05  mov     rax, [rax+28h]
0x1800bed09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed0e  mov     ebx, eax
0x1800bed10  mov     rcx, [rbp+pPrinterName]; bstrString
0x1800bed14  test    rcx, rcx
0x1800bed17  jz      short loc_1800BED1F
0x1800bed19  call    cs:__imp_SysFreeString
0x1800bed1f  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800bed23  test    rcx, rcx
0x1800bed26  jz      short loc_1800BED2E
0x1800bed28  call    cs:__imp_ClosePrinter
0x1800bed2e  mov     rcx, [rbp+phProvider]; hProvider
0x1800bed32  test    rcx, rcx
0x1800bed35  jz      short loc_1800BED3E
0x1800bed37  call    cs:__imp_PTCloseProvider
0x1800bed3d  nop
0x1800bed3e  mov     rcx, [rbp+ppstm]
0x1800bed42  test    rcx, rcx
0x1800bed45  jz      short loc_1800BED54
0x1800bed47  mov     rax, [rcx]
0x1800bed4a  mov     rax, [rax+10h]
0x1800bed4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed53  nop
0x1800bed54  lea     rcx, [rbp+pPrinter]
0x1800bed58  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800bed5d  mov     eax, ebx
0x1800bed5f  add     rsp, 60h
0x1800bed63  pop     rdi
0x1800bed64  pop     rbx
0x1800bed65  pop     rbp
0x1800bed66  retn
```

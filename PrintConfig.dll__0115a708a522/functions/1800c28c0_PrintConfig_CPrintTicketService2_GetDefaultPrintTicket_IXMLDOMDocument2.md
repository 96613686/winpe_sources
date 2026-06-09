# PrintConfig::CPrintTicketService2::GetDefaultPrintTicket(IXMLDOMDocument2 * *)

- ea: `0x1800c28c0`
- end: `0x1800c2b06`
- name: `?GetDefaultPrintTicket@CPrintTicketService2@PrintConfig@@UEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(PrintConfig::CPrintTicketService2 *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18000e82c`
- `0x18000fb68`
- `0x1800c28c0`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800c292f`
- `KERNEL32!GetLastError` at `0x1800c297f`
- `KERNEL32!GetLastError` at `0x1800c2990`
- `KERNEL32!GetLastError` at `0x1800c29e4`
- `KERNEL32!GetLastError` at `0x1800c292f`
- `KERNEL32!GetLastError` at `0x1800c297f`
- `KERNEL32!GetLastError` at `0x1800c2990`
- `KERNEL32!GetLastError` at `0x1800c29e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c2aa5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c2aa5`
- `ole32!CreateStreamOnHGlobal` at `0x1800c2a3b`
- `ole32!CreateStreamOnHGlobal` at `0x1800c2a3b`
- `WINSPOOL!GetPrinterW` at `0x1800c2968`
- `WINSPOOL!GetPrinterW` at `0x1800c29d4`
- `WINSPOOL!GetPrinterW` at `0x1800c2968`
- `WINSPOOL!GetPrinterW` at `0x1800c29d4`
- `WINSPOOL!OpenPrinter2W` at `0x1800c291f`
- `WINSPOOL!OpenPrinter2W` at `0x1800c291f`
- `WINSPOOL!ClosePrinter` at `0x1800c2aba`
- `WINSPOOL!ClosePrinter` at `0x1800c2aba`
- `prntvpt!__imp_PTOpenProvider` at `0x1800c2a16`
- `prntvpt!__imp_PTOpenProvider` at `0x1800c2a16`
- `prntvpt!__imp_PTCloseProvider` at `0x1800c2acf`
- `prntvpt!__imp_PTCloseProvider` at `0x1800c2acf`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1800c2a70`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1800c2a70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrintConfig::CPrintTicketService2::GetDefaultPrintTicket(
        PrintConfig::CPrintTicketService2 *this,
        struct IXMLDOMDocument2 **a2)
{
  int v3; // ebx
  __int64 v4; // r8
  signed int LastError; // eax
  signed int v6; // eax
  signed int v7; // eax
  LPBYTE v8; // rdi
  LPSTREAM ppstm; // [rsp+30h] [rbp-30h] BYREF
  HPTPROVIDER phProvider[2]; // [rsp+38h] [rbp-28h] BYREF
  LPBYTE pPrinter; // [rsp+48h] [rbp-18h] BYREF
  int v12; // [rsp+50h] [rbp-10h]
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
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
    }
  }
  std::vector<unsigned char>::vector<unsigned char>((__int64 *)&pPrinter, pcbNeeded, v4);
  if ( v3 >= 0 && !GetPrinterW(phPrinter, 2u, pPrinter, v12 - (_DWORD)pPrinter, &pcbNeeded) )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
  }
  v8 = 0;
  phProvider[0] = 0;
  if ( v3 >= 0 )
  {
    v8 = pPrinter;
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
             *(unsigned __int16 *)(*((_QWORD *)v8 + 7) + 68LL) + *(unsigned __int16 *)(*((_QWORD *)v8 + 7) + 70LL),
             *((PDEVMODE *)v8 + 7),
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
  std::vector<char>::~vector<char>((char **)&pPrinter);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800c28c0  push    rbp
0x1800c28c2  push    rbx
0x1800c28c3  push    rdi
0x1800c28c4  mov     rbp, rsp
0x1800c28c7  sub     rsp, 60h
0x1800c28cb  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1800c28d3  test    rdx, rdx
0x1800c28d6  jnz     short loc_1800C28E2
0x1800c28d8  mov     eax, 80004003h
0x1800c28dd  jmp     loc_1800C2AFD
0x1800c28e2  mov     [rbp+pPrinterName], 0
0x1800c28ea  mov     rcx, [rcx+40h]
0x1800c28ee  mov     rax, [rcx]
0x1800c28f1  lea     rdx, [rbp+pPrinterName]
0x1800c28f5  mov     rax, [rax+40h]
0x1800c28f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c28fe  mov     ebx, eax
0x1800c2900  mov     [rbp+phPrinter], 0
0x1800c2908  mov     edi, 80070000h
0x1800c290d  test    eax, eax
0x1800c290f  js      short loc_1800C2946
0x1800c2911  xor     r9d, r9d; pOptions
0x1800c2914  xor     r8d, r8d; pDefault
0x1800c2917  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800c291b  mov     rcx, [rbp+pPrinterName]; pPrinterName
0x1800c291f  call    cs:__imp_OpenPrinter2W
0x1800c2926  nop     dword ptr [rax+rax+00h]
0x1800c292b  test    eax, eax
0x1800c292d  jnz     short loc_1800C2946
0x1800c292f  call    cs:__imp_GetLastError
0x1800c2936  nop     dword ptr [rax+rax+00h]
0x1800c293b  mov     ebx, eax
0x1800c293d  test    eax, eax
0x1800c293f  jle     short loc_1800C2946
0x1800c2941  movzx   ebx, ax
0x1800c2944  or      ebx, edi
0x1800c2946  mov     [rbp+arg_8], 0
0x1800c294d  test    ebx, ebx
0x1800c294f  js      short loc_1800C29A7
0x1800c2951  lea     rax, [rbp+arg_8]
0x1800c2955  mov     [rsp+60h+pcbNeeded], rax; pcbNeeded
0x1800c295a  xor     r9d, r9d; cbBuf
0x1800c295d  xor     r8d, r8d; pPrinter
0x1800c2960  lea     edx, [r9+2]; Level
0x1800c2964  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800c2968  call    cs:__imp_GetPrinterW
0x1800c296f  nop     dword ptr [rax+rax+00h]
0x1800c2974  test    eax, eax
0x1800c2976  jz      short loc_1800C297F
0x1800c2978  mov     ebx, 8000FFFFh
0x1800c297d  jmp     short loc_1800C29A7
0x1800c297f  call    cs:__imp_GetLastError
0x1800c2986  nop     dword ptr [rax+rax+00h]
0x1800c298b  cmp     eax, 7Ah ; 'z'
0x1800c298e  jz      short loc_1800C29A7
0x1800c2990  call    cs:__imp_GetLastError
0x1800c2997  nop     dword ptr [rax+rax+00h]
0x1800c299c  mov     ebx, eax
0x1800c299e  test    eax, eax
0x1800c29a0  jle     short loc_1800C29A7
0x1800c29a2  movzx   ebx, ax
0x1800c29a5  or      ebx, edi
0x1800c29a7  mov     edx, [rbp+arg_8]
0x1800c29aa  lea     rcx, [rbp+pPrinter]
0x1800c29ae  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800c29b3  test    ebx, ebx
0x1800c29b5  js      short loc_1800C29FB
0x1800c29b7  mov     r8, [rbp+pPrinter]; pPrinter
0x1800c29bb  mov     r9d, [rbp+var_10]
0x1800c29bf  sub     r9d, r8d; cbBuf
0x1800c29c2  lea     rax, [rbp+arg_8]
0x1800c29c6  mov     [rsp+60h+pcbNeeded], rax; pcbNeeded
0x1800c29cb  mov     edx, 2; Level
0x1800c29d0  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800c29d4  call    cs:__imp_GetPrinterW
0x1800c29db  nop     dword ptr [rax+rax+00h]
0x1800c29e0  test    eax, eax
0x1800c29e2  jnz     short loc_1800C29FB
0x1800c29e4  call    cs:__imp_GetLastError
0x1800c29eb  nop     dword ptr [rax+rax+00h]
0x1800c29f0  mov     ebx, eax
0x1800c29f2  test    eax, eax
0x1800c29f4  jle     short loc_1800C29FB
0x1800c29f6  movzx   ebx, ax
0x1800c29f9  or      ebx, edi
0x1800c29fb  xor     edi, edi
0x1800c29fd  mov     [rbp+phProvider], rdi
0x1800c2a01  test    ebx, ebx
0x1800c2a03  js      short loc_1800C2A24
0x1800c2a05  mov     rdi, [rbp+pPrinter]
0x1800c2a09  lea     r8, [rbp+phProvider]; phProvider
0x1800c2a0d  mov     edx, 1; dwVersion
0x1800c2a12  mov     rcx, [rbp+pPrinterName]; pszPrinterName
0x1800c2a16  call    cs:__imp_PTOpenProvider
0x1800c2a1d  nop     dword ptr [rax+rax+00h]
0x1800c2a22  mov     ebx, eax
0x1800c2a24  mov     [rbp+ppstm], 0
0x1800c2a2c  test    ebx, ebx
0x1800c2a2e  js      short loc_1800C2A9C
0x1800c2a30  lea     r8, [rbp+ppstm]; ppstm
0x1800c2a34  mov     edx, 1; fDeleteOnRelease
0x1800c2a39  xor     ecx, ecx; hGlobal
0x1800c2a3b  call    cs:__imp_CreateStreamOnHGlobal
0x1800c2a42  nop     dword ptr [rax+rax+00h]
0x1800c2a47  mov     ebx, eax
0x1800c2a49  test    eax, eax
0x1800c2a4b  js      short loc_1800C2A9C
0x1800c2a4d  mov     r10, [rbp+ppstm]
0x1800c2a51  mov     r8, [rdi+38h]; pDevmode
0x1800c2a55  movzx   edx, word ptr [r8+46h]
0x1800c2a5a  movzx   eax, word ptr [r8+44h]
0x1800c2a5f  add     edx, eax; cbDevmode
0x1800c2a61  mov     [rsp+60h+pcbNeeded], r10; pPrintTicket
0x1800c2a66  mov     r9d, 2; scope
0x1800c2a6c  mov     rcx, [rbp+phProvider]; hProvider
0x1800c2a70  call    cs:__imp_PTConvertDevModeToPrintTicket
0x1800c2a77  nop     dword ptr [rax+rax+00h]
0x1800c2a7c  mov     ebx, eax
0x1800c2a7e  test    eax, eax
0x1800c2a80  js      short loc_1800C2A9C
0x1800c2a82  mov     rcx, [rbp+ppstm]
0x1800c2a86  xor     edx, edx
0x1800c2a88  mov     rax, [rcx]
0x1800c2a8b  xor     r9d, r9d
0x1800c2a8e  xor     r8d, r8d
0x1800c2a91  mov     rax, [rax+28h]
0x1800c2a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2a9a  mov     ebx, eax
0x1800c2a9c  mov     rcx, [rbp+pPrinterName]; bstrString
0x1800c2aa0  test    rcx, rcx
0x1800c2aa3  jz      short loc_1800C2AB1
0x1800c2aa5  call    cs:__imp_SysFreeString
0x1800c2aac  nop     dword ptr [rax+rax+00h]
0x1800c2ab1  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800c2ab5  test    rcx, rcx
0x1800c2ab8  jz      short loc_1800C2AC6
0x1800c2aba  call    cs:__imp_ClosePrinter
0x1800c2ac1  nop     dword ptr [rax+rax+00h]
0x1800c2ac6  mov     rcx, [rbp+phProvider]; hProvider
0x1800c2aca  test    rcx, rcx
0x1800c2acd  jz      short loc_1800C2ADC
0x1800c2acf  call    cs:__imp_PTCloseProvider
0x1800c2ad6  nop     dword ptr [rax+rax+00h]
0x1800c2adb  nop
0x1800c2adc  mov     rcx, [rbp+ppstm]
0x1800c2ae0  test    rcx, rcx
0x1800c2ae3  jz      short loc_1800C2AF2
0x1800c2ae5  mov     rax, [rcx]
0x1800c2ae8  mov     rax, [rax+10h]
0x1800c2aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2af1  nop
0x1800c2af2  lea     rcx, [rbp+pPrinter]
0x1800c2af6  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800c2afb  mov     eax, ebx
0x1800c2afd  add     rsp, 60h
0x1800c2b01  pop     rdi
0x1800c2b02  pop     rbx
0x1800c2b03  pop     rbp
0x1800c2b04  retn
```

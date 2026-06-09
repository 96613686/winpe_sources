# VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort(ushort const *,VirtualMon::VirtualPrinterInfo const &)

- ea: `0x1800362f8`
- end: `0x180036646`
- name: `?ChangeVirtualPrinterPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBGAEBUVirtualPrinterInfo@2@@Z`
- size: `846`
- prototype: `void __fastcall(VirtualMon::VirtualPrinterInstaller *this, const unsigned __int16 *, const struct VirtualMon::VirtualPrinterInfo *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180036ca0`

## callees

- `0x180002d40`
- `0x180003254`
- `0x180006b48`
- `0x180007a28`
- `0x1800080f8`
- `0x18000876c`
- `0x18000e5f4`
- `0x18000fa18`
- `0x1800182ec`
- `0x18001cfb4`
- `0x18002f194`
- `0x1800361ac`
- `0x1800362f8`
- `0x18003666c`
- `0x180037210`
- `0x180038174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003645e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003645e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036587`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180036450`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x1800364bf`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180036450`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x1800364bf`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x1800363f2`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x1800363f2`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18003641a`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18003641a`
- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x180036524`
- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x180036524`

## string_xrefs

- `0x180036346`: `VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort`
- `0x1800365aa`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800365c2`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800365d7`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800365ef`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036607`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x18003661c`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036634`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`

## pseudocode

```c
void __fastcall VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort(
        VirtualMon::VirtualPrinterInstaller *this,
        const unsigned __int16 *a2,
        const struct VirtualMon::VirtualPrinterInfo *a3)
{
  const struct VirtualMon::VirtualPrinterInfo *v6; // r9
  char v7; // di
  int v9; // eax
  signed int LastError; // eax
  char v11; // cl
  BYTE **v12; // rsi
  const char *v13; // r9
  unsigned int VirtualMonPort; // eax
  const struct VirtualMon::VirtualPrinterInfo *v15; // rax
  BYTE *v16; // rax
  signed int v17; // eax
  unsigned int v18; // eax
  int pcbNeeded; // [rsp+20h] [rbp-E0h]
  int pcbNeededa; // [rsp+20h] [rbp-E0h]
  int pcbNeededb; // [rsp+20h] [rbp-E0h]
  HANDLE hPrinter; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbBuf; // [rsp+38h] [rbp-C8h] BYREF
  BYTE **v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pPrinterName[528]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  if ( *((_QWORD *)a3 + 3) <= 7u )
    v6 = a3;
  else
    v6 = *(const struct VirtualMon::VirtualPrinterInfo **)a3;
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort",
    L"PrinterName: %ws, PortName: %ws",
    a2,
    v6);
  hPrinter = 0;
  v25 = 0;
  v7 = 1;
  if ( !a2 || !*((_QWORD *)a3 + 2) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      (const char *)0x80070057LL,
      pcbNeeded);
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(&pDefault.DesiredAccess + 1) = 0;
  pDefault.DesiredAccess = 983052;
  v9 = StringCchPrintfW(pPrinterName, 0x209u, L"%s:%s");
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      (const char *)(unsigned int)v9,
      (int)a2);
  hPrinter = 0;
  if ( OpenPrinterW(pPrinterName, &hPrinter, &pDefault) )
  {
    cbBuf = 0;
    if ( GetPrinterW(hPrinter, 5u, 0, 0, &cbBuf) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x60,
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
LABEL_16:
        if ( v11 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x62,
            (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
            (const char *)(unsigned int)LastError,
            pcbNeededa);
        v12 = (BYTE **)operator new[](cbBuf);
        v24 = v12;
        if ( !GetPrinterW(hPrinter, 5u, (LPBYTE)v12, cbBuf, &cbBuf) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x66,
            (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
            v13);
        VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(this, v12[1]);
        VirtualMonPort = VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort(this, a3);
        if ( VirtualMonPort && VirtualMonPort != -2147024713 )
          v7 = 0;
        if ( !v7 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6E,
            (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
            (const char *)VirtualMonPort,
            pcbNeededb);
        if ( *((_QWORD *)a3 + 3) <= 7u )
          v15 = a3;
        else
          v15 = *(const struct VirtualMon::VirtualPrinterInfo **)a3;
        v12[1] = (BYTE *)v15;
        if ( !SetPrinterW(hPrinter, 5u, (LPBYTE)v12, 0) )
        {
          v16 = (BYTE *)std::wstring::c_str(a3);
          VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(this, v16);
          v17 = GetLastError();
          if ( v17 > 0 )
            v17 = (unsigned __int16)v17 | 0x80070000;
          v18 = wil::verify_hresult<long>((unsigned int)v17);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x77,
            (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
            (const char *)v18,
            pcbNeededb);
        }
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v24);
        goto LABEL_27;
      }
    }
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
LABEL_27:
  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v25);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPrinter);
}

```

## disassembly

```asm
0x1800362f8  mov     [rsp-8+arg_18], rbx
0x1800362fd  push    rbp
0x1800362fe  push    rsi
0x1800362ff  push    rdi
0x180036300  push    r14
0x180036302  push    r15
0x180036304  lea     rbp, [rsp-3A0h]
0x18003630c  sub     rsp, 4A0h
0x180036313  mov     rax, cs:__security_cookie
0x18003631a  xor     rax, rsp
0x18003631d  mov     [rbp+3C0h+var_30], rax
0x180036324  mov     rbx, r8
0x180036327  mov     rsi, rdx
0x18003632a  mov     r14, rcx
0x18003632d  cmp     qword ptr [r8+18h], 7
0x180036332  jbe     short loc_180036339
0x180036334  mov     r9, [r8]
0x180036337  jmp     short loc_18003633C
0x180036339  mov     r9, rbx
0x18003633c  mov     r8, rsi
0x18003633f  lea     rdx, aPrinternameWsP; "PrinterName: %ws, PortName: %ws"
0x180036346  lea     rcx, aVirtualmonVirt_13; "VirtualMon::VirtualPrinterInstaller::Ch"...
0x18003634d  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180036352  mov     [rsp+4C0h+hPrinter], 0
0x18003635b  mov     [rsp+4C0h+var_478], 0
0x180036364  mov     dil, 1
0x180036367  test    rsi, rsi
0x18003636a  jz      short loc_180036377
0x18003636c  cmp     qword ptr [rbx+10h], 0
0x180036371  jz      short loc_180036377
0x180036373  xor     al, al
0x180036375  jmp     short loc_18003637A
0x180036377  mov     al, dil
0x18003637a  mov     rcx, [rbp+3C8h]; this
0x180036381  test    al, al
0x180036383  jnz     loc_1800365BC
0x180036389  xorps   xmm0, xmm0
0x18003638c  xor     eax, eax
0x18003638e  movups  xmmword ptr [rsp+4C0h+pDefault.pDatatype], xmm0
0x180036393  mov     qword ptr [rsp+4C0h+pDefault.DesiredAccess], rax
0x180036398  mov     [rsp+4C0h+pDefault.DesiredAccess], 0F000Ch
0x1800363a0  lea     r9, [r14+80h]
0x1800363a7  cmp     qword ptr [r9+18h], 7
0x1800363ac  jbe     short loc_1800363B1
0x1800363ae  mov     r9, [r9]
0x1800363b1  mov     qword ptr [rsp+4C0h+pcbNeeded], rsi; int
0x1800363b6  lea     r8, aSS; "%s:%s"
0x1800363bd  mov     edx, 209h; unsigned __int64
0x1800363c2  lea     rcx, [rsp+4C0h+pPrinterName]; unsigned __int16 *
0x1800363c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800363cc  mov     rcx, [rbp+3C8h]; this
0x1800363d3  test    eax, eax
0x1800363d5  js      loc_1800365D4
0x1800363db  mov     rsi, [rsp+4C0h+hPrinter]
0x1800363e0  test    rsi, rsi
0x1800363e3  jz      short loc_180036402
0x1800363e5  lea     rcx, [rsp+4C0h+cbBuf]; this
0x1800363ea  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800363ef  mov     rcx, rsi; hPrinter
0x1800363f2  call    cs:__imp_ClosePrinter
0x1800363f8  lea     rcx, [rsp+4C0h+cbBuf]; this
0x1800363fd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036402  mov     [rsp+4C0h+hPrinter], 0
0x18003640b  lea     r8, [rsp+4C0h+pDefault]; pDefault
0x180036410  lea     rdx, [rsp+4C0h+hPrinter]; phPrinter
0x180036415  lea     rcx, [rsp+4C0h+pPrinterName]; pPrinterName
0x18003641a  call    cs:__imp_OpenPrinterW
0x180036420  test    eax, eax
0x180036422  jz      loc_180036539
0x180036428  mov     [rsp+4C0h+cbBuf], 0
0x180036430  mov     rsi, [rbp+3C8h]
0x180036437  lea     rax, [rsp+4C0h+cbBuf]
0x18003643c  mov     qword ptr [rsp+4C0h+pcbNeeded], rax; int
0x180036441  xor     r9d, r9d; cbBuf
0x180036444  xor     r8d, r8d; pPrinter
0x180036447  lea     edx, [r9+5]; Level
0x18003644b  mov     rcx, [rsp+4C0h+hPrinter]; hPrinter
0x180036450  call    cs:__imp_GetPrinterW
0x180036456  test    eax, eax
0x180036458  jnz     loc_1800365E9
0x18003645e  call    cs:__imp_GetLastError
0x180036464  cmp     eax, 7Ah ; 'z'
0x180036467  jnz     short loc_18003646D
0x180036469  xor     cl, cl
0x18003646b  jmp     short loc_180036474
0x18003646d  mov     cl, dil
0x180036470  test    eax, eax
0x180036472  jle     short loc_18003647C
0x180036474  movzx   eax, ax
0x180036477  or      eax, 80070000h
0x18003647c  mov     r10, [rbp+3C8h]
0x180036483  test    cl, cl
0x180036485  jnz     loc_180036604
0x18003648b  mov     ecx, [rsp+4C0h+cbBuf]; unsigned __int64
0x18003648f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180036494  mov     rsi, rax
0x180036497  mov     [rsp+4C0h+var_480], rax
0x18003649c  mov     r15, [rbp+3C8h]
0x1800364a3  lea     rax, [rsp+4C0h+cbBuf]
0x1800364a8  mov     qword ptr [rsp+4C0h+pcbNeeded], rax; int
0x1800364ad  mov     r9d, [rsp+4C0h+cbBuf]; cbBuf
0x1800364b2  mov     r8, rsi; pPrinter
0x1800364b5  mov     edx, 5; Level
0x1800364ba  mov     rcx, [rsp+4C0h+hPrinter]; hPrinter
0x1800364bf  call    cs:__imp_GetPrinterW
0x1800364c5  test    eax, eax
0x1800364c7  jz      loc_18003661C
0x1800364cd  mov     rdx, [rsi+8]; unsigned __int16 *
0x1800364d1  mov     rcx, r14; this
0x1800364d4  call    ?RemoveVirtualMonPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG@Z; VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(ushort const *)
0x1800364d9  mov     rdx, rbx; struct VirtualMon::VirtualPrinterInfo *
0x1800364dc  mov     rcx, r14; this
0x1800364df  call    ?CreateVirtualMonPort@VirtualPrinterInstaller@VirtualMon@@AEAAJAEBUVirtualPrinterInfo@2@@Z; VirtualMon::VirtualPrinterInstaller::CreateVirtualMonPort(VirtualMon::VirtualPrinterInfo const &)
0x1800364e4  test    eax, eax
0x1800364e6  jz      short loc_1800364F2
0x1800364e8  cmp     eax, 800700B7h
0x1800364ed  jz      short loc_1800364F2
0x1800364ef  xor     dil, dil
0x1800364f2  mov     rcx, [rbp+3C8h]; this
0x1800364f9  test    dil, dil
0x1800364fc  jz      loc_180036631
0x180036502  cmp     qword ptr [rbx+18h], 7
0x180036507  jbe     short loc_18003650E
0x180036509  mov     rax, [rbx]
0x18003650c  jmp     short loc_180036511
0x18003650e  mov     rax, rbx
0x180036511  mov     [rsi+8], rax
0x180036515  xor     r9d, r9d; Command
0x180036518  mov     r8, rsi; pPrinter
0x18003651b  lea     edx, [r9+5]; Level
0x18003651f  mov     rcx, [rsp+4C0h+hPrinter]; hPrinter
0x180036524  call    cs:__imp_SetPrinterW
0x18003652a  test    eax, eax
0x18003652c  jz      short loc_180036574
0x18003652e  lea     rcx, [rsp+4C0h+var_480]
0x180036533  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180036538  nop
0x180036539  lea     rcx, [rsp+4C0h+var_478]
0x18003653e  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x180036543  nop
0x180036544  lea     rcx, [rsp+4C0h+hPrinter]
0x180036549  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003654e  mov     rcx, [rbp+3C0h+var_30]
0x180036555  xor     rcx, rsp; StackCookie
0x180036558  call    __security_check_cookie
0x18003655d  mov     rbx, [rsp+4C0h+arg_18]
0x180036565  add     rsp, 4A0h
0x18003656c  pop     r15
0x18003656e  pop     r14
0x180036570  pop     rdi
0x180036571  pop     rsi
0x180036572  pop     rbp
0x180036573  retn
0x180036574  mov     rcx, rbx
0x180036577  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18003657c  mov     rdx, rax; unsigned __int16 *
0x18003657f  mov     rcx, r14; this
0x180036582  call    ?RemoveVirtualMonPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG@Z; VirtualMon::VirtualPrinterInstaller::RemoveVirtualMonPort(ushort const *)
0x180036587  call    cs:__imp_GetLastError
0x18003658d  test    eax, eax
0x18003658f  jle     short loc_180036599
0x180036591  movzx   eax, ax
0x180036594  or      eax, 80070000h
0x180036599  mov     ecx, eax
0x18003659b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800365a0  mov     r9d, eax; char *
0x1800365a3  mov     rcx, [rbp+3C8h]; this
0x1800365aa  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800365b1  mov     edx, 77h ; 'w'; void *
0x1800365b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800365bc  mov     r9d, 80070057h; char *
0x1800365c2  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800365c9  mov     edx, 51h ; 'Q'; void *
0x1800365ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800365d4  mov     r9d, eax; char *
0x1800365d7  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800365de  mov     edx, 59h ; 'Y'; void *
0x1800365e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800365e9  mov     r9d, 8000FFFFh; char *
0x1800365ef  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800365f6  mov     edx, 60h ; '`'; void *
0x1800365fb  mov     rcx, rsi; this
0x1800365fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036604  mov     r9d, eax; char *
0x180036607  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x18003660e  mov     edx, 62h ; 'b'; void *
0x180036613  mov     rcx, r10; this
0x180036616  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003661c  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036623  mov     edx, 66h ; 'f'; void *
0x180036628  mov     rcx, r15; this
0x18003662b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180036631  mov     r9d, eax; char *
0x180036634  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x18003663b  mov     edx, 6Eh ; 'n'; void *
0x180036640  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

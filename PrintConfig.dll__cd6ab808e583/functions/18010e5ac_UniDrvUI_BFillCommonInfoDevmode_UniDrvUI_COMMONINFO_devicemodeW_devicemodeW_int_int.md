# UniDrvUI::BFillCommonInfoDevmode(UniDrvUI::_COMMONINFO *,_devicemodeW *,_devicemodeW *,int,int)

- ea: `0x18010e5ac`
- end: `0x18010e8d7`
- name: `?BFillCommonInfoDevmode@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@1HH@Z`
- size: `811`
- prototype: `__int64 __usercall@<rax>(UniDrvUI *__hidden this@<rcx>, struct UniDrvUI::_COMMONINFO *@<rdx>, struct _devicemodeW *@<r8>, struct _devicemodeW *@<r9>, int, int)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180105174`
- `0x180105f48`
- `0x1801067bc`
- `0x18010722c`
- `0x18010c890`
- `0x18010cc88`
- `0x18010ec78`
- `0x18010f628`
- `0x180111870`

## callees

- `0x1800153fc`
- `0x18001878c`
- `0x180020040`
- `0x1800fc90c`
- `0x180102674`
- `0x18010427c`
- `0x180106b84`
- `0x18010e5ac`
- `0x18010e9ac`
- `0x18010fff8`
- `0x180110780`
- `0x180148d9c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18010e6d9`
- `KERNEL32!FreeLibrary` at `0x18010e6d9`
- `KERNEL32!GetLastError` at `0x18010e62a`
- `KERNEL32!GetLastError` at `0x18010e62a`
- `KERNEL32!LocalFree` at `0x18010e79a`
- `KERNEL32!LocalFree` at `0x18010e7e2`
- `KERNEL32!LocalFree` at `0x18010e79a`
- `KERNEL32!LocalFree` at `0x18010e7e2`
- `KERNEL32!LoadLibraryExW` at `0x18010e6c4`
- `KERNEL32!LoadLibraryExW` at `0x18010e6c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18010e84a`
- `OLEAUT32!__imp_SysFreeString` at `0x18010e8cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18010e84a`
- `OLEAUT32!__imp_SysFreeString` at `0x18010e8cc`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x18010e737`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x18010e737`

## string_xrefs

- `0x18010e72d`: `Windows.PrintSupportExtension`
- `0x18010e6bd`: `Print.PrintSupport.Source.dll`
- `0x18010e5f6`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18010e646`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18010e66a`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18010e7b2`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18010e85c`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18010e87c`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18010e8b2`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18010e5ef`: `Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .`
- `0x18010e7ce`: `Can not perform PrintSupport printTicket valdation from legacy devmode path. hr: 0x%x.`
- `0x18010e8ab`: `Can not perform IHV JScript printTicket valdation from legacy devmode path. hr: 0x%x.`
- `0x18010e663`: `Attempt to perform IHV JScript validaton of the public devmode.`
- `0x18010e683`: `The driver does not use print config module.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UniDrvUI::BFillCommonInfoDevmode(
        UniDrvUI *this,
        struct UniDrvUI::_COMMONINFO *a2,
        struct _devicemodeW *a3,
        struct _devicemodeW *a4,
        unsigned int a5)
{
  int v5; // r13d
  unsigned int v6; // ebx
  char *v9; // r15
  signed int LastError; // eax
  int *v12; // r8
  int IsIppOrMpsOrVirtualPrinterCommon; // edi
  bool v14; // bl
  HMODULE Library; // rax
  void **Printer; // rax
  void **v17; // rbx
  void *v18; // rdi
  int v19; // eax
  int v20; // edi
  unsigned __int16 **v21; // r8
  int v22; // eax
  struct _OPTSELECT *v23; // r9
  struct _devicemodeW **v24; // [rsp+20h] [rbp-30h]
  unsigned int *v25; // [rsp+30h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  BSTR bstrString; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v28; // [rsp+98h] [rbp+48h] BYREF

  v5 = (int)a4;
  v6 = (unsigned int)a3;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::BFillCommonInfoDevmode",
    L"Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .",
    (_DWORD)a4 != 0,
    a5 != 0);
  v9 = (char *)this + 88;
  if ( !UniDrvUI::BGetValidatedUserDefaultDevmode(
          this,
          a2,
          (struct _devicemodeW *)0xFFFFFFFFLL,
          v6,
          (struct _devicemodeW *)((char *)this + 88),
          (struct _devicemodeW **)this + 12,
          (struct _UNIDRVEXTRA **)v25) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::BFillCommonInfoDevmode",
      L"Can not process devmode information (hr: 0x%x).",
      (unsigned int)LastError);
    return 0;
  }
  if ( !a5 )
    goto LABEL_36;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::BFillCommonInfoDevmode",
    L"Attempt to perform IHV JScript validaton of the public devmode.");
  if ( (*(_DWORD *)(*((_QWORD *)this + 6) + 24LL) & 0x100000) != 0 )
  {
    a5 = 0;
    IsIppOrMpsOrVirtualPrinterCommon = PrintCore::IsIppOrMpsOrVirtualPrinterCommon(*((PrintCore **)this + 4), &a5, v12);
    v14 = a5 != 0;
    if ( !`PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isLoadLibraryCheckDone )
    {
      Library = LoadLibraryExW(L"Print.PrintSupport.Source.dll", 0, 0x800u);
      if ( Library )
      {
        `PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isPrintSupportAvailable = 1;
        FreeLibrary(Library);
      }
      `PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isLoadLibraryCheckDone = 1;
    }
    if ( `PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isPrintSupportAvailable
      && IsIppOrMpsOrVirtualPrinterCommon >= 0 )
    {
      if ( v14 )
      {
        LOBYTE(a5) = 0;
        Printer = (void **)MyGetPrinter(*((HANDLE *)this + 4), 4u);
        v17 = Printer;
        if ( !Printer || (v18 = *Printer) == 0 )
          v18 = (void *)*((_QWORD *)this + 3);
        v19 = IsPsaEnabledForContract(v18, L"Windows.PrintSupportExtension", &a5);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5A9,
            (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\driverui.c",
            (const char *)(unsigned int)v19,
            (int)v24);
        if ( (_BYTE)a5 )
        {
          LODWORD(v24) = *(unsigned __int16 *)(*(_QWORD *)v9 + 68LL) + *(unsigned __int16 *)(*(_QWORD *)v9 + 70LL);
          v20 = UniDrvUI::TryPrintSupportValidation(
                  (void **)this,
                  *((struct UniDrvUI::_COMMONINFO **)this + 4),
                  v18,
                  (unsigned __int16 *)this + 44,
                  v24,
                  &v28,
                  (unsigned int *)this + 24);
          if ( v17 )
            LocalFree(v17);
          if ( v20 == -2147467263 )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "UniDrvUI::BFillCommonInfoDevmode",
              L"PrintSupport printTicket valdation not implemented. hr: 0x%x.");
            return 1;
          }
          if ( v20 < 0 )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "UniDrvUI::BFillCommonInfoDevmode",
              L"Can not perform PrintSupport printTicket valdation from legacy devmode path. hr: 0x%x.",
              (unsigned int)v20);
            return 0;
          }
        }
        else if ( v17 )
        {
          LocalFree(v17);
        }
LABEL_36:
        if ( v5 )
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
            "UniDrvUI::BFillCommonInfoDevmode",
            L"Populate the JT expansion block per caller request.");
          UniDrvUI::bDocOptionArrayToJTKeywords(this, 0, 0, v23);
        }
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::BFillCommonInfoDevmode", L"Exit.");
        return 1;
      }
    }
    else if ( v14 )
    {
      goto LABEL_36;
    }
    if ( !PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
    {
      bstrString = 0;
      v22 = PSUI::RetrieveDriverJScriptFilename(*((PSUI **)this + 4), &bstrString, v21);
      if ( v22 )
      {
        if ( v22 < 0 )
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::BFillCommonInfoDevmode",
            L"Can not perform IHV JScript printTicket valdation from legacy devmode path. hr: 0x%x.",
            (unsigned int)v22);
          if ( bstrString )
            SysFreeString(bstrString);
          return 0;
        }
      }
      else
      {
        UniDrvUI::PerformJScriptDevmodeValidation(
          this,
          *((struct UniDrvUI::_COMMONINFO **)this + 4),
          (const struct _devicemodeW **)this + 11,
          (struct _devicemodeW **)(*(unsigned __int16 *)(*(_QWORD *)v9 + 68LL)
                                 + (unsigned int)*(unsigned __int16 *)(*(_QWORD *)v9 + 70LL)),
          &a5,
          (unsigned int *)this + 24);
      }
      if ( bstrString )
        SysFreeString(bstrString);
    }
    goto LABEL_36;
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::BFillCommonInfoDevmode",
    L"The driver does not use print config module.");
  return 1;
}

```

## disassembly

```asm
0x18010e5ac  mov     rax, rsp
0x18010e5af  push    rbp
0x18010e5b0  push    rdi
0x18010e5b1  push    r12
0x18010e5b3  push    r13
0x18010e5b5  push    r15
0x18010e5b7  mov     rbp, rsp
0x18010e5ba  sub     rsp, 50h
0x18010e5be  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18010e5c6  mov     [rax+10h], rbx
0x18010e5ca  mov     [rax+18h], rsi
0x18010e5ce  mov     r13d, r9d
0x18010e5d1  mov     rbx, r8
0x18010e5d4  mov     rdi, rdx
0x18010e5d7  mov     rsi, rcx
0x18010e5da  xor     r9d, r9d
0x18010e5dd  cmp     [rbp+arg_20], r9d
0x18010e5e1  setnz   r9b
0x18010e5e5  xor     r8d, r8d
0x18010e5e8  test    r13d, r13d
0x18010e5eb  setnz   r8b
0x18010e5ef  lea     rdx, aPopulatesTheDe; "Populates the devmode fields in COMMONI"...
0x18010e5f6  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18010e5fd  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010e602  lea     r12, [rsi+60h]
0x18010e606  lea     r15, [rsi+58h]
0x18010e60a  mov     [rsp+50h+var_28], r12; struct _devicemodeW **
0x18010e60f  mov     [rsp+50h+var_30], r15; int
0x18010e614  mov     r9, rbx; unsigned int
0x18010e617  or      r8d, 0FFFFFFFFh; struct _devicemodeW *
0x18010e61b  mov     rdx, rdi; struct UniDrvUI::_COMMONINFO *
0x18010e61e  mov     rcx, rsi; this
0x18010e621  call    ?BGetValidatedUserDefaultDevmode@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@K1PEAPEAU3@PEAPEAU_UNIDRVEXTRA@@@Z; UniDrvUI::BGetValidatedUserDefaultDevmode(UniDrvUI::_COMMONINFO *,_devicemodeW *,ulong,_devicemodeW *,_devicemodeW * *,_UNIDRVEXTRA * *)
0x18010e626  test    eax, eax
0x18010e628  jnz     short loc_18010E659
0x18010e62a  call    cs:__imp_GetLastError
0x18010e630  test    eax, eax
0x18010e632  jle     short loc_18010E63C
0x18010e634  movzx   eax, ax
0x18010e637  or      eax, 80070000h
0x18010e63c  mov     r8d, eax
0x18010e63f  lea     rdx, aCanNotProcessD; "Can not process devmode information (hr"...
0x18010e646  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18010e64d  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010e652  xor     eax, eax
0x18010e654  jmp     loc_18010E88D
0x18010e659  cmp     [rbp+arg_20], 0
0x18010e65d  jz      loc_18010E850
0x18010e663  lea     rdx, aAttemptToPerfo; "Attempt to perform IHV JScript validato"...
0x18010e66a  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18010e671  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010e676  mov     rcx, [rsi+30h]
0x18010e67a  test    dword ptr [rcx+18h], 100000h
0x18010e681  jnz     short loc_18010E68F
0x18010e683  lea     rdx, aTheDriverDoesN; "The driver does not use print config mo"...
0x18010e68a  jmp     loc_18010E87C
0x18010e68f  mov     [rbp+arg_20], 0
0x18010e696  lea     rdx, [rbp+arg_20]; void *
0x18010e69a  mov     rcx, [rsi+20h]; this
0x18010e69e  call    ?IsIppOrMpsOrVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsIppOrMpsOrVirtualPrinterCommon(void *,int *)
0x18010e6a3  mov     edi, eax
0x18010e6a5  cmp     [rbp+arg_20], 0
0x18010e6a9  setnz   bl
0x18010e6ac  cmp     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x18010e6b3  jnz     short loc_18010E6E6
0x18010e6b5  xor     edx, edx; hFile
0x18010e6b7  mov     r8d, 800h; dwFlags
0x18010e6bd  lea     rcx, aPrintPrintsupp_1; "Print.PrintSupport.Source.dll"
0x18010e6c4  call    cs:__imp_LoadLibraryExW
0x18010e6ca  test    rax, rax
0x18010e6cd  jz      short loc_18010E6DF
0x18010e6cf  mov     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x18010e6d6  mov     rcx, rax; hLibModule
0x18010e6d9  call    cs:__imp_FreeLibrary
0x18010e6df  mov     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x18010e6e6  cmp     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x18010e6ed  jz      loc_18010E7EA
0x18010e6f3  test    edi, edi
0x18010e6f5  js      loc_18010E7EA
0x18010e6fb  test    bl, bl
0x18010e6fd  jz      loc_18010E7EE
0x18010e703  mov     byte ptr [rbp+arg_20], 0
0x18010e707  mov     edx, 4; Level
0x18010e70c  mov     rcx, [rsi+20h]; hPrinter
0x18010e710  call    MyGetPrinter
0x18010e715  mov     rbx, rax
0x18010e718  test    rax, rax
0x18010e71b  jz      short loc_18010E725
0x18010e71d  mov     rdi, [rax]
0x18010e720  test    rdi, rdi
0x18010e723  jnz     short loc_18010E729
0x18010e725  mov     rdi, [rsi+18h]
0x18010e729  lea     r8, [rbp+arg_20]
0x18010e72d  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x18010e734  mov     rcx, rdi
0x18010e737  call    cs:__imp_IsPsaEnabledForContract
0x18010e73d  mov     rcx, [rbp+28h]; this
0x18010e741  test    eax, eax
0x18010e743  jns     short loc_18010E759
0x18010e745  mov     r9d, eax; char *
0x18010e748  lea     r8, aPrintscanPrint_19; "printscan\\print\\drivers\\usermode\\dr"...
0x18010e74f  mov     edx, 5A9h; void *
0x18010e754  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010e759  cmp     byte ptr [rbp+arg_20], 0
0x18010e75d  jz      short loc_18010E7DA
0x18010e75f  mov     rax, [r15]
0x18010e762  movzx   ecx, word ptr [rax+46h]
0x18010e766  movzx   eax, word ptr [rax+44h]
0x18010e76a  add     ecx, eax
0x18010e76c  mov     [rsp+50h+var_20], r12; unsigned int *
0x18010e771  lea     rax, [rbp+arg_18]
0x18010e775  mov     [rsp+50h+var_28], rax; unsigned int
0x18010e77a  mov     dword ptr [rsp+50h+var_30], ecx; struct _devicemodeW **
0x18010e77e  mov     r9, r15; unsigned __int16 *
0x18010e781  mov     r8, rdi; void *
0x18010e784  mov     rdx, [rsi+20h]; struct UniDrvUI::_COMMONINFO *
0x18010e788  mov     rcx, rsi; this
0x18010e78b  call    ?TryPrintSupportValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z; UniDrvUI::TryPrintSupportValidation(UniDrvUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)
0x18010e790  mov     edi, eax
0x18010e792  test    rbx, rbx
0x18010e795  jz      short loc_18010E7A0
0x18010e797  mov     rcx, rbx; hMem
0x18010e79a  call    cs:__imp_LocalFree
0x18010e7a0  mov     r8d, 80004001h
0x18010e7a6  cmp     edi, r8d
0x18010e7a9  jnz     short loc_18010E7C3
0x18010e7ab  lea     rdx, aPrintsupportPr; "PrintSupport printTicket valdation not "...
0x18010e7b2  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18010e7b9  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010e7be  jmp     loc_18010E888
0x18010e7c3  test    edi, edi
0x18010e7c5  jns     loc_18010E850
0x18010e7cb  mov     r8d, edi
0x18010e7ce  lea     rdx, aCanNotPerformP; "Can not perform PrintSupport printTicke"...
0x18010e7d5  jmp     loc_18010E646
0x18010e7da  test    rbx, rbx
0x18010e7dd  jz      short loc_18010E850
0x18010e7df  mov     rcx, rbx; hMem
0x18010e7e2  call    cs:__imp_LocalFree
0x18010e7e8  jmp     short loc_18010E850
0x18010e7ea  test    bl, bl
0x18010e7ec  jnz     short loc_18010E850
0x18010e7ee  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x18010e7f3  test    al, al
0x18010e7f5  jnz     short loc_18010E850
0x18010e7f7  mov     [rbp+bstrString], 0
0x18010e7ff  lea     rdx, [rbp+bstrString]; void *
0x18010e803  mov     rcx, [rsi+20h]; this
0x18010e807  call    ?RetrieveDriverJScriptFilename@PSUI@@YAJPEAXPEAPEAG@Z; PSUI::RetrieveDriverJScriptFilename(void *,ushort * *)
0x18010e80c  test    eax, eax
0x18010e80e  jnz     loc_18010E8A6
0x18010e814  mov     rax, [r15]
0x18010e817  movzx   r9d, word ptr [rax+46h]
0x18010e81c  movzx   eax, word ptr [rax+44h]
0x18010e820  add     r9d, eax; struct _devicemodeW **
0x18010e823  mov     [rsp+50h+var_28], r12; unsigned int *
0x18010e828  lea     rax, [rbp+arg_20]
0x18010e82c  mov     [rsp+50h+var_30], rax; unsigned int
0x18010e831  mov     r8, r15; void *
0x18010e834  mov     rdx, [rsi+20h]; struct UniDrvUI::_COMMONINFO *
0x18010e838  mov     rcx, rsi; this
0x18010e83b  call    ?PerformJScriptDevmodeValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z; UniDrvUI::PerformJScriptDevmodeValidation(UniDrvUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)
0x18010e840  nop
0x18010e841  mov     rcx, [rbp+bstrString]; bstrString
0x18010e845  test    rcx, rcx
0x18010e848  jz      short loc_18010E850
0x18010e84a  call    cs:__imp_SysFreeString
0x18010e850  test    r13d, r13d
0x18010e853  jz      short loc_18010E875
0x18010e855  lea     rdx, aPopulateTheJtE; "Populate the JT expansion block per cal"...
0x18010e85c  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18010e863  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010e868  xor     r8d, r8d; struct _devicemodeW *
0x18010e86b  xor     edx, edx; struct UniDrvUI::_COMMONINFO *
0x18010e86d  mov     rcx, rsi; this
0x18010e870  call    ?bDocOptionArrayToJTKeywords@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@PEAU_OPTSELECT@@@Z; UniDrvUI::bDocOptionArrayToJTKeywords(UniDrvUI::_COMMONINFO *,_devicemodeW *,_OPTSELECT *)
0x18010e875  lea     rdx, aExit; "Exit."
0x18010e87c  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18010e883  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010e888  mov     eax, 1
0x18010e88d  lea     r11, [rsp+50h+var_s0]
0x18010e892  mov     rbx, [r11+38h]
0x18010e896  mov     rsi, [r11+40h]
0x18010e89a  mov     rsp, r11
0x18010e89d  pop     r15
0x18010e89f  pop     r13
0x18010e8a1  pop     r12
0x18010e8a3  pop     rdi
0x18010e8a4  pop     rbp
0x18010e8a5  retn
0x18010e8a6  jns     short loc_18010E841
0x18010e8a8  mov     r8d, eax
0x18010e8ab  lea     rdx, aCanNotPerformI; "Can not perform IHV JScript printTicket"...
0x18010e8b2  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18010e8b9  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010e8be  nop
0x18010e8bf  mov     rcx, [rbp+bstrString]; bstrString
0x18010e8c3  test    rcx, rcx
0x18010e8c6  jz      loc_18010E652
0x18010e8cc  call    cs:__imp_SysFreeString
0x18010e8d2  jmp     loc_18010E652
```

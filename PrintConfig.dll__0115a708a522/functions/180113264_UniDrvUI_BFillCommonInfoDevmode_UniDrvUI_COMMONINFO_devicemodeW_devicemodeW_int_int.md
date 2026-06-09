# UniDrvUI::BFillCommonInfoDevmode(UniDrvUI::_COMMONINFO *,_devicemodeW *,_devicemodeW *,int,int)

- ea: `0x180113264`
- end: `0x1801135c4`
- name: `?BFillCommonInfoDevmode@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@1HH@Z`
- size: `864`
- prototype: `__int64 __fastcall(UniDrvUI *this, struct UniDrvUI::_COMMONINFO *, struct _devicemodeW *, struct _devicemodeW *, unsigned int)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180109e0c`
- `0x18010abf4`
- `0x18010b490`
- `0x18010bf20`
- `0x18011150c`
- `0x180111908`
- `0x1801139d8`
- `0x1801143f4`
- `0x1801167fc`

## callees

- `0x180015d7c`
- `0x1800192fc`
- `0x180020a0c`
- `0x18010147c`
- `0x180107214`
- `0x180108e2c`
- `0x18010b86c`
- `0x180113264`
- `0x1801136a4`
- `0x180114e38`
- `0x180115610`
- `0x18014fa24`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18011339d`
- `KERNEL32!FreeLibrary` at `0x18011339d`
- `KERNEL32!GetLastError` at `0x1801132e2`
- `KERNEL32!GetLastError` at `0x1801132e2`
- `KERNEL32!LocalFree` at `0x18011346e`
- `KERNEL32!LocalFree` at `0x1801134bc`
- `KERNEL32!LocalFree` at `0x18011346e`
- `KERNEL32!LocalFree` at `0x1801134bc`
- `KERNEL32!LoadLibraryExW` at `0x180113382`
- `KERNEL32!LoadLibraryExW` at `0x180113382`
- `OLEAUT32!__imp_SysFreeString` at `0x18011352a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801135b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18011352a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801135b3`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x180113401`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x180113401`

## string_xrefs

- `0x1801133f7`: `Windows.PrintSupportExtension`
- `0x18011337b`: `Print.PrintSupport.Source.dll`
- `0x1801132ae`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x180113304`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x180113328`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x18011348c`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x180113542`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x180113562`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x180113599`: `UniDrvUI::BFillCommonInfoDevmode`
- `0x180113341`: `The driver does not use print config module.`
- `0x180113321`: `Attempt to perform IHV JScript validaton of the public devmode.`
- `0x1801132a7`: `Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .`
- `0x180113592`: `Can not perform IHV JScript printTicket valdation from legacy devmode path. hr: 0x%x.`
- `0x1801134a8`: `Can not perform PrintSupport printTicket valdation from legacy devmode path. hr: 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UniDrvUI::BFillCommonInfoDevmode(
        UniDrvUI *this,
        struct _devicemodeW *a2,
        struct _devicemodeW *a3,
        struct _devicemodeW *a4,
        unsigned int a5)
{
  int v5; // r13d
  char *v9; // r15
  signed int LastError; // eax
  struct _DRIVER_INFO_8W **v12; // r8
  int IsIppOrMpsOrVirtualPrinterCommon; // edi
  bool v14; // bl
  HMODULE Library; // rax
  BYTE *Printer; // rax
  BYTE *v17; // rbx
  void *v18; // rdi
  int v19; // eax
  int v20; // edi
  unsigned __int16 **v21; // r8
  int v22; // eax
  struct _OPTSELECT *v23; // r9
  struct _devicemodeW **v24; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  BSTR bstrString; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v27; // [rsp+98h] [rbp+48h] BYREF

  v5 = (int)a4;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::BFillCommonInfoDevmode",
    L"Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .",
    (_DWORD)a4 != 0,
    a5 != 0);
  v9 = (char *)this + 88;
  if ( !(unsigned int)UniDrvUI::BGetValidatedUserDefaultDevmode(
                        this,
                        a2,
                        (struct _devicemodeW *)0xFFFFFFFFLL,
                        a3,
                        (struct _devicemodeW *)((char *)this + 88),
                        (struct _devicemodeW **)this + 12) )
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
        Printer = MyGetPrinter(*((HANDLE *)this + 4), 4u);
        v17 = Printer;
        if ( !Printer || (v18 = *(void **)Printer) == 0 )
          v18 = (void *)*((_QWORD *)this + 3);
        v19 = IsPsaEnabledForContract(v18, L"Windows.PrintSupportExtension", &a5);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5A9,
            (__int64)"printscan\\print\\drivers\\usermode\\driverui\\driverui.c",
            (const char *)(unsigned int)v19);
        if ( (_BYTE)a5 )
        {
          LODWORD(v24) = *(unsigned __int16 *)(*(_QWORD *)v9 + 68LL) + *(unsigned __int16 *)(*(_QWORD *)v9 + 70LL);
          v20 = UniDrvUI::TryPrintSupportValidation(
                  (void **)this,
                  *((struct UniDrvUI::_COMMONINFO **)this + 4),
                  v18,
                  (unsigned __int16 *)this + 44,
                  v24,
                  &v27,
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
0x180113264  mov     rax, rsp
0x180113267  push    rbp
0x180113268  push    rdi
0x180113269  push    r12
0x18011326b  push    r13
0x18011326d  push    r15
0x18011326f  mov     rbp, rsp
0x180113272  sub     rsp, 50h
0x180113276  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18011327e  mov     [rax+10h], rbx
0x180113282  mov     [rax+18h], rsi
0x180113286  mov     r13d, r9d
0x180113289  mov     rbx, r8
0x18011328c  mov     rdi, rdx
0x18011328f  mov     rsi, rcx
0x180113292  xor     r9d, r9d
0x180113295  cmp     [rbp+arg_20], r9d
0x180113299  setnz   r9b
0x18011329d  xor     r8d, r8d
0x1801132a0  test    r13d, r13d
0x1801132a3  setnz   r8b
0x1801132a7  lea     rdx, aPopulatesTheDe; "Populates the devmode fields in COMMONI"...
0x1801132ae  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x1801132b5  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801132ba  lea     r12, [rsi+60h]
0x1801132be  lea     r15, [rsi+58h]
0x1801132c2  mov     [rsp+50h+var_28], r12; struct _devicemodeW **
0x1801132c7  mov     [rsp+50h+var_30], r15; int
0x1801132cc  mov     r9, rbx; unsigned int
0x1801132cf  or      r8d, 0FFFFFFFFh; struct _devicemodeW *
0x1801132d3  mov     rdx, rdi; struct UniDrvUI::_COMMONINFO *
0x1801132d6  mov     rcx, rsi; this
0x1801132d9  call    ?BGetValidatedUserDefaultDevmode@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@K1PEAPEAU3@PEAPEAU_UNIDRVEXTRA@@@Z; UniDrvUI::BGetValidatedUserDefaultDevmode(UniDrvUI::_COMMONINFO *,_devicemodeW *,ulong,_devicemodeW *,_devicemodeW * *,_UNIDRVEXTRA * *)
0x1801132de  test    eax, eax
0x1801132e0  jnz     short loc_180113317
0x1801132e2  call    cs:__imp_GetLastError
0x1801132e9  nop     dword ptr [rax+rax+00h]
0x1801132ee  test    eax, eax
0x1801132f0  jle     short loc_1801132FA
0x1801132f2  movzx   eax, ax
0x1801132f5  or      eax, 80070000h
0x1801132fa  mov     r8d, eax
0x1801132fd  lea     rdx, aCanNotProcessD; "Can not process devmode information (hr"...
0x180113304  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18011330b  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180113310  xor     eax, eax
0x180113312  jmp     loc_180113573
0x180113317  cmp     [rbp+arg_20], 0
0x18011331b  jz      loc_180113536
0x180113321  lea     rdx, aAttemptToPerfo; "Attempt to perform IHV JScript validato"...
0x180113328  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x18011332f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180113334  mov     rcx, [rsi+30h]
0x180113338  test    dword ptr [rcx+18h], 100000h
0x18011333f  jnz     short loc_18011334D
0x180113341  lea     rdx, aTheDriverDoesN; "The driver does not use print config mo"...
0x180113348  jmp     loc_180113562
0x18011334d  mov     [rbp+arg_20], 0
0x180113354  lea     rdx, [rbp+arg_20]; void *
0x180113358  mov     rcx, [rsi+20h]; this
0x18011335c  call    ?IsIppOrMpsOrVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsIppOrMpsOrVirtualPrinterCommon(void *,int *)
0x180113361  mov     edi, eax
0x180113363  cmp     [rbp+arg_20], 0
0x180113367  setnz   bl
0x18011336a  cmp     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x180113371  jnz     short loc_1801133B0
0x180113373  xor     edx, edx; hFile
0x180113375  mov     r8d, 800h; dwFlags
0x18011337b  lea     rcx, aPrintPrintsupp_1; "Print.PrintSupport.Source.dll"
0x180113382  call    cs:__imp_LoadLibraryExW
0x180113389  nop     dword ptr [rax+rax+00h]
0x18011338e  test    rax, rax
0x180113391  jz      short loc_1801133A9
0x180113393  mov     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x18011339a  mov     rcx, rax; hLibModule
0x18011339d  call    cs:__imp_FreeLibrary
0x1801133a4  nop     dword ptr [rax+rax+00h]
0x1801133a9  mov     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x1801133b0  cmp     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x1801133b7  jz      loc_1801134CA
0x1801133bd  test    edi, edi
0x1801133bf  js      loc_1801134CA
0x1801133c5  test    bl, bl
0x1801133c7  jz      loc_1801134CE
0x1801133cd  mov     byte ptr [rbp+arg_20], 0
0x1801133d1  mov     edx, 4; Level
0x1801133d6  mov     rcx, [rsi+20h]; hPrinter
0x1801133da  call    MyGetPrinter
0x1801133df  mov     rbx, rax
0x1801133e2  test    rax, rax
0x1801133e5  jz      short loc_1801133EF
0x1801133e7  mov     rdi, [rax]
0x1801133ea  test    rdi, rdi
0x1801133ed  jnz     short loc_1801133F3
0x1801133ef  mov     rdi, [rsi+18h]
0x1801133f3  lea     r8, [rbp+arg_20]
0x1801133f7  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x1801133fe  mov     rcx, rdi
0x180113401  call    cs:__imp_IsPsaEnabledForContract
0x180113408  nop     dword ptr [rax+rax+00h]
0x18011340d  mov     rcx, [rbp+28h]; this
0x180113411  test    eax, eax
0x180113413  jns     short loc_180113429
0x180113415  mov     r9d, eax; char *
0x180113418  lea     r8, aPrintscanPrint_19; "printscan\\print\\drivers\\usermode\\dr"...
0x18011341f  mov     edx, 5A9h; void *
0x180113424  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180113429  cmp     byte ptr [rbp+arg_20], 0
0x18011342d  jz      loc_1801134B4
0x180113433  mov     rax, [r15]
0x180113436  movzx   ecx, word ptr [rax+46h]
0x18011343a  movzx   eax, word ptr [rax+44h]
0x18011343e  add     ecx, eax
0x180113440  mov     [rsp+50h+var_20], r12; unsigned int *
0x180113445  lea     rax, [rbp+arg_18]
0x180113449  mov     [rsp+50h+var_28], rax; unsigned int
0x18011344e  mov     dword ptr [rsp+50h+var_30], ecx; struct _devicemodeW **
0x180113452  mov     r9, r15; unsigned __int16 *
0x180113455  mov     r8, rdi; void *
0x180113458  mov     rdx, [rsi+20h]; struct UniDrvUI::_COMMONINFO *
0x18011345c  mov     rcx, rsi; this
0x18011345f  call    ?TryPrintSupportValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z; UniDrvUI::TryPrintSupportValidation(UniDrvUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)
0x180113464  mov     edi, eax
0x180113466  test    rbx, rbx
0x180113469  jz      short loc_18011347A
0x18011346b  mov     rcx, rbx; hMem
0x18011346e  call    cs:__imp_LocalFree
0x180113475  nop     dword ptr [rax+rax+00h]
0x18011347a  mov     r8d, 80004001h
0x180113480  cmp     edi, r8d
0x180113483  jnz     short loc_18011349D
0x180113485  lea     rdx, aPrintsupportPr; "PrintSupport printTicket valdation not "...
0x18011348c  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x180113493  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180113498  jmp     loc_18011356E
0x18011349d  test    edi, edi
0x18011349f  jns     loc_180113536
0x1801134a5  mov     r8d, edi
0x1801134a8  lea     rdx, aCanNotPerformP; "Can not perform PrintSupport printTicke"...
0x1801134af  jmp     loc_180113304
0x1801134b4  test    rbx, rbx
0x1801134b7  jz      short loc_180113536
0x1801134b9  mov     rcx, rbx; hMem
0x1801134bc  call    cs:__imp_LocalFree
0x1801134c3  nop     dword ptr [rax+rax+00h]
0x1801134c8  jmp     short loc_180113536
0x1801134ca  test    bl, bl
0x1801134cc  jnz     short loc_180113536
0x1801134ce  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x1801134d3  test    al, al
0x1801134d5  jnz     short loc_180113536
0x1801134d7  mov     [rbp+bstrString], 0
0x1801134df  lea     rdx, [rbp+bstrString]; void *
0x1801134e3  mov     rcx, [rsi+20h]; this
0x1801134e7  call    ?RetrieveDriverJScriptFilename@PSUI@@YAJPEAXPEAPEAG@Z; PSUI::RetrieveDriverJScriptFilename(void *,ushort * *)
0x1801134ec  test    eax, eax
0x1801134ee  jnz     loc_18011358D
0x1801134f4  mov     rax, [r15]
0x1801134f7  movzx   r9d, word ptr [rax+46h]
0x1801134fc  movzx   eax, word ptr [rax+44h]
0x180113500  add     r9d, eax; struct _devicemodeW **
0x180113503  mov     [rsp+50h+var_28], r12; unsigned int *
0x180113508  lea     rax, [rbp+arg_20]
0x18011350c  mov     [rsp+50h+var_30], rax; unsigned int
0x180113511  mov     r8, r15; void *
0x180113514  mov     rdx, [rsi+20h]; struct UniDrvUI::_COMMONINFO *
0x180113518  mov     rcx, rsi; this
0x18011351b  call    ?PerformJScriptDevmodeValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z; UniDrvUI::PerformJScriptDevmodeValidation(UniDrvUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)
0x180113520  nop
0x180113521  mov     rcx, [rbp+bstrString]; bstrString
0x180113525  test    rcx, rcx
0x180113528  jz      short loc_180113536
0x18011352a  call    cs:__imp_SysFreeString
0x180113531  nop     dword ptr [rax+rax+00h]
0x180113536  test    r13d, r13d
0x180113539  jz      short loc_18011355B
0x18011353b  lea     rdx, aPopulateTheJtE; "Populate the JT expansion block per cal"...
0x180113542  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x180113549  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011354e  xor     r8d, r8d; struct _devicemodeW *
0x180113551  xor     edx, edx; struct UniDrvUI::_COMMONINFO *
0x180113553  mov     rcx, rsi; this
0x180113556  call    ?bDocOptionArrayToJTKeywords@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@PEAU_OPTSELECT@@@Z; UniDrvUI::bDocOptionArrayToJTKeywords(UniDrvUI::_COMMONINFO *,_devicemodeW *,_OPTSELECT *)
0x18011355b  lea     rdx, aExit; "Exit."
0x180113562  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x180113569  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011356e  mov     eax, 1
0x180113573  lea     r11, [rsp+50h+var_s0]
0x180113578  mov     rbx, [r11+38h]
0x18011357c  mov     rsi, [r11+40h]
0x180113580  mov     rsp, r11
0x180113583  pop     r15
0x180113585  pop     r13
0x180113587  pop     r12
0x180113589  pop     rdi
0x18011358a  pop     rbp
0x18011358b  retn
0x18011358d  jns     short loc_180113521
0x18011358f  mov     r8d, eax
0x180113592  lea     rdx, aCanNotPerformI; "Can not perform IHV JScript printTicket"...
0x180113599  lea     rcx, aUnidrvuiBfillc; "UniDrvUI::BFillCommonInfoDevmode"
0x1801135a0  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801135a5  nop
0x1801135a6  mov     rcx, [rbp+bstrString]; bstrString
0x1801135aa  test    rcx, rcx
0x1801135ad  jz      loc_180113310
0x1801135b3  call    cs:__imp_SysFreeString
0x1801135ba  nop     dword ptr [rax+rax+00h]
0x1801135bf  jmp     loc_180113310
```

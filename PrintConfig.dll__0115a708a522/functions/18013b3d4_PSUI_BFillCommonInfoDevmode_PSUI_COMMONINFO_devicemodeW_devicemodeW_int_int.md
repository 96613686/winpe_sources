# PSUI::BFillCommonInfoDevmode(PSUI::_COMMONINFO *,_devicemodeW *,_devicemodeW *,int,int)

- ea: `0x18013b3d4`
- end: `0x18013b734`
- name: `?BFillCommonInfoDevmode@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@1HH@Z`
- size: `864`
- prototype: `__int64 __fastcall(PSUI *this, struct PSUI::_COMMONINFO *, struct _devicemodeW *, struct _devicemodeW *, unsigned int)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180132a00`
- `0x180133b50`
- `0x1801343c0`
- `0x180134ce0`
- `0x180139bb4`
- `0x180139f20`
- `0x18013b9fc`
- `0x18013c170`
- `0x18013e2ec`

## callees

- `0x180015d7c`
- `0x1800192fc`
- `0x180020a0c`
- `0x18010147c`
- `0x180107214`
- `0x180108e2c`
- `0x180134660`
- `0x18013b3d4`
- `0x18013b814`
- `0x18013cbd8`
- `0x18013d3b0`
- `0x18014fa24`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18013b50d`
- `KERNEL32!FreeLibrary` at `0x18013b50d`
- `KERNEL32!GetLastError` at `0x18013b452`
- `KERNEL32!GetLastError` at `0x18013b452`
- `KERNEL32!LocalFree` at `0x18013b5de`
- `KERNEL32!LocalFree` at `0x18013b62c`
- `KERNEL32!LocalFree` at `0x18013b5de`
- `KERNEL32!LocalFree` at `0x18013b62c`
- `KERNEL32!LoadLibraryExW` at `0x18013b4f2`
- `KERNEL32!LoadLibraryExW` at `0x18013b4f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18013b69a`
- `OLEAUT32!__imp_SysFreeString` at `0x18013b723`
- `OLEAUT32!__imp_SysFreeString` at `0x18013b69a`
- `OLEAUT32!__imp_SysFreeString` at `0x18013b723`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x18013b571`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x18013b571`

## string_xrefs

- `0x18013b567`: `Windows.PrintSupportExtension`
- `0x18013b4eb`: `Print.PrintSupport.Source.dll`
- `0x18013b4b1`: `The driver does not use print config module.`
- `0x18013b491`: `Attempt to perform IHV JScript validaton of the public devmode.`
- `0x18013b417`: `Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .`
- `0x18013b702`: `Can not perform IHV JScript printTicket valdation from legacy devmode path. hr: 0x%x.`
- `0x18013b618`: `Can not perform PrintSupport printTicket valdation from legacy devmode path. hr: 0x%x.`
- `0x18013b41e`: `PSUI::BFillCommonInfoDevmode`
- `0x18013b474`: `PSUI::BFillCommonInfoDevmode`
- `0x18013b498`: `PSUI::BFillCommonInfoDevmode`
- `0x18013b5fc`: `PSUI::BFillCommonInfoDevmode`
- `0x18013b6b2`: `PSUI::BFillCommonInfoDevmode`
- `0x18013b6d2`: `PSUI::BFillCommonInfoDevmode`
- `0x18013b709`: `PSUI::BFillCommonInfoDevmode`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PSUI::BFillCommonInfoDevmode(
        PSUI *this,
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
    "PSUI::BFillCommonInfoDevmode",
    L"Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .",
    (_DWORD)a4 != 0,
    a5 != 0);
  v9 = (char *)this + 88;
  if ( !(unsigned int)PSUI::BGetValidatedUserDefaultDevmode(
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
      "PSUI::BFillCommonInfoDevmode",
      L"Can not process devmode information (hr: 0x%x).",
      (unsigned int)LastError);
    return 0;
  }
  if ( !a5 )
    goto LABEL_36;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::BFillCommonInfoDevmode",
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
          v20 = PSUI::TryPrintSupportValidation(
                  (void **)this,
                  *((struct PSUI::_COMMONINFO **)this + 4),
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
              "PSUI::BFillCommonInfoDevmode",
              L"PrintSupport printTicket valdation not implemented. hr: 0x%x.");
            return 1;
          }
          if ( v20 < 0 )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "PSUI::BFillCommonInfoDevmode",
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
            "PSUI::BFillCommonInfoDevmode",
            L"Populate the JT expansion block per caller request.");
          PSUI::bDocOptionArrayToJTKeywords(this, 0, 0, v23);
        }
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::BFillCommonInfoDevmode", L"Exit.");
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
            "PSUI::BFillCommonInfoDevmode",
            L"Can not perform IHV JScript printTicket valdation from legacy devmode path. hr: 0x%x.",
            (unsigned int)v22);
          if ( bstrString )
            SysFreeString(bstrString);
          return 0;
        }
      }
      else
      {
        PSUI::PerformJScriptDevmodeValidation(
          this,
          *((struct PSUI::_COMMONINFO **)this + 4),
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
    "PSUI::BFillCommonInfoDevmode",
    L"The driver does not use print config module.");
  return 1;
}

```

## disassembly

```asm
0x18013b3d4  mov     rax, rsp
0x18013b3d7  push    rbp
0x18013b3d8  push    rdi
0x18013b3d9  push    r12
0x18013b3db  push    r13
0x18013b3dd  push    r15
0x18013b3df  mov     rbp, rsp
0x18013b3e2  sub     rsp, 50h
0x18013b3e6  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18013b3ee  mov     [rax+10h], rbx
0x18013b3f2  mov     [rax+18h], rsi
0x18013b3f6  mov     r13d, r9d
0x18013b3f9  mov     rbx, r8
0x18013b3fc  mov     rdi, rdx
0x18013b3ff  mov     rsi, rcx
0x18013b402  xor     r9d, r9d
0x18013b405  cmp     [rbp+arg_20], r9d
0x18013b409  setnz   r9b
0x18013b40d  xor     r8d, r8d
0x18013b410  test    r13d, r13d
0x18013b413  setnz   r8b
0x18013b417  lea     rdx, aPopulatesTheDe; "Populates the devmode fields in COMMONI"...
0x18013b41e  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013b425  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013b42a  lea     r12, [rsi+60h]
0x18013b42e  lea     r15, [rsi+58h]
0x18013b432  mov     [rsp+50h+var_28], r12; struct _devicemodeW **
0x18013b437  mov     [rsp+50h+var_30], r15; int
0x18013b43c  mov     r9, rbx; unsigned int
0x18013b43f  or      r8d, 0FFFFFFFFh; struct _devicemodeW *
0x18013b443  mov     rdx, rdi; struct PSUI::_COMMONINFO *
0x18013b446  mov     rcx, rsi; this
0x18013b449  call    ?BGetValidatedUserDefaultDevmode@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@K1PEAPEAU3@PEAPEAU_PSDRVEXTRA@@@Z; PSUI::BGetValidatedUserDefaultDevmode(PSUI::_COMMONINFO *,_devicemodeW *,ulong,_devicemodeW *,_devicemodeW * *,_PSDRVEXTRA * *)
0x18013b44e  test    eax, eax
0x18013b450  jnz     short loc_18013B487
0x18013b452  call    cs:__imp_GetLastError
0x18013b459  nop     dword ptr [rax+rax+00h]
0x18013b45e  test    eax, eax
0x18013b460  jle     short loc_18013B46A
0x18013b462  movzx   eax, ax
0x18013b465  or      eax, 80070000h
0x18013b46a  mov     r8d, eax
0x18013b46d  lea     rdx, aCanNotProcessD; "Can not process devmode information (hr"...
0x18013b474  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013b47b  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013b480  xor     eax, eax
0x18013b482  jmp     loc_18013B6E3
0x18013b487  cmp     [rbp+arg_20], 0
0x18013b48b  jz      loc_18013B6A6
0x18013b491  lea     rdx, aAttemptToPerfo; "Attempt to perform IHV JScript validato"...
0x18013b498  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013b49f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013b4a4  mov     rcx, [rsi+30h]
0x18013b4a8  test    dword ptr [rcx+18h], 100000h
0x18013b4af  jnz     short loc_18013B4BD
0x18013b4b1  lea     rdx, aTheDriverDoesN; "The driver does not use print config mo"...
0x18013b4b8  jmp     loc_18013B6D2
0x18013b4bd  mov     [rbp+arg_20], 0
0x18013b4c4  lea     rdx, [rbp+arg_20]; void *
0x18013b4c8  mov     rcx, [rsi+20h]; this
0x18013b4cc  call    ?IsIppOrMpsOrVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsIppOrMpsOrVirtualPrinterCommon(void *,int *)
0x18013b4d1  mov     edi, eax
0x18013b4d3  cmp     [rbp+arg_20], 0
0x18013b4d7  setnz   bl
0x18013b4da  cmp     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x18013b4e1  jnz     short loc_18013B520
0x18013b4e3  xor     edx, edx; hFile
0x18013b4e5  mov     r8d, 800h; dwFlags
0x18013b4eb  lea     rcx, aPrintPrintsupp_1; "Print.PrintSupport.Source.dll"
0x18013b4f2  call    cs:__imp_LoadLibraryExW
0x18013b4f9  nop     dword ptr [rax+rax+00h]
0x18013b4fe  test    rax, rax
0x18013b501  jz      short loc_18013B519
0x18013b503  mov     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x18013b50a  mov     rcx, rax; hLibModule
0x18013b50d  call    cs:__imp_FreeLibrary
0x18013b514  nop     dword ptr [rax+rax+00h]
0x18013b519  mov     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x18013b520  cmp     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x18013b527  jz      loc_18013B63A
0x18013b52d  test    edi, edi
0x18013b52f  js      loc_18013B63A
0x18013b535  test    bl, bl
0x18013b537  jz      loc_18013B63E
0x18013b53d  mov     byte ptr [rbp+arg_20], 0
0x18013b541  mov     edx, 4; Level
0x18013b546  mov     rcx, [rsi+20h]; hPrinter
0x18013b54a  call    MyGetPrinter
0x18013b54f  mov     rbx, rax
0x18013b552  test    rax, rax
0x18013b555  jz      short loc_18013B55F
0x18013b557  mov     rdi, [rax]
0x18013b55a  test    rdi, rdi
0x18013b55d  jnz     short loc_18013B563
0x18013b55f  mov     rdi, [rsi+18h]
0x18013b563  lea     r8, [rbp+arg_20]
0x18013b567  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x18013b56e  mov     rcx, rdi
0x18013b571  call    cs:__imp_IsPsaEnabledForContract
0x18013b578  nop     dword ptr [rax+rax+00h]
0x18013b57d  mov     rcx, [rbp+28h]; this
0x18013b581  test    eax, eax
0x18013b583  jns     short loc_18013B599
0x18013b585  mov     r9d, eax; char *
0x18013b588  lea     r8, aPrintscanPrint_19; "printscan\\print\\drivers\\usermode\\dr"...
0x18013b58f  mov     edx, 5A9h; void *
0x18013b594  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013b599  cmp     byte ptr [rbp+arg_20], 0
0x18013b59d  jz      loc_18013B624
0x18013b5a3  mov     rax, [r15]
0x18013b5a6  movzx   ecx, word ptr [rax+46h]
0x18013b5aa  movzx   eax, word ptr [rax+44h]
0x18013b5ae  add     ecx, eax
0x18013b5b0  mov     [rsp+50h+var_20], r12; unsigned int *
0x18013b5b5  lea     rax, [rbp+arg_18]
0x18013b5b9  mov     [rsp+50h+var_28], rax; unsigned int
0x18013b5be  mov     dword ptr [rsp+50h+var_30], ecx; struct _devicemodeW **
0x18013b5c2  mov     r9, r15; unsigned __int16 *
0x18013b5c5  mov     r8, rdi; void *
0x18013b5c8  mov     rdx, [rsi+20h]; struct PSUI::_COMMONINFO *
0x18013b5cc  mov     rcx, rsi; this
0x18013b5cf  call    ?TryPrintSupportValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z; PSUI::TryPrintSupportValidation(PSUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)
0x18013b5d4  mov     edi, eax
0x18013b5d6  test    rbx, rbx
0x18013b5d9  jz      short loc_18013B5EA
0x18013b5db  mov     rcx, rbx; hMem
0x18013b5de  call    cs:__imp_LocalFree
0x18013b5e5  nop     dword ptr [rax+rax+00h]
0x18013b5ea  mov     r8d, 80004001h
0x18013b5f0  cmp     edi, r8d
0x18013b5f3  jnz     short loc_18013B60D
0x18013b5f5  lea     rdx, aPrintsupportPr; "PrintSupport printTicket valdation not "...
0x18013b5fc  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013b603  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013b608  jmp     loc_18013B6DE
0x18013b60d  test    edi, edi
0x18013b60f  jns     loc_18013B6A6
0x18013b615  mov     r8d, edi
0x18013b618  lea     rdx, aCanNotPerformP; "Can not perform PrintSupport printTicke"...
0x18013b61f  jmp     loc_18013B474
0x18013b624  test    rbx, rbx
0x18013b627  jz      short loc_18013B6A6
0x18013b629  mov     rcx, rbx; hMem
0x18013b62c  call    cs:__imp_LocalFree
0x18013b633  nop     dword ptr [rax+rax+00h]
0x18013b638  jmp     short loc_18013B6A6
0x18013b63a  test    bl, bl
0x18013b63c  jnz     short loc_18013B6A6
0x18013b63e  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x18013b643  test    al, al
0x18013b645  jnz     short loc_18013B6A6
0x18013b647  mov     [rbp+bstrString], 0
0x18013b64f  lea     rdx, [rbp+bstrString]; void *
0x18013b653  mov     rcx, [rsi+20h]; this
0x18013b657  call    ?RetrieveDriverJScriptFilename@PSUI@@YAJPEAXPEAPEAG@Z; PSUI::RetrieveDriverJScriptFilename(void *,ushort * *)
0x18013b65c  test    eax, eax
0x18013b65e  jnz     loc_18013B6FD
0x18013b664  mov     rax, [r15]
0x18013b667  movzx   r9d, word ptr [rax+46h]
0x18013b66c  movzx   eax, word ptr [rax+44h]
0x18013b670  add     r9d, eax; struct _devicemodeW **
0x18013b673  mov     [rsp+50h+var_28], r12; unsigned int *
0x18013b678  lea     rax, [rbp+arg_20]
0x18013b67c  mov     [rsp+50h+var_30], rax; unsigned int
0x18013b681  mov     r8, r15; void *
0x18013b684  mov     rdx, [rsi+20h]; struct PSUI::_COMMONINFO *
0x18013b688  mov     rcx, rsi; this
0x18013b68b  call    ?PerformJScriptDevmodeValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z; PSUI::PerformJScriptDevmodeValidation(PSUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)
0x18013b690  nop
0x18013b691  mov     rcx, [rbp+bstrString]; bstrString
0x18013b695  test    rcx, rcx
0x18013b698  jz      short loc_18013B6A6
0x18013b69a  call    cs:__imp_SysFreeString
0x18013b6a1  nop     dword ptr [rax+rax+00h]
0x18013b6a6  test    r13d, r13d
0x18013b6a9  jz      short loc_18013B6CB
0x18013b6ab  lea     rdx, aPopulateTheJtE; "Populate the JT expansion block per cal"...
0x18013b6b2  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013b6b9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013b6be  xor     r8d, r8d; struct _devicemodeW *
0x18013b6c1  xor     edx, edx; struct PSUI::_COMMONINFO *
0x18013b6c3  mov     rcx, rsi; this
0x18013b6c6  call    ?bDocOptionArrayToJTKeywords@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@PEAU_OPTSELECT@@@Z; PSUI::bDocOptionArrayToJTKeywords(PSUI::_COMMONINFO *,_devicemodeW *,_OPTSELECT *)
0x18013b6cb  lea     rdx, aExit; "Exit."
0x18013b6d2  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013b6d9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013b6de  mov     eax, 1
0x18013b6e3  lea     r11, [rsp+50h+var_s0]
0x18013b6e8  mov     rbx, [r11+38h]
0x18013b6ec  mov     rsi, [r11+40h]
0x18013b6f0  mov     rsp, r11
0x18013b6f3  pop     r15
0x18013b6f5  pop     r13
0x18013b6f7  pop     r12
0x18013b6f9  pop     rdi
0x18013b6fa  pop     rbp
0x18013b6fb  retn
0x18013b6fd  jns     short loc_18013B691
0x18013b6ff  mov     r8d, eax
0x18013b702  lea     rdx, aCanNotPerformI; "Can not perform IHV JScript printTicket"...
0x18013b709  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013b710  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013b715  nop
0x18013b716  mov     rcx, [rbp+bstrString]; bstrString
0x18013b71a  test    rcx, rcx
0x18013b71d  jz      loc_18013B480
0x18013b723  call    cs:__imp_SysFreeString
0x18013b72a  nop     dword ptr [rax+rax+00h]
0x18013b72f  jmp     loc_18013B480
```

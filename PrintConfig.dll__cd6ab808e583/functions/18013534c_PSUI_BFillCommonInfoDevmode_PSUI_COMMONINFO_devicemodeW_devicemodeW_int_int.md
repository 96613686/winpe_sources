# PSUI::BFillCommonInfoDevmode(PSUI::_COMMONINFO *,_devicemodeW *,_devicemodeW *,int,int)

- ea: `0x18013534c`
- end: `0x180135677`
- name: `?BFillCommonInfoDevmode@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@1HH@Z`
- size: `811`
- prototype: `__int64 __usercall@<rax>(PSUI *__hidden this@<rcx>, struct PSUI::_COMMONINFO *@<rdx>, struct _devicemodeW *@<r8>, struct _devicemodeW *@<r9>, int, int)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012cb5c`
- `0x18012dc54`
- `0x18012e4a0`
- `0x18012ed9c`
- `0x180133b68`
- `0x180133ecc`
- `0x18013592c`
- `0x180136084`
- `0x180138054`

## callees

- `0x1800153fc`
- `0x18001878c`
- `0x180020040`
- `0x1800fc90c`
- `0x180102674`
- `0x18010427c`
- `0x18012e72c`
- `0x18013534c`
- `0x18013574c`
- `0x180136a68`
- `0x1801371f0`
- `0x180148d9c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180135479`
- `KERNEL32!FreeLibrary` at `0x180135479`
- `KERNEL32!GetLastError` at `0x1801353ca`
- `KERNEL32!GetLastError` at `0x1801353ca`
- `KERNEL32!LocalFree` at `0x18013553a`
- `KERNEL32!LocalFree` at `0x180135582`
- `KERNEL32!LocalFree` at `0x18013553a`
- `KERNEL32!LocalFree` at `0x180135582`
- `KERNEL32!LoadLibraryExW` at `0x180135464`
- `KERNEL32!LoadLibraryExW` at `0x180135464`
- `OLEAUT32!__imp_SysFreeString` at `0x1801355ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18013566c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801355ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18013566c`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x1801354d7`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x1801354d7`

## string_xrefs

- `0x1801354cd`: `Windows.PrintSupportExtension`
- `0x18013545d`: `Print.PrintSupport.Source.dll`
- `0x18013538f`: `Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .`
- `0x18013556e`: `Can not perform PrintSupport printTicket valdation from legacy devmode path. hr: 0x%x.`
- `0x18013564b`: `Can not perform IHV JScript printTicket valdation from legacy devmode path. hr: 0x%x.`
- `0x180135403`: `Attempt to perform IHV JScript validaton of the public devmode.`
- `0x180135423`: `The driver does not use print config module.`
- `0x180135396`: `PSUI::BFillCommonInfoDevmode`
- `0x1801353e6`: `PSUI::BFillCommonInfoDevmode`
- `0x18013540a`: `PSUI::BFillCommonInfoDevmode`
- `0x180135552`: `PSUI::BFillCommonInfoDevmode`
- `0x1801355fc`: `PSUI::BFillCommonInfoDevmode`
- `0x18013561c`: `PSUI::BFillCommonInfoDevmode`
- `0x180135652`: `PSUI::BFillCommonInfoDevmode`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PSUI::BFillCommonInfoDevmode(
        PSUI *this,
        struct PSUI::_COMMONINFO *a2,
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
    "PSUI::BFillCommonInfoDevmode",
    L"Populates the devmode fields in COMMONINFO structure with bExpandJT: %d, bPerformExtensionValidation: %d .",
    (_DWORD)a4 != 0,
    a5 != 0);
  v9 = (char *)this + 88;
  if ( !PSUI::BGetValidatedUserDefaultDevmode(
          this,
          a2,
          (struct _devicemodeW *)0xFFFFFFFFLL,
          v6,
          (struct _devicemodeW *)((char *)this + 88),
          (struct _devicemodeW **)this + 12,
          (struct _PSDRVEXTRA **)v25) )
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
          v20 = PSUI::TryPrintSupportValidation(
                  (void **)this,
                  *((struct PSUI::_COMMONINFO **)this + 4),
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
0x18013534c  mov     rax, rsp
0x18013534f  push    rbp
0x180135350  push    rdi
0x180135351  push    r12
0x180135353  push    r13
0x180135355  push    r15
0x180135357  mov     rbp, rsp
0x18013535a  sub     rsp, 50h
0x18013535e  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180135366  mov     [rax+10h], rbx
0x18013536a  mov     [rax+18h], rsi
0x18013536e  mov     r13d, r9d
0x180135371  mov     rbx, r8
0x180135374  mov     rdi, rdx
0x180135377  mov     rsi, rcx
0x18013537a  xor     r9d, r9d
0x18013537d  cmp     [rbp+arg_20], r9d
0x180135381  setnz   r9b
0x180135385  xor     r8d, r8d
0x180135388  test    r13d, r13d
0x18013538b  setnz   r8b
0x18013538f  lea     rdx, aPopulatesTheDe; "Populates the devmode fields in COMMONI"...
0x180135396  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x18013539d  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801353a2  lea     r12, [rsi+60h]
0x1801353a6  lea     r15, [rsi+58h]
0x1801353aa  mov     [rsp+50h+var_28], r12; struct _devicemodeW **
0x1801353af  mov     [rsp+50h+var_30], r15; int
0x1801353b4  mov     r9, rbx; unsigned int
0x1801353b7  or      r8d, 0FFFFFFFFh; struct _devicemodeW *
0x1801353bb  mov     rdx, rdi; struct PSUI::_COMMONINFO *
0x1801353be  mov     rcx, rsi; this
0x1801353c1  call    ?BGetValidatedUserDefaultDevmode@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@K1PEAPEAU3@PEAPEAU_PSDRVEXTRA@@@Z; PSUI::BGetValidatedUserDefaultDevmode(PSUI::_COMMONINFO *,_devicemodeW *,ulong,_devicemodeW *,_devicemodeW * *,_PSDRVEXTRA * *)
0x1801353c6  test    eax, eax
0x1801353c8  jnz     short loc_1801353F9
0x1801353ca  call    cs:__imp_GetLastError
0x1801353d0  test    eax, eax
0x1801353d2  jle     short loc_1801353DC
0x1801353d4  movzx   eax, ax
0x1801353d7  or      eax, 80070000h
0x1801353dc  mov     r8d, eax
0x1801353df  lea     rdx, aCanNotProcessD; "Can not process devmode information (hr"...
0x1801353e6  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x1801353ed  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801353f2  xor     eax, eax
0x1801353f4  jmp     loc_18013562D
0x1801353f9  cmp     [rbp+arg_20], 0
0x1801353fd  jz      loc_1801355F0
0x180135403  lea     rdx, aAttemptToPerfo; "Attempt to perform IHV JScript validato"...
0x18013540a  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x180135411  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180135416  mov     rcx, [rsi+30h]
0x18013541a  test    dword ptr [rcx+18h], 100000h
0x180135421  jnz     short loc_18013542F
0x180135423  lea     rdx, aTheDriverDoesN; "The driver does not use print config mo"...
0x18013542a  jmp     loc_18013561C
0x18013542f  mov     [rbp+arg_20], 0
0x180135436  lea     rdx, [rbp+arg_20]; void *
0x18013543a  mov     rcx, [rsi+20h]; this
0x18013543e  call    ?IsIppOrMpsOrVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsIppOrMpsOrVirtualPrinterCommon(void *,int *)
0x180135443  mov     edi, eax
0x180135445  cmp     [rbp+arg_20], 0
0x180135449  setnz   bl
0x18013544c  cmp     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x180135453  jnz     short loc_180135486
0x180135455  xor     edx, edx; hFile
0x180135457  mov     r8d, 800h; dwFlags
0x18013545d  lea     rcx, aPrintPrintsupp_1; "Print.PrintSupport.Source.dll"
0x180135464  call    cs:__imp_LoadLibraryExW
0x18013546a  test    rax, rax
0x18013546d  jz      short loc_18013547F
0x18013546f  mov     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x180135476  mov     rcx, rax; hLibModule
0x180135479  call    cs:__imp_FreeLibrary
0x18013547f  mov     cs:?s_isLoadLibraryCheckDone@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 1; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x180135486  cmp     cs:?s_isPrintSupportAvailable@?1??IsPrintSupportAvailable@PrintSupportUtil@@YA_NXZ@4_NA, 0; bool `PrintSupportUtil::IsPrintSupportAvailable(void)'::`2'::s_isPrintSupportAvailable
0x18013548d  jz      loc_18013558A
0x180135493  test    edi, edi
0x180135495  js      loc_18013558A
0x18013549b  test    bl, bl
0x18013549d  jz      loc_18013558E
0x1801354a3  mov     byte ptr [rbp+arg_20], 0
0x1801354a7  mov     edx, 4; Level
0x1801354ac  mov     rcx, [rsi+20h]; hPrinter
0x1801354b0  call    MyGetPrinter
0x1801354b5  mov     rbx, rax
0x1801354b8  test    rax, rax
0x1801354bb  jz      short loc_1801354C5
0x1801354bd  mov     rdi, [rax]
0x1801354c0  test    rdi, rdi
0x1801354c3  jnz     short loc_1801354C9
0x1801354c5  mov     rdi, [rsi+18h]
0x1801354c9  lea     r8, [rbp+arg_20]
0x1801354cd  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x1801354d4  mov     rcx, rdi
0x1801354d7  call    cs:__imp_IsPsaEnabledForContract
0x1801354dd  mov     rcx, [rbp+28h]; this
0x1801354e1  test    eax, eax
0x1801354e3  jns     short loc_1801354F9
0x1801354e5  mov     r9d, eax; char *
0x1801354e8  lea     r8, aPrintscanPrint_19; "printscan\\print\\drivers\\usermode\\dr"...
0x1801354ef  mov     edx, 5A9h; void *
0x1801354f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801354f9  cmp     byte ptr [rbp+arg_20], 0
0x1801354fd  jz      short loc_18013557A
0x1801354ff  mov     rax, [r15]
0x180135502  movzx   ecx, word ptr [rax+46h]
0x180135506  movzx   eax, word ptr [rax+44h]
0x18013550a  add     ecx, eax
0x18013550c  mov     [rsp+50h+var_20], r12; unsigned int *
0x180135511  lea     rax, [rbp+arg_18]
0x180135515  mov     [rsp+50h+var_28], rax; unsigned int
0x18013551a  mov     dword ptr [rsp+50h+var_30], ecx; struct _devicemodeW **
0x18013551e  mov     r9, r15; unsigned __int16 *
0x180135521  mov     r8, rdi; void *
0x180135524  mov     rdx, [rsi+20h]; struct PSUI::_COMMONINFO *
0x180135528  mov     rcx, rsi; this
0x18013552b  call    ?TryPrintSupportValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z; PSUI::TryPrintSupportValidation(PSUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)
0x180135530  mov     edi, eax
0x180135532  test    rbx, rbx
0x180135535  jz      short loc_180135540
0x180135537  mov     rcx, rbx; hMem
0x18013553a  call    cs:__imp_LocalFree
0x180135540  mov     r8d, 80004001h
0x180135546  cmp     edi, r8d
0x180135549  jnz     short loc_180135563
0x18013554b  lea     rdx, aPrintsupportPr; "PrintSupport printTicket valdation not "...
0x180135552  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x180135559  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013555e  jmp     loc_180135628
0x180135563  test    edi, edi
0x180135565  jns     loc_1801355F0
0x18013556b  mov     r8d, edi
0x18013556e  lea     rdx, aCanNotPerformP; "Can not perform PrintSupport printTicke"...
0x180135575  jmp     loc_1801353E6
0x18013557a  test    rbx, rbx
0x18013557d  jz      short loc_1801355F0
0x18013557f  mov     rcx, rbx; hMem
0x180135582  call    cs:__imp_LocalFree
0x180135588  jmp     short loc_1801355F0
0x18013558a  test    bl, bl
0x18013558c  jnz     short loc_1801355F0
0x18013558e  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x180135593  test    al, al
0x180135595  jnz     short loc_1801355F0
0x180135597  mov     [rbp+bstrString], 0
0x18013559f  lea     rdx, [rbp+bstrString]; void *
0x1801355a3  mov     rcx, [rsi+20h]; this
0x1801355a7  call    ?RetrieveDriverJScriptFilename@PSUI@@YAJPEAXPEAPEAG@Z; PSUI::RetrieveDriverJScriptFilename(void *,ushort * *)
0x1801355ac  test    eax, eax
0x1801355ae  jnz     loc_180135646
0x1801355b4  mov     rax, [r15]
0x1801355b7  movzx   r9d, word ptr [rax+46h]
0x1801355bc  movzx   eax, word ptr [rax+44h]
0x1801355c0  add     r9d, eax; struct _devicemodeW **
0x1801355c3  mov     [rsp+50h+var_28], r12; unsigned int *
0x1801355c8  lea     rax, [rbp+arg_20]
0x1801355cc  mov     [rsp+50h+var_30], rax; unsigned int
0x1801355d1  mov     r8, r15; void *
0x1801355d4  mov     rdx, [rsi+20h]; struct PSUI::_COMMONINFO *
0x1801355d8  mov     rcx, rsi; this
0x1801355db  call    ?PerformJScriptDevmodeValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z; PSUI::PerformJScriptDevmodeValidation(PSUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)
0x1801355e0  nop
0x1801355e1  mov     rcx, [rbp+bstrString]; bstrString
0x1801355e5  test    rcx, rcx
0x1801355e8  jz      short loc_1801355F0
0x1801355ea  call    cs:__imp_SysFreeString
0x1801355f0  test    r13d, r13d
0x1801355f3  jz      short loc_180135615
0x1801355f5  lea     rdx, aPopulateTheJtE; "Populate the JT expansion block per cal"...
0x1801355fc  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x180135603  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180135608  xor     r8d, r8d; struct _devicemodeW *
0x18013560b  xor     edx, edx; struct PSUI::_COMMONINFO *
0x18013560d  mov     rcx, rsi; this
0x180135610  call    ?bDocOptionArrayToJTKeywords@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_devicemodeW@@PEAU_OPTSELECT@@@Z; PSUI::bDocOptionArrayToJTKeywords(PSUI::_COMMONINFO *,_devicemodeW *,_OPTSELECT *)
0x180135615  lea     rdx, aExit; "Exit."
0x18013561c  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x180135623  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180135628  mov     eax, 1
0x18013562d  lea     r11, [rsp+50h+var_s0]
0x180135632  mov     rbx, [r11+38h]
0x180135636  mov     rsi, [r11+40h]
0x18013563a  mov     rsp, r11
0x18013563d  pop     r15
0x18013563f  pop     r13
0x180135641  pop     r12
0x180135643  pop     rdi
0x180135644  pop     rbp
0x180135645  retn
0x180135646  jns     short loc_1801355E1
0x180135648  mov     r8d, eax
0x18013564b  lea     rdx, aCanNotPerformI; "Can not perform IHV JScript printTicket"...
0x180135652  lea     rcx, aPsuiBfillcommo_0; "PSUI::BFillCommonInfoDevmode"
0x180135659  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013565e  nop
0x18013565f  mov     rcx, [rbp+bstrString]; bstrString
0x180135663  test    rcx, rcx
0x180135666  jz      loc_1801353F2
0x18013566c  call    cs:__imp_SysFreeString
0x180135672  jmp     loc_1801353F2
```

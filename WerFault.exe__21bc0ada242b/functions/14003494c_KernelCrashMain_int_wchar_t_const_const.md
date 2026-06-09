# KernelCrashMain(int,wchar_t const * * const)

- ea: `0x14003494c`
- end: `0x140034d96`
- name: `?KernelCrashMain@@YAHHQEAPEB_W@Z`
- size: `1098`
- prototype: `__int64 __fastcall(int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d9f0`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000bcf8`
- `0x140011db4`
- `0x14001211c`
- `0x14003494c`
- `0x140034d9c`
- `0x140034ed8`
- `0x140035d20`
- `0x1400361e8`
- `0x140039230`
- `0x140039614`
- `0x140039820`
- `0x140039c40`
- `0x14005b7c4`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140034a0f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140034a0f`
- `ntdll!DbgPrint` at `0x140034a1f`
- `ntdll!DbgPrint` at `0x140034a1f`

## string_xrefs

- `0x140034d0f`: `Invalid number of command line params passed`
- `0x140034b20`: `ParseCommandLine`
- `0x140034d23`: `ParseCommandLine`
- `0x140034b0c`: `Invalid command lines passed`
- `0x140034d3c`: `Invalid command lines passed`

## pseudocode

```c
__int64 __fastcall KernelCrashMain(int a1, const wchar_t **const a2)
{
  const wchar_t *CommandLineW; // rax
  const wchar_t *v5; // rbx
  int v6; // ebx
  int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  wil::details *v11; // [rsp+20h] [rbp-E0h]
  bool v12; // [rsp+28h] [rbp-D8h]
  char *v13; // [rsp+30h] [rbp-D0h]
  _BYTE v14[128]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[520]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v16; // [rsp+2C8h] [rbp+1C8h]
  _QWORD v17[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v18; // [rsp+2E0h] [rbp+1E0h]
  _WORD *v19; // [rsp+2F0h] [rbp+1F0h]
  _WORD *v20; // [rsp+2F8h] [rbp+1F8h]
  _WORD v21[8]; // [rsp+300h] [rbp+200h] BYREF
  unsigned int DWORD; // [rsp+310h] [rbp+210h]
  int v23; // [rsp+314h] [rbp+214h]
  int v24; // [rsp+318h] [rbp+218h]
  __int64 v25; // [rsp+31Ch] [rbp+21Ch]
  wil::details::in1diag4 *retaddr; // [rsp+378h] [rbp+278h]

  memset_0(v14, 0, sizeof(v14));
  memset_0(v15, 0, sizeof(v15));
  v16 = 0;
  v17[0] = v17;
  v17[1] = v17;
  v18 = 0;
  v19 = v21;
  v20 = v21;
  v21[0] = 0;
  DWORD = -1;
  v23 = 0;
  v24 = -1;
  v25 = 0;
  CommandLineW = GetCommandLineW();
  DbgPrint("Starting kernel vertical - %S\r\n", CommandLineW);
  UtilCheckDebugWait(L"KernelReport");
  if ( (unsigned int)(a1 - 3) > 2 )
  {
    LODWORD(v11) = -2147024809;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
      "ParseCommandLine",
      v11,
      (int)"Invalid number of command line params passed",
      v13);
    goto LABEL_55;
  }
  v5 = a2[2];
  if ( *v5 != 45 )
    goto LABEL_18;
  if ( v5[1] == 99 && !v5[2] && a1 == 3 )
  {
    v6 = 1;
    goto LABEL_27;
  }
  if ( *v5 != 45 )
    goto LABEL_18;
  if ( v5[1] == 113 && !v5[2] && a1 == 3 )
  {
    v6 = 2;
    goto LABEL_27;
  }
  if ( *v5 == 45 && v5[1] == 108 && !v5[2] && a1 == 5 )
  {
    v6 = 3;
  }
  else
  {
LABEL_18:
    if ( !wcscmp_0(a2[2], L"-lc") && a1 == 5 )
    {
      v6 = 4;
    }
    else if ( !wcscmp_0(v5, L"-lcq") && a1 == 3 )
    {
      v6 = 5;
    }
    else if ( !wcscmp_0(v5, L"-re") && a1 == 4 )
    {
      v6 = 6;
    }
    else
    {
      v6 = 0;
      LODWORD(v11) = -2147024809;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
        "ParseCommandLine",
        v11,
        (int)"Invalid command lines passed",
        v13);
    }
  }
LABEL_27:
  if ( !v6 )
  {
LABEL_55:
    v7 = -2147467259;
    v8 = "Invalid command lines passed";
    v9 = 162;
    goto LABEL_56;
  }
  DWORD = UtilRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\CrashControl",
            L"CrashDumpEnabled",
            0xFFFFFFFF,
            0,
            v12);
  switch ( v6 )
  {
    case 1:
      v7 = CKernelReport::ConvertDumpAndReport((CKernelReport *)v14);
      if ( v7 < 0 )
      {
        v8 = "ConvertDumpAndReport failed";
        v9 = 183;
LABEL_56:
        LODWORD(v11) = v7;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)v9,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
          "KernelCrashMain",
          v11,
          (int)v8,
          v13);
        goto LABEL_57;
      }
      v7 = CKernelReport::ReportFromKQueue((CKernelReport *)v14);
      if ( v7 < 0 )
      {
        v8 = "ReportFromKQueue failed";
        v9 = 194;
        goto LABEL_56;
      }
      goto LABEL_53;
    case 2:
      v7 = CKernelReport::ReportFromKQueue((CKernelReport *)v14);
      if ( v7 < 0 )
      {
        v8 = "ReportFromKQueue failed";
        v9 = 207;
        goto LABEL_56;
      }
      goto LABEL_53;
    case 3:
      if ( a1 == 5 )
      {
        v7 = CKernelReport::ReportLiveReport((CKernelReport *)v14, a2[3], a2[4]);
        if ( v7 < 0 )
        {
          v8 = "ReportLiveReport failed";
          v9 = 218;
          goto LABEL_56;
        }
        goto LABEL_53;
      }
LABEL_52:
      LODWORD(v13) = v6;
      LODWORD(v11) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
        "KernelCrashMain",
        v11,
        (int)"Invalid mode passed: %u",
        v13);
LABEL_53:
      v7 = 0;
      goto LABEL_57;
    case 4:
      if ( a1 == 5 )
      {
        v7 = CKernelReport::ConvertLiveDumpAndReport((CKernelReport *)v14, a2[3], a2[4]);
        if ( v7 < 0 )
        {
          v8 = "ConvertLiveDumpAndReport failed";
          v9 = 229;
          goto LABEL_56;
        }
        goto LABEL_53;
      }
      goto LABEL_52;
    case 5:
      v7 = CKernelReport::ReportAllLiveReports((CKernelReport *)v14);
      if ( v7 < 0 )
      {
        v8 = "ReportAllLiveReports failed";
        v9 = 242;
        goto LABEL_56;
      }
      goto LABEL_53;
  }
  if ( a1 != 4 )
    goto LABEL_52;
  if ( UtilIsWinRE() )
  {
    v7 = CKernelReport::ReportFromWinRE((CKernelReport *)v14, a2[3]);
    if ( v7 < 0 )
    {
      v8 = "ReportFromWinRE failed";
      v9 = 260;
      goto LABEL_56;
    }
    goto LABEL_53;
  }
  v7 = 0;
  LODWORD(v11) = 0x80000000;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0xFC,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
    "KernelCrashMain",
    v11,
    (int)"Not in recovery environment",
    v13);
LABEL_57:
  CKernelReport::~CKernelReport((CKernelReport *)v14);
  return (unsigned int)v7 >> 31;
}

```

## disassembly

```asm
0x14003494c  push    rbp
0x14003494e  push    rbx
0x14003494f  push    rsi
0x140034950  push    rdi
0x140034951  push    r14
0x140034953  push    r15
0x140034955  lea     rbp, [rsp-248h]
0x14003495d  sub     rsp, 348h
0x140034964  mov     rax, cs:__security_cookie
0x14003496b  xor     rax, rsp
0x14003496e  mov     [rbp+270h+var_40], rax
0x140034975  mov     r14, rdx
0x140034978  mov     esi, ecx
0x14003497a  xor     edx, edx; Val
0x14003497c  mov     r8d, 80h; Size
0x140034982  lea     rcx, [rsp+370h+var_330]; void *
0x140034987  call    memset_0
0x14003498c  xor     edx, edx; Val
0x14003498e  mov     r8d, 208h; Size
0x140034994  lea     rcx, [rbp+270h+var_2B0]; void *
0x140034998  call    memset_0
0x14003499d  xor     r15d, r15d
0x1400349a0  mov     [rbp+270h+var_A8], r15
0x1400349a7  lea     rax, [rbp+270h+var_A0]
0x1400349ae  mov     [rbp+270h+var_A0], rax
0x1400349b5  lea     rax, [rbp+270h+var_A0]
0x1400349bc  mov     [rbp+270h+var_98], rax
0x1400349c3  xorps   xmm0, xmm0
0x1400349c6  movdqa  [rbp+270h+var_90], xmm0
0x1400349ce  lea     rax, [rbp+270h+var_70]
0x1400349d5  mov     [rbp+270h+var_80], rax
0x1400349dc  lea     rax, [rbp+270h+var_70]
0x1400349e3  mov     [rbp+270h+var_78], rax
0x1400349ea  mov     [rbp+270h+var_70], r15w
0x1400349f2  or      eax, 0FFFFFFFFh
0x1400349f5  mov     [rbp+270h+var_60], eax
0x1400349fb  mov     [rbp+270h+var_5C], r15d
0x140034a02  mov     [rbp+270h+var_58], eax
0x140034a08  mov     [rbp+270h+var_54], r15
0x140034a0f  call    cs:__imp_GetCommandLineW
0x140034a15  mov     rdx, rax
0x140034a18  lea     rcx, aStartingKernel; "Starting kernel vertical - %S\r\n"
0x140034a1f  call    cs:__imp_DbgPrint
0x140034a25  lea     rcx, aKernelreport; "KernelReport"
0x140034a2c  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x140034a31  lea     eax, [rsi-3]
0x140034a34  lea     rdi, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werfa"...
0x140034a3b  cmp     eax, 2
0x140034a3e  ja      loc_140034D08
0x140034a44  mov     rbx, [r14+10h]
0x140034a48  cmp     word ptr [rbx], 2Dh ; '-'
0x140034a4c  jnz     short loc_140034AAB
0x140034a4e  cmp     word ptr [rbx+2], 63h ; 'c'
0x140034a53  jnz     short loc_140034A69
0x140034a55  cmp     [rbx+4], r15w
0x140034a5a  jnz     short loc_140034A69
0x140034a5c  cmp     esi, 3
0x140034a5f  jnz     short loc_140034A69
0x140034a61  lea     ebx, [rsi-2]
0x140034a64  jmp     loc_140034B34
0x140034a69  cmp     word ptr [rbx], 2Dh ; '-'
0x140034a6d  jnz     short loc_140034AAB
0x140034a6f  cmp     word ptr [rbx+2], 71h ; 'q'
0x140034a74  jnz     short loc_140034A8A
0x140034a76  cmp     [rbx+4], r15w
0x140034a7b  jnz     short loc_140034A8A
0x140034a7d  cmp     esi, 3
0x140034a80  jnz     short loc_140034A8A
0x140034a82  lea     ebx, [rsi-1]
0x140034a85  jmp     loc_140034B34
0x140034a8a  cmp     word ptr [rbx], 2Dh ; '-'
0x140034a8e  jnz     short loc_140034AAB
0x140034a90  cmp     word ptr [rbx+2], 6Ch ; 'l'
0x140034a95  jnz     short loc_140034AAB
0x140034a97  cmp     [rbx+4], r15w
0x140034a9c  jnz     short loc_140034AAB
0x140034a9e  cmp     esi, 5
0x140034aa1  jnz     short loc_140034AAB
0x140034aa3  lea     ebx, [rsi-2]
0x140034aa6  jmp     loc_140034B34
0x140034aab  lea     rdx, aLc; "-lc"
0x140034ab2  mov     rcx, rbx; String1
0x140034ab5  call    wcscmp_0
0x140034aba  test    eax, eax
0x140034abc  jnz     short loc_140034AC8
0x140034abe  cmp     esi, 5
0x140034ac1  jnz     short loc_140034AC8
0x140034ac3  lea     ebx, [rax+4]
0x140034ac6  jmp     short loc_140034B34
0x140034ac8  lea     rdx, aLcq; "-lcq"
0x140034acf  mov     rcx, rbx; String1
0x140034ad2  call    wcscmp_0
0x140034ad7  test    eax, eax
0x140034ad9  jnz     short loc_140034AE5
0x140034adb  cmp     esi, 3
0x140034ade  jnz     short loc_140034AE5
0x140034ae0  lea     ebx, [rax+5]
0x140034ae3  jmp     short loc_140034B34
0x140034ae5  lea     rdx, aRe; "-re"
0x140034aec  mov     rcx, rbx; String1
0x140034aef  call    wcscmp_0
0x140034af4  test    eax, eax
0x140034af6  jnz     short loc_140034B02
0x140034af8  cmp     esi, 4
0x140034afb  jnz     short loc_140034B02
0x140034afd  lea     ebx, [rax+6]
0x140034b00  jmp     short loc_140034B34
0x140034b02  mov     ebx, r15d
0x140034b05  mov     rcx, [rbp+278h]; this
0x140034b0c  lea     rax, aInvalidCommand_0; "Invalid command lines passed"
0x140034b13  mov     qword ptr [rsp+370h+var_348], rax; bool
0x140034b18  mov     dword ptr [rsp+370h+var_350], 80070057h; wil::details *
0x140034b20  lea     r9, aParsecommandli; "ParseCommandLine"
0x140034b27  mov     r8, rdi; unsigned int
0x140034b2a  mov     edx, 70h ; 'p'; void *
0x140034b2f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140034b34  test    ebx, ebx
0x140034b36  jz      loc_140034D37
0x140034b3c  mov     [rsp+370h+var_350], r15; bool *
0x140034b41  or      r9d, 0FFFFFFFFh; unsigned int
0x140034b45  lea     r8, aCrashdumpenabl; "CrashDumpEnabled"
0x140034b4c  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x140034b53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140034b5a  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140034b5f  mov     [rbp+270h+var_60], eax
0x140034b65  cmp     ebx, 1
0x140034b68  jnz     short loc_140034BB0
0x140034b6a  lea     rcx, [rsp+370h+var_330]; this
0x140034b6f  call    ?ConvertDumpAndReport@CKernelReport@@QEAAJXZ; CKernelReport::ConvertDumpAndReport(void)
0x140034b74  mov     ebx, eax
0x140034b76  test    eax, eax
0x140034b78  jns     short loc_140034B8B
0x140034b7a  lea     rax, aConvertdumpand; "ConvertDumpAndReport failed"
0x140034b81  mov     edx, 0B7h
0x140034b86  jmp     loc_140034D48
0x140034b8b  lea     rcx, [rsp+370h+var_330]; this
0x140034b90  call    ?ReportFromKQueue@CKernelReport@@QEAAJXZ; CKernelReport::ReportFromKQueue(void)
0x140034b95  mov     ebx, eax
0x140034b97  test    eax, eax
0x140034b99  jns     loc_140034D03
0x140034b9f  lea     rax, aReportfromkque; "ReportFromKQueue failed"
0x140034ba6  mov     edx, 0C2h
0x140034bab  jmp     loc_140034D48
0x140034bb0  cmp     ebx, 2
0x140034bb3  jnz     short loc_140034BDA
0x140034bb5  lea     rcx, [rsp+370h+var_330]; this
0x140034bba  call    ?ReportFromKQueue@CKernelReport@@QEAAJXZ; CKernelReport::ReportFromKQueue(void)
0x140034bbf  mov     ebx, eax
0x140034bc1  test    eax, eax
0x140034bc3  jns     loc_140034D03
0x140034bc9  lea     rax, aReportfromkque; "ReportFromKQueue failed"
0x140034bd0  mov     edx, 0CFh
0x140034bd5  jmp     loc_140034D48
0x140034bda  cmp     ebx, 3
0x140034bdd  jnz     short loc_140034C15
0x140034bdf  cmp     esi, 5
0x140034be2  jnz     loc_140034CD0
0x140034be8  mov     r8, [r14+20h]; lpSubKey
0x140034bec  mov     rdx, [r14+18h]; wchar_t *
0x140034bf0  lea     rcx, [rsp+370h+var_330]; this
0x140034bf5  call    ?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)
0x140034bfa  mov     ebx, eax
0x140034bfc  test    eax, eax
0x140034bfe  jns     loc_140034D03
0x140034c04  lea     rax, aReportliverepo; "ReportLiveReport failed"
0x140034c0b  mov     edx, 0DAh
0x140034c10  jmp     loc_140034D48
0x140034c15  cmp     ebx, 4
0x140034c18  jnz     short loc_140034C50
0x140034c1a  cmp     esi, 5
0x140034c1d  jnz     loc_140034CD0
0x140034c23  mov     r8, [r14+20h]; wchar_t *
0x140034c27  mov     rdx, [r14+18h]; wchar_t *
0x140034c2b  lea     rcx, [rsp+370h+var_330]; this
0x140034c30  call    ?ConvertLiveDumpAndReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ConvertLiveDumpAndReport(wchar_t const *,wchar_t const *)
0x140034c35  mov     ebx, eax
0x140034c37  test    eax, eax
0x140034c39  jns     loc_140034D03
0x140034c3f  lea     rax, aConvertlivedum; "ConvertLiveDumpAndReport failed"
0x140034c46  mov     edx, 0E5h
0x140034c4b  jmp     loc_140034D48
0x140034c50  cmp     ebx, 5
0x140034c53  jnz     short loc_140034C7A
0x140034c55  lea     rcx, [rsp+370h+var_330]; this
0x140034c5a  call    ?ReportAllLiveReports@CKernelReport@@QEAAJXZ; CKernelReport::ReportAllLiveReports(void)
0x140034c5f  mov     ebx, eax
0x140034c61  test    eax, eax
0x140034c63  jns     loc_140034D03
0x140034c69  lea     rax, aReportallliver; "ReportAllLiveReports failed"
0x140034c70  mov     edx, 0F2h
0x140034c75  jmp     loc_140034D48
0x140034c7a  cmp     ebx, 6
0x140034c7d  jnz     short loc_140034CD0
0x140034c7f  cmp     esi, 4
0x140034c82  jnz     short loc_140034CD0
0x140034c84  call    ?UtilIsWinRE@@YA_NXZ; UtilIsWinRE(void)
0x140034c89  test    al, al
0x140034c8b  jnz     short loc_140034CAE
0x140034c8d  mov     ebx, r15d
0x140034c90  lea     rax, aNotInRecoveryE; "Not in recovery environment"
0x140034c97  mov     qword ptr [rsp+370h+var_348], rax
0x140034c9c  mov     dword ptr [rsp+370h+var_350], 80000000h
0x140034ca4  mov     edx, 0FCh
0x140034ca9  jmp     loc_140034D51
0x140034cae  mov     rdx, [r14+18h]; wchar_t *
0x140034cb2  lea     rcx, [rsp+370h+var_330]; this
0x140034cb7  call    ?ReportFromWinRE@CKernelReport@@QEAAJPEB_W@Z; CKernelReport::ReportFromWinRE(wchar_t const *)
0x140034cbc  mov     ebx, eax
0x140034cbe  test    eax, eax
0x140034cc0  jns     short loc_140034D03
0x140034cc2  lea     rax, aReportfromwinr; "ReportFromWinRE failed"
0x140034cc9  mov     edx, 104h
0x140034cce  jmp     short loc_140034D48
0x140034cd0  mov     rcx, [rbp+278h]; this
0x140034cd7  mov     dword ptr [rsp+370h+var_340], ebx; char *
0x140034cdb  lea     rax, aInvalidModePas; "Invalid mode passed: %u"
0x140034ce2  mov     qword ptr [rsp+370h+var_348], rax; int
0x140034ce7  mov     dword ptr [rsp+370h+var_350], 80000000h; wil::details *
0x140034cef  lea     r9, aKernelcrashmai; "KernelCrashMain"
0x140034cf6  mov     r8, rdi; unsigned int
0x140034cf9  mov     edx, 10Ah; void *
0x140034cfe  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140034d03  mov     ebx, r15d
0x140034d06  jmp     short loc_140034D68
0x140034d08  mov     rcx, [rbp+278h]; this
0x140034d0f  lea     rax, aInvalidNumberO; "Invalid number of command line params p"...
0x140034d16  mov     qword ptr [rsp+370h+var_348], rax; int
0x140034d1b  mov     dword ptr [rsp+370h+var_350], 80070057h; wil::details *
0x140034d23  lea     r9, aParsecommandli; "ParseCommandLine"
0x140034d2a  mov     r8, rdi; unsigned int
0x140034d2d  mov     edx, 43h ; 'C'; void *
0x140034d32  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140034d37  mov     ebx, 80004005h
0x140034d3c  lea     rax, aInvalidCommand_0; "Invalid command lines passed"
0x140034d43  mov     edx, 0A2h; void *
0x140034d48  mov     qword ptr [rsp+370h+var_348], rax; int
0x140034d4d  mov     dword ptr [rsp+370h+var_350], ebx; wil::details *
0x140034d51  lea     r9, aKernelcrashmai; "KernelCrashMain"
0x140034d58  mov     r8, rdi; unsigned int
0x140034d5b  mov     rcx, [rbp+278h]; this
0x140034d62  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140034d67  nop
0x140034d68  shr     ebx, 1Fh
0x140034d6b  lea     rcx, [rsp+370h+var_330]; this
0x140034d70  call    ??1CKernelReport@@QEAA@XZ; CKernelReport::~CKernelReport(void)
0x140034d75  mov     eax, ebx
0x140034d77  mov     rcx, [rbp+270h+var_40]
0x140034d7e  xor     rcx, rsp; StackCookie
0x140034d81  call    __security_check_cookie
0x140034d86  add     rsp, 348h
0x140034d8d  pop     r15
0x140034d8f  pop     r14
0x140034d91  pop     rdi
0x140034d92  pop     rsi
0x140034d93  pop     rbx
0x140034d94  pop     rbp
0x140034d95  retn
```

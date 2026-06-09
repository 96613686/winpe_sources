# KernelCrashMain(int,wchar_t const * * const)

- ea: `0x140036e5c`
- end: `0x1400372d4`
- name: `?KernelCrashMain@@YAHHQEAPEB_W@Z`
- size: `1144`
- prototype: `__int64 __fastcall(int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000ddb8`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000bee0`
- `0x1400125ec`
- `0x140012994`
- `0x1400149e8`
- `0x140036e5c`
- `0x1400372dc`
- `0x140037480`
- `0x140038274`
- `0x140038760`
- `0x14003b784`
- `0x14003bbd4`
- `0x14003be5c`
- `0x14003c2bc`
- `0x14005f564`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140036f1f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140036f1f`
- `ntdll!DbgPrint` at `0x140036f35`
- `ntdll!DbgPrint` at `0x140036f35`

## string_xrefs

- `0x14003724c`: `Invalid number of command line params passed`
- `0x14003704d`: `ParseCommandLine`
- `0x140037260`: `ParseCommandLine`
- `0x140037039`: `Invalid command lines passed`
- `0x140037279`: `Invalid command lines passed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      (void *)0x44,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
      "ParseCommandLine",
      v11,
      (int)"Invalid number of command line params passed",
      v13);
    goto LABEL_57;
  }
  v5 = a2[2];
  if ( *v5 != 45 )
    goto LABEL_18;
  if ( v5[1] == 99 && !v5[2] && a1 == 3 )
  {
    v6 = 1;
    goto LABEL_28;
  }
  if ( *v5 != 45 )
    goto LABEL_18;
  if ( v5[1] == 113 && !v5[2] && a1 == 3 )
  {
    v6 = 2;
    goto LABEL_28;
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
    else
    {
      v6 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl) )
      {
        if ( !wcscmp_0(a2[2], L"-re") && a1 == 4 )
          v6 = 6;
      }
      else
      {
        LODWORD(v11) = -2147024809;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
          "ParseCommandLine",
          v11,
          (int)"Invalid command lines passed",
          v13);
      }
    }
  }
LABEL_28:
  if ( !v6 )
  {
LABEL_57:
    v7 = -2147467259;
    v8 = "Invalid command lines passed";
    v9 = 166;
    goto LABEL_58;
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
        v9 = 187;
LABEL_58:
        LODWORD(v11) = v7;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)v9,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
          "KernelCrashMain",
          v11,
          (int)v8,
          v13);
        goto LABEL_59;
      }
      v7 = CKernelReport::ReportFromKQueue((CKernelReport *)v14);
      if ( v7 < 0 )
      {
        v8 = "ReportFromKQueue failed";
        v9 = 198;
        goto LABEL_58;
      }
      goto LABEL_55;
    case 2:
      v7 = CKernelReport::ReportFromKQueue((CKernelReport *)v14);
      if ( v7 < 0 )
      {
        v8 = "ReportFromKQueue failed";
        v9 = 211;
        goto LABEL_58;
      }
      goto LABEL_55;
    case 3:
      if ( a1 == 5 )
      {
        v7 = CKernelReport::ReportLiveReport((CKernelReport *)v14, a2[3], a2[4]);
        if ( v7 < 0 )
        {
          v8 = "ReportLiveReport failed";
          v9 = 222;
          goto LABEL_58;
        }
        goto LABEL_55;
      }
LABEL_54:
      LODWORD(v13) = v6;
      LODWORD(v11) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x111,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
        "KernelCrashMain",
        v11,
        (int)"Invalid mode passed: %u",
        v13);
      goto LABEL_55;
    case 4:
      if ( a1 == 5 )
      {
        v7 = CKernelReport::ConvertLiveDumpAndReport((CKernelReport *)v14, a2[3], a2[4]);
        if ( v7 < 0 )
        {
          v8 = "ConvertLiveDumpAndReport failed";
          v9 = 233;
          goto LABEL_58;
        }
        goto LABEL_55;
      }
      goto LABEL_54;
    case 5:
      v7 = CKernelReport::ReportAllLiveReports((CKernelReport *)v14);
      if ( v7 < 0 )
      {
        v8 = "ReportAllLiveReports failed";
        v9 = 246;
        goto LABEL_58;
      }
      goto LABEL_55;
  }
  if ( a1 != 4 )
    goto LABEL_54;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl) )
  {
LABEL_55:
    v7 = 0;
    goto LABEL_59;
  }
  if ( UtilIsWinRE() )
  {
    v7 = CKernelReport::ReportFromWinRE((CKernelReport *)v14, a2[3]);
    if ( v7 < 0 )
    {
      v8 = "ReportFromWinRE failed";
      v9 = 266;
      goto LABEL_58;
    }
    goto LABEL_55;
  }
  v7 = 0;
  LODWORD(v11) = 0x80000000;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x102,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelfault.cpp",
    "KernelCrashMain",
    v11,
    (int)"Not in recovery environment",
    v13);
LABEL_59:
  CKernelReport::~CKernelReport((CKernelReport *)v14);
  return (unsigned int)v7 >> 31;
}

```

## disassembly

```asm
0x140036e5c  push    rbp
0x140036e5e  push    rbx
0x140036e5f  push    rsi
0x140036e60  push    rdi
0x140036e61  push    r14
0x140036e63  push    r15
0x140036e65  lea     rbp, [rsp-248h]
0x140036e6d  sub     rsp, 348h
0x140036e74  mov     rax, cs:__security_cookie
0x140036e7b  xor     rax, rsp
0x140036e7e  mov     [rbp+270h+var_40], rax
0x140036e85  mov     r14, rdx
0x140036e88  mov     esi, ecx
0x140036e8a  xor     edx, edx; Val
0x140036e8c  mov     r8d, 80h; Size
0x140036e92  lea     rcx, [rsp+370h+var_330]; void *
0x140036e97  call    memset_0
0x140036e9c  xor     edx, edx; Val
0x140036e9e  mov     r8d, 208h; Size
0x140036ea4  lea     rcx, [rbp+270h+var_2B0]; void *
0x140036ea8  call    memset_0
0x140036ead  xor     r15d, r15d
0x140036eb0  mov     [rbp+270h+var_A8], r15
0x140036eb7  lea     rax, [rbp+270h+var_A0]
0x140036ebe  mov     [rbp+270h+var_A0], rax
0x140036ec5  lea     rax, [rbp+270h+var_A0]
0x140036ecc  mov     [rbp+270h+var_98], rax
0x140036ed3  xorps   xmm0, xmm0
0x140036ed6  movdqa  [rbp+270h+var_90], xmm0
0x140036ede  lea     rax, [rbp+270h+var_70]
0x140036ee5  mov     [rbp+270h+var_80], rax
0x140036eec  lea     rax, [rbp+270h+var_70]
0x140036ef3  mov     [rbp+270h+var_78], rax
0x140036efa  mov     [rbp+270h+var_70], r15w
0x140036f02  or      eax, 0FFFFFFFFh
0x140036f05  mov     [rbp+270h+var_60], eax
0x140036f0b  mov     [rbp+270h+var_5C], r15d
0x140036f12  mov     [rbp+270h+var_58], eax
0x140036f18  mov     [rbp+270h+var_54], r15
0x140036f1f  call    cs:__imp_GetCommandLineW
0x140036f26  nop     dword ptr [rax+rax+00h]
0x140036f2b  mov     rdx, rax
0x140036f2e  lea     rcx, aStartingKernel; "Starting kernel vertical - %S\r\n"
0x140036f35  call    cs:__imp_DbgPrint
0x140036f3c  nop     dword ptr [rax+rax+00h]
0x140036f41  lea     rcx, aKernelreport; "KernelReport"
0x140036f48  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x140036f4d  lea     eax, [rsi-3]
0x140036f50  lea     rdi, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werfa"...
0x140036f57  cmp     eax, 2
0x140036f5a  ja      loc_140037245
0x140036f60  mov     rbx, [r14+10h]
0x140036f64  cmp     word ptr [rbx], 2Dh ; '-'
0x140036f68  jnz     short loc_140036FC7
0x140036f6a  cmp     word ptr [rbx+2], 63h ; 'c'
0x140036f6f  jnz     short loc_140036F85
0x140036f71  cmp     [rbx+4], r15w
0x140036f76  jnz     short loc_140036F85
0x140036f78  cmp     esi, 3
0x140036f7b  jnz     short loc_140036F85
0x140036f7d  lea     ebx, [rsi-2]
0x140036f80  jmp     loc_140037061
0x140036f85  cmp     word ptr [rbx], 2Dh ; '-'
0x140036f89  jnz     short loc_140036FC7
0x140036f8b  cmp     word ptr [rbx+2], 71h ; 'q'
0x140036f90  jnz     short loc_140036FA6
0x140036f92  cmp     [rbx+4], r15w
0x140036f97  jnz     short loc_140036FA6
0x140036f99  cmp     esi, 3
0x140036f9c  jnz     short loc_140036FA6
0x140036f9e  lea     ebx, [rsi-1]
0x140036fa1  jmp     loc_140037061
0x140036fa6  cmp     word ptr [rbx], 2Dh ; '-'
0x140036faa  jnz     short loc_140036FC7
0x140036fac  cmp     word ptr [rbx+2], 6Ch ; 'l'
0x140036fb1  jnz     short loc_140036FC7
0x140036fb3  cmp     [rbx+4], r15w
0x140036fb8  jnz     short loc_140036FC7
0x140036fba  cmp     esi, 5
0x140036fbd  jnz     short loc_140036FC7
0x140036fbf  lea     ebx, [rsi-2]
0x140036fc2  jmp     loc_140037061
0x140036fc7  lea     rdx, aLc; "-lc"
0x140036fce  mov     rcx, rbx; String1
0x140036fd1  call    wcscmp_0
0x140036fd6  test    eax, eax
0x140036fd8  jnz     short loc_140036FE4
0x140036fda  cmp     esi, 5
0x140036fdd  jnz     short loc_140036FE4
0x140036fdf  lea     ebx, [rax+4]
0x140036fe2  jmp     short loc_140037061
0x140036fe4  lea     rdx, aLcq; "-lcq"
0x140036feb  mov     rcx, rbx; String1
0x140036fee  call    wcscmp_0
0x140036ff3  test    eax, eax
0x140036ff5  jnz     short loc_140037001
0x140036ff7  cmp     esi, 3
0x140036ffa  jnz     short loc_140037001
0x140036ffc  lea     ebx, [rax+5]
0x140036fff  jmp     short loc_140037061
0x140037001  mov     ebx, r15d
0x140037004  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl(void)'::`2'::impl
0x14003700b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(void)
0x140037010  test    al, al
0x140037012  jz      short loc_140037032
0x140037014  lea     rdx, aRe; "-re"
0x14003701b  mov     rcx, [r14+10h]; String1
0x14003701f  call    wcscmp_0
0x140037024  test    eax, eax
0x140037026  jnz     short loc_140037061
0x140037028  cmp     esi, 4
0x14003702b  jnz     short loc_140037061
0x14003702d  lea     ebx, [rax+6]
0x140037030  jmp     short loc_140037061
0x140037032  mov     rcx, [rbp+278h]; this
0x140037039  lea     rax, aInvalidCommand_0; "Invalid command lines passed"
0x140037040  mov     qword ptr [rsp+370h+var_348], rax; bool
0x140037045  mov     dword ptr [rsp+370h+var_350], 80070057h; wil::details *
0x14003704d  lea     r9, aParsecommandli; "ParseCommandLine"
0x140037054  mov     r8, rdi; unsigned int
0x140037057  mov     edx, 74h ; 't'; void *
0x14003705c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140037061  test    ebx, ebx
0x140037063  jz      loc_140037274
0x140037069  mov     [rsp+370h+var_350], r15; bool *
0x14003706e  or      r9d, 0FFFFFFFFh; unsigned int
0x140037072  lea     r8, aCrashdumpenabl; "CrashDumpEnabled"
0x140037079  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x140037080  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140037087  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x14003708c  mov     [rbp+270h+var_60], eax
0x140037092  cmp     ebx, 1
0x140037095  jnz     short loc_1400370DD
0x140037097  lea     rcx, [rsp+370h+var_330]; this
0x14003709c  call    ?ConvertDumpAndReport@CKernelReport@@QEAAJXZ; CKernelReport::ConvertDumpAndReport(void)
0x1400370a1  mov     ebx, eax
0x1400370a3  test    eax, eax
0x1400370a5  jns     short loc_1400370B8
0x1400370a7  lea     rax, aConvertdumpand; "ConvertDumpAndReport failed"
0x1400370ae  mov     edx, 0BBh
0x1400370b3  jmp     loc_140037285
0x1400370b8  lea     rcx, [rsp+370h+var_330]; this
0x1400370bd  call    ?ReportFromKQueue@CKernelReport@@QEAAJXZ; CKernelReport::ReportFromKQueue(void)
0x1400370c2  mov     ebx, eax
0x1400370c4  test    eax, eax
0x1400370c6  jns     loc_140037240
0x1400370cc  lea     rax, aReportfromkque; "ReportFromKQueue failed"
0x1400370d3  mov     edx, 0C6h
0x1400370d8  jmp     loc_140037285
0x1400370dd  cmp     ebx, 2
0x1400370e0  jnz     short loc_140037107
0x1400370e2  lea     rcx, [rsp+370h+var_330]; this
0x1400370e7  call    ?ReportFromKQueue@CKernelReport@@QEAAJXZ; CKernelReport::ReportFromKQueue(void)
0x1400370ec  mov     ebx, eax
0x1400370ee  test    eax, eax
0x1400370f0  jns     loc_140037240
0x1400370f6  lea     rax, aReportfromkque; "ReportFromKQueue failed"
0x1400370fd  mov     edx, 0D3h
0x140037102  jmp     loc_140037285
0x140037107  cmp     ebx, 3
0x14003710a  jnz     short loc_140037142
0x14003710c  cmp     esi, 5
0x14003710f  jnz     loc_14003720D
0x140037115  mov     r8, [r14+20h]; lpSubKey
0x140037119  mov     rdx, [r14+18h]; wchar_t *
0x14003711d  lea     rcx, [rsp+370h+var_330]; this
0x140037122  call    ?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)
0x140037127  mov     ebx, eax
0x140037129  test    eax, eax
0x14003712b  jns     loc_140037240
0x140037131  lea     rax, aReportliverepo; "ReportLiveReport failed"
0x140037138  mov     edx, 0DEh
0x14003713d  jmp     loc_140037285
0x140037142  cmp     ebx, 4
0x140037145  jnz     short loc_14003717D
0x140037147  cmp     esi, 5
0x14003714a  jnz     loc_14003720D
0x140037150  mov     r8, [r14+20h]; wchar_t *
0x140037154  mov     rdx, [r14+18h]; wchar_t *
0x140037158  lea     rcx, [rsp+370h+var_330]; this
0x14003715d  call    ?ConvertLiveDumpAndReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ConvertLiveDumpAndReport(wchar_t const *,wchar_t const *)
0x140037162  mov     ebx, eax
0x140037164  test    eax, eax
0x140037166  jns     loc_140037240
0x14003716c  lea     rax, aConvertlivedum; "ConvertLiveDumpAndReport failed"
0x140037173  mov     edx, 0E9h
0x140037178  jmp     loc_140037285
0x14003717d  cmp     ebx, 5
0x140037180  jnz     short loc_1400371A7
0x140037182  lea     rcx, [rsp+370h+var_330]; this
0x140037187  call    ?ReportAllLiveReports@CKernelReport@@QEAAJXZ; CKernelReport::ReportAllLiveReports(void)
0x14003718c  mov     ebx, eax
0x14003718e  test    eax, eax
0x140037190  jns     loc_140037240
0x140037196  lea     rax, aReportallliver; "ReportAllLiveReports failed"
0x14003719d  mov     edx, 0F6h
0x1400371a2  jmp     loc_140037285
0x1400371a7  cmp     ebx, 6
0x1400371aa  jnz     short loc_14003720D
0x1400371ac  cmp     esi, 4
0x1400371af  jnz     short loc_14003720D
0x1400371b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl(void)'::`2'::impl
0x1400371b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(void)
0x1400371bd  test    al, al
0x1400371bf  jz      short loc_140037240
0x1400371c1  call    ?UtilIsWinRE@@YA_NXZ; UtilIsWinRE(void)
0x1400371c6  test    al, al
0x1400371c8  jnz     short loc_1400371EB
0x1400371ca  mov     ebx, r15d
0x1400371cd  lea     rax, aNotInRecoveryE; "Not in recovery environment"
0x1400371d4  mov     qword ptr [rsp+370h+var_348], rax
0x1400371d9  mov     dword ptr [rsp+370h+var_350], 80000000h
0x1400371e1  mov     edx, 102h
0x1400371e6  jmp     loc_14003728E
0x1400371eb  mov     rdx, [r14+18h]; wchar_t *
0x1400371ef  lea     rcx, [rsp+370h+var_330]; this
0x1400371f4  call    ?ReportFromWinRE@CKernelReport@@QEAAJPEB_W@Z; CKernelReport::ReportFromWinRE(wchar_t const *)
0x1400371f9  mov     ebx, eax
0x1400371fb  test    eax, eax
0x1400371fd  jns     short loc_140037240
0x1400371ff  lea     rax, aReportfromwinr; "ReportFromWinRE failed"
0x140037206  mov     edx, 10Ah
0x14003720b  jmp     short loc_140037285
0x14003720d  mov     rcx, [rbp+278h]; this
0x140037214  mov     dword ptr [rsp+370h+var_340], ebx; char *
0x140037218  lea     rax, aInvalidModePas; "Invalid mode passed: %u"
0x14003721f  mov     qword ptr [rsp+370h+var_348], rax; int
0x140037224  mov     dword ptr [rsp+370h+var_350], 80000000h; wil::details *
0x14003722c  lea     r9, aKernelcrashmai; "KernelCrashMain"
0x140037233  mov     r8, rdi; unsigned int
0x140037236  mov     edx, 111h; void *
0x14003723b  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140037240  mov     ebx, r15d
0x140037243  jmp     short loc_1400372A5
0x140037245  mov     rcx, [rbp+278h]; this
0x14003724c  lea     rax, aInvalidNumberO; "Invalid number of command line params p"...
0x140037253  mov     qword ptr [rsp+370h+var_348], rax; int
0x140037258  mov     dword ptr [rsp+370h+var_350], 80070057h; wil::details *
0x140037260  lea     r9, aParsecommandli; "ParseCommandLine"
0x140037267  mov     r8, rdi; unsigned int
0x14003726a  mov     edx, 44h ; 'D'; void *
0x14003726f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140037274  mov     ebx, 80004005h
0x140037279  lea     rax, aInvalidCommand_0; "Invalid command lines passed"
0x140037280  mov     edx, 0A6h; void *
0x140037285  mov     qword ptr [rsp+370h+var_348], rax; int
0x14003728a  mov     dword ptr [rsp+370h+var_350], ebx; wil::details *
0x14003728e  lea     r9, aKernelcrashmai; "KernelCrashMain"
0x140037295  mov     r8, rdi; unsigned int
0x140037298  mov     rcx, [rbp+278h]; this
0x14003729f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400372a4  nop
0x1400372a5  shr     ebx, 1Fh
0x1400372a8  lea     rcx, [rsp+370h+var_330]; this
0x1400372ad  call    ??1CKernelReport@@QEAA@XZ; CKernelReport::~CKernelReport(void)
0x1400372b2  mov     eax, ebx
0x1400372b4  mov     rcx, [rbp+270h+var_40]
0x1400372bb  xor     rcx, rsp; StackCookie
0x1400372be  call    __security_check_cookie
0x1400372c3  add     rsp, 348h
0x1400372ca  pop     r15
0x1400372cc  pop     r14
0x1400372ce  pop     rdi
0x1400372cf  pop     rsi
0x1400372d0  pop     rbx
0x1400372d1  pop     rbp
0x1400372d2  retn
```

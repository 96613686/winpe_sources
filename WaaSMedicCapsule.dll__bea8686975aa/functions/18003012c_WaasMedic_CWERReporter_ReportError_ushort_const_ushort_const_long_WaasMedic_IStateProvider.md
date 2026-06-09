# WaasMedic::CWERReporter::ReportError(ushort const *,ushort const *,long,WaasMedic::IStateProvider *)

- ea: `0x18003012c`
- end: `0x18003045e`
- name: `?ReportError@CWERReporter@WaasMedic@@SAJPEBG0JPEAVIStateProvider@2@@Z`
- size: `818`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, struct WaasMedic::IStateProvider *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d420`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x1800251a8`
- `0x18002543c`
- `0x1800271c8`
- `0x18002ed2c`
- `0x18002f218`
- `0x18002f608`
- `0x18002f844`
- `0x18002fd7c`
- `0x180030098`
- `0x18003012c`
- `0x180030464`
- `0x180030ee8`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800303cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800303cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180030370`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180030370`
- `OLEAUT32!__imp_SysAllocString` at `0x180030396`
- `OLEAUT32!__imp_SysAllocString` at `0x180030396`
- `OLEAUT32!__imp_VariantInit` at `0x18003016a`
- `OLEAUT32!__imp_VariantInit` at `0x18003016a`
- `OLEAUT32!__imp_VariantClear` at `0x1800301ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800301ff`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003024f`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003024f`

## string_xrefs

- `0x1800301a3`: `%PROGRAMDATA%\USOShared\Logs`
- `0x180030198`: `%WINDIR%\Logs\WindowsUpdate`
- `0x1800301c9`: `Invalid pointer to CWERReporter::ReportError: pszScenario=%s, pszComponent=%s`
- `0x1800302b4`: `Failed to create instance for WER reporter with error hr=0x%08X`
- `0x18003028e`: `Skipping CRemediationPluginBase::ReportRemediationError for %s.`
- `0x18003040c`: `WER report sent successfully for scenario=%s, and component=%s. hr=0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CWERReporter::ReportError(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        struct WaasMedic::IStateProvider *a4)
{
  void *v8; // rdx
  int v9; // ebx
  __int64 i; // rdi
  void *v11; // rdx
  unsigned int v12; // edi
  struct CMedicEtwConsumer *Instance; // rax
  int v15; // eax
  int DefaultWERReportParamsWithScenario; // eax
  WaasMedic::CWERReporter *v17; // rcx
  const unsigned __int16 *v18; // rdx
  unsigned int v19; // r9d
  unsigned int v20; // r8d
  unsigned __int64 v21; // rdx
  __int64 (__fastcall *v22)(struct WaasMedic::IStateProvider *, unsigned __int64, const wchar_t *, VARIANTARG *); // rbx
  int v23; // eax
  int v24; // eax
  int v25; // [rsp+20h] [rbp-E0h]
  unsigned int v26; // [rsp+30h] [rbp-D0h]
  bool v27; // [rsp+40h] [rbp-C0h] BYREF
  WaasMedic::CWERReporter *v28; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  WaasMedic *v30[10]; // [rsp+70h] [rbp-90h] BYREF
  WaasMedic *v31[10]; // [rsp+C0h] [rbp-40h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v33; // [rsp+120h] [rbp+20h]
  OLECHAR psz[24]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v28 = 0;
  VariantInit(&pvarg);
  v27 = 0;
  memset_0(v30, 0, 0x48u);
  memset_0(v31, 0, 0x48u);
  *(_QWORD *)&SystemTime.wYear = L"%WINDIR%\\Logs\\WindowsUpdate";
  *(_QWORD *)&SystemTime.wHour = L"%PROGRAMDATA%\\USOShared\\Logs";
  v33 = L"%WINDIR%\\Logs\\waasmedic";
  if ( !a1 )
  {
    v9 = -2147467261;
    LogLevelW(2u, L"Invalid pointer to CWERReporter::ReportError: pszScenario=%s, pszComponent=%s", 0, a2);
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    goto LABEL_3;
  }
  Instance = CMedicEtwConsumer::getInstance();
  if ( *(_QWORD *)Instance != -1 )
    ControlTraceW(
      *(_QWORD *)Instance,
      L"ECCB175F-1EB2-43DA-BFB5-A8D58A40A4D7",
      *((PEVENT_TRACE_PROPERTIES *)Instance + 1),
      3u);
  v15 = WaasMedic::CWERReporter::NeedToSkipWERReport(a2, a4, &v27);
  v9 = v15;
  if ( v15 < 0 )
  {
    LogLevelW(2u, L"Failed to call CWERReporter::NeedToSkipWERReport with error hr=0x%08X", (unsigned int)v15);
    goto LABEL_3;
  }
  if ( v27 )
  {
    LogLevelW(4u, L"Skipping CRemediationPluginBase::ReportRemediationError for %s.", a2);
    goto LABEL_3;
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::CreateInstance(&v28);
  v9 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v18 = L"Failed to create instance for WER reporter with error hr=0x%08X";
LABEL_17:
    LogLevelW(2u, v18, (unsigned int)DefaultWERReportParamsWithScenario);
    goto LABEL_34;
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::GetDefaultWERReportParamsWithScenario(
                                         v17,
                                         a1,
                                         a2,
                                         a3,
                                         (unsigned __int16 **const)v30,
                                         (unsigned __int16 **const)v31,
                                         v26);
  v9 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v18 = L"Failed to initialize the WER reporter with default parameters and scenarios with error hr=0x%08X";
    goto LABEL_17;
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::PopulateWERReportParameters(
                                         v28,
                                         (unsigned __int16 **const)v30,
                                         (unsigned __int16 **const)v31,
                                         v19);
  v9 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v18 = L"Failed to execute WER reporter with error hr=0x%08X";
    goto LABEL_17;
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::AddDirectoriesToWERReport(
                                         v28,
                                         (unsigned __int16 **const)&SystemTime,
                                         v20);
  v9 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v18 = L"Failed to add directories to the WER report! hr = 0x%08x";
    goto LABEL_17;
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::SubmitWERReport(v28);
  v9 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v18 = L"Failed to submit WER report! hr = 0x%08x";
    goto LABEL_17;
  }
  pvarg.vt = 8;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( (int)WaasMedic::TimeHelper::SystemTimeToString(psz, v21, &SystemTime) < 0 )
  {
    pvarg.llVal = 0;
LABEL_30:
    v9 = -2147024882;
    LogLevelW(2u, L"Failed to allocate memory for saving Last Wer reporting RunTime with error hr=0x%08X", 2147942414LL);
    goto LABEL_34;
  }
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
    goto LABEL_30;
  v22 = *(__int64 (__fastcall **)(struct WaasMedic::IStateProvider *, unsigned __int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)a4 + 24LL);
  v23 = _o__wcsicmp(L"Engine", a2);
  DefaultWERReportParamsWithScenario = v22(
                                         a4,
                                         (unsigned __int64)a2 & -(__int64)(v23 != 0),
                                         L"WerReportingLastRunTime",
                                         &pvarg);
  v9 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v18 = L"Failed to persist the last WER reporting RunTime with error hr=0x%08X";
    goto LABEL_17;
  }
  v25 = DefaultWERReportParamsWithScenario;
  LogLevelW(4u, L"WER report sent successfully for scenario=%s, and component=%s. hr=0x%08X", a1, a2);
LABEL_34:
  if ( v28 )
  {
    v24 = WaasMedic::CWERReporter::DestroyInstance(&v28);
    v12 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41E,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\werreporter.cpp",
        (const char *)(unsigned int)v24,
        v25);
      goto LABEL_6;
    }
  }
LABEL_3:
  for ( i = 0; i != 9; ++i )
  {
    WaasMedic::SafeFree(v30[i], v8);
    WaasMedic::SafeFree(v31[i], v11);
  }
  v12 = v9;
LABEL_6:
  VariantClear(&pvarg);
  return v12;
}

```

## disassembly

```asm
0x18003012c  push    rbp
0x18003012e  push    rbx
0x18003012f  push    rdi
0x180030130  push    r12
0x180030132  push    r14
0x180030134  push    r15
0x180030136  lea     rbp, [rsp-68h]
0x18003013b  sub     rsp, 168h
0x180030142  mov     rax, cs:__security_cookie
0x180030149  xor     rax, rsp
0x18003014c  mov     [rbp+90h+var_38], rax
0x180030150  mov     r14, r9
0x180030153  mov     r12d, r8d
0x180030156  mov     rdi, rdx
0x180030159  mov     r15, rcx
0x18003015c  mov     [rsp+190h+var_148], 0
0x180030165  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18003016a  call    cs:__imp_VariantInit
0x180030170  nop
0x180030171  mov     [rsp+190h+var_150], 0
0x180030176  mov     ebx, 48h ; 'H'
0x18003017b  mov     r8d, ebx; Size
0x18003017e  xor     edx, edx; Val
0x180030180  lea     rcx, [rsp+190h+var_120]; void *
0x180030185  call    memset_0
0x18003018a  mov     r8d, ebx; Size
0x18003018d  xor     edx, edx; Val
0x18003018f  lea     rcx, [rbp+90h+var_D0]; void *
0x180030193  call    memset_0
0x180030198  lea     rax, aWindirLogsWind; "%WINDIR%\\Logs\\WindowsUpdate"
0x18003019f  mov     qword ptr [rbp+90h+SystemTime.wYear], rax
0x1800301a3  lea     rax, aProgramdataUso; "%PROGRAMDATA%\\USOShared\\Logs"
0x1800301aa  mov     qword ptr [rbp+90h+SystemTime.wHour], rax
0x1800301ae  lea     rax, aWindirLogsWaas; "%WINDIR%\\Logs\\waasmedic"
0x1800301b5  mov     [rbp+90h+var_70], rax
0x1800301b9  test    r15, r15
0x1800301bc  jnz     short loc_180030224
0x1800301be  mov     ebx, 80004003h
0x1800301c3  mov     r9, rdi
0x1800301c6  xor     r8d, r8d
0x1800301c9  lea     rdx, aInvalidPointer_5; "Invalid pointer to CWERReporter::Report"...
0x1800301d0  lea     ecx, [r15+2]; unsigned __int8
0x1800301d4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800301d9  xor     edi, edi
0x1800301db  mov     rcx, [rsp+rdi*8+190h+var_120]; this
0x1800301e0  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x1800301e5  mov     rcx, [rbp+rdi*8+90h+var_D0]; this
0x1800301ea  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x1800301ef  inc     rdi
0x1800301f2  cmp     rdi, 9
0x1800301f6  jnz     short loc_1800301DB
0x1800301f8  mov     edi, ebx
0x1800301fa  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1800301ff  call    cs:__imp_VariantClear
0x180030205  mov     eax, edi
0x180030207  mov     rcx, [rbp+90h+var_38]
0x18003020b  xor     rcx, rsp; StackCookie
0x18003020e  call    __security_check_cookie
0x180030213  add     rsp, 168h
0x18003021a  pop     r15
0x18003021c  pop     r14
0x18003021e  pop     r12
0x180030220  pop     rdi
0x180030221  pop     rbx
0x180030222  pop     rbp
0x180030223  retn
0x180030224  test    r14, r14
0x180030227  jnz     short loc_180030230
0x180030229  mov     ebx, 80004003h
0x18003022e  jmp     short loc_1800301D9
0x180030230  call    ?getInstance@CMedicEtwConsumer@@SAAEAV1@XZ; CMedicEtwConsumer::getInstance(void)
0x180030235  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x180030239  jz      short loc_180030255
0x18003023b  mov     r9d, 3; ControlCode
0x180030241  mov     r8, [rax+8]; Properties
0x180030245  lea     rdx, InstanceName; "ECCB175F-1EB2-43DA-BFB5-A8D58A40A4D7"
0x18003024c  mov     rcx, [rax]; TraceHandle
0x18003024f  call    cs:__imp_ControlTraceW
0x180030255  lea     r8, [rsp+190h+var_150]; bool *
0x18003025a  mov     rdx, r14; struct WaasMedic::IStateProvider *
0x18003025d  mov     rcx, rdi; unsigned __int16 *
0x180030260  call    ?NeedToSkipWERReport@CWERReporter@WaasMedic@@SAJPEBGPEAVIStateProvider@2@PEA_N@Z; WaasMedic::CWERReporter::NeedToSkipWERReport(ushort const *,WaasMedic::IStateProvider *,bool *)
0x180030265  mov     ebx, eax
0x180030267  test    eax, eax
0x180030269  jns     short loc_180030284
0x18003026b  mov     r8d, eax
0x18003026e  lea     rdx, aFailedToCallCw; "Failed to call CWERReporter::NeedToSkip"...
0x180030275  mov     ecx, 2; unsigned __int8
0x18003027a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003027f  jmp     loc_1800301D9
0x180030284  cmp     [rsp+190h+var_150], 0
0x180030289  jz      short loc_1800302A4
0x18003028b  mov     r8, rdi
0x18003028e  lea     rdx, aSkippingCremed; "Skipping CRemediationPluginBase::Report"...
0x180030295  mov     ecx, 4; unsigned __int8
0x18003029a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003029f  jmp     loc_1800301D9
0x1800302a4  lea     rcx, [rsp+190h+var_148]; struct WaasMedic::CWERReporter **
0x1800302a9  call    ?CreateInstance@CWERReporter@WaasMedic@@SAJPEAPEAV12@@Z; WaasMedic::CWERReporter::CreateInstance(WaasMedic::CWERReporter * *)
0x1800302ae  mov     ebx, eax
0x1800302b0  test    eax, eax
0x1800302b2  jns     short loc_1800302CD
0x1800302b4  lea     rdx, aFailedToCreate_6; "Failed to create instance for WER repor"...
0x1800302bb  mov     r8d, eax
0x1800302be  mov     ecx, 2; unsigned __int8
0x1800302c3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800302c8  jmp     loc_18003041D
0x1800302cd  lea     rax, [rbp+90h+var_D0]
0x1800302d1  mov     [rsp+190h+var_168], rax; unsigned __int16 **
0x1800302d6  lea     rax, [rsp+190h+var_120]
0x1800302db  mov     [rsp+190h+var_170], rax; unsigned __int16 **
0x1800302e0  mov     r9d, r12d; int
0x1800302e3  mov     r8, rdi; unsigned __int16 *
0x1800302e6  mov     rdx, r15; unsigned __int16 *
0x1800302e9  call    ?GetDefaultWERReportParamsWithScenario@CWERReporter@WaasMedic@@QEAAJPEBG0JQEAPEAG1K@Z; WaasMedic::CWERReporter::GetDefaultWERReportParamsWithScenario(ushort const *,ushort const *,long,ushort * * const,ushort * * const,ulong)
0x1800302ee  mov     ebx, eax
0x1800302f0  test    eax, eax
0x1800302f2  jns     short loc_1800302FD
0x1800302f4  lea     rdx, aFailedToInitia_0; "Failed to initialize the WER reporter w"...
0x1800302fb  jmp     short loc_1800302BB
0x1800302fd  lea     r8, [rbp+90h+var_D0]; unsigned __int16 **
0x180030301  lea     rdx, [rsp+190h+var_120]; unsigned __int16 **
0x180030306  mov     rcx, [rsp+190h+var_148]; this
0x18003030b  call    ?PopulateWERReportParameters@CWERReporter@WaasMedic@@QEAAJQEAPEAG0K@Z; WaasMedic::CWERReporter::PopulateWERReportParameters(ushort * * const,ushort * * const,ulong)
0x180030310  mov     ebx, eax
0x180030312  test    eax, eax
0x180030314  jns     short loc_18003031F
0x180030316  lea     rdx, aFailedToExecut_0; "Failed to execute WER reporter with err"...
0x18003031d  jmp     short loc_1800302BB
0x18003031f  lea     rdx, [rbp+90h+SystemTime]; unsigned __int16 **
0x180030323  mov     rcx, [rsp+190h+var_148]; this
0x180030328  call    ?AddDirectoriesToWERReport@CWERReporter@WaasMedic@@QEAAJQEAPEAGK@Z; WaasMedic::CWERReporter::AddDirectoriesToWERReport(ushort * * const,ulong)
0x18003032d  mov     ebx, eax
0x18003032f  test    eax, eax
0x180030331  jns     short loc_18003033F
0x180030333  lea     rdx, aFailedToAddDir; "Failed to add directories to the WER re"...
0x18003033a  jmp     loc_1800302BB
0x18003033f  mov     rcx, [rsp+190h+var_148]; this
0x180030344  call    ?SubmitWERReport@CWERReporter@WaasMedic@@QEAAJXZ; WaasMedic::CWERReporter::SubmitWERReport(void)
0x180030349  mov     ebx, eax
0x18003034b  test    eax, eax
0x18003034d  jns     short loc_18003035B
0x18003034f  lea     rdx, aFailedToSubmit; "Failed to submit WER report! hr = 0x%08"...
0x180030356  jmp     loc_1800302BB
0x18003035b  mov     eax, 8
0x180030360  mov     word ptr [rsp+190h+pvarg], ax
0x180030365  xorps   xmm0, xmm0
0x180030368  movups  xmmword ptr [rbp+90h+SystemTime.wYear], xmm0
0x18003036c  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x180030370  call    cs:__imp_GetSystemTime
0x180030376  lea     r8, [rbp+90h+SystemTime]; struct _SYSTEMTIME *
0x18003037a  lea     rcx, [rbp+90h+psz]; unsigned __int16 *
0x18003037e  call    ?SystemTimeToString@TimeHelper@WaasMedic@@SAJPEAG_KAEBU_SYSTEMTIME@@@Z; WaasMedic::TimeHelper::SystemTimeToString(ushort *,unsigned __int64,_SYSTEMTIME const &)
0x180030383  test    eax, eax
0x180030385  jns     short loc_180030392
0x180030387  mov     qword ptr [rsp+190h+pvarg+8], 0
0x180030390  jmp     short loc_1800303A6
0x180030392  lea     rcx, [rbp+90h+psz]; psz
0x180030396  call    cs:__imp_SysAllocString
0x18003039c  mov     qword ptr [rsp+190h+pvarg+8], rax
0x1800303a1  test    rax, rax
0x1800303a4  jnz     short loc_1800303BA
0x1800303a6  mov     ebx, 8007000Eh
0x1800303ab  mov     r8d, ebx
0x1800303ae  lea     rdx, aFailedToAlloca_30; "Failed to allocate memory for saving La"...
0x1800303b5  jmp     loc_1800302BE
0x1800303ba  mov     rax, [r14]
0x1800303bd  mov     rbx, [rax+18h]
0x1800303c1  mov     rdx, rdi
0x1800303c4  lea     rcx, aEngine; "Engine"
0x1800303cb  call    cs:__imp__o__wcsicmp
0x1800303d1  neg     eax
0x1800303d3  sbb     rdx, rdx
0x1800303d6  and     rdx, rdi
0x1800303d9  lea     r9, [rsp+190h+pvarg]
0x1800303de  lea     r8, aWerreportingla; "WerReportingLastRunTime"
0x1800303e5  mov     rcx, r14
0x1800303e8  mov     rax, rbx
0x1800303eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303f0  mov     ebx, eax
0x1800303f2  test    eax, eax
0x1800303f4  jns     short loc_180030402
0x1800303f6  lea     rdx, aFailedToPersis; "Failed to persist the last WER reportin"...
0x1800303fd  jmp     loc_1800302BB
0x180030402  mov     dword ptr [rsp+190h+var_170], eax; int
0x180030406  mov     r9, rdi
0x180030409  mov     r8, r15
0x18003040c  lea     rdx, aWerReportSentS; "WER report sent successfully for scenar"...
0x180030413  mov     ecx, 4; unsigned __int8
0x180030418  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003041d  cmp     [rsp+190h+var_148], 0
0x180030423  jz      loc_1800301D9
0x180030429  lea     rcx, [rsp+190h+var_148]; struct WaasMedic::CWERReporter **
0x18003042e  call    ?DestroyInstance@CWERReporter@WaasMedic@@SAJPEAPEAV12@@Z; WaasMedic::CWERReporter::DestroyInstance(WaasMedic::CWERReporter * *)
0x180030433  mov     edi, eax
0x180030435  test    eax, eax
0x180030437  jns     loc_1800301D9
0x18003043d  mov     rcx, [rbp+98h]; this
0x180030444  mov     r9d, eax; char *
0x180030447  lea     r8, aOnecoreEnduser_28; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003044e  mov     edx, 41Eh; void *
0x180030453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030458  jmp     loc_1800301FA
```

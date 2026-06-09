# WaasMedic::CWERReporter::ReportError(ushort const *,ushort const *,long,WaasMedic::IStateProvider *)

- ea: `0x18002c844`
- end: `0x18002cbbb`
- name: `?ReportError@CWERReporter@WaasMedic@@SAJPEBG0JPEAVIStateProvider@2@@Z`
- size: `887`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, struct WaasMedic::IStateProvider *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017a60`
- `0x1800184b0`

## callees

- `0x1800050a0`
- `0x180005584`
- `0x180005bbc`
- `0x18001d994`
- `0x18002a24c`
- `0x18002a4e4`
- `0x18002b53c`
- `0x18002b63c`
- `0x18002b824`
- `0x18002bde8`
- `0x18002c2dc`
- `0x18002c844`
- `0x18002e81c`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002caf5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002caf5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002ca9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002ca9a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cabc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cabc`
- `OLEAUT32!__imp_VariantInit` at `0x18002c87a`
- `OLEAUT32!__imp_VariantInit` at `0x18002c87a`
- `OLEAUT32!__imp_VariantClear` at `0x18002cb87`
- `OLEAUT32!__imp_VariantClear` at `0x18002cb87`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002c8f6`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002c8f6`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x18002c9c5`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x18002c9c5`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x18002ca3f`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x18002ca3f`

## string_xrefs

- `0x18002cb33`: `AllPluginsIneffective`
- `0x18002ca52`: `CWERReporter::SubmitWERReport - WER report upload completed with WER status 0x%08x (hr=0x%08x)`
- `0x18002c8b2`: `%PROGRAMDATA%\USOShared\Logs`
- `0x18002c8a7`: `%WINDIR%\Logs\WindowsUpdate`
- `0x18002c95f`: `Failed to create instance for WER reporter with error hr=0x%08X`
- `0x18002c936`: `Skipping CRemediationPluginBase::ReportRemediationError for %s.`
- `0x18002cb3a`: `WER report sent successfully for scenario=%s, and component=%s. hr=0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall WaasMedic::CWERReporter::ReportError(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        struct WaasMedic::IStateProvider *a4)
{
  void *v5; // rdx
  unsigned int v6; // ebx
  struct CMedicEtwConsumer *Instance; // rax
  const unsigned __int16 *v8; // rcx
  int v9; // eax
  int DefaultWERReportParamsWithScenario; // eax
  const unsigned __int16 *v11; // rdx
  WaasMedic::CWERReporter *v12; // rcx
  const unsigned __int16 *v13; // r8
  int v14; // r9d
  void **v15; // rdi
  const unsigned __int16 *v16; // rdx
  DWORD i; // esi
  PCWSTR v18; // r14
  const WCHAR *v19; // r15
  HRESULT v20; // eax
  HRESULT v21; // eax
  unsigned __int64 v22; // rdx
  __int64 (__fastcall *v23)(struct WaasMedic::IStateProvider *, unsigned __int64, const wchar_t *, VARIANTARG *); // rbx
  int v24; // eax
  __int64 j; // rdi
  void *v26; // rdx
  HRESULT v27; // eax
  unsigned __int16 **v29; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v30; // [rsp+28h] [rbp-D8h]
  unsigned int v31; // [rsp+30h] [rbp-D0h]
  bool v32; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR pwzName[10]; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR pwzValue[10]; // [rsp+B0h] [rbp-50h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult[4]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR psz[4]; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v38; // [rsp+118h] [rbp+18h]
  const WCHAR *v39; // [rsp+120h] [rbp+20h]

  *(_QWORD *)pSubmitResult = 0;
  VariantInit(&pvarg);
  v32 = 0;
  memset_0(pwzName, 0, 0x48u);
  memset_0(pwzValue, 0, 0x48u);
  *(_QWORD *)psz = L"%WINDIR%\\Logs\\WindowsUpdate";
  v38 = L"%PROGRAMDATA%\\USOShared\\Logs";
  v39 = L"%WINDIR%\\Logs\\waasmedic";
  if ( !a4 )
  {
    v6 = -2147467261;
    goto LABEL_36;
  }
  Instance = CMedicEtwConsumer::getInstance();
  if ( *(_QWORD *)Instance != -1 )
    ControlTraceW(
      *(_QWORD *)Instance,
      L"ECCB175F-1EB2-43DA-BFB5-A8D58A40A4D7",
      *((PEVENT_TRACE_PROPERTIES *)Instance + 1),
      3u);
  v9 = WaasMedic::CWERReporter::NeedToSkipWERReport(v8, a4, &v32);
  v6 = v9;
  if ( v9 < 0 )
  {
    LogLevelW(2u, L"Failed to call CWERReporter::NeedToSkipWERReport with error hr=0x%08X", (unsigned int)v9);
    goto LABEL_36;
  }
  if ( v32 )
  {
    LogLevelW(4u, L"Skipping CRemediationPluginBase::ReportRemediationError for %s.", L"Engine");
    goto LABEL_36;
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::CreateInstance((struct WaasMedic::CWERReporter **)pSubmitResult);
  v6 = DefaultWERReportParamsWithScenario;
  v15 = *(void ***)pSubmitResult;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v16 = L"Failed to create instance for WER reporter with error hr=0x%08X";
    goto LABEL_11;
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::GetDefaultWERReportParamsWithScenario(
                                         v12,
                                         v11,
                                         v13,
                                         v14,
                                         (unsigned __int16 **const)pwzName,
                                         (unsigned __int16 **const)pwzValue,
                                         v31);
  v6 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v16 = L"Failed to initialize the WER reporter with default parameters and scenarios with error hr=0x%08X";
    goto LABEL_11;
  }
  for ( i = 0; i < 9; ++i )
  {
    v18 = pwzName[i];
    if ( !v18 || !*v18 )
      break;
    v19 = pwzValue[i];
    v20 = WerReportSetParameter(v15[6], i, pwzName[i], v19);
    v6 = v20;
    if ( v20 < 0 )
    {
      LODWORD(v30) = v20;
      LogLevelW(2u, L"Failed to set %u parameter %s with value %s! hr = 0x%08x", i, v18, v19, v30);
      LogLevelW(2u, L"Failed to execute WER reporter with error hr=0x%08X", v6);
      goto LABEL_34;
    }
  }
  DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::AddDirectoriesToWERReport(
                                         v15,
                                         (unsigned __int16 **const)psz);
  v6 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario < 0 )
  {
    v16 = L"Failed to add directories to the WER report! hr = 0x%08x";
    goto LABEL_11;
  }
  pSubmitResult[0] = WerReportQueued;
  v21 = WerReportSubmit(v15[6], WerConsentNotAsked, 4u, pSubmitResult);
  v6 = v21;
  if ( v21 < 0 )
    LogLevelW(
      3u,
      L"CWERReporter::SubmitWERReport - WER report upload completed with WER status 0x%08x (hr=0x%08x)",
      (unsigned int)pSubmitResult[0],
      (unsigned int)v21);
  LogLevelW(4u, L"CWERReporter finished handling the event. Error = (0x%08x)", v6);
  if ( (v6 & 0x80000000) != 0 )
  {
    LogLevelW(2u, L"Failed to submit WER report! hr = 0x%08x", v6);
    goto LABEL_34;
  }
  pvarg.vt = 8;
  *(_OWORD *)pSubmitResult = 0;
  GetSystemTime((LPSYSTEMTIME)pSubmitResult);
  if ( (int)WaasMedic::TimeHelper::SystemTimeToString(psz, v22, (const struct _SYSTEMTIME *)pSubmitResult) < 0 )
  {
    pvarg.llVal = 0;
LABEL_30:
    v6 = -2147024882;
    LogLevelW(2u, L"Failed to allocate memory for saving Last Wer reporting RunTime with error hr=0x%08X", 2147942414LL);
    goto LABEL_34;
  }
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
    goto LABEL_30;
  v23 = *(__int64 (__fastcall **)(struct WaasMedic::IStateProvider *, unsigned __int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)a4 + 24LL);
  v24 = _o__wcsicmp(L"Engine", L"Engine");
  DefaultWERReportParamsWithScenario = v23(
                                         a4,
                                         (unsigned __int64)L"Engine" & -(__int64)(v24 != 0),
                                         L"WerReportingLastRunTime",
                                         &pvarg);
  v6 = DefaultWERReportParamsWithScenario;
  if ( DefaultWERReportParamsWithScenario >= 0 )
  {
    LODWORD(v29) = DefaultWERReportParamsWithScenario;
    LogLevelW(
      4u,
      L"WER report sent successfully for scenario=%s, and component=%s. hr=0x%08X",
      L"AllPluginsIneffective",
      L"Engine",
      v29);
    goto LABEL_34;
  }
  v16 = L"Failed to persist the last WER reporting RunTime with error hr=0x%08X";
LABEL_11:
  LogLevelW(2u, v16, (unsigned int)DefaultWERReportParamsWithScenario);
LABEL_34:
  if ( v15 )
  {
    WaasMedic::CWERReporter::~CWERReporter((WaasMedic::CWERReporter *)v15);
    operator delete(v15, (const struct std::nothrow_t *)0x38);
  }
LABEL_36:
  for ( j = 0; j != 9; ++j )
  {
    WaasMedic::SafeFree((WaasMedic *)pwzName[j], v5);
    WaasMedic::SafeFree((WaasMedic *)pwzValue[j], v26);
  }
  v27 = VariantClear(&pvarg);
  if ( v27 < 0 )
    _com_issue_error(v27);
  return v6;
}

```

## disassembly

```asm
0x18002c844  push    rbp
0x18002c846  push    rbx
0x18002c847  push    rsi
0x18002c848  push    rdi
0x18002c849  push    r12
0x18002c84b  push    r13
0x18002c84d  push    r14
0x18002c84f  push    r15
0x18002c851  lea     rbp, [rsp-58h]
0x18002c856  sub     rsp, 158h
0x18002c85d  mov     rax, cs:__security_cookie
0x18002c864  xor     rax, rsp
0x18002c867  mov     [rbp+90h+var_50], rax
0x18002c86b  mov     r12, r9
0x18002c86e  xor     r13d, r13d
0x18002c871  mov     qword ptr [rbp+90h+pSubmitResult], r13
0x18002c875  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18002c87a  call    cs:__imp_VariantInit
0x18002c880  nop
0x18002c881  mov     [rsp+190h+var_150], r13b
0x18002c886  lea     ebx, [r13+48h]
0x18002c88a  mov     r8d, ebx; Size
0x18002c88d  xor     edx, edx; Val
0x18002c88f  lea     rcx, [rsp+190h+pwzName]; void *
0x18002c894  call    memset_0
0x18002c899  mov     r8d, ebx; Size
0x18002c89c  xor     edx, edx; Val
0x18002c89e  lea     rcx, [rbp+90h+pwzValue]; void *
0x18002c8a2  call    memset_0
0x18002c8a7  lea     rax, aWindirLogsWind; "%WINDIR%\\Logs\\WindowsUpdate"
0x18002c8ae  mov     qword ptr [rbp+90h+psz], rax
0x18002c8b2  lea     rax, aProgramdataUso; "%PROGRAMDATA%\\USOShared\\Logs"
0x18002c8b9  mov     [rbp+90h+var_78], rax
0x18002c8bd  lea     rax, Src; "%WINDIR%\\Logs\\waasmedic"
0x18002c8c4  mov     [rbp+90h+var_70], rax
0x18002c8c8  test    r12, r12
0x18002c8cb  jnz     short loc_18002C8D7
0x18002c8cd  mov     ebx, 80004003h
0x18002c8d2  jmp     loc_18002CB62
0x18002c8d7  call    ?getInstance@CMedicEtwConsumer@@SAAEAV1@XZ; CMedicEtwConsumer::getInstance(void)
0x18002c8dc  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18002c8e0  jz      short loc_18002C8FC
0x18002c8e2  mov     r9d, 3; ControlCode
0x18002c8e8  mov     r8, [rax+8]; Properties
0x18002c8ec  lea     rdx, InstanceName; "ECCB175F-1EB2-43DA-BFB5-A8D58A40A4D7"
0x18002c8f3  mov     rcx, [rax]; TraceHandle
0x18002c8f6  call    cs:__imp_ControlTraceW
0x18002c8fc  lea     r8, [rsp+190h+var_150]; bool *
0x18002c901  mov     rdx, r12; struct WaasMedic::IStateProvider *
0x18002c904  call    ?NeedToSkipWERReport@CWERReporter@WaasMedic@@SAJPEBGPEAVIStateProvider@2@PEA_N@Z; WaasMedic::CWERReporter::NeedToSkipWERReport(ushort const *,WaasMedic::IStateProvider *,bool *)
0x18002c909  mov     ebx, eax
0x18002c90b  test    eax, eax
0x18002c90d  jns     short loc_18002C928
0x18002c90f  mov     r8d, eax
0x18002c912  lea     rdx, aFailedToCallCw_0; "Failed to call CWERReporter::NeedToSkip"...
0x18002c919  mov     ecx, 2; unsigned __int8
0x18002c91e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c923  jmp     loc_18002CB62
0x18002c928  cmp     [rsp+190h+var_150], r13b
0x18002c92d  jz      short loc_18002C94C
0x18002c92f  lea     r8, aEngine; "Engine"
0x18002c936  lea     rdx, aSkippingCremed; "Skipping CRemediationPluginBase::Report"...
0x18002c93d  mov     ecx, 4; unsigned __int8
0x18002c942  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c947  jmp     loc_18002CB62
0x18002c94c  lea     rcx, [rbp+90h+pSubmitResult]; struct WaasMedic::CWERReporter **
0x18002c950  call    ?CreateInstance@CWERReporter@WaasMedic@@SAJPEAPEAV12@@Z; WaasMedic::CWERReporter::CreateInstance(WaasMedic::CWERReporter * *)
0x18002c955  mov     ebx, eax
0x18002c957  mov     rdi, qword ptr [rbp+90h+pSubmitResult]
0x18002c95b  test    eax, eax
0x18002c95d  jns     short loc_18002C978
0x18002c95f  lea     rdx, aFailedToCreate_5; "Failed to create instance for WER repor"...
0x18002c966  mov     r8d, eax
0x18002c969  mov     ecx, 2; unsigned __int8
0x18002c96e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c973  jmp     loc_18002CB48
0x18002c978  lea     rax, [rbp+90h+pwzValue]
0x18002c97c  mov     [rsp+190h+var_168], rax; unsigned __int16 **
0x18002c981  lea     rax, [rsp+190h+pwzName]
0x18002c986  mov     [rsp+190h+var_170], rax; unsigned __int16 **
0x18002c98b  call    ?GetDefaultWERReportParamsWithScenario@CWERReporter@WaasMedic@@QEAAJPEBG0JQEAPEAG1K@Z; WaasMedic::CWERReporter::GetDefaultWERReportParamsWithScenario(ushort const *,ushort const *,long,ushort * * const,ushort * * const,ulong)
0x18002c990  mov     ebx, eax
0x18002c992  test    eax, eax
0x18002c994  jns     short loc_18002C99F
0x18002c996  lea     rdx, aFailedToInitia; "Failed to initialize the WER reporter w"...
0x18002c99d  jmp     short loc_18002C966
0x18002c99f  mov     esi, r13d
0x18002c9a2  mov     eax, esi
0x18002c9a4  mov     r14, [rsp+rax*8+190h+pwzName]
0x18002c9a9  test    r14, r14
0x18002c9ac  jz      short loc_18002C9D8
0x18002c9ae  cmp     [r14], r13w
0x18002c9b2  jz      short loc_18002C9D8
0x18002c9b4  mov     r15, [rbp+rax*8+90h+pwzValue]
0x18002c9b9  mov     r9, r15; pwzValue
0x18002c9bc  mov     r8, r14; pwzName
0x18002c9bf  mov     edx, esi; dwparamID
0x18002c9c1  mov     rcx, [rdi+30h]; hReportHandle
0x18002c9c5  call    cs:__imp_WerReportSetParameter
0x18002c9cb  mov     ebx, eax
0x18002c9cd  test    eax, eax
0x18002c9cf  js      short loc_18002C9F6
0x18002c9d1  inc     esi
0x18002c9d3  cmp     esi, 9
0x18002c9d6  jb      short loc_18002C9A2
0x18002c9d8  lea     rdx, [rbp+90h+psz]; unsigned __int16 **
0x18002c9dc  mov     rcx, rdi; this
0x18002c9df  call    ?AddDirectoriesToWERReport@CWERReporter@WaasMedic@@QEAAJQEAPEAGK@Z; WaasMedic::CWERReporter::AddDirectoriesToWERReport(ushort * * const,ulong)
0x18002c9e4  mov     ebx, eax
0x18002c9e6  test    eax, eax
0x18002c9e8  jns     short loc_18002CA25
0x18002c9ea  lea     rdx, aFailedToAddDir; "Failed to add directories to the WER re"...
0x18002c9f1  jmp     loc_18002C966
0x18002c9f6  mov     dword ptr [rsp+190h+var_168], ebx
0x18002c9fa  mov     [rsp+190h+var_170], r15
0x18002c9ff  mov     r9, r14
0x18002ca02  mov     r8d, esi
0x18002ca05  lea     rdx, aFailedToSetUPa; "Failed to set %u parameter %s with valu"...
0x18002ca0c  mov     ecx, 2; unsigned __int8
0x18002ca11  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002ca16  mov     r8d, ebx
0x18002ca19  lea     rdx, aFailedToExecut_0; "Failed to execute WER reporter with err"...
0x18002ca20  jmp     loc_18002C969
0x18002ca25  mov     [rbp+90h+pSubmitResult], 1
0x18002ca2c  lea     r9, [rbp+90h+pSubmitResult]; pSubmitResult
0x18002ca30  mov     esi, 4
0x18002ca35  mov     r8d, esi; dwFlags
0x18002ca38  lea     edx, [rsi-3]; consent
0x18002ca3b  mov     rcx, [rdi+30h]; hReportHandle
0x18002ca3f  call    cs:__imp_WerReportSubmit
0x18002ca45  mov     ebx, eax
0x18002ca47  test    eax, eax
0x18002ca49  jns     short loc_18002CA61
0x18002ca4b  mov     r9d, eax
0x18002ca4e  mov     r8d, [rbp+90h+pSubmitResult]
0x18002ca52  lea     rdx, aCwerreporterSu; "CWERReporter::SubmitWERReport - WER rep"...
0x18002ca59  lea     ecx, [rsi-1]; unsigned __int8
0x18002ca5c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002ca61  mov     r8d, ebx
0x18002ca64  lea     rdx, aCwerreporterFi; "CWERReporter finished handling the even"...
0x18002ca6b  mov     ecx, esi; unsigned __int8
0x18002ca6d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002ca72  test    ebx, ebx
0x18002ca74  jns     short loc_18002CA85
0x18002ca76  mov     r8d, ebx
0x18002ca79  lea     rdx, aFailedToSubmit; "Failed to submit WER report! hr = 0x%08"...
0x18002ca80  jmp     loc_18002C969
0x18002ca85  mov     eax, 8
0x18002ca8a  mov     word ptr [rsp+190h+pvarg], ax
0x18002ca8f  xorps   xmm0, xmm0
0x18002ca92  movups  xmmword ptr [rbp+90h+pSubmitResult], xmm0
0x18002ca96  lea     rcx, [rbp+90h+pSubmitResult]; lpSystemTime
0x18002ca9a  call    cs:__imp_GetSystemTime
0x18002caa0  lea     r8, [rbp+90h+pSubmitResult]; struct _SYSTEMTIME *
0x18002caa4  lea     rcx, [rbp+90h+psz]; unsigned __int16 *
0x18002caa8  call    ?SystemTimeToString@TimeHelper@WaasMedic@@SAJPEAG_KAEBU_SYSTEMTIME@@@Z; WaasMedic::TimeHelper::SystemTimeToString(ushort *,unsigned __int64,_SYSTEMTIME const &)
0x18002caad  test    eax, eax
0x18002caaf  jns     short loc_18002CAB8
0x18002cab1  mov     qword ptr [rsp+190h+pvarg+8], r13
0x18002cab6  jmp     short loc_18002CACC
0x18002cab8  lea     rcx, [rbp+90h+psz]; psz
0x18002cabc  call    cs:__imp_SysAllocString
0x18002cac2  mov     qword ptr [rsp+190h+pvarg+8], rax
0x18002cac7  test    rax, rax
0x18002caca  jnz     short loc_18002CAE0
0x18002cacc  mov     ebx, 8007000Eh
0x18002cad1  mov     r8d, ebx
0x18002cad4  lea     rdx, aFailedToAlloca_28; "Failed to allocate memory for saving La"...
0x18002cadb  jmp     loc_18002C969
0x18002cae0  mov     rax, [r12]
0x18002cae4  mov     rbx, [rax+18h]
0x18002cae8  lea     r14, aEngine; "Engine"
0x18002caef  mov     rdx, r14
0x18002caf2  mov     rcx, r14
0x18002caf5  call    cs:__imp__o__wcsicmp
0x18002cafb  neg     eax
0x18002cafd  sbb     rdx, rdx
0x18002cb00  and     rdx, r14
0x18002cb03  lea     r9, [rsp+190h+pvarg]
0x18002cb08  lea     r8, aWerreportingla; "WerReportingLastRunTime"
0x18002cb0f  mov     rcx, r12
0x18002cb12  mov     rax, rbx
0x18002cb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb1a  mov     ebx, eax
0x18002cb1c  test    eax, eax
0x18002cb1e  jns     short loc_18002CB2C
0x18002cb20  lea     rdx, aFailedToPersis_1; "Failed to persist the last WER reportin"...
0x18002cb27  jmp     loc_18002C966
0x18002cb2c  mov     dword ptr [rsp+190h+var_170], eax
0x18002cb30  mov     r9, r14
0x18002cb33  lea     r8, aAllpluginsinef; "AllPluginsIneffective"
0x18002cb3a  lea     rdx, aWerReportSentS; "WER report sent successfully for scenar"...
0x18002cb41  mov     ecx, esi; unsigned __int8
0x18002cb43  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002cb48  test    rdi, rdi
0x18002cb4b  jz      short loc_18002CB62
0x18002cb4d  mov     rcx, rdi; this
0x18002cb50  call    ??1CWERReporter@WaasMedic@@UEAA@XZ; WaasMedic::CWERReporter::~CWERReporter(void)
0x18002cb55  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18002cb5a  mov     rcx, rdi; void *
0x18002cb5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cb62  mov     rdi, r13
0x18002cb65  mov     rcx, [rsp+rdi*8+190h+pwzName]; this
0x18002cb6a  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18002cb6f  mov     rcx, [rbp+rdi*8+90h+pwzValue]; this
0x18002cb74  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18002cb79  inc     rdi
0x18002cb7c  cmp     rdi, 9
0x18002cb80  jnz     short loc_18002CB65
0x18002cb82  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18002cb87  call    cs:__imp_VariantClear
0x18002cb8d  test    eax, eax
0x18002cb8f  js      short loc_18002CBB3
0x18002cb91  mov     eax, ebx
0x18002cb93  mov     rcx, [rbp+90h+var_50]
0x18002cb97  xor     rcx, rsp; StackCookie
0x18002cb9a  call    __security_check_cookie
0x18002cb9f  add     rsp, 158h
0x18002cba6  pop     r15
0x18002cba8  pop     r14
0x18002cbaa  pop     r13
0x18002cbac  pop     r12
0x18002cbae  pop     rdi
0x18002cbaf  pop     rsi
0x18002cbb0  pop     rbx
0x18002cbb1  pop     rbp
0x18002cbb2  retn
0x18002cbb3  mov     ecx, eax; int
0x18002cbb5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```

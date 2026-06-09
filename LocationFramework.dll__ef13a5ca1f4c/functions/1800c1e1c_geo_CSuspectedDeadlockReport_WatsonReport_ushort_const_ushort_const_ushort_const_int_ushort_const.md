# geo::CSuspectedDeadlockReport::WatsonReport(ushort const *,ushort const *,ushort const *,int,ushort const *)

- ea: `0x1800c1e1c`
- end: `0x1800c211a`
- name: `?WatsonReport@CSuspectedDeadlockReport@geo@@SAJPEBG00H0@Z`
- size: `766`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c1aa0`

## callees

- `0x18009c310`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800c0b60`
- `0x1800c1e1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800c1ea7`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800c1ea7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c1e78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2062`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c1e78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2062`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c2059`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c2059`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x1800c20cc`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x1800c20cc`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1f01`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1f5b`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1f91`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1fc6`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c2001`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c2038`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1f01`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1f5b`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1f91`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c1fc6`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c2001`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800c2038`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800c2092`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800c2092`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1800c1ecc`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1800c1ecc`

## string_xrefs

- `0x1800c1ee1`: `WerReportCreate(L"WindowsNonFatalSuspectedDeadlock", WerReportNonCritical, &WerReportInfo, hReport.addressof())`
- `0x1800c1f2b`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\SuspectedDeadlockReport.h`
- `0x1800c1fb7`: `InternalComponentId`
- `0x1800c1fdb`: `WerReportSetParameter(hReport.get(), WER_P3, L"InternalComponentId", szInternalComponentId)`
- `0x1800c20a7`: `WerReportAddDump(hReport.get(), GetCurrentProcess(), GetCurrentThread(), WerDumpTypeMiniDump, nullptr, nullptr, 0)`
- `0x1800c20e1`: `WerReportSubmit( hReport.get(), WerConsentNotAsked, WER_SUBMIT_QUEUE | WER_SUBMIT_BYPASS_DATA_THROTTLING | WER_SUBMIT_OUTOFPROCESS, &SubmitResult)`

## pseudocode

```c
__int64 __fastcall geo::CSuspectedDeadlockReport::WatsonReport(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int16 *a5)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const char *v11; // rax
  HRESULT v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HANDLE CurrentThread; // rbx
  HANDLE CurrentProcess; // rax
  HRESULT v20; // eax
  HRESULT v21; // eax
  wil::details *pDumpCustomOptions; // [rsp+28h] [rbp-D8h]
  DWORD dwFlags; // [rsp+30h] [rbp-D0h]
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT phReportHandle; // [rsp+8E0h] [rbp+7E0h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+8E8h] [rbp+7E8h] BYREF
  WCHAR pwzValue[8]; // [rsp+8F0h] [rbp+7F0h] BYREF
  __int128 v29; // [rsp+900h] [rbp+800h]
  wil::details::in1diag5 *retaddr; // [rsp+948h] [rbp+848h]

  phReportHandle = 0;
  memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
  pReportInformation.dwSize = 2208;
  pReportInformation.hProcess = GetCurrentProcess();
  *(_OWORD *)pwzValue = 0;
  v29 = 0;
  _o__itow_s(a4, pwzValue, 16);
  pSubmitResult = 0;
  v8 = WerReportCreate(L"WindowsNonFatalSuspectedDeadlock", WerReportNonCritical, &pReportInformation, &phReportHandle);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v12 = WerReportSetParameter(phReportHandle, 0, L"Version", L"2");
    v9 = v12;
    if ( v12 >= 0 )
    {
      v13 = WerReportSetParameter(phReportHandle, 1u, L"AppName", L"Unknown");
      v9 = v13;
      if ( v13 >= 0 )
      {
        v14 = WerReportSetParameter(phReportHandle, 2u, L"FaultingModule", a2);
        v9 = v14;
        if ( v14 >= 0 )
        {
          v15 = WerReportSetParameter(phReportHandle, 3u, L"InternalComponentId", a3);
          v9 = v15;
          if ( v15 >= 0 )
          {
            v16 = WerReportSetParameter(phReportHandle, 4u, L"DeadlockTimeoutMs", pwzValue);
            v9 = v16;
            if ( v16 >= 0 )
            {
              v17 = WerReportSetParameter(phReportHandle, 5u, L"OriginatingCodeHint", a5);
              v9 = v17;
              if ( v17 >= 0 )
              {
                CurrentThread = GetCurrentThread();
                CurrentProcess = GetCurrentProcess();
                v20 = WerReportAddDump(phReportHandle, CurrentProcess, CurrentThread, WerDumpTypeMiniDump, 0, 0, 0);
                v9 = v20;
                if ( v20 >= 0 )
                {
                  v21 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x824u, &pSubmitResult);
                  v9 = v21;
                  if ( v21 >= 0 )
                  {
                    v9 = 0;
                    goto LABEL_21;
                  }
                  LODWORD(pDumpCustomOptions) = v21;
                  v10 = 51;
                  v11 = "WerReportSubmit( hReport.get(), WerConsentNotAsked, WER_SUBMIT_QUEUE | WER_SUBMIT_BYPASS_DATA_TH"
                        "ROTTLING | WER_SUBMIT_OUTOFPROCESS, &SubmitResult)";
                }
                else
                {
                  LODWORD(pDumpCustomOptions) = v20;
                  v10 = 48;
                  v11 = "WerReportAddDump(hReport.get(), GetCurrentProcess(), GetCurrentThread(), WerDumpTypeMiniDump, nu"
                        "llptr, nullptr, 0)";
                }
              }
              else
              {
                LODWORD(pDumpCustomOptions) = v17;
                v10 = 44;
                v11 = "WerReportSetParameter(hReport.get(), WER_P5, L\"OriginatingCodeHint\", szOriginatingCodeHint)";
              }
            }
            else
            {
              LODWORD(pDumpCustomOptions) = v16;
              v10 = 43;
              v11 = "WerReportSetParameter(hReport.get(), WER_P4, L\"DeadlockTimeoutMs\", szDeadlockTimeoutMs)";
            }
          }
          else
          {
            LODWORD(pDumpCustomOptions) = v15;
            v10 = 42;
            v11 = "WerReportSetParameter(hReport.get(), WER_P3, L\"InternalComponentId\", szInternalComponentId)";
          }
        }
        else
        {
          LODWORD(pDumpCustomOptions) = v14;
          v10 = 41;
          v11 = "WerReportSetParameter(hReport.get(), WER_P2, L\"FaultingModule\", szFaultingModule)";
        }
      }
      else
      {
        LODWORD(pDumpCustomOptions) = v13;
        v10 = 40;
        v11 = "WerReportSetParameter(hReport.get(), WER_P1, L\"AppName\", szAppName)";
      }
    }
    else
    {
      LODWORD(pDumpCustomOptions) = v12;
      v10 = 38;
      v11 = "WerReportSetParameter(hReport.get(), WER_P0, L\"Version\", L\"2\")";
    }
  }
  else
  {
    LODWORD(pDumpCustomOptions) = v8;
    v10 = 35;
    v11 = "WerReportCreate(L\"WindowsNonFatalSuspectedDeadlock\", WerReportNonCritical, &WerReportInfo, hReport.addressof())";
  }
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\SuspectedDeadlockReport.h",
    "geo::CSuspectedDeadlockReport::WatsonReport",
    v11,
    pDumpCustomOptions,
    dwFlags);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportHandle);
  return v9;
}

```

## disassembly

```asm
0x1800c1e1c  push    rbp
0x1800c1e1e  push    rbx
0x1800c1e1f  push    rsi
0x1800c1e20  push    rdi
0x1800c1e21  push    r14
0x1800c1e23  lea     rbp, [rsp-820h]
0x1800c1e2b  sub     rsp, 920h
0x1800c1e32  mov     rax, cs:__security_cookie
0x1800c1e39  xor     rax, rsp
0x1800c1e3c  mov     [rbp+840h+var_30], rax
0x1800c1e43  mov     r14, [rbp+840h+arg_20]
0x1800c1e4a  lea     rcx, [rsp+940h+pReportInformation+4]; void *
0x1800c1e4f  mov     rsi, r8
0x1800c1e52  mov     [rbp+840h+phReportHandle], 0
0x1800c1e5d  mov     rdi, rdx
0x1800c1e60  mov     r8d, 89Ch; Size
0x1800c1e66  xor     edx, edx; Val
0x1800c1e68  mov     ebx, r9d
0x1800c1e6b  call    memset_0
0x1800c1e70  mov     [rsp+940h+pReportInformation.dwSize], 8A0h
0x1800c1e78  call    cs:__imp_GetCurrentProcess
0x1800c1e7e  xorps   xmm0, xmm0
0x1800c1e81  lea     rdx, [rbp+840h+pwzValue]
0x1800c1e88  mov     r9d, 0Ah
0x1800c1e8e  mov     [rsp+940h+pReportInformation.hProcess], rax
0x1800c1e93  mov     ecx, ebx
0x1800c1e95  movups  xmmword ptr [rbp+840h+pwzValue], xmm0
0x1800c1e9c  lea     r8d, [r9+6]
0x1800c1ea0  movups  [rbp+840h+var_40], xmm0
0x1800c1ea7  call    cs:__imp__o__itow_s
0x1800c1ead  lea     r9, [rbp+840h+phReportHandle]; phReportHandle
0x1800c1eb4  mov     [rbp+840h+pSubmitResult], 0
0x1800c1ebe  lea     r8, [rsp+940h+pReportInformation]; pReportInformation
0x1800c1ec3  xor     edx, edx; repType
0x1800c1ec5  lea     rcx, pwzEventType; "WindowsNonFatalSuspectedDeadlock"
0x1800c1ecc  call    cs:__imp_WerReportCreate
0x1800c1ed2  mov     ebx, eax
0x1800c1ed4  test    eax, eax
0x1800c1ed6  jns     short loc_1800C1EEA
0x1800c1ed8  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c1edc  mov     edx, 23h ; '#'
0x1800c1ee1  lea     rax, aWerreportcreat_0; "WerReportCreate(L\"WindowsNonFatalSuspe"...
0x1800c1ee8  jmp     short loc_1800C1F1D
0x1800c1eea  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c1ef1  lea     r9, pwzValue; "2"
0x1800c1ef8  lea     r8, pwzName; "Version"
0x1800c1eff  xor     edx, edx; dwparamID
0x1800c1f01  call    cs:__imp_WerReportSetParameter
0x1800c1f07  mov     ebx, eax
0x1800c1f09  test    eax, eax
0x1800c1f0b  jns     short loc_1800C1F41
0x1800c1f0d  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax; wil::details *
0x1800c1f11  mov     edx, 26h ; '&'; void *
0x1800c1f16  lea     rax, aWerreportsetpa_0; "WerReportSetParameter(hReport.get(), WE"...
0x1800c1f1d  mov     rcx, [rbp+848h]; this
0x1800c1f24  lea     r9, aGeoCsuspectedd; "geo::CSuspectedDeadlockReport::WatsonRe"...
0x1800c1f2b  lea     r8, aOnecoreuapDriv_39; "onecoreuap\\drivers\\MobilePC\\Location"...
0x1800c1f32  mov     [rsp+940h+pExceptionParam], rax; char *
0x1800c1f37  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800c1f3c  jmp     loc_1800C20EF
0x1800c1f41  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c1f48  lea     r9, aUnknown; "Unknown"
0x1800c1f4f  lea     r8, aAppname; "AppName"
0x1800c1f56  mov     edx, 1; dwparamID
0x1800c1f5b  call    cs:__imp_WerReportSetParameter
0x1800c1f61  mov     ebx, eax
0x1800c1f63  test    eax, eax
0x1800c1f65  jns     short loc_1800C1F79
0x1800c1f67  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c1f6b  mov     edx, 28h ; '('
0x1800c1f70  lea     rax, aWerreportsetpa_1; "WerReportSetParameter(hReport.get(), WE"...
0x1800c1f77  jmp     short loc_1800C1F1D
0x1800c1f79  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c1f80  lea     r8, aFaultingmodule; "FaultingModule"
0x1800c1f87  mov     r9, rdi; pwzValue
0x1800c1f8a  mov     edi, 2
0x1800c1f8f  mov     edx, edi; dwparamID
0x1800c1f91  call    cs:__imp_WerReportSetParameter
0x1800c1f97  mov     ebx, eax
0x1800c1f99  test    eax, eax
0x1800c1f9b  jns     short loc_1800C1FB0
0x1800c1f9d  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c1fa1  lea     edx, [rdi+27h]
0x1800c1fa4  lea     rax, aWerreportsetpa_2; "WerReportSetParameter(hReport.get(), WE"...
0x1800c1fab  jmp     loc_1800C1F1D
0x1800c1fb0  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c1fb7  lea     r8, aInternalcompon; "InternalComponentId"
0x1800c1fbe  mov     r9, rsi; pwzValue
0x1800c1fc1  mov     edx, 3; dwparamID
0x1800c1fc6  call    cs:__imp_WerReportSetParameter
0x1800c1fcc  mov     ebx, eax
0x1800c1fce  test    eax, eax
0x1800c1fd0  jns     short loc_1800C1FE7
0x1800c1fd2  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c1fd6  mov     edx, 2Ah ; '*'
0x1800c1fdb  lea     rax, aWerreportsetpa_3; "WerReportSetParameter(hReport.get(), WE"...
0x1800c1fe2  jmp     loc_1800C1F1D
0x1800c1fe7  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c1fee  lea     r9, [rbp+840h+pwzValue]; pwzValue
0x1800c1ff5  lea     r8, aDeadlocktimeou; "DeadlockTimeoutMs"
0x1800c1ffc  mov     edx, 4; dwparamID
0x1800c2001  call    cs:__imp_WerReportSetParameter
0x1800c2007  mov     ebx, eax
0x1800c2009  test    eax, eax
0x1800c200b  jns     short loc_1800C2022
0x1800c200d  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c2011  mov     edx, 2Bh ; '+'
0x1800c2016  lea     rax, aWerreportsetpa_5; "WerReportSetParameter(hReport.get(), WE"...
0x1800c201d  jmp     loc_1800C1F1D
0x1800c2022  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c2029  lea     r8, aOriginatingcod; "OriginatingCodeHint"
0x1800c2030  mov     r9, r14; pwzValue
0x1800c2033  mov     edx, 5; dwparamID
0x1800c2038  call    cs:__imp_WerReportSetParameter
0x1800c203e  mov     ebx, eax
0x1800c2040  test    eax, eax
0x1800c2042  jns     short loc_1800C2059
0x1800c2044  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c2048  mov     edx, 2Ch ; ','
0x1800c204d  lea     rax, aWerreportsetpa_4; "WerReportSetParameter(hReport.get(), WE"...
0x1800c2054  jmp     loc_1800C1F1D
0x1800c2059  call    cs:__imp_GetCurrentThread
0x1800c205f  mov     rbx, rax
0x1800c2062  call    cs:__imp_GetCurrentProcess
0x1800c2068  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c206f  mov     r9d, edi; dumpType
0x1800c2072  mov     [rsp+940h+dwFlags], 0; dwFlags
0x1800c207a  mov     rdx, rax; hProcess
0x1800c207d  mov     [rsp+940h+pDumpCustomOptions], 0; pDumpCustomOptions
0x1800c2086  mov     r8, rbx; hThread
0x1800c2089  mov     [rsp+940h+pExceptionParam], 0; pExceptionParam
0x1800c2092  call    cs:__imp_WerReportAddDump
0x1800c2098  mov     ebx, eax
0x1800c209a  test    eax, eax
0x1800c209c  jns     short loc_1800C20B3
0x1800c209e  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c20a2  mov     edx, 30h ; '0'
0x1800c20a7  lea     rax, aWerreportadddu_0; "WerReportAddDump(hReport.get(), GetCurr"...
0x1800c20ae  jmp     loc_1800C1F1D
0x1800c20b3  mov     rcx, [rbp+840h+phReportHandle]; hReportHandle
0x1800c20ba  lea     r9, [rbp+840h+pSubmitResult]; pSubmitResult
0x1800c20c1  mov     edx, 1; consent
0x1800c20c6  mov     r8d, 824h; dwFlags
0x1800c20cc  call    cs:__imp_WerReportSubmit
0x1800c20d2  mov     ebx, eax
0x1800c20d4  test    eax, eax
0x1800c20d6  jns     short loc_1800C20ED
0x1800c20d8  mov     dword ptr [rsp+940h+pDumpCustomOptions], eax
0x1800c20dc  mov     edx, 33h ; '3'
0x1800c20e1  lea     rax, aWerreportsubmi_0; "WerReportSubmit( hReport.get(), WerCons"...
0x1800c20e8  jmp     loc_1800C1F1D
0x1800c20ed  xor     ebx, ebx
0x1800c20ef  lea     rcx, [rbp+840h+phReportHandle]
0x1800c20f6  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800c20fb  mov     eax, ebx
0x1800c20fd  mov     rcx, [rbp+840h+var_30]
0x1800c2104  xor     rcx, rsp; StackCookie
0x1800c2107  call    __security_check_cookie
0x1800c210c  add     rsp, 920h
0x1800c2113  pop     r14
0x1800c2115  pop     rdi
0x1800c2116  pop     rsi
0x1800c2117  pop     rbx
0x1800c2118  pop     rbp
0x1800c2119  retn
```

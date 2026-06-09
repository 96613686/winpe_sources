# CWatsonHelper::Run(void)

- ea: `0x18008bb50`
- end: `0x18008c3d9`
- name: `?Run@CWatsonHelper@@EEAAXXZ`
- size: `2185`
- prototype: `void __fastcall(CWatsonHelper *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x18000a0e8`
- `0x18000afc8`
- `0x18000c4c4`
- `0x18000cbc8`
- `0x18000fdc0`
- `0x180010198`
- `0x180012430`
- `0x1800124dc`
- `0x18001270c`
- `0x180013eb0`
- `0x180020254`
- `0x180077acc`
- `0x18008bb50`
- `0x18009b208`
- `0x18009b860`
- `0x1801dfc4c`
- `0x1801e4b84`
- `0x1801efdc0`
- `0x1801f8f3c`
- `0x1802246e8`
- `0x18022477c`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18008c21f`
- `ntdll!RtlRaiseStatus` at `0x18008c260`
- `ntdll!RtlRaiseStatus` at `0x18008c2f5`
- `ntdll!RtlRaiseStatus` at `0x18008c21f`
- `ntdll!RtlRaiseStatus` at `0x18008c260`
- `ntdll!RtlRaiseStatus` at `0x18008c2f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18008c209`
- `ntdll!RtlLeaveCriticalSection` at `0x18008c24a`
- `ntdll!RtlLeaveCriticalSection` at `0x18008c2e3`
- `ntdll!RtlLeaveCriticalSection` at `0x18008c209`
- `ntdll!RtlLeaveCriticalSection` at `0x18008c24a`
- `ntdll!RtlLeaveCriticalSection` at `0x18008c2e3`
- `ntdll!RtlEnterCriticalSection` at `0x18008c199`
- `ntdll!RtlEnterCriticalSection` at `0x18008c199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c16c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c16c`
- `wer!WerReportSubmit` at `0x18008c0ff`
- `wer!WerReportSubmit` at `0x18008c0ff`
- `wer!WerReportCloseHandle` at `0x18008bd64`
- `wer!WerReportCloseHandle` at `0x18008be26`
- `wer!WerReportCloseHandle` at `0x18008c378`
- `wer!WerReportCloseHandle` at `0x18008c3a2`
- `wer!WerReportCloseHandle` at `0x18008bd64`
- `wer!WerReportCloseHandle` at `0x18008be26`
- `wer!WerReportCloseHandle` at `0x18008c378`
- `wer!WerReportCloseHandle` at `0x18008c3a2`
- `wer!WerReportAddFile` at `0x18008c099`
- `wer!WerReportAddFile` at `0x18008c099`
- `wer!WerReportSetParameter` at `0x18008bf15`
- `wer!WerReportSetParameter` at `0x18008bf15`
- `wer!WerReportSetUIOption` at `0x18008bd8c`
- `wer!WerReportSetUIOption` at `0x18008bd8c`
- `wer!WerReportCreate` at `0x18008bcc5`
- `wer!WerReportCreate` at `0x18008bcc5`

## string_xrefs

- `0x18008bcbe`: `UpdateAgentDiag`
- `0x18008c2a3`: `UpdateAgentDiag`
- `0x18008bcef`: `WatsonHelper: Could not create helper`
- `0x18008bd45`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\WatsonHelperImpl.h`
- `0x18008be07`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\WatsonHelperImpl.h`
- `0x18008bd76`: `Microsoft Installation encountered a problem and needs to close. We are sorry for the inconvenience.`
- `0x18008c2b7`: `WatsonHelper: Consent value [HKCU\{}!{}] could NOT be deleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWatsonHelper::Run(CWatsonHelper *this)
{
  const char *v2; // r9
  int v3; // edx
  int v4; // ecx
  DWORD LastError; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // edx
  int v9; // r9d
  HRESULT v10; // eax
  unsigned int v11; // r14d
  __int64 v12; // rdx
  HRESULT v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  DWORD i; // eax
  __int64 v19; // r9
  const wchar_t *v20; // r9
  HRESULT v21; // eax
  __int64 v22; // rdx
  _QWORD *v23; // r14
  _QWORD *v24; // rbx
  PCWSTR v25; // rdi
  __int64 v26; // rcx
  _QWORD *v27; // rax
  PCWSTR j; // rbx
  const WCHAR *v29; // rdx
  HRESULT v30; // eax
  HRESULT v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rdx
  void *v36; // rdx
  signed int v37; // ebx
  unsigned int v38; // r8d
  __int64 v39; // rdi
  int v40; // eax
  bool v41; // r15
  unsigned int v42; // eax
  __int64 v43; // rdx
  int v44; // eax
  int v45; // eax
  int v46; // eax
  unsigned int v47; // eax
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v48; // [rsp+20h] [rbp-968h]
  void *p_dwparamID; // [rsp+28h] [rbp-960h]
  unsigned int v50[2]; // [rsp+30h] [rbp-958h] BYREF
  __int64 v51; // [rsp+38h] [rbp-950h]
  unsigned __int64 v52; // [rsp+40h] [rbp-948h] BYREF
  const char *v53; // [rsp+48h] [rbp-940h]
  __int64 v54; // [rsp+50h] [rbp-938h]
  const char *v55; // [rsp+58h] [rbp-930h]
  __int64 (__fastcall *v56)(); // [rsp+60h] [rbp-928h]
  const WCHAR *v57; // [rsp+68h] [rbp-920h]
  __int64 v58; // [rsp+70h] [rbp-918h]
  DWORD dwparamID; // [rsp+78h] [rbp-910h] BYREF
  PCWSTR pwzValue[2]; // [rsp+80h] [rbp-908h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+90h] [rbp-8F8h] BYREF
  DWORD v62; // [rsp+930h] [rbp-58h] BYREF
  HREPORT phReportHandle; // [rsp+938h] [rbp-50h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+940h] [rbp-48h] BYREF
  PCWSTR pwzPath[2]; // [rsp+948h] [rbp-40h] BYREF
  const WCHAR *v66; // [rsp+958h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+988h] [rbp+0h]

  v58 = -2;
  try
  {
    if ( !*((_BYTE *)this + 8) )
    {
      LogAdapter::TraceInfo<>("WatsonHelper: No opt-in");
      return;
    }
    dwparamID = 4;
    if ( !(unsigned int)RegSetDword() )
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        p_dwparamID = &dwparamID;
        LogAdapter::Logger::LogPartial<wchar_t [59],wchar_t [16],int>(v4, v3, v6, v7);
        v62 = LastError;
        pwzValue[0] = (PCWSTR)&v62;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(
          LogAdapter::g_Logger,
          v8,
          2,
          v9,
          (__int64)pwzValue);
      }
    }
    *(_QWORD *)&pReportInformation.dwSize = 2208;
    pReportInformation.hProcess = 0;
    memset_0(pReportInformation.wzConsentKey, 0, sizeof(pReportInformation.wzConsentKey));
    memset_0(pReportInformation.wzFriendlyEventName, 0, sizeof(pReportInformation.wzFriendlyEventName));
    memset_0(pReportInformation.wzApplicationName, 0, sizeof(pReportInformation.wzApplicationName));
    memset_0(pReportInformation.wzApplicationPath, 0, sizeof(pReportInformation.wzApplicationPath));
    memset_0(pReportInformation.wzDescription, 0, sizeof(pReportInformation.wzDescription));
    pReportInformation.hwndParent = 0;
    phReportHandle = 0;
    v10 = WerReportCreate(L"UpdateAgentDiag", WerReportNonCritical, &pReportInformation, &phReportHandle);
    v11 = v10;
    if ( v10 < 0 )
    {
      v62 = v10;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "WatsonHelper: Could not create helper");
        pwzValue[0] = (PCWSTR)&v62;
        v48 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)pwzValue;
        LOBYTE(v12) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v12,
          3,
          ": {}");
      }
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\WatsonHelperImpl.h",
        (const char *)v11,
        (int)v48);
      if ( phReportHandle )
        WerReportCloseHandle(phReportHandle);
      return;
    }
    v13 = WerReportSetUIOption(
            phReportHandle,
            WerUIConsentDlgHeader,
            L"Microsoft Installation encountered a problem and needs to close. We are sorry for the inconvenience.");
    v14 = v13;
    v15 = *(_QWORD *)&LogAdapter::g_Logger;
    if ( v13 < 0 )
    {
      v62 = v13;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "WatsonHelper: Could not set UI option");
        pwzValue[0] = (PCWSTR)&v62;
        v48 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)pwzValue;
        LOBYTE(v16) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v16,
          3,
          ": {}");
      }
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\WatsonHelperImpl.h",
        (const char *)v14,
        (int)v48);
      if ( phReportHandle )
        WerReportCloseHandle(phReportHandle);
      return;
    }
    v17 = 0;
    for ( i = 0; ; i = dwparamID + 1 )
    {
      dwparamID = v17;
      v19 = *((_QWORD *)this + 2);
      if ( i >= (unsigned __int64)((*((_QWORD *)this + 3) - v19) >> 5) )
        break;
      v20 = (const wchar_t *)(32LL * i + v19);
      if ( *((_QWORD *)v20 + 3) > 7u )
        v20 = *(const wchar_t **)v20;
      pwzValue[0] = v20;
      if ( *(_BYTE *)(i + *((_QWORD *)this + 8)) )
      {
        if ( v15 )
        {
          p_dwparamID = pwzValue;
          v48 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)&dwparamID;
          LOBYTE(v17) = 1;
          LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
            v15,
            v17,
            1,
            "WatsonHelper: Parameter [{}] is muted - Ignoring: [{}]");
          v17 = dwparamID;
          v15 = *(_QWORD *)&LogAdapter::g_Logger;
        }
        v20 = L"X";
        pwzValue[0] = L"X";
      }
      if ( v15 )
      {
        p_dwparamID = pwzValue;
        v48 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)&dwparamID;
        LOBYTE(v17) = 1;
        LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
          v15,
          v17,
          1,
          "WatsonHelper: Setting Parameter [{}] to: [{}]");
        LODWORD(v17) = dwparamID;
        v20 = pwzValue[0];
      }
      v21 = WerReportSetParameter(phReportHandle, v17, 0, v20);
      if ( v21 < 0 )
      {
        v62 = v21;
        v15 = *(_QWORD *)&LogAdapter::g_Logger;
        if ( !*(_QWORD *)&LogAdapter::g_Logger )
          goto LABEL_33;
        p_dwparamID = pwzValue;
        LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          2,
          "WatsonHelper: Failed to add parameter [{} = {}]");
        *(_QWORD *)v50 = &v62;
        v48 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)v50;
        LOBYTE(v22) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v22,
          2,
          ": {0}");
      }
      v15 = *(_QWORD *)&LogAdapter::g_Logger;
LABEL_33:
      v17 = dwparamID + 1;
    }
    *(_OWORD *)pwzPath = 0;
    v66 = 0;
    v23 = (_QWORD *)*((_QWORD *)this + 6);
    v24 = (_QWORD *)*((_QWORD *)this + 5);
    v25 = (PCWSTR)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    while ( v24 != v23 )
    {
      v26 = v24[2];
      if ( v24[3] <= 7u )
        v27 = v24;
      else
        v27 = (_QWORD *)*v24;
      *(_QWORD *)v50 = v27;
      v51 = v26;
      if ( (unsigned __int8)FileExists(v50) )
      {
        if ( pwzPath[1] != v66 )
        {
          std::wstring::wstring(pwzPath[1], v24);
          v25 = pwzPath[1] + 16;
          pwzPath[1] += 16;
          goto LABEL_44;
        }
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, pwzPath[1], v24);
      }
      v25 = pwzPath[1];
LABEL_44:
      v24 += 4;
    }
    for ( j = pwzPath[0]; j != v25; j += 16 )
    {
      LogAdapter::TraceAtLevel<std::wstring>(1, "WatsonHelper: Adding file to report [{}]", j);
      if ( *((_QWORD *)j + 3) <= 7u )
        v29 = j;
      else
        v29 = *(const WCHAR **)j;
      v30 = WerReportAddFile(phReportHandle, v29, WerFileTypeOther, 2u);
      if ( v30 < 0 )
        LogAdapter::TraceAtLevelHr<long,std::wstring>(
          2,
          (unsigned int)v30,
          "WatsonHelper: Failed to add file [{}]",
          j,
          v48,
          p_dwparamID);
    }
    pSubmitResult = 0;
    LogAdapter::TraceInfo<>("WatsonHelper:  Uploading Report.");
    *(_QWORD *)v50 = &pSubmitResult;
    v31 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x40u, &pSubmitResult);
    if ( v31 < 0 )
    {
      v62 = v31;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<Windows::WCP::Rtl::FormatHexWrapper<enum _WER_SUBMIT_RESULT>>(
          v33,
          v32,
          v34,
          v50,
          v48,
          p_dwparamID);
        pwzValue[0] = (PCWSTR)&v62;
        v48 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)pwzValue;
        LOBYTE(v35) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v35,
          2,
          ": {0}");
      }
    }
    if ( (unsigned int)RegDelete() )
    {
      std::vector<UUPInstallPlan::UUPProduct>::_Tidy(pwzPath);
      if ( phReportHandle )
        WerReportCloseHandle(phReportHandle);
    }
    else
    {
      v37 = GetLastError();
      v39 = *(_QWORD *)&LogAdapter::g_Logger;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        *(_QWORD *)v50 = *(_QWORD *)&LogAdapter::g_Logger + 4160LL;
        v40 = RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)&LogAdapter::g_Logger + 4160LL));
        v41 = v40 >= 0;
        LOBYTE(v51) = v40 >= 0;
        if ( v40 >= 0 )
        {
          if ( (**(int (__fastcall ***)(__int64))v39)(v39) >= 0 )
          {
            v52 = 0;
            v53 = (const char *)`Windows::Tracing::RtlFormatIntoStream<wchar_t [1025]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
            v54 = (__int64)L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent";
            v55 = 0;
            v56 = `Windows::Tracing::RtlFormatIntoStream<wchar_t [1025]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
            v57 = L"UpdateAgentDiag";
            Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
              *(Windows::WCP::Rtl **)(v39 + 8),
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"WatsonHelper: Consent value [HKCU\\{}!{}] could NOT be deleted",
              (const char *const)2,
              (unsigned __int64)&v52,
              v48);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v39 + 8) + 496LL))(*(_QWORD *)(v39 + 8));
            if ( v41 )
            {
              v46 = RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v39 + 4160));
              if ( v46 < 0 )
                RtlRaiseStatus(v46);
            }
          }
          else if ( v41 )
          {
            v45 = RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v39 + 4160));
            if ( v45 < 0 )
              RtlRaiseStatus(v45);
          }
        }
        else
        {
          v52 = (unsigned __int64)"OneCore\\Private\\Base\\inc\\LogAdapter.h";
          v53 = "LogAdapter::Logger::LogNumObjects";
          v54 = 195;
          v55 = "QueueLock.Acquire()";
          v42 = ConvertNtStatusToHResult(v40);
          RtlReportErrorOrigination(&v52, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v42);
          if ( v41 )
          {
            v44 = RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v39 + 4160));
            if ( v44 < 0 )
              RtlRaiseStatus(v44);
          }
        }
        if ( v37 > 0 )
          v47 = (unsigned __int16)v37 | 0x80070000;
        else
          v47 = v37;
        v62 = v47;
        *(_QWORD *)v50 = &v62;
        v48 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)v50;
        LOBYTE(v43) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v43,
          2,
          ": {0}");
      }
      if ( v37 )
        wil::details::in1diag3::_Log_Win32(retaddr, v36, v38, (const char *)(unsigned int)v37, (unsigned int)v48);
      std::vector<UUPInstallPlan::UUPProduct>::_Tidy(pwzPath);
      if ( phReportHandle )
        WerReportCloseHandle(phReportHandle);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\WatsonHelperImpl.h",
      v2);
  }
}

```

## disassembly

```asm
0x18008bb50  mov     rax, rsp
0x18008bb53  push    rdi
0x18008bb54  push    r14
0x18008bb56  push    r15
0x18008bb58  sub     rsp, 970h
0x18008bb5f  mov     [rsp+988h+var_918], 0FFFFFFFFFFFFFFFEh
0x18008bb68  mov     [rax+10h], rbx
0x18008bb6c  mov     [rax+18h], rsi
0x18008bb70  mov     rax, cs:__security_cookie
0x18008bb77  xor     rax, rsp
0x18008bb7a  mov     [rsp+988h+var_28], rax
0x18008bb82  mov     rdi, rcx
0x18008bb85  cmp     byte ptr [rcx+8], 0
0x18008bb89  jnz     short loc_18008BB9D
0x18008bb8b  lea     rcx, aWatsonhelperNo; "WatsonHelper: No opt-in"
0x18008bb92  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18008bb97  nop
0x18008bb98  jmp     loc_18008C3AF
0x18008bb9d  mov     [rsp+988h+dwparamID], 4
0x18008bba5  call    RegSetDword
0x18008bbaa  test    eax, eax
0x18008bbac  jnz     short loc_18008BC0F
0x18008bbae  call    cs:__imp_GetLastError
0x18008bbb5  nop     dword ptr [rax+rax+00h]
0x18008bbba  mov     ebx, eax
0x18008bbbc  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bbc4  jz      short loc_18008BC0F
0x18008bbc6  lea     rax, [rsp+988h+dwparamID]
0x18008bbcb  mov     [rsp+988h+var_960], rax
0x18008bbd0  call    ??$LogPartial@$$BY0DL@_W$$BY0BA@_WH@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEAY0DL@$$CB_WAEAY0BA@$$CB_WAEBH@Z; LogAdapter::Logger::LogPartial<wchar_t [59],wchar_t [16],int>(LogAdapter::LogLevel,char const * const,wchar_t const (&)[59],wchar_t const (&)[16],int const &)
0x18008bbd5  mov     [rsp+988h+var_58], ebx
0x18008bbdc  lea     rax, [rsp+988h+var_58]
0x18008bbe4  mov     [rsp+988h+pwzValue], rax
0x18008bbec  lea     rax, [rsp+988h+pwzValue]
0x18008bbf4  mov     [rsp+988h+var_968], rax
0x18008bbf9  mov     esi, 2
0x18008bbfe  mov     r8d, esi
0x18008bc01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bc08  call    ??$LogNumObjects@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x18008bc0d  jmp     short loc_18008BC14
0x18008bc0f  mov     esi, 2
0x18008bc14  mov     qword ptr [rsp+988h+pReportInformation.dwSize], 8A0h
0x18008bc20  mov     [rsp+988h+pReportInformation.hProcess], 0
0x18008bc2c  xor     edx, edx; Val
0x18008bc2e  mov     r8d, 80h; Size
0x18008bc34  lea     rcx, [rsp+988h+pReportInformation.wzConsentKey]; void *
0x18008bc3c  call    memset_0
0x18008bc41  mov     ebx, 100h
0x18008bc46  mov     r8d, ebx; Size
0x18008bc49  xor     edx, edx; Val
0x18008bc4b  lea     rcx, [rsp+988h+pReportInformation.wzFriendlyEventName]; void *
0x18008bc53  call    memset_0
0x18008bc58  mov     r8d, ebx; Size
0x18008bc5b  xor     edx, edx; Val
0x18008bc5d  lea     rcx, [rsp+988h+pReportInformation.wzApplicationName]; void *
0x18008bc65  call    memset_0
0x18008bc6a  xor     edx, edx; Val
0x18008bc6c  mov     r8d, 208h; Size
0x18008bc72  lea     rcx, [rsp+988h+pReportInformation.wzApplicationPath]; void *
0x18008bc7a  call    memset_0
0x18008bc7f  xor     edx, edx; Val
0x18008bc81  mov     r8d, 400h; Size
0x18008bc87  lea     rcx, [rsp+988h+pReportInformation.wzDescription]; void *
0x18008bc8f  call    memset_0
0x18008bc94  mov     [rsp+988h+pReportInformation.hwndParent], 0
0x18008bca0  mov     [rsp+988h+phReportHandle], 0
0x18008bcac  lea     r9, [rsp+988h+phReportHandle]; phReportHandle
0x18008bcb4  lea     r8, [rsp+988h+pReportInformation]; pReportInformation
0x18008bcbc  xor     edx, edx; repType
0x18008bcbe  lea     rcx, pwzEventType; "UpdateAgentDiag"
0x18008bcc5  call    cs:__imp_WerReportCreate
0x18008bccc  nop     dword ptr [rax+rax+00h]
0x18008bcd1  mov     r14d, eax
0x18008bcd4  test    eax, eax
0x18008bcd6  jns     loc_18008BD76
0x18008bcdc  mov     [rsp+988h+var_58], eax
0x18008bce3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bcea  test    rcx, rcx
0x18008bced  jz      short loc_18008BD3A
0x18008bcef  lea     r9, aWatsonhelperCo_1; "WatsonHelper: Could not create helper"
0x18008bcf6  mov     ebx, 3
0x18008bcfb  mov     r8d, ebx
0x18008bcfe  xor     edx, edx
0x18008bd00  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008bd05  lea     rax, [rsp+988h+var_58]
0x18008bd0d  mov     [rsp+988h+pwzValue], rax
0x18008bd15  lea     rax, [rsp+988h+pwzValue]
0x18008bd1d  mov     [rsp+988h+var_968], rax; int
0x18008bd22  lea     r9, asc_1802C6678; ": {}"
0x18008bd29  mov     r8d, ebx
0x18008bd2c  mov     dl, 1
0x18008bd2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bd35  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008bd3a  mov     rcx, [rsp+988h]; this
0x18008bd42  mov     r9d, r14d; char *
0x18008bd45  lea     r8, aOnecoreBaseNts_17; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008bd4c  mov     edx, 85h; void *
0x18008bd51  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008bd56  nop
0x18008bd57  mov     rcx, [rsp+988h+phReportHandle]; hReportHandle
0x18008bd5f  test    rcx, rcx
0x18008bd62  jz      short loc_18008BD71
0x18008bd64  call    cs:__imp_WerReportCloseHandle
0x18008bd6b  nop     dword ptr [rax+rax+00h]
0x18008bd70  nop
0x18008bd71  jmp     loc_18008C3AF
0x18008bd76  lea     r8, pwzValue; "Microsoft Installation encountered a pr"...
0x18008bd7d  mov     ebx, 3
0x18008bd82  mov     edx, ebx; repUITypeID
0x18008bd84  mov     rcx, [rsp+988h+phReportHandle]; hReportHandle
0x18008bd8c  call    cs:__imp_WerReportSetUIOption
0x18008bd93  nop     dword ptr [rax+rax+00h]
0x18008bd98  mov     r14d, eax
0x18008bd9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bda2  test    eax, eax
0x18008bda4  jns     loc_18008BE38
0x18008bdaa  mov     [rsp+988h+var_58], eax
0x18008bdb1  test    rcx, rcx
0x18008bdb4  jz      short loc_18008BDFC
0x18008bdb6  lea     r9, aWatsonhelperCo_0; "WatsonHelper: Could not set UI option"
0x18008bdbd  mov     r8d, ebx
0x18008bdc0  xor     edx, edx
0x18008bdc2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008bdc7  lea     rax, [rsp+988h+var_58]
0x18008bdcf  mov     [rsp+988h+pwzValue], rax
0x18008bdd7  lea     rax, [rsp+988h+pwzValue]
0x18008bddf  mov     [rsp+988h+var_968], rax; int
0x18008bde4  lea     r9, asc_1802C6678; ": {}"
0x18008bdeb  mov     r8d, ebx
0x18008bdee  mov     dl, 1
0x18008bdf0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bdf7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008bdfc  mov     rcx, [rsp+988h]; this
0x18008be04  mov     r9d, r14d; char *
0x18008be07  lea     r8, aOnecoreBaseNts_17; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008be0e  mov     edx, 87h; void *
0x18008be13  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008be18  nop
0x18008be19  mov     rcx, [rsp+988h+phReportHandle]; hReportHandle
0x18008be21  test    rcx, rcx
0x18008be24  jz      short loc_18008BE33
0x18008be26  call    cs:__imp_WerReportCloseHandle
0x18008be2d  nop     dword ptr [rax+rax+00h]
0x18008be32  nop
0x18008be33  jmp     loc_18008C3AF
0x18008be38  xor     edx, edx
0x18008be3a  xor     eax, eax
0x18008be3c  mov     [rsp+988h+dwparamID], edx
0x18008be40  mov     r9, [rdi+10h]
0x18008be44  mov     r8d, eax
0x18008be47  mov     rax, [rdi+18h]
0x18008be4b  sub     rax, r9
0x18008be4e  sar     rax, 5
0x18008be52  cmp     r8, rax
0x18008be55  jnb     loc_18008BFA3
0x18008be5b  mov     eax, r8d
0x18008be5e  shl     rax, 5
0x18008be62  add     r9, rax
0x18008be65  cmp     qword ptr [r9+18h], 7
0x18008be6a  jbe     short loc_18008BE6F
0x18008be6c  mov     r9, [r9]
0x18008be6f  mov     [rsp+988h+pwzValue], r9
0x18008be77  mov     rax, [rdi+40h]
0x18008be7b  cmp     byte ptr [r8+rax], 0
0x18008be80  jz      short loc_18008BECD
0x18008be82  test    rcx, rcx
0x18008be85  jz      short loc_18008BEBE
0x18008be87  lea     rax, [rsp+988h+pwzValue]
0x18008be8f  mov     [rsp+988h+var_960], rax
0x18008be94  lea     rax, [rsp+988h+dwparamID]
0x18008be99  mov     [rsp+988h+var_968], rax
0x18008be9e  lea     r9, aWatsonhelperPa; "WatsonHelper: Parameter [{}] is muted -"...
0x18008bea5  mov     r8d, 1
0x18008beab  mov     dl, r8b
0x18008beae  call    ??$LogNumObjects@KPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBKAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<ulong,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,ulong const &,wchar_t const * const &)
0x18008beb3  mov     edx, [rsp+988h+dwparamID]
0x18008beb7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bebe  lea     r9, asc_1802C6800; "X"
0x18008bec5  mov     [rsp+988h+pwzValue], r9
0x18008becd  test    rcx, rcx
0x18008bed0  jz      short loc_18008BF0A
0x18008bed2  lea     rax, [rsp+988h+pwzValue]
0x18008beda  mov     [rsp+988h+var_960], rax
0x18008bedf  lea     rax, [rsp+988h+dwparamID]
0x18008bee4  mov     [rsp+988h+var_968], rax
0x18008bee9  lea     r9, aWatsonhelperSe_0; "WatsonHelper: Setting Parameter [{}] to"...
0x18008bef0  mov     r8d, 1
0x18008bef6  mov     dl, r8b
0x18008bef9  call    ??$LogNumObjects@KPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBKAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<ulong,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,ulong const &,wchar_t const * const &)
0x18008befe  mov     edx, [rsp+988h+dwparamID]; dwparamID
0x18008bf02  mov     r9, [rsp+988h+pwzValue]; pwzValue
0x18008bf0a  xor     r8d, r8d; pwzName
0x18008bf0d  mov     rcx, [rsp+988h+phReportHandle]; hReportHandle
0x18008bf15  call    cs:__imp_WerReportSetParameter
0x18008bf1c  nop     dword ptr [rax+rax+00h]
0x18008bf21  test    eax, eax
0x18008bf23  jns     short loc_18008BF8F
0x18008bf25  mov     [rsp+988h+var_58], eax
0x18008bf2c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bf33  test    rcx, rcx
0x18008bf36  jz      short loc_18008BF96
0x18008bf38  lea     rax, [rsp+988h+pwzValue]
0x18008bf40  mov     [rsp+988h+var_960], rax
0x18008bf45  lea     rax, [rsp+988h+dwparamID]
0x18008bf4a  mov     [rsp+988h+var_968], rax
0x18008bf4f  lea     r9, aWatsonhelperFa_1; "WatsonHelper: Failed to add parameter ["...
0x18008bf56  mov     r8d, esi
0x18008bf59  xor     edx, edx
0x18008bf5b  call    ??$LogNumObjects@KPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBKAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<ulong,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,ulong const &,wchar_t const * const &)
0x18008bf60  lea     rax, [rsp+988h+var_58]
0x18008bf68  mov     qword ptr [rsp+988h+var_958], rax
0x18008bf6d  lea     rax, [rsp+988h+var_958]
0x18008bf72  mov     [rsp+988h+var_968], rax
0x18008bf77  lea     r9, a0; ": {0}"
0x18008bf7e  mov     r8d, esi
0x18008bf81  mov     dl, 1
0x18008bf83  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bf8a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008bf8f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008bf96  mov     edx, [rsp+988h+dwparamID]
0x18008bf9a  inc     edx
0x18008bf9c  mov     eax, edx
0x18008bf9e  jmp     loc_18008BE3C
0x18008bfa3  xorps   xmm0, xmm0
0x18008bfa6  movdqu  xmmword ptr [rsp+988h+pwzPath], xmm0
0x18008bfaf  mov     [rsp+988h+var_30], 0
0x18008bfbb  mov     r14, [rdi+30h]
0x18008bfbf  mov     rbx, [rdi+28h]
0x18008bfc3  psrldq  xmm0, 8
0x18008bfc8  movq    rdi, xmm0
0x18008bfcd  cmp     rbx, r14
0x18008bfd0  jz      loc_18008C058
0x18008bfd6  mov     rcx, [rbx+10h]
0x18008bfda  cmp     qword ptr [rbx+18h], 7
0x18008bfdf  jbe     short loc_18008BFE6
0x18008bfe1  mov     rax, [rbx]
0x18008bfe4  jmp     short loc_18008BFE9
0x18008bfe6  mov     rax, rbx
0x18008bfe9  mov     qword ptr [rsp+988h+var_958], rax
0x18008bfee  mov     [rsp+988h+var_950], rcx
0x18008bff3  lea     rcx, [rsp+988h+var_958]
0x18008bff8  call    ?FileExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; FileExists(wil::basic_zstring_view<wchar_t> const &)
0x18008bffd  test    al, al
0x18008bfff  jz      short loc_18008C047
0x18008c001  mov     rax, [rsp+988h+pwzPath+8]
0x18008c009  cmp     rax, [rsp+988h+var_30]
0x18008c011  jz      short loc_18008C034
0x18008c013  mov     rdx, rbx
0x18008c016  mov     rcx, rax
0x18008c019  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008c01e  mov     rdi, [rsp+988h+pwzPath+8]
0x18008c026  add     rdi, 20h ; ' '
0x18008c02a  mov     [rsp+988h+pwzPath+8], rdi
0x18008c032  jmp     short loc_18008C04F
0x18008c034  mov     r8, rbx
0x18008c037  mov     rdx, rax
0x18008c03a  lea     rcx, [rsp+988h+pwzPath]
0x18008c042  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18008c047  mov     rdi, [rsp+988h+pwzPath+8]
0x18008c04f  add     rbx, 20h ; ' '
0x18008c053  jmp     loc_18008BFCD
0x18008c058  mov     rbx, [rsp+988h+pwzPath]
0x18008c060  cmp     rbx, rdi
0x18008c063  jz      short loc_18008C0C2
0x18008c065  mov     r8, rbx
0x18008c068  lea     rdx, aWatsonhelperAd; "WatsonHelper: Adding file to report [{}"...
0x18008c06f  mov     ecx, 1
0x18008c074  call    ??$TraceAtLevel@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXW4LogLevel@0@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceAtLevel<std::wstring>(LogAdapter::LogLevel,char const * const,std::wstring const &)
0x18008c079  cmp     qword ptr [rbx+18h], 7
0x18008c07e  jbe     short loc_18008C085
0x18008c080  mov     rdx, [rbx]
0x18008c083  jmp     short loc_18008C088
0x18008c085  mov     rdx, rbx; pwzPath
0x18008c088  mov     r9d, esi; dwFileFlags
0x18008c08b  mov     r8d, 5; repFileType
0x18008c091  mov     rcx, [rsp+988h+phReportHandle]; hReportHandle
0x18008c099  call    cs:__imp_WerReportAddFile
0x18008c0a0  nop     dword ptr [rax+rax+00h]
0x18008c0a5  test    eax, eax
0x18008c0a7  jns     short loc_18008C0BC
0x18008c0a9  mov     r9, rbx
0x18008c0ac  lea     r8, aWatsonhelperFa_0; "WatsonHelper: Failed to add file [{}]"
0x18008c0b3  mov     edx, eax
0x18008c0b5  mov     ecx, esi
0x18008c0b7  call    ??$TraceAtLevelHr@JV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceAtLevelHr<long,std::wstring>(LogAdapter::LogLevel,long,char const * const,std::wstring const &)
0x18008c0bc  add     rbx, 20h ; ' '
0x18008c0c0  jmp     short loc_18008C060
0x18008c0c2  mov     [rsp+988h+pSubmitResult], 0
0x18008c0cd  lea     rcx, aWatsonhelperUp; "WatsonHelper:  Uploading Report."
0x18008c0d4  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18008c0d9  lea     rax, [rsp+988h+pSubmitResult]
0x18008c0e1  mov     qword ptr [rsp+988h+var_958], rax
0x18008c0e6  lea     r9, [rsp+988h+pSubmitResult]; pSubmitResult
0x18008c0ee  mov     edx, 1; consent
0x18008c0f3  lea     r8d, [rdx+3Fh]; dwFlags
0x18008c0f7  mov     rcx, [rsp+988h+phReportHandle]; hReportHandle
0x18008c0ff  call    cs:__imp_WerReportSubmit
0x18008c106  nop     dword ptr [rax+rax+00h]
0x18008c10b  test    eax, eax
0x18008c10d  jns     short loc_18008C15F
  ... truncated ...
```

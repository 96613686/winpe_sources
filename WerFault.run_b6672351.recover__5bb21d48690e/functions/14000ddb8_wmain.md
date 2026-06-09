# wmain

- ea: `0x14000ddb8`
- end: `0x14000e3b0`
- name: `wmain`
- size: `1528`
- prototype: `__int64 __fastcall(int, wchar_t **)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400022d0`

## callees

- `0x140001008`
- `0x140002490`
- `0x1400030f8`
- `0x140005550`
- `0x1400088e8`
- `0x14000b398`
- `0x14000beb8`
- `0x14000c53c`
- `0x14000c980`
- `0x14000d438`
- `0x14000d464`
- `0x14000d49c`
- `0x14000d5ac`
- `0x14000ddb8`
- `0x14001254c`
- `0x140014f14`
- `0x140018a1c`
- `0x14001a274`
- `0x1400311d8`
- `0x1400314d0`
- `0x140036e5c`
- `0x140048410`
- `0x14005f564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000e00b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000e00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dfc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dfc4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000de96`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000de96`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e10d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e12e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e14f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e170`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e1a1`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e10d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e12e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e14f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e170`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000e1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000dea5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000deb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000dea5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000deb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000e034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000e034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e0e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e35d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e0e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e35d`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000dfb4`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000dfb4`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x14000e052`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x14000e052`
- `ntdll!EtwUnregisterTraceGuids` at `0x14000e330`
- `ntdll!EtwUnregisterTraceGuids` at `0x14000e330`
- `ntdll!EtwRegisterTraceGuidsW` at `0x14000de63`
- `ntdll!EtwRegisterTraceGuidsW` at `0x14000de63`
- `wer!WerpCreateMachineStore` at `0x14000e079`
- `wer!WerpCreateMachineStore` at `0x14000e079`
- `wer!WerpSetExitListeners` at `0x14000e01c`
- `wer!WerpSetExitListeners` at `0x14000e01c`

## string_xrefs

- `0x14000e2a3`: `Invalid commandline passed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wmain(unsigned int a1, const wchar_t **a2)
{
  __int64 *v4; // rbx
  __int64 *v5; // rdi
  __int64 v6; // r8
  LPWSTR CommandLineW; // rdi
  char CurrentProcessId; // bl
  DWORD v9; // eax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // edi
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  unsigned int v18; // edx
  __int64 v19; // rax
  wchar_t *v20; // rbx
  unsigned int v21; // eax
  HANDLE v22; // rcx
  REGHANDLE v23; // rcx
  REGHANDLE v24; // rcx
  REGHANDLE v25; // rcx
  REGHANDLE v26; // rcx
  REGHANDLE v27; // rcx
  CUserModeHangReport *v28; // rbx
  const struct wil::FailureInfo *v30; // rdx
  char *v31; // [rsp+28h] [rbp-D8h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v34[160]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v36; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  qword_14007EEF0 = 0;
  WPP_MAIN_CB = 0;
  qword_14007EEF8 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WerFaultTracingGuid;
  v4 = &WPP_MAIN_CB;
  WPP_GLOBAL_Control = (CUserModeHangReport *)&WPP_MAIN_CB;
  v5 = &WPP_REGISTRATION_GUIDS;
  do
  {
    v6 = *v5++;
    v35 = v6;
    v36 = 0;
    v4[4] = v6;
    EtwRegisterTraceGuidsW(WppControlCallback, v4, v6, 1, &v35, 0, 0, v4 + 1);
    v4 = (__int64 *)*v4;
  }
  while ( v4 );
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    CommandLineW = GetCommandLineW();
    CurrentProcessId = GetCurrentProcessId();
    v9 = GetCurrentProcessId();
    WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v9, CurrentProcessId, (__int64)CommandLineW);
  }
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007E0B8);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007E0F0);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007E038);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007E000);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::GetImpl'::`2'::impl) )
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007E1C8);
  McGenEventRegister_EventRegister(
    EventProviderApplication_Error,
    v12,
    EventProviderApplication_Error_Context,
    EventProviderApplication_Error_Context);
  McGenEventRegister_EventRegister(
    S_MICROSOFT_WINDOWS_WER_DIAG,
    v13,
    S_MICROSOFT_WINDOWS_WER_DIAG_Context,
    S_MICROSOFT_WINDOWS_WER_DIAG_Context);
  McGenEventRegister_EventRegister(
    S_Microsoft_Windows_WER_SystemErrorReporting,
    v14,
    S_Microsoft_Windows_WER_SystemErrorReporting_Context,
    S_Microsoft_Windows_WER_SystemErrorReporting_Context);
  if ( wil::details::g_pfnLoggingCallback
    && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != ResultLoggingCallback )
  {
    memset_0(v34, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v34, v30);
  }
  v15 = 1;
  wil::details::g_pfnLoggingCallback = (__int64)ResultLoggingCallback;
  v33 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &v33, 4) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        188,
        WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
        (unsigned int)LastError);
    }
  }
  SetErrorMode(2u);
  CBlackBox::Start();
  WerpSetExitListeners();
  v35 = 0x100000001LL;
  LODWORD(v36) = 1;
  CurrentProcess = GetCurrentProcess();
  SetProcessInformation(CurrentProcess, 4, &v35, 12);
  hObject = 0;
  if ( UtilIsWinPE()
    || (v19 = tlx::replace<tlx::file_handle_traits>(&hObject), (int)WerpCreateMachineStore(v19) >= 0)
    && hObject != (HANDLE)-1LL )
  {
    if ( a1 - 3 > 0xB )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6fbb6397bf5c3852453c2114d40a8940_Traceguids, a1, 3, 14);
      }
    }
    else
    {
      v20 = (wchar_t *)a2[1];
      if ( *v20 == 45 )
      {
        if ( v20[1] == 117 && !v20[2] )
        {
          v21 = UserCrashMainSEH(a1, a2);
LABEL_24:
          v15 = v21;
          goto LABEL_25;
        }
        if ( *v20 == 45 && v20[1] == 107 && !v20[2] )
        {
          v21 = KernelCrashMain(a1, a2);
          goto LABEL_24;
        }
      }
      if ( !wcscmp_0(a2[1], L"/hc") || *v20 == 47 && v20[1] == 104 && !v20[2] )
      {
        v21 = WerCoreReportHang(a1 - 1, a2 + 1);
        goto LABEL_24;
      }
      if ( *v20 == 45 && v20[1] == 115 && !v20[2] )
      {
        v21 = SilentProcessExitMain(a1, a2);
        goto LABEL_24;
      }
      if ( !wcscmp_0(v20, L"-pr") )
      {
        v21 = ReflectionServerMain(a1, a2);
        goto LABEL_24;
      }
      if ( !wcscmp_0(v20, L"-pss") )
      {
        v21 = SnapshotCaptureMain(a1, a2);
        goto LABEL_24;
      }
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\standard\\werfaultexemain.cpp",
        (const char *)0x80000000LL,
        (int)"Invalid commandline passed",
        v31);
    }
  }
LABEL_25:
  v22 = hObject;
  hObject = 0;
  if ( (unsigned __int64)v22 + 1 > 1 )
    CloseHandle(v22);
  CBlackBox::Stop((wchar_t *)v22, v18);
  v23 = RegHandle;
  dword_14007E0B8 = 0;
  RegHandle = 0;
  EventUnregister(v23);
  v24 = qword_14007E110;
  dword_14007E0F0 = 0;
  qword_14007E110 = 0;
  EventUnregister(v24);
  v25 = qword_14007E058;
  dword_14007E038 = 0;
  qword_14007E058 = 0;
  EventUnregister(v25);
  v26 = qword_14007E020;
  dword_14007E000 = 0;
  qword_14007E020 = 0;
  EventUnregister(v26);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::GetImpl'::`2'::impl) )
  {
    v27 = qword_14007E1E8;
    dword_14007E1C8 = 0;
    qword_14007E1E8 = 0;
    EventUnregister(v27);
  }
  McGenEventUnregister_EventUnregister(EventProviderApplication_Error_Context);
  McGenEventUnregister_EventUnregister(S_MICROSOFT_WINDOWS_WER_DIAG_Context);
  McGenEventUnregister_EventUnregister(S_Microsoft_Windows_WER_SystemErrorReporting_Context);
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control )
  {
    while ( v28 )
    {
      if ( *((_QWORD *)v28 + 1) )
      {
        EtwUnregisterTraceGuids();
        *((_QWORD *)v28 + 1) = 0;
      }
      v28 = *(CUserModeHangReport **)v28;
    }
    WPP_GLOBAL_Control = (CUserModeHangReport *)&WPP_GLOBAL_Control;
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v15;
}

```

## disassembly

```asm
0x14000ddb8  mov     [rsp-8+arg_10], rbx
0x14000ddbd  push    rbp
0x14000ddbe  push    rsi
0x14000ddbf  push    rdi
0x14000ddc0  push    r12
0x14000ddc2  push    r13
0x14000ddc4  push    r14
0x14000ddc6  push    r15
0x14000ddc8  lea     rbp, [rsp-10h]
0x14000ddcd  sub     rsp, 110h
0x14000ddd4  mov     rax, cs:__security_cookie
0x14000dddb  xor     rax, rsp
0x14000ddde  mov     [rbp+40h+var_40], rax
0x14000dde2  mov     r14, rdx
0x14000dde5  mov     esi, ecx
0x14000dde7  xor     r12d, r12d
0x14000ddea  mov     cs:qword_14007EEF0, r12
0x14000ddf1  mov     cs:WPP_MAIN_CB, r12
0x14000ddf8  lea     r13d, [r12+1]
0x14000ddfd  mov     cs:qword_14007EEF8, r13
0x14000de04  lea     rax, WPP_ThisDir_CTLGUID_WerFaultTracingGuid
0x14000de0b  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x14000de12  lea     rbx, WPP_MAIN_CB
0x14000de19  mov     cs:WPP_GLOBAL_Control, rbx
0x14000de20  lea     rdi, WPP_REGISTRATION_GUIDS
0x14000de27  mov     r8, [rdi]
0x14000de2a  lea     rdi, [rdi+8]
0x14000de2e  mov     [rbp+40h+var_50], r8
0x14000de32  mov     [rbp+40h+var_48], r12
0x14000de36  mov     [rbx+20h], r8
0x14000de3a  lea     rax, [rbx+8]
0x14000de3e  mov     [rsp+140h+var_108], rax
0x14000de43  mov     [rsp+140h+var_110], r12
0x14000de48  mov     [rsp+140h+var_118], r12
0x14000de4d  lea     rax, [rbp+40h+var_50]
0x14000de51  mov     qword ptr [rsp+140h+var_120], rax
0x14000de56  mov     r9d, r13d
0x14000de59  mov     rdx, rbx
0x14000de5c  lea     rcx, WppControlCallback
0x14000de63  call    cs:__imp_EtwRegisterTraceGuidsW
0x14000de6a  nop     dword ptr [rax+rax+00h]
0x14000de6f  mov     rbx, [rbx]
0x14000de72  test    rbx, rbx
0x14000de75  jnz     short loc_14000DE27
0x14000de77  lea     rbx, WPP_GLOBAL_Control
0x14000de7e  mov     r15d, 4
0x14000de84  mov     rax, cs:WPP_GLOBAL_Control
0x14000de8b  cmp     rax, rbx
0x14000de8e  jz      short loc_14000DEE2
0x14000de90  test    [rax+1Ch], r15b
0x14000de94  jz      short loc_14000DEE2
0x14000de96  call    cs:__imp_GetCommandLineW
0x14000de9d  nop     dword ptr [rax+rax+00h]
0x14000dea2  mov     rdi, rax
0x14000dea5  call    cs:__imp_GetCurrentProcessId
0x14000deac  nop     dword ptr [rax+rax+00h]
0x14000deb1  mov     ebx, eax
0x14000deb3  call    cs:__imp_GetCurrentProcessId
0x14000deba  nop     dword ptr [rax+rax+00h]
0x14000debf  mov     [rsp+140h+var_118], rdi; char *
0x14000dec4  mov     [rsp+140h+var_120], ebx
0x14000dec8  mov     r9d, eax
0x14000decb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ded2  mov     rcx, [rcx+10h]
0x14000ded6  call    WPP_SF_DDS
0x14000dedb  lea     rbx, WPP_GLOBAL_Control
0x14000dee2  lea     rcx, dword_14007E0B8; CallbackContext
0x14000dee9  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000deee  lea     rcx, dword_14007E0F0; CallbackContext
0x14000def5  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000defa  lea     rcx, dword_14007E038; CallbackContext
0x14000df01  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000df06  lea     rcx, dword_14007E000; CallbackContext
0x14000df0d  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000df12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace> `wil::Feature<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::GetImpl(void)'::`2'::impl
0x14000df19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::__private_IsEnabled(void)
0x14000df1e  test    al, al
0x14000df20  jz      short loc_14000DF2E
0x14000df22  lea     rcx, dword_14007E1C8; CallbackContext
0x14000df29  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000df2e  lea     r9, EventProviderApplication_Error_Context
0x14000df35  lea     r8, EventProviderApplication_Error_Context
0x14000df3c  lea     rcx, EventProviderApplication_Error
0x14000df43  call    McGenEventRegister_EventRegister
0x14000df48  lea     r9, S_MICROSOFT_WINDOWS_WER_DIAG_Context
0x14000df4f  lea     r8, S_MICROSOFT_WINDOWS_WER_DIAG_Context
0x14000df56  lea     rcx, S_MICROSOFT_WINDOWS_WER_DIAG
0x14000df5d  call    McGenEventRegister_EventRegister
0x14000df62  lea     r9, S_Microsoft_Windows_WER_SystemErrorReporting_Context
0x14000df69  lea     r8, S_Microsoft_Windows_WER_SystemErrorReporting_Context
0x14000df70  lea     rcx, S_Microsoft_Windows_WER_SystemErrorReporting
0x14000df77  call    McGenEventRegister_EventRegister
0x14000df7c  lea     rcx, ?ResultLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z; ResultLoggingCallback(wil::FailureInfo const &)
0x14000df83  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000df8a  test    rax, rax
0x14000df8d  jz      short loc_14000DF98
0x14000df8f  cmp     rax, rcx
0x14000df92  jnz     loc_14000E393
0x14000df98  mov     edi, r13d
0x14000df9b  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x14000dfa2  mov     [rsp+140h+var_F8], r13d
0x14000dfa7  mov     r8, r15
0x14000dfaa  lea     rdx, [rsp+140h+var_F8]
0x14000dfaf  mov     ecx, 10h
0x14000dfb4  call    cs:__imp_SetProcessMitigationPolicy
0x14000dfbb  nop     dword ptr [rax+rax+00h]
0x14000dfc0  test    eax, eax
0x14000dfc2  jnz     short loc_14000E006
0x14000dfc4  call    cs:__imp_GetLastError
0x14000dfcb  nop     dword ptr [rax+rax+00h]
0x14000dfd0  test    eax, eax
0x14000dfd2  jle     short loc_14000DFDC
0x14000dfd4  movzx   eax, ax
0x14000dfd7  or      eax, 80070000h
0x14000dfdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfe3  cmp     rcx, rbx
0x14000dfe6  jz      short loc_14000E006
0x14000dfe8  test    [rcx+1Ch], r13b
0x14000dfec  jz      short loc_14000E006
0x14000dfee  mov     edx, 0BCh
0x14000dff3  mov     r9d, eax
0x14000dff6  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x14000dffd  mov     rcx, [rcx+10h]
0x14000e001  call    WPP_SF_d
0x14000e006  mov     ecx, 2; uMode
0x14000e00b  call    cs:__imp_SetErrorMode
0x14000e012  nop     dword ptr [rax+rax+00h]
0x14000e017  call    ?Start@CBlackBox@@SAJXZ; CBlackBox::Start(void)
0x14000e01c  call    cs:__imp_WerpSetExitListeners
0x14000e023  nop     dword ptr [rax+rax+00h]
0x14000e028  mov     dword ptr [rbp+40h+var_50], r13d
0x14000e02c  mov     dword ptr [rbp+40h+var_50+4], r13d
0x14000e030  mov     dword ptr [rbp+40h+var_48], r13d
0x14000e034  call    cs:__imp_GetCurrentProcess
0x14000e03b  nop     dword ptr [rax+rax+00h]
0x14000e040  mov     rcx, rax
0x14000e043  mov     ebx, 0Ch
0x14000e048  mov     r9d, ebx
0x14000e04b  lea     r8, [rbp+40h+var_50]
0x14000e04f  mov     edx, r15d
0x14000e052  call    cs:__imp_SetProcessInformation
0x14000e059  nop     dword ptr [rax+rax+00h]
0x14000e05e  mov     [rsp+140h+hObject], r12
0x14000e063  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x14000e068  test    al, al
0x14000e06a  jnz     short loc_14000E091
0x14000e06c  lea     rcx, [rsp+140h+hObject]
0x14000e071  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14000e076  mov     rcx, rax
0x14000e079  call    cs:__imp_WerpCreateMachineStore
0x14000e080  nop     dword ptr [rax+rax+00h]
0x14000e085  test    eax, eax
0x14000e087  js      short loc_14000E0CD
0x14000e089  cmp     [rsp+140h+hObject], 0FFFFFFFFFFFFFFFFh
0x14000e08f  jz      short loc_14000E0CD
0x14000e091  lea     eax, [rsi-3]
0x14000e094  cmp     eax, 0Bh
0x14000e097  ja      loc_14000E2DC
0x14000e09d  mov     rbx, [r14+8]
0x14000e0a1  cmp     word ptr [rbx], 2Dh ; '-'
0x14000e0a5  jnz     loc_14000E209
0x14000e0ab  cmp     word ptr [rbx+2], 75h ; 'u'
0x14000e0b0  jnz     loc_14000E1E6
0x14000e0b6  cmp     [rbx+4], r12w
0x14000e0bb  jnz     loc_14000E1E6
0x14000e0c1  mov     rdx, r14
0x14000e0c4  mov     ecx, esi
0x14000e0c6  call    UserCrashMainSEH
0x14000e0cb  mov     edi, eax
0x14000e0cd  lea     r14, WPP_GLOBAL_Control
0x14000e0d4  mov     rcx, [rsp+140h+hObject]; hObject
0x14000e0d9  mov     [rsp+140h+hObject], r12
0x14000e0de  lea     rax, [rcx+1]
0x14000e0e2  cmp     rax, r13
0x14000e0e5  jbe     short loc_14000E0F3
0x14000e0e7  call    cs:__imp_CloseHandle
0x14000e0ee  nop     dword ptr [rax+rax+00h]
0x14000e0f3  call    ?Stop@CBlackBox@@SAJPEA_WK@Z; CBlackBox::Stop(wchar_t *,ulong)
0x14000e0f8  mov     rcx, cs:RegHandle; RegHandle
0x14000e0ff  mov     cs:dword_14007E0B8, r12d
0x14000e106  mov     cs:RegHandle, r12
0x14000e10d  call    cs:__imp_EventUnregister
0x14000e114  nop     dword ptr [rax+rax+00h]
0x14000e119  mov     rcx, cs:qword_14007E110; RegHandle
0x14000e120  mov     cs:dword_14007E0F0, r12d
0x14000e127  mov     cs:qword_14007E110, r12
0x14000e12e  call    cs:__imp_EventUnregister
0x14000e135  nop     dword ptr [rax+rax+00h]
0x14000e13a  mov     rcx, cs:qword_14007E058; RegHandle
0x14000e141  mov     cs:dword_14007E038, r12d
0x14000e148  mov     cs:qword_14007E058, r12
0x14000e14f  call    cs:__imp_EventUnregister
0x14000e156  nop     dword ptr [rax+rax+00h]
0x14000e15b  mov     rcx, cs:qword_14007E020; RegHandle
0x14000e162  mov     cs:dword_14007E000, r12d
0x14000e169  mov     cs:qword_14007E020, r12
0x14000e170  call    cs:__imp_EventUnregister
0x14000e177  nop     dword ptr [rax+rax+00h]
0x14000e17c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace> `wil::Feature<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::GetImpl(void)'::`2'::impl
0x14000e183  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHealthAndExperienceHangTrace>::__private_IsEnabled(void)
0x14000e188  test    al, al
0x14000e18a  jz      short loc_14000E1AD
0x14000e18c  mov     rcx, cs:qword_14007E1E8; RegHandle
0x14000e193  mov     cs:dword_14007E1C8, r12d
0x14000e19a  mov     cs:qword_14007E1E8, r12
0x14000e1a1  call    cs:__imp_EventUnregister
0x14000e1a8  nop     dword ptr [rax+rax+00h]
0x14000e1ad  lea     rcx, EventProviderApplication_Error_Context
0x14000e1b4  call    McGenEventUnregister_EventUnregister
0x14000e1b9  lea     rcx, S_MICROSOFT_WINDOWS_WER_DIAG_Context
0x14000e1c0  call    McGenEventUnregister_EventUnregister
0x14000e1c5  lea     rcx, S_Microsoft_Windows_WER_SystemErrorReporting_Context
0x14000e1cc  call    McGenEventUnregister_EventUnregister
0x14000e1d1  mov     rbx, cs:WPP_GLOBAL_Control
0x14000e1d8  cmp     rbx, r14
0x14000e1db  jz      loc_14000E34F
0x14000e1e1  jmp     loc_14000E343
0x14000e1e6  cmp     word ptr [rbx], 2Dh ; '-'
0x14000e1ea  jnz     short loc_14000E209
0x14000e1ec  cmp     word ptr [rbx+2], 6Bh ; 'k'
0x14000e1f1  jnz     short loc_14000E209
0x14000e1f3  cmp     [rbx+4], r12w
0x14000e1f8  jnz     short loc_14000E209
0x14000e1fa  mov     rdx, r14; wchar_t **
0x14000e1fd  mov     ecx, esi; int
0x14000e1ff  call    ?KernelCrashMain@@YAHHQEAPEB_W@Z; KernelCrashMain(int,wchar_t const * * const)
0x14000e204  jmp     loc_14000E0CB
0x14000e209  lea     rdx, aHc; "/hc"
0x14000e210  mov     rcx, rbx; String1
0x14000e213  call    wcscmp_0
0x14000e218  test    eax, eax
0x14000e21a  jz      loc_14000E2CB
0x14000e220  cmp     word ptr [rbx], 2Fh ; '/'
0x14000e224  jnz     short loc_14000E238
0x14000e226  cmp     word ptr [rbx+2], 68h ; 'h'
0x14000e22b  jnz     short loc_14000E238
0x14000e22d  cmp     [rbx+4], r12w
0x14000e232  jz      loc_14000E2CB
0x14000e238  cmp     word ptr [rbx], 2Dh ; '-'
0x14000e23c  jnz     short loc_14000E25B
0x14000e23e  cmp     word ptr [rbx+2], 73h ; 's'
0x14000e243  jnz     short loc_14000E25B
0x14000e245  cmp     [rbx+4], r12w
0x14000e24a  jnz     short loc_14000E25B
0x14000e24c  mov     rdx, r14; wchar_t **
0x14000e24f  mov     ecx, esi; int
0x14000e251  call    ?SilentProcessExitMain@@YAHHQEAPEB_W@Z; SilentProcessExitMain(int,wchar_t const * * const)
0x14000e256  jmp     loc_14000E0CB
0x14000e25b  lea     rdx, aPr; "-pr"
0x14000e262  mov     rcx, rbx; String1
0x14000e265  call    wcscmp_0
0x14000e26a  test    eax, eax
0x14000e26c  jnz     short loc_14000E27D
0x14000e26e  mov     rdx, r14; wchar_t **
0x14000e271  mov     ecx, esi; int
0x14000e273  call    ?ReflectionServerMain@@YAHHQEAPEB_W@Z; ReflectionServerMain(int,wchar_t const * * const)
0x14000e278  jmp     loc_14000E0CB
0x14000e27d  lea     rdx, aPss; "-pss"
0x14000e284  mov     rcx, rbx; String1
0x14000e287  call    wcscmp_0
0x14000e28c  test    eax, eax
0x14000e28e  jnz     short loc_14000E29F
0x14000e290  mov     rdx, r14; wchar_t **
0x14000e293  mov     ecx, esi; int
0x14000e295  call    ?SnapshotCaptureMain@@YAHHQEAPEB_W@Z; SnapshotCaptureMain(int,wchar_t const * * const)
0x14000e29a  jmp     loc_14000E0CB
0x14000e29f  mov     rcx, [rbp+48h]; this
0x14000e2a3  lea     rax, aInvalidCommand; "Invalid commandline passed"
0x14000e2aa  mov     qword ptr [rsp+140h+var_120], rax; int
0x14000e2af  mov     r9d, 80000000h; char *
0x14000e2b5  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\werfa"...
0x14000e2bc  mov     edx, 11Bh; void *
0x14000e2c1  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000e2c6  jmp     loc_14000E0CD
0x14000e2cb  lea     ecx, [rsi-1]; int
0x14000e2ce  lea     rdx, [r14+8]; wchar_t **
0x14000e2d2  call    ?WerCoreReportHang@@YAHHQEAPEB_W@Z; WerCoreReportHang(int,wchar_t const * * const)
0x14000e2d7  jmp     loc_14000E0CB
0x14000e2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e2e3  lea     r14, WPP_GLOBAL_Control
0x14000e2ea  cmp     rcx, r14
0x14000e2ed  jz      loc_14000E0D4
0x14000e2f3  test    [rcx+1Ch], r13b
0x14000e2f7  jz      loc_14000E0D4
0x14000e2fd  mov     edx, ebx
0x14000e2ff  mov     dword ptr [rsp+140h+var_118], 0Eh
0x14000e307  mov     [rsp+140h+var_120], 3
0x14000e30f  mov     r9d, esi
0x14000e312  lea     r8, WPP_6fbb6397bf5c3852453c2114d40a8940_Traceguids
0x14000e319  mov     rcx, [rcx+10h]
0x14000e31d  call    WPP_SF_DDD
0x14000e322  jmp     loc_14000E0D4
0x14000e327  mov     rcx, [rbx+8]
0x14000e32b  test    rcx, rcx
0x14000e32e  jz      short loc_14000E340
0x14000e330  call    cs:__imp_EtwUnregisterTraceGuids
0x14000e337  nop     dword ptr [rax+rax+00h]
0x14000e33c  mov     [rbx+8], r12
0x14000e340  mov     rbx, [rbx]
0x14000e343  test    rbx, rbx
  ... truncated ...
```

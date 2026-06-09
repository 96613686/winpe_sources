# ServiceLoop(void)

- ea: `0x14000e134`
- end: `0x14000e718`
- name: `?ServiceLoop@@YAJXZ`
- size: `1508`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140011650`

## callees

- `0x140008000`
- `0x140009df4`
- `0x14000a1b0`
- `0x14000c32c`
- `0x14000d4f4`
- `0x14000e030`
- `0x14000e134`
- `0x14000e720`
- `0x140010ec0`
- `0x140011ea8`
- `0x140017a40`
- `0x14001f8f4`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000e301`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000e34c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000e301`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000e34c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000e3a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000e3a1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000e543`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000e543`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e449`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e648`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e449`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e648`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x14000e4d5`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x14000e4d5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x14000e5a0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x14000e5a0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x14000e58a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x14000e58a`

## string_xrefs

- `0x14000e62b`: `SpeechRuntime: Global logoff event signalled. Exiting ServiceLoop`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 ServiceLoop(void)
{
  SpPerfTelemetry::SpeechRuntime *v0; // rcx
  HRESULT v1; // eax
  unsigned int v2; // edi
  __int64 v3; // rdx
  int v4; // esi
  HRESULT v5; // eax
  int v6; // eax
  SpPerfTelemetry::SpeechRuntime *v7; // rcx
  NLInternal::CNotifyVoiceClip *v8; // rcx
  int v9; // r15d
  BOOL v10; // edi
  int v11; // eax
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  char v14; // r14
  DWORD v15; // r8d
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // r14d
  int ppv; // [rsp+20h] [rbp-89h]
  int ppva; // [rsp+20h] [rbp-89h]
  LPVOID v28; // [rsp+30h] [rbp-79h] BYREF
  int v29; // [rsp+38h] [rbp-71h] BYREF
  int v30; // [rsp+3Ch] [rbp-6Dh] BYREF
  LPVOID v31; // [rsp+40h] [rbp-69h] BYREF
  MSG Msg; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v33[128]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  int v35; // [rsp+110h] [rbp+67h] BYREF
  int v36; // [rsp+118h] [rbp+6Fh] BYREF
  int v37; // [rsp+120h] [rbp+77h] BYREF
  int v38; // [rsp+128h] [rbp+7Fh] BYREF

  SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(&g_telemetry, v33);
  SpPerfTelemetry::SpeechRuntime::ServiceLoop(v0);
  v31 = 0;
  v28 = 0;
  v38 = 1;
  v30 = 0;
  v29 = 0;
  v36 = 0;
  v35 = 0;
  v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)g_cpOrchestratorPolicy + 72LL))(
         g_cpOrchestratorPolicy,
         L"VoiceActivationOn",
         &qword_14004D658);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 561;
LABEL_65:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
      (const char *)(unsigned int)v1,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v33);
    return v2;
  }
  v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)g_cpOrchestratorPolicy + 72LL))(
         g_cpOrchestratorPolicy,
         L"VoiceActivationEnableAboveLockscreen",
         &qword_14004D660);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 562;
    goto LABEL_65;
  }
  v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)g_cpOrchestratorPolicy + 72LL))(
         g_cpOrchestratorPolicy,
         L"SpeakerIDOn",
         &qword_14004D668);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 563;
    goto LABEL_65;
  }
  v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)g_cpOrchestratorPolicy + 72LL))(
         g_cpOrchestratorPolicy,
         L"SpeechRuntimeLifetimeOptions",
         &qword_14004D698);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 564;
    goto LABEL_65;
  }
  v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, int *))(*(_QWORD *)g_cpOrchestratorPolicy + 32LL))(
         g_cpOrchestratorPolicy,
         L"VoiceActivationAndCortanaOn",
         &v36);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 567;
    goto LABEL_65;
  }
  v4 = v36 != 0;
  v37 = v4;
  v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, int *))(*(_QWORD *)g_cpOrchestratorPolicy + 32LL))(
         g_cpOrchestratorPolicy,
         L"SpeechRuntimeLifetimeOptions",
         &v35);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 570;
    goto LABEL_65;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  v5 = CoCreateInstance(&CLSID_SpDesktopFocusHandler, 0, 1u, &GUID_f4f33d23_96e6_44a8_b8e5_7c939e50871d, &v31);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
  v1 = CoCreateInstance(&CLSID_SpSapiServer, 0, 1u, &GUID_31e99ed0_6ad8_431b_ae3c_652d9e8c7832, &v28);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 578;
    goto LABEL_65;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v28 + 80LL))(v28, &qword_14004D680);
  v7 = retaddr;
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  if ( !v4 && WaitForSingleObject(hObject, 0x2710u) == 258 )
    v38 = 0;
  if ( !g_areVoiceActivationAndCortanaOnBeforeOrchestratorCreation )
  {
    v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, int *))(*(_QWORD *)g_cpOrchestratorPolicy + 32LL))(
           g_cpOrchestratorPolicy,
           L"VoiceActivationAndCortanaOn",
           &v36);
    v2 = v1;
    if ( v1 < 0 )
    {
      v3 = 596;
      goto LABEL_65;
    }
    if ( v36 )
    {
      v4 = 1;
      v37 = 1;
      v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)g_cpOrchestratorKeywordDetector + 24LL))(g_cpOrchestratorKeywordDetector);
      v2 = v1;
      if ( v1 < 0 )
      {
        v3 = 601;
        goto LABEL_65;
      }
    }
    else
    {
      v4 = 0;
      v37 = 0;
    }
  }
  SpPerfTelemetry::SpeechRuntime::Ready(v7);
  v1 = NLInternal::CNotifyVoiceClip::SendToastIfNotEnabled(v8);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 608;
    goto LABEL_65;
  }
  v9 = 1;
  v10 = v35;
  if ( v35 == 2 )
    v10 = IsDebuggerPresent();
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)g_cpOrchestratorInput + 88LL))(
          g_cpOrchestratorInput,
          &v29);
  v12 = retaddr;
  if ( v11 < 0 )
  {
    v13 = 611;
LABEL_35:
    wil::details::in1diag3::_Log_Hr(
      v12,
      (void *)v13,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    goto LABEL_36;
  }
  while ( 1 )
  {
    do
    {
LABEL_36:
      if ( !v10 && (!v9 || !v4 && !v38 && !v30 && !v29) )
      {
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v33);
        return 0;
      }
      v14 = 1;
      v15 = -1;
      if ( v35 == 2 )
        v15 = 500;
      v16 = MsgWaitForMultipleObjectsEx(0xAu, &g_eventHandles, v15, 0x1CFFu, 2u);
      if ( v16 > 5 )
      {
        v19 = v16 - 6;
        if ( !v19 )
        {
          DoTraceMessage(8, "SpeechRuntime: Global logoff event signalled. Exiting ServiceLoop");
          v9 = 0;
LABEL_69:
          v14 = 0;
          goto LABEL_70;
        }
        v20 = v19 - 1;
        if ( !v20 )
        {
          v23 = NLInternal::CVoiceEnabledShellHost::ReleaseVoiceShell();
          if ( v23 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x283,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
              (const char *)(unsigned int)v23,
              ppv);
          goto LABEL_70;
        }
        v21 = v20 - 2;
        if ( !v21 )
        {
          v1 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, int *))(*(_QWORD *)g_cpOrchestratorPolicy + 32LL))(
                 g_cpOrchestratorPolicy,
                 L"SpeechRuntimeLifetimeOptions",
                 &v35);
          v2 = v1;
          if ( v1 < 0 )
          {
            v3 = 647;
            goto LABEL_65;
          }
          goto LABEL_69;
        }
        if ( v21 != 249 )
        {
LABEL_59:
          memset(&Msg, 0, sizeof(Msg));
          while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
            DispatchMessageW(&Msg);
        }
      }
      else if ( v16 == 5 || !v16 )
      {
        ResetEvent(g_eventHandles);
      }
      else
      {
        v17 = v16 - 1;
        if ( v17 && (v18 = v17 - 1) != 0 )
        {
          if ( v18 - 1 > 1 )
            goto LABEL_59;
          v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)g_cpOrchestratorKeywordDetector + 24LL))(g_cpOrchestratorKeywordDetector);
          v2 = v1;
          if ( v1 < 0 )
          {
            v3 = 628;
            goto LABEL_65;
          }
        }
        else
        {
          v1 = CheckVoiceActivationAndCortanaOnOff(&v37);
          v2 = v1;
          if ( v1 < 0 )
          {
            v3 = 623;
            goto LABEL_65;
          }
          v4 = v37;
        }
      }
LABEL_70:
      if ( v35 == 2 )
        v10 = IsDebuggerPresent();
      else
        v10 = v35;
    }
    while ( !v14 );
    v24 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v28 + 48LL))(v28, &v38);
    v25 = v24;
    if ( v24 < 0 )
      break;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)g_cpOrchestratorInput + 80LL))(
            g_cpOrchestratorInput,
            &v30);
    if ( v11 < 0 )
    {
      v12 = retaddr;
      v13 = 667;
      goto LABEL_35;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x29A,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
    (const char *)(unsigned int)v24,
    ppv);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v33);
  return v25;
}

```

## disassembly

```asm
0x14000e134  push    rbp
0x14000e136  push    rbx
0x14000e137  push    rsi
0x14000e138  push    rdi
0x14000e139  push    r12
0x14000e13b  push    r14
0x14000e13d  push    r15
0x14000e13f  lea     rbp, [rsp-27h]
0x14000e144  sub     rsp, 0D0h
0x14000e14b  lea     rdx, [rbp+57h+var_80]
0x14000e14f  lea     rcx, ?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x14000e156  call    ?ContinueActivityOnCurrentThread@SpeechRuntime@SpPerfTelemetry@@UEAA?AVActivityThreadWatcher@wil@@XZ; SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(void)
0x14000e15b  nop
0x14000e15c  call    ?ServiceLoop@SpeechRuntime@SpPerfTelemetry@@QEAAXXZ; SpPerfTelemetry::SpeechRuntime::ServiceLoop(void)
0x14000e161  xor     r12d, r12d
0x14000e164  mov     [rbp+57h+var_C0], r12
0x14000e168  mov     [rbp+57h+var_D0], r12
0x14000e16c  mov     [rbp+57h+arg_18], 1
0x14000e173  mov     [rbp+57h+var_C4], r12d
0x14000e177  mov     [rbp+57h+var_C8], r12d
0x14000e17b  mov     [rbp+57h+arg_8], r12d
0x14000e17f  mov     [rbp+57h+arg_0], r12d
0x14000e183  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e18a  mov     rax, [rcx]
0x14000e18d  lea     r8, qword_14004D658
0x14000e194  lea     rdx, aVoiceactivatio_1; "VoiceActivationOn"
0x14000e19b  mov     rax, [rax+48h]
0x14000e19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1a4  mov     edi, eax
0x14000e1a6  test    eax, eax
0x14000e1a8  jns     short loc_14000E1BB
0x14000e1aa  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000e1b1  mov     edx, 231h
0x14000e1b6  jmp     loc_14000E5DB
0x14000e1bb  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e1c2  mov     rax, [rcx]
0x14000e1c5  lea     r8, qword_14004D660
0x14000e1cc  lea     rdx, aVoiceactivatio_3; "VoiceActivationEnableAboveLockscreen"
0x14000e1d3  mov     rax, [rax+48h]
0x14000e1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1dc  mov     edi, eax
0x14000e1de  test    eax, eax
0x14000e1e0  jns     short loc_14000E1F3
0x14000e1e2  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000e1e9  mov     edx, 232h
0x14000e1ee  jmp     loc_14000E5DB
0x14000e1f3  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e1fa  mov     rax, [rcx]
0x14000e1fd  lea     r8, qword_14004D668
0x14000e204  lea     rdx, aSpeakeridon; "SpeakerIDOn"
0x14000e20b  mov     rax, [rax+48h]
0x14000e20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e214  mov     edi, eax
0x14000e216  test    eax, eax
0x14000e218  jns     short loc_14000E22B
0x14000e21a  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000e221  mov     edx, 233h
0x14000e226  jmp     loc_14000E5DB
0x14000e22b  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e232  mov     rax, [rcx]
0x14000e235  lea     r8, qword_14004D698
0x14000e23c  lea     rdx, aSpeechruntimel; "SpeechRuntimeLifetimeOptions"
0x14000e243  mov     rax, [rax+48h]
0x14000e247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e24c  mov     edi, eax
0x14000e24e  test    eax, eax
0x14000e250  jns     short loc_14000E263
0x14000e252  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000e259  mov     edx, 234h
0x14000e25e  jmp     loc_14000E5DB
0x14000e263  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e26a  mov     rax, [rcx]
0x14000e26d  lea     r8, [rbp+57h+arg_8]
0x14000e271  lea     rdx, aVoiceactivatio; "VoiceActivationAndCortanaOn"
0x14000e278  mov     rax, [rax+20h]
0x14000e27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e281  mov     edi, eax
0x14000e283  test    eax, eax
0x14000e285  jns     short loc_14000E298
0x14000e287  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000e28e  mov     edx, 237h
0x14000e293  jmp     loc_14000E5DB
0x14000e298  mov     esi, r12d
0x14000e29b  cmp     [rbp+57h+arg_8], r12d
0x14000e29f  setnz   sil
0x14000e2a3  mov     [rbp+57h+arg_10], esi
0x14000e2a6  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e2ad  mov     rax, [rcx]
0x14000e2b0  lea     r8, [rbp+57h+arg_0]
0x14000e2b4  lea     rdx, aSpeechruntimel; "SpeechRuntimeLifetimeOptions"
0x14000e2bb  mov     rax, [rax+20h]
0x14000e2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2c4  mov     edi, eax
0x14000e2c6  test    eax, eax
0x14000e2c8  jns     short loc_14000E2DB
0x14000e2ca  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000e2d1  mov     edx, 23Ah
0x14000e2d6  jmp     loc_14000E5DB
0x14000e2db  lea     rcx, [rbp+57h+var_C0]
0x14000e2df  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000e2e4  lea     rax, [rbp+57h+var_C0]
0x14000e2e8  mov     qword ptr [rsp+100h+ppv], rax; int
0x14000e2ed  lea     r9, _GUID_f4f33d23_96e6_44a8_b8e5_7c939e50871d; riid
0x14000e2f4  xor     edx, edx; pUnkOuter
0x14000e2f6  lea     r8d, [rdx+1]; dwClsContext
0x14000e2fa  lea     rcx, CLSID_SpDesktopFocusHandler; rclsid
0x14000e301  call    cs:__imp_CoCreateInstance
0x14000e307  mov     rcx, [rbp+5Fh]; this
0x14000e30b  lea     rbx, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000e312  test    eax, eax
0x14000e314  jns     short loc_14000E326
0x14000e316  mov     r9d, eax; char *
0x14000e319  mov     r8, rbx; unsigned int
0x14000e31c  mov     edx, 23Eh; void *
0x14000e321  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e326  lea     rcx, [rbp+57h+var_D0]
0x14000e32a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000e32f  lea     rax, [rbp+57h+var_D0]
0x14000e333  mov     qword ptr [rsp+100h+ppv], rax; int
0x14000e338  lea     r9, _GUID_31e99ed0_6ad8_431b_ae3c_652d9e8c7832; riid
0x14000e33f  xor     edx, edx; pUnkOuter
0x14000e341  lea     r8d, [rdx+1]; dwClsContext
0x14000e345  lea     rcx, CLSID_SpSapiServer; rclsid
0x14000e34c  call    cs:__imp_CoCreateInstance
0x14000e352  mov     edi, eax
0x14000e354  test    eax, eax
0x14000e356  jns     short loc_14000E362
0x14000e358  mov     edx, 242h
0x14000e35d  jmp     loc_14000E5D8
0x14000e362  mov     rcx, [rbp+57h+var_D0]
0x14000e366  mov     rax, [rcx]
0x14000e369  lea     rdx, qword_14004D680
0x14000e370  mov     rax, [rax+50h]
0x14000e374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e379  mov     rcx, [rbp+5Fh]; this
0x14000e37d  test    eax, eax
0x14000e37f  jns     short loc_14000E391
0x14000e381  mov     r9d, eax; char *
0x14000e384  mov     r8, rbx; unsigned int
0x14000e387  mov     edx, 244h; void *
0x14000e38c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e391  test    esi, esi
0x14000e393  jnz     short loc_14000E3B2
0x14000e395  mov     edx, 2710h; dwMilliseconds
0x14000e39a  mov     rcx, cs:hObject; hHandle
0x14000e3a1  call    cs:__imp_WaitForSingleObject
0x14000e3a7  cmp     eax, 102h
0x14000e3ac  jnz     short loc_14000E3B2
0x14000e3ae  mov     [rbp+57h+arg_18], r12d
0x14000e3b2  cmp     cs:?g_areVoiceActivationAndCortanaOnBeforeOrchestratorCreation@@3HA, r12d; int g_areVoiceActivationAndCortanaOnBeforeOrchestratorCreation
0x14000e3b9  jnz     short loc_14000E421
0x14000e3bb  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e3c2  mov     rax, [rcx]
0x14000e3c5  lea     r8, [rbp+57h+arg_8]
0x14000e3c9  lea     rdx, aVoiceactivatio; "VoiceActivationAndCortanaOn"
0x14000e3d0  mov     rax, [rax+20h]
0x14000e3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3d9  mov     edi, eax
0x14000e3db  test    eax, eax
0x14000e3dd  jns     short loc_14000E3E9
0x14000e3df  mov     edx, 254h
0x14000e3e4  jmp     loc_14000E5D8
0x14000e3e9  cmp     [rbp+57h+arg_8], r12d
0x14000e3ed  jz      short loc_14000E41A
0x14000e3ef  mov     esi, 1
0x14000e3f4  mov     [rbp+57h+arg_10], esi
0x14000e3f7  mov     rcx, cs:?g_cpOrchestratorKeywordDetector@@3V?$CComPtr@UISpAudioOrchestratorKeywordDetector@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorKeywordDetector> g_cpOrchestratorKeywordDetector
0x14000e3fe  mov     rax, [rcx]
0x14000e401  mov     rax, [rax+18h]
0x14000e405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e40a  mov     edi, eax
0x14000e40c  test    eax, eax
0x14000e40e  jns     short loc_14000E421
0x14000e410  mov     edx, 259h
0x14000e415  jmp     loc_14000E5D8
0x14000e41a  mov     esi, r12d
0x14000e41d  mov     [rbp+57h+arg_10], r12d
0x14000e421  call    ?Ready@SpeechRuntime@SpPerfTelemetry@@QEAAXXZ; SpPerfTelemetry::SpeechRuntime::Ready(void)
0x14000e426  call    ?SendToastIfNotEnabled@CNotifyVoiceClip@NLInternal@@QEAAJXZ; NLInternal::CNotifyVoiceClip::SendToastIfNotEnabled(void)
0x14000e42b  mov     edi, eax
0x14000e42d  test    eax, eax
0x14000e42f  jns     short loc_14000E43B
0x14000e431  mov     edx, 260h
0x14000e436  jmp     loc_14000E5D8
0x14000e43b  mov     r15d, 1
0x14000e441  mov     edi, [rbp+57h+arg_0]
0x14000e444  cmp     edi, 2
0x14000e447  jnz     short loc_14000E451
0x14000e449  call    cs:__imp_IsDebuggerPresent
0x14000e44f  mov     edi, eax
0x14000e451  mov     rcx, cs:?g_cpOrchestratorInput@@3V?$CComPtr@UISpAudioOrchestratorInput@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorInput> g_cpOrchestratorInput
0x14000e458  mov     rax, [rcx]
0x14000e45b  lea     rdx, [rbp+57h+var_C8]
0x14000e45f  mov     rax, [rax+58h]
0x14000e463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e468  mov     rcx, [rbp+5Fh]; this
0x14000e46c  test    eax, eax
0x14000e46e  jns     short loc_14000E480
0x14000e470  mov     edx, 263h; void *
0x14000e475  mov     r9d, eax; char *
0x14000e478  mov     r8, rbx; unsigned int
0x14000e47b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e480  test    edi, edi
0x14000e482  jnz     short loc_14000E4A7
0x14000e484  test    r15d, r15d
0x14000e487  jz      loc_14000E6A6
0x14000e48d  test    esi, esi
0x14000e48f  jnz     short loc_14000E4A7
0x14000e491  cmp     [rbp+57h+arg_18], r12d
0x14000e495  jnz     short loc_14000E4A7
0x14000e497  cmp     [rbp+57h+var_C4], r12d
0x14000e49b  jnz     short loc_14000E4A7
0x14000e49d  cmp     [rbp+57h+var_C8], r12d
0x14000e4a1  jz      loc_14000E6A6
0x14000e4a7  mov     r14b, 1
0x14000e4aa  or      r8d, 0FFFFFFFFh
0x14000e4ae  mov     eax, 1F4h
0x14000e4b3  cmp     [rbp+57h+arg_0], 2
0x14000e4b7  cmovz   r8d, eax; dwMilliseconds
0x14000e4bb  mov     [rsp+100h+ppv], 2; int
0x14000e4c3  mov     r9d, 1CFFh; dwWakeMask
0x14000e4c9  lea     rdx, ?g_eventHandles@@3PAPEAXA; pHandles
0x14000e4d0  mov     ecx, 0Ah; nCount
0x14000e4d5  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x14000e4db  cmp     eax, 5
0x14000e4de  ja      short loc_14000E54E
0x14000e4e0  jz      short loc_14000E53C
0x14000e4e2  test    eax, eax
0x14000e4e4  jz      short loc_14000E53C
0x14000e4e6  sub     eax, 1
0x14000e4e9  jz      short loc_14000E521
0x14000e4eb  sub     eax, 1
0x14000e4ee  jz      short loc_14000E521
0x14000e4f0  sub     eax, 1
0x14000e4f3  jz      short loc_14000E4FA
0x14000e4f5  cmp     eax, 1
0x14000e4f8  jnz     short loc_14000E570
0x14000e4fa  mov     rcx, cs:?g_cpOrchestratorKeywordDetector@@3V?$CComPtr@UISpAudioOrchestratorKeywordDetector@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorKeywordDetector> g_cpOrchestratorKeywordDetector
0x14000e501  mov     rax, [rcx]
0x14000e504  mov     rax, [rax+18h]
0x14000e508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e50d  mov     edi, eax
0x14000e50f  test    eax, eax
0x14000e511  jns     loc_14000E642
0x14000e517  mov     edx, 274h
0x14000e51c  jmp     loc_14000E5D8
0x14000e521  lea     rcx, [rbp+57h+arg_10]; int *
0x14000e525  call    ?CheckVoiceActivationAndCortanaOnOff@@YAJPEAH@Z; CheckVoiceActivationAndCortanaOnOff(int *)
0x14000e52a  mov     edi, eax
0x14000e52c  test    eax, eax
0x14000e52e  js      loc_14000E6C7
0x14000e534  mov     esi, [rbp+57h+arg_10]
0x14000e537  jmp     loc_14000E642
0x14000e53c  mov     rcx, cs:?g_eventHandles@@3PAPEAXA; hEvent
0x14000e543  call    cs:__imp_ResetEvent
0x14000e549  jmp     loc_14000E642
0x14000e54e  sub     eax, 6
0x14000e551  jz      loc_14000E62B
0x14000e557  sub     eax, 1
0x14000e55a  jz      loc_14000E60C
0x14000e560  sub     eax, 2
0x14000e563  jz      short loc_14000E5AF
0x14000e565  cmp     eax, 0F9h
0x14000e56a  jz      loc_14000E642
0x14000e570  xorps   xmm0, xmm0
0x14000e573  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000e577  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000e57b  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14000e57f  mov     edi, 1
0x14000e584  jmp     short loc_14000E590
0x14000e586  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000e58a  call    cs:__imp_DispatchMessageW
0x14000e590  mov     [rsp+100h+ppv], edi; wRemoveMsg
0x14000e594  xor     r9d, r9d; wMsgFilterMax
0x14000e597  xor     r8d, r8d; wMsgFilterMin
0x14000e59a  xor     edx, edx; hWnd
0x14000e59c  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000e5a0  call    cs:__imp_PeekMessageW
0x14000e5a6  test    eax, eax
0x14000e5a8  jnz     short loc_14000E586
0x14000e5aa  jmp     loc_14000E642
0x14000e5af  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x14000e5b6  mov     rax, [rcx]
0x14000e5b9  lea     r8, [rbp+57h+arg_0]
0x14000e5bd  lea     rdx, aSpeechruntimel; "SpeechRuntimeLifetimeOptions"
0x14000e5c4  mov     rax, [rax+20h]
0x14000e5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5cd  mov     edi, eax
0x14000e5cf  test    eax, eax
0x14000e5d1  jns     short loc_14000E63F
0x14000e5d3  mov     edx, 287h; void *
0x14000e5d8  mov     r8, rbx; unsigned int
0x14000e5db  mov     r9d, eax; char *
0x14000e5de  mov     rcx, [rbp+5Fh]; this
0x14000e5e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e5e7  nop
0x14000e5e8  lea     rcx, [rbp+57h+var_D0]
0x14000e5ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000e5f1  nop
0x14000e5f2  lea     rcx, [rbp+57h+var_C0]
  ... truncated ...
```

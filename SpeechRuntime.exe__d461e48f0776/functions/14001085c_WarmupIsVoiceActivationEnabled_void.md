# WarmupIsVoiceActivationEnabled(void)

- ea: `0x14001085c`
- end: `0x1400109e3`
- name: `?WarmupIsVoiceActivationEnabled@@YAJXZ`
- size: `391`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140011650`

## callees

- `0x140007c0c`
- `0x140008000`
- `0x14000a1b0`
- `0x14001085c`
- `0x1400109ec`
- `0x140010b14`
- `0x140011ea8`
- `0x14001260c`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400108ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400108ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WarmupIsVoiceActivationEnabled(void)
{
  SpPerfTelemetry::SpeechRuntime *v0; // rcx
  SpPerfTelemetry::SpeechRuntime *v1; // rcx
  HRESULT v2; // ebx
  int v3; // eax
  _BYTE v5[88]; // [rsp+30h] [rbp-58h] BYREF
  int v6; // [rsp+90h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+10h] BYREF

  SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(&g_telemetry, v5);
  SpPerfTelemetry::SpeechRuntime::WarmupIsVoiceActivationEnabled_Enter(v0);
  ppv = 0;
  v2 = CoCreateInstance(&CLSID_SpVAEngineModel, 0, 0x17u, &GUID_1ef9e8e7_e32c_4466_9bba_a962ea1f0d94, &ppv);
  if ( v2 >= 0 )
  {
    v6 = 0;
    v3 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, int *))(*(_QWORD *)g_cpOrchestratorPolicy + 32LL))(
           g_cpOrchestratorPolicy,
           L"SoftwareSpeakerIDInSKU",
           &v6);
    if ( v3 < 0 )
      DoTraceMessage(
        2,
        "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"WarmupIsVoiceActivationEnabled",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp(304)",
        v3);
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, bool))(*(_QWORD *)ppv + 24LL))(ppv, 1, v6 != 0);
  }
  if ( v2 == -2147200942 )
  {
    (*(void (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)g_cpOrchestratorPolicy + 48LL))(
      g_cpOrchestratorPolicy,
      L"HardwareKeywordDetectorTypeSupported",
      0);
    SpLogEvent("WarmupIsVoiceActivationEnabled", 2u, L"Voice Activation - Unsupported hardware offload language");
    DoTraceMessage(8, "Hardware Voice Activation - Language Unsupported");
  }
  else if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 80LL))(ppv);
  }
  SpPerfTelemetry::SpeechRuntime::WarmupIsVoiceActivationEnabled_Exit(v1, v2);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&ppv);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001085c  mov     [rsp+arg_10], rbx
0x140010861  push    rsi
0x140010862  sub     rsp, 80h
0x140010869  lea     rdx, [rsp+88h+var_58]
0x14001086e  lea     rcx, ?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x140010875  call    ?ContinueActivityOnCurrentThread@SpeechRuntime@SpPerfTelemetry@@UEAA?AVActivityThreadWatcher@wil@@XZ; SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(void)
0x14001087a  nop
0x14001087b  call    ?WarmupIsVoiceActivationEnabled_Enter@SpeechRuntime@SpPerfTelemetry@@QEAAXXZ; SpPerfTelemetry::SpeechRuntime::WarmupIsVoiceActivationEnabled_Enter(void)
0x140010880  mov     [rsp+88h+arg_8], 0
0x14001088c  lea     rax, [rsp+88h+arg_8]
0x140010894  mov     [rsp+88h+ppv], rax; ppv
0x140010899  lea     r9, _GUID_1ef9e8e7_e32c_4466_9bba_a962ea1f0d94; riid
0x1400108a0  xor     edx, edx; pUnkOuter
0x1400108a2  lea     r8d, [rdx+17h]; dwClsContext
0x1400108a6  lea     rcx, CLSID_SpVAEngineModel; rclsid
0x1400108ad  call    cs:__imp_CoCreateInstance
0x1400108b3  mov     ebx, eax
0x1400108b5  mov     esi, 2
0x1400108ba  test    eax, eax
0x1400108bc  js      loc_140010949
0x1400108c2  mov     [rsp+88h+arg_0], 0
0x1400108cd  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x1400108d4  mov     rax, [rcx]
0x1400108d7  lea     r8, [rsp+88h+arg_0]
0x1400108df  lea     rdx, aSoftwarespeake; "SoftwareSpeakerIDInSKU"
0x1400108e6  mov     rax, [rax+20h]
0x1400108ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108ef  test    eax, eax
0x1400108f1  jns     short loc_14001091F
0x1400108f3  mov     [rsp+88h+var_60], eax
0x1400108f7  lea     rax, aOnecoreuapEndu_8; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x1400108fe  mov     [rsp+88h+ppv], rax
0x140010903  lea     r9, aWarmupisvoicea; "WarmupIsVoiceActivationEnabled"
0x14001090a  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x140010911  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x140010918  mov     ecx, esi; int
0x14001091a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001091f  xor     r8d, r8d
0x140010922  cmp     [rsp+88h+arg_0], r8d
0x14001092a  setnz   r8b
0x14001092e  mov     rcx, [rsp+88h+arg_8]
0x140010936  mov     rax, [rcx]
0x140010939  mov     edx, 1
0x14001093e  mov     rax, [rax+18h]
0x140010942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010947  mov     ebx, eax
0x140010949  cmp     ebx, 80045052h
0x14001094f  jnz     short loc_140010996
0x140010951  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x140010958  mov     rax, [rcx]
0x14001095b  xor     r8d, r8d
0x14001095e  lea     rdx, aHardwarekeywor; "HardwareKeywordDetectorTypeSupported"
0x140010965  mov     rax, [rax+30h]
0x140010969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001096e  lea     r8, aVoiceActivatio; "Voice Activation - Unsupported hardware"...
0x140010975  mov     edx, esi; unsigned __int16
0x140010977  lea     rcx, aWarmupisvoicea_0; "WarmupIsVoiceActivationEnabled"
0x14001097e  call    ?SpLogEvent@@YAXPEBDGPEBGZZ; SpLogEvent(char const *,ushort,ushort const *,...)
0x140010983  lea     rdx, aHardwareVoiceA; "Hardware Voice Activation - Language Un"...
0x14001098a  mov     ecx, 8; int
0x14001098f  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x140010994  jmp     short loc_1400109B0
0x140010996  test    ebx, ebx
0x140010998  js      short loc_1400109B0
0x14001099a  mov     rcx, [rsp+88h+arg_8]
0x1400109a2  mov     rax, [rcx]
0x1400109a5  mov     rax, [rax+50h]
0x1400109a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109ae  mov     ebx, eax
0x1400109b0  mov     edx, ebx; int
0x1400109b2  call    ?WarmupIsVoiceActivationEnabled_Exit@SpeechRuntime@SpPerfTelemetry@@QEAAXJ@Z; SpPerfTelemetry::SpeechRuntime::WarmupIsVoiceActivationEnabled_Exit(long)
0x1400109b7  nop
0x1400109b8  lea     rcx, [rsp+88h+arg_8]
0x1400109c0  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1400109c5  nop
0x1400109c6  lea     rcx, [rsp+88h+var_58]; this
0x1400109cb  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1400109d0  mov     eax, ebx
0x1400109d2  mov     rbx, [rsp+88h+arg_10]
0x1400109da  add     rsp, 80h
0x1400109e1  pop     rsi
0x1400109e2  retn
```

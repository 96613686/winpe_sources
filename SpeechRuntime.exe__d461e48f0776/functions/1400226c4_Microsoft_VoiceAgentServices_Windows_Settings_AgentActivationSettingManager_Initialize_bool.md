# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize(bool)

- ea: `0x1400226c4`
- end: `0x140022877`
- name: `?Initialize@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAJ_N@Z`
- size: `435`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__hidden this, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400220a8`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140020f34`
- `0x140020ff0`
- `0x140021658`
- `0x140021a4c`
- `0x1400226c4`
- `0x140022880`
- `0x14002302c`
- `0x140023120`
- `0x140023438`
- `0x140031010`

## string_xrefs

- `0x14002270f`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x14002279b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x14002280f`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x1400226fe`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize`
- `0x1400227fb`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r14
  void (__fastcall *v8)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD); // rsi
  int v9; // r8d
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  _BYTE v14[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v16[40]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v17[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v16,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize");
  std::string::string(
    v15,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v3(v2, v15, v16, 183);
  std::string::~string(v15);
  std::string::~string(v16);
  wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v17);
  v17[0] = &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::`vftable';
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::StartActivity((Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize *)v17);
  v4 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting(this);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents(this);
    v5 = v4;
    if ( v4 >= 0 )
    {
      *((_BYTE *)this + 369) = 1;
      wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
      v7 = *((_QWORD *)this + 47);
      v8 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD))(*(_QWORD *)v7 + 72LL);
      v10 = std::string::string(v16, "hr = 0x%x", v9);
      v11 = std::string::string(
              v15,
              "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize");
      v12 = std::string::string(
              v14,
              "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
      v8(v7, v12, v11, 197, v10, this, 0);
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 192;
  }
  else
  {
    v6 = 186;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
    (const char *)(unsigned int)v4,
    (int)this);
LABEL_7:
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::~AgentActivationSettingManagerInitialize((Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize *)v17);
  return v5;
}

```

## disassembly

```asm
0x1400226c4  push    rbp
0x1400226c6  push    rbx
0x1400226c7  push    rsi
0x1400226c8  push    rdi
0x1400226c9  push    r14
0x1400226cb  push    r15
0x1400226cd  lea     rbp, [rsp-128h]
0x1400226d5  sub     rsp, 228h
0x1400226dc  mov     rax, cs:__security_cookie
0x1400226e3  xor     rax, rsp
0x1400226e6  mov     [rbp+150h+var_40], rax
0x1400226ed  mov     r15, rcx
0x1400226f0  mov     rdi, [rcx+178h]
0x1400226f7  mov     rax, [rdi]
0x1400226fa  mov     rbx, [rax+28h]
0x1400226fe  lea     rdx, aMicrosoftVoice_14; "Microsoft::VoiceAgentServices::Windows:"...
0x140022705  lea     rcx, [rbp+150h+var_1B8]
0x140022709  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002270e  nop
0x14002270f  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140022716  lea     rcx, [rsp+250h+var_1D8]
0x14002271b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022720  nop
0x140022721  mov     qword ptr [rsp+250h+var_230], r15; int
0x140022726  mov     r9d, 0B7h
0x14002272c  lea     r8, [rbp+150h+var_1B8]
0x140022730  lea     rdx, [rsp+250h+var_1D8]
0x140022735  mov     rcx, rdi
0x140022738  mov     rax, rbx
0x14002273b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022740  nop
0x140022741  lea     rcx, [rsp+250h+var_1D8]
0x140022746  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002274b  nop
0x14002274c  lea     rcx, [rbp+150h+var_1B8]
0x140022750  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140022755  lea     rcx, [rbp+150h+var_190]; struct wil::details::IFailureCallback *
0x140022759  call    ??0?$ActivityBase@VAgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14002275e  lea     rax, ??_7AgentActivationSettingManagerInitialize@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::`vftable'
0x140022765  mov     [rbp+150h+var_190], rax
0x140022769  lea     rcx, [rbp+150h+var_190]; this
0x14002276d  call    ?StartActivity@AgentActivationSettingManagerInitialize@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAXXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::StartActivity(void)
0x140022772  nop
0x140022773  mov     rcx, r15; this
0x140022776  call    ?InitializeAllAgentsActivationSetting@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting(void)
0x14002277b  mov     ebx, eax
0x14002277d  test    eax, eax
0x14002277f  jns     short loc_140022788
0x140022781  mov     edx, 0BAh
0x140022786  jmp     short loc_14002279B
0x140022788  mov     rcx, r15; this
0x14002278b  call    ?SubscribeForSystemEvents@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents(void)
0x140022790  mov     ebx, eax
0x140022792  test    eax, eax
0x140022794  jns     short loc_1400227B6
0x140022796  mov     edx, 0C0h; void *
0x14002279b  lea     r8, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400227a2  mov     r9d, eax; char *
0x1400227a5  mov     rcx, [rbp+158h]; this
0x1400227ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400227b1  jmp     loc_14002284D
0x1400227b6  mov     byte ptr [r15+171h], 1
0x1400227be  lea     rcx, [rbp+150h+var_190]
0x1400227c2  call    ?Stop@?$ActivityBase@VAgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400227c7  mov     r14, [r15+178h]
0x1400227ce  mov     rax, [r14]
0x1400227d1  mov     rsi, [rax+48h]
0x1400227d5  lea     rax, [rbp+150h+var_1B8]
0x1400227d9  mov     [rsp+250h+var_210], rax
0x1400227de  lea     rdx, aHr0xX; "hr = 0x%x"
0x1400227e5  lea     rcx, [rbp+150h+var_1B8]
0x1400227e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400227ee  mov     rdi, rax
0x1400227f1  lea     rax, [rsp+250h+var_1D8]
0x1400227f6  mov     [rsp+250h+var_208], rax
0x1400227fb  lea     rdx, aMicrosoftVoice_14; "Microsoft::VoiceAgentServices::Windows:"...
0x140022802  lea     rcx, [rsp+250h+var_1D8]
0x140022807  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002280c  mov     rbx, rax
0x14002280f  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140022816  lea     rcx, [rsp+250h+var_1F8]
0x14002281b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022820  nop
0x140022821  mov     [rsp+250h+var_220], 0
0x14002282a  mov     [rsp+250h+var_228], r15
0x14002282f  mov     qword ptr [rsp+250h+var_230], rdi
0x140022834  mov     r9d, 0C5h
0x14002283a  mov     r8, rbx
0x14002283d  mov     rdx, rax
0x140022840  mov     rcx, r14
0x140022843  mov     rax, rsi
0x140022846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002284b  xor     ebx, ebx
0x14002284d  lea     rcx, [rbp+150h+var_190]; this
0x140022851  call    ??1AgentActivationSettingManagerInitialize@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@QEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::~AgentActivationSettingManagerInitialize(void)
0x140022856  mov     eax, ebx
0x140022858  mov     rcx, [rbp+150h+var_40]
0x14002285f  xor     rcx, rsp; StackCookie
0x140022862  call    __security_check_cookie
0x140022867  add     rsp, 228h
0x14002286e  pop     r15
0x140022870  pop     r14
0x140022872  pop     rdi
0x140022873  pop     rsi
0x140022874  pop     rbx
0x140022875  pop     rbp
0x140022876  retn
```

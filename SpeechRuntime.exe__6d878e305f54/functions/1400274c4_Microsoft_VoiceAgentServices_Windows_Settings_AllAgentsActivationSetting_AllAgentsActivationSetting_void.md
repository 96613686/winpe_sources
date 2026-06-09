# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::~AllAgentsActivationSetting(void)

- ea: `0x1400274c4`
- end: `0x140027595`
- name: `??1AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@UEAA@XZ`
- size: `209`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400275b0`

## callees

- `0x140020ff0`
- `0x140028724`
- `0x140031010`

## string_xrefs

- `0x140027508`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027557`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x1400274f4`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::~AllAgentsActivationSetting`
- `0x140027543`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::~AllAgentsActivationSetting`

## pseudocode

```c
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::~AllAgentsActivationSetting(
        Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *this)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v10[32]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v11[72]; // [rsp+50h] [rbp-48h] BYREF

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'};
  *((_QWORD *)this + 1) = &Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'};
  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v2 + 96LL);
  v4 = std::string::string(
         v10,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::~AllAgentsActivationSetting");
  v5 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v3(v2, v5, v4, 19, this);
  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v6 + 104LL);
  v8 = std::string::string(
         v11,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::~AllAgentsActivationSetting");
  v9 = std::string::string(
         v10,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v7(v6, v9, v8, 20, this);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase(this);
}

```

## disassembly

```asm
0x1400274c4  push    rbx
0x1400274c6  push    rsi
0x1400274c7  push    rdi
0x1400274c8  push    r14
0x1400274ca  sub     rsp, 78h
0x1400274ce  mov     r14, rcx
0x1400274d1  lea     rax, ??_7AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSettingView@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'}
0x1400274d8  mov     [rcx], rax
0x1400274db  lea     rax, ??_7AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSetting@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'}
0x1400274e2  mov     [rcx+8], rax
0x1400274e6  mov     rsi, [rcx+178h]
0x1400274ed  mov     rax, [rsi]
0x1400274f0  mov     rdi, [rax+60h]
0x1400274f4  lea     rdx, aMicrosoftVoice_9; "Microsoft::VoiceAgentServices::Windows:"...
0x1400274fb  lea     rcx, [rsp+98h+var_68]
0x140027500  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027505  mov     rbx, rax
0x140027508  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002750f  lea     rcx, [rsp+98h+var_48]
0x140027514  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027519  mov     [rsp+98h+var_78], r14
0x14002751e  mov     r9d, 13h
0x140027524  mov     r8, rbx
0x140027527  mov     rdx, rax
0x14002752a  mov     rcx, rsi
0x14002752d  mov     rax, rdi
0x140027530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027535  mov     rsi, [r14+178h]
0x14002753c  mov     rax, [rsi]
0x14002753f  mov     rdi, [rax+68h]
0x140027543  lea     rdx, aMicrosoftVoice_9; "Microsoft::VoiceAgentServices::Windows:"...
0x14002754a  lea     rcx, [rsp+98h+var_48]
0x14002754f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027554  mov     rbx, rax
0x140027557  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002755e  lea     rcx, [rsp+98h+var_68]
0x140027563  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027568  mov     [rsp+98h+var_78], r14
0x14002756d  mov     r9d, 14h
0x140027573  mov     r8, rbx
0x140027576  mov     rdx, rax
0x140027579  mov     rcx, rsi
0x14002757c  mov     rax, rdi
0x14002757f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027584  mov     rcx, r14; this
0x140027587  add     rsp, 78h
0x14002758b  pop     r14
0x14002758d  pop     rdi
0x14002758e  pop     rsi
0x14002758f  pop     rbx
0x140027590  jmp     ??1AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase(void)
```

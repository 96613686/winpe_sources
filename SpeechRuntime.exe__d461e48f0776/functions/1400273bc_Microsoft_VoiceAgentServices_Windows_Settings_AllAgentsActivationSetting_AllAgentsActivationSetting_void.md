# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting(void)

- ea: `0x1400273bc`
- end: `0x1400274bb`
- name: `??0AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ`
- size: `255`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400275ec`

## callees

- `0x140020ff0`
- `0x1400285bc`
- `0x140031010`

## string_xrefs

- `0x140027407`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting`
- `0x140027464`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting`
- `0x14002741b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027478`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *__fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting(
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
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v12[56]; // [rsp+50h] [rbp-38h] BYREF

  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase(this);
  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'};
  *((_QWORD *)this + 1) = &Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'};
  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v2 + 80LL);
  v4 = std::string::string(
         v11,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting");
  v5 = std::string::string(
         v12,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v3(v2, v5, v4, 13, this);
  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v6 + 88LL);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v7(v6, v9, v8, 14, this);
  return this;
}

```

## disassembly

```asm
0x1400273bc  mov     [rsp+arg_18], rbx
0x1400273c1  mov     [rsp+arg_0], rcx
0x1400273c6  push    rsi
0x1400273c7  push    rdi
0x1400273c8  push    r14
0x1400273ca  sub     rsp, 70h
0x1400273ce  mov     r14, rcx
0x1400273d1  call    ??0AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@IEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase(void)
0x1400273d6  nop
0x1400273d7  lea     rax, ??_7AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSettingView@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'}
0x1400273de  mov     [r14], rax
0x1400273e1  lea     rax, ??_7AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSetting@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'}
0x1400273e8  mov     [r14+8], rax
0x1400273ec  mov     rsi, [r14+178h]
0x1400273f3  mov     rax, [rsi]
0x1400273f6  mov     rdi, [rax+50h]
0x1400273fa  lea     rax, [rsp+88h+var_58]
0x1400273ff  mov     [rsp+88h+arg_8], rax
0x140027407  lea     rdx, aMicrosoftVoice_10; "Microsoft::VoiceAgentServices::Windows:"...
0x14002740e  lea     rcx, [rsp+88h+var_58]
0x140027413  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027418  mov     rbx, rax
0x14002741b  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027422  lea     rcx, [rsp+88h+var_38]
0x140027427  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002742c  nop
0x14002742d  mov     [rsp+88h+var_68], r14
0x140027432  mov     r9d, 0Dh
0x140027438  mov     r8, rbx
0x14002743b  mov     rdx, rax
0x14002743e  mov     rcx, rsi
0x140027441  mov     rax, rdi
0x140027444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027449  mov     rsi, [r14+178h]
0x140027450  mov     rax, [rsi]
0x140027453  mov     rdi, [rax+58h]
0x140027457  lea     rax, [rsp+88h+var_38]
0x14002745c  mov     [rsp+88h+arg_8], rax
0x140027464  lea     rdx, aMicrosoftVoice_10; "Microsoft::VoiceAgentServices::Windows:"...
0x14002746b  lea     rcx, [rsp+88h+var_38]
0x140027470  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027475  mov     rbx, rax
0x140027478  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002747f  lea     rcx, [rsp+88h+var_58]
0x140027484  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027489  nop
0x14002748a  mov     [rsp+88h+var_68], r14
0x14002748f  mov     r9d, 0Eh
0x140027495  mov     r8, rbx
0x140027498  mov     rdx, rax
0x14002749b  mov     rcx, rsi
0x14002749e  mov     rax, rdi
0x1400274a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400274a6  nop
0x1400274a7  mov     rax, r14
0x1400274aa  mov     rbx, [rsp+88h+arg_18]
0x1400274b2  add     rsp, 70h
0x1400274b6  pop     r14
0x1400274b8  pop     rdi
0x1400274b9  pop     rsi
0x1400274ba  retn
```

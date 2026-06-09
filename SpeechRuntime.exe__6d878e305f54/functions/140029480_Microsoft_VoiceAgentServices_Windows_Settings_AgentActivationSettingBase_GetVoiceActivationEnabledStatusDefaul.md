# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusDefault(void)

- ea: `0x140029480`
- end: `0x1400295ca`
- name: `?GetVoiceActivationEnabledStatusDefault@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAA_NXZ`
- size: `330`
- prototype: `bool __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140028e08`
- `0x140031010`

## string_xrefs

- `0x1400294ce`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029568`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x1400294bd`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusDefault`
- `0x140029555`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusDefault`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusDefault(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  BOOL EnabledStatusFromHint; // r15d
  __int64 v5; // r14
  void (__fastcall *v6)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL); // rsi
  int v7; // r8d
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  _BYTE v12[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v14[32]; // [rsp+98h] [rbp+Fh] BYREF

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v14,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusDefault");
  std::string::string(
    v13,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v13, v14, 417, this);
  std::string::~string(v13);
  std::string::~string(v14);
  EnabledStatusFromHint = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint(
                            (__int64)this,
                            *((_DWORD *)this + 42));
  v5 = *((_QWORD *)this + 47);
  v6 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL))(*(_QWORD *)v5 + 72LL);
  v8 = std::string::string(v14, "status = %d", v7);
  v9 = std::string::string(
         v13,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusDefault");
  v10 = std::string::string(
          v12,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v6(v5, v10, v9, 419, v8, this, EnabledStatusFromHint);
  return EnabledStatusFromHint;
}

```

## disassembly

```asm
0x140029480  mov     [rsp-8+arg_8], rbx
0x140029485  mov     [rsp-8+arg_10], rsi
0x14002948a  push    rbp
0x14002948b  push    rdi
0x14002948c  push    r13
0x14002948e  push    r14
0x140029490  push    r15
0x140029492  lea     rbp, [rsp-37h]
0x140029497  sub     rsp, 0C0h
0x14002949e  mov     rax, cs:__security_cookie
0x1400294a5  xor     rax, rsp
0x1400294a8  mov     [rbp+57h+var_28], rax
0x1400294ac  mov     r13, rcx
0x1400294af  mov     rdi, [rcx+178h]
0x1400294b6  mov     rax, [rdi]
0x1400294b9  mov     rbx, [rax+28h]
0x1400294bd  lea     rdx, aMicrosoftVoice_47; "Microsoft::VoiceAgentServices::Windows:"...
0x1400294c4  lea     rcx, [rbp+57h+var_48]
0x1400294c8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400294cd  nop
0x1400294ce  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400294d5  lea     rcx, [rbp+57h+var_68]
0x1400294d9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400294de  nop
0x1400294df  mov     [rsp+0E0h+var_C0], r13
0x1400294e4  mov     r9d, 1A1h
0x1400294ea  lea     r8, [rbp+57h+var_48]
0x1400294ee  lea     rdx, [rbp+57h+var_68]
0x1400294f2  mov     rcx, rdi
0x1400294f5  mov     rax, rbx
0x1400294f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400294fd  nop
0x1400294fe  lea     rcx, [rbp+57h+var_68]
0x140029502  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029507  nop
0x140029508  lea     rcx, [rbp+57h+var_48]
0x14002950c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029511  mov     edx, [r13+0A8h]
0x140029518  mov     rcx, r13
0x14002951b  call    ?GetEnabledStatusFromHint@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA_NW4AgentConfigurationSettingDefaultHint@2345@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint(Microsoft::VoiceAgentServices::Windows::Settings::AgentConfigurationSettingDefaultHint)
0x140029520  movzx   r15d, al
0x140029524  mov     r14, [r13+178h]
0x14002952b  mov     rcx, [r14]
0x14002952e  mov     rsi, [rcx+48h]
0x140029532  lea     rax, [rbp+57h+var_48]
0x140029536  mov     [rbp+57h+var_A0], rax
0x14002953a  lea     rdx, aStatusD; "status = %d"
0x140029541  lea     rcx, [rbp+57h+var_48]
0x140029545  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002954a  mov     rdi, rax
0x14002954d  lea     rax, [rbp+57h+var_68]
0x140029551  mov     [rbp+57h+var_98], rax
0x140029555  lea     rdx, aMicrosoftVoice_47; "Microsoft::VoiceAgentServices::Windows:"...
0x14002955c  lea     rcx, [rbp+57h+var_68]
0x140029560  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029565  mov     rbx, rax
0x140029568  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002956f  lea     rcx, [rbp+57h+var_88]
0x140029573  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029578  nop
0x140029579  mov     [rsp+0E0h+var_B0], r15d
0x14002957e  mov     [rsp+0E0h+var_B8], r13
0x140029583  mov     [rsp+0E0h+var_C0], rdi
0x140029588  mov     r9d, 1A3h
0x14002958e  mov     r8, rbx
0x140029591  mov     rdx, rax
0x140029594  mov     rcx, r14
0x140029597  mov     rax, rsi
0x14002959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002959f  mov     al, r15b
0x1400295a2  mov     rcx, [rbp+57h+var_28]
0x1400295a6  xor     rcx, rsp; StackCookie
0x1400295a9  call    __security_check_cookie
0x1400295ae  lea     r11, [rsp+0E0h+var_20]
0x1400295b6  mov     rbx, [r11+38h]
0x1400295ba  mov     rsi, [r11+40h]
0x1400295be  mov     rsp, r11
0x1400295c1  pop     r15
0x1400295c3  pop     r14
0x1400295c5  pop     r13
0x1400295c7  pop     rdi
0x1400295c8  pop     rbp
0x1400295c9  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusDefault(void)

- ea: `0x140029c00`
- end: `0x140029d24`
- name: `?GetVoiceActivationLastUsedEnabledStatusDefault@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAA_NXZ`
- size: `292`
- prototype: `bool __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140031010`

## string_xrefs

- `0x140029c45`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029ccc`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029c34`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusDefault`
- `0x140029cb9`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusDefault`

## pseudocode

```c
char __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusDefault(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  __int64 v4; // r14
  void (__fastcall *v5)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, int); // rsi
  int v6; // r8d
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v11[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v12[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v13[32]; // [rsp+98h] [rbp-1h] BYREF

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v13,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusDefault");
  std::string::string(
    v12,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v12, v13, 454, this);
  std::string::~string(v12);
  std::string::~string(v13);
  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, int))(*(_QWORD *)v4 + 72LL);
  v7 = std::string::string(v13, "enabled = %d", v6);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusDefault");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v9, v8, 456, v7, this, 1);
  return 1;
}

```

## disassembly

```asm
0x140029c00  push    rbp
0x140029c02  push    rbx
0x140029c03  push    rsi
0x140029c04  push    rdi
0x140029c05  push    r14
0x140029c07  push    r15
0x140029c09  lea     rbp, [rsp-2Fh]
0x140029c0e  sub     rsp, 0C8h
0x140029c15  mov     rax, cs:__security_cookie
0x140029c1c  xor     rax, rsp
0x140029c1f  mov     [rbp+57h+var_38], rax
0x140029c23  mov     r15, rcx
0x140029c26  mov     rdi, [rcx+178h]
0x140029c2d  mov     rax, [rdi]
0x140029c30  mov     rbx, [rax+28h]
0x140029c34  lea     rdx, aMicrosoftVoice_26; "Microsoft::VoiceAgentServices::Windows:"...
0x140029c3b  lea     rcx, [rbp+57h+var_58]
0x140029c3f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029c44  nop
0x140029c45  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029c4c  lea     rcx, [rbp+57h+var_78]
0x140029c50  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029c55  nop
0x140029c56  mov     [rsp+0F0h+var_D0], r15
0x140029c5b  mov     r9d, 1C6h
0x140029c61  lea     r8, [rbp+57h+var_58]
0x140029c65  lea     rdx, [rbp+57h+var_78]
0x140029c69  mov     rcx, rdi
0x140029c6c  mov     rax, rbx
0x140029c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029c74  nop
0x140029c75  lea     rcx, [rbp+57h+var_78]
0x140029c79  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029c7e  nop
0x140029c7f  lea     rcx, [rbp+57h+var_58]
0x140029c83  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029c88  mov     r14, [r15+178h]
0x140029c8f  mov     rax, [r14]
0x140029c92  mov     rsi, [rax+48h]
0x140029c96  lea     rax, [rbp+57h+var_58]
0x140029c9a  mov     [rbp+57h+var_B0], rax
0x140029c9e  lea     rdx, aEnabledD; "enabled = %d"
0x140029ca5  lea     rcx, [rbp+57h+var_58]
0x140029ca9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029cae  mov     rdi, rax
0x140029cb1  lea     rax, [rbp+57h+var_78]
0x140029cb5  mov     [rbp+57h+var_A8], rax
0x140029cb9  lea     rdx, aMicrosoftVoice_26; "Microsoft::VoiceAgentServices::Windows:"...
0x140029cc0  lea     rcx, [rbp+57h+var_78]
0x140029cc4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029cc9  mov     rbx, rax
0x140029ccc  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029cd3  lea     rcx, [rbp+57h+var_98]
0x140029cd7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029cdc  nop
0x140029cdd  mov     [rsp+0F0h+var_C0], 1
0x140029ce5  mov     [rsp+0F0h+var_C8], r15
0x140029cea  mov     [rsp+0F0h+var_D0], rdi
0x140029cef  mov     r9d, 1C8h
0x140029cf5  mov     r8, rbx
0x140029cf8  mov     rdx, rax
0x140029cfb  mov     rcx, r14
0x140029cfe  mov     rax, rsi
0x140029d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029d06  mov     al, 1
0x140029d08  mov     rcx, [rbp+57h+var_38]
0x140029d0c  xor     rcx, rsp; StackCookie
0x140029d0f  call    __security_check_cookie
0x140029d14  add     rsp, 0C8h
0x140029d1b  pop     r15
0x140029d1d  pop     r14
0x140029d1f  pop     rdi
0x140029d20  pop     rsi
0x140029d21  pop     rbx
0x140029d22  pop     rbp
0x140029d23  retn
```

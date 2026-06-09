# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusDefault(void)

- ea: `0x14002a8b0`
- end: `0x14002a9d4`
- name: `?GetVoiceActivationOnLockScreenSupportedStatusDefault@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAA_NXZ`
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

- `0x14002a8f5`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a97c`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a8e4`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusDefault`
- `0x14002a969`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusDefault`

## pseudocode

```c
char __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusDefault(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusDefault");
  std::string::string(
    v12,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v12, v13, 431, this);
  std::string::~string(v12);
  std::string::~string(v13);
  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, int))(*(_QWORD *)v4 + 72LL);
  v7 = std::string::string(v13, "status = %d", v6);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSup"
         "portedStatusDefault");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v9, v8, 433, v7, this, 1);
  return 1;
}

```

## disassembly

```asm
0x14002a8b0  push    rbp
0x14002a8b2  push    rbx
0x14002a8b3  push    rsi
0x14002a8b4  push    rdi
0x14002a8b5  push    r14
0x14002a8b7  push    r15
0x14002a8b9  lea     rbp, [rsp-2Fh]
0x14002a8be  sub     rsp, 0C8h
0x14002a8c5  mov     rax, cs:__security_cookie
0x14002a8cc  xor     rax, rsp
0x14002a8cf  mov     [rbp+57h+var_38], rax
0x14002a8d3  mov     r15, rcx
0x14002a8d6  mov     rdi, [rcx+178h]
0x14002a8dd  mov     rax, [rdi]
0x14002a8e0  mov     rbx, [rax+28h]
0x14002a8e4  lea     rdx, aMicrosoftVoice_50; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a8eb  lea     rcx, [rbp+57h+var_58]
0x14002a8ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a8f4  nop
0x14002a8f5  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a8fc  lea     rcx, [rbp+57h+var_78]
0x14002a900  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a905  nop
0x14002a906  mov     [rsp+0F0h+var_D0], r15
0x14002a90b  mov     r9d, 1AFh
0x14002a911  lea     r8, [rbp+57h+var_58]
0x14002a915  lea     rdx, [rbp+57h+var_78]
0x14002a919  mov     rcx, rdi
0x14002a91c  mov     rax, rbx
0x14002a91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a924  nop
0x14002a925  lea     rcx, [rbp+57h+var_78]
0x14002a929  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a92e  nop
0x14002a92f  lea     rcx, [rbp+57h+var_58]
0x14002a933  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a938  mov     r14, [r15+178h]
0x14002a93f  mov     rax, [r14]
0x14002a942  mov     rsi, [rax+48h]
0x14002a946  lea     rax, [rbp+57h+var_58]
0x14002a94a  mov     [rbp+57h+var_B0], rax
0x14002a94e  lea     rdx, aStatusD; "status = %d"
0x14002a955  lea     rcx, [rbp+57h+var_58]
0x14002a959  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a95e  mov     rdi, rax
0x14002a961  lea     rax, [rbp+57h+var_78]
0x14002a965  mov     [rbp+57h+var_A8], rax
0x14002a969  lea     rdx, aMicrosoftVoice_50; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a970  lea     rcx, [rbp+57h+var_78]
0x14002a974  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a979  mov     rbx, rax
0x14002a97c  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a983  lea     rcx, [rbp+57h+var_98]
0x14002a987  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a98c  nop
0x14002a98d  mov     [rsp+0F0h+var_C0], 1
0x14002a995  mov     [rsp+0F0h+var_C8], r15
0x14002a99a  mov     [rsp+0F0h+var_D0], rdi
0x14002a99f  mov     r9d, 1B1h
0x14002a9a5  mov     r8, rbx
0x14002a9a8  mov     rdx, rax
0x14002a9ab  mov     rcx, r14
0x14002a9ae  mov     rax, rsi
0x14002a9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a9b6  mov     al, 1
0x14002a9b8  mov     rcx, [rbp+57h+var_38]
0x14002a9bc  xor     rcx, rsp; StackCookie
0x14002a9bf  call    __security_check_cookie
0x14002a9c4  add     rsp, 0C8h
0x14002a9cb  pop     r15
0x14002a9cd  pop     r14
0x14002a9cf  pop     rdi
0x14002a9d0  pop     rsi
0x14002a9d1  pop     rbx
0x14002a9d2  pop     rbp
0x14002a9d3  retn
```

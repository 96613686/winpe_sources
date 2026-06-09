# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::InitializeInternal(void)

- ea: `0x14002b1a0`
- end: `0x14002b2ea`
- name: `?InitializeInternal@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJXZ`
- size: `330`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14001296c`
- `0x140020ff0`
- `0x140021658`
- `0x140021b80`
- `0x140025630`
- `0x140031010`

## string_xrefs

- `0x14002b1e5`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b291`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b1d4`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::InitializeInternal`
- `0x14002b27e`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::InitializeInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::InitializeInternal(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  __int64 RegistryConfigurationPath; // rax
  __int64 v5; // r14
  void (__fastcall *v6)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v7; // r8d
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  _BYTE v12[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v14[32]; // [rsp+98h] [rbp-1h] BYREF

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v13,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::InitializeInternal");
  std::string::string(
    v14,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v14, v13, 587, this);
  std::string::~string(v14);
  std::string::~string(v13);
  RegistryConfigurationPath = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(
                                v13,
                                (char *)this + 32);
  std::wstring::operator=((char *)this + 272, RegistryConfigurationPath);
  std::wstring::~wstring(v13);
  v5 = *((_QWORD *)this + 47);
  v6 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v5 + 72LL);
  v8 = std::string::string(v13, "hr = 0x%x", v7);
  v9 = std::string::string(
         v14,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::InitializeInternal");
  v10 = std::string::string(
          v12,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v6(v5, v10, v9, 589, v8, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002b1a0  push    rbp
0x14002b1a2  push    rbx
0x14002b1a3  push    rsi
0x14002b1a4  push    rdi
0x14002b1a5  push    r14
0x14002b1a7  push    r15
0x14002b1a9  lea     rbp, [rsp-2Fh]
0x14002b1ae  sub     rsp, 0C8h
0x14002b1b5  mov     rax, cs:__security_cookie
0x14002b1bc  xor     rax, rsp
0x14002b1bf  mov     [rbp+57h+var_38], rax
0x14002b1c3  mov     r15, rcx
0x14002b1c6  mov     rdi, [rcx+178h]
0x14002b1cd  mov     rax, [rdi]
0x14002b1d0  mov     rbx, [rax+28h]
0x14002b1d4  lea     rdx, aMicrosoftVoice_2; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b1db  lea     rcx, [rbp+57h+var_78]
0x14002b1df  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b1e4  nop
0x14002b1e5  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b1ec  lea     rcx, [rbp+57h+var_58]
0x14002b1f0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b1f5  nop
0x14002b1f6  mov     [rsp+0F0h+var_D0], r15
0x14002b1fb  mov     r9d, 24Bh
0x14002b201  lea     r8, [rbp+57h+var_78]
0x14002b205  lea     rdx, [rbp+57h+var_58]
0x14002b209  mov     rcx, rdi
0x14002b20c  mov     rax, rbx
0x14002b20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b214  nop
0x14002b215  lea     rcx, [rbp+57h+var_58]
0x14002b219  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b21e  nop
0x14002b21f  lea     rcx, [rbp+57h+var_78]
0x14002b223  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b228  lea     rdx, [r15+20h]
0x14002b22c  lea     rcx, [rbp+57h+var_78]
0x14002b230  call    ?GetRegistryConfigurationPath@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV67@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(std::wstring const &)
0x14002b235  lea     rcx, [r15+110h]
0x14002b23c  mov     rdx, rax
0x14002b23f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14002b244  lea     rcx, [rbp+57h+var_78]
0x14002b248  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b24d  mov     r14, [r15+178h]
0x14002b254  mov     rax, [r14]
0x14002b257  mov     rsi, [rax+48h]
0x14002b25b  lea     rax, [rbp+57h+var_78]
0x14002b25f  mov     [rbp+57h+var_B0], rax
0x14002b263  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002b26a  lea     rcx, [rbp+57h+var_78]
0x14002b26e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b273  mov     rdi, rax
0x14002b276  lea     rax, [rbp+57h+var_58]
0x14002b27a  mov     [rbp+57h+var_A8], rax
0x14002b27e  lea     rdx, aMicrosoftVoice_2; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b285  lea     rcx, [rbp+57h+var_58]
0x14002b289  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b28e  mov     rbx, rax
0x14002b291  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b298  lea     rcx, [rbp+57h+var_98]
0x14002b29c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b2a1  nop
0x14002b2a2  mov     [rsp+0F0h+var_C0], 0
0x14002b2ab  mov     [rsp+0F0h+var_C8], r15
0x14002b2b0  mov     [rsp+0F0h+var_D0], rdi
0x14002b2b5  mov     r9d, 24Dh
0x14002b2bb  mov     r8, rbx
0x14002b2be  mov     rdx, rax
0x14002b2c1  mov     rcx, r14
0x14002b2c4  mov     rax, rsi
0x14002b2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b2cc  xor     eax, eax
0x14002b2ce  mov     rcx, [rbp+57h+var_38]
0x14002b2d2  xor     rcx, rsp; StackCookie
0x14002b2d5  call    __security_check_cookie
0x14002b2da  add     rsp, 0C8h
0x14002b2e1  pop     r15
0x14002b2e3  pop     r14
0x14002b2e5  pop     rdi
0x14002b2e6  pop     rsi
0x14002b2e7  pop     rbx
0x14002b2e8  pop     rbp
0x14002b2e9  retn
```

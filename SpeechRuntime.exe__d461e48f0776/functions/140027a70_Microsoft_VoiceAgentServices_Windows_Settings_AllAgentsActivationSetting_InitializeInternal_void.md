# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::InitializeInternal(void)

- ea: `0x140027a70`
- end: `0x140027bd5`
- name: `?InitializeInternal@AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJXZ`
- size: `357`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x1400128b8`
- `0x14001296c`
- `0x140020ff0`
- `0x140021658`
- `0x140021b80`
- `0x140025630`
- `0x140031010`

## string_xrefs

- `0x140027ab5`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027b7c`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027aa4`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::InitializeInternal`
- `0x140027b69`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::InitializeInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::InitializeInternal(
        Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *); // rbx
  __int64 RegistryConfigurationPath; // rax
  __int64 v5; // r14
  void (__fastcall *v6)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, _QWORD); // rsi
  int v7; // r8d
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  _BYTE v12[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v14[32]; // [rsp+98h] [rbp-1h] BYREF

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v13,
    "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::InitializeInternal");
  std::string::string(
    v14,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v3(v2, v14, v13, 46, this);
  std::string::~string(v14);
  std::string::~string(v13);
  std::wstring::wstring(v13, L"UserPreferenceForAllApps");
  RegistryConfigurationPath = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(
                                v14,
                                v13);
  std::wstring::operator=((char *)this + 272, RegistryConfigurationPath);
  std::wstring::~wstring(v14);
  std::wstring::~wstring(v13);
  v5 = *((_QWORD *)this + 47);
  v6 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, _QWORD))(*(_QWORD *)v5 + 72LL);
  v8 = std::string::string(v13, "hr = 0x%x", v7);
  v9 = std::string::string(
         v14,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::InitializeInternal");
  v10 = std::string::string(
          v12,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v6(v5, v10, v9, 48, v8, this, 0);
  return 0;
}

```

## disassembly

```asm
0x140027a70  push    rbp
0x140027a72  push    rbx
0x140027a73  push    rsi
0x140027a74  push    rdi
0x140027a75  push    r14
0x140027a77  push    r15
0x140027a79  lea     rbp, [rsp-2Fh]
0x140027a7e  sub     rsp, 0C8h
0x140027a85  mov     rax, cs:__security_cookie
0x140027a8c  xor     rax, rsp
0x140027a8f  mov     [rbp+57h+var_38], rax
0x140027a93  mov     r15, rcx
0x140027a96  mov     rdi, [rcx+178h]
0x140027a9d  mov     rax, [rdi]
0x140027aa0  mov     rbx, [rax+28h]
0x140027aa4  lea     rdx, aMicrosoftVoice_46; "Microsoft::VoiceAgentServices::Windows:"...
0x140027aab  lea     rcx, [rbp+57h+var_78]
0x140027aaf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027ab4  nop
0x140027ab5  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027abc  lea     rcx, [rbp+57h+var_58]
0x140027ac0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027ac5  nop
0x140027ac6  mov     [rsp+0F0h+var_D0], r15
0x140027acb  mov     r9d, 2Eh ; '.'
0x140027ad1  lea     r8, [rbp+57h+var_78]
0x140027ad5  lea     rdx, [rbp+57h+var_58]
0x140027ad9  mov     rcx, rdi
0x140027adc  mov     rax, rbx
0x140027adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027ae4  nop
0x140027ae5  lea     rcx, [rbp+57h+var_58]
0x140027ae9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140027aee  nop
0x140027aef  lea     rcx, [rbp+57h+var_78]
0x140027af3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140027af8  lea     rdx, aUserpreference; "UserPreferenceForAllApps"
0x140027aff  lea     rcx, [rbp+57h+var_78]
0x140027b03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140027b08  nop
0x140027b09  lea     rdx, [rbp+57h+var_78]
0x140027b0d  lea     rcx, [rbp+57h+var_58]
0x140027b11  call    ?GetRegistryConfigurationPath@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV67@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(std::wstring const &)
0x140027b16  lea     rcx, [r15+110h]
0x140027b1d  mov     rdx, rax
0x140027b20  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140027b25  lea     rcx, [rbp+57h+var_58]
0x140027b29  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140027b2e  nop
0x140027b2f  lea     rcx, [rbp+57h+var_78]
0x140027b33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140027b38  mov     r14, [r15+178h]
0x140027b3f  mov     rax, [r14]
0x140027b42  mov     rsi, [rax+48h]
0x140027b46  lea     rax, [rbp+57h+var_78]
0x140027b4a  mov     [rbp+57h+var_B0], rax
0x140027b4e  lea     rdx, aHr0xX; "hr = 0x%x"
0x140027b55  lea     rcx, [rbp+57h+var_78]
0x140027b59  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027b5e  mov     rdi, rax
0x140027b61  lea     rax, [rbp+57h+var_58]
0x140027b65  mov     [rbp+57h+var_A8], rax
0x140027b69  lea     rdx, aMicrosoftVoice_46; "Microsoft::VoiceAgentServices::Windows:"...
0x140027b70  lea     rcx, [rbp+57h+var_58]
0x140027b74  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027b79  mov     rbx, rax
0x140027b7c  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027b83  lea     rcx, [rbp+57h+var_98]
0x140027b87  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027b8c  nop
0x140027b8d  mov     [rsp+0F0h+var_C0], 0
0x140027b96  mov     [rsp+0F0h+var_C8], r15
0x140027b9b  mov     [rsp+0F0h+var_D0], rdi
0x140027ba0  mov     r9d, 30h ; '0'
0x140027ba6  mov     r8, rbx
0x140027ba9  mov     rdx, rax
0x140027bac  mov     rcx, r14
0x140027baf  mov     rax, rsi
0x140027bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027bb7  xor     eax, eax
0x140027bb9  mov     rcx, [rbp+57h+var_38]
0x140027bbd  xor     rcx, rsp; StackCookie
0x140027bc0  call    __security_check_cookie
0x140027bc5  add     rsp, 0C8h
0x140027bcc  pop     r15
0x140027bce  pop     r14
0x140027bd0  pop     rdi
0x140027bd1  pop     rsi
0x140027bd2  pop     rbx
0x140027bd3  pop     rbp
0x140027bd4  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::NotifyUpdated(std::function<void (void)>)

- ea: `0x140024e20`
- end: `0x140024f76`
- name: `?NotifyUpdated@RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJV?$function@$$A6AXXZ@std@@@Z`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021528`
- `0x140021658`
- `0x140024830`
- `0x140031010`

## string_xrefs

- `0x140024e75`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x140024f08`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x140024e64`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::NotifyUpdated`
- `0x140024ef5`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::NotifyUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::NotifyUpdated(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64, __int64); // rbx
  __int64 v6; // r14
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD); // rsi
  int v8; // r8d
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  _BYTE v13[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v14[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v15[32]; // [rsp+A0h] [rbp+7h] BYREF

  v4 = *(_QWORD *)(a1 + 136);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, __int64))(*(_QWORD *)v4 + 40LL);
  std::string::string(v15, "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::NotifyUpdated");
  std::string::string(
    v14,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v5(v4, v14, v15, 38, a1);
  std::string::~string(v14);
  std::string::~string(v15);
  std::function<void (std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)>::operator=(
    a1 + 48,
    a2);
  v6 = *(_QWORD *)(a1 + 136);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v6 + 72LL);
  v9 = std::string::string(v15, "hr = 0x%x", v8);
  v10 = std::string::string(
          v14,
          "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::NotifyUpdated");
  v11 = std::string::string(
          v13,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v7(v6, v11, v10, 40, v9, a1, 0);
  std::_Func_class<void,>::~_Func_class<void,>(a2);
  return 0;
}

```

## disassembly

```asm
0x140024e20  mov     [rsp-8+arg_10], rbx
0x140024e25  mov     [rsp-8+arg_18], rsi
0x140024e2a  push    rbp
0x140024e2b  push    rdi
0x140024e2c  push    r12
0x140024e2e  push    r14
0x140024e30  push    r15
0x140024e32  lea     rbp, [rsp-37h]
0x140024e37  sub     rsp, 0D0h
0x140024e3e  mov     rax, cs:__security_cookie
0x140024e45  xor     rax, rsp
0x140024e48  mov     [rbp+57h+var_30], rax
0x140024e4c  mov     r12, rdx
0x140024e4f  mov     r15, rcx
0x140024e52  mov     [rbp+57h+var_B0], rdx
0x140024e56  mov     rdi, [rcx+88h]
0x140024e5d  mov     rax, [rdi]
0x140024e60  mov     rbx, [rax+28h]
0x140024e64  lea     rdx, aMicrosoftVoice_19; "Microsoft::VoiceAgentServices::Windows:"...
0x140024e6b  lea     rcx, [rbp+57h+var_50]
0x140024e6f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024e74  nop
0x140024e75  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140024e7c  lea     rcx, [rbp+57h+var_70]
0x140024e80  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024e85  nop
0x140024e86  mov     [rsp+0F0h+var_D0], r15
0x140024e8b  mov     r9d, 26h ; '&'
0x140024e91  lea     r8, [rbp+57h+var_50]
0x140024e95  lea     rdx, [rbp+57h+var_70]
0x140024e99  mov     rcx, rdi
0x140024e9c  mov     rax, rbx
0x140024e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024ea4  nop
0x140024ea5  lea     rcx, [rbp+57h+var_70]
0x140024ea9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140024eae  nop
0x140024eaf  lea     rcx, [rbp+57h+var_50]
0x140024eb3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140024eb8  lea     rcx, [r15+30h]
0x140024ebc  mov     rdx, r12
0x140024ebf  call    ??4?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)>::operator=(std::function<void (std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)> const &)
0x140024ec4  mov     r14, [r15+88h]
0x140024ecb  mov     rax, [r14]
0x140024ece  mov     rsi, [rax+48h]
0x140024ed2  lea     rax, [rbp+57h+var_50]
0x140024ed6  mov     [rbp+57h+var_A8], rax
0x140024eda  lea     rdx, aHr0xX; "hr = 0x%x"
0x140024ee1  lea     rcx, [rbp+57h+var_50]
0x140024ee5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024eea  mov     rdi, rax
0x140024eed  lea     rax, [rbp+57h+var_70]
0x140024ef1  mov     [rbp+57h+var_A0], rax
0x140024ef5  lea     rdx, aMicrosoftVoice_19; "Microsoft::VoiceAgentServices::Windows:"...
0x140024efc  lea     rcx, [rbp+57h+var_70]
0x140024f00  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024f05  mov     rbx, rax
0x140024f08  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140024f0f  lea     rcx, [rbp+57h+var_90]
0x140024f13  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024f18  nop
0x140024f19  mov     [rsp+0F0h+var_C0], 0
0x140024f22  mov     [rsp+0F0h+var_C8], r15
0x140024f27  mov     [rsp+0F0h+var_D0], rdi
0x140024f2c  mov     r9d, 28h ; '('
0x140024f32  mov     r8, rbx
0x140024f35  mov     rdx, rax
0x140024f38  mov     rcx, r14
0x140024f3b  mov     rax, rsi
0x140024f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024f43  nop
0x140024f44  mov     rcx, r12
0x140024f47  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140024f4c  xor     eax, eax
0x140024f4e  mov     rcx, [rbp+57h+var_30]
0x140024f52  xor     rcx, rsp; StackCookie
0x140024f55  call    __security_check_cookie
0x140024f5a  lea     r11, [rsp+0F0h+var_20]
0x140024f62  mov     rbx, [r11+40h]
0x140024f66  mov     rsi, [r11+48h]
0x140024f6a  mov     rsp, r11
0x140024f6d  pop     r15
0x140024f6f  pop     r14
0x140024f71  pop     r12
0x140024f73  pop     rdi
0x140024f74  pop     rbp
0x140024f75  retn
```

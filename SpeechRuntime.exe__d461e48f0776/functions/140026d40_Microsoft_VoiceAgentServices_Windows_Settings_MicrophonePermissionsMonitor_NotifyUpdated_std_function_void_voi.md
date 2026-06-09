# Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::NotifyUpdated(std::function<void (void)>)

- ea: `0x140026d40`
- end: `0x140026e90`
- name: `?NotifyUpdated@MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJV?$function@$$A6AXXZ@std@@@Z`
- size: `336`
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

- `0x140026d81`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::NotifyUpdated`
- `0x140026e0f`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::NotifyUpdated`
- `0x140026d92`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`
- `0x140026e22`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::NotifyUpdated(
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

  v4 = *(_QWORD *)(a1 + 104);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, __int64))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v15,
    "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::NotifyUpdated");
  std::string::string(
    v14,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v5(v4, v14, v15, 36, a1);
  std::string::~string(v14);
  std::string::~string(v15);
  std::function<void (std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)>::operator=(
    a1 + 16,
    a2);
  v6 = *(_QWORD *)(a1 + 104);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v6 + 72LL);
  v9 = std::string::string(v15, "hr = 0x%x", v8);
  v10 = std::string::string(
          v14,
          "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::NotifyUpdated");
  v11 = std::string::string(
          v13,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v7(v6, v11, v10, 38, v9, a1, 0);
  std::_Func_class<void,>::~_Func_class<void,>(a2);
  return 0;
}

```

## disassembly

```asm
0x140026d40  mov     [rsp-8+arg_10], rbx
0x140026d45  mov     [rsp-8+arg_18], rsi
0x140026d4a  push    rbp
0x140026d4b  push    rdi
0x140026d4c  push    r12
0x140026d4e  push    r14
0x140026d50  push    r15
0x140026d52  lea     rbp, [rsp-37h]
0x140026d57  sub     rsp, 0D0h
0x140026d5e  mov     rax, cs:__security_cookie
0x140026d65  xor     rax, rsp
0x140026d68  mov     [rbp+57h+var_30], rax
0x140026d6c  mov     r12, rdx
0x140026d6f  mov     r15, rcx
0x140026d72  mov     [rbp+57h+var_B0], rdx
0x140026d76  mov     rdi, [rcx+68h]
0x140026d7a  mov     rax, [rdi]
0x140026d7d  mov     rbx, [rax+28h]
0x140026d81  lea     rdx, aMicrosoftVoice_51; "Microsoft::VoiceAgentServices::Windows:"...
0x140026d88  lea     rcx, [rbp+57h+var_50]
0x140026d8c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026d91  nop
0x140026d92  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026d99  lea     rcx, [rbp+57h+var_70]
0x140026d9d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026da2  nop
0x140026da3  mov     [rsp+0F0h+var_D0], r15
0x140026da8  mov     r9d, 24h ; '$'
0x140026dae  lea     r8, [rbp+57h+var_50]
0x140026db2  lea     rdx, [rbp+57h+var_70]
0x140026db6  mov     rcx, rdi
0x140026db9  mov     rax, rbx
0x140026dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026dc1  nop
0x140026dc2  lea     rcx, [rbp+57h+var_70]
0x140026dc6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140026dcb  nop
0x140026dcc  lea     rcx, [rbp+57h+var_50]
0x140026dd0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140026dd5  lea     rcx, [r15+10h]
0x140026dd9  mov     rdx, r12
0x140026ddc  call    ??4?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)>::operator=(std::function<void (std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)> const &)
0x140026de1  mov     r14, [r15+68h]
0x140026de5  mov     rax, [r14]
0x140026de8  mov     rsi, [rax+48h]
0x140026dec  lea     rax, [rbp+57h+var_50]
0x140026df0  mov     [rbp+57h+var_A8], rax
0x140026df4  lea     rdx, aHr0xX; "hr = 0x%x"
0x140026dfb  lea     rcx, [rbp+57h+var_50]
0x140026dff  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026e04  mov     rdi, rax
0x140026e07  lea     rax, [rbp+57h+var_70]
0x140026e0b  mov     [rbp+57h+var_A0], rax
0x140026e0f  lea     rdx, aMicrosoftVoice_51; "Microsoft::VoiceAgentServices::Windows:"...
0x140026e16  lea     rcx, [rbp+57h+var_70]
0x140026e1a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026e1f  mov     rbx, rax
0x140026e22  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026e29  lea     rcx, [rbp+57h+var_90]
0x140026e2d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026e32  nop
0x140026e33  mov     [rsp+0F0h+var_C0], 0
0x140026e3c  mov     [rsp+0F0h+var_C8], r15
0x140026e41  mov     [rsp+0F0h+var_D0], rdi
0x140026e46  mov     r9d, 26h ; '&'
0x140026e4c  mov     r8, rbx
0x140026e4f  mov     rdx, rax
0x140026e52  mov     rcx, r14
0x140026e55  mov     rax, rsi
0x140026e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e5d  nop
0x140026e5e  mov     rcx, r12
0x140026e61  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140026e66  xor     eax, eax
0x140026e68  mov     rcx, [rbp+57h+var_30]
0x140026e6c  xor     rcx, rsp; StackCookie
0x140026e6f  call    __security_check_cookie
0x140026e74  lea     r11, [rsp+0F0h+var_20]
0x140026e7c  mov     rbx, [r11+40h]
0x140026e80  mov     rsi, [r11+48h]
0x140026e84  mov     rsp, r11
0x140026e87  pop     r15
0x140026e89  pop     r14
0x140026e8b  pop     r12
0x140026e8d  pop     rdi
0x140026e8e  pop     rbp
0x140026e8f  retn
```

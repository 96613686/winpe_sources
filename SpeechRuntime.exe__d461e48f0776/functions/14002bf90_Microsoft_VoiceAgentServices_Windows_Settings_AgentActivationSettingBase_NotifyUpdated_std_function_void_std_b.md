# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::NotifyUpdated(std::function<void (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)>)

- ea: `0x14002bf90`
- end: `0x14002c0e9`
- name: `?NotifyUpdated@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJV?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z@std@@@Z`
- size: `345`
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

- `0x14002bfe5`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c07b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002bfd4`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::NotifyUpdated`
- `0x14002c068`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::NotifyUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::NotifyUpdated(
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

  v4 = *(_QWORD *)(a1 + 376);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, __int64))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v15,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::NotifyUpdated");
  std::string::string(
    v14,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v14, v15, 88, a1);
  std::string::~string(v14);
  std::string::~string(v15);
  std::function<void (std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)>::operator=(
    a1 + 208,
    a2);
  v6 = *(_QWORD *)(a1 + 376);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v6 + 72LL);
  v9 = std::string::string(v15, "hr = 0x%x", v8);
  v10 = std::string::string(
          v14,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::NotifyUpdated");
  v11 = std::string::string(
          v13,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v11, v10, 90, v9, a1, 0);
  std::_Func_class<void,>::~_Func_class<void,>(a2);
  return 0;
}

```

## disassembly

```asm
0x14002bf90  mov     [rsp-8+arg_10], rbx
0x14002bf95  mov     [rsp-8+arg_18], rsi
0x14002bf9a  push    rbp
0x14002bf9b  push    rdi
0x14002bf9c  push    r12
0x14002bf9e  push    r14
0x14002bfa0  push    r15
0x14002bfa2  lea     rbp, [rsp-37h]
0x14002bfa7  sub     rsp, 0D0h
0x14002bfae  mov     rax, cs:__security_cookie
0x14002bfb5  xor     rax, rsp
0x14002bfb8  mov     [rbp+57h+var_30], rax
0x14002bfbc  mov     r12, rdx
0x14002bfbf  mov     r15, rcx
0x14002bfc2  mov     [rbp+57h+var_B0], rdx
0x14002bfc6  mov     rdi, [rcx+178h]
0x14002bfcd  mov     rax, [rdi]
0x14002bfd0  mov     rbx, [rax+28h]
0x14002bfd4  lea     rdx, aMicrosoftVoice_43; "Microsoft::VoiceAgentServices::Windows:"...
0x14002bfdb  lea     rcx, [rbp+57h+var_50]
0x14002bfdf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bfe4  nop
0x14002bfe5  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002bfec  lea     rcx, [rbp+57h+var_70]
0x14002bff0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bff5  nop
0x14002bff6  mov     [rsp+0F0h+var_D0], r15
0x14002bffb  mov     r9d, 58h ; 'X'
0x14002c001  lea     r8, [rbp+57h+var_50]
0x14002c005  lea     rdx, [rbp+57h+var_70]
0x14002c009  mov     rcx, rdi
0x14002c00c  mov     rax, rbx
0x14002c00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c014  nop
0x14002c015  lea     rcx, [rbp+57h+var_70]
0x14002c019  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c01e  nop
0x14002c01f  lea     rcx, [rbp+57h+var_50]
0x14002c023  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c028  lea     rcx, [r15+0D0h]
0x14002c02f  mov     rdx, r12
0x14002c032  call    ??4?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)>::operator=(std::function<void (std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)> const &)
0x14002c037  mov     r14, [r15+178h]
0x14002c03e  mov     rax, [r14]
0x14002c041  mov     rsi, [rax+48h]
0x14002c045  lea     rax, [rbp+57h+var_50]
0x14002c049  mov     [rbp+57h+var_A8], rax
0x14002c04d  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002c054  lea     rcx, [rbp+57h+var_50]
0x14002c058  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c05d  mov     rdi, rax
0x14002c060  lea     rax, [rbp+57h+var_70]
0x14002c064  mov     [rbp+57h+var_A0], rax
0x14002c068  lea     rdx, aMicrosoftVoice_43; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c06f  lea     rcx, [rbp+57h+var_70]
0x14002c073  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c078  mov     rbx, rax
0x14002c07b  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c082  lea     rcx, [rbp+57h+var_90]
0x14002c086  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c08b  nop
0x14002c08c  mov     [rsp+0F0h+var_C0], 0
0x14002c095  mov     [rsp+0F0h+var_C8], r15
0x14002c09a  mov     [rsp+0F0h+var_D0], rdi
0x14002c09f  mov     r9d, 5Ah ; 'Z'
0x14002c0a5  mov     r8, rbx
0x14002c0a8  mov     rdx, rax
0x14002c0ab  mov     rcx, r14
0x14002c0ae  mov     rax, rsi
0x14002c0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c0b6  nop
0x14002c0b7  mov     rcx, r12
0x14002c0ba  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x14002c0bf  xor     eax, eax
0x14002c0c1  mov     rcx, [rbp+57h+var_30]
0x14002c0c5  xor     rcx, rsp; StackCookie
0x14002c0c8  call    __security_check_cookie
0x14002c0cd  lea     r11, [rsp+0F0h+var_20]
0x14002c0d5  mov     rbx, [r11+40h]
0x14002c0d9  mov     rsi, [r11+48h]
0x14002c0dd  mov     rsp, r11
0x14002c0e0  pop     r15
0x14002c0e2  pop     r14
0x14002c0e4  pop     r12
0x14002c0e6  pop     rdi
0x14002c0e7  pop     rbp
0x14002c0e8  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint(Microsoft::VoiceAgentServices::Windows::Settings::AgentConfigurationSettingDefaultHint)

- ea: `0x140028e08`
- end: `0x140028f53`
- name: `?GetEnabledStatusFromHint@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA_NW4AgentConfigurationSettingDefaultHint@2345@@Z`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140029480`
- `0x14002a1f0`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140028e08`
- `0x140031010`

## string_xrefs

- `0x140028e58`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028eef`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028e47`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint`
- `0x140028edc`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint(
        __int64 a1,
        int a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64, __int64); // rbx
  bool v6; // r15
  __int64 v7; // r14
  void (__fastcall *v8)(__int64, __int64, __int64, __int64, __int64, __int64, bool); // rsi
  int v9; // r8d
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  _BYTE v14[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v15[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v16[32]; // [rsp+98h] [rbp+Fh] BYREF

  v4 = *(_QWORD *)(a1 + 376);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, __int64))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v16,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint");
  std::string::string(
    v15,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v15, v16, 440, a1);
  std::string::~string(v15);
  std::string::~string(v16);
  v6 = (unsigned int)(a2 - 1) <= 1;
  v7 = *(_QWORD *)(a1 + 376);
  v8 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, __int64, bool))(*(_QWORD *)v7 + 72LL);
  v10 = std::string::string(v16, "enabled = %d", v9);
  v11 = std::string::string(
          v15,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint");
  v12 = std::string::string(
          v14,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v8(v7, v12, v11, 449, v10, a1, v6);
  return v6;
}

```

## disassembly

```asm
0x140028e08  mov     [rsp-8+arg_8], rbx
0x140028e0d  mov     [rsp-8+arg_10], rsi
0x140028e12  push    rbp
0x140028e13  push    rdi
0x140028e14  push    r13
0x140028e16  push    r14
0x140028e18  push    r15
0x140028e1a  lea     rbp, [rsp-37h]
0x140028e1f  sub     rsp, 0C0h
0x140028e26  mov     rax, cs:__security_cookie
0x140028e2d  xor     rax, rsp
0x140028e30  mov     [rbp+57h+var_28], rax
0x140028e34  mov     esi, edx
0x140028e36  mov     r13, rcx
0x140028e39  mov     rdi, [rcx+178h]
0x140028e40  mov     rax, [rdi]
0x140028e43  mov     rbx, [rax+28h]
0x140028e47  lea     rdx, aMicrosoftVoice_39; "Microsoft::VoiceAgentServices::Windows:"...
0x140028e4e  lea     rcx, [rbp+57h+var_48]
0x140028e52  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028e57  nop
0x140028e58  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028e5f  lea     rcx, [rbp+57h+var_68]
0x140028e63  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028e68  nop
0x140028e69  mov     [rsp+0E0h+var_C0], r13
0x140028e6e  mov     r9d, 1B8h
0x140028e74  lea     r8, [rbp+57h+var_48]
0x140028e78  lea     rdx, [rbp+57h+var_68]
0x140028e7c  mov     rcx, rdi
0x140028e7f  mov     rax, rbx
0x140028e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028e87  nop
0x140028e88  lea     rcx, [rbp+57h+var_68]
0x140028e8c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028e91  nop
0x140028e92  lea     rcx, [rbp+57h+var_48]
0x140028e96  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028e9b  xor     r15b, r15b
0x140028e9e  sub     esi, 1
0x140028ea1  jz      short loc_140028EA8
0x140028ea3  cmp     esi, 1
0x140028ea6  jnz     short loc_140028EAB
0x140028ea8  mov     r15b, 1
0x140028eab  mov     r14, [r13+178h]
0x140028eb2  mov     rax, [r14]
0x140028eb5  mov     rsi, [rax+48h]
0x140028eb9  lea     rax, [rbp+57h+var_48]
0x140028ebd  mov     [rbp+57h+var_A0], rax
0x140028ec1  lea     rdx, aEnabledD; "enabled = %d"
0x140028ec8  lea     rcx, [rbp+57h+var_48]
0x140028ecc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028ed1  mov     rdi, rax
0x140028ed4  lea     rax, [rbp+57h+var_68]
0x140028ed8  mov     [rbp+57h+var_98], rax
0x140028edc  lea     rdx, aMicrosoftVoice_39; "Microsoft::VoiceAgentServices::Windows:"...
0x140028ee3  lea     rcx, [rbp+57h+var_68]
0x140028ee7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028eec  mov     rbx, rax
0x140028eef  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028ef6  lea     rcx, [rbp+57h+var_88]
0x140028efa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028eff  movzx   edx, r15b
0x140028f03  mov     [rsp+0E0h+var_B0], edx
0x140028f07  mov     [rsp+0E0h+var_B8], r13
0x140028f0c  mov     [rsp+0E0h+var_C0], rdi
0x140028f11  mov     r9d, 1C1h
0x140028f17  mov     r8, rbx
0x140028f1a  mov     rdx, rax
0x140028f1d  mov     rcx, r14
0x140028f20  mov     rax, rsi
0x140028f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028f28  mov     al, r15b
0x140028f2b  mov     rcx, [rbp+57h+var_28]
0x140028f2f  xor     rcx, rsp; StackCookie
0x140028f32  call    __security_check_cookie
0x140028f37  lea     r11, [rsp+0E0h+var_20]
0x140028f3f  mov     rbx, [r11+38h]
0x140028f43  mov     rsi, [r11+40h]
0x140028f47  mov     rsp, r11
0x140028f4a  pop     r15
0x140028f4c  pop     r14
0x140028f4e  pop     r13
0x140028f50  pop     rdi
0x140028f51  pop     rbp
0x140028f52  retn
```

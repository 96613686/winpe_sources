# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetAgentConfiguration(Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration &)

- ea: `0x1400276e0`
- end: `0x140027807`
- name: `?GetAgentConfiguration@AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEAUAgentConfiguration@2345@@Z`
- size: `295`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *__hidden this, struct Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140031010`

## string_xrefs

- `0x140027725`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x1400277ac`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027714`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetAgentConfiguration`
- `0x140027799`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetAgentConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetAgentConfiguration(
        Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *this,
        struct Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration *a2)
{
  __int64 v3; // rdi
  void (__fastcall *v4)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *); // rbx
  __int64 v5; // r14
  void (__fastcall *v6)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, int); // rsi
  int v7; // r8d
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  _BYTE v12[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v14[32]; // [rsp+98h] [rbp-1h] BYREF

  v3 = *((_QWORD *)this + 47);
  v4 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v3 + 40LL);
  std::string::string(
    v14,
    "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetAgentConfiguration");
  std::string::string(
    v13,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v4(v3, v13, v14, 40, this);
  std::string::~string(v13);
  std::string::~string(v14);
  v5 = *((_QWORD *)this + 47);
  v6 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, int))(*(_QWORD *)v5 + 72LL);
  v8 = std::string::string(v14, "hr = 0x%x", v7);
  v9 = std::string::string(
         v13,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetAgentConfiguration");
  v10 = std::string::string(
          v12,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v6(v5, v10, v9, 41, v8, this, -2147418113);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1400276e0  push    rbp
0x1400276e2  push    rbx
0x1400276e3  push    rsi
0x1400276e4  push    rdi
0x1400276e5  push    r14
0x1400276e7  push    r15
0x1400276e9  lea     rbp, [rsp-2Fh]
0x1400276ee  sub     rsp, 0C8h
0x1400276f5  mov     rax, cs:__security_cookie
0x1400276fc  xor     rax, rsp
0x1400276ff  mov     [rbp+57h+var_38], rax
0x140027703  mov     r15, rcx
0x140027706  mov     rdi, [rcx+178h]
0x14002770d  mov     rax, [rdi]
0x140027710  mov     rbx, [rax+28h]
0x140027714  lea     rdx, aMicrosoftVoice_11; "Microsoft::VoiceAgentServices::Windows:"...
0x14002771b  lea     rcx, [rbp+57h+var_58]
0x14002771f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027724  nop
0x140027725  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002772c  lea     rcx, [rbp+57h+var_78]
0x140027730  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027735  nop
0x140027736  mov     [rsp+0F0h+var_D0], r15
0x14002773b  mov     r9d, 28h ; '('
0x140027741  lea     r8, [rbp+57h+var_58]
0x140027745  lea     rdx, [rbp+57h+var_78]
0x140027749  mov     rcx, rdi
0x14002774c  mov     rax, rbx
0x14002774f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027754  nop
0x140027755  lea     rcx, [rbp+57h+var_78]
0x140027759  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002775e  nop
0x14002775f  lea     rcx, [rbp+57h+var_58]
0x140027763  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140027768  mov     r14, [r15+178h]
0x14002776f  mov     rax, [r14]
0x140027772  mov     rsi, [rax+48h]
0x140027776  lea     rax, [rbp+57h+var_58]
0x14002777a  mov     [rbp+57h+var_B0], rax
0x14002777e  lea     rdx, aHr0xX; "hr = 0x%x"
0x140027785  lea     rcx, [rbp+57h+var_58]
0x140027789  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002778e  mov     rdi, rax
0x140027791  lea     rax, [rbp+57h+var_78]
0x140027795  mov     [rbp+57h+var_A8], rax
0x140027799  lea     rdx, aMicrosoftVoice_11; "Microsoft::VoiceAgentServices::Windows:"...
0x1400277a0  lea     rcx, [rbp+57h+var_78]
0x1400277a4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400277a9  mov     rbx, rax
0x1400277ac  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400277b3  lea     rcx, [rbp+57h+var_98]
0x1400277b7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400277bc  nop
0x1400277bd  mov     [rsp+0F0h+var_C0], 8000FFFFh
0x1400277c5  mov     [rsp+0F0h+var_C8], r15
0x1400277ca  mov     [rsp+0F0h+var_D0], rdi
0x1400277cf  mov     r9d, 29h ; ')'
0x1400277d5  mov     r8, rbx
0x1400277d8  mov     rdx, rax
0x1400277db  mov     rcx, r14
0x1400277de  mov     rax, rsi
0x1400277e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400277e6  mov     eax, 8000FFFFh
0x1400277eb  mov     rcx, [rbp+57h+var_38]
0x1400277ef  xor     rcx, rsp; StackCookie
0x1400277f2  call    __security_check_cookie
0x1400277f7  add     rsp, 0C8h
0x1400277fe  pop     r15
0x140027800  pop     r14
0x140027802  pop     rdi
0x140027803  pop     rsi
0x140027804  pop     rbx
0x140027805  pop     rbp
0x140027806  retn
```

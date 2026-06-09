# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationOnLockScreenEnabledStatusDefault(void)

- ea: `0x140027940`
- end: `0x140027a64`
- name: `?GetVoiceActivationOnLockScreenEnabledStatusDefault@AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@MEAA_NXZ`
- size: `292`
- prototype: `bool __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140031010`

## string_xrefs

- `0x140027985`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027a0c`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027974`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationOnLockScreenEnabledStatusDefault`
- `0x1400279f9`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationOnLockScreenEnabledStatusDefault`

## pseudocode

```c
char __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationOnLockScreenEnabledStatusDefault(
        Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *); // rbx
  __int64 v4; // r14
  void (__fastcall *v5)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, int); // rsi
  int v6; // r8d
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v11[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v12[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v13[32]; // [rsp+98h] [rbp-1h] BYREF

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v13,
    "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationOnLockScreenEnabledStatusDefault");
  std::string::string(
    v12,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v3(v2, v12, v13, 61, this);
  std::string::~string(v12);
  std::string::~string(v13);
  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, int))(*(_QWORD *)v4 + 72LL);
  v7 = std::string::string(v13, "enabled = %d", v6);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationOnLockScreenEna"
         "bledStatusDefault");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v5(v4, v9, v8, 64, v7, this, 1);
  return 1;
}

```

## disassembly

```asm
0x140027940  push    rbp
0x140027942  push    rbx
0x140027943  push    rsi
0x140027944  push    rdi
0x140027945  push    r14
0x140027947  push    r15
0x140027949  lea     rbp, [rsp-2Fh]
0x14002794e  sub     rsp, 0C8h
0x140027955  mov     rax, cs:__security_cookie
0x14002795c  xor     rax, rsp
0x14002795f  mov     [rbp+57h+var_38], rax
0x140027963  mov     r15, rcx
0x140027966  mov     rdi, [rcx+178h]
0x14002796d  mov     rax, [rdi]
0x140027970  mov     rbx, [rax+28h]
0x140027974  lea     rdx, aMicrosoftVoice_12; "Microsoft::VoiceAgentServices::Windows:"...
0x14002797b  lea     rcx, [rbp+57h+var_58]
0x14002797f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027984  nop
0x140027985  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002798c  lea     rcx, [rbp+57h+var_78]
0x140027990  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027995  nop
0x140027996  mov     [rsp+0F0h+var_D0], r15
0x14002799b  mov     r9d, 3Dh ; '='
0x1400279a1  lea     r8, [rbp+57h+var_58]
0x1400279a5  lea     rdx, [rbp+57h+var_78]
0x1400279a9  mov     rcx, rdi
0x1400279ac  mov     rax, rbx
0x1400279af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400279b4  nop
0x1400279b5  lea     rcx, [rbp+57h+var_78]
0x1400279b9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400279be  nop
0x1400279bf  lea     rcx, [rbp+57h+var_58]
0x1400279c3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400279c8  mov     r14, [r15+178h]
0x1400279cf  mov     rax, [r14]
0x1400279d2  mov     rsi, [rax+48h]
0x1400279d6  lea     rax, [rbp+57h+var_58]
0x1400279da  mov     [rbp+57h+var_B0], rax
0x1400279de  lea     rdx, aEnabledD; "enabled = %d"
0x1400279e5  lea     rcx, [rbp+57h+var_58]
0x1400279e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400279ee  mov     rdi, rax
0x1400279f1  lea     rax, [rbp+57h+var_78]
0x1400279f5  mov     [rbp+57h+var_A8], rax
0x1400279f9  lea     rdx, aMicrosoftVoice_12; "Microsoft::VoiceAgentServices::Windows:"...
0x140027a00  lea     rcx, [rbp+57h+var_78]
0x140027a04  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027a09  mov     rbx, rax
0x140027a0c  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027a13  lea     rcx, [rbp+57h+var_98]
0x140027a17  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027a1c  nop
0x140027a1d  mov     [rsp+0F0h+var_C0], 1
0x140027a25  mov     [rsp+0F0h+var_C8], r15
0x140027a2a  mov     [rsp+0F0h+var_D0], rdi
0x140027a2f  mov     r9d, 40h ; '@'
0x140027a35  mov     r8, rbx
0x140027a38  mov     rdx, rax
0x140027a3b  mov     rcx, r14
0x140027a3e  mov     rax, rsi
0x140027a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027a46  mov     al, 1
0x140027a48  mov     rcx, [rbp+57h+var_38]
0x140027a4c  xor     rcx, rsp; StackCookie
0x140027a4f  call    __security_check_cookie
0x140027a54  add     rsp, 0C8h
0x140027a5b  pop     r15
0x140027a5d  pop     r14
0x140027a5f  pop     rdi
0x140027a60  pop     rsi
0x140027a61  pop     rbx
0x140027a62  pop     rbp
0x140027a63  retn
```

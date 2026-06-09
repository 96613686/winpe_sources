# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusDefault(void)

- ea: `0x14002a1f0`
- end: `0x14002a33a`
- name: `?GetVoiceActivationOnLockScreenEnabledStatusDefault@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAA_NXZ`
- size: `330`
- prototype: `bool __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140028e08`
- `0x140031010`

## string_xrefs

- `0x14002a23e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a2d8`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a22d`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusDefault`
- `0x14002a2c5`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusDefault`

## pseudocode

```c
bool __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusDefault(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  BOOL EnabledStatusFromHint; // r15d
  __int64 v5; // r14
  void (__fastcall *v6)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL); // rsi
  int v7; // r8d
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  _BYTE v12[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v14[32]; // [rsp+98h] [rbp+Fh] BYREF

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v14,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusDefault");
  std::string::string(
    v13,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v13, v14, 424, this);
  std::string::~string(v13);
  std::string::~string(v14);
  EnabledStatusFromHint = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint(
                            (__int64)this,
                            *((_DWORD *)this + 43));
  v5 = *((_QWORD *)this + 47);
  v6 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL))(*(_QWORD *)v5 + 72LL);
  v8 = std::string::string(v14, "status = %d", v7);
  v9 = std::string::string(
         v13,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEna"
         "bledStatusDefault");
  v10 = std::string::string(
          v12,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v6(v5, v10, v9, 426, v8, this, EnabledStatusFromHint);
  return EnabledStatusFromHint;
}

```

## disassembly

```asm
0x14002a1f0  mov     [rsp-8+arg_8], rbx
0x14002a1f5  mov     [rsp-8+arg_10], rsi
0x14002a1fa  push    rbp
0x14002a1fb  push    rdi
0x14002a1fc  push    r13
0x14002a1fe  push    r14
0x14002a200  push    r15
0x14002a202  lea     rbp, [rsp-37h]
0x14002a207  sub     rsp, 0C0h
0x14002a20e  mov     rax, cs:__security_cookie
0x14002a215  xor     rax, rsp
0x14002a218  mov     [rbp+57h+var_28], rax
0x14002a21c  mov     r13, rcx
0x14002a21f  mov     rdi, [rcx+178h]
0x14002a226  mov     rax, [rdi]
0x14002a229  mov     rbx, [rax+28h]
0x14002a22d  lea     rdx, aMicrosoftVoice_29; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a234  lea     rcx, [rbp+57h+var_48]
0x14002a238  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a23d  nop
0x14002a23e  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a245  lea     rcx, [rbp+57h+var_68]
0x14002a249  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a24e  nop
0x14002a24f  mov     [rsp+0E0h+var_C0], r13
0x14002a254  mov     r9d, 1A8h
0x14002a25a  lea     r8, [rbp+57h+var_48]
0x14002a25e  lea     rdx, [rbp+57h+var_68]
0x14002a262  mov     rcx, rdi
0x14002a265  mov     rax, rbx
0x14002a268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a26d  nop
0x14002a26e  lea     rcx, [rbp+57h+var_68]
0x14002a272  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a277  nop
0x14002a278  lea     rcx, [rbp+57h+var_48]
0x14002a27c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a281  mov     edx, [r13+0ACh]
0x14002a288  mov     rcx, r13
0x14002a28b  call    ?GetEnabledStatusFromHint@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA_NW4AgentConfigurationSettingDefaultHint@2345@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetEnabledStatusFromHint(Microsoft::VoiceAgentServices::Windows::Settings::AgentConfigurationSettingDefaultHint)
0x14002a290  movzx   r15d, al
0x14002a294  mov     r14, [r13+178h]
0x14002a29b  mov     rcx, [r14]
0x14002a29e  mov     rsi, [rcx+48h]
0x14002a2a2  lea     rax, [rbp+57h+var_48]
0x14002a2a6  mov     [rbp+57h+var_A0], rax
0x14002a2aa  lea     rdx, aStatusD; "status = %d"
0x14002a2b1  lea     rcx, [rbp+57h+var_48]
0x14002a2b5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a2ba  mov     rdi, rax
0x14002a2bd  lea     rax, [rbp+57h+var_68]
0x14002a2c1  mov     [rbp+57h+var_98], rax
0x14002a2c5  lea     rdx, aMicrosoftVoice_29; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a2cc  lea     rcx, [rbp+57h+var_68]
0x14002a2d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a2d5  mov     rbx, rax
0x14002a2d8  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a2df  lea     rcx, [rbp+57h+var_88]
0x14002a2e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a2e8  nop
0x14002a2e9  mov     [rsp+0E0h+var_B0], r15d
0x14002a2ee  mov     [rsp+0E0h+var_B8], r13
0x14002a2f3  mov     [rsp+0E0h+var_C0], rdi
0x14002a2f8  mov     r9d, 1AAh
0x14002a2fe  mov     r8, rbx
0x14002a301  mov     rdx, rax
0x14002a304  mov     rcx, r14
0x14002a307  mov     rax, rsi
0x14002a30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a30f  mov     al, r15b
0x14002a312  mov     rcx, [rbp+57h+var_28]
0x14002a316  xor     rcx, rsp; StackCookie
0x14002a319  call    __security_check_cookie
0x14002a31e  lea     r11, [rsp+0E0h+var_20]
0x14002a326  mov     rbx, [r11+38h]
0x14002a32a  mov     rsi, [r11+40h]
0x14002a32e  mov     rsp, r11
0x14002a331  pop     r15
0x14002a333  pop     r14
0x14002a335  pop     r13
0x14002a337  pop     rdi
0x14002a338  pop     rbp
0x14002a339  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x14002a0a0`
- end: `0x14002a1e8`
- name: `?GetVoiceActivationOnLockScreenEnabledStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
- size: `328`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *, enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140031010`

## string_xrefs

- `0x14002a0ee`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a188`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a0dd`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus`
- `0x14002a175`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus`

## pseudocode

```c
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2,
        enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *a3)
{
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  __int64 v8; // r14
  void (__fastcall *v9)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v10; // r8d
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  _BYTE v15[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v16[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v17[32]; // [rsp+98h] [rbp+Fh] BYREF

  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v6 + 40LL);
  std::string::string(
    v17,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus");
  std::string::string(
    v16,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v16, v17, 61, this);
  std::string::~string(v16);
  std::string::~string(v17);
  *a2 = *((_BYTE *)this + 312);
  *(_DWORD *)a3 = *((_DWORD *)this + 79);
  v8 = *((_QWORD *)this + 47);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v8 + 72LL);
  v11 = std::string::string(v17, "hr = 0x%x", v10);
  v12 = std::string::string(
          v16,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus");
  v13 = std::string::string(
          v15,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v9(v8, v13, v12, 64, v11, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002a0a0  mov     [rsp-8+arg_18], rbx
0x14002a0a5  push    rbp
0x14002a0a6  push    rsi
0x14002a0a7  push    rdi
0x14002a0a8  push    r14
0x14002a0aa  push    r15
0x14002a0ac  lea     rbp, [rsp-37h]
0x14002a0b1  sub     rsp, 0C0h
0x14002a0b8  mov     rax, cs:__security_cookie
0x14002a0bf  xor     rax, rsp
0x14002a0c2  mov     [rbp+57h+var_28], rax
0x14002a0c6  mov     r14, r8
0x14002a0c9  mov     rsi, rdx
0x14002a0cc  mov     r15, rcx
0x14002a0cf  mov     rdi, [rcx+178h]
0x14002a0d6  mov     rax, [rdi]
0x14002a0d9  mov     rbx, [rax+28h]
0x14002a0dd  lea     rdx, aMicrosoftVoice_54; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a0e4  lea     rcx, [rbp+57h+var_48]
0x14002a0e8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a0ed  nop
0x14002a0ee  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a0f5  lea     rcx, [rbp+57h+var_68]
0x14002a0f9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a0fe  nop
0x14002a0ff  mov     [rsp+0E0h+var_C0], r15
0x14002a104  mov     r9d, 3Dh ; '='
0x14002a10a  lea     r8, [rbp+57h+var_48]
0x14002a10e  lea     rdx, [rbp+57h+var_68]
0x14002a112  mov     rcx, rdi
0x14002a115  mov     rax, rbx
0x14002a118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a11d  nop
0x14002a11e  lea     rcx, [rbp+57h+var_68]
0x14002a122  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a127  nop
0x14002a128  lea     rcx, [rbp+57h+var_48]
0x14002a12c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a131  mov     al, [r15+138h]
0x14002a138  mov     [rsi], al
0x14002a13a  mov     eax, [r15+13Ch]
0x14002a141  mov     [r14], eax
0x14002a144  mov     r14, [r15+178h]
0x14002a14b  mov     rax, [r14]
0x14002a14e  mov     rsi, [rax+48h]
0x14002a152  lea     rax, [rbp+57h+var_48]
0x14002a156  mov     [rbp+57h+var_A0], rax
0x14002a15a  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002a161  lea     rcx, [rbp+57h+var_48]
0x14002a165  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a16a  mov     rdi, rax
0x14002a16d  lea     rax, [rbp+57h+var_68]
0x14002a171  mov     [rbp+57h+var_98], rax
0x14002a175  lea     rdx, aMicrosoftVoice_54; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a17c  lea     rcx, [rbp+57h+var_68]
0x14002a180  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a185  mov     rbx, rax
0x14002a188  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a18f  lea     rcx, [rbp+57h+var_88]
0x14002a193  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a198  nop
0x14002a199  mov     [rsp+0E0h+var_B0], 0
0x14002a1a2  mov     [rsp+0E0h+var_B8], r15
0x14002a1a7  mov     [rsp+0E0h+var_C0], rdi
0x14002a1ac  mov     r9d, 40h ; '@'
0x14002a1b2  mov     r8, rbx
0x14002a1b5  mov     rdx, rax
0x14002a1b8  mov     rcx, r14
0x14002a1bb  mov     rax, rsi
0x14002a1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a1c3  xor     eax, eax
0x14002a1c5  mov     rcx, [rbp+57h+var_28]
0x14002a1c9  xor     rcx, rsp; StackCookie
0x14002a1cc  call    __security_check_cookie
0x14002a1d1  mov     rbx, [rsp+0E0h+arg_18]
0x14002a1d9  add     rsp, 0C0h
0x14002a1e0  pop     r15
0x14002a1e2  pop     r14
0x14002a1e4  pop     rdi
0x14002a1e5  pop     rsi
0x14002a1e6  pop     rbp
0x14002a1e7  retn
```

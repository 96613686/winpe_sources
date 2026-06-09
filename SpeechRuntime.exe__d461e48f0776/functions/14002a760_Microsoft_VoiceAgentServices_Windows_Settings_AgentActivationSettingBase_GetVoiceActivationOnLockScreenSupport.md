# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x14002a760`
- end: `0x14002a8a8`
- name: `?GetVoiceActivationOnLockScreenSupportedStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
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

- `0x14002a7ae`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a848`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a79d`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus`
- `0x14002a835`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus`

## pseudocode

```c
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus");
  std::string::string(
    v16,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v16, v17, 70, this);
  std::string::~string(v16);
  std::string::~string(v17);
  *a2 = *((_BYTE *)this + 320);
  *(_DWORD *)a3 = *((_DWORD *)this + 81);
  v8 = *((_QWORD *)this + 47);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v8 + 72LL);
  v11 = std::string::string(v17, "hr = 0x%x", v10);
  v12 = std::string::string(
          v16,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus");
  v13 = std::string::string(
          v15,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v9(v8, v13, v12, 73, v11, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002a760  mov     [rsp-8+arg_18], rbx
0x14002a765  push    rbp
0x14002a766  push    rsi
0x14002a767  push    rdi
0x14002a768  push    r14
0x14002a76a  push    r15
0x14002a76c  lea     rbp, [rsp-37h]
0x14002a771  sub     rsp, 0C0h
0x14002a778  mov     rax, cs:__security_cookie
0x14002a77f  xor     rax, rsp
0x14002a782  mov     [rbp+57h+var_28], rax
0x14002a786  mov     r14, r8
0x14002a789  mov     rsi, rdx
0x14002a78c  mov     r15, rcx
0x14002a78f  mov     rdi, [rcx+178h]
0x14002a796  mov     rax, [rdi]
0x14002a799  mov     rbx, [rax+28h]
0x14002a79d  lea     rdx, aMicrosoftVoice_36; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a7a4  lea     rcx, [rbp+57h+var_48]
0x14002a7a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a7ad  nop
0x14002a7ae  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a7b5  lea     rcx, [rbp+57h+var_68]
0x14002a7b9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a7be  nop
0x14002a7bf  mov     [rsp+0E0h+var_C0], r15
0x14002a7c4  mov     r9d, 46h ; 'F'
0x14002a7ca  lea     r8, [rbp+57h+var_48]
0x14002a7ce  lea     rdx, [rbp+57h+var_68]
0x14002a7d2  mov     rcx, rdi
0x14002a7d5  mov     rax, rbx
0x14002a7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a7dd  nop
0x14002a7de  lea     rcx, [rbp+57h+var_68]
0x14002a7e2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a7e7  nop
0x14002a7e8  lea     rcx, [rbp+57h+var_48]
0x14002a7ec  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a7f1  mov     al, [r15+140h]
0x14002a7f8  mov     [rsi], al
0x14002a7fa  mov     eax, [r15+144h]
0x14002a801  mov     [r14], eax
0x14002a804  mov     r14, [r15+178h]
0x14002a80b  mov     rax, [r14]
0x14002a80e  mov     rsi, [rax+48h]
0x14002a812  lea     rax, [rbp+57h+var_48]
0x14002a816  mov     [rbp+57h+var_A0], rax
0x14002a81a  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002a821  lea     rcx, [rbp+57h+var_48]
0x14002a825  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a82a  mov     rdi, rax
0x14002a82d  lea     rax, [rbp+57h+var_68]
0x14002a831  mov     [rbp+57h+var_98], rax
0x14002a835  lea     rdx, aMicrosoftVoice_36; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a83c  lea     rcx, [rbp+57h+var_68]
0x14002a840  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a845  mov     rbx, rax
0x14002a848  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a84f  lea     rcx, [rbp+57h+var_88]
0x14002a853  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a858  nop
0x14002a859  mov     [rsp+0E0h+var_B0], 0
0x14002a862  mov     [rsp+0E0h+var_B8], r15
0x14002a867  mov     [rsp+0E0h+var_C0], rdi
0x14002a86c  mov     r9d, 49h ; 'I'
0x14002a872  mov     r8, rbx
0x14002a875  mov     rdx, rax
0x14002a878  mov     rcx, r14
0x14002a87b  mov     rax, rsi
0x14002a87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a883  xor     eax, eax
0x14002a885  mov     rcx, [rbp+57h+var_28]
0x14002a889  xor     rcx, rsp; StackCookie
0x14002a88c  call    __security_check_cookie
0x14002a891  mov     rbx, [rsp+0E0h+arg_18]
0x14002a899  add     rsp, 0C0h
0x14002a8a0  pop     r15
0x14002a8a2  pop     r14
0x14002a8a4  pop     rdi
0x14002a8a5  pop     rsi
0x14002a8a6  pop     rbp
0x14002a8a7  retn
```

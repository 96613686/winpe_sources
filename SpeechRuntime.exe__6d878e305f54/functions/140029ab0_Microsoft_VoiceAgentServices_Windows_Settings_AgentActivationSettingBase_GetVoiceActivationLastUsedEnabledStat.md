# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x140029ab0`
- end: `0x140029bf8`
- name: `?GetVoiceActivationLastUsedEnabledStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
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

- `0x140029afe`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029b98`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029aed`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus`
- `0x140029b85`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus`

## pseudocode

```c
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus");
  std::string::string(
    v16,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v16, v17, 79, this);
  std::string::~string(v16);
  std::string::~string(v17);
  *a2 = *((_BYTE *)this + 336);
  *(_DWORD *)a3 = *((_DWORD *)this + 83);
  v8 = *((_QWORD *)this + 47);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v8 + 72LL);
  v11 = std::string::string(v17, "hr = 0x%x", v10);
  v12 = std::string::string(
          v16,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus");
  v13 = std::string::string(
          v15,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v9(v8, v13, v12, 82, v11, this, 0);
  return 0;
}

```

## disassembly

```asm
0x140029ab0  mov     [rsp-8+arg_18], rbx
0x140029ab5  push    rbp
0x140029ab6  push    rsi
0x140029ab7  push    rdi
0x140029ab8  push    r14
0x140029aba  push    r15
0x140029abc  lea     rbp, [rsp-37h]
0x140029ac1  sub     rsp, 0C0h
0x140029ac8  mov     rax, cs:__security_cookie
0x140029acf  xor     rax, rsp
0x140029ad2  mov     [rbp+57h+var_28], rax
0x140029ad6  mov     r14, r8
0x140029ad9  mov     rsi, rdx
0x140029adc  mov     r15, rcx
0x140029adf  mov     rdi, [rcx+178h]
0x140029ae6  mov     rax, [rdi]
0x140029ae9  mov     rbx, [rax+28h]
0x140029aed  lea     rdx, aMicrosoftVoice_22; "Microsoft::VoiceAgentServices::Windows:"...
0x140029af4  lea     rcx, [rbp+57h+var_48]
0x140029af8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029afd  nop
0x140029afe  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029b05  lea     rcx, [rbp+57h+var_68]
0x140029b09  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029b0e  nop
0x140029b0f  mov     [rsp+0E0h+var_C0], r15
0x140029b14  mov     r9d, 4Fh ; 'O'
0x140029b1a  lea     r8, [rbp+57h+var_48]
0x140029b1e  lea     rdx, [rbp+57h+var_68]
0x140029b22  mov     rcx, rdi
0x140029b25  mov     rax, rbx
0x140029b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029b2d  nop
0x140029b2e  lea     rcx, [rbp+57h+var_68]
0x140029b32  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029b37  nop
0x140029b38  lea     rcx, [rbp+57h+var_48]
0x140029b3c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029b41  mov     al, [r15+150h]
0x140029b48  mov     [rsi], al
0x140029b4a  mov     eax, [r15+14Ch]
0x140029b51  mov     [r14], eax
0x140029b54  mov     r14, [r15+178h]
0x140029b5b  mov     rax, [r14]
0x140029b5e  mov     rsi, [rax+48h]
0x140029b62  lea     rax, [rbp+57h+var_48]
0x140029b66  mov     [rbp+57h+var_A0], rax
0x140029b6a  lea     rdx, aHr0xX; "hr = 0x%x"
0x140029b71  lea     rcx, [rbp+57h+var_48]
0x140029b75  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029b7a  mov     rdi, rax
0x140029b7d  lea     rax, [rbp+57h+var_68]
0x140029b81  mov     [rbp+57h+var_98], rax
0x140029b85  lea     rdx, aMicrosoftVoice_22; "Microsoft::VoiceAgentServices::Windows:"...
0x140029b8c  lea     rcx, [rbp+57h+var_68]
0x140029b90  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029b95  mov     rbx, rax
0x140029b98  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029b9f  lea     rcx, [rbp+57h+var_88]
0x140029ba3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029ba8  nop
0x140029ba9  mov     [rsp+0E0h+var_B0], 0
0x140029bb2  mov     [rsp+0E0h+var_B8], r15
0x140029bb7  mov     [rsp+0E0h+var_C0], rdi
0x140029bbc  mov     r9d, 52h ; 'R'
0x140029bc2  mov     r8, rbx
0x140029bc5  mov     rdx, rax
0x140029bc8  mov     rcx, r14
0x140029bcb  mov     rax, rsi
0x140029bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bd3  xor     eax, eax
0x140029bd5  mov     rcx, [rbp+57h+var_28]
0x140029bd9  xor     rcx, rsp; StackCookie
0x140029bdc  call    __security_check_cookie
0x140029be1  mov     rbx, [rsp+0E0h+arg_18]
0x140029be9  add     rsp, 0C0h
0x140029bf0  pop     r15
0x140029bf2  pop     r14
0x140029bf4  pop     rdi
0x140029bf5  pop     rsi
0x140029bf6  pop     rbp
0x140029bf7  retn
```

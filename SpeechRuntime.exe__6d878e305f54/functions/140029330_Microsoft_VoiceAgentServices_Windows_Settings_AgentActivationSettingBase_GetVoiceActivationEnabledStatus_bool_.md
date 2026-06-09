# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x140029330`
- end: `0x140029478`
- name: `?GetVoiceActivationEnabledStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
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

- `0x14002937e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029418`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002936d`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus`
- `0x140029405`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus");
  std::string::string(
    v16,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v16, v17, 52, this);
  std::string::~string(v16);
  std::string::~string(v17);
  *a2 = *((_BYTE *)this + 304);
  *(_DWORD *)a3 = *((_DWORD *)this + 77);
  v8 = *((_QWORD *)this + 47);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v8 + 72LL);
  v11 = std::string::string(v17, "hr = 0x%x", v10);
  v12 = std::string::string(
          v16,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus");
  v13 = std::string::string(
          v15,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v9(v8, v13, v12, 55, v11, this, 0);
  return 0;
}

```

## disassembly

```asm
0x140029330  mov     [rsp-8+arg_18], rbx
0x140029335  push    rbp
0x140029336  push    rsi
0x140029337  push    rdi
0x140029338  push    r14
0x14002933a  push    r15
0x14002933c  lea     rbp, [rsp-37h]
0x140029341  sub     rsp, 0C0h
0x140029348  mov     rax, cs:__security_cookie
0x14002934f  xor     rax, rsp
0x140029352  mov     [rbp+57h+var_28], rax
0x140029356  mov     r14, r8
0x140029359  mov     rsi, rdx
0x14002935c  mov     r15, rcx
0x14002935f  mov     rdi, [rcx+178h]
0x140029366  mov     rax, [rdi]
0x140029369  mov     rbx, [rax+28h]
0x14002936d  lea     rdx, aMicrosoftVoice_34; "Microsoft::VoiceAgentServices::Windows:"...
0x140029374  lea     rcx, [rbp+57h+var_48]
0x140029378  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002937d  nop
0x14002937e  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029385  lea     rcx, [rbp+57h+var_68]
0x140029389  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002938e  nop
0x14002938f  mov     [rsp+0E0h+var_C0], r15
0x140029394  mov     r9d, 34h ; '4'
0x14002939a  lea     r8, [rbp+57h+var_48]
0x14002939e  lea     rdx, [rbp+57h+var_68]
0x1400293a2  mov     rcx, rdi
0x1400293a5  mov     rax, rbx
0x1400293a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400293ad  nop
0x1400293ae  lea     rcx, [rbp+57h+var_68]
0x1400293b2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400293b7  nop
0x1400293b8  lea     rcx, [rbp+57h+var_48]
0x1400293bc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400293c1  mov     al, [r15+130h]
0x1400293c8  mov     [rsi], al
0x1400293ca  mov     eax, [r15+134h]
0x1400293d1  mov     [r14], eax
0x1400293d4  mov     r14, [r15+178h]
0x1400293db  mov     rax, [r14]
0x1400293de  mov     rsi, [rax+48h]
0x1400293e2  lea     rax, [rbp+57h+var_48]
0x1400293e6  mov     [rbp+57h+var_A0], rax
0x1400293ea  lea     rdx, aHr0xX; "hr = 0x%x"
0x1400293f1  lea     rcx, [rbp+57h+var_48]
0x1400293f5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400293fa  mov     rdi, rax
0x1400293fd  lea     rax, [rbp+57h+var_68]
0x140029401  mov     [rbp+57h+var_98], rax
0x140029405  lea     rdx, aMicrosoftVoice_34; "Microsoft::VoiceAgentServices::Windows:"...
0x14002940c  lea     rcx, [rbp+57h+var_68]
0x140029410  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029415  mov     rbx, rax
0x140029418  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002941f  lea     rcx, [rbp+57h+var_88]
0x140029423  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029428  nop
0x140029429  mov     [rsp+0E0h+var_B0], 0
0x140029432  mov     [rsp+0E0h+var_B8], r15
0x140029437  mov     [rsp+0E0h+var_C0], rdi
0x14002943c  mov     r9d, 37h ; '7'
0x140029442  mov     r8, rbx
0x140029445  mov     rdx, rax
0x140029448  mov     rcx, r14
0x14002944b  mov     rax, rsi
0x14002944e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029453  xor     eax, eax
0x140029455  mov     rcx, [rbp+57h+var_28]
0x140029459  xor     rcx, rsp; StackCookie
0x14002945c  call    __security_check_cookie
0x140029461  mov     rbx, [rsp+0E0h+arg_18]
0x140029469  add     rsp, 0C0h
0x140029470  pop     r15
0x140029472  pop     r14
0x140029474  pop     rdi
0x140029475  pop     rsi
0x140029476  pop     rbp
0x140029477  retn
```

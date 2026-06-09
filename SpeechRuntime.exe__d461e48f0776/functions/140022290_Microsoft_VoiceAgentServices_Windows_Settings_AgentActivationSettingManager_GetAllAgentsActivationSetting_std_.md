# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::GetAllAgentsActivationSetting(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView> &)

- ea: `0x140022290`
- end: `0x1400223fb`
- name: `?GetAllAgentsActivationSetting@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAJAEAV?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001a500`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140020ff0`
- `0x140021658`
- `0x140021c00`
- `0x140022290`
- `0x140023728`
- `0x140031010`

## string_xrefs

- `0x1400222db`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140022333`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x14002239b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x1400222ca`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::GetAllAgentsActivationSetting`
- `0x140022388`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::GetAllAgentsActivationSetting`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::GetAllAgentsActivationSetting(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this,
        __int64 a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int valid; // eax
  unsigned int v7; // ebx
  __int64 v9; // r14
  void (__fastcall *v10)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD); // rsi
  int v11; // r8d
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  _BYTE v15[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v16[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v17[32]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v17,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::GetAllAgentsActivationSetting");
  std::string::string(
    v16,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v5(v4, v16, v17, 156);
  std::string::~string(v16);
  std::string::~string(v17);
  valid = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState(this);
  v7 = valid;
  if ( valid >= 0 )
  {
    std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::operator=(
      a2,
      (char *)this + 72);
    v9 = *((_QWORD *)this + 47);
    v10 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD))(*(_QWORD *)v9 + 72LL);
    v12 = std::string::string(v17, "hr = 0x%x", v11);
    v13 = std::string::string(
            v16,
            "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::GetAllAgentsActivationSetting");
    v14 = std::string::string(
            v15,
            "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
    v10(v9, v14, v13, 160, v12, this, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
      (const char *)(unsigned int)valid,
      (int)this);
    return v7;
  }
}

```

## disassembly

```asm
0x140022290  mov     [rsp-8+arg_10], rbx
0x140022295  push    rbp
0x140022296  push    rsi
0x140022297  push    rdi
0x140022298  push    r14
0x14002229a  push    r15
0x14002229c  lea     rbp, [rsp-37h]
0x1400222a1  sub     rsp, 0C0h
0x1400222a8  mov     rax, cs:__security_cookie
0x1400222af  xor     rax, rsp
0x1400222b2  mov     [rbp+57h+var_28], rax
0x1400222b6  mov     rsi, rdx
0x1400222b9  mov     r15, rcx
0x1400222bc  mov     rdi, [rcx+178h]
0x1400222c3  mov     rax, [rdi]
0x1400222c6  mov     rbx, [rax+28h]
0x1400222ca  lea     rdx, aMicrosoftVoice_37; "Microsoft::VoiceAgentServices::Windows:"...
0x1400222d1  lea     rcx, [rbp+57h+var_48]
0x1400222d5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400222da  nop
0x1400222db  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400222e2  lea     rcx, [rbp+57h+var_68]
0x1400222e6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400222eb  nop
0x1400222ec  mov     qword ptr [rsp+0E0h+var_C0], r15; int
0x1400222f1  mov     r9d, 9Ch
0x1400222f7  lea     r8, [rbp+57h+var_48]
0x1400222fb  lea     rdx, [rbp+57h+var_68]
0x1400222ff  mov     rcx, rdi
0x140022302  mov     rax, rbx
0x140022305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002230a  nop
0x14002230b  lea     rcx, [rbp+57h+var_68]
0x14002230f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140022314  nop
0x140022315  lea     rcx, [rbp+57h+var_48]
0x140022319  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002231e  mov     rcx, r15; this
0x140022321  call    ?TestValidState@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState(void)
0x140022326  mov     ebx, eax
0x140022328  test    eax, eax
0x14002232a  jns     short loc_14002234B
0x14002232c  mov     rcx, [rbp+5Fh]; this
0x140022330  mov     r9d, eax; char *
0x140022333  lea     r8, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002233a  mov     edx, 9Dh; void *
0x14002233f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022344  mov     eax, ebx
0x140022346  jmp     loc_1400223D8
0x14002234b  lea     rdx, [r15+48h]
0x14002234f  mov     rcx, rsi
0x140022352  call    ??4?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::operator=(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView> const &)
0x140022357  mov     r14, [r15+178h]
0x14002235e  mov     rax, [r14]
0x140022361  mov     rsi, [rax+48h]
0x140022365  lea     rax, [rbp+57h+var_48]
0x140022369  mov     [rbp+57h+var_A0], rax
0x14002236d  lea     rdx, aHr0xX; "hr = 0x%x"
0x140022374  lea     rcx, [rbp+57h+var_48]
0x140022378  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002237d  mov     rdi, rax
0x140022380  lea     rax, [rbp+57h+var_68]
0x140022384  mov     [rbp+57h+var_98], rax
0x140022388  lea     rdx, aMicrosoftVoice_37; "Microsoft::VoiceAgentServices::Windows:"...
0x14002238f  lea     rcx, [rbp+57h+var_68]
0x140022393  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022398  mov     rbx, rax
0x14002239b  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400223a2  lea     rcx, [rbp+57h+var_88]
0x1400223a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400223ab  nop
0x1400223ac  mov     [rsp+0E0h+var_B0], 0
0x1400223b5  mov     [rsp+0E0h+var_B8], r15
0x1400223ba  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x1400223bf  mov     r9d, 0A0h
0x1400223c5  mov     r8, rbx
0x1400223c8  mov     rdx, rax
0x1400223cb  mov     rcx, r14
0x1400223ce  mov     rax, rsi
0x1400223d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400223d6  xor     eax, eax
0x1400223d8  mov     rcx, [rbp+57h+var_28]
0x1400223dc  xor     rcx, rsp; StackCookie
0x1400223df  call    __security_check_cookie
0x1400223e4  mov     rbx, [rsp+0E0h+arg_10]
0x1400223ec  add     rsp, 0C0h
0x1400223f3  pop     r15
0x1400223f5  pop     r14
0x1400223f7  pop     rdi
0x1400223f8  pop     rsi
0x1400223f9  pop     rbp
0x1400223fa  retn
```

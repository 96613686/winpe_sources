# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState(void)

- ea: `0x140023728`
- end: `0x14002387b`
- name: `?TestValidState@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ`
- size: `339`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140022290`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140020ff0`
- `0x140021658`
- `0x140023728`
- `0x140031010`

## string_xrefs

- `0x14002376d`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x1400237c6`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140023822`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x14002375c`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState`
- `0x14002380f`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int v4; // r8d
  __int64 v6; // r14
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD); // rsi
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  _BYTE v11[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v12[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v13[32]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v13,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState");
  std::string::string(
    v12,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v3(v2, v12, v13, 376);
  std::string::~string(v12);
  std::string::~string(v13);
  if ( *((_BYTE *)this + 369) )
  {
    v6 = *((_QWORD *)this + 47);
    v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD))(*(_QWORD *)v6 + 72LL);
    v8 = std::string::string(v13, "hr = 0x%x", v4);
    v9 = std::string::string(
           v12,
           "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::TestValidState");
    v10 = std::string::string(
            v11,
            "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
    v7(v6, v10, v9, 378, v8, this, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x179,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
      (const char *)0x8007139FLL,
      (int)this);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x140023728  push    rbp
0x14002372a  push    rbx
0x14002372b  push    rsi
0x14002372c  push    rdi
0x14002372d  push    r14
0x14002372f  push    r15
0x140023731  lea     rbp, [rsp-2Fh]
0x140023736  sub     rsp, 0C8h
0x14002373d  mov     rax, cs:__security_cookie
0x140023744  xor     rax, rsp
0x140023747  mov     [rbp+57h+var_38], rax
0x14002374b  mov     r15, rcx
0x14002374e  mov     rdi, [rcx+178h]
0x140023755  mov     rax, [rdi]
0x140023758  mov     rbx, [rax+28h]
0x14002375c  lea     rdx, aMicrosoftVoice_15; "Microsoft::VoiceAgentServices::Windows:"...
0x140023763  lea     rcx, [rbp+57h+var_58]
0x140023767  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002376c  nop
0x14002376d  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140023774  lea     rcx, [rbp+57h+var_78]
0x140023778  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002377d  nop
0x14002377e  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x140023783  mov     r9d, 178h
0x140023789  lea     r8, [rbp+57h+var_58]
0x14002378d  lea     rdx, [rbp+57h+var_78]
0x140023791  mov     rcx, rdi
0x140023794  mov     rax, rbx
0x140023797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002379c  nop
0x14002379d  lea     rcx, [rbp+57h+var_78]
0x1400237a1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400237a6  nop
0x1400237a7  lea     rcx, [rbp+57h+var_58]
0x1400237ab  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400237b0  cmp     byte ptr [r15+171h], 0
0x1400237b8  jnz     short loc_1400237DE
0x1400237ba  mov     rcx, [rbp+5Fh]; this
0x1400237be  mov     ebx, 8007139Fh
0x1400237c3  mov     r9d, ebx; char *
0x1400237c6  lea     r8, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400237cd  mov     edx, 179h; void *
0x1400237d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400237d7  mov     eax, ebx
0x1400237d9  jmp     loc_14002385F
0x1400237de  mov     r14, [r15+178h]
0x1400237e5  mov     rax, [r14]
0x1400237e8  mov     rsi, [rax+48h]
0x1400237ec  lea     rax, [rbp+57h+var_58]
0x1400237f0  mov     [rbp+57h+var_B0], rax
0x1400237f4  lea     rdx, aHr0xX; "hr = 0x%x"
0x1400237fb  lea     rcx, [rbp+57h+var_58]
0x1400237ff  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140023804  mov     rdi, rax
0x140023807  lea     rax, [rbp+57h+var_78]
0x14002380b  mov     [rbp+57h+var_A8], rax
0x14002380f  lea     rdx, aMicrosoftVoice_15; "Microsoft::VoiceAgentServices::Windows:"...
0x140023816  lea     rcx, [rbp+57h+var_78]
0x14002381a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002381f  mov     rbx, rax
0x140023822  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140023829  lea     rcx, [rbp+57h+var_98]
0x14002382d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140023832  nop
0x140023833  mov     [rsp+0F0h+var_C0], 0
0x14002383c  mov     [rsp+0F0h+var_C8], r15
0x140023841  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x140023846  mov     r9d, 17Ah
0x14002384c  mov     r8, rbx
0x14002384f  mov     rdx, rax
0x140023852  mov     rcx, r14
0x140023855  mov     rax, rsi
0x140023858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002385d  xor     eax, eax
0x14002385f  mov     rcx, [rbp+57h+var_38]
0x140023863  xor     rcx, rsp; StackCookie
0x140023866  call    __security_check_cookie
0x14002386b  add     rsp, 0C8h
0x140023872  pop     r15
0x140023874  pop     r14
0x140023876  pop     rdi
0x140023877  pop     rsi
0x140023878  pop     rbx
0x140023879  pop     rbp
0x14002387a  retn
```

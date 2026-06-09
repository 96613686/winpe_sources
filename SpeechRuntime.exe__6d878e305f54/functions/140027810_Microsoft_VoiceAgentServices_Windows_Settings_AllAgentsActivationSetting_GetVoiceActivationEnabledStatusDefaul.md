# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationEnabledStatusDefault(void)

- ea: `0x140027810`
- end: `0x140027934`
- name: `?GetVoiceActivationEnabledStatusDefault@AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@MEAA_NXZ`
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

- `0x140027855`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x1400278dc`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027844`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationEnabledStatusDefault`
- `0x1400278c9`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationEnabledStatusDefault`

## pseudocode

```c
char __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationEnabledStatusDefault(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationEnabledStatusDefault");
  std::string::string(
    v12,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v3(v2, v12, v13, 53, this);
  std::string::~string(v12);
  std::string::~string(v13);
  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, int))(*(_QWORD *)v4 + 72LL);
  v7 = std::string::string(v13, "enabled = %d", v6);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::GetVoiceActivationEnabledStatusDefault");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v5(v4, v9, v8, 56, v7, this, 1);
  return 1;
}

```

## disassembly

```asm
0x140027810  push    rbp
0x140027812  push    rbx
0x140027813  push    rsi
0x140027814  push    rdi
0x140027815  push    r14
0x140027817  push    r15
0x140027819  lea     rbp, [rsp-2Fh]
0x14002781e  sub     rsp, 0C8h
0x140027825  mov     rax, cs:__security_cookie
0x14002782c  xor     rax, rsp
0x14002782f  mov     [rbp+57h+var_38], rax
0x140027833  mov     r15, rcx
0x140027836  mov     rdi, [rcx+178h]
0x14002783d  mov     rax, [rdi]
0x140027840  mov     rbx, [rax+28h]
0x140027844  lea     rdx, aMicrosoftVoice_45; "Microsoft::VoiceAgentServices::Windows:"...
0x14002784b  lea     rcx, [rbp+57h+var_58]
0x14002784f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027854  nop
0x140027855  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002785c  lea     rcx, [rbp+57h+var_78]
0x140027860  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027865  nop
0x140027866  mov     [rsp+0F0h+var_D0], r15
0x14002786b  mov     r9d, 35h ; '5'
0x140027871  lea     r8, [rbp+57h+var_58]
0x140027875  lea     rdx, [rbp+57h+var_78]
0x140027879  mov     rcx, rdi
0x14002787c  mov     rax, rbx
0x14002787f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027884  nop
0x140027885  lea     rcx, [rbp+57h+var_78]
0x140027889  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002788e  nop
0x14002788f  lea     rcx, [rbp+57h+var_58]
0x140027893  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140027898  mov     r14, [r15+178h]
0x14002789f  mov     rax, [r14]
0x1400278a2  mov     rsi, [rax+48h]
0x1400278a6  lea     rax, [rbp+57h+var_58]
0x1400278aa  mov     [rbp+57h+var_B0], rax
0x1400278ae  lea     rdx, aEnabledD; "enabled = %d"
0x1400278b5  lea     rcx, [rbp+57h+var_58]
0x1400278b9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400278be  mov     rdi, rax
0x1400278c1  lea     rax, [rbp+57h+var_78]
0x1400278c5  mov     [rbp+57h+var_A8], rax
0x1400278c9  lea     rdx, aMicrosoftVoice_45; "Microsoft::VoiceAgentServices::Windows:"...
0x1400278d0  lea     rcx, [rbp+57h+var_78]
0x1400278d4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400278d9  mov     rbx, rax
0x1400278dc  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400278e3  lea     rcx, [rbp+57h+var_98]
0x1400278e7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400278ec  nop
0x1400278ed  mov     [rsp+0F0h+var_C0], 1
0x1400278f5  mov     [rsp+0F0h+var_C8], r15
0x1400278fa  mov     [rsp+0F0h+var_D0], rdi
0x1400278ff  mov     r9d, 38h ; '8'
0x140027905  mov     r8, rbx
0x140027908  mov     rdx, rax
0x14002790b  mov     rcx, r14
0x14002790e  mov     rax, rsi
0x140027911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027916  mov     al, 1
0x140027918  mov     rcx, [rbp+57h+var_38]
0x14002791c  xor     rcx, rsp; StackCookie
0x14002791f  call    __security_check_cookie
0x140027924  add     rsp, 0C8h
0x14002792b  pop     r15
0x14002792d  pop     r14
0x14002792f  pop     rdi
0x140027930  pop     rsi
0x140027931  pop     rbx
0x140027932  pop     rbp
0x140027933  retn
```

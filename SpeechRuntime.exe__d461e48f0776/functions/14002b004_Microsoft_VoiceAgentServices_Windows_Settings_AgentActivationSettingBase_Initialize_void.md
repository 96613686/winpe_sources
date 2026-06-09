# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize(void)

- ea: `0x14002b004`
- end: `0x14002b19a`
- name: `?Initialize@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@IEAAJXZ`
- size: `406`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400275ec`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140020ff0`
- `0x140021658`
- `0x14002b004`
- `0x14002c0f0`
- `0x14002cba4`
- `0x140031010`

## string_xrefs

- `0x14002b052`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b041`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize`
- `0x14002b126`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int InitialValues; // ebx
  __int64 v5; // rdx
  int v7; // r8d
  __int64 v8; // r14
  void (__fastcall *v9)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  _BYTE v13[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v14[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v15[32]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v2 + 40LL);
  std::string::string(v15, "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize");
  std::string::string(
    v14,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v14, v15, 210);
  std::string::~string(v14);
  std::string::~string(v15);
  InitialValues = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)this + 136LL))(this);
  if ( InitialValues < 0 )
  {
    v5 = 211;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)InitialValues,
      (int)this);
    return (unsigned int)InitialValues;
  }
  InitialValues = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues(this);
  if ( InitialValues < 0 )
  {
    v5 = 212;
    goto LABEL_3;
  }
  InitialValues = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates(this);
  if ( InitialValues < 0 )
  {
    v5 = 213;
    goto LABEL_3;
  }
  v8 = *((_QWORD *)this + 47);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v8 + 72LL);
  v10 = std::string::string(v15, "hr = 0x%x", v7);
  v11 = std::string::string(
          v14,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize");
  v12 = std::string::string(
          v13,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v9(v8, v12, v11, 214, v10, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002b004  mov     [rsp-8+arg_8], rbx
0x14002b009  mov     [rsp-8+arg_10], rsi
0x14002b00e  push    rbp
0x14002b00f  push    rdi
0x14002b010  push    r12
0x14002b012  push    r14
0x14002b014  push    r15
0x14002b016  lea     rbp, [rsp-37h]
0x14002b01b  sub     rsp, 0C0h
0x14002b022  mov     rax, cs:__security_cookie
0x14002b029  xor     rax, rsp
0x14002b02c  mov     [rbp+57h+var_28], rax
0x14002b030  mov     r15, rcx
0x14002b033  mov     rdi, [rcx+178h]
0x14002b03a  mov     rax, [rdi]
0x14002b03d  mov     rbx, [rax+28h]
0x14002b041  lea     rdx, aMicrosoftVoice_24; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b048  lea     rcx, [rbp+57h+var_48]
0x14002b04c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b051  nop
0x14002b052  lea     r12, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b059  mov     rdx, r12
0x14002b05c  lea     rcx, [rbp+57h+var_68]
0x14002b060  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b065  nop
0x14002b066  mov     qword ptr [rsp+0E0h+var_C0], r15; int
0x14002b06b  mov     r9d, 0D2h
0x14002b071  lea     r8, [rbp+57h+var_48]
0x14002b075  lea     rdx, [rbp+57h+var_68]
0x14002b079  mov     rcx, rdi
0x14002b07c  mov     rax, rbx
0x14002b07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b084  nop
0x14002b085  lea     rcx, [rbp+57h+var_68]
0x14002b089  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b08e  nop
0x14002b08f  lea     rcx, [rbp+57h+var_48]
0x14002b093  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b098  mov     rax, [r15]
0x14002b09b  mov     rcx, r15
0x14002b09e  mov     rax, [rax+88h]
0x14002b0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b0aa  mov     ebx, eax
0x14002b0ac  test    eax, eax
0x14002b0ae  jns     short loc_14002B0CB
0x14002b0b0  mov     edx, 0D3h; void *
0x14002b0b5  mov     rcx, [rbp+5Fh]; this
0x14002b0b9  mov     r9d, ebx; char *
0x14002b0bc  mov     r8, r12; unsigned int
0x14002b0bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b0c4  mov     eax, ebx
0x14002b0c6  jmp     loc_14002B172
0x14002b0cb  mov     rcx, r15; this
0x14002b0ce  call    ?QueryInitialValues@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues(void)
0x14002b0d3  mov     ebx, eax
0x14002b0d5  test    eax, eax
0x14002b0d7  jns     short loc_14002B0E0
0x14002b0d9  mov     edx, 0D4h
0x14002b0de  jmp     short loc_14002B0B5
0x14002b0e0  mov     rcx, r15; this
0x14002b0e3  call    ?SetupMonitorsForUpdates@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates(void)
0x14002b0e8  mov     ebx, eax
0x14002b0ea  test    eax, eax
0x14002b0ec  jns     short loc_14002B0F5
0x14002b0ee  mov     edx, 0D5h
0x14002b0f3  jmp     short loc_14002B0B5
0x14002b0f5  mov     r14, [r15+178h]
0x14002b0fc  mov     rax, [r14]
0x14002b0ff  mov     rsi, [rax+48h]
0x14002b103  lea     rax, [rbp+57h+var_48]
0x14002b107  mov     [rbp+57h+var_A0], rax
0x14002b10b  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002b112  lea     rcx, [rbp+57h+var_48]
0x14002b116  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b11b  mov     rdi, rax
0x14002b11e  lea     rax, [rbp+57h+var_68]
0x14002b122  mov     [rbp+57h+var_98], rax
0x14002b126  lea     rdx, aMicrosoftVoice_24; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b12d  lea     rcx, [rbp+57h+var_68]
0x14002b131  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b136  mov     rbx, rax
0x14002b139  mov     rdx, r12
0x14002b13c  lea     rcx, [rbp+57h+var_88]
0x14002b140  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b145  nop
0x14002b146  mov     [rsp+0E0h+var_B0], 0
0x14002b14f  mov     [rsp+0E0h+var_B8], r15
0x14002b154  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x14002b159  mov     r9d, 0D6h
0x14002b15f  mov     r8, rbx
0x14002b162  mov     rdx, rax
0x14002b165  mov     rcx, r14
0x14002b168  mov     rax, rsi
0x14002b16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b170  xor     eax, eax
0x14002b172  mov     rcx, [rbp+57h+var_28]
0x14002b176  xor     rcx, rsp; StackCookie
0x14002b179  call    __security_check_cookie
0x14002b17e  lea     r11, [rsp+0E0h+var_20]
0x14002b186  mov     rbx, [r11+38h]
0x14002b18a  mov     rsi, [r11+40h]
0x14002b18e  mov     rsp, r11
0x14002b191  pop     r15
0x14002b193  pop     r14
0x14002b195  pop     r12
0x14002b197  pop     rdi
0x14002b198  pop     rbp
0x14002b199  retn
```

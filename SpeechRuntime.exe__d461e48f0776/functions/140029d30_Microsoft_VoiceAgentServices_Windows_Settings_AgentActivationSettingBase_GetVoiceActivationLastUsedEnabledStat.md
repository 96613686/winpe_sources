# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusInternal(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x140029d30`
- end: `0x140029ee5`
- name: `?GetVoiceActivationLastUsedEnabledStatusInternal@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
- size: `437`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *, enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x14002837c`
- `0x140029d30`
- `0x140031010`

## string_xrefs

- `0x140029d7e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029de8`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029e85`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029d6d`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusInternal`
- `0x140029e72`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusInternal(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2,
        enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *a3)
{
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  char v11; // al
  __int64 v12; // r14
  void (__fastcall *v13)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v14; // r8d
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  _BYTE v18[8]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v6 + 40LL);
  std::string::string(
    v22,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatusInternal");
  std::string::string(
    v21,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v21, v22, 405);
  std::string::~string(v21);
  std::string::~string(v22);
  v18[0] = 0;
  v8 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _BYTE *))(*(_QWORD *)this + 128LL))(
         this,
         v18);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v8 == 1 )
      v11 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)this + 168LL))(this);
    else
      v11 = v18[0];
    *a2 = v11;
    *(_DWORD *)a3 = 0;
    v19[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
    Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationLastUsedEnabledStatus<unsigned short const *,bool &,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(
      v19,
      a2,
      a3);
    v12 = *((_QWORD *)this + 47);
    v13 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v12 + 72LL);
    v19[0] = v22;
    v15 = std::string::string(v22, "hr = 0x%x", v14);
    v19[1] = v21;
    v16 = std::string::string(
            v21,
            "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnab"
            "ledStatusInternal");
    v17 = std::string::string(
            v20,
            "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
    v13(v12, v17, v16, 412, v15, this, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)v8,
      (int)this);
    return v9;
  }
}

```

## disassembly

```asm
0x140029d30  mov     [rsp-8+arg_18], rbx
0x140029d35  push    rbp
0x140029d36  push    rsi
0x140029d37  push    rdi
0x140029d38  push    r14
0x140029d3a  push    r15
0x140029d3c  lea     rbp, [rsp-37h]
0x140029d41  sub     rsp, 0D0h
0x140029d48  mov     rax, cs:__security_cookie
0x140029d4f  xor     rax, rsp
0x140029d52  mov     [rbp+57h+var_30], rax
0x140029d56  mov     r14, r8
0x140029d59  mov     rsi, rdx
0x140029d5c  mov     r15, rcx
0x140029d5f  mov     rdi, [rcx+178h]
0x140029d66  mov     rax, [rdi]
0x140029d69  mov     rbx, [rax+28h]
0x140029d6d  lea     rdx, aMicrosoftVoice_18; "Microsoft::VoiceAgentServices::Windows:"...
0x140029d74  lea     rcx, [rbp+57h+var_50]
0x140029d78  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029d7d  nop
0x140029d7e  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029d85  lea     rcx, [rbp+57h+var_70]
0x140029d89  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029d8e  nop
0x140029d8f  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x140029d94  mov     r9d, 195h
0x140029d9a  lea     r8, [rbp+57h+var_50]
0x140029d9e  lea     rdx, [rbp+57h+var_70]
0x140029da2  mov     rcx, rdi
0x140029da5  mov     rax, rbx
0x140029da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029dad  nop
0x140029dae  lea     rcx, [rbp+57h+var_70]
0x140029db2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029db7  nop
0x140029db8  lea     rcx, [rbp+57h+var_50]
0x140029dbc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029dc1  mov     [rbp+57h+var_B0], 0
0x140029dc5  mov     rax, [r15]
0x140029dc8  lea     rdx, [rbp+57h+var_B0]
0x140029dcc  mov     rcx, r15
0x140029dcf  mov     rax, [rax+80h]
0x140029dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029ddb  mov     ebx, eax
0x140029ddd  test    eax, eax
0x140029ddf  jns     short loc_140029E00
0x140029de1  mov     rcx, [rbp+5Fh]; this
0x140029de5  mov     r9d, eax; char *
0x140029de8  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029def  mov     edx, 198h; void *
0x140029df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140029df9  mov     eax, ebx
0x140029dfb  jmp     loc_140029EC2
0x140029e00  cmp     ebx, 1
0x140029e03  jnz     short loc_140029E19
0x140029e05  mov     rax, [r15]
0x140029e08  mov     rcx, r15
0x140029e0b  mov     rax, [rax+0A8h]
0x140029e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029e17  jmp     short loc_140029E1C
0x140029e19  mov     al, [rbp+57h+var_B0]
0x140029e1c  mov     [rsi], al
0x140029e1e  mov     dword ptr [r14], 0
0x140029e25  lea     rcx, [r15+20h]
0x140029e29  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029e2e  mov     [rbp+57h+var_A8], rax
0x140029e32  mov     r8, r14
0x140029e35  mov     rdx, rsi
0x140029e38  lea     rcx, [rbp+57h+var_A8]
0x140029e3c  call    ??$VoiceActivationLastUsedEnabledStatus@PEBGAEA_NAEAW4AgentActivationStatusDisabledReason@Settings@Windows@VoiceAgentServices@Microsoft@@@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEA_NAEAW4AgentActivationStatusDisabledReason@1234@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationLastUsedEnabledStatus<ushort const *,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(ushort const * &&,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)
0x140029e41  mov     r14, [r15+178h]
0x140029e48  mov     rax, [r14]
0x140029e4b  mov     rsi, [rax+48h]
0x140029e4f  lea     rax, [rbp+57h+var_50]
0x140029e53  mov     [rbp+57h+var_A8], rax
0x140029e57  lea     rdx, aHr0xX; "hr = 0x%x"
0x140029e5e  lea     rcx, [rbp+57h+var_50]
0x140029e62  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029e67  mov     rdi, rax
0x140029e6a  lea     rax, [rbp+57h+var_70]
0x140029e6e  mov     [rbp+57h+var_A0], rax
0x140029e72  lea     rdx, aMicrosoftVoice_18; "Microsoft::VoiceAgentServices::Windows:"...
0x140029e79  lea     rcx, [rbp+57h+var_70]
0x140029e7d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029e82  mov     rbx, rax
0x140029e85  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029e8c  lea     rcx, [rbp+57h+var_90]
0x140029e90  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029e95  nop
0x140029e96  mov     [rsp+0F0h+var_C0], 0
0x140029e9f  mov     [rsp+0F0h+var_C8], r15
0x140029ea4  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x140029ea9  mov     r9d, 19Ch
0x140029eaf  mov     r8, rbx
0x140029eb2  mov     rdx, rax
0x140029eb5  mov     rcx, r14
0x140029eb8  mov     rax, rsi
0x140029ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029ec0  xor     eax, eax
0x140029ec2  mov     rcx, [rbp+57h+var_30]
0x140029ec6  xor     rcx, rsp; StackCookie
0x140029ec9  call    __security_check_cookie
0x140029ece  mov     rbx, [rsp+0F0h+arg_18]
0x140029ed6  add     rsp, 0D0h
0x140029edd  pop     r15
0x140029edf  pop     r14
0x140029ee1  pop     rdi
0x140029ee2  pop     rsi
0x140029ee3  pop     rbp
0x140029ee4  retn
```

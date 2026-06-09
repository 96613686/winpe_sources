# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusInternal(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x14002a9e0`
- end: `0x14002ab92`
- name: `?GetVoiceActivationOnLockScreenSupportedStatusInternal@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
- size: `434`
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
- `0x14002850c`
- `0x14002a9e0`
- `0x140031010`

## string_xrefs

- `0x14002aa2e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002aa95`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002ab32`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002aa1d`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusInternal`
- `0x14002ab1f`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusInternal(
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
  char v18[8]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v6 + 40LL);
  std::string::string(
    v22,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatusInternal");
  std::string::string(
    v21,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v21, v22, 392);
  std::string::~string(v21);
  std::string::~string(v22);
  v18[0] = 1;
  v8 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *))(*(_QWORD *)this + 120LL))(
         this,
         v18);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v8 == 1 )
      v11 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)this + 160LL))(this);
    else
      v11 = v18[0];
    *a2 = v11;
    *(_DWORD *)a3 = 0;
    v19[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
    Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenSupportedStatus<unsigned short const *,bool &,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(
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
            "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreen"
            "SupportedStatusInternal");
    v17 = std::string::string(
            v20,
            "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
    v13(v12, v17, v16, 399, v15, this, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)v8,
      (int)this);
    return v9;
  }
}

```

## disassembly

```asm
0x14002a9e0  mov     [rsp-8+arg_18], rbx
0x14002a9e5  push    rbp
0x14002a9e6  push    rsi
0x14002a9e7  push    rdi
0x14002a9e8  push    r14
0x14002a9ea  push    r15
0x14002a9ec  lea     rbp, [rsp-37h]
0x14002a9f1  sub     rsp, 0D0h
0x14002a9f8  mov     rax, cs:__security_cookie
0x14002a9ff  xor     rax, rsp
0x14002aa02  mov     [rbp+57h+var_30], rax
0x14002aa06  mov     r14, r8
0x14002aa09  mov     rsi, rdx
0x14002aa0c  mov     r15, rcx
0x14002aa0f  mov     rdi, [rcx+178h]
0x14002aa16  mov     rax, [rdi]
0x14002aa19  mov     rbx, [rax+28h]
0x14002aa1d  lea     rdx, aMicrosoftVoice_35; "Microsoft::VoiceAgentServices::Windows:"...
0x14002aa24  lea     rcx, [rbp+57h+var_50]
0x14002aa28  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002aa2d  nop
0x14002aa2e  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002aa35  lea     rcx, [rbp+57h+var_70]
0x14002aa39  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002aa3e  nop
0x14002aa3f  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x14002aa44  mov     r9d, 188h
0x14002aa4a  lea     r8, [rbp+57h+var_50]
0x14002aa4e  lea     rdx, [rbp+57h+var_70]
0x14002aa52  mov     rcx, rdi
0x14002aa55  mov     rax, rbx
0x14002aa58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa5d  nop
0x14002aa5e  lea     rcx, [rbp+57h+var_70]
0x14002aa62  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002aa67  nop
0x14002aa68  lea     rcx, [rbp+57h+var_50]
0x14002aa6c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002aa71  mov     [rbp+57h+var_B0], 1
0x14002aa75  mov     rax, [r15]
0x14002aa78  lea     rdx, [rbp+57h+var_B0]
0x14002aa7c  mov     rcx, r15
0x14002aa7f  mov     rax, [rax+78h]
0x14002aa83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa88  mov     ebx, eax
0x14002aa8a  test    eax, eax
0x14002aa8c  jns     short loc_14002AAAD
0x14002aa8e  mov     rcx, [rbp+5Fh]; this
0x14002aa92  mov     r9d, eax; char *
0x14002aa95  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002aa9c  mov     edx, 18Bh; void *
0x14002aaa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002aaa6  mov     eax, ebx
0x14002aaa8  jmp     loc_14002AB6F
0x14002aaad  cmp     ebx, 1
0x14002aab0  jnz     short loc_14002AAC6
0x14002aab2  mov     rax, [r15]
0x14002aab5  mov     rcx, r15
0x14002aab8  mov     rax, [rax+0A0h]
0x14002aabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aac4  jmp     short loc_14002AAC9
0x14002aac6  mov     al, [rbp+57h+var_B0]
0x14002aac9  mov     [rsi], al
0x14002aacb  mov     dword ptr [r14], 0
0x14002aad2  lea     rcx, [r15+20h]
0x14002aad6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002aadb  mov     [rbp+57h+var_A8], rax
0x14002aadf  mov     r8, r14
0x14002aae2  mov     rdx, rsi
0x14002aae5  lea     rcx, [rbp+57h+var_A8]
0x14002aae9  call    ??$VoiceActivationOnLockScreenSupportedStatus@PEBGAEA_NAEAW4AgentActivationStatusDisabledReason@Settings@Windows@VoiceAgentServices@Microsoft@@@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEA_NAEAW4AgentActivationStatusDisabledReason@1234@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenSupportedStatus<ushort const *,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(ushort const * &&,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)
0x14002aaee  mov     r14, [r15+178h]
0x14002aaf5  mov     rax, [r14]
0x14002aaf8  mov     rsi, [rax+48h]
0x14002aafc  lea     rax, [rbp+57h+var_50]
0x14002ab00  mov     [rbp+57h+var_A8], rax
0x14002ab04  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002ab0b  lea     rcx, [rbp+57h+var_50]
0x14002ab0f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ab14  mov     rdi, rax
0x14002ab17  lea     rax, [rbp+57h+var_70]
0x14002ab1b  mov     [rbp+57h+var_A0], rax
0x14002ab1f  lea     rdx, aMicrosoftVoice_35; "Microsoft::VoiceAgentServices::Windows:"...
0x14002ab26  lea     rcx, [rbp+57h+var_70]
0x14002ab2a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ab2f  mov     rbx, rax
0x14002ab32  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002ab39  lea     rcx, [rbp+57h+var_90]
0x14002ab3d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ab42  nop
0x14002ab43  mov     [rsp+0F0h+var_C0], 0
0x14002ab4c  mov     [rsp+0F0h+var_C8], r15
0x14002ab51  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x14002ab56  mov     r9d, 18Fh
0x14002ab5c  mov     r8, rbx
0x14002ab5f  mov     rdx, rax
0x14002ab62  mov     rcx, r14
0x14002ab65  mov     rax, rsi
0x14002ab68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ab6d  xor     eax, eax
0x14002ab6f  mov     rcx, [rbp+57h+var_30]
0x14002ab73  xor     rcx, rsp; StackCookie
0x14002ab76  call    __security_check_cookie
0x14002ab7b  mov     rbx, [rsp+0F0h+arg_18]
0x14002ab83  add     rsp, 0D0h
0x14002ab8a  pop     r15
0x14002ab8c  pop     r14
0x14002ab8e  pop     rdi
0x14002ab8f  pop     rsi
0x14002ab90  pop     rbp
0x14002ab91  retn
```

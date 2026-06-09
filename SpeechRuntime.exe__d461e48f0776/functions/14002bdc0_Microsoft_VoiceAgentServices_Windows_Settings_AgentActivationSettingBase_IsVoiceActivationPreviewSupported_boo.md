# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported(bool &)

- ea: `0x14002bdc0`
- end: `0x14002bf86`
- name: `?IsVoiceActivationPreviewSupported@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_N@Z`
- size: `454`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140031010`

## string_xrefs

- `0x14002be11`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002bea3`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002bf21`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002be00`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported`
- `0x14002be90`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported`
- `0x14002bf0e`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  int v6; // esi
  __int64 v7; // r15
  void (__fastcall *v8)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, int); // r14
  int v9; // r8d
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r14
  void (__fastcall *v14)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v15; // r8d
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  _BYTE v20[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v21[32]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v22[32]; // [rsp+A8h] [rbp+Fh] BYREF

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v22,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported");
  std::string::string(
    v21,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v21, v22, 579, this);
  std::string::~string(v21);
  std::string::~string(v22);
  v6 = *((unsigned __int8 *)this + 180);
  *a2 = v6;
  v7 = *((_QWORD *)this + 47);
  v8 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, int))(*(_QWORD *)v7 + 16LL);
  v10 = std::string::string(v22, "voiceActivationPreviewSupported = %d", v9);
  v11 = std::string::string(
          v21,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported");
  v12 = std::string::string(
          v20,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v8(v7, 0, v12, v11, 581, v10, this, v6);
  v13 = *((_QWORD *)this + 47);
  v14 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v13 + 72LL);
  v16 = std::string::string(v20, "hr = 0x%x", v15);
  v17 = std::string::string(
          v22,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsVoiceActivationPreviewSupported");
  v18 = std::string::string(
          v21,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v14(v13, v18, v17, 582, v16, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002bdc0  mov     [rsp-8+arg_10], rbx
0x14002bdc5  mov     [rsp-8+arg_18], rsi
0x14002bdca  push    rbp
0x14002bdcb  push    rdi
0x14002bdcc  push    r13
0x14002bdce  push    r14
0x14002bdd0  push    r15
0x14002bdd2  lea     rbp, [rsp-37h]
0x14002bdd7  sub     rsp, 0D0h
0x14002bdde  mov     rax, cs:__security_cookie
0x14002bde5  xor     rax, rsp
0x14002bde8  mov     [rbp+57h+var_28], rax
0x14002bdec  mov     r14, rdx
0x14002bdef  mov     r13, rcx
0x14002bdf2  mov     rdi, [rcx+178h]
0x14002bdf9  mov     rax, [rdi]
0x14002bdfc  mov     rbx, [rax+28h]
0x14002be00  lea     rdx, aMicrosoftVoice_31; "Microsoft::VoiceAgentServices::Windows:"...
0x14002be07  lea     rcx, [rbp+57h+var_48]
0x14002be0b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002be10  nop
0x14002be11  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002be18  lea     rcx, [rbp+57h+var_68]
0x14002be1c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002be21  nop
0x14002be22  mov     [rsp+0F0h+var_D0], r13
0x14002be27  mov     r9d, 243h
0x14002be2d  lea     r8, [rbp+57h+var_48]
0x14002be31  lea     rdx, [rbp+57h+var_68]
0x14002be35  mov     rcx, rdi
0x14002be38  mov     rax, rbx
0x14002be3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002be40  nop
0x14002be41  lea     rcx, [rbp+57h+var_68]
0x14002be45  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002be4a  nop
0x14002be4b  lea     rcx, [rbp+57h+var_48]
0x14002be4f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002be54  movzx   esi, byte ptr [r13+0B4h]
0x14002be5c  mov     [r14], sil
0x14002be5f  mov     r15, [r13+178h]
0x14002be66  mov     rax, [r15]
0x14002be69  mov     r14, [rax+10h]
0x14002be6d  lea     rax, [rbp+57h+var_48]
0x14002be71  mov     [rbp+57h+var_A0], rax
0x14002be75  lea     rdx, aVoiceactivatio_0; "voiceActivationPreviewSupported = %d"
0x14002be7c  lea     rcx, [rbp+57h+var_48]
0x14002be80  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002be85  mov     rdi, rax
0x14002be88  lea     rax, [rbp+57h+var_68]
0x14002be8c  mov     [rbp+57h+var_98], rax
0x14002be90  lea     rdx, aMicrosoftVoice_31; "Microsoft::VoiceAgentServices::Windows:"...
0x14002be97  lea     rcx, [rbp+57h+var_68]
0x14002be9b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bea0  mov     rbx, rax
0x14002bea3  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002beaa  lea     rcx, [rbp+57h+var_88]
0x14002beae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002beb3  nop
0x14002beb4  mov     [rsp+0F0h+var_B8], esi
0x14002beb8  mov     [rsp+0F0h+var_C0], r13
0x14002bebd  mov     [rsp+0F0h+var_C8], rdi
0x14002bec2  mov     dword ptr [rsp+0F0h+var_D0], 245h
0x14002beca  mov     r9, rbx
0x14002becd  mov     r8, rax
0x14002bed0  xor     edx, edx
0x14002bed2  mov     rcx, r15
0x14002bed5  mov     rax, r14
0x14002bed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bedd  mov     r14, [r13+178h]
0x14002bee4  mov     rax, [r14]
0x14002bee7  mov     rsi, [rax+48h]
0x14002beeb  lea     rax, [rbp+57h+var_88]
0x14002beef  mov     [rbp+57h+var_90], rax
0x14002bef3  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002befa  lea     rcx, [rbp+57h+var_88]
0x14002befe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bf03  mov     rdi, rax
0x14002bf06  lea     rax, [rbp+57h+var_48]
0x14002bf0a  mov     [rbp+57h+var_98], rax
0x14002bf0e  lea     rdx, aMicrosoftVoice_31; "Microsoft::VoiceAgentServices::Windows:"...
0x14002bf15  lea     rcx, [rbp+57h+var_48]
0x14002bf19  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bf1e  mov     rbx, rax
0x14002bf21  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002bf28  lea     rcx, [rbp+57h+var_68]
0x14002bf2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bf31  nop
0x14002bf32  mov     [rsp+0F0h+var_C0], 0
0x14002bf3b  mov     [rsp+0F0h+var_C8], r13
0x14002bf40  mov     [rsp+0F0h+var_D0], rdi
0x14002bf45  mov     r9d, 246h
0x14002bf4b  mov     r8, rbx
0x14002bf4e  mov     rdx, rax
0x14002bf51  mov     rcx, r14
0x14002bf54  mov     rax, rsi
0x14002bf57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bf5c  xor     eax, eax
0x14002bf5e  mov     rcx, [rbp+57h+var_28]
0x14002bf62  xor     rcx, rsp; StackCookie
0x14002bf65  call    __security_check_cookie
0x14002bf6a  lea     r11, [rsp+0F0h+var_20]
0x14002bf72  mov     rbx, [r11+40h]
0x14002bf76  mov     rsi, [r11+48h]
0x14002bf7a  mov     rsp, r11
0x14002bf7d  pop     r15
0x14002bf7f  pop     r14
0x14002bf81  pop     r13
0x14002bf83  pop     rdi
0x14002bf84  pop     rbp
0x14002bf85  retn
```

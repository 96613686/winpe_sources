# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusInternal(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x14002a340`
- end: `0x14002a59b`
- name: `?GetVoiceActivationOnLockScreenEnabledStatusInternal@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
- size: `603`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *, enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140021c8c`
- `0x140025768`
- `0x14002708c`
- `0x14002a340`
- `0x140031010`

## string_xrefs

- `0x14002a392`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a381`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusInternal`
- `0x14002a52c`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusInternal(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2,
        enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *a3)
{
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  _QWORD *v8; // rcx
  int IsGroupPolicyAllowed; // ebx
  __int64 v10; // rdx
  char v12; // al
  __int64 v13; // r14
  void (__fastcall *v14)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v15; // r8d
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  bool v19; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v20[7]; // [rsp+41h] [rbp-68h] BYREF
  _QWORD v21[3]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v23[32]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v24[32]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v6 + 40LL);
  std::string::string(
    v24,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatusInternal");
  std::string::string(
    v23,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v23, v24, 340);
  std::string::~string(v23);
  std::string::~string(v24);
  if ( !*((_BYTE *)this + 328) || *((_BYTE *)this + 304) )
  {
    if ( (unsigned __int8)std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::operator bool((char *)this + 16) )
    {
      v19 = 1;
      LODWORD(v21[0]) = 0;
      IsGroupPolicyAllowed = (*(__int64 (__fastcall **)(_QWORD, bool *, _QWORD *))(*(_QWORD *)*v8 + 24LL))(
                               *v8,
                               &v19,
                               v21);
      if ( IsGroupPolicyAllowed < 0 )
      {
        v10 = 354;
        goto LABEL_7;
      }
      if ( !v19 )
      {
        *a2 = 0;
        *(_DWORD *)a3 = 1;
        goto LABEL_21;
      }
    }
    v19 = 0;
    v20[0] = 0;
    IsGroupPolicyAllowed = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsGroupPolicyAllowed(
                             v8,
                             1,
                             &v19,
                             v20);
    if ( IsGroupPolicyAllowed >= 0 )
    {
      if ( !v19 || v20[0] )
      {
        *a2 = v19;
        *(_DWORD *)a3 = 2;
        goto LABEL_21;
      }
      v20[0] = 0;
      IsGroupPolicyAllowed = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _BYTE *))(*(_QWORD *)this + 112LL))(
                               this,
                               v20);
      if ( IsGroupPolicyAllowed >= 0 )
      {
        if ( IsGroupPolicyAllowed == 1 )
          v12 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)this + 152LL))(this);
        else
          v12 = v20[0];
        *a2 = v12;
        *(_DWORD *)a3 = 0;
        goto LABEL_21;
      }
      v10 = 380;
    }
    else
    {
      v10 = 367;
    }
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)IsGroupPolicyAllowed,
      (int)this);
    return (unsigned int)IsGroupPolicyAllowed;
  }
  *a2 = 0;
  *(_DWORD *)a3 = 4;
LABEL_21:
  v21[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenEnabledStatus<unsigned short const *,bool &,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(
    v21,
    a2,
    a3);
  v13 = *((_QWORD *)this + 47);
  v14 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v13 + 72LL);
  v21[0] = v24;
  v16 = std::string::string(v24, "hr = 0x%x", v15);
  v21[1] = v23;
  v17 = std::string::string(
          v23,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEn"
          "abledStatusInternal");
  v18 = std::string::string(
          v22,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v14(v13, v18, v17, 386, v16, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002a340  mov     [rsp-8+arg_18], rbx
0x14002a345  push    rbp
0x14002a346  push    rsi
0x14002a347  push    rdi
0x14002a348  push    r12
0x14002a34a  push    r13
0x14002a34c  push    r14
0x14002a34e  push    r15
0x14002a350  lea     rbp, [rsp-27h]
0x14002a355  sub     rsp, 0D0h
0x14002a35c  mov     rax, cs:__security_cookie
0x14002a363  xor     rax, rsp
0x14002a366  mov     [rbp+57h+var_40], rax
0x14002a36a  mov     r14, r8
0x14002a36d  mov     rsi, rdx
0x14002a370  mov     r15, rcx
0x14002a373  mov     rdi, [rcx+178h]
0x14002a37a  mov     rax, [rdi]
0x14002a37d  mov     rbx, [rax+28h]
0x14002a381  lea     rdx, aMicrosoftVoice_3; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a388  lea     rcx, [rbp+57h+var_60]
0x14002a38c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a391  nop
0x14002a392  lea     r13, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a399  mov     rdx, r13
0x14002a39c  lea     rcx, [rbp+57h+var_80]
0x14002a3a0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a3a5  nop
0x14002a3a6  mov     qword ptr [rsp+100h+var_E0], r15; int
0x14002a3ab  mov     r9d, 154h
0x14002a3b1  lea     r8, [rbp+57h+var_60]
0x14002a3b5  lea     rdx, [rbp+57h+var_80]
0x14002a3b9  mov     rcx, rdi
0x14002a3bc  mov     rax, rbx
0x14002a3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a3c4  nop
0x14002a3c5  lea     rcx, [rbp+57h+var_80]
0x14002a3c9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a3ce  nop
0x14002a3cf  lea     rcx, [rbp+57h+var_60]
0x14002a3d3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a3d8  xor     r12d, r12d
0x14002a3db  cmp     [r15+148h], r12b
0x14002a3e2  jz      short loc_14002A3FC
0x14002a3e4  cmp     [r15+130h], r12b
0x14002a3eb  jnz     short loc_14002A3FC
0x14002a3ed  mov     [rsi], r12b
0x14002a3f0  mov     dword ptr [r14], 4
0x14002a3f7  jmp     loc_14002A4DF
0x14002a3fc  lea     rcx, [r15+10h]
0x14002a400  call    ??B?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::operator bool(void)
0x14002a405  mov     edi, 1
0x14002a40a  test    al, al
0x14002a40c  jz      short loc_14002A45F
0x14002a40e  mov     [rbp+57h+var_C0], dil
0x14002a412  mov     dword ptr [rbp+57h+var_B8], r12d
0x14002a416  mov     rcx, [rcx]
0x14002a419  mov     rax, [rcx]
0x14002a41c  lea     r8, [rbp+57h+var_B8]
0x14002a420  lea     rdx, [rbp+57h+var_C0]
0x14002a424  mov     rax, [rax+18h]
0x14002a428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a42d  mov     ebx, eax
0x14002a42f  test    eax, eax
0x14002a431  jns     short loc_14002A44E
0x14002a433  mov     edx, 162h; void *
0x14002a438  mov     rcx, [rbp+5Fh]; this
0x14002a43c  mov     r9d, ebx; char *
0x14002a43f  mov     r8, r13; unsigned int
0x14002a442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a447  mov     eax, ebx
0x14002a449  jmp     loc_14002A574
0x14002a44e  cmp     [rbp+57h+var_C0], r12b
0x14002a452  jnz     short loc_14002A45F
0x14002a454  mov     [rsi], r12b
0x14002a457  mov     [r14], edi
0x14002a45a  jmp     loc_14002A4DF
0x14002a45f  mov     [rbp+57h+var_C0], r12b
0x14002a463  mov     [rbp+57h+var_BF], r12b
0x14002a467  lea     r9, [rbp+57h+var_BF]
0x14002a46b  lea     r8, [rbp+57h+var_C0]
0x14002a46f  mov     edx, edi
0x14002a471  call    ?IsGroupPolicyAllowed@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@2345@AEA_N2@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsGroupPolicyAllowed(std::wstring const &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName,bool &,bool &)
0x14002a476  mov     ebx, eax
0x14002a478  test    eax, eax
0x14002a47a  jns     short loc_14002A483
0x14002a47c  mov     edx, 16Fh
0x14002a481  jmp     short loc_14002A438
0x14002a483  mov     al, [rbp+57h+var_C0]
0x14002a486  test    al, al
0x14002a488  jz      short loc_14002A4D6
0x14002a48a  cmp     [rbp+57h+var_BF], r12b
0x14002a48e  jnz     short loc_14002A4D6
0x14002a490  mov     [rbp+57h+var_BF], r12b
0x14002a494  mov     rax, [r15]
0x14002a497  lea     rdx, [rbp+57h+var_BF]
0x14002a49b  mov     rcx, r15
0x14002a49e  mov     rax, [rax+70h]
0x14002a4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a4a7  mov     ebx, eax
0x14002a4a9  test    eax, eax
0x14002a4ab  jns     short loc_14002A4B4
0x14002a4ad  mov     edx, 17Ch
0x14002a4b2  jmp     short loc_14002A438
0x14002a4b4  cmp     ebx, edi
0x14002a4b6  jnz     short loc_14002A4CC
0x14002a4b8  mov     rax, [r15]
0x14002a4bb  mov     rcx, r15
0x14002a4be  mov     rax, [rax+98h]
0x14002a4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a4ca  jmp     short loc_14002A4CF
0x14002a4cc  mov     al, [rbp+57h+var_BF]
0x14002a4cf  mov     [rsi], al
0x14002a4d1  mov     [r14], r12d
0x14002a4d4  jmp     short loc_14002A4DF
0x14002a4d6  mov     [rsi], al
0x14002a4d8  mov     dword ptr [r14], 2
0x14002a4df  lea     rcx, [r15+20h]
0x14002a4e3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002a4e8  mov     [rbp+57h+var_B8], rax
0x14002a4ec  mov     r8, r14
0x14002a4ef  mov     rdx, rsi
0x14002a4f2  lea     rcx, [rbp+57h+var_B8]
0x14002a4f6  call    ??$VoiceActivationOnLockScreenEnabledStatus@PEBGAEA_NAEAW4AgentActivationStatusDisabledReason@Settings@Windows@VoiceAgentServices@Microsoft@@@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEA_NAEAW4AgentActivationStatusDisabledReason@1234@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenEnabledStatus<ushort const *,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(ushort const * &&,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)
0x14002a4fb  mov     r14, [r15+178h]
0x14002a502  mov     rax, [r14]
0x14002a505  mov     rsi, [rax+48h]
0x14002a509  lea     rax, [rbp+57h+var_60]
0x14002a50d  mov     [rbp+57h+var_B8], rax
0x14002a511  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002a518  lea     rcx, [rbp+57h+var_60]
0x14002a51c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a521  mov     rdi, rax
0x14002a524  lea     rax, [rbp+57h+var_80]
0x14002a528  mov     [rbp+57h+var_B0], rax
0x14002a52c  lea     rdx, aMicrosoftVoice_3; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a533  lea     rcx, [rbp+57h+var_80]
0x14002a537  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a53c  mov     rbx, rax
0x14002a53f  mov     rdx, r13
0x14002a542  lea     rcx, [rbp+57h+var_A0]
0x14002a546  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a54b  nop
0x14002a54c  mov     [rsp+100h+var_D0], r12
0x14002a551  mov     [rsp+100h+var_D8], r15
0x14002a556  mov     qword ptr [rsp+100h+var_E0], rdi
0x14002a55b  mov     r9d, 182h
0x14002a561  mov     r8, rbx
0x14002a564  mov     rdx, rax
0x14002a567  mov     rcx, r14
0x14002a56a  mov     rax, rsi
0x14002a56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a572  xor     eax, eax
0x14002a574  mov     rcx, [rbp+57h+var_40]
0x14002a578  xor     rcx, rsp; StackCookie
0x14002a57b  call    __security_check_cookie
0x14002a580  mov     rbx, [rsp+100h+arg_18]
0x14002a588  add     rsp, 0D0h
0x14002a58f  pop     r15
0x14002a591  pop     r14
0x14002a593  pop     r13
0x14002a595  pop     r12
0x14002a597  pop     rdi
0x14002a598  pop     rsi
0x14002a599  pop     rbp
0x14002a59a  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationLastUsedEnabled(bool)

- ea: `0x14002c830`
- end: `0x14002c9dd`
- name: `?SetVoiceActivationLastUsedEnabled@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJ_N@Z`
- size: `429`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x1400271e4`
- `0x1400280c4`
- `0x14002c830`
- `0x140031010`

## string_xrefs

- `0x14002c883`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c8f4`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c97d`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c872`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationLastUsedEnabled`
- `0x14002c96a`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationLastUsedEnabled`
- `0x14002c91d`: `AgentActivationLastUsed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationLastUsedEnabled(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        unsigned __int8 a2)
{
  int v2; // esi
  char *v4; // r15
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v10; // rax
  HKEY v11; // rcx
  int v12; // r8d
  __int64 v13; // r14
  void (__fastcall *v14)(__int64, __int64, __int64, __int64, __int64, char *, _QWORD); // rsi
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  _BYTE v18[8]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = a2;
  v18[0] = a2;
  v4 = (char *)this - 8;
  v5 = *((_QWORD *)this + 46);
  v6 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v5 + 40LL);
  std::string::string(
    v22,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationLastUsedEnabled");
  std::string::string(
    v21,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v6(v5, v21, v22, 120);
  std::string::~string(v21);
  std::string::~string(v22);
  v19[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 24);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationLastUsedEnabled<unsigned short const *,bool const &>(
    v19,
    v18);
  if ( *((_DWORD *)this + 81) )
  {
    v7 = -2146233079;
    v8 = 122;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)v7,
      (int)v4);
    return (unsigned int)v7;
  }
  v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 264);
  v7 = SpRegUtil::Set(v11, v10, L"AgentActivationLastUsed", v2);
  if ( v7 < 0 )
  {
    v8 = 123;
    goto LABEL_3;
  }
  v13 = *((_QWORD *)this + 46);
  v14 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, char *, _QWORD))(*(_QWORD *)v13 + 72LL);
  v19[0] = v22;
  v15 = std::string::string(v22, "hr = 0x%x", v12);
  v19[1] = v21;
  v16 = std::string::string(
          v21,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationLastUsedEnabled");
  v17 = std::string::string(
          v20,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v14(v13, v17, v16, 124, v15, v4, 0);
  return 0;
}

```

## disassembly

```asm
0x14002c830  mov     [rsp-8+arg_10], rbx
0x14002c835  push    rbp
0x14002c836  push    rsi
0x14002c837  push    rdi
0x14002c838  push    r14
0x14002c83a  push    r15
0x14002c83c  lea     rbp, [rsp-37h]
0x14002c841  sub     rsp, 0D0h
0x14002c848  mov     rax, cs:__security_cookie
0x14002c84f  xor     rax, rsp
0x14002c852  mov     [rbp+57h+var_30], rax
0x14002c856  movzx   esi, dl
0x14002c859  mov     r14, rcx
0x14002c85c  mov     [rbp+57h+var_B0], sil
0x14002c860  lea     r15, [rcx-8]
0x14002c864  mov     rdi, [r15+178h]
0x14002c86b  mov     rax, [rdi]
0x14002c86e  mov     rbx, [rax+28h]
0x14002c872  lea     rdx, aMicrosoftVoice_38; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c879  lea     rcx, [rbp+57h+var_50]
0x14002c87d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c882  nop
0x14002c883  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c88a  lea     rcx, [rbp+57h+var_70]
0x14002c88e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c893  nop
0x14002c894  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x14002c899  mov     r9d, 78h ; 'x'
0x14002c89f  lea     r8, [rbp+57h+var_50]
0x14002c8a3  lea     rdx, [rbp+57h+var_70]
0x14002c8a7  mov     rcx, rdi
0x14002c8aa  mov     rax, rbx
0x14002c8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8b2  nop
0x14002c8b3  lea     rcx, [rbp+57h+var_70]
0x14002c8b7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c8bc  nop
0x14002c8bd  lea     rcx, [rbp+57h+var_50]
0x14002c8c1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c8c6  lea     rcx, [r14+18h]
0x14002c8ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002c8cf  mov     [rbp+57h+var_A8], rax
0x14002c8d3  lea     rdx, [rbp+57h+var_B0]
0x14002c8d7  lea     rcx, [rbp+57h+var_A8]
0x14002c8db  call    ??$SetVoiceActivationLastUsedEnabled@PEBGAEB_N@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEB_N@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationLastUsedEnabled<ushort const *,bool const &>(ushort const * &&,bool const &)
0x14002c8e0  cmp     dword ptr [r14+144h], 0
0x14002c8e8  jz      short loc_14002C90E
0x14002c8ea  mov     ebx, 80131509h
0x14002c8ef  mov     edx, 7Ah ; 'z'; void *
0x14002c8f4  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c8fb  mov     r9d, ebx; char *
0x14002c8fe  mov     rcx, [rbp+5Fh]; this
0x14002c902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c907  mov     eax, ebx
0x14002c909  jmp     loc_14002C9BA
0x14002c90e  lea     rcx, [r14+108h]
0x14002c915  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002c91a  mov     r9d, esi; unsigned int
0x14002c91d  lea     r8, aAgentactivatio_1; "AgentActivationLastUsed"
0x14002c924  mov     rdx, rax; unsigned __int16 *
0x14002c927  call    ?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG1K@Z; SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *,ulong)
0x14002c92c  mov     ebx, eax
0x14002c92e  test    eax, eax
0x14002c930  jns     short loc_14002C939
0x14002c932  mov     edx, 7Bh ; '{'
0x14002c937  jmp     short loc_14002C8F4
0x14002c939  mov     r14, [r14+170h]
0x14002c940  mov     rax, [r14]
0x14002c943  mov     rsi, [rax+48h]
0x14002c947  lea     rax, [rbp+57h+var_50]
0x14002c94b  mov     [rbp+57h+var_A8], rax
0x14002c94f  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002c956  lea     rcx, [rbp+57h+var_50]
0x14002c95a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c95f  mov     rdi, rax
0x14002c962  lea     rax, [rbp+57h+var_70]
0x14002c966  mov     [rbp+57h+var_A0], rax
0x14002c96a  lea     rdx, aMicrosoftVoice_38; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c971  lea     rcx, [rbp+57h+var_70]
0x14002c975  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c97a  mov     rbx, rax
0x14002c97d  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c984  lea     rcx, [rbp+57h+var_90]
0x14002c988  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c98d  nop
0x14002c98e  mov     [rsp+0F0h+var_C0], 0
0x14002c997  mov     [rsp+0F0h+var_C8], r15
0x14002c99c  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x14002c9a1  mov     r9d, 7Ch ; '|'
0x14002c9a7  mov     r8, rbx
0x14002c9aa  mov     rdx, rax
0x14002c9ad  mov     rcx, r14
0x14002c9b0  mov     rax, rsi
0x14002c9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c9b8  xor     eax, eax
0x14002c9ba  mov     rcx, [rbp+57h+var_30]
0x14002c9be  xor     rcx, rsp; StackCookie
0x14002c9c1  call    __security_check_cookie
0x14002c9c6  mov     rbx, [rsp+0F0h+arg_10]
0x14002c9ce  add     rsp, 0D0h
0x14002c9d5  pop     r15
0x14002c9d7  pop     r14
0x14002c9d9  pop     rdi
0x14002c9da  pop     rsi
0x14002c9db  pop     rbp
0x14002c9dc  retn
```

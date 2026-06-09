# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationOnLockScreenEnabled(bool)

- ea: `0x14002c9f0`
- end: `0x14002cb9d`
- name: `?SetVoiceActivationOnLockScreenEnabled@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJ_N@Z`
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
- `0x140028140`
- `0x14002c9f0`
- `0x140031010`

## string_xrefs

- `0x14002cadd`: `AgentActivationOnLockScreenEnabled`
- `0x14002ca43`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002cab4`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002cb3d`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002ca32`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationOnLockScreenEnabled`
- `0x14002cb2a`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationOnLockScreenEnabled`

## pseudocode

```c
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationOnLockScreenEnabled(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationOnLockScreenEnabled");
  std::string::string(
    v21,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v6(v5, v21, v22, 110);
  std::string::~string(v21);
  std::string::~string(v22);
  v19[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 24);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationOnLockScreenEnabled<unsigned short const *,bool const &>(
    v19,
    v18);
  if ( *((_DWORD *)this + 77) )
  {
    v7 = -2146233079;
    v8 = 112;
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
  v7 = SpRegUtil::Set(v11, v10, L"AgentActivationOnLockScreenEnabled", v2);
  if ( v7 < 0 )
  {
    v8 = 113;
    goto LABEL_3;
  }
  v13 = *((_QWORD *)this + 46);
  v14 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, char *, _QWORD))(*(_QWORD *)v13 + 72LL);
  v19[0] = v22;
  v15 = std::string::string(v22, "hr = 0x%x", v12);
  v19[1] = v21;
  v16 = std::string::string(
          v21,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationOnLockScreenEnabled");
  v17 = std::string::string(
          v20,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v14(v13, v17, v16, 114, v15, v4, 0);
  return 0;
}

```

## disassembly

```asm
0x14002c9f0  mov     [rsp-8+arg_10], rbx
0x14002c9f5  push    rbp
0x14002c9f6  push    rsi
0x14002c9f7  push    rdi
0x14002c9f8  push    r14
0x14002c9fa  push    r15
0x14002c9fc  lea     rbp, [rsp-37h]
0x14002ca01  sub     rsp, 0D0h
0x14002ca08  mov     rax, cs:__security_cookie
0x14002ca0f  xor     rax, rsp
0x14002ca12  mov     [rbp+57h+var_30], rax
0x14002ca16  movzx   esi, dl
0x14002ca19  mov     r14, rcx
0x14002ca1c  mov     [rbp+57h+var_B0], sil
0x14002ca20  lea     r15, [rcx-8]
0x14002ca24  mov     rdi, [r15+178h]
0x14002ca2b  mov     rax, [rdi]
0x14002ca2e  mov     rbx, [rax+28h]
0x14002ca32  lea     rdx, aMicrosoftVoice_8; "Microsoft::VoiceAgentServices::Windows:"...
0x14002ca39  lea     rcx, [rbp+57h+var_50]
0x14002ca3d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ca42  nop
0x14002ca43  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002ca4a  lea     rcx, [rbp+57h+var_70]
0x14002ca4e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ca53  nop
0x14002ca54  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x14002ca59  mov     r9d, 6Eh ; 'n'
0x14002ca5f  lea     r8, [rbp+57h+var_50]
0x14002ca63  lea     rdx, [rbp+57h+var_70]
0x14002ca67  mov     rcx, rdi
0x14002ca6a  mov     rax, rbx
0x14002ca6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ca72  nop
0x14002ca73  lea     rcx, [rbp+57h+var_70]
0x14002ca77  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ca7c  nop
0x14002ca7d  lea     rcx, [rbp+57h+var_50]
0x14002ca81  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ca86  lea     rcx, [r14+18h]
0x14002ca8a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002ca8f  mov     [rbp+57h+var_A8], rax
0x14002ca93  lea     rdx, [rbp+57h+var_B0]
0x14002ca97  lea     rcx, [rbp+57h+var_A8]
0x14002ca9b  call    ??$SetVoiceActivationOnLockScreenEnabled@PEBGAEB_N@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEB_N@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationOnLockScreenEnabled<ushort const *,bool const &>(ushort const * &&,bool const &)
0x14002caa0  cmp     dword ptr [r14+134h], 0
0x14002caa8  jz      short loc_14002CACE
0x14002caaa  mov     ebx, 80131509h
0x14002caaf  mov     edx, 70h ; 'p'; void *
0x14002cab4  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002cabb  mov     r9d, ebx; char *
0x14002cabe  mov     rcx, [rbp+5Fh]; this
0x14002cac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002cac7  mov     eax, ebx
0x14002cac9  jmp     loc_14002CB7A
0x14002cace  lea     rcx, [r14+108h]
0x14002cad5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002cada  mov     r9d, esi; unsigned int
0x14002cadd  lea     r8, aAgentactivatio_0; "AgentActivationOnLockScreenEnabled"
0x14002cae4  mov     rdx, rax; unsigned __int16 *
0x14002cae7  call    ?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG1K@Z; SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *,ulong)
0x14002caec  mov     ebx, eax
0x14002caee  test    eax, eax
0x14002caf0  jns     short loc_14002CAF9
0x14002caf2  mov     edx, 71h ; 'q'
0x14002caf7  jmp     short loc_14002CAB4
0x14002caf9  mov     r14, [r14+170h]
0x14002cb00  mov     rax, [r14]
0x14002cb03  mov     rsi, [rax+48h]
0x14002cb07  lea     rax, [rbp+57h+var_50]
0x14002cb0b  mov     [rbp+57h+var_A8], rax
0x14002cb0f  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002cb16  lea     rcx, [rbp+57h+var_50]
0x14002cb1a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cb1f  mov     rdi, rax
0x14002cb22  lea     rax, [rbp+57h+var_70]
0x14002cb26  mov     [rbp+57h+var_A0], rax
0x14002cb2a  lea     rdx, aMicrosoftVoice_8; "Microsoft::VoiceAgentServices::Windows:"...
0x14002cb31  lea     rcx, [rbp+57h+var_70]
0x14002cb35  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cb3a  mov     rbx, rax
0x14002cb3d  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002cb44  lea     rcx, [rbp+57h+var_90]
0x14002cb48  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cb4d  nop
0x14002cb4e  mov     [rsp+0F0h+var_C0], 0
0x14002cb57  mov     [rsp+0F0h+var_C8], r15
0x14002cb5c  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x14002cb61  mov     r9d, 72h ; 'r'
0x14002cb67  mov     r8, rbx
0x14002cb6a  mov     rdx, rax
0x14002cb6d  mov     rcx, r14
0x14002cb70  mov     rax, rsi
0x14002cb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cb78  xor     eax, eax
0x14002cb7a  mov     rcx, [rbp+57h+var_30]
0x14002cb7e  xor     rcx, rsp; StackCookie
0x14002cb81  call    __security_check_cookie
0x14002cb86  mov     rbx, [rsp+0F0h+arg_10]
0x14002cb8e  add     rsp, 0D0h
0x14002cb95  pop     r15
0x14002cb97  pop     r14
0x14002cb99  pop     rdi
0x14002cb9a  pop     rsi
0x14002cb9b  pop     rbp
0x14002cb9c  retn
```

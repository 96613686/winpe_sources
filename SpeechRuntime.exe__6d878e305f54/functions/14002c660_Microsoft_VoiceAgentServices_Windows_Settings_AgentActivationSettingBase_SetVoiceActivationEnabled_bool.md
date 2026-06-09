# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationEnabled(bool)

- ea: `0x14002c660`
- end: `0x14002c82a`
- name: `?SetVoiceActivationEnabled@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJ_N@Z`
- size: `458`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140025e84`
- `0x1400271e4`
- `0x140028048`
- `0x14002c660`
- `0x140031010`

## string_xrefs

- `0x14002c752`: `AgentActivationEnabled`
- `0x14002c6b9`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c6a8`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationEnabled`
- `0x14002c7b6`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationEnabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationEnabled(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationEnabled");
  std::string::string(
    v21,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v6(v5, v21, v22, 96);
  std::string::~string(v21);
  std::string::~string(v22);
  v19[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 24);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationEnabled<unsigned short const *,bool const &>(
    v19,
    v18);
  if ( *((_DWORD *)this + 75) )
  {
    v7 = -2146233079;
    v8 = 98;
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
  v7 = SpRegUtil::Set(v11, v10, L"AgentActivationEnabled", v2);
  if ( v7 < 0 )
  {
    v8 = 99;
    goto LABEL_3;
  }
  if ( (_BYTE)v2 )
  {
    v7 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::RequestAARServiceStart();
    if ( v7 < 0 )
    {
      v8 = 102;
      goto LABEL_3;
    }
  }
  v13 = *((_QWORD *)this + 46);
  v14 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, char *, _QWORD))(*(_QWORD *)v13 + 72LL);
  v19[0] = v22;
  v15 = std::string::string(v22, "hr = 0x%x", v12);
  v19[1] = v21;
  v16 = std::string::string(
          v21,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationEnabled");
  v17 = std::string::string(
          v20,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v14(v13, v17, v16, 104, v15, v4, 0);
  return 0;
}

```

## disassembly

```asm
0x14002c660  mov     [rsp-8+arg_10], rbx
0x14002c665  mov     [rsp-8+arg_18], rsi
0x14002c66a  push    rbp
0x14002c66b  push    rdi
0x14002c66c  push    r12
0x14002c66e  push    r14
0x14002c670  push    r15
0x14002c672  lea     rbp, [rsp-37h]
0x14002c677  sub     rsp, 0D0h
0x14002c67e  mov     rax, cs:__security_cookie
0x14002c685  xor     rax, rsp
0x14002c688  mov     [rbp+57h+var_30], rax
0x14002c68c  movzx   esi, dl
0x14002c68f  mov     r14, rcx
0x14002c692  mov     [rbp+57h+var_B0], sil
0x14002c696  lea     r15, [rcx-8]
0x14002c69a  mov     rdi, [r15+178h]
0x14002c6a1  mov     rax, [rdi]
0x14002c6a4  mov     rbx, [rax+28h]
0x14002c6a8  lea     rdx, aMicrosoftVoice_27; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c6af  lea     rcx, [rbp+57h+var_50]
0x14002c6b3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c6b8  nop
0x14002c6b9  lea     r12, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c6c0  mov     rdx, r12
0x14002c6c3  lea     rcx, [rbp+57h+var_70]
0x14002c6c7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c6cc  nop
0x14002c6cd  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x14002c6d2  mov     r9d, 60h ; '`'
0x14002c6d8  lea     r8, [rbp+57h+var_50]
0x14002c6dc  lea     rdx, [rbp+57h+var_70]
0x14002c6e0  mov     rcx, rdi
0x14002c6e3  mov     rax, rbx
0x14002c6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c6eb  nop
0x14002c6ec  lea     rcx, [rbp+57h+var_70]
0x14002c6f0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c6f5  nop
0x14002c6f6  lea     rcx, [rbp+57h+var_50]
0x14002c6fa  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c6ff  lea     rcx, [r14+18h]
0x14002c703  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002c708  mov     [rbp+57h+var_A8], rax
0x14002c70c  lea     rdx, [rbp+57h+var_B0]
0x14002c710  lea     rcx, [rbp+57h+var_A8]
0x14002c714  call    ??$SetVoiceActivationEnabled@PEBGAEB_N@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEB_N@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationEnabled<ushort const *,bool const &>(ushort const * &&,bool const &)
0x14002c719  cmp     dword ptr [r14+12Ch], 0
0x14002c721  jz      short loc_14002C743
0x14002c723  mov     ebx, 80131509h
0x14002c728  mov     edx, 62h ; 'b'; void *
0x14002c72d  mov     rcx, [rbp+5Fh]; this
0x14002c731  mov     r9d, ebx; char *
0x14002c734  mov     r8, r12; unsigned int
0x14002c737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c73c  mov     eax, ebx
0x14002c73e  jmp     loc_14002C802
0x14002c743  lea     rcx, [r14+108h]
0x14002c74a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002c74f  mov     r9d, esi; unsigned int
0x14002c752  lea     r8, Value; "AgentActivationEnabled"
0x14002c759  mov     rdx, rax; unsigned __int16 *
0x14002c75c  call    ?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG1K@Z; SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *,ulong)
0x14002c761  mov     ebx, eax
0x14002c763  test    eax, eax
0x14002c765  jns     short loc_14002C76E
0x14002c767  mov     edx, 63h ; 'c'
0x14002c76c  jmp     short loc_14002C72D
0x14002c76e  test    sil, sil
0x14002c771  jz      short loc_14002C785
0x14002c773  call    ?RequestAARServiceStart@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::RequestAARServiceStart(void)
0x14002c778  mov     ebx, eax
0x14002c77a  test    eax, eax
0x14002c77c  jns     short loc_14002C785
0x14002c77e  mov     edx, 66h ; 'f'
0x14002c783  jmp     short loc_14002C72D
0x14002c785  mov     r14, [r14+170h]
0x14002c78c  mov     rax, [r14]
0x14002c78f  mov     rsi, [rax+48h]
0x14002c793  lea     rax, [rbp+57h+var_50]
0x14002c797  mov     [rbp+57h+var_A8], rax
0x14002c79b  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002c7a2  lea     rcx, [rbp+57h+var_50]
0x14002c7a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c7ab  mov     rdi, rax
0x14002c7ae  lea     rax, [rbp+57h+var_70]
0x14002c7b2  mov     [rbp+57h+var_A0], rax
0x14002c7b6  lea     rdx, aMicrosoftVoice_27; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c7bd  lea     rcx, [rbp+57h+var_70]
0x14002c7c1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c7c6  mov     rbx, rax
0x14002c7c9  mov     rdx, r12
0x14002c7cc  lea     rcx, [rbp+57h+var_90]
0x14002c7d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c7d5  nop
0x14002c7d6  mov     [rsp+0F0h+var_C0], 0
0x14002c7df  mov     [rsp+0F0h+var_C8], r15
0x14002c7e4  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x14002c7e9  mov     r9d, 68h ; 'h'
0x14002c7ef  mov     r8, rbx
0x14002c7f2  mov     rdx, rax
0x14002c7f5  mov     rcx, r14
0x14002c7f8  mov     rax, rsi
0x14002c7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c800  xor     eax, eax
0x14002c802  mov     rcx, [rbp+57h+var_30]
0x14002c806  xor     rcx, rsp; StackCookie
0x14002c809  call    __security_check_cookie
0x14002c80e  lea     r11, [rsp+0F0h+var_20]
0x14002c816  mov     rbx, [r11+40h]
0x14002c81a  mov     rsi, [r11+48h]
0x14002c81e  mov     rsp, r11
0x14002c821  pop     r15
0x14002c823  pop     r14
0x14002c825  pop     r12
0x14002c827  pop     rdi
0x14002c828  pop     rbp
0x14002c829  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification(void)

- ea: `0x14002ab98`
- end: `0x14002affd`
- name: `?HandleChangeNotification@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAXXZ`
- size: `1125`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140022d74`
- `0x140028910`

## callees

- `0x140002d30`
- `0x140010ec0`
- `0x14001296c`
- `0x140012d68`
- `0x140020208`
- `0x140020ff0`
- `0x1400210a8`
- `0x1400210dc`
- `0x140021658`
- `0x140021bd0`
- `0x140021c7c`
- `0x1400281bc`
- `0x14002829c`
- `0x14002830c`
- `0x14002842c`
- `0x14002849c`
- `0x140028a74`
- `0x14002ab98`
- `0x140031010`

## string_xrefs

- `0x14002abdd`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002af24`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002af7a`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002afb4`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002abcc`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification`
- `0x14002af11`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification`
- `0x14002afa1`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int v4; // eax
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r14
  void (__fastcall *v15)(__int64, __int64, __int64, __int64); // rsi
  __int64 v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rsi
  void (__fastcall *v20)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // [rsp+20h] [rbp-89h]
  char v24; // [rsp+40h] [rbp-69h] BYREF
  char v25; // [rsp+41h] [rbp-68h] BYREF
  char v26; // [rsp+42h] [rbp-67h] BYREF
  _BYTE v27[5]; // [rsp+43h] [rbp-66h] BYREF
  _BYTE *v28; // [rsp+48h] [rbp-61h] BYREF
  int v29; // [rsp+50h] [rbp-59h] BYREF
  int v30; // [rsp+54h] [rbp-55h] BYREF
  _BYTE *v31; // [rsp+58h] [rbp-51h] BYREF
  int v32; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v33[32]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v34[32]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v35[32]; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v34,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification");
  std::string::string(
    v35,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v23 = (int)this;
  v3(v2, v35, v34, 129);
  std::string::~string(v35);
  std::string::~string(v34);
  if ( (unsigned __int8)std::function<void (enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsSystemEventKind)>::operator bool((char *)this + 208) )
  {
    v24 = 0;
    v29 = 0;
    if ( (*(int (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *, int *))(*(_QWORD *)this + 184LL))(
           this,
           &v24,
           &v29) >= 0 )
    {
      v4 = v29;
      if ( v24 != *((_BYTE *)this + 304) || v29 != *((_DWORD *)this + 77) )
      {
        *((_BYTE *)this + 304) = v24;
        *((_DWORD *)this + 77) = v4;
        v28 = (_BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationEnabledChanged<unsigned short const *>(&v28);
        v5 = std::wstring::wstring(v34, (char *)this + 32);
        std::_Func_class<void,std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(
          (char *)this + 208,
          v5,
          0);
      }
    }
    v25 = 0;
    v30 = 0;
    if ( (*(int (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *, int *))(*(_QWORD *)this + 192LL))(
           this,
           &v25,
           &v30) >= 0 )
    {
      v6 = v30;
      if ( v25 != *((_BYTE *)this + 312) || v30 != *((_DWORD *)this + 79) )
      {
        *((_BYTE *)this + 312) = v25;
        *((_DWORD *)this + 79) = v6;
        v28 = (_BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenEnabledChanged<unsigned short const *>(&v28);
        v7 = std::wstring::wstring(v34, (char *)this + 32);
        std::_Func_class<void,std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(
          (char *)this + 208,
          v7,
          1);
      }
    }
    v26 = 0;
    v32 = 0;
    if ( (*(int (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *, int *))(*(_QWORD *)this + 200LL))(
           this,
           &v26,
           &v32) >= 0 )
    {
      v8 = v32;
      if ( v26 != *((_BYTE *)this + 320) || v32 != *((_DWORD *)this + 81) )
      {
        *((_BYTE *)this + 320) = v26;
        *((_DWORD *)this + 81) = v8;
        v28 = (_BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenSupportedChanged<unsigned short const *>(&v28);
        v9 = std::wstring::wstring(v34, (char *)this + 32);
        std::_Func_class<void,std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(
          (char *)this + 208,
          v9,
          1);
      }
    }
    v27[0] = 0;
    LODWORD(v31) = 0;
    if ( (*(int (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _BYTE *, _BYTE **))(*(_QWORD *)this + 208LL))(
           this,
           v27,
           &v31) >= 0 )
    {
      v10 = (int)v31;
      if ( v27[0] != *((_BYTE *)this + 336) || (_DWORD)v31 != *((_DWORD *)this + 83) )
      {
        *((_BYTE *)this + 336) = v27[0];
        *((_DWORD *)this + 83) = v10;
        v28 = (_BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationLastUsedEnabledChanged<unsigned short const *>(&v28);
        v11 = std::wstring::wstring(v34, (char *)this + 32);
        std::_Func_class<void,std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(
          (char *)this + 208,
          v11,
          3);
      }
    }
    std::wstring::wstring(v35);
    if ( (*(int (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _BYTE *))(*(_QWORD *)this + 48LL))(
           this,
           v35) >= 0
      && (unsigned __int8)std::operator!=<unsigned short>(v35, (char *)this + 344) )
    {
      v28 = (_BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
      Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationDefaultAgentChanged<unsigned short const *>(&v28);
      v12 = std::wstring::wstring(v34, (char *)this + 344);
      std::_Func_class<void,std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(
        (char *)this + 208,
        v12,
        2);
      v13 = std::wstring::wstring(v34, v35);
      std::_Func_class<void,std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(
        (char *)this + 208,
        v13,
        2);
      std::wstring::operator=((char *)this + 344, v35);
    }
    std::wstring::~wstring(v35);
  }
  else
  {
    v14 = *((_QWORD *)this + 47);
    v15 = *(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v14 + 32LL);
    v28 = v34;
    std::string::string(v34, "No callback assigned");
    v31 = v35;
    v16 = std::string::string(
            v35,
            "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification");
    v17 = std::string::string(
            v33,
            "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
    v23 = 202;
    v15(v14, 2, v17, v16);
  }
  v18 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)this + 176LL))(this);
  if ( v18 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)v18,
      v23);
  v19 = *((_QWORD *)this + 47);
  v20 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v19 + 64LL);
  v28 = v33;
  v21 = std::string::string(
          v33,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification");
  v22 = std::string::string(
          v34,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v20(v19, v22, v21, 205, this);
}

```

## disassembly

```asm
0x14002ab98  push    rbp
0x14002ab9a  push    rbx
0x14002ab9b  push    rsi
0x14002ab9c  push    rdi
0x14002ab9d  push    r14
0x14002ab9f  push    r15
0x14002aba1  lea     rbp, [rsp-2Fh]
0x14002aba6  sub     rsp, 0D8h
0x14002abad  mov     rax, cs:__security_cookie
0x14002abb4  xor     rax, rsp
0x14002abb7  mov     [rbp+57h+var_38], rax
0x14002abbb  mov     r15, rcx
0x14002abbe  mov     rdi, [rcx+178h]
0x14002abc5  mov     rax, [rdi]
0x14002abc8  mov     rbx, [rax+28h]
0x14002abcc  lea     rdx, aMicrosoftVoice_48; "Microsoft::VoiceAgentServices::Windows:"...
0x14002abd3  lea     rcx, [rbp+57h+var_78]
0x14002abd7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002abdc  nop
0x14002abdd  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002abe4  lea     rcx, [rbp+57h+var_58]
0x14002abe8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002abed  nop
0x14002abee  mov     qword ptr [rsp+100h+var_E0], r15
0x14002abf3  mov     r9d, 81h
0x14002abf9  lea     r8, [rbp+57h+var_78]
0x14002abfd  lea     rdx, [rbp+57h+var_58]
0x14002ac01  mov     rcx, rdi
0x14002ac04  mov     rax, rbx
0x14002ac07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac0c  nop
0x14002ac0d  lea     rcx, [rbp+57h+var_58]
0x14002ac11  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ac16  nop
0x14002ac17  lea     rcx, [rbp+57h+var_78]
0x14002ac1b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ac20  lea     rdi, [r15+0D0h]
0x14002ac27  mov     rcx, rdi
0x14002ac2a  call    ??B?$function@$$A6AXW4AgentActivationSettingsSystemEventKind@Settings@Windows@VoiceAgentServices@Microsoft@@@Z@std@@QEBA_NXZ; std::function<void (Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsSystemEventKind)>::operator bool(void)
0x14002ac2f  test    al, al
0x14002ac31  jz      loc_14002AEE0
0x14002ac37  mov     [rbp+57h+var_C0], 0
0x14002ac3b  mov     [rbp+57h+var_B0], 0
0x14002ac42  mov     rax, [r15]
0x14002ac45  lea     r8, [rbp+57h+var_B0]
0x14002ac49  lea     rdx, [rbp+57h+var_C0]
0x14002ac4d  mov     rcx, r15
0x14002ac50  mov     rax, [rax+0B8h]
0x14002ac57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac5c  test    eax, eax
0x14002ac5e  js      short loc_14002ACB7
0x14002ac60  mov     eax, [rbp+57h+var_B0]
0x14002ac63  mov     cl, [rbp+57h+var_C0]
0x14002ac66  cmp     cl, [r15+130h]
0x14002ac6d  jnz     short loc_14002AC78
0x14002ac6f  cmp     eax, [r15+134h]
0x14002ac76  jz      short loc_14002ACB7
0x14002ac78  mov     [r15+130h], cl
0x14002ac7f  mov     [r15+134h], eax
0x14002ac86  lea     rcx, [r15+20h]
0x14002ac8a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002ac8f  mov     [rbp+57h+var_B8], rax
0x14002ac93  lea     rcx, [rbp+57h+var_B8]
0x14002ac97  call    ??$VoiceActivationEnabledChanged@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationEnabledChanged<ushort const *>(ushort const * &&)
0x14002ac9c  lea     rdx, [r15+20h]
0x14002aca0  lea     rcx, [rbp+57h+var_78]
0x14002aca4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002aca9  xor     r8d, r8d
0x14002acac  mov     rdx, rax
0x14002acaf  mov     rcx, rdi
0x14002acb2  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::_Func_class<void,std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)
0x14002acb7  mov     [rbp+57h+var_BF], 0
0x14002acbb  mov     [rbp+57h+var_AC], 0
0x14002acc2  mov     rax, [r15]
0x14002acc5  lea     r8, [rbp+57h+var_AC]
0x14002acc9  lea     rdx, [rbp+57h+var_BF]
0x14002accd  mov     rcx, r15
0x14002acd0  mov     rax, [rax+0C0h]
0x14002acd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002acdc  mov     esi, 1
0x14002ace1  test    eax, eax
0x14002ace3  js      short loc_14002AD3C
0x14002ace5  mov     eax, [rbp+57h+var_AC]
0x14002ace8  mov     cl, [rbp+57h+var_BF]
0x14002aceb  cmp     cl, [r15+138h]
0x14002acf2  jnz     short loc_14002ACFD
0x14002acf4  cmp     eax, [r15+13Ch]
0x14002acfb  jz      short loc_14002AD3C
0x14002acfd  mov     [r15+138h], cl
0x14002ad04  mov     [r15+13Ch], eax
0x14002ad0b  lea     rcx, [r15+20h]
0x14002ad0f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002ad14  mov     [rbp+57h+var_B8], rax
0x14002ad18  lea     rcx, [rbp+57h+var_B8]
0x14002ad1c  call    ??$VoiceActivationOnLockScreenEnabledChanged@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenEnabledChanged<ushort const *>(ushort const * &&)
0x14002ad21  lea     rdx, [r15+20h]
0x14002ad25  lea     rcx, [rbp+57h+var_78]
0x14002ad29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002ad2e  mov     r8d, esi
0x14002ad31  mov     rdx, rax
0x14002ad34  mov     rcx, rdi
0x14002ad37  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::_Func_class<void,std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)
0x14002ad3c  mov     [rbp+57h+var_BE], 0
0x14002ad40  mov     [rbp+57h+var_A0], 0
0x14002ad47  mov     rax, [r15]
0x14002ad4a  lea     r8, [rbp+57h+var_A0]
0x14002ad4e  lea     rdx, [rbp+57h+var_BE]
0x14002ad52  mov     rcx, r15
0x14002ad55  mov     rax, [rax+0C8h]
0x14002ad5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ad61  test    eax, eax
0x14002ad63  js      short loc_14002ADBC
0x14002ad65  mov     eax, [rbp+57h+var_A0]
0x14002ad68  mov     cl, [rbp+57h+var_BE]
0x14002ad6b  cmp     cl, [r15+140h]
0x14002ad72  jnz     short loc_14002AD7D
0x14002ad74  cmp     eax, [r15+144h]
0x14002ad7b  jz      short loc_14002ADBC
0x14002ad7d  mov     [r15+140h], cl
0x14002ad84  mov     [r15+144h], eax
0x14002ad8b  lea     rcx, [r15+20h]
0x14002ad8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002ad94  mov     [rbp+57h+var_B8], rax
0x14002ad98  lea     rcx, [rbp+57h+var_B8]
0x14002ad9c  call    ??$VoiceActivationOnLockScreenSupportedChanged@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationOnLockScreenSupportedChanged<ushort const *>(ushort const * &&)
0x14002ada1  lea     rdx, [r15+20h]
0x14002ada5  lea     rcx, [rbp+57h+var_78]
0x14002ada9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002adae  mov     r8d, esi
0x14002adb1  mov     rdx, rax
0x14002adb4  mov     rcx, rdi
0x14002adb7  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::_Func_class<void,std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)
0x14002adbc  mov     [rbp+57h+var_BD], 0
0x14002adc0  mov     dword ptr [rbp+57h+var_A8], 0
0x14002adc7  mov     rax, [r15]
0x14002adca  lea     r8, [rbp+57h+var_A8]
0x14002adce  lea     rdx, [rbp+57h+var_BD]
0x14002add2  mov     rcx, r15
0x14002add5  mov     rax, [rax+0D0h]
0x14002addc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ade1  test    eax, eax
0x14002ade3  js      short loc_14002AE3F
0x14002ade5  mov     eax, dword ptr [rbp+57h+var_A8]
0x14002ade8  mov     cl, [rbp+57h+var_BD]
0x14002adeb  cmp     cl, [r15+150h]
0x14002adf2  jnz     short loc_14002ADFD
0x14002adf4  cmp     eax, [r15+14Ch]
0x14002adfb  jz      short loc_14002AE3F
0x14002adfd  mov     [r15+150h], cl
0x14002ae04  mov     [r15+14Ch], eax
0x14002ae0b  lea     rcx, [r15+20h]
0x14002ae0f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002ae14  mov     [rbp+57h+var_B8], rax
0x14002ae18  lea     rcx, [rbp+57h+var_B8]
0x14002ae1c  call    ??$VoiceActivationLastUsedEnabledChanged@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationLastUsedEnabledChanged<ushort const *>(ushort const * &&)
0x14002ae21  lea     rdx, [r15+20h]
0x14002ae25  lea     rcx, [rbp+57h+var_78]
0x14002ae29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002ae2e  mov     r8d, 3
0x14002ae34  mov     rdx, rax
0x14002ae37  mov     rcx, rdi
0x14002ae3a  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::_Func_class<void,std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)
0x14002ae3f  lea     rcx, [rbp+57h+var_58]
0x14002ae43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14002ae48  nop
0x14002ae49  mov     rax, [r15]
0x14002ae4c  lea     rdx, [rbp+57h+var_58]
0x14002ae50  mov     rcx, r15
0x14002ae53  mov     rax, [rax+30h]
0x14002ae57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae5c  test    eax, eax
0x14002ae5e  js      short loc_14002AED5
0x14002ae60  lea     rbx, [r15+158h]
0x14002ae67  mov     rdx, rbx
0x14002ae6a  lea     rcx, [rbp+57h+var_58]
0x14002ae6e  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x14002ae73  test    al, al
0x14002ae75  jz      short loc_14002AED5
0x14002ae77  lea     rcx, [rbp+57h+var_58]
0x14002ae7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002ae80  mov     [rbp+57h+var_B8], rax
0x14002ae84  lea     rcx, [rbp+57h+var_B8]
0x14002ae88  call    ??$VoiceActivationDefaultAgentChanged@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationDefaultAgentChanged<ushort const *>(ushort const * &&)
0x14002ae8d  mov     rdx, rbx
0x14002ae90  lea     rcx, [rbp+57h+var_78]
0x14002ae94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002ae99  mov     r8d, 2
0x14002ae9f  mov     rdx, rax
0x14002aea2  mov     rcx, rdi
0x14002aea5  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::_Func_class<void,std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)
0x14002aeaa  lea     rdx, [rbp+57h+var_58]
0x14002aeae  lea     rcx, [rbp+57h+var_78]
0x14002aeb2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002aeb7  mov     r8d, 2
0x14002aebd  mov     rdx, rax
0x14002aec0  mov     rcx, rdi
0x14002aec3  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::_Func_class<void,std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)
0x14002aec8  lea     rdx, [rbp+57h+var_58]
0x14002aecc  mov     rcx, rbx
0x14002aecf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14002aed4  nop
0x14002aed5  lea     rcx, [rbp+57h+var_58]
0x14002aed9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002aede  jmp     short loc_14002AF5D
0x14002aee0  mov     r14, [r15+178h]
0x14002aee7  mov     rax, [r14]
0x14002aeea  mov     rsi, [rax+20h]
0x14002aeee  lea     rax, [rbp+57h+var_78]
0x14002aef2  mov     [rbp+57h+var_B8], rax
0x14002aef6  lea     rdx, aNoCallbackAssi; "No callback assigned"
0x14002aefd  lea     rcx, [rbp+57h+var_78]
0x14002af01  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002af06  mov     rdi, rax
0x14002af09  lea     rax, [rbp+57h+var_58]
0x14002af0d  mov     [rbp+57h+var_A8], rax
0x14002af11  lea     rdx, aMicrosoftVoice_48; "Microsoft::VoiceAgentServices::Windows:"...
0x14002af18  lea     rcx, [rbp+57h+var_58]
0x14002af1c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002af21  mov     rbx, rax
0x14002af24  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002af2b  lea     rcx, [rbp+57h+var_98]
0x14002af2f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002af34  nop
0x14002af35  mov     [rsp+100h+var_D0], r15
0x14002af3a  mov     [rsp+100h+var_D8], rdi
0x14002af3f  mov     [rsp+100h+var_E0], 0CAh; int
0x14002af47  mov     r9, rbx
0x14002af4a  mov     r8, rax
0x14002af4d  mov     edx, 2
0x14002af52  mov     rcx, r14
0x14002af55  mov     rax, rsi
0x14002af58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af5d  mov     rax, [r15]
0x14002af60  mov     rcx, r15
0x14002af63  mov     rax, [rax+0B0h]
0x14002af6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af6f  mov     rcx, [rbp+5Fh]; this
0x14002af73  test    eax, eax
0x14002af75  jns     short loc_14002AF8B
0x14002af77  mov     r9d, eax; char *
0x14002af7a  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002af81  mov     edx, 0CCh; void *
0x14002af86  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002af8b  mov     rsi, [r15+178h]
0x14002af92  mov     rax, [rsi]
0x14002af95  mov     rdi, [rax+40h]
0x14002af99  lea     rax, [rbp+57h+var_98]
0x14002af9d  mov     [rbp+57h+var_B8], rax
0x14002afa1  lea     rdx, aMicrosoftVoice_48; "Microsoft::VoiceAgentServices::Windows:"...
0x14002afa8  lea     rcx, [rbp+57h+var_98]
0x14002afac  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002afb1  mov     rbx, rax
0x14002afb4  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002afbb  lea     rcx, [rbp+57h+var_78]
0x14002afbf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002afc4  nop
0x14002afc5  mov     qword ptr [rsp+100h+var_E0], r15
0x14002afca  mov     r9d, 0CDh
0x14002afd0  mov     r8, rbx
0x14002afd3  mov     rdx, rax
0x14002afd6  mov     rcx, rsi
0x14002afd9  mov     rax, rdi
0x14002afdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002afe1  mov     rcx, [rbp+57h+var_38]
0x14002afe5  xor     rcx, rsp; StackCookie
0x14002afe8  call    __security_check_cookie
0x14002afed  add     rsp, 0D8h
0x14002aff4  pop     r15
0x14002aff6  pop     r14
0x14002aff8  pop     rdi
0x14002aff9  pop     rsi
0x14002affa  pop     rbx
0x14002affb  pop     rbp
0x14002affc  retn
```

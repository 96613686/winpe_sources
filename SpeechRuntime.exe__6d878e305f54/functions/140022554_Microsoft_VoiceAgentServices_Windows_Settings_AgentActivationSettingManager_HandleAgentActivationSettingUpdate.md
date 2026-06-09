# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::HandleAgentActivationSettingUpdate(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)

- ea: `0x140022554`
- end: `0x1400226bb`
- name: `?HandleAgentActivationSettingUpdate@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@2345@@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140020e7c`

## callees

- `0x140002d30`
- `0x14001296c`
- `0x140012d68`
- `0x140020220`
- `0x140020ff0`
- `0x1400210a8`
- `0x140021658`
- `0x140021c7c`
- `0x140021dd8`
- `0x140022554`
- `0x140031010`

## string_xrefs

- `0x1400225aa`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140022662`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140022599`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::HandleAgentActivationSettingUpdate`
- `0x14002264f`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::HandleAgentActivationSettingUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::HandleAgentActivationSettingUpdate(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, _BYTE *, _BYTE *, __int64, __int64); // rbx
  __int64 v8; // rax
  __int64 v9; // rsi
  void (__fastcall *v10)(__int64, __int64, __int64, __int64, __int64); // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  _BYTE *v14; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-21h] BYREF
  __int64 v16; // [rsp+40h] [rbp-19h]
  _BYTE v17[32]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp+Fh] BYREF

  v16 = a2;
  v15 = a3;
  v6 = *(_QWORD *)(a1 + 376);
  v7 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, __int64))(*(_QWORD *)v6 + 40LL);
  std::string::string(
    v17,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::HandleAgentActivationSettingUpdate");
  std::string::string(
    v18,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v7(v6, v18, v17, 398, a1);
  std::string::~string(v18);
  std::string::~string(v17);
  v14 = (_BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingUpdate<unsigned short const *,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName &>(
    &v14,
    &v15);
  if ( (unsigned __int8)std::function<void (enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsSystemEventKind)>::operator bool(a1 + 168) )
  {
    v8 = std::wstring::wstring(v17, a2);
    std::_Func_class<void,std::wstring,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentConfigurationUpdateKind,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(
      a1 + 168,
      v8,
      2,
      a3);
  }
  v9 = *(_QWORD *)(a1 + 376);
  v10 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64))(*(_QWORD *)v9 + 64LL);
  v14 = v17;
  v11 = std::string::string(
          v17,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::HandleAgentActivationSettingUpdate");
  v12 = std::string::string(
          v18,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v10(v9, v12, v11, 404, a1);
  return std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x140022554  mov     [rsp-8+arg_18], rbx
0x140022559  push    rbp
0x14002255a  push    rsi
0x14002255b  push    rdi
0x14002255c  push    r14
0x14002255e  push    r15
0x140022560  lea     rbp, [rsp-37h]
0x140022565  sub     rsp, 90h
0x14002256c  mov     rax, cs:__security_cookie
0x140022573  xor     rax, rsp
0x140022576  mov     [rbp+57h+var_28], rax
0x14002257a  mov     esi, r8d
0x14002257d  mov     r14, rdx
0x140022580  mov     r15, rcx
0x140022583  mov     [rbp+57h+var_70], rdx
0x140022587  mov     [rbp+57h+var_78], r8d
0x14002258b  mov     rdi, [rcx+178h]
0x140022592  mov     rax, [rdi]
0x140022595  mov     rbx, [rax+28h]
0x140022599  lea     rdx, aMicrosoftVoice_23; "Microsoft::VoiceAgentServices::Windows:"...
0x1400225a0  lea     rcx, [rbp+57h+var_68]
0x1400225a4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400225a9  nop
0x1400225aa  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400225b1  lea     rcx, [rbp+57h+var_48]
0x1400225b5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400225ba  nop
0x1400225bb  mov     [rsp+0B0h+var_90], r15
0x1400225c0  mov     r9d, 18Eh
0x1400225c6  lea     r8, [rbp+57h+var_68]
0x1400225ca  lea     rdx, [rbp+57h+var_48]
0x1400225ce  mov     rcx, rdi
0x1400225d1  mov     rax, rbx
0x1400225d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400225d9  nop
0x1400225da  lea     rcx, [rbp+57h+var_48]
0x1400225de  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400225e3  nop
0x1400225e4  lea     rcx, [rbp+57h+var_68]
0x1400225e8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400225ed  mov     rcx, r14
0x1400225f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400225f5  mov     [rbp+57h+var_80], rax
0x1400225f9  lea     rdx, [rbp+57h+var_78]
0x1400225fd  lea     rcx, [rbp+57h+var_80]
0x140022601  call    ??$AgentActivationSettingUpdate@PEBGAEAW4AgentActivationSettingName@Settings@Windows@VoiceAgentServices@Microsoft@@@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEAW4AgentActivationSettingName@1234@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingUpdate<ushort const *,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName &>(ushort const * &&,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName &)
0x140022606  lea     rbx, [r15+0A8h]
0x14002260d  mov     rcx, rbx
0x140022610  call    ??B?$function@$$A6AXW4AgentActivationSettingsSystemEventKind@Settings@Windows@VoiceAgentServices@Microsoft@@@Z@std@@QEBA_NXZ; std::function<void (Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsSystemEventKind)>::operator bool(void)
0x140022615  test    al, al
0x140022617  jz      short loc_140022639
0x140022619  mov     rdx, r14
0x14002261c  lea     rcx, [rbp+57h+var_68]
0x140022620  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140022625  mov     r9d, esi
0x140022628  mov     r8d, 2
0x14002262e  mov     rdx, rax
0x140022631  mov     rcx, rbx
0x140022634  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentConfigurationUpdateKind@Settings@Windows@VoiceAgentServices@Microsoft@@W4AgentActivationSettingName@4567@@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4AgentConfigurationUpdateKind@Settings@Windows@VoiceAgentServices@Microsoft@@W4AgentActivationSettingName@4567@@Z; std::_Func_class<void,std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentConfigurationUpdateKind,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName>::operator()(std::wstring,Microsoft::VoiceAgentServices::Windows::Settings::AgentConfigurationUpdateKind,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName)
0x140022639  mov     rsi, [r15+178h]
0x140022640  mov     rax, [rsi]
0x140022643  mov     rdi, [rax+40h]
0x140022647  lea     rax, [rbp+57h+var_68]
0x14002264b  mov     [rbp+57h+var_80], rax
0x14002264f  lea     rdx, aMicrosoftVoice_23; "Microsoft::VoiceAgentServices::Windows:"...
0x140022656  lea     rcx, [rbp+57h+var_68]
0x14002265a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002265f  mov     rbx, rax
0x140022662  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140022669  lea     rcx, [rbp+57h+var_48]
0x14002266d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022672  nop
0x140022673  mov     [rsp+0B0h+var_90], r15
0x140022678  mov     r9d, 194h
0x14002267e  mov     r8, rbx
0x140022681  mov     rdx, rax
0x140022684  mov     rcx, rsi
0x140022687  mov     rax, rdi
0x14002268a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002268f  nop
0x140022690  mov     rcx, r14
0x140022693  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140022698  mov     rcx, [rbp+57h+var_28]
0x14002269c  xor     rcx, rsp; StackCookie
0x14002269f  call    __security_check_cookie
0x1400226a4  mov     rbx, [rsp+0B0h+arg_18]
0x1400226ac  add     rsp, 90h
0x1400226b3  pop     r15
0x1400226b5  pop     r14
0x1400226b7  pop     rdi
0x1400226b8  pop     rsi
0x1400226b9  pop     rbp
0x1400226ba  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase(void)

- ea: `0x1400285bc`
- end: `0x14002871e`
- name: `??0AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@IEAA@XZ`
- size: `354`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400273bc`

## callees

- `0x140019c18`
- `0x140020ff0`
- `0x1400210dc`
- `0x140021148`
- `0x140021360`
- `0x140022404`
- `0x1400245e4`
- `0x140031010`

## string_xrefs

- `0x14002866a`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase`
- `0x1400286c7`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase`
- `0x14002867e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x1400286db`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v12[56]; // [rsp+50h] [rbp-38h] BYREF

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'};
  *((_QWORD *)this + 1) = &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'};
  std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>((char *)this + 16);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration::AgentConfiguration((Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *)((char *)this + 32));
  std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>((char *)this + 184);
  std::function<void (void)>::function<void (void)>((char *)this + 208);
  std::wstring::wstring((char *)this + 272);
  *((_BYTE *)this + 328) = 1;
  std::wstring::wstring((char *)this + 344);
  *((_QWORD *)this + 47) = Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance();
  std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>((char *)this + 384);
  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v2 + 80LL);
  v4 = std::string::string(
         v11,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase");
  v5 = std::string::string(
         v12,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v5, v4, 22, this);
  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v6 + 88LL);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::AgentActivationSettingBase");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v7(v6, v9, v8, 23, this);
  return this;
}

```

## disassembly

```asm
0x1400285bc  mov     [rsp+arg_18], rbx
0x1400285c1  mov     [rsp+arg_0], rcx
0x1400285c6  push    rsi
0x1400285c7  push    rdi
0x1400285c8  push    r14
0x1400285ca  sub     rsp, 70h
0x1400285ce  mov     r14, rcx
0x1400285d1  lea     rax, ??_7AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSettingView@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'}
0x1400285d8  mov     [rcx], rax
0x1400285db  lea     rax, ??_7AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSetting@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'}
0x1400285e2  mov     [rcx+8], rax
0x1400285e6  add     rcx, 10h
0x1400285ea  call    ??0?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(void)
0x1400285ef  nop
0x1400285f0  lea     rcx, [r14+20h]; this
0x1400285f4  call    ??0AgentConfiguration@Settings@Windows@VoiceAgentServices@Microsoft@@QEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration::AgentConfiguration(void)
0x1400285f9  nop
0x1400285fa  lea     rcx, [r14+0B8h]
0x140028601  call    ??0?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>(void)
0x140028606  nop
0x140028607  lea     rcx, [r14+0D0h]
0x14002860e  call    ??0?$function@$$A6AXXZ@std@@QEAA@XZ; std::function<void (void)>::function<void (void)>(void)
0x140028613  nop
0x140028614  lea     rcx, [r14+110h]
0x14002861b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140028620  nop
0x140028621  mov     byte ptr [r14+148h], 1
0x140028629  lea     rcx, [r14+158h]
0x140028630  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140028635  nop
0x140028636  call    ?GetInstance@SettingLogger@Settings@Windows@VoiceAgentServices@Microsoft@@SAAEAVILogger@45@XZ; Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance(void)
0x14002863b  mov     [r14+178h], rax
0x140028642  lea     rcx, [r14+180h]
0x140028649  call    ??0?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(void)
0x14002864e  nop
0x14002864f  mov     rsi, [r14+178h]
0x140028656  mov     rax, [rsi]
0x140028659  mov     rdi, [rax+50h]
0x14002865d  lea     rax, [rsp+88h+var_58]
0x140028662  mov     [rsp+88h+arg_8], rax
0x14002866a  lea     rdx, aMicrosoftVoice_42; "Microsoft::VoiceAgentServices::Windows:"...
0x140028671  lea     rcx, [rsp+88h+var_58]
0x140028676  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002867b  mov     rbx, rax
0x14002867e  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028685  lea     rcx, [rsp+88h+var_38]
0x14002868a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002868f  nop
0x140028690  mov     [rsp+88h+var_68], r14
0x140028695  mov     r9d, 16h
0x14002869b  mov     r8, rbx
0x14002869e  mov     rdx, rax
0x1400286a1  mov     rcx, rsi
0x1400286a4  mov     rax, rdi
0x1400286a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400286ac  mov     rsi, [r14+178h]
0x1400286b3  mov     rax, [rsi]
0x1400286b6  mov     rdi, [rax+58h]
0x1400286ba  lea     rax, [rsp+88h+var_38]
0x1400286bf  mov     [rsp+88h+arg_8], rax
0x1400286c7  lea     rdx, aMicrosoftVoice_42; "Microsoft::VoiceAgentServices::Windows:"...
0x1400286ce  lea     rcx, [rsp+88h+var_38]
0x1400286d3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400286d8  mov     rbx, rax
0x1400286db  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400286e2  lea     rcx, [rsp+88h+var_58]
0x1400286e7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400286ec  nop
0x1400286ed  mov     [rsp+88h+var_68], r14
0x1400286f2  mov     r9d, 17h
0x1400286f8  mov     r8, rbx
0x1400286fb  mov     rdx, rax
0x1400286fe  mov     rcx, rsi
0x140028701  mov     rax, rdi
0x140028704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028709  nop
0x14002870a  mov     rax, r14
0x14002870d  mov     rbx, [rsp+88h+arg_18]
0x140028715  add     rsp, 70h
0x140028719  pop     r14
0x14002871b  pop     rdi
0x14002871c  pop     rsi
0x14002871d  retn
```

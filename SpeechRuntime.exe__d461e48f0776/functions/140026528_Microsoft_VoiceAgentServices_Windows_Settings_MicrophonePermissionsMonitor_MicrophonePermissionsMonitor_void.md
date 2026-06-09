# Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor(void)

- ea: `0x140026528`
- end: `0x140026634`
- name: `??0MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ`
- size: `268`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400269d8`

## callees

- `0x140019c18`
- `0x140020ff0`
- `0x140022404`
- `0x1400245e4`
- `0x140031010`

## string_xrefs

- `0x140026583`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor`
- `0x1400265dd`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor`
- `0x140026597`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`
- `0x1400265f1`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *__fastcall Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor(
        Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *this)
{
  struct Microsoft::VoiceAgentServices::ILogger *Instance; // rsi
  void (__fastcall *v3)(struct Microsoft::VoiceAgentServices::ILogger *, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v12[56]; // [rsp+50h] [rbp-38h] BYREF

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::`vftable';
  std::function<void (void)>::function<void (void)>((char *)this + 16);
  *((_QWORD *)this + 10) = 0;
  std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>((char *)this + 88);
  Instance = Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance();
  *((_QWORD *)this + 13) = Instance;
  v3 = *(void (__fastcall **)(struct Microsoft::VoiceAgentServices::ILogger *, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *))(*(_QWORD *)Instance + 80LL);
  v4 = std::string::string(
         v11,
         "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor");
  v5 = std::string::string(
         v12,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v3(Instance, v5, v4, 8, this);
  v6 = *((_QWORD *)this + 13);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *))(*(_QWORD *)v6 + 88LL);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v7(v6, v9, v8, 9, this);
  return this;
}

```

## disassembly

```asm
0x140026528  mov     [rsp+arg_18], rbx
0x14002652d  mov     [rsp+arg_0], rcx
0x140026532  push    rsi
0x140026533  push    rdi
0x140026534  push    r14
0x140026536  sub     rsp, 70h
0x14002653a  mov     r14, rcx
0x14002653d  lea     rax, ??_7MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::`vftable'
0x140026544  mov     [rcx], rax
0x140026547  add     rcx, 10h
0x14002654b  call    ??0?$function@$$A6AXXZ@std@@QEAA@XZ; std::function<void (void)>::function<void (void)>(void)
0x140026550  nop
0x140026551  mov     qword ptr [r14+50h], 0
0x140026559  lea     rcx, [r14+58h]
0x14002655d  call    ??0?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(void)
0x140026562  nop
0x140026563  call    ?GetInstance@SettingLogger@Settings@Windows@VoiceAgentServices@Microsoft@@SAAEAVILogger@45@XZ; Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance(void)
0x140026568  mov     rsi, rax
0x14002656b  mov     [r14+68h], rax
0x14002656f  mov     rcx, [rax]
0x140026572  mov     rdi, [rcx+50h]
0x140026576  lea     rax, [rsp+88h+var_58]
0x14002657b  mov     [rsp+88h+arg_8], rax
0x140026583  lea     rdx, aMicrosoftVoice_6; "Microsoft::VoiceAgentServices::Windows:"...
0x14002658a  lea     rcx, [rsp+88h+var_58]
0x14002658f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026594  mov     rbx, rax
0x140026597  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002659e  lea     rcx, [rsp+88h+var_38]
0x1400265a3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400265a8  nop
0x1400265a9  mov     [rsp+88h+var_68], r14
0x1400265ae  mov     r9d, 8
0x1400265b4  mov     r8, rbx
0x1400265b7  mov     rdx, rax
0x1400265ba  mov     rcx, rsi
0x1400265bd  mov     rax, rdi
0x1400265c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400265c5  mov     rsi, [r14+68h]
0x1400265c9  mov     rax, [rsi]
0x1400265cc  mov     rdi, [rax+58h]
0x1400265d0  lea     rax, [rsp+88h+var_38]
0x1400265d5  mov     [rsp+88h+arg_8], rax
0x1400265dd  lea     rdx, aMicrosoftVoice_6; "Microsoft::VoiceAgentServices::Windows:"...
0x1400265e4  lea     rcx, [rsp+88h+var_38]
0x1400265e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400265ee  mov     rbx, rax
0x1400265f1  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400265f8  lea     rcx, [rsp+88h+var_58]
0x1400265fd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026602  nop
0x140026603  mov     [rsp+88h+var_68], r14
0x140026608  mov     r9d, 9
0x14002660e  mov     r8, rbx
0x140026611  mov     rdx, rax
0x140026614  mov     rcx, rsi
0x140026617  mov     rax, rdi
0x14002661a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002661f  nop
0x140026620  mov     rax, r14
0x140026623  mov     rbx, [rsp+88h+arg_18]
0x14002662b  add     rsp, 70h
0x14002662f  pop     r14
0x140026631  pop     rdi
0x140026632  pop     rsi
0x140026633  retn
```

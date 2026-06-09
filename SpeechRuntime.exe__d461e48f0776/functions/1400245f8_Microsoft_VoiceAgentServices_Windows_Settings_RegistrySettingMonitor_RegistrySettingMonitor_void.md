# Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor(void)

- ea: `0x1400245f8`
- end: `0x140024714`
- name: `??0RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ`
- size: `284`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140024a6c`

## callees

- `0x140019c18`
- `0x140020ff0`
- `0x1400210dc`
- `0x140022404`
- `0x1400245e4`
- `0x140031010`

## string_xrefs

- `0x140024660`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor`
- `0x1400246bd`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor`
- `0x140024674`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x1400246d1`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *__fastcall Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor(
        Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *this)
{
  struct Microsoft::VoiceAgentServices::ILogger *Instance; // rsi
  void (__fastcall *v3)(struct Microsoft::VoiceAgentServices::ILogger *, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v12[56]; // [rsp+50h] [rbp-38h] BYREF

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::`vftable';
  std::wstring::wstring((char *)this + 16);
  std::function<void (void)>::function<void (void)>((char *)this + 48);
  *((_QWORD *)this + 14) = 0;
  std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>((char *)this + 120);
  Instance = Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance();
  *((_QWORD *)this + 17) = Instance;
  v3 = *(void (__fastcall **)(struct Microsoft::VoiceAgentServices::ILogger *, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *))(*(_QWORD *)Instance + 80LL);
  v4 = std::string::string(
         v11,
         "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor");
  v5 = std::string::string(
         v12,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v3(Instance, v5, v4, 8, this);
  v6 = *((_QWORD *)this + 17);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *))(*(_QWORD *)v6 + 88LL);
  v8 = std::string::string(
         v12,
         "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor");
  v9 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v7(v6, v9, v8, 9, this);
  return this;
}

```

## disassembly

```asm
0x1400245f8  mov     [rsp+arg_18], rbx
0x1400245fd  mov     [rsp+arg_0], rcx
0x140024602  push    rsi
0x140024603  push    rdi
0x140024604  push    r14
0x140024606  sub     rsp, 70h
0x14002460a  mov     r14, rcx
0x14002460d  lea     rax, ??_7RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::`vftable'
0x140024614  mov     [rcx], rax
0x140024617  add     rcx, 10h
0x14002461b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140024620  nop
0x140024621  lea     rcx, [r14+30h]
0x140024625  call    ??0?$function@$$A6AXXZ@std@@QEAA@XZ; std::function<void (void)>::function<void (void)>(void)
0x14002462a  nop
0x14002462b  mov     qword ptr [r14+70h], 0
0x140024633  lea     rcx, [r14+78h]
0x140024637  call    ??0?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(void)
0x14002463c  nop
0x14002463d  call    ?GetInstance@SettingLogger@Settings@Windows@VoiceAgentServices@Microsoft@@SAAEAVILogger@45@XZ; Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance(void)
0x140024642  mov     rsi, rax
0x140024645  mov     [r14+88h], rax
0x14002464c  mov     rcx, [rax]
0x14002464f  mov     rdi, [rcx+50h]
0x140024653  lea     rax, [rsp+88h+var_58]
0x140024658  mov     [rsp+88h+arg_8], rax
0x140024660  lea     rdx, aMicrosoftVoice_13; "Microsoft::VoiceAgentServices::Windows:"...
0x140024667  lea     rcx, [rsp+88h+var_58]
0x14002466c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024671  mov     rbx, rax
0x140024674  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002467b  lea     rcx, [rsp+88h+var_38]
0x140024680  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024685  nop
0x140024686  mov     [rsp+88h+var_68], r14
0x14002468b  mov     r9d, 8
0x140024691  mov     r8, rbx
0x140024694  mov     rdx, rax
0x140024697  mov     rcx, rsi
0x14002469a  mov     rax, rdi
0x14002469d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400246a2  mov     rsi, [r14+88h]
0x1400246a9  mov     rax, [rsi]
0x1400246ac  mov     rdi, [rax+58h]
0x1400246b0  lea     rax, [rsp+88h+var_38]
0x1400246b5  mov     [rsp+88h+arg_8], rax
0x1400246bd  lea     rdx, aMicrosoftVoice_13; "Microsoft::VoiceAgentServices::Windows:"...
0x1400246c4  lea     rcx, [rsp+88h+var_38]
0x1400246c9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400246ce  mov     rbx, rax
0x1400246d1  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400246d8  lea     rcx, [rsp+88h+var_58]
0x1400246dd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400246e2  nop
0x1400246e3  mov     [rsp+88h+var_68], r14
0x1400246e8  mov     r9d, 9
0x1400246ee  mov     r8, rbx
0x1400246f1  mov     rdx, rax
0x1400246f4  mov     rcx, rsi
0x1400246f7  mov     rax, rdi
0x1400246fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400246ff  nop
0x140024700  mov     rax, r14
0x140024703  mov     rbx, [rsp+88h+arg_18]
0x14002470b  add     rsp, 70h
0x14002470f  pop     r14
0x140024711  pop     rdi
0x140024712  pop     rsi
0x140024713  retn
```

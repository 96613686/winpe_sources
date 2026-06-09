# Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::~RegistrySettingMonitor(void)

- ea: `0x140024730`
- end: `0x14002482a`
- name: `??1RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@UEAA@XZ`
- size: `250`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140024a30`

## callees

- `0x14001296c`
- `0x140020ff0`
- `0x140021528`
- `0x140021768`
- `0x140023988`
- `0x140024258`
- `0x140031010`

## string_xrefs

- `0x14002476a`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x1400247c4`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x140024756`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::~RegistrySettingMonitor`
- `0x1400247b0`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::~RegistrySettingMonitor`

## pseudocode

```c
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::~RegistrySettingMonitor(
        Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *this)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v10[32]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v11[72]; // [rsp+50h] [rbp-48h] BYREF

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::`vftable';
  v2 = *((_QWORD *)this + 17);
  v3 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *))(*(_QWORD *)v2 + 96LL);
  v4 = std::string::string(
         v10,
         "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::~RegistrySettingMonitor");
  v5 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v3(v2, v5, v4, 14, this);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    (char *)this + 112,
    0);
  v6 = *((_QWORD *)this + 17);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *))(*(_QWORD *)v6 + 104LL);
  v8 = std::string::string(
         v11,
         "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::~RegistrySettingMonitor");
  v9 = std::string::string(
         v10,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v7(v6, v9, v8, 16, this);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref((char *)this + 120);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>((char *)this + 112);
  std::_Func_class<void,>::~_Func_class<void,>((char *)this + 48);
  std::wstring::~wstring((char *)this + 16);
  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor::`vftable';
}

```

## disassembly

```asm
0x140024730  push    rbx
0x140024732  push    rbp
0x140024733  push    rsi
0x140024734  push    rdi
0x140024735  push    r14
0x140024737  sub     rsp, 70h
0x14002473b  mov     r14, rcx
0x14002473e  lea     rax, ??_7RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::`vftable'
0x140024745  mov     [rcx], rax
0x140024748  mov     rsi, [rcx+88h]
0x14002474f  mov     rax, [rsi]
0x140024752  mov     rdi, [rax+60h]
0x140024756  lea     rdx, aMicrosoftVoice_52; "Microsoft::VoiceAgentServices::Windows:"...
0x14002475d  lea     rcx, [rsp+98h+var_68]
0x140024762  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024767  mov     rbx, rax
0x14002476a  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140024771  lea     rcx, [rsp+98h+var_48]
0x140024776  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002477b  mov     [rsp+98h+var_78], r14
0x140024780  mov     r9d, 0Eh
0x140024786  mov     r8, rbx
0x140024789  mov     rdx, rax
0x14002478c  mov     rcx, rsi
0x14002478f  mov     rax, rdi
0x140024792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024797  xor     edx, edx
0x140024799  lea     rcx, [r14+70h]
0x14002479d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x1400247a2  mov     rsi, [r14+88h]
0x1400247a9  mov     rax, [rsi]
0x1400247ac  mov     rdi, [rax+68h]
0x1400247b0  lea     rdx, aMicrosoftVoice_52; "Microsoft::VoiceAgentServices::Windows:"...
0x1400247b7  lea     rcx, [rsp+98h+var_48]
0x1400247bc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400247c1  mov     rbx, rax
0x1400247c4  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400247cb  lea     rcx, [rsp+98h+var_68]
0x1400247d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400247d5  mov     [rsp+98h+var_78], r14
0x1400247da  mov     r9d, 10h
0x1400247e0  mov     r8, rbx
0x1400247e3  mov     rdx, rax
0x1400247e6  mov     rcx, rsi
0x1400247e9  mov     rax, rdi
0x1400247ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400247f1  lea     rcx, [r14+78h]
0x1400247f5  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x1400247fa  lea     rcx, [r14+70h]
0x1400247fe  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x140024803  lea     rcx, [r14+30h]
0x140024807  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x14002480c  lea     rcx, [r14+10h]
0x140024810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024815  lea     rax, ??_7IAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor::`vftable'
0x14002481c  mov     [r14], rax
0x14002481f  add     rsp, 70h
0x140024823  pop     r14
0x140024825  pop     rdi
0x140024826  pop     rsi
0x140024827  pop     rbp
0x140024828  pop     rbx
0x140024829  retn
```

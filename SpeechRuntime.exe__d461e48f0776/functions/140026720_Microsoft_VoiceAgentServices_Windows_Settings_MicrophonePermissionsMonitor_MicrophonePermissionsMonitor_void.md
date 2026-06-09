# Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::~MicrophonePermissionsMonitor(void)

- ea: `0x140026720`
- end: `0x14002680b`
- name: `??1MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@UEAA@XZ`
- size: `235`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140026950`

## callees

- `0x140020ff0`
- `0x140021528`
- `0x140023988`
- `0x1400266b4`
- `0x140026f88`
- `0x140031010`

## string_xrefs

- `0x140026757`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`
- `0x1400267ae`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`
- `0x140026743`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::~MicrophonePermissionsMonitor`
- `0x14002679a`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::~MicrophonePermissionsMonitor`

## pseudocode

```c
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::~MicrophonePermissionsMonitor(
        Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *this)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _BYTE v10[32]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v11[72]; // [rsp+50h] [rbp-48h] BYREF

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::`vftable';
  v2 = *((_QWORD *)this + 13);
  v3 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *))(*(_QWORD *)v2 + 96LL);
  v4 = std::string::string(
         v10,
         "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::~MicrophonePermissionsMonitor");
  v5 = std::string::string(
         v11,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v3(v2, v5, v4, 14, this);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
    (char *)this + 80,
    0);
  v6 = *((_QWORD *)this + 13);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *))(*(_QWORD *)v6 + 104LL);
  v8 = std::string::string(
         v11,
         "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::~MicrophonePermissionsMonitor");
  v9 = std::string::string(
         v10,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v7(v6, v9, v8, 16, this);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref((char *)this + 88);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 80);
  std::_Func_class<void,>::~_Func_class<void,>((char *)this + 16);
  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor::`vftable';
}

```

## disassembly

```asm
0x140026720  push    rbx
0x140026722  push    rbp
0x140026723  push    rsi
0x140026724  push    rdi
0x140026725  push    r14
0x140026727  sub     rsp, 70h
0x14002672b  mov     r14, rcx
0x14002672e  lea     rax, ??_7MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::`vftable'
0x140026735  mov     [rcx], rax
0x140026738  mov     rsi, [rcx+68h]
0x14002673c  mov     rax, [rsi]
0x14002673f  mov     rdi, [rax+60h]
0x140026743  lea     rdx, aMicrosoftVoice_41; "Microsoft::VoiceAgentServices::Windows:"...
0x14002674a  lea     rcx, [rsp+98h+var_68]
0x14002674f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026754  mov     rbx, rax
0x140026757  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002675e  lea     rcx, [rsp+98h+var_48]
0x140026763  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026768  mov     [rsp+98h+var_78], r14
0x14002676d  mov     r9d, 0Eh
0x140026773  mov     r8, rbx
0x140026776  mov     rdx, rax
0x140026779  mov     rcx, rsi
0x14002677c  mov     rax, rdi
0x14002677f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026784  xor     edx, edx
0x140026786  lea     rcx, [r14+50h]
0x14002678a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x14002678f  mov     rsi, [r14+68h]
0x140026793  mov     rax, [rsi]
0x140026796  mov     rdi, [rax+68h]
0x14002679a  lea     rdx, aMicrosoftVoice_41; "Microsoft::VoiceAgentServices::Windows:"...
0x1400267a1  lea     rcx, [rsp+98h+var_48]
0x1400267a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400267ab  mov     rbx, rax
0x1400267ae  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400267b5  lea     rcx, [rsp+98h+var_68]
0x1400267ba  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400267bf  mov     [rsp+98h+var_78], r14
0x1400267c4  mov     r9d, 10h
0x1400267ca  mov     r8, rbx
0x1400267cd  mov     rdx, rax
0x1400267d0  mov     rcx, rsi
0x1400267d3  mov     rax, rdi
0x1400267d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400267db  lea     rcx, [r14+58h]
0x1400267df  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x1400267e4  lea     rcx, [r14+50h]
0x1400267e8  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1400267ed  lea     rcx, [r14+10h]
0x1400267f1  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1400267f6  lea     rax, ??_7IAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor::`vftable'
0x1400267fd  mov     [r14], rax
0x140026800  add     rsp, 70h
0x140026804  pop     r14
0x140026806  pop     rdi
0x140026807  pop     rsi
0x140026808  pop     rbp
0x140026809  pop     rbx
0x14002680a  retn
```

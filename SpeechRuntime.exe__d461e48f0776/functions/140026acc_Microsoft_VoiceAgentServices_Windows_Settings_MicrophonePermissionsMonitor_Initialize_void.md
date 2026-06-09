# Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize(void)

- ea: `0x140026acc`
- end: `0x140026d2b`
- name: `?Initialize@MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ`
- size: `607`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400269d8`

## callees

- `0x140002d30`
- `0x140013c58`
- `0x140019bfc`
- `0x140020dc4`
- `0x140020f1c`
- `0x140020ff0`
- `0x140021658`
- `0x140023988`
- `0x140026344`
- `0x1400266b4`
- `0x140026acc`
- `0x140026f88`
- `0x140031010`

## string_xrefs

- `0x140026b02`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize`
- `0x140026c98`: `Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize`
- `0x140026b17`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`
- `0x140026cac`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize(
        Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *); // rsi
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *, _QWORD); // r15
  int v8; // r8d
  __int64 v9; // r14
  __int64 v10; // rsi
  __int64 v11; // rax
  _BYTE *v13; // [rsp+40h] [rbp-158h] BYREF
  _QWORD v14[2]; // [rsp+48h] [rbp-150h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-140h] BYREF
  _BYTE v16[32]; // [rsp+78h] [rbp-120h] BYREF
  _BYTE v17[32]; // [rsp+98h] [rbp-100h] BYREF
  _BYTE v18[32]; // [rsp+B8h] [rbp-E0h] BYREF
  _BYTE v19[32]; // [rsp+D8h] [rbp-C0h] BYREF
  _BYTE v20[8]; // [rsp+F8h] [rbp-A0h] BYREF
  void **v21; // [rsp+100h] [rbp-98h] BYREF
  _BYTE v22[96]; // [rsp+108h] [rbp-90h] BYREF
  void ***v23; // [rsp+168h] [rbp-30h]

  v2 = *((_QWORD *)this + 13);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *))(*(_QWORD *)v2 + 40LL);
  std::string::string(v18, "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize");
  std::string::string(
    v19,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v3(v2, v19, v18, 43, this);
  std::string::~string(v19);
  std::string::~string(v18);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(v19);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
    v19,
    (char *)this + 88);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(v18);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
    v18,
    v19);
  v23 = 0;
  v21 = &wistd::__function::__func<_lambda_e3fe99c513cb9a7a285c998437d908d3_,void (void)>::`vftable';
  lambda_e3fe99c513cb9a7a285c998437d908d3_::_lambda_e3fe99c513cb9a7a285c998437d908d3_(v22, v18);
  v23 = &v21;
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v18);
  v13 = 0;
  if ( (int)wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v4, v20, v5, &v13) < 0 )
    v14[0] = 0;
  else
    v14[0] = v13;
  if ( (_QWORD *)((char *)this + 80) != v14 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset();
    v14[0] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v14);
  wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>(v20);
  v6 = *((_QWORD *)this + 13);
  v7 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *, _QWORD))(*(_QWORD *)v6 + 72LL);
  v13 = v15;
  v9 = std::string::string(v15, "hr = 0x%x", v8);
  v14[1] = v16;
  v10 = std::string::string(
          v16,
          "Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize");
  v11 = std::string::string(
          v17,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp");
  v7(v6, v11, v10, 59, v9, this, 0);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v19);
  return 0;
}

```

## disassembly

```asm
0x140026acc  mov     [rsp+arg_8], rbx
0x140026ad1  mov     [rsp+arg_10], rsi
0x140026ad6  push    rdi
0x140026ad7  push    r14
0x140026ad9  push    r15
0x140026adb  sub     rsp, 180h
0x140026ae2  mov     rax, cs:__security_cookie
0x140026ae9  xor     rax, rsp
0x140026aec  mov     [rsp+198h+var_28], rax
0x140026af4  mov     rbx, rcx
0x140026af7  mov     rdi, [rcx+68h]
0x140026afb  mov     rax, [rdi]
0x140026afe  mov     rsi, [rax+28h]
0x140026b02  lea     rdx, aMicrosoftVoice_32; "Microsoft::VoiceAgentServices::Windows:"...
0x140026b09  lea     rcx, [rsp+198h+var_E0]
0x140026b11  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026b16  nop
0x140026b17  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026b1e  lea     rcx, [rsp+198h+var_C0]
0x140026b26  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026b2b  nop
0x140026b2c  mov     [rsp+198h+var_178], rbx
0x140026b31  mov     r9d, 2Bh ; '+'
0x140026b37  lea     r8, [rsp+198h+var_E0]
0x140026b3f  lea     rdx, [rsp+198h+var_C0]
0x140026b47  mov     rcx, rdi
0x140026b4a  mov     rax, rsi
0x140026b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026b52  nop
0x140026b53  lea     rcx, [rsp+198h+var_C0]
0x140026b5b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140026b60  nop
0x140026b61  lea     rcx, [rsp+198h+var_E0]
0x140026b69  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140026b6e  lea     rcx, [rsp+198h+var_C0]
0x140026b76  call    ??0?$_Ptr_base@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAA@XZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(void)
0x140026b7b  lea     rdx, [rbx+58h]
0x140026b7f  lea     rcx, [rsp+198h+var_C0]
0x140026b87  call    ??$_Weakly_construct_from@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@?$_Ptr_base@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXAEBV01@@Z; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140026b8c  nop
0x140026b8d  lea     rcx, [rsp+198h+var_E0]
0x140026b95  call    ??0?$_Ptr_base@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAA@XZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(void)
0x140026b9a  lea     rdx, [rsp+198h+var_C0]
0x140026ba2  lea     rcx, [rsp+198h+var_E0]
0x140026baa  call    ??$_Weakly_construct_from@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@?$_Ptr_base@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXAEBV01@@Z; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140026baf  mov     [rsp+198h+var_30], 0
0x140026bbb  lea     rax, ??_7?$__func@V_lambda_e3fe99c513cb9a7a285c998437d908d3_@@$$A6AXXZ@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e3fe99c513cb9a7a285c998437d908d3_,void (void)>::`vftable'
0x140026bc2  mov     [rsp+198h+var_98], rax
0x140026bca  lea     rdx, [rsp+198h+var_E0]
0x140026bd2  lea     rcx, [rsp+198h+var_90]
0x140026bda  call    _lambda_e3fe99c513cb9a7a285c998437d908d3____lambda_e3fe99c513cb9a7a285c998437d908d3_
0x140026bdf  lea     rcx, [rsp+198h+var_98]
0x140026be7  mov     [rsp+198h+var_30], rcx
0x140026bef  lea     rcx, [rsp+198h+var_E0]
0x140026bf7  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140026bfc  mov     [rsp+198h+var_158], 0
0x140026c05  lea     r9, [rsp+198h+var_158]
0x140026c0a  lea     rdx, [rsp+198h+var_A0]
0x140026c12  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x140026c17  test    eax, eax
0x140026c19  js      short loc_140026C27
0x140026c1b  mov     rdx, [rsp+198h+var_158]
0x140026c20  mov     [rsp+198h+var_150], rdx
0x140026c25  jmp     short loc_140026C32
0x140026c27  mov     [rsp+198h+var_150], 0
0x140026c30  xor     edx, edx
0x140026c32  lea     rcx, [rbx+50h]
0x140026c36  lea     rax, [rsp+198h+var_150]
0x140026c3b  cmp     rcx, rax
0x140026c3e  jz      short loc_140026C4E
0x140026c40  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x140026c45  mov     [rsp+198h+var_150], 0
0x140026c4e  lea     rcx, [rsp+198h+var_150]
0x140026c53  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x140026c58  lea     rcx, [rsp+198h+var_A0]
0x140026c60  call    ??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ; wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)
0x140026c65  mov     rdi, [rbx+68h]
0x140026c69  mov     rax, [rdi]
0x140026c6c  mov     r15, [rax+48h]
0x140026c70  lea     rax, [rsp+198h+var_140]
0x140026c75  mov     [rsp+198h+var_158], rax
0x140026c7a  lea     rdx, aHr0xX; "hr = 0x%x"
0x140026c81  lea     rcx, [rsp+198h+var_140]
0x140026c86  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026c8b  mov     r14, rax
0x140026c8e  lea     rax, [rsp+198h+var_120]
0x140026c93  mov     [rsp+198h+var_148], rax
0x140026c98  lea     rdx, aMicrosoftVoice_32; "Microsoft::VoiceAgentServices::Windows:"...
0x140026c9f  lea     rcx, [rsp+198h+var_120]
0x140026ca4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026ca9  mov     rsi, rax
0x140026cac  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026cb3  lea     rcx, [rsp+198h+var_100]
0x140026cbb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140026cc0  nop
0x140026cc1  mov     [rsp+198h+var_168], 0
0x140026cca  mov     [rsp+198h+var_170], rbx
0x140026ccf  mov     [rsp+198h+var_178], r14
0x140026cd4  mov     r9d, 3Bh ; ';'
0x140026cda  mov     r8, rsi
0x140026cdd  mov     rdx, rax
0x140026ce0  mov     rcx, rdi
0x140026ce3  mov     rax, r15
0x140026ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026ceb  nop
0x140026cec  lea     rcx, [rsp+198h+var_C0]
0x140026cf4  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140026cf9  xor     eax, eax
0x140026cfb  jmp     short loc_140026D01
0x140026cfd  mov     eax, dword ptr [rsp+198h+var_158]
0x140026d01  mov     rcx, [rsp+198h+var_28]
0x140026d09  xor     rcx, rsp; StackCookie
0x140026d0c  call    __security_check_cookie
0x140026d11  lea     r11, [rsp+198h+var_18]
0x140026d19  mov     rbx, [r11+28h]
0x140026d1d  mov     rsi, [r11+30h]
0x140026d21  mov     rsp, r11
0x140026d24  pop     r15
0x140026d26  pop     r14
0x140026d28  pop     rdi
0x140026d29  retn
```

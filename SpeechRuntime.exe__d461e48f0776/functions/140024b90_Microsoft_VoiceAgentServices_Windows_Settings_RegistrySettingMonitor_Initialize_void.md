# Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize(void)

- ea: `0x140024b90`
- end: `0x140024e17`
- name: `?Initialize@RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ`
- size: `647`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140024a6c`

## callees

- `0x140002d30`
- `0x140012d68`
- `0x140013c58`
- `0x140019bfc`
- `0x140020dc4`
- `0x140020f1c`
- `0x140020ff0`
- `0x140021658`
- `0x140021768`
- `0x140021c44`
- `0x140023988`
- `0x140024130`
- `0x1400244c4`
- `0x140024b90`
- `0x140031010`

## string_xrefs

- `0x140024bde`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x140024d98`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x140024bc9`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize`
- `0x140024d84`: `Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize(
        Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *this)
{
  __int64 v2; // rbx
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *); // rsi
  const wchar_t *v4; // rax
  int v5; // eax
  int v6; // r9d
  __int64 registry_watcher; // rax
  __int64 v8; // rbx
  void (__fastcall *v9)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *, _QWORD); // r15
  int v10; // r8d
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rax
  const wchar_t *v15; // [rsp+40h] [rbp-148h] BYREF
  _BYTE *v16; // [rsp+48h] [rbp-140h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-138h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp-118h] BYREF
  _BYTE v19[32]; // [rsp+90h] [rbp-F8h] BYREF
  _BYTE v20[32]; // [rsp+B0h] [rbp-D8h] BYREF
  _BYTE v21[32]; // [rsp+D0h] [rbp-B8h] BYREF
  _BYTE v22[8]; // [rsp+F0h] [rbp-98h] BYREF
  void **v23; // [rsp+F8h] [rbp-90h] BYREF
  _BYTE v24[96]; // [rsp+100h] [rbp-88h] BYREF
  void ***v25; // [rsp+160h] [rbp-28h]

  v2 = *((_QWORD *)this + 17);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *))(*(_QWORD *)v2 + 40LL);
  std::string::string(v20, "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize");
  std::string::string(
    v21,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v3(v2, v21, v20, 45, this);
  std::string::~string(v21);
  std::string::~string(v20);
  v16 = (_BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 16);
  v4 = L"HKCU";
  if ( *((_QWORD *)this + 1) != -2147483647 )
    v4 = L"HKLM";
  v15 = v4;
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::RegistrySettingMonitorSetup<unsigned short const *,unsigned short const *>(
    &v15,
    &v16);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(v21);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
    v21,
    (char *)this + 120);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(v20);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
    v20,
    v21);
  v25 = 0;
  v23 = &wistd::__function::__func<_lambda_80b08b6f555ca3773a66f833209d2d64_,void (enum wil::RegistryChangeKind)>::`vftable';
  lambda_e3fe99c513cb9a7a285c998437d908d3_::_lambda_e3fe99c513cb9a7a285c998437d908d3_(v24, v20);
  v25 = &v23;
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v20);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 16);
  LOBYTE(v6) = 1;
  registry_watcher = wil::make_registry_watcher((unsigned int)&v15, *((_QWORD *)this + 1), v5, v6, (__int64)v22);
  wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(
    (char *)this + 112,
    registry_watcher);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v15);
  wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>(v22);
  v8 = *((_QWORD *)this + 17);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *, _QWORD))(*(_QWORD *)v8 + 72LL);
  v15 = (const wchar_t *)v17;
  v11 = std::string::string(v17, "hr = 0x%x", v10);
  v16 = v18;
  v12 = std::string::string(v18, "Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize");
  v13 = std::string::string(
          v19,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp");
  v9(v8, v13, v12, 64, v11, this, 0);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v21);
  return 0;
}

```

## disassembly

```asm
0x140024b90  mov     [rsp+arg_8], rbx
0x140024b95  mov     [rsp+arg_10], rsi
0x140024b9a  push    rdi
0x140024b9b  push    r14
0x140024b9d  push    r15
0x140024b9f  sub     rsp, 170h
0x140024ba6  mov     rax, cs:__security_cookie
0x140024bad  xor     rax, rsp
0x140024bb0  mov     [rsp+188h+var_20], rax
0x140024bb8  mov     rdi, rcx
0x140024bbb  mov     rbx, [rcx+88h]
0x140024bc2  mov     rax, [rbx]
0x140024bc5  mov     rsi, [rax+28h]
0x140024bc9  lea     rdx, aMicrosoftVoice_7; "Microsoft::VoiceAgentServices::Windows:"...
0x140024bd0  lea     rcx, [rsp+188h+var_D8]
0x140024bd8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024bdd  nop
0x140024bde  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140024be5  lea     rcx, [rsp+188h+var_B8]
0x140024bed  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024bf2  nop
0x140024bf3  mov     [rsp+188h+var_168], rdi
0x140024bf8  mov     r9d, 2Dh ; '-'
0x140024bfe  lea     r8, [rsp+188h+var_D8]
0x140024c06  lea     rdx, [rsp+188h+var_B8]
0x140024c0e  mov     rcx, rbx
0x140024c11  mov     rax, rsi
0x140024c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c19  nop
0x140024c1a  lea     rcx, [rsp+188h+var_B8]
0x140024c22  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140024c27  nop
0x140024c28  lea     rcx, [rsp+188h+var_D8]
0x140024c30  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140024c35  lea     rcx, [rdi+10h]
0x140024c39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140024c3e  mov     [rsp+188h+var_140], rax
0x140024c43  lea     rcx, aHklm; "HKLM"
0x140024c4a  lea     rax, aHkcu; "HKCU"
0x140024c51  cmp     qword ptr [rdi+8], 0FFFFFFFF80000001h
0x140024c59  cmovnz  rax, rcx
0x140024c5d  mov     [rsp+188h+var_148], rax
0x140024c62  lea     rdx, [rsp+188h+var_140]
0x140024c67  lea     rcx, [rsp+188h+var_148]
0x140024c6c  call    ??$RegistrySettingMonitorSetup@PEBGPEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG0@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::RegistrySettingMonitorSetup<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x140024c71  lea     rcx, [rsp+188h+var_B8]
0x140024c79  call    ??0?$_Ptr_base@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAA@XZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(void)
0x140024c7e  lea     rdx, [rdi+78h]
0x140024c82  lea     rcx, [rsp+188h+var_B8]
0x140024c8a  call    ??$_Weakly_construct_from@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@?$_Ptr_base@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXAEBV01@@Z; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140024c8f  nop
0x140024c90  lea     rcx, [rsp+188h+var_D8]
0x140024c98  call    ??0?$_Ptr_base@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAA@XZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(void)
0x140024c9d  lea     rdx, [rsp+188h+var_B8]
0x140024ca5  lea     rcx, [rsp+188h+var_D8]
0x140024cad  call    ??$_Weakly_construct_from@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@?$_Ptr_base@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXAEBV01@@Z; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140024cb2  mov     [rsp+188h+var_28], 0
0x140024cbe  lea     rax, ??_7?$__func@V_lambda_80b08b6f555ca3773a66f833209d2d64_@@$$A6AXW4RegistryChangeKind@wil@@@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_80b08b6f555ca3773a66f833209d2d64_,void (wil::RegistryChangeKind)>::`vftable'
0x140024cc5  mov     [rsp+188h+var_90], rax
0x140024ccd  lea     rdx, [rsp+188h+var_D8]
0x140024cd5  lea     rcx, [rsp+188h+var_88]
0x140024cdd  call    _lambda_e3fe99c513cb9a7a285c998437d908d3____lambda_e3fe99c513cb9a7a285c998437d908d3_
0x140024ce2  lea     rcx, [rsp+188h+var_90]
0x140024cea  mov     [rsp+188h+var_28], rcx
0x140024cf2  lea     rcx, [rsp+188h+var_D8]
0x140024cfa  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140024cff  nop
0x140024d00  lea     rcx, [rdi+10h]
0x140024d04  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140024d09  lea     rcx, [rsp+188h+var_98]
0x140024d11  mov     [rsp+188h+var_168], rcx
0x140024d16  mov     r9b, 1
0x140024d19  mov     r8, rax
0x140024d1c  mov     rdx, [rdi+8]
0x140024d20  lea     rcx, [rsp+188h+var_148]
0x140024d25  call    ?make_registry_watcher@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::make_registry_watcher(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x140024d2a  lea     rcx, [rdi+70h]
0x140024d2e  mov     rdx, rax
0x140024d31  call    ??4?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> &&)
0x140024d36  lea     rcx, [rsp+188h+var_148]
0x140024d3b  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x140024d40  nop
0x140024d41  lea     rcx, [rsp+188h+var_98]
0x140024d49  call    ??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ; wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)
0x140024d4e  mov     rbx, [rdi+88h]
0x140024d55  mov     rax, [rbx]
0x140024d58  mov     r15, [rax+48h]
0x140024d5c  lea     rax, [rsp+188h+var_138]
0x140024d61  mov     [rsp+188h+var_148], rax
0x140024d66  lea     rdx, aHr0xX; "hr = 0x%x"
0x140024d6d  lea     rcx, [rsp+188h+var_138]
0x140024d72  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024d77  mov     r14, rax
0x140024d7a  lea     rax, [rsp+188h+var_118]
0x140024d7f  mov     [rsp+188h+var_140], rax
0x140024d84  lea     rdx, aMicrosoftVoice_7; "Microsoft::VoiceAgentServices::Windows:"...
0x140024d8b  lea     rcx, [rsp+188h+var_118]
0x140024d90  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024d95  mov     rsi, rax
0x140024d98  lea     rdx, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140024d9f  lea     rcx, [rsp+188h+var_F8]
0x140024da7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024dac  nop
0x140024dad  mov     [rsp+188h+var_158], 0
0x140024db6  mov     [rsp+188h+var_160], rdi
0x140024dbb  mov     [rsp+188h+var_168], r14
0x140024dc0  mov     r9d, 40h ; '@'
0x140024dc6  mov     r8, rsi
0x140024dc9  mov     rdx, rax
0x140024dcc  mov     rcx, rbx
0x140024dcf  mov     rax, r15
0x140024dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024dd7  nop
0x140024dd8  lea     rcx, [rsp+188h+var_B8]
0x140024de0  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140024de5  xor     eax, eax
0x140024de7  jmp     short loc_140024DED
0x140024de9  mov     eax, dword ptr [rsp+188h+var_140]
0x140024ded  mov     rcx, [rsp+188h+var_20]
0x140024df5  xor     rcx, rsp; StackCookie
0x140024df8  call    __security_check_cookie
0x140024dfd  lea     r11, [rsp+188h+var_18]
0x140024e05  mov     rbx, [r11+28h]
0x140024e09  mov     rsi, [r11+30h]
0x140024e0d  mov     rsp, r11
0x140024e10  pop     r15
0x140024e12  pop     r14
0x140024e14  pop     rdi
0x140024e15  retn
```

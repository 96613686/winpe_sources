# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents(void)

- ea: `0x140023438`
- end: `0x140023721`
- name: `?SubscribeForSystemEvents@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ`
- size: `745`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400226c4`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x14001296c`
- `0x140013c58`
- `0x140019bfc`
- `0x14001ae60`
- `0x14002007c`
- `0x1400201ac`
- `0x140020dc4`
- `0x140020f1c`
- `0x140020ff0`
- `0x140021658`
- `0x140021768`
- `0x140021b80`
- `0x140021c44`
- `0x140022480`
- `0x140023438`
- `0x140023988`
- `0x140024130`
- `0x140031010`

## string_xrefs

- `0x140023486`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140023632`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x1400236a2`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140023471`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents`
- `0x14002368e`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)
{
  __int64 v2; // rbx
  void (__fastcall *v3)(__int64, int *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *); // rsi
  __int64 String; // rax
  __int64 registry_watcher; // rax
  int v6; // r8d
  __int64 v8; // rbx
  void (__fastcall *v9)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD); // r15
  __int64 v10; // r14
  __int64 v11; // rsi
  __int64 v12; // rax
  int v13; // [rsp+20h] [rbp-168h]
  _QWORD v14[2]; // [rsp+40h] [rbp-148h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-138h] BYREF
  _BYTE v16[32]; // [rsp+70h] [rbp-118h] BYREF
  _BYTE v17[32]; // [rsp+90h] [rbp-F8h] BYREF
  _BYTE v18[32]; // [rsp+B0h] [rbp-D8h] BYREF
  int v19[8]; // [rsp+D0h] [rbp-B8h] BYREF
  int v20; // [rsp+F0h] [rbp-98h] BYREF
  void **v21; // [rsp+F8h] [rbp-90h] BYREF
  _BYTE v22[96]; // [rsp+100h] [rbp-88h] BYREF
  void ***v23; // [rsp+160h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, int *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v18,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents");
  std::string::string(
    v19,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v3(v2, v19, v18, 330, this);
  std::string::~string(v19);
  std::string::~string(v18);
  String = SpRegUtil::GetString(
             (int)v19,
             -2147483647,
             (int)L"SOFTWARE\\Microsoft\\Speech_OneCore\\Settings\\SpeechRecognizer",
             (int)L"RecognizedLanguage",
             (unsigned __int16 *)&byte_140034BFC);
  std::wstring::operator=((char *)this + 304, String);
  std::wstring::~wstring(v19);
  std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
    v18,
    (char *)this + 8);
  std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
    v19,
    v18);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v18);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(v18);
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
    v18,
    v19);
  v23 = 0;
  v21 = &wistd::__function::__func<_lambda_b11965a84a817caa8852f69bfbdd9632_,void (enum wil::RegistryChangeKind)>::`vftable';
  lambda_e3fe99c513cb9a7a285c998437d908d3_::_lambda_e3fe99c513cb9a7a285c998437d908d3_(v22, v18);
  v23 = &v21;
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v18);
  registry_watcher = wil::make_registry_watcher(
                       (unsigned int)v14,
                       -2147483647,
                       (unsigned int)L"SOFTWARE\\Microsoft\\Speech_OneCore\\Settings\\SpeechRecognizer",
                       0,
                       (__int64)&v20);
  wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(
    (char *)this + 296,
    registry_watcher);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(v14);
  wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>(&v20);
  if ( *((_QWORD *)this + 37) )
  {
    v8 = *((_QWORD *)this + 47);
    v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD))(*(_QWORD *)v8 + 72LL);
    v14[0] = v15;
    v10 = std::string::string(v15, "hr = 0x%x", v6);
    v14[1] = v16;
    v11 = std::string::string(
            v16,
            "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::SubscribeForSystemEvents");
    v12 = std::string::string(
            v17,
            "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
    v9(v8, v12, v11, 357, v10, this, 0);
    std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v19);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
      (const char *)0x8007000ELL,
      v13);
    std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v19);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140023438  mov     [rsp+arg_8], rbx
0x14002343d  mov     [rsp+arg_10], rsi
0x140023442  push    rdi
0x140023443  push    r14
0x140023445  push    r15
0x140023447  sub     rsp, 170h
0x14002344e  mov     rax, cs:__security_cookie
0x140023455  xor     rax, rsp
0x140023458  mov     [rsp+188h+var_20], rax
0x140023460  mov     rdi, rcx
0x140023463  mov     rbx, [rcx+178h]
0x14002346a  mov     rax, [rbx]
0x14002346d  mov     rsi, [rax+28h]
0x140023471  lea     rdx, aMicrosoftVoice_33; "Microsoft::VoiceAgentServices::Windows:"...
0x140023478  lea     rcx, [rsp+188h+var_D8]
0x140023480  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140023485  nop
0x140023486  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002348d  lea     rcx, [rsp+188h+var_B8]
0x140023495  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002349a  nop
0x14002349b  mov     [rsp+188h+var_168], rdi
0x1400234a0  mov     r9d, 14Ah
0x1400234a6  lea     r8, [rsp+188h+var_D8]
0x1400234ae  lea     rdx, [rsp+188h+var_B8]
0x1400234b6  mov     rcx, rbx
0x1400234b9  mov     rax, rsi
0x1400234bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400234c1  nop
0x1400234c2  lea     rcx, [rsp+188h+var_B8]
0x1400234ca  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400234cf  nop
0x1400234d0  lea     rcx, [rsp+188h+var_D8]
0x1400234d8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400234dd  lea     rax, byte_140034BFC
0x1400234e4  mov     [rsp+188h+var_168], rax; unsigned __int16 *
0x1400234e9  lea     r9, aRecognizedlang; "RecognizedLanguage"
0x1400234f0  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Speech_OneCore\\Se"...
0x1400234f7  mov     rbx, 0FFFFFFFF80000001h
0x1400234fe  mov     rdx, rbx; int
0x140023501  lea     rcx, [rsp+188h+var_B8]; int
0x140023509  call    ?GetString@SpRegUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG11@Z; SpRegUtil::GetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14002350e  lea     rcx, [rdi+130h]
0x140023515  mov     rdx, rax
0x140023518  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14002351d  lea     rcx, [rsp+188h+var_B8]
0x140023525  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002352a  lea     rdx, [rdi+8]
0x14002352e  lea     rcx, [rsp+188h+var_D8]
0x140023536  call    ??$?0VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@AEBV?$weak_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x14002353b  lea     rdx, [rsp+188h+var_D8]
0x140023543  lea     rcx, [rsp+188h+var_B8]
0x14002354b  call    ??$?0VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$weak_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140023550  nop
0x140023551  lea     rcx, [rsp+188h+var_D8]
0x140023559  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x14002355e  lea     rcx, [rsp+188h+var_D8]
0x140023566  call    ??0?$_Ptr_base@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAA@XZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(void)
0x14002356b  lea     rdx, [rsp+188h+var_B8]
0x140023573  lea     rcx, [rsp+188h+var_D8]
0x14002357b  call    ??$_Weakly_construct_from@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@?$_Ptr_base@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXAEBV01@@Z; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140023580  mov     [rsp+188h+var_28], 0
0x14002358c  lea     rax, ??_7?$__func@V_lambda_b11965a84a817caa8852f69bfbdd9632_@@$$A6AXW4RegistryChangeKind@wil@@@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_b11965a84a817caa8852f69bfbdd9632_,void (wil::RegistryChangeKind)>::`vftable'
0x140023593  mov     [rsp+188h+var_90], rax
0x14002359b  lea     rdx, [rsp+188h+var_D8]
0x1400235a3  lea     rcx, [rsp+188h+var_88]
0x1400235ab  call    _lambda_e3fe99c513cb9a7a285c998437d908d3____lambda_e3fe99c513cb9a7a285c998437d908d3_
0x1400235b0  lea     rcx, [rsp+188h+var_90]
0x1400235b8  mov     [rsp+188h+var_28], rcx
0x1400235c0  lea     rcx, [rsp+188h+var_D8]
0x1400235c8  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x1400235cd  nop
0x1400235ce  lea     rax, [rsp+188h+var_98]
0x1400235d6  mov     [rsp+188h+var_168], rax; int
0x1400235db  xor     r9d, r9d
0x1400235de  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Speech_OneCore\\Se"...
0x1400235e5  mov     rdx, rbx
0x1400235e8  lea     rcx, [rsp+188h+var_148]
0x1400235ed  call    ?make_registry_watcher@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::make_registry_watcher(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1400235f2  lea     rbx, [rdi+128h]
0x1400235f9  mov     rdx, rax
0x1400235fc  mov     rcx, rbx
0x1400235ff  call    ??4?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> &&)
0x140023604  lea     rcx, [rsp+188h+var_148]
0x140023609  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x14002360e  nop
0x14002360f  lea     rcx, [rsp+188h+var_98]
0x140023617  call    ??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ; wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)
0x14002361c  cmp     qword ptr [rbx], 0
0x140023620  jnz     short loc_140023658
0x140023622  mov     rcx, [rsp+188h]; this
0x14002362a  mov     ebx, 8007000Eh
0x14002362f  mov     r9d, ebx; char *
0x140023632  lea     r8, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140023639  mov     edx, 163h; void *
0x14002363e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023643  nop
0x140023644  lea     rcx, [rsp+188h+var_B8]
0x14002364c  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140023651  mov     eax, ebx
0x140023653  jmp     loc_1400236F7
0x140023658  mov     rbx, [rdi+178h]
0x14002365f  mov     rax, [rbx]
0x140023662  mov     r15, [rax+48h]
0x140023666  lea     rax, [rsp+188h+var_138]
0x14002366b  mov     [rsp+188h+var_148], rax
0x140023670  lea     rdx, aHr0xX; "hr = 0x%x"
0x140023677  lea     rcx, [rsp+188h+var_138]
0x14002367c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140023681  mov     r14, rax
0x140023684  lea     rax, [rsp+188h+var_118]
0x140023689  mov     [rsp+188h+var_140], rax
0x14002368e  lea     rdx, aMicrosoftVoice_33; "Microsoft::VoiceAgentServices::Windows:"...
0x140023695  lea     rcx, [rsp+188h+var_118]
0x14002369a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002369f  mov     rsi, rax
0x1400236a2  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400236a9  lea     rcx, [rsp+188h+var_F8]
0x1400236b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400236b6  nop
0x1400236b7  mov     [rsp+188h+var_158], 0
0x1400236c0  mov     [rsp+188h+var_160], rdi
0x1400236c5  mov     [rsp+188h+var_168], r14
0x1400236ca  mov     r9d, 165h
0x1400236d0  mov     r8, rsi
0x1400236d3  mov     rdx, rax
0x1400236d6  mov     rcx, rbx
0x1400236d9  mov     rax, r15
0x1400236dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400236e1  nop
0x1400236e2  lea     rcx, [rsp+188h+var_B8]
0x1400236ea  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x1400236ef  xor     eax, eax
0x1400236f1  jmp     short loc_1400236F7
0x1400236f3  mov     eax, dword ptr [rsp+188h+var_148]
0x1400236f7  mov     rcx, [rsp+188h+var_20]
0x1400236ff  xor     rcx, rsp; StackCookie
0x140023702  call    __security_check_cookie
0x140023707  lea     r11, [rsp+188h+var_18]
0x14002370f  mov     rbx, [r11+28h]
0x140023713  mov     rsi, [r11+30h]
0x140023717  mov     rsp, r11
0x14002371a  pop     r15
0x14002371c  pop     r14
0x14002371e  pop     rdi
0x14002371f  retn
```

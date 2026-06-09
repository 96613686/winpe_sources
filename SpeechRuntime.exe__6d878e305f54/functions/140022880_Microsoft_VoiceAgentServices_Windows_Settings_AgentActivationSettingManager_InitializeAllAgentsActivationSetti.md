# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting(void)

- ea: `0x140022880`
- end: `0x140022b7a`
- name: `?InitializeAllAgentsActivationSetting@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ`
- size: `762`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400226c4`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x1400128b8`
- `0x14001296c`
- `0x140019bfc`
- `0x140019c18`
- `0x14001ae60`
- `0x14002001c`
- `0x14002007c`
- `0x1400201ac`
- `0x140020dc4`
- `0x140020ff0`
- `0x140021148`
- `0x140021658`
- `0x140022880`
- `0x140023988`
- `0x140023be0`
- `0x140024164`
- `0x140024a6c`
- `0x140025630`
- `0x1400269d8`
- `0x1400275ec`
- `0x140031010`

## string_xrefs

- `0x1400228ce`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x1400228bd`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting`
- `0x140022adb`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  __int64 RegistryConfigurationPath; // rax
  __int64 v5; // rcx
  int Instance; // ebx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, __int64); // r9
  __int64 v12; // r10
  int v13; // r8d
  __int64 v14; // r14
  void (__fastcall *v15)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD); // rsi
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  _BYTE v20[16]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[24]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v23; // [rsp+90h] [rbp-70h]
  _BYTE v24[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v25[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v26[64]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v27[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v28[32]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v27,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting");
  std::string::string(
    v28,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v3(v2, v28, v27, 301);
  std::string::~string(v28);
  std::string::~string(v27);
  std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>(v22);
  std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(v28);
  std::wstring::wstring(v27, L"UserPreferenceForAllApps");
  RegistryConfigurationPath = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(
                                v21,
                                v27);
  Instance = Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::CreateInstance(
               v5,
               RegistryConfigurationPath,
               v28);
  std::wstring::~wstring(v27);
  if ( Instance >= 0 )
  {
    std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::push_back(
      v22,
      v28);
    std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(v21);
    v7 = std::wstring::wstring(v27, L"UserPreferenceForAllApps");
    v8 = Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::CreateInstance(v7, v21);
    Instance = v8;
    if ( v8 >= 0 )
    {
      std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::push_back(
        v22,
        v21);
      v8 = Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::CreateInstance(
             v22,
             (char *)this + 72);
      Instance = v8;
      if ( v8 >= 0 )
      {
        std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
          v20,
          (char *)this + 8);
        std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
          v27,
          v20);
        std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v20);
        std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(v20);
        std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
          v20,
          v27);
        v10 = std::function_void___cdecl_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____enum_Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName__::function_void___cdecl_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____enum_Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName____lambda_abff7d7366045b68624f81f62b98428a__0_(
                v26,
                v20);
        Instance = v11(v12, v10);
        std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v20);
        if ( Instance >= 0 )
        {
          v14 = *((_QWORD *)this + 47);
          v15 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *, _QWORD))(*(_QWORD *)v14 + 72LL);
          v16 = std::string::string(v24, "hr = 0x%x", v13);
          v23 = v25;
          v17 = std::string::string(
                  v25,
                  "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::InitializeAllAgentsActivationSetting");
          v18 = std::string::string(
                  v26,
                  "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
          v15(v14, v18, v17, 325, v16, this, 0);
          std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v27);
          std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v21);
          Instance = 0;
          goto LABEL_12;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x143,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
          (const char *)(unsigned int)Instance,
          (int)this);
        std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(v27);
        goto LABEL_6;
      }
      v9 = 313;
    }
    else
    {
      v9 = 310;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
      (const char *)(unsigned int)v8,
      (int)this);
LABEL_6:
    std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v21);
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x132,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
    (const char *)(unsigned int)Instance,
    (int)this);
LABEL_12:
  std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v28);
  std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::_Tidy(v22);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140022880  mov     [rsp-8+arg_8], rbx
0x140022885  mov     [rsp-8+arg_10], rsi
0x14002288a  push    rbp
0x14002288b  push    rdi
0x14002288c  push    r12
0x14002288e  push    r14
0x140022890  push    r15
0x140022892  lea     rbp, [rsp-60h]
0x140022897  sub     rsp, 160h
0x14002289e  mov     rax, cs:__security_cookie
0x1400228a5  xor     rax, rsp
0x1400228a8  mov     [rbp+80h+var_28], rax
0x1400228ac  mov     r15, rcx
0x1400228af  mov     rdi, [rcx+178h]
0x1400228b6  mov     rax, [rdi]
0x1400228b9  mov     rbx, [rax+28h]
0x1400228bd  lea     rdx, aMicrosoftVoice_28; "Microsoft::VoiceAgentServices::Windows:"...
0x1400228c4  lea     rcx, [rbp+80h+var_68]
0x1400228c8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400228cd  nop
0x1400228ce  lea     r12, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400228d5  mov     rdx, r12
0x1400228d8  lea     rcx, [rbp+80h+var_48]
0x1400228dc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400228e1  nop
0x1400228e2  mov     qword ptr [rsp+180h+var_160], r15; int
0x1400228e7  mov     r9d, 12Dh
0x1400228ed  lea     r8, [rbp+80h+var_68]
0x1400228f1  lea     rdx, [rbp+80h+var_48]
0x1400228f5  mov     rcx, rdi
0x1400228f8  mov     rax, rbx
0x1400228fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022900  nop
0x140022901  lea     rcx, [rbp+80h+var_48]
0x140022905  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002290a  nop
0x14002290b  lea     rcx, [rbp+80h+var_68]
0x14002290f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140022914  lea     rcx, [rsp+180h+var_108]
0x140022919  call    ??0?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>(void)
0x14002291e  nop
0x14002291f  lea     rcx, [rbp+80h+var_48]
0x140022923  call    ??0?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(void)
0x140022928  nop
0x140022929  lea     rdx, aUserpreference; "UserPreferenceForAllApps"
0x140022930  lea     rcx, [rbp+80h+var_68]
0x140022934  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140022939  nop
0x14002293a  lea     rdx, [rbp+80h+var_68]
0x14002293e  lea     rcx, [rsp+180h+var_128]
0x140022943  call    ?GetRegistryConfigurationPath@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV67@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(std::wstring const &)
0x140022948  lea     r8, [rbp+80h+var_48]
0x14002294c  mov     rdx, rax
0x14002294f  call    ?CreateInstance@RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@SAJPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@8@@Z; Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::CreateInstance(HKEY__ *,std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)
0x140022954  mov     ebx, eax
0x140022956  lea     rcx, [rbp+80h+var_68]
0x14002295a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002295f  test    ebx, ebx
0x140022961  jns     short loc_14002297F
0x140022963  mov     rcx, [rbp+88h]; this
0x14002296a  mov     r9d, ebx; char *
0x14002296d  mov     r8, r12; unsigned int
0x140022970  mov     edx, 132h; void *
0x140022975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002297a  jmp     loc_140022B3C
0x14002297f  lea     rdx, [rbp+80h+var_48]
0x140022983  lea     rcx, [rsp+180h+var_108]
0x140022988  call    ?push_back@?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@Z; std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::push_back(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> const &)
0x14002298d  lea     rcx, [rsp+180h+var_128]
0x140022992  call    ??0?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(void)
0x140022997  nop
0x140022998  lea     rdx, aUserpreference; "UserPreferenceForAllApps"
0x14002299f  lea     rcx, [rbp+80h+var_68]
0x1400229a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400229a8  lea     rdx, [rsp+180h+var_128]
0x1400229ad  mov     rcx, rax
0x1400229b0  call    ?CreateInstance@MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@7@@Z; Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::CreateInstance(std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)
0x1400229b5  mov     ebx, eax
0x1400229b7  test    eax, eax
0x1400229b9  jns     short loc_1400229E2
0x1400229bb  mov     edx, 136h; void *
0x1400229c0  mov     r8, r12; unsigned int
0x1400229c3  mov     r9d, eax; char *
0x1400229c6  mov     rcx, [rbp+88h]; this
0x1400229cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400229d2  nop
0x1400229d3  lea     rcx, [rsp+180h+var_128]
0x1400229d8  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x1400229dd  jmp     loc_140022B3C
0x1400229e2  lea     rdx, [rsp+180h+var_128]
0x1400229e7  lea     rcx, [rsp+180h+var_108]
0x1400229ec  call    ?push_back@?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@Z; std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::push_back(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> const &)
0x1400229f1  lea     rdx, [r15+48h]
0x1400229f5  lea     rcx, [rsp+180h+var_108]
0x1400229fa  call    ?CreateInstance@AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEAV?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@AEAV?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@7@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::CreateInstance(std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>> &,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView> &)
0x1400229ff  mov     ebx, eax
0x140022a01  test    eax, eax
0x140022a03  jns     short loc_140022A0C
0x140022a05  mov     edx, 139h
0x140022a0a  jmp     short loc_1400229C0
0x140022a0c  lea     rdx, [r15+8]
0x140022a10  lea     rcx, [rsp+180h+var_138]
0x140022a15  call    ??$?0VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@AEBV?$weak_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140022a1a  lea     rdx, [rsp+180h+var_138]
0x140022a1f  lea     rcx, [rbp+80h+var_68]
0x140022a23  call    ??$?0VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$weak_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140022a28  nop
0x140022a29  lea     rcx, [rsp+180h+var_138]
0x140022a2e  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140022a33  mov     r10, [r15+48h]
0x140022a37  mov     rax, [r10]
0x140022a3a  mov     r9, [rax+38h]
0x140022a3e  lea     rcx, [rsp+180h+var_138]
0x140022a43  call    ??0?$_Ptr_base@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAA@XZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(void)
0x140022a48  lea     rdx, [rbp+80h+var_68]
0x140022a4c  lea     rcx, [rsp+180h+var_138]
0x140022a51  call    ??$_Weakly_construct_from@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@?$_Ptr_base@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXAEBV01@@Z; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::_Weakly_construct_from<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &)
0x140022a56  nop
0x140022a57  lea     rdx, [rsp+180h+var_138]
0x140022a5c  lea     rcx, [rbp+80h+var_A8]
0x140022a60  call    std__function_void___cdecl_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____enum_Microsoft__VoiceAgentServices__Windows__Settings__AgentActivationSettingName____function_void___cdecl_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____enum_Microsoft__VoiceAgentServices__Windows__Settings__AgentActivationSettingName____lambda_abff7d7366045b68624f81f62b98428a__0_
0x140022a65  mov     rdx, rax
0x140022a68  mov     rcx, r10
0x140022a6b  mov     rax, r9
0x140022a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022a73  mov     ebx, eax
0x140022a75  lea     rcx, [rsp+180h+var_138]
0x140022a7a  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140022a7f  test    ebx, ebx
0x140022a81  jns     short loc_140022AA9
0x140022a83  mov     rcx, [rbp+88h]; this
0x140022a8a  mov     r9d, ebx; char *
0x140022a8d  mov     r8, r12; unsigned int
0x140022a90  mov     edx, 143h; void *
0x140022a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022a9a  nop
0x140022a9b  lea     rcx, [rbp+80h+var_68]
0x140022a9f  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140022aa4  jmp     loc_1400229D3
0x140022aa9  mov     r14, [r15+178h]
0x140022ab0  mov     rax, [r14]
0x140022ab3  mov     rsi, [rax+48h]
0x140022ab7  lea     rax, [rbp+80h+var_E8]
0x140022abb  mov     [rsp+180h+var_140], rax
0x140022ac0  lea     rdx, aHr0xX; "hr = 0x%x"
0x140022ac7  lea     rcx, [rbp+80h+var_E8]
0x140022acb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022ad0  mov     rdi, rax
0x140022ad3  lea     rax, [rbp+80h+var_C8]
0x140022ad7  mov     [rbp+80h+var_F0], rax
0x140022adb  lea     rdx, aMicrosoftVoice_28; "Microsoft::VoiceAgentServices::Windows:"...
0x140022ae2  lea     rcx, [rbp+80h+var_C8]
0x140022ae6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022aeb  mov     rbx, rax
0x140022aee  mov     rdx, r12
0x140022af1  lea     rcx, [rbp+80h+var_A8]
0x140022af5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022afa  nop
0x140022afb  mov     [rsp+180h+var_150], 0
0x140022b04  mov     [rsp+180h+var_158], r15
0x140022b09  mov     qword ptr [rsp+180h+var_160], rdi
0x140022b0e  mov     r9d, 145h
0x140022b14  mov     r8, rbx
0x140022b17  mov     rdx, rax
0x140022b1a  mov     rcx, r14
0x140022b1d  mov     rax, rsi
0x140022b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022b25  nop
0x140022b26  lea     rcx, [rbp+80h+var_68]
0x140022b2a  call    ?_Decwref@?$_Ptr_base@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::_Decwref(void)
0x140022b2f  nop
0x140022b30  lea     rcx, [rsp+180h+var_128]
0x140022b35  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140022b3a  xor     ebx, ebx
0x140022b3c  lea     rcx, [rbp+80h+var_48]
0x140022b40  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140022b45  nop
0x140022b46  lea     rcx, [rsp+180h+var_108]
0x140022b4b  call    ?_Tidy@?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::_Tidy(void)
0x140022b50  mov     eax, ebx
0x140022b52  mov     rcx, [rbp+80h+var_28]
0x140022b56  xor     rcx, rsp; StackCookie
0x140022b59  call    __security_check_cookie
0x140022b5e  lea     r11, [rsp+180h+var_20]
0x140022b66  mov     rbx, [r11+38h]
0x140022b6a  mov     rsi, [r11+40h]
0x140022b6e  mov     rsp, r11
0x140022b71  pop     r15
0x140022b73  pop     r14
0x140022b75  pop     r12
0x140022b77  pop     rdi
0x140022b78  pop     rbp
0x140022b79  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::RefreshAgentSettings(void)

- ea: `0x140022d74`
- end: `0x140022ed4`
- name: `?RefreshAgentSettings@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAXXZ`
- size: `352`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140020e7c`

## callees

- `0x140002d30`
- `0x140020ff0`
- `0x140021658`
- `0x140021cac`
- `0x140021ccc`
- `0x140022d74`
- `0x140023c30`
- `0x14002ab98`
- `0x14002f3c4`
- `0x140031010`

## string_xrefs

- `0x140022dbe`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140022e83`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x140022dad`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::RefreshAgentSettings`
- `0x140022e70`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::RefreshAgentSettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::RefreshAgentSettings(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *); // rbx
  __int64 v4; // rbx
  __int64 v5; // rax
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *v6; // rax
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *); // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  _QWORD v11[2]; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp+17h] BYREF

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v13,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::RefreshAgentSettings");
  std::string::string(
    v12,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v3(v2, v12, v13, 362, this);
  std::string::~string(v12);
  std::string::~string(v13);
  std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>,0>>::_Unchecked_begin(
    (char *)this + 88,
    v11);
  v4 = *((_QWORD *)this + 12);
  while ( v11[0] != v4 )
  {
    v5 = std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>>>::operator*(v11);
    v6 = (Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *)_RTDynamicCast_0(
                                                                                           *(_QWORD *)(v5 + 32),
                                                                                           0,
                                                                                           &Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView `RTTI Type Descriptor',
                                                                                           &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase `RTTI Type Descriptor',
                                                                                           0);
    if ( v6 )
      Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification(v6);
    std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>>>::operator++(v11);
  }
  v7 = *((_QWORD *)this + 47);
  v8 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *))(*(_QWORD *)v7 + 64LL);
  v11[0] = v13;
  v9 = std::string::string(
         v13,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::RefreshAgentSettings");
  v10 = std::string::string(
          v12,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v8(v7, v10, v9, 371, this);
}

```

## disassembly

```asm
0x140022d74  mov     [rsp-8+arg_8], rbx
0x140022d79  mov     [rsp-8+arg_10], rsi
0x140022d7e  push    rbp
0x140022d7f  push    rdi
0x140022d80  push    r14
0x140022d82  lea     rbp, [rsp-47h]
0x140022d87  sub     rsp, 90h
0x140022d8e  mov     rax, cs:__security_cookie
0x140022d95  xor     rax, rsp
0x140022d98  mov     [rbp+57h+var_20], rax
0x140022d9c  mov     r14, rcx
0x140022d9f  mov     rdi, [rcx+178h]
0x140022da6  mov     rax, [rdi]
0x140022da9  mov     rbx, [rax+28h]
0x140022dad  lea     rdx, aMicrosoftVoice_5; "Microsoft::VoiceAgentServices::Windows:"...
0x140022db4  lea     rcx, [rbp+57h+var_40]
0x140022db8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022dbd  nop
0x140022dbe  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140022dc5  lea     rcx, [rbp+57h+var_60]
0x140022dc9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022dce  nop
0x140022dcf  mov     [rsp+0A0h+var_80], r14
0x140022dd4  mov     r9d, 16Ah
0x140022dda  lea     r8, [rbp+57h+var_40]
0x140022dde  lea     rdx, [rbp+57h+var_60]
0x140022de2  mov     rcx, rdi
0x140022de5  mov     rax, rbx
0x140022de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022ded  nop
0x140022dee  lea     rcx, [rbp+57h+var_60]
0x140022df2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140022df7  nop
0x140022df8  lea     rcx, [rbp+57h+var_40]
0x140022dfc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140022e01  lea     rdx, [rbp+57h+var_70]
0x140022e05  lea     rcx, [r14+58h]
0x140022e09  call    ?_Unchecked_begin@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@std@@@std@@@std@@@2@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>,0>>::_Unchecked_begin(void)
0x140022e0e  mov     rbx, [r14+60h]
0x140022e12  cmp     [rbp+57h+var_70], rbx
0x140022e16  jz      short loc_140022E5A
0x140022e18  lea     rcx, [rbp+57h+var_70]
0x140022e1c  call    ??D?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@1@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>>>::operator*(void)
0x140022e21  mov     dword ptr [rsp+0A0h+var_80], 0
0x140022e29  lea     r9, ??_R0?AVAgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@@8; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase `RTTI Type Descriptor'
0x140022e30  lea     r8, ??_R0?AVIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@8; Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView `RTTI Type Descriptor'
0x140022e37  xor     edx, edx
0x140022e39  mov     rcx, [rax+20h]
0x140022e3d  call    __RTDynamicCast_0
0x140022e42  test    rax, rax
0x140022e45  jz      short loc_140022E4F
0x140022e47  mov     rcx, rax; this
0x140022e4a  call    ?HandleChangeNotification@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAXXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification(void)
0x140022e4f  lea     rcx, [rbp+57h+var_70]
0x140022e53  call    ??E?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>>>::operator++(void)
0x140022e58  jmp     short loc_140022E12
0x140022e5a  mov     rsi, [r14+178h]
0x140022e61  mov     rax, [rsi]
0x140022e64  mov     rdi, [rax+40h]
0x140022e68  lea     rax, [rbp+57h+var_40]
0x140022e6c  mov     [rbp+57h+var_70], rax
0x140022e70  lea     rdx, aMicrosoftVoice_5; "Microsoft::VoiceAgentServices::Windows:"...
0x140022e77  lea     rcx, [rbp+57h+var_40]
0x140022e7b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022e80  mov     rbx, rax
0x140022e83  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140022e8a  lea     rcx, [rbp+57h+var_60]
0x140022e8e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022e93  nop
0x140022e94  mov     [rsp+0A0h+var_80], r14
0x140022e99  mov     r9d, 173h
0x140022e9f  mov     r8, rbx
0x140022ea2  mov     rdx, rax
0x140022ea5  mov     rcx, rsi
0x140022ea8  mov     rax, rdi
0x140022eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022eb0  mov     rcx, [rbp+57h+var_20]
0x140022eb4  xor     rcx, rsp; StackCookie
0x140022eb7  call    __security_check_cookie
0x140022ebc  lea     r11, [rsp+0A0h+var_10]
0x140022ec4  mov     rbx, [r11+28h]
0x140022ec8  mov     rsi, [r11+30h]
0x140022ecc  mov     rsp, r11
0x140022ecf  pop     r14
0x140022ed1  pop     rdi
0x140022ed2  pop     rbp
0x140022ed3  retn
```

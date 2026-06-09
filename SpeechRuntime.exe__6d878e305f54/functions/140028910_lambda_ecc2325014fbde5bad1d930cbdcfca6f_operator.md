# _lambda_ecc2325014fbde5bad1d930cbdcfca6f_::operator()

- ea: `0x140028910`
- end: `0x140028a6d`
- name: `_lambda_ecc2325014fbde5bad1d930cbdcfca6f_::operator()`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002ce60`

## callees

- `0x140002d30`
- `0x14001ae60`
- `0x140020ff0`
- `0x140021658`
- `0x140021c8c`
- `0x140025030`
- `0x140028910`
- `0x14002ab98`
- `0x14002f3c4`
- `0x140031010`

## string_xrefs

- `0x140028979`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028a12`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028968`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates::<lambda_ecc2325014fbde5bad1d930cbdcfca6f>::operator ()`
- `0x1400289ff`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates::<lambda_ecc2325014fbde5bad1d930cbdcfca6f>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall lambda_ecc2325014fbde5bad1d930cbdcfca6f_::operator()(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  void (__fastcall *v4)(__int64, _BYTE *, _BYTE *, __int64, __int64); // rdi
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // r14
  void (__fastcall *v8)(__int64, __int64, __int64, __int64, __int64); // rsi
  __int64 v9; // rbx
  __int64 v10; // rax
  _QWORD v12[4]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v14[32]; // [rsp+70h] [rbp+17h] BYREF

  std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::lock(a1, v12);
  if ( (unsigned __int8)std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::operator bool(v12) )
  {
    v2 = *(_QWORD *)(a1 + 16);
    v3 = *(_QWORD *)(v2 + 376);
    v4 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, __int64))(*(_QWORD *)v3 + 40LL);
    std::string::string(
      v14,
      "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates::<lambda_ecc"
      "2325014fbde5bad1d930cbdcfca6f>::operator ()");
    std::string::string(
      v13,
      "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
    v4(v3, v13, v14, 473, v2);
    std::string::~string(v13);
    std::string::~string(v14);
    v5 = (Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *)_RTDynamicCast_0(
                                                                                           v12[0],
                                                                                           0,
                                                                                           &Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView `RTTI Type Descriptor',
                                                                                           &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase `RTTI Type Descriptor',
                                                                                           0);
    Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification(v5);
    v6 = *(_QWORD *)(a1 + 16);
    v7 = *(_QWORD *)(v6 + 376);
    v8 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64))(*(_QWORD *)v7 + 64LL);
    v12[2] = v14;
    v9 = std::string::string(
           v14,
           "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates::<lambd"
           "a_ecc2325014fbde5bad1d930cbdcfca6f>::operator ()");
    v10 = std::string::string(
            v13,
            "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
    v8(v7, v10, v9, 473, v6);
  }
  return std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v12);
}

```

## disassembly

```asm
0x140028910  mov     [rsp-8+arg_8], rbx
0x140028915  mov     [rsp-8+arg_10], rsi
0x14002891a  push    rbp
0x14002891b  push    rdi
0x14002891c  push    r14
0x14002891e  lea     rbp, [rsp-47h]
0x140028923  sub     rsp, 0A0h
0x14002892a  mov     rax, cs:__security_cookie
0x140028931  xor     rax, rsp
0x140028934  mov     [rbp+57h+var_20], rax
0x140028938  mov     r14, rcx
0x14002893b  lea     rdx, [rbp+57h+var_80]
0x14002893f  call    ?lock@?$weak_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBA?AV?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@XZ; std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::lock(void)
0x140028944  nop
0x140028945  lea     rcx, [rbp+57h+var_80]
0x140028949  call    ??B?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::operator bool(void)
0x14002894e  test    al, al
0x140028950  jz      loc_140028A40
0x140028956  mov     rbx, [r14+10h]
0x14002895a  mov     rsi, [rbx+178h]
0x140028961  mov     rax, [rsi]
0x140028964  mov     rdi, [rax+28h]
0x140028968  lea     rdx, aMicrosoftVoice_49; "Microsoft::VoiceAgentServices::Windows:"...
0x14002896f  lea     rcx, [rbp+57h+var_40]
0x140028973  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028978  nop
0x140028979  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028980  lea     rcx, [rbp+57h+var_60]
0x140028984  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028989  nop
0x14002898a  mov     [rsp+0B0h+var_90], rbx
0x14002898f  mov     r9d, 1D9h
0x140028995  lea     r8, [rbp+57h+var_40]
0x140028999  lea     rdx, [rbp+57h+var_60]
0x14002899d  mov     rcx, rsi
0x1400289a0  mov     rax, rdi
0x1400289a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400289a8  nop
0x1400289a9  lea     rcx, [rbp+57h+var_60]
0x1400289ad  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400289b2  nop
0x1400289b3  lea     rcx, [rbp+57h+var_40]
0x1400289b7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400289bc  mov     dword ptr [rsp+0B0h+var_90], 0
0x1400289c4  lea     r9, ??_R0?AVAgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@@8; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase `RTTI Type Descriptor'
0x1400289cb  lea     r8, ??_R0?AVIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@8; Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView `RTTI Type Descriptor'
0x1400289d2  xor     edx, edx
0x1400289d4  mov     rcx, [rbp+57h+var_80]
0x1400289d8  call    __RTDynamicCast_0
0x1400289dd  mov     rcx, rax; this
0x1400289e0  call    ?HandleChangeNotification@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAXXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::HandleChangeNotification(void)
0x1400289e5  mov     rdi, [r14+10h]
0x1400289e9  mov     r14, [rdi+178h]
0x1400289f0  mov     rax, [r14]
0x1400289f3  mov     rsi, [rax+40h]
0x1400289f7  lea     rax, [rbp+57h+var_40]
0x1400289fb  mov     [rbp+57h+var_70], rax
0x1400289ff  lea     rdx, aMicrosoftVoice_49; "Microsoft::VoiceAgentServices::Windows:"...
0x140028a06  lea     rcx, [rbp+57h+var_40]
0x140028a0a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028a0f  mov     rbx, rax
0x140028a12  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028a19  lea     rcx, [rbp+57h+var_60]
0x140028a1d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028a22  nop
0x140028a23  mov     [rsp+0B0h+var_90], rdi
0x140028a28  mov     r9d, 1D9h
0x140028a2e  mov     r8, rbx
0x140028a31  mov     rdx, rax
0x140028a34  mov     rcx, r14
0x140028a37  mov     rax, rsi
0x140028a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028a3f  nop
0x140028a40  lea     rcx, [rbp+57h+var_80]
0x140028a44  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140028a49  mov     rcx, [rbp+57h+var_20]
0x140028a4d  xor     rcx, rsp; StackCookie
0x140028a50  call    __security_check_cookie
0x140028a55  lea     r11, [rsp+0B0h+var_10]
0x140028a5d  mov     rbx, [r11+28h]
0x140028a61  mov     rsi, [r11+30h]
0x140028a65  mov     rsp, r11
0x140028a68  pop     r14
0x140028a6a  pop     rdi
0x140028a6b  pop     rbp
0x140028a6c  retn
```

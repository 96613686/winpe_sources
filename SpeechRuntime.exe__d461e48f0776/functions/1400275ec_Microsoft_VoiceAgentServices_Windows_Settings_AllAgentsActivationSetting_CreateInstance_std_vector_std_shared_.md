# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::CreateInstance(std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>,std::allocator<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>> &,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView> &)

- ea: `0x1400275ec`
- end: `0x1400276d2`
- name: `?CreateInstance@AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEAV?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@AEAV?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@7@@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140022880`

## callees

- `0x140002d60`
- `0x14000e030`
- `0x14001ae60`
- `0x1400242e0`
- `0x140024480`
- `0x140027300`
- `0x14002733c`
- `0x1400273bc`
- `0x1400275ec`
- `0x14002b004`

## string_xrefs

- `0x14002763d`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027694`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::CreateInstance(
        __int64 a1,
        __int64 a2)
{
  Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *v4; // rax
  Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *v5; // rbx
  unsigned int v6; // ebx
  int v7; // eax
  int v9[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = (Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *)operator new(
                                                                                         0x190u,
                                                                                         (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v5 = Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>(
      v9,
      v5);
    std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::operator=<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor,0>(
      (char *)v5 + 384,
      v9);
    std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::swap(
      a1,
      (char *)v5 + 184);
    v7 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize(v5);
    v6 = v7;
    if ( v7 >= 0 )
    {
      std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(a2, v9);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp",
        (const char *)(unsigned int)v7,
        v9[0]);
    }
    std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v9);
  }
  else
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp",
      (const char *)0x8007000ELL,
      v9[0]);
  }
  return v6;
}

```

## disassembly

```asm
0x1400275ec  mov     [rsp+arg_0], rbx
0x1400275f1  mov     [rsp+arg_8], rsi
0x1400275f6  push    rdi
0x1400275f7  sub     rsp, 30h
0x1400275fb  mov     rdi, rdx
0x1400275fe  mov     rsi, rcx
0x140027601  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140027608  mov     ecx, 190h; unsigned __int64
0x14002760d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140027612  mov     [rsp+38h+arg_10], rax
0x140027617  test    rax, rax
0x14002761a  jz      short loc_140027629
0x14002761c  mov     rcx, rax; this
0x14002761f  call    ??0AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::AllAgentsActivationSetting(void)
0x140027624  mov     rbx, rax
0x140027627  jmp     short loc_14002762B
0x140027629  xor     ebx, ebx
0x14002762b  test    rbx, rbx
0x14002762e  jnz     short loc_140027650
0x140027630  mov     rcx, [rsp+38h]; this
0x140027635  mov     ebx, 8007000Eh
0x14002763a  mov     r9d, ebx; char *
0x14002763d  lea     r8, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027644  mov     edx, 1Ah; void *
0x140027649  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002764e  jmp     short loc_1400276C0
0x140027650  mov     rdx, rbx
0x140027653  lea     rcx, [rsp+38h+var_18]
0x140027658  call    ??$?0VAllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@PEAVAllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>(Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *)
0x14002765d  nop
0x14002765e  lea     rcx, [rbx+180h]
0x140027665  lea     rdx, [rsp+38h+var_18]
0x14002766a  call    ??$?4VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$weak_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::operator=<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor,0>(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> const &)
0x14002766f  lea     rdx, [rbx+0B8h]
0x140027676  mov     rcx, rsi
0x140027679  call    ?swap@?$vector@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@2@@std@@QEAAXAEAV12@@Z; std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>::swap(std::vector<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>> &)
0x14002767e  mov     rcx, rbx; this
0x140027681  call    ?Initialize@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@IEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::Initialize(void)
0x140027686  mov     ebx, eax
0x140027688  test    eax, eax
0x14002768a  jns     short loc_1400276A7
0x14002768c  mov     rcx, [rsp+38h]; this
0x140027691  mov     r9d, eax; char *
0x140027694  lea     r8, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002769b  mov     edx, 20h ; ' '; void *
0x1400276a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400276a5  jmp     short loc_1400276B6
0x1400276a7  lea     rdx, [rsp+38h+var_18]
0x1400276ac  mov     rcx, rdi
0x1400276af  call    ?swap@?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)
0x1400276b4  xor     ebx, ebx
0x1400276b6  lea     rcx, [rsp+38h+var_18]
0x1400276bb  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x1400276c0  mov     eax, ebx
0x1400276c2  mov     rbx, [rsp+38h+arg_0]
0x1400276c7  mov     rsi, [rsp+38h+arg_8]
0x1400276cc  add     rsp, 30h
0x1400276d0  pop     rdi
0x1400276d1  retn
```

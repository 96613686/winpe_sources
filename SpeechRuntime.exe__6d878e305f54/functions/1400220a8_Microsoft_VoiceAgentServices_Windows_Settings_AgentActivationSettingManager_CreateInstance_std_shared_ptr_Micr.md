# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::CreateInstance(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> &,bool)

- ea: `0x1400220a8`
- end: `0x14002218a`
- name: `?CreateInstance@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEAV?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@_N@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001a500`

## callees

- `0x140002d60`
- `0x140004e40`
- `0x14000e030`
- `0x14001ae60`
- `0x1400200b0`
- `0x14002118c`
- `0x1400220a8`
- `0x1400226c4`
- `0x1400242e0`

## string_xrefs

- `0x140022106`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x14002213e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::CreateInstance(
        __int64 a1)
{
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *v2; // rax
  const char *v3; // r9
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebx
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *v7[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *)operator new(
                                                                                            0x180u,
                                                                                            (const struct std::nothrow_t *)&std::nothrow);
  try
  {
    if ( v2 )
      v2 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager(v2);
    std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(
      v7,
      v2);
    if ( (unsigned __int8)std::operator==<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(v7) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
        (const char *)0x8007000ELL,
        (int)v7[0]);
      std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v7);
      result = 2147942414LL;
    }
    else
    {
      v5 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize(v7[0]);
      v6 = v5;
      if ( v5 >= 0 )
      {
        std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(v7, a1);
        std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v7);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp",
          (const char *)(unsigned int)v5,
          (int)v7[0]);
        std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v7);
        result = v6;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x51,
                           (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactiv"
                                         "ationsettingmanager.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x1400220a8  mov     [rsp+arg_0], rbx
0x1400220ad  mov     byte ptr [rsp+arg_8], dl
0x1400220b1  push    rdi
0x1400220b2  sub     rsp, 30h
0x1400220b6  mov     rdi, rcx
0x1400220b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400220c0  mov     ecx, 180h; unsigned __int64
0x1400220c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400220ca  mov     [rsp+38h+arg_10], rax
0x1400220cf  test    rax, rax
0x1400220d2  jz      short loc_1400220DD
0x1400220d4  mov     rcx, rax; this
0x1400220d7  call    ??0AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager(void)
0x1400220dc  nop
0x1400220dd  mov     rdx, rax
0x1400220e0  lea     rcx, [rsp+38h+var_18]
0x1400220e5  call    ??$?0VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@PEAVAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *)
0x1400220ea  nop
0x1400220eb  lea     rcx, [rsp+38h+var_18]
0x1400220f0  call    ??$?8VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@YA_NAEBV?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager> const &,std::nullptr_t)
0x1400220f5  test    al, al
0x1400220f7  jz      short loc_140022126
0x1400220f9  mov     rcx, [rsp+38h]; this
0x1400220fe  mov     ebx, 8007000Eh
0x140022103  mov     r9d, ebx; char *
0x140022106  lea     r8, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002210d  mov     edx, 4Dh ; 'M'; void *
0x140022112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022117  nop
0x140022118  lea     rcx, [rsp+38h+var_18]
0x14002211d  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140022122  mov     eax, ebx
0x140022124  jmp     short loc_14002217E
0x140022126  mov     rcx, [rsp+38h+var_18]; this
0x14002212b  call    ?Initialize@AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAJ_N@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::Initialize(bool)
0x140022130  mov     ebx, eax
0x140022132  test    eax, eax
0x140022134  jns     short loc_14002215E
0x140022136  mov     rcx, [rsp+38h]; this
0x14002213b  mov     r9d, eax; char *
0x14002213e  lea     r8, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140022145  mov     edx, 4Eh ; 'N'; void *
0x14002214a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002214f  nop
0x140022150  lea     rcx, [rsp+38h+var_18]
0x140022155  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x14002215a  mov     eax, ebx
0x14002215c  jmp     short loc_14002217E
0x14002215e  mov     rdx, rdi
0x140022161  lea     rcx, [rsp+38h+var_18]
0x140022166  call    ?swap@?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)
0x14002216b  nop
0x14002216c  lea     rcx, [rsp+38h+var_18]
0x140022171  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140022176  xor     eax, eax
0x140022178  jmp     short loc_14002217E
0x14002217a  mov     eax, [rsp+38h+arg_8]
0x14002217e  mov     rbx, [rsp+38h+arg_0]
0x140022183  add     rsp, 30h
0x140022187  pop     rdi
0x140022188  retn
```

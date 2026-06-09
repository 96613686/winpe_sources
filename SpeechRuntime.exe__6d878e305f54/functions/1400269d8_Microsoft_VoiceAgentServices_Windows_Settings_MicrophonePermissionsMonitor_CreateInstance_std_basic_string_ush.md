# Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::CreateInstance(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)

- ea: `0x1400269d8`
- end: `0x140026ac5`
- name: `?CreateInstance@MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@7@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140022880`

## callees

- `0x140002d60`
- `0x14000e030`
- `0x14001296c`
- `0x14001ae60`
- `0x1400242e0`
- `0x140024480`
- `0x140026244`
- `0x140026528`
- `0x1400269d8`
- `0x140026acc`

## string_xrefs

- `0x140026a2e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`
- `0x140026a73`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\microphonepermissionsmonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::CreateInstance(
        __int64 a1,
        __int64 a2)
{
  Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *v4; // rax
  Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *v5; // rbx
  unsigned int v6; // ebx
  int v7; // eax
  int v9[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = (Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *)operator new(
                                                                                           0x70u,
                                                                                           (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v5 = Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(
      v9,
      v5);
    std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::operator=<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor,0>(
      (char *)v5 + 88,
      v9);
    v7 = Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize(v5);
    v6 = v7;
    if ( v7 >= 0 )
    {
      std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(a2, v9);
      std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v9);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp",
        (const char *)(unsigned int)v7,
        v9[0]);
      std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v9);
    }
  }
  else
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\microphonepermissionsmonitor.cpp",
      (const char *)0x8007000ELL,
      v9[0]);
  }
  std::wstring::~wstring(a1);
  return v6;
}

```

## disassembly

```asm
0x1400269d8  mov     [rsp+arg_8], rbx
0x1400269dd  mov     [rsp+arg_18], rsi
0x1400269e2  mov     [rsp+arg_0], rcx
0x1400269e7  push    rdi
0x1400269e8  sub     rsp, 30h
0x1400269ec  mov     rsi, rdx
0x1400269ef  mov     rdi, rcx
0x1400269f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400269f9  mov     ecx, 70h ; 'p'; unsigned __int64
0x1400269fe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140026a03  mov     [rsp+38h+arg_10], rax
0x140026a08  test    rax, rax
0x140026a0b  jz      short loc_140026A1A
0x140026a0d  mov     rcx, rax; this
0x140026a10  call    ??0MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::MicrophonePermissionsMonitor(void)
0x140026a15  mov     rbx, rax
0x140026a18  jmp     short loc_140026A1C
0x140026a1a  xor     ebx, ebx
0x140026a1c  test    rbx, rbx
0x140026a1f  jnz     short loc_140026A41
0x140026a21  mov     rcx, [rsp+38h]; this
0x140026a26  mov     ebx, 8007000Eh
0x140026a2b  mov     r9d, ebx; char *
0x140026a2e  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026a35  mov     edx, 16h; void *
0x140026a3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026a3f  jmp     short loc_140026AAB
0x140026a41  mov     rdx, rbx
0x140026a44  lea     rcx, [rsp+38h+var_18]
0x140026a49  call    ??$?0VMicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@PEAVMicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor *)
0x140026a4e  nop
0x140026a4f  lea     rcx, [rbx+58h]
0x140026a53  lea     rdx, [rsp+38h+var_18]
0x140026a58  call    ??$?4VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$weak_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::operator=<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor,0>(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> const &)
0x140026a5d  mov     rcx, rbx; this
0x140026a60  call    ?Initialize@MicrophonePermissionsMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::MicrophonePermissionsMonitor::Initialize(void)
0x140026a65  mov     ebx, eax
0x140026a67  test    eax, eax
0x140026a69  jns     short loc_140026A91
0x140026a6b  mov     rcx, [rsp+38h]; this
0x140026a70  mov     r9d, eax; char *
0x140026a73  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026a7a  mov     edx, 1Bh; void *
0x140026a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026a84  nop
0x140026a85  lea     rcx, [rsp+38h+var_18]
0x140026a8a  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140026a8f  jmp     short loc_140026AAB
0x140026a91  lea     rdx, [rsp+38h+var_18]
0x140026a96  mov     rcx, rsi
0x140026a99  call    ?swap@?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)
0x140026a9e  nop
0x140026a9f  lea     rcx, [rsp+38h+var_18]
0x140026aa4  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140026aa9  xor     ebx, ebx
0x140026aab  mov     rcx, rdi
0x140026aae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140026ab3  mov     eax, ebx
0x140026ab5  mov     rbx, [rsp+38h+arg_8]
0x140026aba  mov     rsi, [rsp+38h+arg_18]
0x140026abf  add     rsp, 30h
0x140026ac3  pop     rdi
0x140026ac4  retn
```

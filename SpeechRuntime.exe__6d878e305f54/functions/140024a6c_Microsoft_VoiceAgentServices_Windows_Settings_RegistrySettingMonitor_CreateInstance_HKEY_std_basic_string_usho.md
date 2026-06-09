# Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::CreateInstance(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)

- ea: `0x140024a6c`
- end: `0x140024b89`
- name: `?CreateInstance@RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@SAJPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@8@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140022880`

## callees

- `0x140002d30`
- `0x140002d60`
- `0x14000e030`
- `0x14001296c`
- `0x14001ae60`
- `0x140021bd0`
- `0x1400242e0`
- `0x140024400`
- `0x140024480`
- `0x1400245f8`
- `0x140024a6c`
- `0x140024b90`

## string_xrefs

- `0x140024ad1`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`
- `0x140024b2a`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\registrysettingmonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *v5; // rax
  Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *v6; // rbx
  unsigned int v7; // ebx
  int v8; // eax
  int v10[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v11 = a2;
  v5 = (Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *)operator new(
                                                                                     0x90u,
                                                                                     (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)v10 = v5;
  if ( v5 )
    v6 = Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor(v5);
  else
    v6 = 0;
  if ( v6 )
  {
    std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(
      v10,
      v6);
    *((_QWORD *)v6 + 1) = -2147483647;
    std::wstring::operator=((char *)v6 + 16, a2);
    std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::operator=<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor,0>(
      (char *)v6 + 120,
      v10);
    v8 = Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize(v6);
    v7 = v8;
    if ( v8 >= 0 )
    {
      std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(a3, v10);
      std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v10);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp",
        (const char *)(unsigned int)v8,
        v10[0]);
      std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(v10);
    }
  }
  else
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\registrysettingmonitor.cpp",
      (const char *)0x8007000ELL,
      v10[0]);
  }
  std::wstring::~wstring(a2);
  return v7;
}

```

## disassembly

```asm
0x140024a6c  mov     [rsp+arg_0], rbx
0x140024a71  mov     [rsp+arg_18], rsi
0x140024a76  push    rdi
0x140024a77  sub     rsp, 40h
0x140024a7b  mov     rax, cs:__security_cookie
0x140024a82  xor     rax, rsp
0x140024a85  mov     [rsp+48h+var_10], rax
0x140024a8a  mov     rsi, r8
0x140024a8d  mov     rdi, rdx
0x140024a90  mov     [rsp+48h+var_18], rdx
0x140024a95  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140024a9c  mov     ecx, 90h; unsigned __int64
0x140024aa1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140024aa6  mov     qword ptr [rsp+48h+var_28], rax; int
0x140024aab  test    rax, rax
0x140024aae  jz      short loc_140024ABD
0x140024ab0  mov     rcx, rax; this
0x140024ab3  call    ??0RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::RegistrySettingMonitor(void)
0x140024ab8  mov     rbx, rax
0x140024abb  jmp     short loc_140024ABF
0x140024abd  xor     ebx, ebx
0x140024abf  test    rbx, rbx
0x140024ac2  jnz     short loc_140024AE4
0x140024ac4  mov     rcx, [rsp+48h]; this
0x140024ac9  mov     ebx, 8007000Eh
0x140024ace  mov     r9d, ebx; char *
0x140024ad1  lea     r8, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140024ad8  mov     edx, 16h; void *
0x140024add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024ae2  jmp     short loc_140024B62
0x140024ae4  mov     rdx, rbx
0x140024ae7  lea     rcx, [rsp+48h+var_28]
0x140024aec  call    ??$?0VRegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAA@PEAVRegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>(Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor *)
0x140024af1  nop
0x140024af2  mov     qword ptr [rbx+8], 0FFFFFFFF80000001h
0x140024afa  lea     rcx, [rbx+10h]
0x140024afe  mov     rdx, rdi
0x140024b01  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140024b06  lea     rcx, [rbx+78h]
0x140024b0a  lea     rdx, [rsp+48h+var_28]
0x140024b0f  call    ??$?4VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@@?$weak_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::operator=<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor,0>(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> const &)
0x140024b14  mov     rcx, rbx; this
0x140024b17  call    ?Initialize@RegistrySettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ; Microsoft::VoiceAgentServices::Windows::Settings::RegistrySettingMonitor::Initialize(void)
0x140024b1c  mov     ebx, eax
0x140024b1e  test    eax, eax
0x140024b20  jns     short loc_140024B48
0x140024b22  mov     rcx, [rsp+48h]; this
0x140024b27  mov     r9d, eax; char *
0x140024b2a  lea     r8, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140024b31  mov     edx, 1Dh; void *
0x140024b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024b3b  nop
0x140024b3c  lea     rcx, [rsp+48h+var_28]
0x140024b41  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140024b46  jmp     short loc_140024B62
0x140024b48  lea     rdx, [rsp+48h+var_28]
0x140024b4d  mov     rcx, rsi
0x140024b50  call    ?swap@?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>::swap(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> &)
0x140024b55  nop
0x140024b56  lea     rcx, [rsp+48h+var_28]
0x140024b5b  call    ?_Decref@?$_Ptr_base@VInstalledAgentConfigurationList@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@IEAAXXZ; std::_Ptr_base<Microsoft::VoiceAgentServices::Windows::Settings::InstalledAgentConfigurationList>::_Decref(void)
0x140024b60  xor     ebx, ebx
0x140024b62  mov     rcx, rdi
0x140024b65  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024b6a  mov     eax, ebx
0x140024b6c  mov     rcx, [rsp+48h+var_10]
0x140024b71  xor     rcx, rsp; StackCookie
0x140024b74  call    __security_check_cookie
0x140024b79  mov     rbx, [rsp+48h+arg_0]
0x140024b7e  mov     rsi, [rsp+48h+arg_18]
0x140024b83  add     rsp, 40h
0x140024b87  pop     rdi
0x140024b88  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationDefaultAgent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140028f60`
- end: `0x1400290ed`
- name: `?GetVoiceActivationDefaultAgent@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14001296c`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140021b80`
- `0x140022480`
- `0x14002822c`
- `0x140031010`

## string_xrefs

- `0x140028fab`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002908d`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028f9a`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationDefaultAgent`
- `0x14002907a`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationDefaultAgent`
- `0x140029006`: `AgentActivationDefaultApp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationDefaultAgent(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, int *, __int64, __int64); // rbx
  int v6; // eax
  __int64 String; // rax
  __int64 v8; // r14
  void (__fastcall *v9)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD); // rsi
  int v10; // r8d
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  _QWORD v15[3]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-31h] BYREF
  int v17[8]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v18[32]; // [rsp+98h] [rbp+Fh] BYREF

  v4 = *(_QWORD *)(a1 + 376);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, int *, __int64, __int64))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v17,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationDefaultAgent");
  std::string::string(
    v18,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v18, v17, 506, a1);
  std::string::~string(v18);
  std::string::~string(v17);
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 272);
  String = SpRegUtil::GetString(
             (int)v17,
             -2147483647,
             v6,
             (int)L"AgentActivationDefaultApp",
             L"Microsoft.549981C3F5F10_8wekyb3d8bbwe!App");
  std::wstring::operator=(a2, String);
  std::wstring::~wstring(v17);
  v15[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationDefaultAgentStatus<unsigned short const *>(v15);
  v8 = *(_QWORD *)(a1 + 376);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v8 + 72LL);
  v15[0] = v17;
  v11 = std::string::string(v17, "hr = 0x%x", v10);
  v15[1] = v18;
  v12 = std::string::string(
          v18,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationDefaultAgent");
  v13 = std::string::string(
          v16,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v9(v8, v13, v12, 509, v11, a1, 0);
  return 0;
}

```

## disassembly

```asm
0x140028f60  mov     [rsp-8+arg_10], rbx
0x140028f65  push    rbp
0x140028f66  push    rsi
0x140028f67  push    rdi
0x140028f68  push    r14
0x140028f6a  push    r15
0x140028f6c  lea     rbp, [rsp-37h]
0x140028f71  sub     rsp, 0C0h
0x140028f78  mov     rax, cs:__security_cookie
0x140028f7f  xor     rax, rsp
0x140028f82  mov     [rbp+57h+var_28], rax
0x140028f86  mov     rsi, rdx
0x140028f89  mov     r15, rcx
0x140028f8c  mov     rdi, [rcx+178h]
0x140028f93  mov     rax, [rdi]
0x140028f96  mov     rbx, [rax+28h]
0x140028f9a  lea     rdx, aMicrosoftVoice_20; "Microsoft::VoiceAgentServices::Windows:"...
0x140028fa1  lea     rcx, [rbp+57h+var_68]
0x140028fa5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028faa  nop
0x140028fab  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028fb2  lea     rcx, [rbp+57h+var_48]
0x140028fb6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028fbb  nop
0x140028fbc  mov     [rsp+0E0h+var_C0], r15
0x140028fc1  mov     r9d, 1FAh
0x140028fc7  lea     r8, [rbp+57h+var_68]
0x140028fcb  lea     rdx, [rbp+57h+var_48]
0x140028fcf  mov     rcx, rdi
0x140028fd2  mov     rax, rbx
0x140028fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028fda  nop
0x140028fdb  lea     rcx, [rbp+57h+var_48]
0x140028fdf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028fe4  nop
0x140028fe5  lea     rcx, [rbp+57h+var_68]
0x140028fe9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028fee  lea     rcx, [r15+110h]
0x140028ff5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028ffa  lea     rcx, aMicrosoft54998; "Microsoft.549981C3F5F10_8wekyb3d8bbwe!A"...
0x140029001  mov     [rsp+0E0h+var_C0], rcx; unsigned __int16 *
0x140029006  lea     r9, aAgentactivatio_2; "AgentActivationDefaultApp"
0x14002900d  mov     r8, rax; int
0x140029010  mov     rdx, 0FFFFFFFF80000001h; int
0x140029017  lea     rcx, [rbp+57h+var_68]; int
0x14002901b  call    ?GetString@SpRegUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG11@Z; SpRegUtil::GetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x140029020  mov     rdx, rax
0x140029023  mov     rcx, rsi
0x140029026  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14002902b  lea     rcx, [rbp+57h+var_68]
0x14002902f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029034  mov     rcx, rsi
0x140029037  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002903c  mov     [rbp+57h+var_A0], rax
0x140029040  lea     rcx, [rbp+57h+var_A0]
0x140029044  call    ??$VoiceActivationDefaultAgentStatus@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationDefaultAgentStatus<ushort const *>(ushort const * &&)
0x140029049  mov     r14, [r15+178h]
0x140029050  mov     rax, [r14]
0x140029053  mov     rsi, [rax+48h]
0x140029057  lea     rax, [rbp+57h+var_68]
0x14002905b  mov     [rbp+57h+var_A0], rax
0x14002905f  lea     rdx, aHr0xX; "hr = 0x%x"
0x140029066  lea     rcx, [rbp+57h+var_68]
0x14002906a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002906f  mov     rdi, rax
0x140029072  lea     rax, [rbp+57h+var_48]
0x140029076  mov     [rbp+57h+var_98], rax
0x14002907a  lea     rdx, aMicrosoftVoice_20; "Microsoft::VoiceAgentServices::Windows:"...
0x140029081  lea     rcx, [rbp+57h+var_48]
0x140029085  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002908a  mov     rbx, rax
0x14002908d  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029094  lea     rcx, [rbp+57h+var_88]
0x140029098  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002909d  nop
0x14002909e  mov     [rsp+0E0h+var_B0], 0
0x1400290a7  mov     [rsp+0E0h+var_B8], r15
0x1400290ac  mov     [rsp+0E0h+var_C0], rdi
0x1400290b1  mov     r9d, 1FDh
0x1400290b7  mov     r8, rbx
0x1400290ba  mov     rdx, rax
0x1400290bd  mov     rcx, r14
0x1400290c0  mov     rax, rsi
0x1400290c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400290c8  xor     eax, eax
0x1400290ca  mov     rcx, [rbp+57h+var_28]
0x1400290ce  xor     rcx, rsp; StackCookie
0x1400290d1  call    __security_check_cookie
0x1400290d6  mov     rbx, [rsp+0E0h+arg_10]
0x1400290de  add     rsp, 0C0h
0x1400290e5  pop     r15
0x1400290e7  pop     r14
0x1400290e9  pop     rdi
0x1400290ea  pop     rsi
0x1400290eb  pop     rbp
0x1400290ec  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration(Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration &)

- ea: `0x140028bb0`
- end: `0x140028e02`
- name: `?GetAgentConfiguration@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEAUAgentConfiguration@2345@@Z`
- size: `594`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, struct Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14001296c`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140021b80`
- `0x140022480`
- `0x14002713c`
- `0x140028bb0`
- `0x140031010`

## string_xrefs

- `0x140028c03`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028d11`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028d9e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028ce3`: `Get agent configuration for app Id: %ls, keywordId: %ls, displayName: %ls`
- `0x140028bf2`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration`
- `0x140028cfe`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration`
- `0x140028d8b`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        struct Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, int *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  int v6; // eax
  unsigned __int16 *v7; // rdx
  __int64 String; // rax
  __int64 v9; // r13
  void (__fastcall *v10)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, __int64, __int64, __int64); // r12
  __int64 v11; // r15
  __int64 v12; // r14
  __int64 v13; // rsi
  const wchar_t *v14; // r8
  const wchar_t *v15; // r9
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // r14
  void (__fastcall *v20)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v21; // r8d
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rax
  unsigned __int16 *v26; // [rsp+20h] [rbp-A9h]
  _BYTE v28[32]; // [rsp+80h] [rbp-49h] BYREF
  int v29[8]; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-9h] BYREF

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, int *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v29,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration");
  std::string::string(
    v30,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v30, v29, 39, this);
  std::string::~string(v30);
  std::string::~string(v29);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration::operator=(a2, (char *)this + 32);
  if ( !*((_QWORD *)a2 + 14) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 32);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 272);
    String = SpRegUtil::GetString((int)v29, -2147483647, v6, (int)L"DisplayName", v7);
    std::wstring::operator=((char *)a2 + 96, String);
    std::wstring::~wstring(v29);
  }
  v9 = *((_QWORD *)this + 47);
  v10 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, __int64, __int64, __int64))(*(_QWORD *)v9 + 16LL);
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 128);
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 96);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
  v16 = std::string::string(
          v29,
          "Get agent configuration for app Id: %ls, keywordId: %ls, displayName: %ls",
          v14,
          v15,
          v26);
  v17 = std::string::string(
          v30,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration");
  v18 = std::string::string(
          v28,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v10(v9, 0, v18, v17, 45, v16, this, v13, v12, v11);
  v19 = *((_QWORD *)this + 47);
  v20 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v19 + 72LL);
  v22 = std::string::string(v28, "hr = 0x%x", v21);
  v23 = std::string::string(
          v29,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetAgentConfiguration");
  v24 = std::string::string(
          v30,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v20(v19, v24, v23, 46, v22, this, 0);
  return 0;
}

```

## disassembly

```asm
0x140028bb0  mov     [rsp-8+arg_10], rbx
0x140028bb5  push    rbp
0x140028bb6  push    rsi
0x140028bb7  push    rdi
0x140028bb8  push    r12
0x140028bba  push    r13
0x140028bbc  push    r14
0x140028bbe  push    r15
0x140028bc0  lea     rbp, [rsp-27h]
0x140028bc5  sub     rsp, 0F0h
0x140028bcc  mov     rax, cs:__security_cookie
0x140028bd3  xor     rax, rsp
0x140028bd6  mov     [rbp+57h+var_40], rax
0x140028bda  mov     r14, rdx
0x140028bdd  mov     rsi, rcx
0x140028be0  mov     [rbp+57h+var_C0], rcx
0x140028be4  mov     rdi, [rcx+178h]
0x140028beb  mov     rax, [rdi]
0x140028bee  mov     rbx, [rax+28h]
0x140028bf2  lea     rdx, aMicrosoftVoice_53; "Microsoft::VoiceAgentServices::Windows:"...
0x140028bf9  lea     rcx, [rbp+57h+var_80]
0x140028bfd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028c02  nop
0x140028c03  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028c0a  lea     rcx, [rbp+57h+var_60]
0x140028c0e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028c13  nop
0x140028c14  mov     [rsp+120h+var_100], rsi
0x140028c19  mov     r9d, 27h ; '''
0x140028c1f  lea     r8, [rbp+57h+var_80]
0x140028c23  lea     rdx, [rbp+57h+var_60]
0x140028c27  mov     rcx, rdi
0x140028c2a  mov     rax, rbx
0x140028c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028c32  nop
0x140028c33  lea     rcx, [rbp+57h+var_60]
0x140028c37  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028c3c  nop
0x140028c3d  lea     rcx, [rbp+57h+var_80]
0x140028c41  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028c46  lea     rdx, [rsi+20h]
0x140028c4a  mov     rcx, r14
0x140028c4d  call    ??4AgentConfiguration@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAAEAU01234@AEBU01234@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration::operator=(Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration const &)
0x140028c52  cmp     qword ptr [r14+70h], 0
0x140028c57  jnz     short loc_140028CA5
0x140028c59  lea     rcx, [r14+20h]
0x140028c5d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028c62  mov     rdx, rax
0x140028c65  lea     rcx, [rsi+110h]
0x140028c6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028c71  mov     [rsp+120h+var_100], rdx; unsigned __int16 *
0x140028c76  lea     r9, aDisplayname; "DisplayName"
0x140028c7d  mov     r8, rax; int
0x140028c80  mov     rdx, 0FFFFFFFF80000001h; int
0x140028c87  lea     rcx, [rbp+57h+var_80]; int
0x140028c8b  call    ?GetString@SpRegUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG11@Z; SpRegUtil::GetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x140028c90  mov     rdx, rax
0x140028c93  lea     rcx, [r14+60h]
0x140028c97  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140028c9c  lea     rcx, [rbp+57h+var_80]
0x140028ca0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028ca5  mov     r13, [rsi+178h]
0x140028cac  mov     rax, [r13+0]
0x140028cb0  mov     r12, [rax+10h]
0x140028cb4  lea     rcx, [rsi+80h]
0x140028cbb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028cc0  mov     r15, rax
0x140028cc3  lea     rcx, [rsi+60h]
0x140028cc7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028ccc  mov     r14, rax
0x140028ccf  lea     rcx, [rsi+20h]
0x140028cd3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028cd8  mov     rsi, rax
0x140028cdb  lea     rax, [rbp+57h+var_80]
0x140028cdf  mov     [rbp+57h+var_B8], rax
0x140028ce3  lea     rdx, aGetAgentConfig; "Get agent configuration for app Id: %ls"...
0x140028cea  lea     rcx, [rbp+57h+var_80]
0x140028cee  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028cf3  mov     rdi, rax
0x140028cf6  lea     rax, [rbp+57h+var_60]
0x140028cfa  mov     [rbp+57h+var_B0], rax
0x140028cfe  lea     rdx, aMicrosoftVoice_53; "Microsoft::VoiceAgentServices::Windows:"...
0x140028d05  lea     rcx, [rbp+57h+var_60]
0x140028d09  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028d0e  mov     rbx, rax
0x140028d11  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028d18  lea     rcx, [rbp+57h+var_A0]
0x140028d1c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028d21  nop
0x140028d22  mov     [rsp+120h+var_D8], r15
0x140028d27  mov     [rsp+120h+var_E0], r14
0x140028d2c  mov     [rsp+120h+var_E8], rsi
0x140028d31  mov     r15, [rbp+57h+var_C0]
0x140028d35  mov     [rsp+120h+var_F0], r15
0x140028d3a  mov     [rsp+120h+var_F8], rdi
0x140028d3f  mov     dword ptr [rsp+120h+var_100], 2Dh ; '-'
0x140028d47  mov     r9, rbx
0x140028d4a  mov     r8, rax
0x140028d4d  xor     edx, edx
0x140028d4f  mov     rcx, r13
0x140028d52  mov     rax, r12
0x140028d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028d5a  mov     r14, [r15+178h]
0x140028d61  mov     rax, [r14]
0x140028d64  mov     rsi, [rax+48h]
0x140028d68  lea     rax, [rbp+57h+var_A0]
0x140028d6c  mov     [rbp+57h+var_A8], rax
0x140028d70  lea     rdx, aHr0xX; "hr = 0x%x"
0x140028d77  lea     rcx, [rbp+57h+var_A0]
0x140028d7b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028d80  mov     rdi, rax
0x140028d83  lea     rax, [rbp+57h+var_80]
0x140028d87  mov     [rbp+57h+var_B0], rax
0x140028d8b  lea     rdx, aMicrosoftVoice_53; "Microsoft::VoiceAgentServices::Windows:"...
0x140028d92  lea     rcx, [rbp+57h+var_80]
0x140028d96  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028d9b  mov     rbx, rax
0x140028d9e  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028da5  lea     rcx, [rbp+57h+var_60]
0x140028da9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028dae  nop
0x140028daf  mov     [rsp+120h+var_F0], 0
0x140028db8  mov     [rsp+120h+var_F8], r15
0x140028dbd  mov     [rsp+120h+var_100], rdi
0x140028dc2  mov     r9d, 2Eh ; '.'
0x140028dc8  mov     r8, rbx
0x140028dcb  mov     rdx, rax
0x140028dce  mov     rcx, r14
0x140028dd1  mov     rax, rsi
0x140028dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028dd9  xor     eax, eax
0x140028ddb  mov     rcx, [rbp+57h+var_40]
0x140028ddf  xor     rcx, rsp; StackCookie
0x140028de2  call    __security_check_cookie
0x140028de7  mov     rbx, [rsp+120h+arg_10]
0x140028def  add     rsp, 0F0h
0x140028df6  pop     r15
0x140028df8  pop     r14
0x140028dfa  pop     r13
0x140028dfc  pop     r12
0x140028dfe  pop     rdi
0x140028dff  pop     rsi
0x140028e00  pop     rbp
0x140028e01  retn
```

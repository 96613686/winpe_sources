# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus(bool &)

- ea: `0x140029100`
- end: `0x140029323`
- name: `?GetVoiceActivationEnabledStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_N@Z`
- size: `547`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140029100`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400291dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400291dc`

## string_xrefs

- `0x1400291cb`: `AgentActivationEnabled`
- `0x14002914f`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029241`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x1400292c2`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002913e`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus`
- `0x14002922e`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus`
- `0x1400292af`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  const WCHAR *v6; // rax
  unsigned int v7; // r15d
  int v8; // r8d
  int v9; // eax
  bool v10; // r12
  __int64 v11; // r14
  void (__fastcall *v12)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, bool); // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // r14
  void (__fastcall *v17)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, unsigned int); // rsi
  int v18; // r8d
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  _BYTE *pvData; // [rsp+50h] [rbp-59h] BYREF
  DWORD pcbData[2]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE *v25; // [rsp+60h] [rbp-49h]
  _BYTE v26[32]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v27[32]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v28[32]; // [rsp+A8h] [rbp-1h] BYREF

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v28,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus");
  std::string::string(
    v27,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v27, v28, 220, this);
  std::string::~string(v27);
  std::string::~string(v28);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 272);
  LODWORD(pvData) = -559038737;
  pcbData[0] = 4;
  v7 = 0;
  RegGetValueW(HKEY_CURRENT_USER, v6, L"AgentActivationEnabled", 0x18u, 0, &pvData, pcbData);
  v9 = (int)pvData;
  v10 = (_DWORD)pvData != -559038737 && (_DWORD)pvData != 0;
  *a2 = v10;
  LOBYTE(v7) = v9 == -559038737;
  v11 = *((_QWORD *)this + 47);
  v12 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, bool))(*(_QWORD *)v11 + 16LL);
  *(_QWORD *)pcbData = v28;
  v13 = std::string::string(v28, "enabled = %d", v8);
  pvData = v27;
  v14 = std::string::string(
          v27,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus");
  v15 = std::string::string(
          v26,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v12(v11, 0, v15, v14, 224, v13, this, v10);
  v16 = *((_QWORD *)this + 47);
  v17 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, unsigned int))(*(_QWORD *)v16 + 72LL);
  v25 = v26;
  v19 = std::string::string(v26, "hr = 0x%x", v18);
  *(_QWORD *)pcbData = v28;
  v20 = std::string::string(
          v28,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatus");
  v21 = std::string::string(
          v27,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v17(v16, v21, v20, 225, v19, this, v7);
  return v7;
}

```

## disassembly

```asm
0x140029100  mov     [rsp-8+arg_10], rbx
0x140029105  push    rbp
0x140029106  push    rsi
0x140029107  push    rdi
0x140029108  push    r12
0x14002910a  push    r13
0x14002910c  push    r14
0x14002910e  push    r15
0x140029110  lea     rbp, [rsp-27h]
0x140029115  sub     rsp, 0D0h
0x14002911c  mov     rax, cs:__security_cookie
0x140029123  xor     rax, rsp
0x140029126  mov     [rbp+57h+var_38], rax
0x14002912a  mov     rsi, rdx
0x14002912d  mov     r13, rcx
0x140029130  mov     rdi, [rcx+178h]
0x140029137  mov     rax, [rdi]
0x14002913a  mov     rbx, [rax+28h]
0x14002913e  lea     rdx, aMicrosoftVoice_34; "Microsoft::VoiceAgentServices::Windows:"...
0x140029145  lea     rcx, [rbp+57h+var_58]
0x140029149  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002914e  nop
0x14002914f  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029156  lea     rcx, [rbp+57h+var_78]
0x14002915a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002915f  nop
0x140029160  mov     [rsp+100h+pdwType], r13
0x140029165  mov     r9d, 0DCh
0x14002916b  lea     r8, [rbp+57h+var_58]
0x14002916f  lea     rdx, [rbp+57h+var_78]
0x140029173  mov     rcx, rdi
0x140029176  mov     rax, rbx
0x140029179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002917e  nop
0x14002917f  lea     rcx, [rbp+57h+var_78]
0x140029183  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029188  nop
0x140029189  lea     rcx, [rbp+57h+var_58]
0x14002918d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029192  lea     rcx, [r13+110h]
0x140029199  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002919e  mov     ebx, 0DEADBEEFh
0x1400291a3  mov     dword ptr [rbp+57h+var_B0], ebx
0x1400291a6  mov     [rbp+57h+var_A8], 4
0x1400291ad  lea     rcx, [rbp+57h+var_A8]
0x1400291b1  mov     [rsp+100h+pcbData], rcx; pcbData
0x1400291b6  lea     rcx, [rbp+57h+var_B0]
0x1400291ba  mov     [rsp+100h+pvData], rcx; pvData
0x1400291bf  xor     r15d, r15d
0x1400291c2  mov     [rsp+100h+pdwType], r15; pdwType
0x1400291c7  lea     r9d, [r15+18h]; dwFlags
0x1400291cb  lea     r8, Value; "AgentActivationEnabled"
0x1400291d2  mov     rdx, rax; lpSubKey
0x1400291d5  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1400291dc  call    cs:__imp_RegGetValueW
0x1400291e2  mov     eax, dword ptr [rbp+57h+var_B0]
0x1400291e5  cmp     eax, ebx
0x1400291e7  jnz     short loc_1400291EE
0x1400291e9  mov     r12b, r15b
0x1400291ec  jmp     short loc_1400291F4
0x1400291ee  test    eax, eax
0x1400291f0  setnz   r12b
0x1400291f4  mov     [rsi], r12b
0x1400291f7  cmp     eax, ebx
0x1400291f9  setz    r15b
0x1400291fd  mov     r14, [r13+178h]
0x140029204  mov     rax, [r14]
0x140029207  mov     rsi, [rax+10h]
0x14002920b  lea     rax, [rbp+57h+var_58]
0x14002920f  mov     qword ptr [rbp+57h+var_A8], rax
0x140029213  lea     rdx, aEnabledD; "enabled = %d"
0x14002921a  lea     rcx, [rbp+57h+var_58]
0x14002921e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029223  mov     rdi, rax
0x140029226  lea     rax, [rbp+57h+var_78]
0x14002922a  mov     [rbp+57h+var_B0], rax
0x14002922e  lea     rdx, aMicrosoftVoice_34; "Microsoft::VoiceAgentServices::Windows:"...
0x140029235  lea     rcx, [rbp+57h+var_78]
0x140029239  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002923e  mov     rbx, rax
0x140029241  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029248  lea     rcx, [rbp+57h+var_98]
0x14002924c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029251  movzx   edx, r12b
0x140029255  mov     [rsp+100h+var_C8], edx
0x140029259  mov     [rsp+100h+pcbData], r13
0x14002925e  mov     [rsp+100h+pvData], rdi
0x140029263  mov     dword ptr [rsp+100h+pdwType], 0E0h
0x14002926b  mov     r9, rbx
0x14002926e  mov     r8, rax
0x140029271  xor     edx, edx
0x140029273  mov     rcx, r14
0x140029276  mov     rax, rsi
0x140029279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002927e  mov     r14, [r13+178h]
0x140029285  mov     rax, [r14]
0x140029288  mov     rsi, [rax+48h]
0x14002928c  lea     rax, [rbp+57h+var_98]
0x140029290  mov     [rbp+57h+var_A0], rax
0x140029294  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002929b  lea     rcx, [rbp+57h+var_98]
0x14002929f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400292a4  mov     rdi, rax
0x1400292a7  lea     rax, [rbp+57h+var_58]
0x1400292ab  mov     qword ptr [rbp+57h+var_A8], rax
0x1400292af  lea     rdx, aMicrosoftVoice_34; "Microsoft::VoiceAgentServices::Windows:"...
0x1400292b6  lea     rcx, [rbp+57h+var_58]
0x1400292ba  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400292bf  mov     rbx, rax
0x1400292c2  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400292c9  lea     rcx, [rbp+57h+var_78]
0x1400292cd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400292d2  nop
0x1400292d3  mov     dword ptr [rsp+100h+pcbData], r15d
0x1400292d8  mov     [rsp+100h+pvData], r13
0x1400292dd  mov     [rsp+100h+pdwType], rdi
0x1400292e2  mov     r9d, 0E1h
0x1400292e8  mov     r8, rbx
0x1400292eb  mov     rdx, rax
0x1400292ee  mov     rcx, r14
0x1400292f1  mov     rax, rsi
0x1400292f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400292f9  mov     eax, r15d
0x1400292fc  mov     rcx, [rbp+57h+var_38]
0x140029300  xor     rcx, rsp; StackCookie
0x140029303  call    __security_check_cookie
0x140029308  mov     rbx, [rsp+100h+arg_10]
0x140029310  add     rsp, 0D0h
0x140029317  pop     r15
0x140029319  pop     r14
0x14002931b  pop     r13
0x14002931d  pop     r12
0x14002931f  pop     rdi
0x140029320  pop     rsi
0x140029321  pop     rbp
0x140029322  retn
```

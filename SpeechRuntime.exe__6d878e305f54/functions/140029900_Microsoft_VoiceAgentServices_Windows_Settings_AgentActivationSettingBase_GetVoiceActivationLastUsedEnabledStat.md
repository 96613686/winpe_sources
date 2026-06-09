# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus(bool &)

- ea: `0x140029900`
- end: `0x140029aa3`
- name: `?GetVoiceActivationLastUsedEnabledStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_N@Z`
- size: `419`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140029900`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400299de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400299de`

## string_xrefs

- `0x140029951`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029a41`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029940`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus`
- `0x140029a2e`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus`
- `0x1400299cd`: `AgentActivationLastUsed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  const WCHAR *v6; // rax
  unsigned int v7; // r15d
  int v8; // r8d
  int v9; // ecx
  bool v10; // al
  __int64 v11; // r14
  void (__fastcall *v12)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, unsigned int); // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  _BYTE *pvData; // [rsp+40h] [rbp-49h] BYREF
  DWORD pcbData[4]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v20[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v21[32]; // [rsp+98h] [rbp+Fh] BYREF

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v21,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus");
  std::string::string(
    v20,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v20, v21, 251, this);
  std::string::~string(v20);
  std::string::~string(v21);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 272);
  LODWORD(pvData) = -559038737;
  pcbData[0] = 4;
  v7 = 0;
  RegGetValueW(HKEY_CURRENT_USER, v6, L"AgentActivationLastUsed", 0x18u, 0, &pvData, pcbData);
  v9 = (int)pvData;
  v10 = (_DWORD)pvData != -559038737 && (_DWORD)pvData != 0;
  *a2 = v10;
  LOBYTE(v7) = v9 == -559038737;
  v11 = *((_QWORD *)this + 47);
  v12 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, unsigned int))(*(_QWORD *)v11 + 72LL);
  *(_QWORD *)pcbData = v21;
  v13 = std::string::string(v21, "hr = 0x%x", v8);
  pvData = v20;
  v14 = std::string::string(
          v20,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationLastUsedEnabledStatus");
  v15 = std::string::string(
          v19,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v12(v11, v15, v14, 255, v13, this, v7);
  return v7;
}

```

## disassembly

```asm
0x140029900  mov     [rsp-8+arg_10], rbx
0x140029905  mov     [rsp-8+arg_18], rsi
0x14002990a  push    rbp
0x14002990b  push    rdi
0x14002990c  push    r13
0x14002990e  push    r14
0x140029910  push    r15
0x140029912  lea     rbp, [rsp-37h]
0x140029917  sub     rsp, 0C0h
0x14002991e  mov     rax, cs:__security_cookie
0x140029925  xor     rax, rsp
0x140029928  mov     [rbp+57h+var_28], rax
0x14002992c  mov     rsi, rdx
0x14002992f  mov     r13, rcx
0x140029932  mov     rdi, [rcx+178h]
0x140029939  mov     rax, [rdi]
0x14002993c  mov     rbx, [rax+28h]
0x140029940  lea     rdx, aMicrosoftVoice_22; "Microsoft::VoiceAgentServices::Windows:"...
0x140029947  lea     rcx, [rbp+57h+var_48]
0x14002994b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029950  nop
0x140029951  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029958  lea     rcx, [rbp+57h+var_68]
0x14002995c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029961  nop
0x140029962  mov     [rsp+0E0h+pdwType], r13
0x140029967  mov     r9d, 0FBh
0x14002996d  lea     r8, [rbp+57h+var_48]
0x140029971  lea     rdx, [rbp+57h+var_68]
0x140029975  mov     rcx, rdi
0x140029978  mov     rax, rbx
0x14002997b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029980  nop
0x140029981  lea     rcx, [rbp+57h+var_68]
0x140029985  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002998a  nop
0x14002998b  lea     rcx, [rbp+57h+var_48]
0x14002998f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029994  lea     rcx, [r13+110h]
0x14002999b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400299a0  mov     ebx, 0DEADBEEFh
0x1400299a5  mov     dword ptr [rbp+57h+var_A0], ebx
0x1400299a8  mov     [rbp+57h+var_98], 4
0x1400299af  lea     rcx, [rbp+57h+var_98]
0x1400299b3  mov     [rsp+0E0h+pcbData], rcx; pcbData
0x1400299b8  lea     rcx, [rbp+57h+var_A0]
0x1400299bc  mov     [rsp+0E0h+pvData], rcx; pvData
0x1400299c1  xor     r15d, r15d
0x1400299c4  mov     [rsp+0E0h+pdwType], r15; pdwType
0x1400299c9  lea     r9d, [r15+18h]; dwFlags
0x1400299cd  lea     r8, aAgentactivatio_1; "AgentActivationLastUsed"
0x1400299d4  mov     rdx, rax; lpSubKey
0x1400299d7  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1400299de  call    cs:__imp_RegGetValueW
0x1400299e4  mov     ecx, dword ptr [rbp+57h+var_A0]
0x1400299e7  cmp     ecx, ebx
0x1400299e9  jnz     short loc_1400299F0
0x1400299eb  mov     al, r15b
0x1400299ee  jmp     short loc_1400299F5
0x1400299f0  test    ecx, ecx
0x1400299f2  setnz   al
0x1400299f5  mov     [rsi], al
0x1400299f7  cmp     ecx, ebx
0x1400299f9  setz    r15b
0x1400299fd  mov     r14, [r13+178h]
0x140029a04  mov     rax, [r14]
0x140029a07  mov     rsi, [rax+48h]
0x140029a0b  lea     rax, [rbp+57h+var_48]
0x140029a0f  mov     qword ptr [rbp+57h+var_98], rax
0x140029a13  lea     rdx, aHr0xX; "hr = 0x%x"
0x140029a1a  lea     rcx, [rbp+57h+var_48]
0x140029a1e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029a23  mov     rdi, rax
0x140029a26  lea     rax, [rbp+57h+var_68]
0x140029a2a  mov     [rbp+57h+var_A0], rax
0x140029a2e  lea     rdx, aMicrosoftVoice_22; "Microsoft::VoiceAgentServices::Windows:"...
0x140029a35  lea     rcx, [rbp+57h+var_68]
0x140029a39  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029a3e  mov     rbx, rax
0x140029a41  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029a48  lea     rcx, [rbp+57h+var_88]
0x140029a4c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029a51  nop
0x140029a52  mov     dword ptr [rsp+0E0h+pcbData], r15d
0x140029a57  mov     [rsp+0E0h+pvData], r13
0x140029a5c  mov     [rsp+0E0h+pdwType], rdi
0x140029a61  mov     r9d, 0FFh
0x140029a67  mov     r8, rbx
0x140029a6a  mov     rdx, rax
0x140029a6d  mov     rcx, r14
0x140029a70  mov     rax, rsi
0x140029a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029a78  mov     eax, r15d
0x140029a7b  mov     rcx, [rbp+57h+var_28]
0x140029a7f  xor     rcx, rsp; StackCookie
0x140029a82  call    __security_check_cookie
0x140029a87  lea     r11, [rsp+0E0h+var_20]
0x140029a8f  mov     rbx, [r11+40h]
0x140029a93  mov     rsi, [r11+48h]
0x140029a97  mov     rsp, r11
0x140029a9a  pop     r15
0x140029a9c  pop     r14
0x140029a9e  pop     r13
0x140029aa0  pop     rdi
0x140029aa1  pop     rbp
0x140029aa2  retn
```

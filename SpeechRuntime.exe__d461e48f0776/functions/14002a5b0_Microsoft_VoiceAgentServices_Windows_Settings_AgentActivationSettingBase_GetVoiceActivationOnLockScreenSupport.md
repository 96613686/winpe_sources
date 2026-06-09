# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus(bool &)

- ea: `0x14002a5b0`
- end: `0x14002a753`
- name: `?GetVoiceActivationOnLockScreenSupportedStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_N@Z`
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
- `0x14002a5b0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002a68e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002a68e`

## string_xrefs

- `0x14002a601`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a6f1`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a5f0`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus`
- `0x14002a6de`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus`

## pseudocode

```c
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus");
  std::string::string(
    v20,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v20, v21, 241, this);
  std::string::~string(v20);
  std::string::~string(v21);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 272);
  LODWORD(pvData) = -559038737;
  pcbData[0] = 4;
  v7 = 0;
  RegGetValueW(HKEY_CURRENT_USER, v6, L"LockScreenActivationSupported", 0x18u, 0, &pvData, pcbData);
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
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenSupportedStatus");
  v15 = std::string::string(
          v19,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v12(v11, v15, v14, 245, v13, this, v7);
  return v7;
}

```

## disassembly

```asm
0x14002a5b0  mov     [rsp-8+arg_10], rbx
0x14002a5b5  mov     [rsp-8+arg_18], rsi
0x14002a5ba  push    rbp
0x14002a5bb  push    rdi
0x14002a5bc  push    r13
0x14002a5be  push    r14
0x14002a5c0  push    r15
0x14002a5c2  lea     rbp, [rsp-37h]
0x14002a5c7  sub     rsp, 0C0h
0x14002a5ce  mov     rax, cs:__security_cookie
0x14002a5d5  xor     rax, rsp
0x14002a5d8  mov     [rbp+57h+var_28], rax
0x14002a5dc  mov     rsi, rdx
0x14002a5df  mov     r13, rcx
0x14002a5e2  mov     rdi, [rcx+178h]
0x14002a5e9  mov     rax, [rdi]
0x14002a5ec  mov     rbx, [rax+28h]
0x14002a5f0  lea     rdx, aMicrosoftVoice_36; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a5f7  lea     rcx, [rbp+57h+var_48]
0x14002a5fb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a600  nop
0x14002a601  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a608  lea     rcx, [rbp+57h+var_68]
0x14002a60c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a611  nop
0x14002a612  mov     [rsp+0E0h+pdwType], r13
0x14002a617  mov     r9d, 0F1h
0x14002a61d  lea     r8, [rbp+57h+var_48]
0x14002a621  lea     rdx, [rbp+57h+var_68]
0x14002a625  mov     rcx, rdi
0x14002a628  mov     rax, rbx
0x14002a62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a630  nop
0x14002a631  lea     rcx, [rbp+57h+var_68]
0x14002a635  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a63a  nop
0x14002a63b  lea     rcx, [rbp+57h+var_48]
0x14002a63f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a644  lea     rcx, [r13+110h]
0x14002a64b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002a650  mov     ebx, 0DEADBEEFh
0x14002a655  mov     dword ptr [rbp+57h+var_A0], ebx
0x14002a658  mov     [rbp+57h+var_98], 4
0x14002a65f  lea     rcx, [rbp+57h+var_98]
0x14002a663  mov     [rsp+0E0h+pcbData], rcx; pcbData
0x14002a668  lea     rcx, [rbp+57h+var_A0]
0x14002a66c  mov     [rsp+0E0h+pvData], rcx; pvData
0x14002a671  xor     r15d, r15d
0x14002a674  mov     [rsp+0E0h+pdwType], r15; pdwType
0x14002a679  lea     r9d, [r15+18h]; dwFlags
0x14002a67d  lea     r8, aLockscreenacti; "LockScreenActivationSupported"
0x14002a684  mov     rdx, rax; lpSubKey
0x14002a687  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14002a68e  call    cs:__imp_RegGetValueW
0x14002a694  mov     ecx, dword ptr [rbp+57h+var_A0]
0x14002a697  cmp     ecx, ebx
0x14002a699  jnz     short loc_14002A6A0
0x14002a69b  mov     al, r15b
0x14002a69e  jmp     short loc_14002A6A5
0x14002a6a0  test    ecx, ecx
0x14002a6a2  setnz   al
0x14002a6a5  mov     [rsi], al
0x14002a6a7  cmp     ecx, ebx
0x14002a6a9  setz    r15b
0x14002a6ad  mov     r14, [r13+178h]
0x14002a6b4  mov     rax, [r14]
0x14002a6b7  mov     rsi, [rax+48h]
0x14002a6bb  lea     rax, [rbp+57h+var_48]
0x14002a6bf  mov     qword ptr [rbp+57h+var_98], rax
0x14002a6c3  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002a6ca  lea     rcx, [rbp+57h+var_48]
0x14002a6ce  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a6d3  mov     rdi, rax
0x14002a6d6  lea     rax, [rbp+57h+var_68]
0x14002a6da  mov     [rbp+57h+var_A0], rax
0x14002a6de  lea     rdx, aMicrosoftVoice_36; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a6e5  lea     rcx, [rbp+57h+var_68]
0x14002a6e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a6ee  mov     rbx, rax
0x14002a6f1  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a6f8  lea     rcx, [rbp+57h+var_88]
0x14002a6fc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a701  nop
0x14002a702  mov     dword ptr [rsp+0E0h+pcbData], r15d
0x14002a707  mov     [rsp+0E0h+pvData], r13
0x14002a70c  mov     [rsp+0E0h+pdwType], rdi
0x14002a711  mov     r9d, 0F5h
0x14002a717  mov     r8, rbx
0x14002a71a  mov     rdx, rax
0x14002a71d  mov     rcx, r14
0x14002a720  mov     rax, rsi
0x14002a723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a728  mov     eax, r15d
0x14002a72b  mov     rcx, [rbp+57h+var_28]
0x14002a72f  xor     rcx, rsp; StackCookie
0x14002a732  call    __security_check_cookie
0x14002a737  lea     r11, [rsp+0E0h+var_20]
0x14002a73f  mov     rbx, [r11+40h]
0x14002a743  mov     rsi, [r11+48h]
0x14002a747  mov     rsp, r11
0x14002a74a  pop     r15
0x14002a74c  pop     r14
0x14002a74e  pop     r13
0x14002a750  pop     rdi
0x14002a751  pop     rbp
0x14002a752  retn
```

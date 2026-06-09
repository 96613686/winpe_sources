# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus(bool &)

- ea: `0x140029ef0`
- end: `0x14002a093`
- name: `?GetVoiceActivationOnLockScreenEnabledStatus@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_N@Z`
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
- `0x140029ef0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140029fce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140029fce`

## string_xrefs

- `0x140029fbd`: `AgentActivationOnLockScreenEnabled`
- `0x140029f41`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002a031`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029f30`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus`
- `0x14002a01e`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus`

## pseudocode

```c
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus(
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
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus");
  std::string::string(
    v20,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v20, v21, 231, this);
  std::string::~string(v20);
  std::string::~string(v21);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 272);
  LODWORD(pvData) = -559038737;
  pcbData[0] = 4;
  v7 = 0;
  RegGetValueW(HKEY_CURRENT_USER, v6, L"AgentActivationOnLockScreenEnabled", 0x18u, 0, &pvData, pcbData);
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
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationOnLockScreenEnabledStatus");
  v15 = std::string::string(
          v19,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v12(v11, v15, v14, 235, v13, this, v7);
  return v7;
}

```

## disassembly

```asm
0x140029ef0  mov     [rsp-8+arg_10], rbx
0x140029ef5  mov     [rsp-8+arg_18], rsi
0x140029efa  push    rbp
0x140029efb  push    rdi
0x140029efc  push    r13
0x140029efe  push    r14
0x140029f00  push    r15
0x140029f02  lea     rbp, [rsp-37h]
0x140029f07  sub     rsp, 0C0h
0x140029f0e  mov     rax, cs:__security_cookie
0x140029f15  xor     rax, rsp
0x140029f18  mov     [rbp+57h+var_28], rax
0x140029f1c  mov     rsi, rdx
0x140029f1f  mov     r13, rcx
0x140029f22  mov     rdi, [rcx+178h]
0x140029f29  mov     rax, [rdi]
0x140029f2c  mov     rbx, [rax+28h]
0x140029f30  lea     rdx, aMicrosoftVoice_54; "Microsoft::VoiceAgentServices::Windows:"...
0x140029f37  lea     rcx, [rbp+57h+var_48]
0x140029f3b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029f40  nop
0x140029f41  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029f48  lea     rcx, [rbp+57h+var_68]
0x140029f4c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029f51  nop
0x140029f52  mov     [rsp+0E0h+pdwType], r13
0x140029f57  mov     r9d, 0E7h
0x140029f5d  lea     r8, [rbp+57h+var_48]
0x140029f61  lea     rdx, [rbp+57h+var_68]
0x140029f65  mov     rcx, rdi
0x140029f68  mov     rax, rbx
0x140029f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029f70  nop
0x140029f71  lea     rcx, [rbp+57h+var_68]
0x140029f75  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029f7a  nop
0x140029f7b  lea     rcx, [rbp+57h+var_48]
0x140029f7f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029f84  lea     rcx, [r13+110h]
0x140029f8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029f90  mov     ebx, 0DEADBEEFh
0x140029f95  mov     dword ptr [rbp+57h+var_A0], ebx
0x140029f98  mov     [rbp+57h+var_98], 4
0x140029f9f  lea     rcx, [rbp+57h+var_98]
0x140029fa3  mov     [rsp+0E0h+pcbData], rcx; pcbData
0x140029fa8  lea     rcx, [rbp+57h+var_A0]
0x140029fac  mov     [rsp+0E0h+pvData], rcx; pvData
0x140029fb1  xor     r15d, r15d
0x140029fb4  mov     [rsp+0E0h+pdwType], r15; pdwType
0x140029fb9  lea     r9d, [r15+18h]; dwFlags
0x140029fbd  lea     r8, aAgentactivatio_0; "AgentActivationOnLockScreenEnabled"
0x140029fc4  mov     rdx, rax; lpSubKey
0x140029fc7  mov     rcx, 0FFFFFFFF80000001h; hkey
0x140029fce  call    cs:__imp_RegGetValueW
0x140029fd4  mov     ecx, dword ptr [rbp+57h+var_A0]
0x140029fd7  cmp     ecx, ebx
0x140029fd9  jnz     short loc_140029FE0
0x140029fdb  mov     al, r15b
0x140029fde  jmp     short loc_140029FE5
0x140029fe0  test    ecx, ecx
0x140029fe2  setnz   al
0x140029fe5  mov     [rsi], al
0x140029fe7  cmp     ecx, ebx
0x140029fe9  setz    r15b
0x140029fed  mov     r14, [r13+178h]
0x140029ff4  mov     rax, [r14]
0x140029ff7  mov     rsi, [rax+48h]
0x140029ffb  lea     rax, [rbp+57h+var_48]
0x140029fff  mov     qword ptr [rbp+57h+var_98], rax
0x14002a003  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002a00a  lea     rcx, [rbp+57h+var_48]
0x14002a00e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a013  mov     rdi, rax
0x14002a016  lea     rax, [rbp+57h+var_68]
0x14002a01a  mov     [rbp+57h+var_A0], rax
0x14002a01e  lea     rdx, aMicrosoftVoice_54; "Microsoft::VoiceAgentServices::Windows:"...
0x14002a025  lea     rcx, [rbp+57h+var_68]
0x14002a029  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a02e  mov     rbx, rax
0x14002a031  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002a038  lea     rcx, [rbp+57h+var_88]
0x14002a03c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a041  nop
0x14002a042  mov     dword ptr [rsp+0E0h+pcbData], r15d
0x14002a047  mov     [rsp+0E0h+pvData], r13
0x14002a04c  mov     [rsp+0E0h+pdwType], rdi
0x14002a051  mov     r9d, 0EBh
0x14002a057  mov     r8, rbx
0x14002a05a  mov     rdx, rax
0x14002a05d  mov     rcx, r14
0x14002a060  mov     rax, rsi
0x14002a063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a068  mov     eax, r15d
0x14002a06b  mov     rcx, [rbp+57h+var_28]
0x14002a06f  xor     rcx, rsp; StackCookie
0x14002a072  call    __security_check_cookie
0x14002a077  lea     r11, [rsp+0E0h+var_20]
0x14002a07f  mov     rbx, [r11+40h]
0x14002a083  mov     rsi, [r11+48h]
0x14002a087  mov     rsp, r11
0x14002a08a  pop     r15
0x14002a08c  pop     r14
0x14002a08e  pop     r13
0x14002a090  pop     rdi
0x14002a091  pop     rbp
0x14002a092  retn
```

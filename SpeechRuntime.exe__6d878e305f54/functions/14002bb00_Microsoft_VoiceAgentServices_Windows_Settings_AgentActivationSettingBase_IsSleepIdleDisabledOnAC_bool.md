# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC(bool &)

- ea: `0x14002bb00`
- end: `0x14002bdb2`
- name: `?IsSleepIdleDisabledOnAC@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_N@Z`
- size: `690`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140020ff0`
- `0x140021658`
- `0x14002bb00`
- `0x140031010`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x14002bbb9`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x14002bbb9`
- `POWRPROF!PowerReadACValueIndex` at `0x14002bc0b`
- `POWRPROF!PowerReadACValueIndex` at `0x14002bc44`
- `POWRPROF!PowerReadACValueIndex` at `0x14002bc0b`
- `POWRPROF!PowerReadACValueIndex` at `0x14002bc44`

## string_xrefs

- `0x14002bb53`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002bcbf`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002bd4e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002bb42`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC`
- `0x14002bcac`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC`
- `0x14002bd3b`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  bool v6; // r15
  signed int ActiveScheme; // eax
  signed int v8; // ebx
  __int64 v9; // rdx
  signed int v11; // eax
  signed int v12; // eax
  int v13; // r8d
  int v14; // r9d
  DWORD v15; // r12d
  DWORD v16; // r13d
  __int64 v17; // r14
  void (__fastcall *v18)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL, DWORD, DWORD); // rsi
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *v22; // r15
  __int64 v23; // r14
  void (__fastcall *v24)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v25; // r8d
  __int64 v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rax
  int AcValueIndex; // [rsp+20h] [rbp-B9h]
  BOOL v30; // [rsp+38h] [rbp-A1h]
  DWORD v31; // [rsp+60h] [rbp-79h] BYREF
  DWORD v32; // [rsp+64h] [rbp-75h] BYREF
  GUID *ActivePolicyGuid; // [rsp+68h] [rbp-71h] BYREF
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *v34; // [rsp+70h] [rbp-69h]
  _BYTE *v35; // [rsp+78h] [rbp-61h]
  _BYTE *v36; // [rsp+80h] [rbp-59h]
  _BYTE *v37; // [rsp+88h] [rbp-51h]
  _BYTE v38[32]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v39[32]; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v40[32]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v34 = this;
  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v40,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC");
  std::string::string(
    v39,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  AcValueIndex = (int)this;
  v5(v4, v39, v40, 515);
  std::string::~string(v39);
  std::string::~string(v40);
  ActivePolicyGuid = 0;
  v6 = 1;
  v32 = 1;
  v31 = 1;
  *a2 = 0;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  v8 = ActiveScheme;
  if ( ActiveScheme > 0 )
    v8 = (unsigned __int16)ActiveScheme | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = 520;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)v8,
      AcValueIndex);
    return (unsigned int)v8;
  }
  v11 = PowerReadACValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_STANDBY_TIMEOUT, &v32);
  v8 = v11;
  if ( v11 > 0 )
    v8 = (unsigned __int16)v11 | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = 521;
    goto LABEL_5;
  }
  v12 = PowerReadACValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_HIBERNATE_TIMEOUT, &v31);
  v8 = v12;
  if ( v12 > 0 )
    v8 = (unsigned __int16)v12 | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = 522;
    goto LABEL_5;
  }
  v15 = v31;
  v16 = v32;
  if ( v32 || v31 )
    v6 = 0;
  *a2 = v6;
  v17 = *((_QWORD *)this + 47);
  v18 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL, DWORD, DWORD))(*(_QWORD *)v17 + 16LL);
  v35 = v40;
  v19 = std::string::string(
          v40,
          "sleepDisabledOnAC = %d, standbyTimeout = %lu, hibernateTimeout = %lu",
          v13,
          v14,
          AcValueIndex);
  v36 = v39;
  v20 = std::string::string(
          v39,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC");
  v21 = std::string::string(
          v38,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v30 = v6;
  v22 = v34;
  v18(v17, 0, v21, v20, 524, v19, v34, v30, v16, v15);
  v23 = *((_QWORD *)v22 + 47);
  v24 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v23 + 72LL);
  v37 = v38;
  v26 = std::string::string(v38, "hr = 0x%x", v25);
  v36 = v40;
  v27 = std::string::string(
          v40,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsSleepIdleDisabledOnAC");
  v28 = std::string::string(
          v39,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v24(v23, v28, v27, 525, v26, v22, 0);
  return 0;
}

```

## disassembly

```asm
0x14002bb00  mov     [rsp-8+arg_10], rbx
0x14002bb05  push    rbp
0x14002bb06  push    rsi
0x14002bb07  push    rdi
0x14002bb08  push    r12
0x14002bb0a  push    r13
0x14002bb0c  push    r14
0x14002bb0e  push    r15
0x14002bb10  lea     rbp, [rsp-27h]
0x14002bb15  sub     rsp, 100h
0x14002bb1c  mov     rax, cs:__security_cookie
0x14002bb23  xor     rax, rsp
0x14002bb26  mov     [rbp+57h+var_40], rax
0x14002bb2a  mov     r14, rdx
0x14002bb2d  mov     rsi, rcx
0x14002bb30  mov     [rbp+57h+var_C0], rcx
0x14002bb34  mov     rdi, [rcx+178h]
0x14002bb3b  mov     rax, [rdi]
0x14002bb3e  mov     rbx, [rax+28h]
0x14002bb42  lea     rdx, aMicrosoftVoice_4; "Microsoft::VoiceAgentServices::Windows:"...
0x14002bb49  lea     rcx, [rbp+57h+var_60]
0x14002bb4d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bb52  nop
0x14002bb53  lea     r12, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002bb5a  mov     rdx, r12
0x14002bb5d  lea     rcx, [rbp+57h+var_80]
0x14002bb61  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bb66  nop
0x14002bb67  mov     [rsp+130h+AcValueIndex], rsi; int
0x14002bb6c  mov     r9d, 203h
0x14002bb72  lea     r8, [rbp+57h+var_60]
0x14002bb76  lea     rdx, [rbp+57h+var_80]
0x14002bb7a  mov     rcx, rdi
0x14002bb7d  mov     rax, rbx
0x14002bb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bb85  nop
0x14002bb86  lea     rcx, [rbp+57h+var_80]
0x14002bb8a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002bb8f  nop
0x14002bb90  lea     rcx, [rbp+57h+var_60]
0x14002bb94  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002bb99  mov     [rbp+57h+ActivePolicyGuid], 0
0x14002bba1  mov     r15d, 1
0x14002bba7  mov     [rbp+57h+var_CC], r15d
0x14002bbab  mov     [rbp+57h+var_D0], r15d
0x14002bbaf  mov     byte ptr [r14], 0
0x14002bbb3  lea     rdx, [rbp+57h+ActivePolicyGuid]; ActivePolicyGuid
0x14002bbb7  xor     ecx, ecx; UserRootPowerKey
0x14002bbb9  call    cs:__imp_PowerGetActiveScheme
0x14002bbbf  mov     ebx, eax
0x14002bbc1  mov     edi, 80070000h
0x14002bbc6  test    eax, eax
0x14002bbc8  jle     short loc_14002BBCF
0x14002bbca  movzx   ebx, ax
0x14002bbcd  or      ebx, edi
0x14002bbcf  test    ebx, ebx
0x14002bbd1  jns     short loc_14002BBEE
0x14002bbd3  mov     edx, 208h; void *
0x14002bbd8  mov     rcx, [rbp+5Fh]; this
0x14002bbdc  mov     r9d, ebx; char *
0x14002bbdf  mov     r8, r12; unsigned int
0x14002bbe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002bbe7  mov     eax, ebx
0x14002bbe9  jmp     loc_14002BD8B
0x14002bbee  lea     rax, [rbp+57h+var_CC]
0x14002bbf2  mov     [rsp+130h+AcValueIndex], rax; AcValueIndex
0x14002bbf7  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x14002bbfe  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x14002bc05  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x14002bc09  xor     ecx, ecx; RootPowerKey
0x14002bc0b  call    cs:__imp_PowerReadACValueIndex
0x14002bc11  mov     ebx, eax
0x14002bc13  test    eax, eax
0x14002bc15  jle     short loc_14002BC1C
0x14002bc17  movzx   ebx, ax
0x14002bc1a  or      ebx, edi
0x14002bc1c  test    ebx, ebx
0x14002bc1e  jns     short loc_14002BC27
0x14002bc20  mov     edx, 209h
0x14002bc25  jmp     short loc_14002BBD8
0x14002bc27  lea     rax, [rbp+57h+var_D0]
0x14002bc2b  mov     [rsp+130h+AcValueIndex], rax; AcValueIndex
0x14002bc30  lea     r9, GUID_HIBERNATE_TIMEOUT; PowerSettingGuid
0x14002bc37  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x14002bc3e  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x14002bc42  xor     ecx, ecx; RootPowerKey
0x14002bc44  call    cs:__imp_PowerReadACValueIndex
0x14002bc4a  mov     ebx, eax
0x14002bc4c  test    eax, eax
0x14002bc4e  jle     short loc_14002BC55
0x14002bc50  movzx   ebx, ax
0x14002bc53  or      ebx, edi
0x14002bc55  test    ebx, ebx
0x14002bc57  jns     short loc_14002BC63
0x14002bc59  mov     edx, 20Ah
0x14002bc5e  jmp     loc_14002BBD8
0x14002bc63  mov     r12d, [rbp+57h+var_D0]
0x14002bc67  mov     r13d, [rbp+57h+var_CC]
0x14002bc6b  test    r13d, r13d
0x14002bc6e  jnz     short loc_14002BC75
0x14002bc70  test    r12d, r12d
0x14002bc73  jz      short loc_14002BC78
0x14002bc75  xor     r15b, r15b
0x14002bc78  mov     [r14], r15b
0x14002bc7b  mov     r14, [rsi+178h]
0x14002bc82  mov     rax, [r14]
0x14002bc85  mov     rsi, [rax+10h]
0x14002bc89  lea     rax, [rbp+57h+var_60]
0x14002bc8d  mov     [rbp+57h+var_B8], rax
0x14002bc91  lea     rdx, aSleepdisabledo; "sleepDisabledOnAC = %d, standbyTimeout "...
0x14002bc98  lea     rcx, [rbp+57h+var_60]
0x14002bc9c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bca1  mov     rdi, rax
0x14002bca4  lea     rax, [rbp+57h+var_80]
0x14002bca8  mov     [rbp+57h+var_B0], rax
0x14002bcac  lea     rdx, aMicrosoftVoice_4; "Microsoft::VoiceAgentServices::Windows:"...
0x14002bcb3  lea     rcx, [rbp+57h+var_80]
0x14002bcb7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bcbc  mov     rbx, rax
0x14002bcbf  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002bcc6  lea     rcx, [rbp+57h+var_A0]
0x14002bcca  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bccf  movzx   edx, r15b
0x14002bcd3  mov     [rsp+130h+var_E8], r12d
0x14002bcd8  mov     [rsp+130h+var_F0], r13d
0x14002bcdd  mov     [rsp+130h+var_F8], edx
0x14002bce1  mov     r15, [rbp+57h+var_C0]
0x14002bce5  mov     [rsp+130h+var_100], r15
0x14002bcea  mov     [rsp+130h+var_108], rdi
0x14002bcef  mov     dword ptr [rsp+130h+AcValueIndex], 20Ch
0x14002bcf7  mov     r9, rbx
0x14002bcfa  mov     r8, rax
0x14002bcfd  xor     edx, edx
0x14002bcff  mov     rcx, r14
0x14002bd02  mov     rax, rsi
0x14002bd05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bd0a  mov     r14, [r15+178h]
0x14002bd11  mov     rax, [r14]
0x14002bd14  mov     rsi, [rax+48h]
0x14002bd18  lea     rax, [rbp+57h+var_A0]
0x14002bd1c  mov     [rbp+57h+var_A8], rax
0x14002bd20  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002bd27  lea     rcx, [rbp+57h+var_A0]
0x14002bd2b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bd30  mov     rdi, rax
0x14002bd33  lea     rax, [rbp+57h+var_60]
0x14002bd37  mov     [rbp+57h+var_B0], rax
0x14002bd3b  lea     rdx, aMicrosoftVoice_4; "Microsoft::VoiceAgentServices::Windows:"...
0x14002bd42  lea     rcx, [rbp+57h+var_60]
0x14002bd46  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bd4b  mov     rbx, rax
0x14002bd4e  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002bd55  lea     rcx, [rbp+57h+var_80]
0x14002bd59  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002bd5e  nop
0x14002bd5f  mov     [rsp+130h+var_100], 0
0x14002bd68  mov     [rsp+130h+var_108], r15
0x14002bd6d  mov     [rsp+130h+AcValueIndex], rdi
0x14002bd72  mov     r9d, 20Dh
0x14002bd78  mov     r8, rbx
0x14002bd7b  mov     rdx, rax
0x14002bd7e  mov     rcx, r14
0x14002bd81  mov     rax, rsi
0x14002bd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bd89  xor     eax, eax
0x14002bd8b  mov     rcx, [rbp+57h+var_40]
0x14002bd8f  xor     rcx, rsp; StackCookie
0x14002bd92  call    __security_check_cookie
0x14002bd97  mov     rbx, [rsp+130h+arg_10]
0x14002bd9f  add     rsp, 100h
0x14002bda6  pop     r15
0x14002bda8  pop     r14
0x14002bdaa  pop     r13
0x14002bdac  pop     r12
0x14002bdae  pop     rdi
0x14002bdaf  pop     rsi
0x14002bdb0  pop     rbp
0x14002bdb1  retn
```

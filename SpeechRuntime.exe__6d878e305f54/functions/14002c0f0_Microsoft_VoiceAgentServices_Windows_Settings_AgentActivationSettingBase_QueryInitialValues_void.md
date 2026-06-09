# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues(void)

- ea: `0x14002c0f0`
- end: `0x14002c31a`
- name: `?QueryInitialValues@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ`
- size: `554`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002b004`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140020ff0`
- `0x140021658`
- `0x14002c0f0`
- `0x140031010`

## string_xrefs

- `0x14002c13e`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c12d`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues`
- `0x14002c2a6`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // r8d
  __int64 v8; // r14
  void (__fastcall *v9)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  _BYTE v13[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v14[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v15[32]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v15,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues");
  std::string::string(
    v14,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v14, v15, 480);
  std::string::~string(v14);
  std::string::~string(v15);
  v4 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *, char *))(*(_QWORD *)this + 184LL))(
         this,
         (char *)this + 304,
         (char *)this + 308);
  if ( v4 < 0 )
  {
    v5 = 481;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
      (const char *)(unsigned int)v4,
      (int)this);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *, char *))(*(_QWORD *)this + 192LL))(
         this,
         (char *)this + 312,
         (char *)this + 316);
  if ( v4 < 0 )
  {
    v5 = 482;
    goto LABEL_3;
  }
  v4 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *, char *))(*(_QWORD *)this + 200LL))(
         this,
         (char *)this + 320,
         (char *)this + 324);
  if ( v4 < 0 )
  {
    v5 = 483;
    goto LABEL_3;
  }
  v4 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *, char *))(*(_QWORD *)this + 208LL))(
         this,
         (char *)this + 336,
         (char *)this + 332);
  if ( v4 < 0 )
  {
    v5 = 484;
    goto LABEL_3;
  }
  v4 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, char *))(*(_QWORD *)this + 48LL))(
         this,
         (char *)this + 344);
  if ( v4 < 0 )
  {
    v5 = 485;
    goto LABEL_3;
  }
  v8 = *((_QWORD *)this + 47);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v8 + 72LL);
  v10 = std::string::string(v15, "hr = 0x%x", v7);
  v11 = std::string::string(
          v14,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::QueryInitialValues");
  v12 = std::string::string(
          v13,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v9(v8, v12, v11, 486, v10, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002c0f0  mov     [rsp-8+arg_8], rbx
0x14002c0f5  mov     [rsp-8+arg_10], rsi
0x14002c0fa  push    rbp
0x14002c0fb  push    rdi
0x14002c0fc  push    r12
0x14002c0fe  push    r14
0x14002c100  push    r15
0x14002c102  lea     rbp, [rsp-37h]
0x14002c107  sub     rsp, 0C0h
0x14002c10e  mov     rax, cs:__security_cookie
0x14002c115  xor     rax, rsp
0x14002c118  mov     [rbp+57h+var_28], rax
0x14002c11c  mov     r15, rcx
0x14002c11f  mov     rdi, [rcx+178h]
0x14002c126  mov     rax, [rdi]
0x14002c129  mov     rbx, [rax+28h]
0x14002c12d  lea     rdx, aMicrosoftVoice_17; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c134  lea     rcx, [rbp+57h+var_48]
0x14002c138  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c13d  nop
0x14002c13e  lea     r12, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c145  mov     rdx, r12
0x14002c148  lea     rcx, [rbp+57h+var_68]
0x14002c14c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c151  nop
0x14002c152  mov     qword ptr [rsp+0E0h+var_C0], r15; int
0x14002c157  mov     r9d, 1E0h
0x14002c15d  lea     r8, [rbp+57h+var_48]
0x14002c161  lea     rdx, [rbp+57h+var_68]
0x14002c165  mov     rcx, rdi
0x14002c168  mov     rax, rbx
0x14002c16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c170  nop
0x14002c171  lea     rcx, [rbp+57h+var_68]
0x14002c175  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c17a  nop
0x14002c17b  lea     rcx, [rbp+57h+var_48]
0x14002c17f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c184  mov     rax, [r15]
0x14002c187  lea     r8, [r15+134h]
0x14002c18e  lea     rdx, [r15+130h]
0x14002c195  mov     rcx, r15
0x14002c198  mov     rax, [rax+0B8h]
0x14002c19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c1a4  mov     ebx, eax
0x14002c1a6  test    eax, eax
0x14002c1a8  jns     short loc_14002C1C5
0x14002c1aa  mov     edx, 1E1h; void *
0x14002c1af  mov     rcx, [rbp+5Fh]; this
0x14002c1b3  mov     r9d, ebx; char *
0x14002c1b6  mov     r8, r12; unsigned int
0x14002c1b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c1be  mov     eax, ebx
0x14002c1c0  jmp     loc_14002C2F2
0x14002c1c5  mov     rax, [r15]
0x14002c1c8  lea     r8, [r15+13Ch]
0x14002c1cf  lea     rdx, [r15+138h]
0x14002c1d6  mov     rcx, r15
0x14002c1d9  mov     rax, [rax+0C0h]
0x14002c1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c1e5  mov     ebx, eax
0x14002c1e7  test    eax, eax
0x14002c1e9  jns     short loc_14002C1F2
0x14002c1eb  mov     edx, 1E2h
0x14002c1f0  jmp     short loc_14002C1AF
0x14002c1f2  mov     rax, [r15]
0x14002c1f5  lea     r8, [r15+144h]
0x14002c1fc  lea     rdx, [r15+140h]
0x14002c203  mov     rcx, r15
0x14002c206  mov     rax, [rax+0C8h]
0x14002c20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c212  mov     ebx, eax
0x14002c214  test    eax, eax
0x14002c216  jns     short loc_14002C21F
0x14002c218  mov     edx, 1E3h
0x14002c21d  jmp     short loc_14002C1AF
0x14002c21f  mov     rax, [r15]
0x14002c222  lea     r8, [r15+14Ch]
0x14002c229  lea     rdx, [r15+150h]
0x14002c230  mov     rcx, r15
0x14002c233  mov     rax, [rax+0D0h]
0x14002c23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c23f  mov     ebx, eax
0x14002c241  test    eax, eax
0x14002c243  jns     short loc_14002C24F
0x14002c245  mov     edx, 1E4h
0x14002c24a  jmp     loc_14002C1AF
0x14002c24f  mov     rax, [r15]
0x14002c252  lea     rdx, [r15+158h]
0x14002c259  mov     rcx, r15
0x14002c25c  mov     rax, [rax+30h]
0x14002c260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c265  mov     ebx, eax
0x14002c267  test    eax, eax
0x14002c269  jns     short loc_14002C275
0x14002c26b  mov     edx, 1E5h
0x14002c270  jmp     loc_14002C1AF
0x14002c275  mov     r14, [r15+178h]
0x14002c27c  mov     rax, [r14]
0x14002c27f  mov     rsi, [rax+48h]
0x14002c283  lea     rax, [rbp+57h+var_48]
0x14002c287  mov     [rbp+57h+var_A0], rax
0x14002c28b  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002c292  lea     rcx, [rbp+57h+var_48]
0x14002c296  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c29b  mov     rdi, rax
0x14002c29e  lea     rax, [rbp+57h+var_68]
0x14002c2a2  mov     [rbp+57h+var_98], rax
0x14002c2a6  lea     rdx, aMicrosoftVoice_17; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c2ad  lea     rcx, [rbp+57h+var_68]
0x14002c2b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c2b6  mov     rbx, rax
0x14002c2b9  mov     rdx, r12
0x14002c2bc  lea     rcx, [rbp+57h+var_88]
0x14002c2c0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c2c5  nop
0x14002c2c6  mov     [rsp+0E0h+var_B0], 0
0x14002c2cf  mov     [rsp+0E0h+var_B8], r15
0x14002c2d4  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x14002c2d9  mov     r9d, 1E6h
0x14002c2df  mov     r8, rbx
0x14002c2e2  mov     rdx, rax
0x14002c2e5  mov     rcx, r14
0x14002c2e8  mov     rax, rsi
0x14002c2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c2f0  xor     eax, eax
0x14002c2f2  mov     rcx, [rbp+57h+var_28]
0x14002c2f6  xor     rcx, rsp; StackCookie
0x14002c2f9  call    __security_check_cookie
0x14002c2fe  lea     r11, [rsp+0E0h+var_20]
0x14002c306  mov     rbx, [r11+38h]
0x14002c30a  mov     rsi, [r11+40h]
0x14002c30e  mov     rsp, r11
0x14002c311  pop     r15
0x14002c313  pop     r14
0x14002c315  pop     r12
0x14002c317  pop     rdi
0x14002c318  pop     rbp
0x14002c319  retn
```

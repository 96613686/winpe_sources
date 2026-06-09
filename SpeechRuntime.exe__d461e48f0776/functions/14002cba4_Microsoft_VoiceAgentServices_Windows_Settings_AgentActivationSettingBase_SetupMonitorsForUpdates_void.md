# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates(void)

- ea: `0x14002cba4`
- end: `0x14002cdc8`
- name: `?SetupMonitorsForUpdates@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAJXZ`
- size: `548`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002b004`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x14001aeb8`
- `0x140020ff0`
- `0x140021658`
- `0x14002cba4`
- `0x140031010`

## string_xrefs

- `0x14002cbf2`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002cd2a`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002cda5`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002cbe1`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates`
- `0x14002cd17`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, __int128 *, _OWORD *, __int64); // rbx
  int v4; // r8d
  volatile signed __int32 *v5; // r15
  __int64 v6; // rdi
  __int64 *v7; // rbx
  __int64 *v8; // r14
  __int64 v9; // r8
  __int64 (__fastcall *v10)(__int64, _QWORD *); // r9
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rax
  int v13; // eax
  unsigned int v14; // esi
  __int64 v15; // r14
  void (__fastcall *v16)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  _QWORD v21[10]; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v22[32]; // [rsp+98h] [rbp-31h] BYREF
  _OWORD v23[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v24; // [rsp+D8h] [rbp+Fh] BYREF
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *v25; // [rsp+E8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, __int128 *, _OWORD *, __int64))(*(_QWORD *)v2 + 40LL);
  std::string::string(
    v23,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates");
  std::string::string(
    &v24,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, &v24, v23, 461);
  std::string::~string(&v24);
  std::string::~string(v23);
  v23[0] = 0;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 49);
  if ( v5 )
  {
    v6 = *((_QWORD *)this + 48);
    *(_QWORD *)&v23[0] = v6;
    *((_QWORD *)&v23[0] + 1) = v5;
    _InterlockedIncrement(v5 + 3);
  }
  else
  {
    v5 = (volatile signed __int32 *)*((_QWORD *)&v23[0] + 1);
    v6 = *(_QWORD *)&v23[0];
  }
  v7 = (__int64 *)*((_QWORD *)this + 23);
  v8 = (__int64 *)*((_QWORD *)this + 24);
  while ( 1 )
  {
    if ( v7 == v8 )
    {
      v15 = *((_QWORD *)this + 47);
      v16 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v15 + 72LL);
      v17 = std::string::string(&v24, "hr = 0x%x", v4);
      v21[8] = v22;
      v18 = std::string::string(
              v22,
              "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetupMonitorsForUpdates");
      v19 = std::string::string(
              v21,
              "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
      v16(v15, v19, v18, 475, v17, this, 0);
      if ( v5 )
        std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v5);
      return 0;
    }
    v9 = *v7;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)*v7 + 8LL);
    v11 = 0;
    v12 = 0;
    if ( v5 )
    {
      v11 = v6;
      v12 = v5;
      _InterlockedIncrement(v5 + 3);
    }
    v25 = this;
    v21[0] = &std::_Func_impl_no_alloc<_lambda_ecc2325014fbde5bad1d930cbdcfca6f_,void,>::`vftable';
    v21[1] = v11;
    v21[2] = v12;
    v24 = 0;
    v21[3] = this;
    v21[7] = v21;
    v13 = v10(v9, v21);
    v14 = v13;
    if ( v13 < 0 )
      break;
    v7 += 2;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D9,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
    (const char *)(unsigned int)v13,
    (int)this);
  if ( v5 )
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v5);
  return v14;
}

```

## disassembly

```asm
0x14002cba4  mov     [rsp-8+arg_8], rbx
0x14002cba9  mov     [rsp-8+arg_10], rsi
0x14002cbae  push    rbp
0x14002cbaf  push    rdi
0x14002cbb0  push    r13
0x14002cbb2  push    r14
0x14002cbb4  push    r15
0x14002cbb6  lea     rbp, [rsp-37h]
0x14002cbbb  sub     rsp, 100h
0x14002cbc2  mov     rax, cs:__security_cookie
0x14002cbc9  xor     rax, rsp
0x14002cbcc  mov     [rbp+57h+var_28], rax
0x14002cbd0  mov     r13, rcx
0x14002cbd3  mov     rdi, [rcx+178h]
0x14002cbda  mov     rax, [rdi]
0x14002cbdd  mov     rbx, [rax+28h]
0x14002cbe1  lea     rdx, aMicrosoftVoice; "Microsoft::VoiceAgentServices::Windows:"...
0x14002cbe8  lea     rcx, [rbp+57h+var_68]
0x14002cbec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cbf1  nop
0x14002cbf2  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002cbf9  lea     rcx, [rbp+57h+var_48]
0x14002cbfd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cc02  nop
0x14002cc03  mov     [rsp+120h+var_100], r13
0x14002cc08  mov     r9d, 1CDh
0x14002cc0e  lea     r8, [rbp+57h+var_68]
0x14002cc12  lea     rdx, [rbp+57h+var_48]
0x14002cc16  mov     rcx, rdi
0x14002cc19  mov     rax, rbx
0x14002cc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cc21  nop
0x14002cc22  lea     rcx, [rbp+57h+var_48]
0x14002cc26  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002cc2b  nop
0x14002cc2c  lea     rcx, [rbp+57h+var_68]
0x14002cc30  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002cc35  xorps   xmm0, xmm0
0x14002cc38  movdqu  [rbp+57h+var_68], xmm0
0x14002cc3d  mov     r15, [r13+188h]
0x14002cc44  test    r15, r15
0x14002cc47  jz      short loc_14002CC5F
0x14002cc49  mov     rdi, [r13+180h]
0x14002cc50  mov     qword ptr [rbp+57h+var_68], rdi
0x14002cc54  mov     qword ptr [rbp+57h+var_68+8], r15
0x14002cc58  lock inc dword ptr [r15+0Ch]
0x14002cc5d  jmp     short loc_14002CC67
0x14002cc5f  mov     r15, qword ptr [rbp+57h+var_68+8]
0x14002cc63  mov     rdi, qword ptr [rbp+57h+var_68]
0x14002cc67  mov     rbx, [r13+0B8h]
0x14002cc6e  mov     r14, [r13+0C0h]
0x14002cc75  jmp     short loc_14002CCE0
0x14002cc77  mov     r8, [rbx]
0x14002cc7a  mov     rax, [r8]
0x14002cc7d  mov     r9, [rax+8]
0x14002cc81  xor     ecx, ecx
0x14002cc83  xor     eax, eax
0x14002cc85  test    r15, r15
0x14002cc88  jz      short loc_14002CC95
0x14002cc8a  mov     rcx, rdi
0x14002cc8d  mov     rax, r15
0x14002cc90  lock inc dword ptr [r15+0Ch]
0x14002cc95  mov     [rbp+57h+var_38], r13
0x14002cc99  lea     rdx, ??_7?$_Func_impl_no_alloc@V_lambda_ecc2325014fbde5bad1d930cbdcfca6f_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_ecc2325014fbde5bad1d930cbdcfca6f_,void,>::`vftable'
0x14002cca0  mov     [rsp+120h+var_D8], rdx
0x14002cca5  mov     [rbp+57h+var_D0], rcx
0x14002cca9  mov     [rbp+57h+var_C8], rax
0x14002ccad  xorps   xmm0, xmm0
0x14002ccb0  movdqu  [rbp+57h+var_48], xmm0
0x14002ccb5  mov     [rbp+57h+var_C0], r13
0x14002ccb9  lea     rax, [rsp+120h+var_D8]
0x14002ccbe  mov     [rbp+57h+var_A0], rax
0x14002ccc2  lea     rdx, [rsp+120h+var_D8]
0x14002ccc7  mov     rcx, r8
0x14002ccca  mov     rax, r9
0x14002cccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ccd2  mov     esi, eax
0x14002ccd4  test    eax, eax
0x14002ccd6  js      loc_14002CD9E
0x14002ccdc  add     rbx, 10h
0x14002cce0  cmp     rbx, r14
0x14002cce3  jnz     short loc_14002CC77
0x14002cce5  mov     r14, [r13+178h]
0x14002ccec  mov     rax, [r14]
0x14002ccef  mov     rsi, [rax+48h]
0x14002ccf3  lea     rax, [rbp+57h+var_48]
0x14002ccf7  mov     [rsp+120h+var_E0], rax
0x14002ccfc  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002cd03  lea     rcx, [rbp+57h+var_48]
0x14002cd07  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cd0c  mov     rdi, rax
0x14002cd0f  lea     rax, [rbp+57h+var_88]
0x14002cd13  mov     [rbp+57h+var_98], rax
0x14002cd17  lea     rdx, aMicrosoftVoice; "Microsoft::VoiceAgentServices::Windows:"...
0x14002cd1e  lea     rcx, [rbp+57h+var_88]
0x14002cd22  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cd27  mov     rbx, rax
0x14002cd2a  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002cd31  lea     rcx, [rsp+120h+var_D8]
0x14002cd36  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002cd3b  nop
0x14002cd3c  mov     [rsp+120h+var_F0], 0
0x14002cd45  mov     [rsp+120h+var_F8], r13
0x14002cd4a  mov     [rsp+120h+var_100], rdi
0x14002cd4f  mov     r9d, 1DBh
0x14002cd55  mov     r8, rbx
0x14002cd58  mov     rdx, rax
0x14002cd5b  mov     rcx, r14
0x14002cd5e  mov     rax, rsi
0x14002cd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cd66  nop
0x14002cd67  test    r15, r15
0x14002cd6a  jz      short loc_14002CD74
0x14002cd6c  mov     rcx, r15; this
0x14002cd6f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x14002cd74  xor     eax, eax
0x14002cd76  mov     rcx, [rbp+57h+var_28]
0x14002cd7a  xor     rcx, rsp; StackCookie
0x14002cd7d  call    __security_check_cookie
0x14002cd82  lea     r11, [rsp+120h+var_20]
0x14002cd8a  mov     rbx, [r11+38h]
0x14002cd8e  mov     rsi, [r11+40h]
0x14002cd92  mov     rsp, r11
0x14002cd95  pop     r15
0x14002cd97  pop     r14
0x14002cd99  pop     r13
0x14002cd9b  pop     rdi
0x14002cd9c  pop     rbp
0x14002cd9d  retn
0x14002cd9e  mov     rcx, [rbp+5Fh]; this
0x14002cda2  mov     r9d, esi; char *
0x14002cda5  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002cdac  mov     edx, 1D9h; void *
0x14002cdb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002cdb6  nop
0x14002cdb7  test    r15, r15
0x14002cdba  jz      short loc_14002CDC4
0x14002cdbc  mov     rcx, r15; this
0x14002cdbf  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x14002cdc4  mov     eax, esi
0x14002cdc6  jmp     short loc_14002CD76
```

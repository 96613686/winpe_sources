# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase(void)

- ea: `0x140028724`
- end: `0x1400288e1`
- name: `??1AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAA@XZ`
- size: `445`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400274c4`
- `0x140028af0`
- `0x1400306b3`

## callees

- `0x140012878`
- `0x140012da4`
- `0x14001ae80`
- `0x14001aeb8`
- `0x1400208bc`
- `0x140020ff0`
- `0x140021a78`
- `0x140023b58`
- `0x140028724`
- `0x140031010`

## string_xrefs

- `0x14002876b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x1400287f3`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140028757`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase`
- `0x1400287df`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase`

## pseudocode

```c
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 **v6; // rdi
  __int64 **i; // rbx
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rsi
  void (__fastcall *v11)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // rcx
  std::_Ref_count_base *v16; // rcx
  _BYTE v17[32]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v18[56]; // [rsp+50h] [rbp-68h] BYREF
  __int64 v19; // [rsp+88h] [rbp-30h]

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'};
  *((_QWORD *)this + 1) = &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'};
  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v2 + 96LL);
  v4 = std::string::string(
         v17,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase");
  v5 = std::string::string(
         v18,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v3(v2, v5, v4, 28, this);
  v6 = (__int64 **)*((_QWORD *)this + 24);
  for ( i = (__int64 **)*((_QWORD *)this + 23); i != v6; i += 2 )
  {
    v8 = *i;
    v9 = **i;
    v19 = 0;
    (*(void (__fastcall **)(__int64 *, _BYTE *))(v9 + 8))(v8, v18);
  }
  v10 = *((_QWORD *)this + 47);
  v11 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v10 + 104LL);
  v12 = std::string::string(
          v18,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::~AgentActivationSettingBase");
  v13 = std::string::string(
          v17,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v11(v10, v13, v12, 33, this);
  v14 = (std::_Ref_count_base *)*((_QWORD *)this + 49);
  if ( v14 )
    std::_Ref_count_base::_Decwref(v14);
  std::wstring::_Tidy_deallocate((char *)this + 344);
  std::wstring::_Tidy_deallocate((char *)this + 272);
  std::_Func_class<void,>::_Tidy((char *)this + 208);
  v15 = *((_QWORD *)this + 23);
  if ( v15 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>>(
      v15,
      *((_QWORD *)this + 24));
    std::_Deallocate<16>(
      *((_QWORD *)this + 23),
      (*((_QWORD *)this + 25) - *((_QWORD *)this + 23)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 23) = 0;
    *((_QWORD *)this + 24) = 0;
    *((_QWORD *)this + 25) = 0;
  }
  Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration::~AgentConfiguration((Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *)((char *)this + 32));
  v16 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  *((_QWORD *)this + 1) = &Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting::`vftable';
  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView::`vftable';
}

```

## disassembly

```asm
0x140028724  push    rbx
0x140028726  push    rsi
0x140028727  push    rdi
0x140028728  push    r14
0x14002872a  sub     rsp, 98h
0x140028731  mov     r14, rcx
0x140028734  lea     rax, ??_7AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSettingView@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView'}
0x14002873b  mov     [rcx], rax
0x14002873e  lea     rax, ??_7AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@6BIAgentActivationSetting@1234@@; const Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::`vftable'{for `Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting'}
0x140028745  mov     [rcx+8], rax
0x140028749  mov     rsi, [rcx+178h]
0x140028750  mov     rax, [rsi]
0x140028753  mov     rdi, [rax+60h]
0x140028757  lea     rdx, aMicrosoftVoice_0; "Microsoft::VoiceAgentServices::Windows:"...
0x14002875e  lea     rcx, [rsp+0B8h+var_88]
0x140028763  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028768  mov     rbx, rax
0x14002876b  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140028772  lea     rcx, [rsp+0B8h+var_68]
0x140028777  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002877c  mov     [rsp+0B8h+var_98], r14
0x140028781  mov     r9d, 1Ch
0x140028787  mov     r8, rbx
0x14002878a  mov     rdx, rax
0x14002878d  mov     rcx, rsi
0x140028790  mov     rax, rdi
0x140028793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028798  mov     rdi, [r14+0C0h]
0x14002879f  mov     rbx, [r14+0B8h]
0x1400287a6  jmp     short loc_1400287CC
0x1400287a8  mov     rcx, [rbx]
0x1400287ab  mov     rax, [rcx]
0x1400287ae  mov     [rsp+0B8h+var_30], 0
0x1400287ba  lea     rdx, [rsp+0B8h+var_68]
0x1400287bf  mov     rax, [rax+8]
0x1400287c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400287c8  add     rbx, 10h
0x1400287cc  cmp     rbx, rdi
0x1400287cf  jnz     short loc_1400287A8
0x1400287d1  mov     rsi, [r14+178h]
0x1400287d8  mov     rax, [rsi]
0x1400287db  mov     rdi, [rax+68h]
0x1400287df  lea     rdx, aMicrosoftVoice_0; "Microsoft::VoiceAgentServices::Windows:"...
0x1400287e6  lea     rcx, [rsp+0B8h+var_68]
0x1400287eb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400287f0  mov     rbx, rax
0x1400287f3  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400287fa  lea     rcx, [rsp+0B8h+var_88]
0x1400287ff  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028804  mov     [rsp+0B8h+var_98], r14
0x140028809  mov     r9d, 21h ; '!'
0x14002880f  mov     r8, rbx
0x140028812  mov     rdx, rax
0x140028815  mov     rcx, rsi
0x140028818  mov     rax, rdi
0x14002881b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028820  mov     rcx, [r14+188h]; this
0x140028827  test    rcx, rcx
0x14002882a  jz      short loc_140028831
0x14002882c  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x140028831  lea     rcx, [r14+158h]
0x140028838  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002883d  lea     rcx, [r14+110h]
0x140028844  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140028849  lea     rcx, [r14+0D0h]
0x140028850  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x140028855  mov     rcx, [r14+0B8h]
0x14002885c  test    rcx, rcx
0x14002885f  jz      short loc_1400288A8
0x140028861  mov     rdx, [r14+0C0h]
0x140028868  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VIAgentSettingMonitor@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>>>(std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> *,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor> * const,std::allocator<std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentSettingMonitor>> &)
0x14002886d  mov     rcx, [r14+0B8h]
0x140028874  mov     rdx, [r14+0C8h]
0x14002887b  sub     rdx, rcx
0x14002887e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x140028882  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140028887  mov     qword ptr [r14+0B8h], 0
0x140028892  mov     qword ptr [r14+0C0h], 0
0x14002889d  mov     qword ptr [r14+0C8h], 0
0x1400288a8  lea     rcx, [r14+20h]; this
0x1400288ac  call    ??1AgentConfiguration@Settings@Windows@VoiceAgentServices@Microsoft@@QEAA@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentConfiguration::~AgentConfiguration(void)
0x1400288b1  mov     rcx, [r14+18h]; this
0x1400288b5  test    rcx, rcx
0x1400288b8  jz      short loc_1400288BF
0x1400288ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400288bf  lea     rax, ??_7IAgentActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSetting::`vftable'
0x1400288c6  mov     [r14+8], rax
0x1400288ca  lea     rax, ??_7IAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView::`vftable'
0x1400288d1  mov     [r14], rax
0x1400288d4  add     rsp, 98h
0x1400288db  pop     r14
0x1400288dd  pop     rdi
0x1400288de  pop     rsi
0x1400288df  pop     rbx
0x1400288e0  retn
```

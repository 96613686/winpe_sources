# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager(void)

- ea: `0x14002118c`
- end: `0x140021357`
- name: `??0AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@AEAA@XZ`
- size: `459`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400220a8`

## callees

- `0x140003320`
- `0x140020ff0`
- `0x140022404`
- `0x140023884`
- `0x140031010`

## string_xrefs

- `0x1400212b2`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager`
- `0x140021308`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager`
- `0x1400212c5`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x14002131b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)
{
  char *v2; // rbx
  _QWORD *v3; // rax
  struct Microsoft::VoiceAgentServices::ILogger *Instance; // rsi
  void (__fastcall *v5)(struct Microsoft::VoiceAgentServices::ILogger *, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *); // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rsi
  void (__fastcall *v9)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *); // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  _BYTE v13[32]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-20h] BYREF

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  v2 = (char *)this + 88;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  v3 = operator new(0x40u);
  *v3 = v3;
  v3[1] = v3;
  *((_QWORD *)v2 + 1) = v3;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 6) = 7;
  *((_QWORD *)v2 + 7) = 8;
  *(_DWORD *)v2 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>>>>>::_Assign_grow(
    v2 + 24,
    16,
    *((_QWORD *)v2 + 1));
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_OWORD *)this + 19) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 7;
  *((_WORD *)this + 152) = 0;
  *((_OWORD *)this + 21) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 7;
  *((_WORD *)this + 168) = 0;
  *((_BYTE *)this + 369) = 0;
  Instance = Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance();
  *((_QWORD *)this + 47) = Instance;
  v5 = *(void (__fastcall **)(struct Microsoft::VoiceAgentServices::ILogger *, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *))(*(_QWORD *)Instance + 80LL);
  v6 = std::string::string(
         v13,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager");
  v7 = std::string::string(
         v14,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v5(Instance, v7, v6, 47, this);
  v8 = *((_QWORD *)this + 47);
  v9 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *))(*(_QWORD *)v8 + 88LL);
  v10 = std::string::string(
          v14,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::AgentActivationSettingManager");
  v11 = std::string::string(
          v13,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v9(v8, v11, v10, 48, this);
  return this;
}

```

## disassembly

```asm
0x14002118c  mov     [rsp-28h+arg_0], rcx
0x140021191  push    rbp
0x140021192  push    rbx
0x140021193  push    rsi
0x140021194  push    rdi
0x140021195  push    r14
0x140021197  mov     rbp, rsp
0x14002119a  sub     rsp, 70h
0x14002119e  mov     r14, rcx
0x1400211a1  xor     esi, esi
0x1400211a3  mov     [rcx+8], rsi
0x1400211a7  mov     [rcx+10h], rsi
0x1400211ab  lea     rax, ??_7AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::`vftable'
0x1400211b2  mov     [rcx], rax
0x1400211b5  mov     [rcx+18h], rsi
0x1400211b9  mov     [rcx+20h], rsi
0x1400211bd  mov     [rcx+28h], rsi
0x1400211c1  mov     [rcx+30h], rsi
0x1400211c5  mov     [rcx+38h], rsi
0x1400211c9  mov     [rcx+40h], rsi
0x1400211cd  mov     [rcx+48h], rsi
0x1400211d1  mov     [rcx+50h], rsi
0x1400211d5  lea     rbx, [rcx+58h]
0x1400211d9  mov     [rbp+arg_8], rbx
0x1400211dd  mov     [rbx], esi
0x1400211df  mov     [rbx+8], rsi
0x1400211e3  mov     [rbx+10h], rsi
0x1400211e7  lea     ecx, [rsi+40h]; Size
0x1400211ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400211ef  mov     [rax], rax
0x1400211f2  mov     [rax+8], rax
0x1400211f6  mov     [rbx+8], rax
0x1400211fa  lea     rcx, [rbx+18h]
0x1400211fe  mov     [rcx], rsi
0x140021201  mov     [rcx+8], rsi
0x140021205  mov     [rcx+10h], rsi
0x140021209  lea     edi, [rsi+7]
0x14002120c  mov     [rbx+30h], rdi
0x140021210  mov     qword ptr [rbx+38h], 8
0x140021218  mov     dword ptr [rbx], 3F800000h
0x14002121e  mov     r8, [rbx+8]
0x140021222  lea     edx, [rsi+10h]
0x140021225  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>>>)
0x14002122a  nop
0x14002122b  mov     [r14+98h], rsi
0x140021232  mov     [r14+0A0h], rsi
0x140021239  mov     [r14+0E0h], rsi
0x140021240  mov     [r14+120h], rsi
0x140021247  mov     [r14+128h], rsi
0x14002124e  xorps   xmm0, xmm0
0x140021251  movups  xmmword ptr [r14+130h], xmm0
0x140021259  mov     [r14+140h], rsi
0x140021260  mov     [r14+148h], rdi
0x140021267  mov     [r14+130h], si
0x14002126f  movups  xmmword ptr [r14+150h], xmm0
0x140021277  mov     [r14+160h], rsi
0x14002127e  mov     [r14+168h], rdi
0x140021285  mov     [r14+150h], si
0x14002128d  mov     [r14+171h], sil
0x140021294  call    ?GetInstance@SettingLogger@Settings@Windows@VoiceAgentServices@Microsoft@@SAAEAVILogger@45@XZ; Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::GetInstance(void)
0x140021299  mov     rsi, rax
0x14002129c  mov     [r14+178h], rax
0x1400212a3  mov     rcx, [rax]
0x1400212a6  mov     rdi, [rcx+50h]
0x1400212aa  lea     rax, [rbp+var_40]
0x1400212ae  mov     [rbp+arg_8], rax
0x1400212b2  lea     rdx, aMicrosoftVoice_55; "Microsoft::VoiceAgentServices::Windows:"...
0x1400212b9  lea     rcx, [rbp+var_40]
0x1400212bd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400212c2  mov     rbx, rax
0x1400212c5  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400212cc  lea     rcx, [rbp+var_20]
0x1400212d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400212d5  nop
0x1400212d6  mov     [rsp+70h+var_50], r14
0x1400212db  mov     r9d, 2Fh ; '/'
0x1400212e1  mov     r8, rbx
0x1400212e4  mov     rdx, rax
0x1400212e7  mov     rcx, rsi
0x1400212ea  mov     rax, rdi
0x1400212ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400212f2  mov     rsi, [r14+178h]
0x1400212f9  mov     rax, [rsi]
0x1400212fc  mov     rdi, [rax+58h]
0x140021300  lea     rax, [rbp+var_20]
0x140021304  mov     [rbp+arg_8], rax
0x140021308  lea     rdx, aMicrosoftVoice_55; "Microsoft::VoiceAgentServices::Windows:"...
0x14002130f  lea     rcx, [rbp+var_20]
0x140021313  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140021318  mov     rbx, rax
0x14002131b  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140021322  lea     rcx, [rbp+var_40]
0x140021326  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002132b  nop
0x14002132c  mov     [rsp+70h+var_50], r14
0x140021331  mov     r9d, 30h ; '0'
0x140021337  mov     r8, rbx
0x14002133a  mov     rdx, rax
0x14002133d  mov     rcx, rsi
0x140021340  mov     rax, rdi
0x140021343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021348  nop
0x140021349  mov     rax, r14
0x14002134c  add     rsp, 70h
0x140021350  pop     r14
0x140021352  pop     rdi
0x140021353  pop     rsi
0x140021354  pop     rbx
0x140021355  pop     rbp
0x140021356  retn
```

# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::~AgentActivationSettingManager(void)

- ea: `0x1400217f4`
- end: `0x140021a44`
- name: `??1AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@UEAA@XZ`
- size: `592`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140021f80`

## callees

- `0x140012878`
- `0x140012da4`
- `0x14001ae80`
- `0x14001aeb8`
- `0x140020884`
- `0x140020ff0`
- `0x140021534`
- `0x140021768`
- `0x1400217f4`
- `0x140023b58`
- `0x140024258`
- `0x140031010`

## string_xrefs

- `0x14002181f`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::~AgentActivationSettingManager`
- `0x140021908`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::~AgentActivationSettingManager`
- `0x140021833`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`
- `0x14002191c`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingmanager.cpp`

## pseudocode

```c
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::~AgentActivationSettingManager(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *this)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 *v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rdi
  _QWORD *i; // rbx
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rsi
  void (__fastcall *v15)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *); // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  std::_Ref_count_base *v18; // rcx
  std::_Ref_count_base *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  std::_Ref_count_base *v22; // rcx
  _BYTE v23[32]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v24[56]; // [rsp+50h] [rbp-78h] BYREF
  __int64 v25; // [rsp+88h] [rbp-40h]

  *(_QWORD *)this = &Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::`vftable';
  v2 = *((_QWORD *)this + 47);
  v3 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *))(*(_QWORD *)v2 + 96LL);
  v4 = std::string::string(
         v23,
         "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::~AgentActivationSettingManager");
  v5 = std::string::string(
         v24,
         "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v3(v2, v5, v4, 53, this);
  *((_BYTE *)this + 369) = 0;
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    (char *)this + 296,
    0);
  v6 = (__int64 *)*((_QWORD *)this + 19);
  if ( v6 )
  {
    v7 = *v6;
    v25 = 0;
    (*(void (__fastcall **)(__int64 *, _BYTE *))(v7 + 24))(v6, v24);
  }
  v8 = (__int64 *)*((_QWORD *)this + 9);
  if ( v8 )
  {
    v9 = *v8;
    v25 = 0;
    (*(void (__fastcall **)(__int64 *, _BYTE *))(v9 + 56))(v8, v24);
  }
  v10 = (_QWORD *)*((_QWORD *)this + 12);
  for ( i = (_QWORD *)*v10; i != v10; i = (_QWORD *)*i )
  {
    v12 = (__int64 *)i[6];
    v13 = *v12;
    v25 = 0;
    (*(void (__fastcall **)(__int64 *, _BYTE *))(v13 + 56))(v12, v24);
  }
  v14 = *((_QWORD *)this + 47);
  v15 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager *))(*(_QWORD *)v14 + 104LL);
  v16 = std::string::string(
          v24,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::~AgentActivationSettingManager");
  v17 = std::string::string(
          v23,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingmanager.cpp");
  v15(v14, v17, v16, 71, this);
  std::wstring::_Tidy_deallocate((char *)this + 336);
  std::wstring::_Tidy_deallocate((char *)this + 304);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>((char *)this + 296);
  std::_Func_class<void,>::_Tidy((char *)this + 232);
  std::_Func_class<void,>::_Tidy((char *)this + 168);
  v18 = (std::_Ref_count_base *)*((_QWORD *)this + 20);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>,0>>((char *)this + 88);
  v19 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  v20 = *((_QWORD *)this + 6);
  if ( v20 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v20, *((_QWORD *)this + 7));
    std::_Deallocate<16>(*((_QWORD *)this + 6), (*((_QWORD *)this + 8) - *((_QWORD *)this + 6)) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
  }
  v21 = *((_QWORD *)this + 3);
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v21, *((_QWORD *)this + 4));
    std::_Deallocate<16>(*((_QWORD *)this + 3), (*((_QWORD *)this + 5) - *((_QWORD *)this + 3)) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  v22 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v22 )
    std::_Ref_count_base::_Decwref(v22);
}

```

## disassembly

```asm
0x1400217f4  push    rbx
0x1400217f6  push    rbp
0x1400217f7  push    rsi
0x1400217f8  push    rdi
0x1400217f9  push    r14
0x1400217fb  push    r15
0x1400217fd  sub     rsp, 98h
0x140021804  mov     r14, rcx
0x140021807  lea     rax, ??_7AgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@6B@; const Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager::`vftable'
0x14002180e  mov     [rcx], rax
0x140021811  mov     rsi, [rcx+178h]
0x140021818  mov     rax, [rsi]
0x14002181b  mov     rdi, [rax+60h]
0x14002181f  lea     rdx, aMicrosoftVoice_16; "Microsoft::VoiceAgentServices::Windows:"...
0x140021826  lea     rcx, [rsp+0C8h+var_98]
0x14002182b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140021830  mov     rbx, rax
0x140021833  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002183a  lea     rcx, [rsp+0C8h+var_78]
0x14002183f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140021844  mov     [rsp+0C8h+var_A8], r14
0x140021849  mov     r9d, 35h ; '5'
0x14002184f  mov     r8, rbx
0x140021852  mov     rdx, rax
0x140021855  mov     rcx, rsi
0x140021858  mov     rax, rdi
0x14002185b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021860  mov     byte ptr [r14+171h], 0
0x140021868  lea     r15, [r14+128h]
0x14002186f  xor     edx, edx
0x140021871  mov     rcx, r15
0x140021874  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x140021879  mov     rcx, [r14+98h]
0x140021880  test    rcx, rcx
0x140021883  jz      short loc_1400218A2
0x140021885  mov     rax, [rcx]
0x140021888  mov     [rsp+0C8h+var_40], 0
0x140021894  lea     rdx, [rsp+0C8h+var_78]
0x140021899  mov     rax, [rax+18h]
0x14002189d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400218a2  mov     rcx, [r14+48h]
0x1400218a6  test    rcx, rcx
0x1400218a9  jz      short loc_1400218C8
0x1400218ab  mov     rax, [rcx]
0x1400218ae  mov     [rsp+0C8h+var_40], 0
0x1400218ba  lea     rdx, [rsp+0C8h+var_78]
0x1400218bf  mov     rax, [rax+38h]
0x1400218c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400218c8  mov     rdi, [r14+60h]
0x1400218cc  mov     rbx, [rdi]
0x1400218cf  cmp     rbx, rdi
0x1400218d2  jz      short loc_1400218FA
0x1400218d4  mov     rcx, [rbx+30h]
0x1400218d8  mov     rax, [rcx]
0x1400218db  mov     [rsp+0C8h+var_40], 0
0x1400218e7  lea     rdx, [rsp+0C8h+var_78]
0x1400218ec  mov     rax, [rax+38h]
0x1400218f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400218f5  mov     rbx, [rbx]
0x1400218f8  jmp     short loc_1400218CF
0x1400218fa  mov     rsi, [r14+178h]
0x140021901  mov     rax, [rsi]
0x140021904  mov     rdi, [rax+68h]
0x140021908  lea     rdx, aMicrosoftVoice_16; "Microsoft::VoiceAgentServices::Windows:"...
0x14002190f  lea     rcx, [rsp+0C8h+var_78]
0x140021914  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140021919  mov     rbx, rax
0x14002191c  lea     rdx, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140021923  lea     rcx, [rsp+0C8h+var_98]
0x140021928  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002192d  mov     [rsp+0C8h+var_A8], r14
0x140021932  mov     r9d, 47h ; 'G'
0x140021938  mov     r8, rbx
0x14002193b  mov     rdx, rax
0x14002193e  mov     rcx, rsi
0x140021941  mov     rax, rdi
0x140021944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021949  lea     rcx, [r14+150h]
0x140021950  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140021955  lea     rcx, [r14+130h]
0x14002195c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140021961  mov     rcx, r15
0x140021964  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x140021969  lea     rcx, [r14+0E8h]
0x140021970  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x140021975  lea     rcx, [r14+0A8h]
0x14002197c  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x140021981  mov     rcx, [r14+0A0h]; this
0x140021988  test    rcx, rcx
0x14002198b  jz      short loc_140021992
0x14002198d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140021992  lea     rcx, [r14+58h]
0x140021996  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VIAgentActivationSettingView@Settings@Windows@VoiceAgentServices@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::IAgentActivationSettingView>>>,0>>(void)
0x14002199b  mov     rcx, [r14+50h]; this
0x14002199f  test    rcx, rcx
0x1400219a2  jz      short loc_1400219A9
0x1400219a4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400219a9  mov     rcx, [r14+30h]
0x1400219ad  test    rcx, rcx
0x1400219b0  jz      short loc_1400219E7
0x1400219b2  mov     rdx, [r14+38h]
0x1400219b6  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1400219bb  mov     rcx, [r14+30h]
0x1400219bf  mov     rdx, [r14+40h]
0x1400219c3  sub     rdx, rcx
0x1400219c6  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1400219ca  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400219cf  mov     qword ptr [r14+30h], 0
0x1400219d7  mov     qword ptr [r14+38h], 0
0x1400219df  mov     qword ptr [r14+40h], 0
0x1400219e7  mov     rcx, [r14+18h]
0x1400219eb  test    rcx, rcx
0x1400219ee  jz      short loc_140021A25
0x1400219f0  mov     rdx, [r14+20h]
0x1400219f4  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1400219f9  mov     rcx, [r14+18h]
0x1400219fd  mov     rdx, [r14+28h]
0x140021a01  sub     rdx, rcx
0x140021a04  and     rdx, 0FFFFFFFFFFFFFFE0h
0x140021a08  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140021a0d  mov     qword ptr [r14+18h], 0
0x140021a15  mov     qword ptr [r14+20h], 0
0x140021a1d  mov     qword ptr [r14+28h], 0
0x140021a25  mov     rcx, [r14+10h]; this
0x140021a29  test    rcx, rcx
0x140021a2c  jz      short loc_140021A34
0x140021a2e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x140021a33  nop
0x140021a34  add     rsp, 98h
0x140021a3b  pop     r15
0x140021a3d  pop     r14
0x140021a3f  pop     rdi
0x140021a40  pop     rsi
0x140021a41  pop     rbp
0x140021a42  pop     rbx
0x140021a43  retn
```

# Windows::Internal::Spelling::RoamingDictionaryManager::StartRoaming(void)

- ea: `0x1800807d0`
- end: `0x180080b3b`
- name: `?StartRoaming@RoamingDictionaryManager@Spelling@Internal@Windows@@UEAAJXZ`
- size: `875`
- prototype: `__int64 __fastcall(Windows::Internal::Spelling::RoamingDictionaryManager *__hidden this)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18003cfbc`
- `0x180040cc4`
- `0x1800411b4`
- `0x1800418a4`
- `0x180041d5c`
- `0x180042f6c`
- `0x180044a24`
- `0x180044a88`
- `0x180044c28`
- `0x180045080`
- `0x180046ef8`
- `0x180050618`
- `0x180053530`
- `0x180054c38`
- `0x180057f1c`
- `0x18005b314`
- `0x180061320`
- `0x180065cc0`
- `0x180070530`
- `0x1800705d8`
- `0x18007b668`
- `0x18007cc90`
- `0x180080154`
- `0x1800807d0`
- `0x1800829f0`
- `0x180082b24`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180080aa8`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180080aa8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180080a17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180080a5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180080a17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180080a5e`
- `ntdll!RtlQueryWnfStateData` at `0x180080922`
- `ntdll!RtlQueryWnfStateData` at `0x180080922`

## string_xrefs

- `0x180080b05`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180080b16`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180080b28`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Spelling::RoamingDictionaryManager::StartRoaming(
        Windows::Internal::Spelling::RoamingDictionaryManager *this)
{
  _QWORD *v2; // rsi
  __int64 *v3; // rdx
  __int64 *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  std::_Ref_count_base *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  std::_Ref_count_base *v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // rdx
  Windows::Internal::Spelling::RoamingDictionaryManager *wnf; // rax
  Windows::Internal::Spelling::RoamingDictionaryManager *v16; // rsi
  regex::detail **v17; // rbx
  regex::detail *v18; // r15
  regex::detail *v19; // r14
  const struct regex::detail::charset *v20; // rdx
  char IsEnabled; // al
  __int64 *v22; // rax
  __int64 v23; // rdx
  PVOID *v24; // rbx
  Windows::Internal::Spelling **v25; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v27; // rdx
  __int64 v28; // r8
  const char *v29; // r9
  PTP_TIMER v30; // rax
  const char *v31; // r9
  const char *v32; // r9
  __int64 result; // rax
  char v34; // [rsp+30h] [rbp-258h] BYREF
  char v35; // [rsp+31h] [rbp-257h] BYREF
  PVOID pv; // [rsp+38h] [rbp-250h] BYREF
  __int64 v37; // [rsp+40h] [rbp-248h] BYREF
  std::_Ref_count_base *v38; // [rsp+48h] [rbp-240h]
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-238h] BYREF
  std::_Ref_count_base *v40; // [rsp+58h] [rbp-230h]
  _BYTE *v41; // [rsp+60h] [rbp-228h] BYREF
  std::_Ref_count_base *v42; // [rsp+68h] [rbp-220h]
  _BYTE v43[128]; // [rsp+70h] [rbp-218h] BYREF
  _QWORD v44[42]; // [rsp+F0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v44,
    "ActivityStartRoaming");
  try
  {
    v44[0] = &SpellingTelemetry::ActivityStartRoaming::`vftable';
    v2 = (_QWORD *)((char *)this + 152);
    if ( !*((_QWORD *)this + 19) )
    {
      v34 = 1;
      v35 = 1;
      v3 = std::make_shared<Windows::Internal::Spelling::TaskConsumer,bool,bool>(&v37, (bool *)&v35, (bool *)&v34);
      v4 = std::make_shared<Windows::Internal::Spelling::TaskDispatcher,std::shared_ptr<Windows::Internal::Spelling::TaskConsumer>>(
             &v39,
             v3);
      v5 = *v4;
      v6 = v4[1];
      *v4 = 0;
      v4[1] = 0;
      *v2 = v5;
      v7 = (std::_Ref_count_base *)*((_QWORD *)this + 20);
      *((_QWORD *)this + 20) = v6;
      if ( v7 )
        std::_Ref_count_base::_Decref(v7);
      if ( v40 )
        std::_Ref_count_base::_Decref(v40);
      if ( v38 )
        std::_Ref_count_base::_Decref(v38);
      v8 = *((_QWORD *)this + 20);
      if ( v8 )
      {
        v9 = *v2;
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 12));
      }
      else
      {
        v8 = 0;
        v9 = 0;
      }
      *(_QWORD *)&Windows::Internal::Spelling::TaskDispatcher::s_weakLinkedInstance = v9;
      v10 = (std::_Ref_count_base *)*((_QWORD *)&Windows::Internal::Spelling::TaskDispatcher::s_weakLinkedInstance + 1);
      *((_QWORD *)&Windows::Internal::Spelling::TaskDispatcher::s_weakLinkedInstance + 1) = v8;
      if ( v10 )
        std::_Ref_count_base::_Decwref(v10);
    }
    std::make_shared<Windows::Internal::Spelling::TaskItem,>(&v41);
    *v41 = 1;
    (*(void (__fastcall **)(_QWORD, _BYTE **))(*(_QWORD *)*v2 + 8LL))(*v2, &v41);
    if ( !*((_BYTE *)this + 64) )
    {
      LODWORD(pv) = 0;
      v11 = RtlQueryWnfStateData(
              &pv,
              WNF_DICT_CONTENT_ADDED,
              Windows::Globalization::Spelling::CEnumStringDecorator::UpdateRegistry,
              0)
          | 0x10000000;
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdi"
                        "ctionarymanager.cpp",
          (const char *)(unsigned int)v11,
          0);
      v13 = (unsigned int)pv;
      std::shared_ptr<Windows::Globalization::Spelling::CWordlist>::shared_ptr<Windows::Globalization::Spelling::CWordlist>(
        &v37,
        (char *)this + 152,
        v12);
      wistd::function_void___cdecl_SpellerDictionaryRequest_const____::function_void___cdecl_SpellerDictionaryRequest_const______lambda_f57266230d17491f151a123939cd65ef__void_(
        v43,
        &v37);
      wnf = (Windows::Internal::Spelling::RoamingDictionaryManager *)wil::make_wnf_subscription<SpellerDictionaryRequest>(
                                                                       &v39,
                                                                       v14,
                                                                       (__int64)v43,
                                                                       v13);
      v16 = wnf;
      v17 = (regex::detail **)((char *)this + 72);
      if ( (Windows::Internal::Spelling::RoamingDictionaryManager *)((char *)this + 72) != wnf )
      {
        v18 = *(regex::detail **)wnf;
        v19 = *v17;
        if ( *v17 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v37);
          regex::detail::free_charset(v19, v20);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v37);
        }
        *v17 = v18;
        *(_QWORD *)v16 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v39);
      wistd::function<bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::~function<bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>(v43);
    }
    if ( !*((_BYTE *)this + 80) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::GetImpl'::`2'::impl);
      v39 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))this;
      if ( IsEnabled )
      {
        v22 = wil::com_weak_query<Windows::Internal::Spelling::RoamingDictionaryManager *>(&v37, &v39);
        v23 = *v22;
        *v22 = 0;
        v24 = (PVOID *)((char *)this + 88);
        wil::com_ptr_t<IWeakReference,wil::err_exception_policy>::attach((char *)this + 88, v23);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
        v25 = (Windows::Internal::Spelling **)((char *)this + 96);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            lambda_1b71c4d37592ed3ade3f2cf41f85802b_::_lambda_invoker_cdecl_,
                            *v24,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          v25,
          ThreadpoolTimer);
        if ( !*v25 )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x91,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            v29);
      }
      else
      {
        wil::com_weak_query<Windows::Internal::Spelling::RoamingDictionaryManager *>(&pv, &v39);
        v25 = (Windows::Internal::Spelling **)((char *)this + 96);
        v30 = CreateThreadpoolTimer(lambda_d6b18a866eec8a0a7a4f6b554c199118_::_lambda_invoker_cdecl_, pv, 0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          v25,
          v30);
        if ( !*v25 )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0xA9,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            v31);
        pv = 0;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pv);
      }
      Windows::Internal::Spelling::SetThreadpoolTimerByMillisecondsDelay(*v25, v27, v28);
    }
    TrySubmitThreadpoolCallback(lambda_2e096ac99a3e668ffe194cfc3391a7ab_::_lambda_invoker_cdecl_, 0, 0);
    wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
    if ( v42 )
      std::_Ref_count_base::_Decref(v42);
    SpellingTelemetry::ActivityStartRoaming::~ActivityStartRoaming((SpellingTelemetry::ActivityStartRoaming *)v44);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB7,
                           (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\c"
                                         "urrent\\roamingdictionarymanager.cpp",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x1800807d0  push    rbx
0x1800807d2  push    rsi
0x1800807d3  push    rdi
0x1800807d4  push    r12
0x1800807d6  push    r14
0x1800807d8  push    r15
0x1800807da  sub     rsp, 258h
0x1800807e1  mov     rax, cs:__security_cookie
0x1800807e8  xor     rax, rsp
0x1800807eb  mov     [rsp+288h+var_48], rax
0x1800807f3  mov     rdi, rcx
0x1800807f6  lea     rdx, aActivitystartr; "ActivityStartRoaming"
0x1800807fd  lea     rcx, [rsp+288h+var_198]
0x180080805  call    ??0?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18008080a  lea     rax, ??_7ActivityStartRoaming@SpellingTelemetry@@6B@; const SpellingTelemetry::ActivityStartRoaming::`vftable'
0x180080811  mov     [rsp+288h+var_198], rax
0x180080819  lea     rsi, [rdi+98h]
0x180080820  xor     r12d, r12d
0x180080823  cmp     [rsi], r12
0x180080826  jnz     loc_1800808D1
0x18008082c  mov     [rsp+288h+var_258], 1
0x180080831  mov     [rsp+288h+var_257], 1
0x180080836  lea     r8, [rsp+288h+var_258]
0x18008083b  lea     rdx, [rsp+288h+var_257]
0x180080840  lea     rcx, [rsp+288h+var_248]
0x180080845  call    ??$make_shared@VTaskConsumer@Spelling@Internal@Windows@@_N_N@std@@YA?AV?$shared_ptr@VTaskConsumer@Spelling@Internal@Windows@@@0@$$QEA_N0@Z; std::make_shared<Windows::Internal::Spelling::TaskConsumer,bool,bool>(bool &&,bool &&)
0x18008084a  nop
0x18008084b  mov     rdx, rax
0x18008084e  lea     rcx, [rsp+288h+var_238]
0x180080853  call    ??$make_shared@VTaskDispatcher@Spelling@Internal@Windows@@V?$shared_ptr@VTaskConsumer@Spelling@Internal@Windows@@@std@@@std@@YA?AV?$shared_ptr@VTaskDispatcher@Spelling@Internal@Windows@@@0@$$QEAV?$shared_ptr@VTaskConsumer@Spelling@Internal@Windows@@@0@@Z; std::make_shared<Windows::Internal::Spelling::TaskDispatcher,std::shared_ptr<Windows::Internal::Spelling::TaskConsumer>>(std::shared_ptr<Windows::Internal::Spelling::TaskConsumer> &&)
0x180080858  mov     rcx, [rax]
0x18008085b  mov     rdx, [rax+8]
0x18008085f  mov     [rax], r12
0x180080862  mov     [rax+8], r12
0x180080866  mov     [rsi], rcx
0x180080869  mov     rcx, [rsi+8]; this
0x18008086d  mov     [rsi+8], rdx
0x180080871  test    rcx, rcx
0x180080874  jz      short loc_18008087B
0x180080876  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008087b  mov     rcx, [rsp+288h+var_230]; this
0x180080880  test    rcx, rcx
0x180080883  jz      short loc_18008088B
0x180080885  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008088a  nop
0x18008088b  mov     rcx, [rsp+288h+var_240]; this
0x180080890  test    rcx, rcx
0x180080893  jz      short loc_18008089A
0x180080895  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008089a  mov     rax, [rsi+8]
0x18008089e  test    rax, rax
0x1800808a1  jz      short loc_1800808AC
0x1800808a3  mov     rcx, [rsi]
0x1800808a6  lock inc dword ptr [rax+0Ch]
0x1800808aa  jmp     short loc_1800808B2
0x1800808ac  mov     rax, r12
0x1800808af  mov     rcx, r12
0x1800808b2  mov     qword ptr cs:?s_weakLinkedInstance@TaskDispatcher@Spelling@Internal@Windows@@2V?$weak_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@A, rcx; std::weak_ptr<Windows::Internal::Spelling::TaskDispatcherInterface> Windows::Internal::Spelling::TaskDispatcher::s_weakLinkedInstance
0x1800808b9  mov     rcx, qword ptr cs:?s_weakLinkedInstance@TaskDispatcher@Spelling@Internal@Windows@@2V?$weak_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@A+8; this
0x1800808c0  mov     qword ptr cs:?s_weakLinkedInstance@TaskDispatcher@Spelling@Internal@Windows@@2V?$weak_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@A+8, rax; std::weak_ptr<Windows::Internal::Spelling::TaskDispatcherInterface> Windows::Internal::Spelling::TaskDispatcher::s_weakLinkedInstance
0x1800808c7  test    rcx, rcx
0x1800808ca  jz      short loc_1800808D1
0x1800808cc  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800808d1  lea     rcx, [rsp+288h+var_228]
0x1800808d6  call    ??$make_shared@UTaskItem@Spelling@Internal@Windows@@$$V@std@@YA?AV?$shared_ptr@UTaskItem@Spelling@Internal@Windows@@@0@XZ; std::make_shared<Windows::Internal::Spelling::TaskItem,>(void)
0x1800808db  nop
0x1800808dc  mov     rax, [rsp+288h+var_228]
0x1800808e1  mov     byte ptr [rax], 1
0x1800808e4  mov     rcx, [rsi]
0x1800808e7  mov     rax, [rcx]
0x1800808ea  lea     rdx, [rsp+288h+var_228]
0x1800808ef  mov     rax, [rax+8]
0x1800808f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800808f8  cmp     [rdi+40h], r12b
0x1800808fc  jnz     loc_1800809BC
0x180080902  mov     dword ptr [rsp+288h+pv], r12d
0x180080907  mov     qword ptr [rsp+288h+var_268], r12; int
0x18008090c  xor     r9d, r9d
0x18008090f  lea     r8, ?UpdateRegistry@CEnumStringDecorator@Spelling@Globalization@Windows@@SAJH@Z; Windows::Globalization::Spelling::CEnumStringDecorator::UpdateRegistry(int)
0x180080916  mov     rdx, cs:WNF_DICT_CONTENT_ADDED
0x18008091d  lea     rcx, [rsp+288h+pv]
0x180080922  call    cs:__imp_RtlQueryWnfStateData
0x180080928  or      eax, 10000000h
0x18008092d  mov     rcx, [rsp+288h]; this
0x180080935  jl      loc_180080B02
0x18008093b  mov     ebx, dword ptr [rsp+288h+pv]
0x18008093f  mov     rdx, rsi
0x180080942  lea     rcx, [rsp+288h+var_248]
0x180080947  call    ??0?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Globalization::Spelling::CWordlist>::shared_ptr<Windows::Globalization::Spelling::CWordlist>(std::shared_ptr<Windows::Globalization::Spelling::CWordlist> const &)
0x18008094c  lea     rdx, [rsp+288h+var_248]
0x180080951  lea     rcx, [rsp+288h+var_218]
0x180080956  call    wistd__function_void___cdecl_SpellerDictionaryRequest_const______function_void___cdecl_SpellerDictionaryRequest_const______lambda_f57266230d17491f151a123939cd65ef__void_
0x18008095b  nop
0x18008095c  mov     r9d, ebx
0x18008095f  lea     r8, [rsp+288h+var_218]
0x180080964  lea     rcx, [rsp+288h+var_238]
0x180080969  call    ??$make_wnf_subscription@USpellerDictionaryRequest@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBUSpellerDictionaryRequest@@@Z@wistd@@K@Z; wil::make_wnf_subscription<SpellerDictionaryRequest>(_WNF_STATE_NAME const &,wistd::function<void (SpellerDictionaryRequest const &)> &&,ulong)
0x18008096e  mov     rsi, rax
0x180080971  lea     rbx, [rdi+48h]
0x180080975  cmp     rbx, rax
0x180080978  jz      short loc_1800809A7
0x18008097a  mov     r15, [rax]
0x18008097d  mov     r14, [rbx]
0x180080980  test    r14, r14
0x180080983  jz      short loc_1800809A1
0x180080985  lea     rcx, [rsp+288h+var_248]; this
0x18008098a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008098f  mov     rcx, r14; this
0x180080992  call    ?free_charset@detail@regex@@YAXPEBUcharset@12@@Z; regex::detail::free_charset(regex::detail::charset const *)
0x180080997  lea     rcx, [rsp+288h+var_248]; this
0x18008099c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800809a1  mov     [rbx], r15
0x1800809a4  mov     [rsi], r12
0x1800809a7  lea     rcx, [rsp+288h+var_238]
0x1800809ac  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800809b1  nop
0x1800809b2  lea     rcx, [rsp+288h+var_218]
0x1800809b7  call    ??1?$function@$$A6A_NPEAX_K01I@Z@wistd@@QEAA@XZ; wistd::function<bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::~function<bool (void *,unsigned __int64,void *,unsigned __int64,uint)>(void)
0x1800809bc  cmp     [rdi+50h], r12b
0x1800809c0  jnz     loc_180080A9C
0x1800809c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager> `wil::Feature<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::GetImpl(void)'::`2'::impl
0x1800809cd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::__private_IsEnabled(void)
0x1800809d2  mov     [rsp+288h+var_238], rdi
0x1800809d7  lea     rdx, [rsp+288h+var_238]
0x1800809dc  test    al, al
0x1800809de  jz      short loc_180080A40
0x1800809e0  lea     rcx, [rsp+288h+var_248]
0x1800809e5  call    ??$com_weak_query@PEAVRoamingDictionaryManager@Spelling@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@$$QEAPEAVRoamingDictionaryManager@Spelling@Internal@Windows@@@Z; wil::com_weak_query<Windows::Internal::Spelling::RoamingDictionaryManager *>(Windows::Internal::Spelling::RoamingDictionaryManager * &&)
0x1800809ea  mov     rdx, [rax]
0x1800809ed  mov     [rax], r12
0x1800809f0  lea     rbx, [rdi+58h]
0x1800809f4  mov     rcx, rbx
0x1800809f7  call    ?attach@?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUIWeakReference@@@Z; wil::com_ptr_t<IWeakReference,wil::err_exception_policy>::attach(IWeakReference *)
0x1800809fc  lea     rcx, [rsp+288h+var_248]
0x180080a01  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180080a06  add     rdi, 60h ; '`'
0x180080a0a  xor     r8d, r8d; pcbe
0x180080a0d  mov     rdx, [rbx]; pv
0x180080a10  lea     rcx, _lambda_1b71c4d37592ed3ade3f2cf41f85802b____lambda_invoker_cdecl_; pfnti
0x180080a17  call    cs:__imp_CreateThreadpoolTimer
0x180080a1d  mov     rdx, rax
0x180080a20  mov     rcx, rdi
0x180080a23  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180080a28  cmp     [rdi], r12
0x180080a2b  setz    al
0x180080a2e  mov     rcx, [rsp+288h]; this
0x180080a36  test    al, al
0x180080a38  jnz     loc_180080B16
0x180080a3e  jmp     short loc_180080A94
0x180080a40  lea     rcx, [rsp+288h+pv]
0x180080a45  call    ??$com_weak_query@PEAVRoamingDictionaryManager@Spelling@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@$$QEAPEAVRoamingDictionaryManager@Spelling@Internal@Windows@@@Z; wil::com_weak_query<Windows::Internal::Spelling::RoamingDictionaryManager *>(Windows::Internal::Spelling::RoamingDictionaryManager * &&)
0x180080a4a  nop
0x180080a4b  add     rdi, 60h ; '`'
0x180080a4f  xor     r8d, r8d; pcbe
0x180080a52  mov     rdx, [rsp+288h+pv]; pv
0x180080a57  lea     rcx, _lambda_d6b18a866eec8a0a7a4f6b554c199118____lambda_invoker_cdecl_; pfnti
0x180080a5e  call    cs:__imp_CreateThreadpoolTimer
0x180080a64  mov     rdx, rax
0x180080a67  mov     rcx, rdi
0x180080a6a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180080a6f  cmp     [rdi], r12
0x180080a72  setz    al
0x180080a75  mov     rcx, [rsp+288h]; this
0x180080a7d  test    al, al
0x180080a7f  jnz     loc_180080B28
0x180080a85  mov     [rsp+288h+pv], r12
0x180080a8a  lea     rcx, [rsp+288h+pv]
0x180080a8f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180080a94  mov     rcx, [rdi]; this
0x180080a97  call    ?SetThreadpoolTimerByMillisecondsDelay@Spelling@Internal@Windows@@YAXPEAU_TP_TIMER@@_J@Z; Windows::Internal::Spelling::SetThreadpoolTimerByMillisecondsDelay(_TP_TIMER *,__int64)
0x180080a9c  xor     r8d, r8d; pcbe
0x180080a9f  xor     edx, edx; pv
0x180080aa1  lea     rcx, _lambda_2e096ac99a3e668ffe194cfc3391a7ab____lambda_invoker_cdecl_; pfns
0x180080aa8  call    cs:__imp_TrySubmitThreadpoolCallback
0x180080aae  lea     rcx, [rsp+288h+var_198]
0x180080ab6  call    ?Stop@?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180080abb  nop
0x180080abc  mov     rcx, [rsp+288h+var_220]; this
0x180080ac1  test    rcx, rcx
0x180080ac4  jz      short loc_180080ACC
0x180080ac6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180080acb  nop
0x180080acc  lea     rcx, [rsp+288h+var_198]; this
0x180080ad4  call    ??1ActivityStartRoaming@SpellingTelemetry@@QEAA@XZ; SpellingTelemetry::ActivityStartRoaming::~ActivityStartRoaming(void)
0x180080ad9  xor     eax, eax
0x180080adb  jmp     short loc_180080AE1
0x180080add  mov     eax, dword ptr [rsp+288h+pv]
0x180080ae1  mov     rcx, [rsp+288h+var_48]
0x180080ae9  xor     rcx, rsp; StackCookie
0x180080aec  call    __security_check_cookie
0x180080af1  add     rsp, 258h
0x180080af8  pop     r15
0x180080afa  pop     r14
0x180080afc  pop     r12
0x180080afe  pop     rdi
0x180080aff  pop     rsi
0x180080b00  pop     rbx
0x180080b01  retn
0x180080b02  mov     r9d, eax; char *
0x180080b05  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180080b0c  mov     edx, 6Fh ; 'o'; void *
0x180080b11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080b16  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180080b1d  mov     edx, 91h; void *
0x180080b22  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180080b28  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180080b2f  mov     edx, 0A9h; void *
0x180080b34  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

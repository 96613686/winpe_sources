# TimeUpdate::Init(bool)

- ea: `0x180007534`
- end: `0x1800079fa`
- name: `?Init@TimeUpdate@@QEAAX_N@Z`
- size: `1222`
- prototype: `void __fastcall(TimeUpdate *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180008d7c`

## callees

- `0x180001010`
- `0x180001054`
- `0x1800012f0`
- `0x180002a70`
- `0x180002a94`
- `0x180004dc0`
- `0x1800055c8`
- `0x180005688`
- `0x1800057d4`
- `0x180005840`
- `0x180005a58`
- `0x180005a74`
- `0x180007534`
- `0x18000a658`
- `0x18000a674`
- `0x18000a6d0`
- `0x18000a9e4`
- `0x18000aa38`
- `0x18000aa8c`
- `0x18000ab38`
- `0x18000b668`
- `0x18000b7d8`
- `0x18000b98c`
- `0x18000bd34`
- `0x18000f540`
- `0x180012010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000795d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000795d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000789f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000789f`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180007875`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180007875`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800077dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800077dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075f7`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180007787`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180007787`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800077a8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800077a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007711`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007711`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000756c`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000756c`

## string_xrefs

- `0x180007967`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`
- `0x180007979`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`
- `0x180007991`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`
- `0x1800079a6`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`
- `0x1800079bb`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`
- `0x1800079cd`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

## pseudocode

```c
void __fastcall TimeUpdate::Init(TimeUpdate *this, unsigned __int8 a2)
{
  int v2; // esi
  char v4; // al
  volatile signed __int32 *v5; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v7; // r9
  WnfSubscription *i; // rbx
  int v9; // eax
  SC_HANDLE v10; // rax
  const char *v11; // r9
  HANDLE EventW; // rax
  const char *v13; // r9
  __int64 v14; // rbx
  _QWORD *v15; // rax
  __int128 v16; // xmm1
  __int64 v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  int v19; // [rsp+20h] [rbp-A9h]
  char v20; // [rsp+30h] [rbp-99h] BYREF
  char *v21; // [rsp+38h] [rbp-91h] BYREF
  __int128 v22; // [rsp+40h] [rbp-89h] BYREF
  char *v23; // [rsp+50h] [rbp-79h] BYREF
  __int64 v24; // [rsp+58h] [rbp-71h] BYREF
  volatile signed __int32 *v25; // [rsp+60h] [rbp-69h]
  _QWORD *v26; // [rsp+68h] [rbp-61h] BYREF
  _QWORD v27[2]; // [rsp+70h] [rbp-59h] BYREF
  char v28; // [rsp+80h] [rbp-49h]
  char *v29; // [rsp+B0h] [rbp-19h]
  __int64 v30; // [rsp+B8h] [rbp-11h]
  char **v31; // [rsp+C0h] [rbp-9h]
  __int64 v32; // [rsp+C8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v2 = a2;
  v23 = 0;
  GetSystemTimePreciseAsFileTime(&v23);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 0x400000000001LL) )
  {
    v21 = v23;
    v20 = v2;
    v31 = &v21;
    v32 = 8;
    v29 = &v20;
    v30 = 1;
    v19 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, &byte_1800167FF, 0, 0);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v21 = (char *)this + 16;
  v4 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = 1;
  if ( v4 )
  {
    if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18001C010,
        &word_180016836,
        0,
        0);
    goto LABEL_8;
  }
  std::make_shared<Settings,Settings::SharedHelper>(&v24);
  std::shared_ptr<Settings>::operator=((char *)this + 224, &v24);
  v5 = v25;
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  *((_BYTE *)this + 240) = 0;
  *((_BYTE *)this + 596) = 0;
  WNFNotificationDispatcher::Init(
    (char *)this + 64,
    (void (__high *)(enum ActionType, void *))lambda_5065b47f869d0d272bc2793c1f862d5c_::_lambda_invoker_cdecl_,
    this);
  WNFNotificationDispatcher::Init(
    (char *)this + 144,
    (void (__high *)(enum ActionType, void *))lambda_f848a3d627fe386eb38ad84789a90242_::_lambda_invoker_cdecl_,
    this);
  ThreadpoolTimer = CreateThreadpoolTimer(lambda_f4791c5cc29f67cb29f425c93d484277_::_lambda_invoker_cdecl_, this, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 248,
    ThreadpoolTimer);
  if ( !*((_QWORD *)this + 31) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
      v7);
  if ( !(unsigned __int8)WNFNotificationDispatcher::Enqueue((char *)this + 64, (unsigned int)(8 * v2 + 4096)) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30E,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
      (const char *)0x80004005LL,
      v19);
  for ( i = (TimeUpdate *)((char *)this + 256);
        i != (TimeUpdate *)((char *)this + 480);
        i = (WnfSubscription *)((char *)i + 56) )
  {
    v9 = WnfSubscription::Subscribe(
           i,
           (void (__high *)(enum ActionType, void *))&lambda_1911fdf903578344d5c92f362d188f99_::_lambda_invoker_cdecl_,
           this);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x317,
        (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
        (const char *)(unsigned int)v9,
        v19);
  }
  SleepEx(1u, 1);
  WNFNotificationDispatcher::Start((TimeUpdate *)((char *)this + 64));
  v10 = OpenSCManagerW(0, 0, 4u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    (char *)this + 640,
    v10);
  if ( !*((_QWORD *)this + 80) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x323,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
      v11);
  EventW = CreateEventW(0, 1, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 584,
    EventW);
  if ( !*((_QWORD *)this + 73) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x326,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
      v13);
  std::promise<long>::promise<long>(v27);
  if ( !(unsigned __int8)std::_State_manager<long>::valid(v27) )
    std::_Throw_future_error2(4);
  if ( v28 )
    std::_Throw_future_error2(2);
  v28 = 1;
  v14 = v27[0];
  v24 = v27[0];
  LOBYTE(v25) = 1;
  if ( v27[0] )
    _InterlockedAdd((volatile signed __int32 *)(v27[0] + 8LL), 1u);
  v15 = operator new(0x10u);
  *v15 = this;
  v15[1] = v27;
  v26 = v15;
  *(_QWORD *)&v22 = _o__beginthreadex(
                      0,
                      0,
                      std::thread::_Invoke_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____0_,
                      v15);
  if ( !(_QWORD)v22 )
  {
    DWORD2(v22) = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_35;
  }
  v26 = 0;
  std::unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______::_unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______(&v26);
  if ( *((_DWORD *)this + 122) )
  {
    _o_terminate();
    __debugbreak();
  }
  v16 = v22;
  v22 = 0;
  *((_OWORD *)this + 30) = v16;
  std::thread::~thread((std::thread *)&v22);
  v24 = 0;
  *(_QWORD *)&v22 = v14;
  BYTE8(v22) = 1;
  if ( !(unsigned __int8)std::_State_manager<long>::valid(&v22) )
    std::_Throw_future_error2(4);
  LOBYTE(v17) = 1;
  LODWORD(v14) = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 16LL))(v14, v17);
  std::_State_manager<long>::~_State_manager<long>(&v22);
  v18 = retaddr;
  if ( (int)v14 < 0 )
LABEL_35:
    wil::details::in1diag3::Throw_Hr(
      v18,
      (void *)0x32F,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
      (const char *)(unsigned int)v14,
      0);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18001C010,
      &word_1800165BE,
      0,
      0);
  std::_State_manager<long>::~_State_manager<long>(&v24);
  std::promise<long>::~promise<long>(v27);
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
}

```

## disassembly

```asm
0x180007534  push    rbp
0x180007536  push    rbx
0x180007537  push    rsi
0x180007538  push    rdi
0x180007539  push    r12
0x18000753b  push    r13
0x18000753d  push    r14
0x18000753f  push    r15
0x180007541  lea     rbp, [rsp-1Fh]
0x180007546  sub     rsp, 0E8h
0x18000754d  mov     rax, cs:__security_cookie
0x180007554  xor     rax, rsp
0x180007557  mov     [rbp+57h+var_50], rax
0x18000755b  movzx   esi, dl
0x18000755e  mov     rdi, rcx
0x180007561  xor     r15d, r15d
0x180007564  mov     [rbp+57h+var_D0], r15
0x180007568  lea     rcx, [rbp+57h+var_D0]
0x18000756c  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180007572  mov     eax, cs:dword_18001C010
0x180007578  lea     r13, dword_18001C010
0x18000757f  lea     r12d, [r15+1]
0x180007583  cmp     eax, 4
0x180007586  jbe     short loc_1800075F0
0x180007588  mov     rdx, 400000000001h
0x180007592  mov     rcx, r13
0x180007595  call    _tlgKeywordOn
0x18000759a  test    al, al
0x18000759c  jz      short loc_1800075F0
0x18000759e  mov     rax, [rbp+57h+var_D0]
0x1800075a2  mov     [rsp+120h+var_E8], rax
0x1800075a7  mov     [rsp+120h+var_F0], sil
0x1800075ac  lea     rax, [rsp+120h+var_E8]
0x1800075b1  mov     [rbp+57h+var_60], rax
0x1800075b5  mov     [rbp+57h+var_58], 8
0x1800075bd  lea     rax, [rsp+120h+var_F0]
0x1800075c2  mov     [rbp+57h+var_70], rax
0x1800075c6  mov     [rbp+57h+var_68], r12
0x1800075ca  lea     rax, [rbp+57h+var_90]
0x1800075ce  mov     [rsp+120h+var_F8], rax
0x1800075d3  mov     [rsp+120h+var_100], 4; int
0x1800075db  xor     r9d, r9d
0x1800075de  xor     r8d, r8d
0x1800075e1  lea     rdx, byte_1800167FF
0x1800075e8  mov     rcx, r13
0x1800075eb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800075f0  lea     rbx, [rdi+10h]
0x1800075f4  mov     rcx, rbx; lpCriticalSection
0x1800075f7  call    cs:__imp_EnterCriticalSection
0x1800075fd  mov     [rsp+120h+var_E8], rbx
0x180007602  mov     eax, r12d
0x180007605  xchg    al, [rdi+38h]
0x180007608  test    al, al
0x18000760a  jz      short loc_180007666
0x18000760c  mov     eax, cs:dword_18001C010
0x180007612  cmp     eax, 3
0x180007615  jbe     short loc_18000763C
0x180007617  mov     rdx, r12
0x18000761a  mov     rcx, r13
0x18000761d  call    _tlgKeywordOn
0x180007622  test    al, al
0x180007624  jz      short loc_18000763C
0x180007626  xor     r9d, r9d
0x180007629  xor     r8d, r8d
0x18000762c  lea     rdx, word_180016836
0x180007633  mov     rcx, r13
0x180007636  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000763b  nop
0x18000763c  lea     rcx, [rsp+120h+var_E8]
0x180007641  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180007646  mov     rcx, [rbp+57h+var_50]
0x18000764a  xor     rcx, rsp; StackCookie
0x18000764d  call    __security_check_cookie
0x180007652  add     rsp, 0E8h
0x180007659  pop     r15
0x18000765b  pop     r14
0x18000765d  pop     r13
0x18000765f  pop     r12
0x180007661  pop     rdi
0x180007662  pop     rsi
0x180007663  pop     rbx
0x180007664  pop     rbp
0x180007665  retn
0x180007666  lea     rcx, [rbp+57h+var_C8]
0x18000766a  call    ??$make_shared@VSettings@@USharedHelper@1@@std@@YA?AV?$shared_ptr@VSettings@@@0@$$QEAUSharedHelper@Settings@@@Z; std::make_shared<Settings,Settings::SharedHelper>(Settings::SharedHelper &&)
0x18000766f  lea     rcx, [rdi+0E0h]
0x180007676  lea     rdx, [rbp+57h+var_C8]
0x18000767a  call    ??4?$shared_ptr@VSettings@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Settings>::operator=(std::shared_ptr<Settings> &&)
0x18000767f  mov     rbx, [rbp+57h+var_C0]
0x180007683  test    rbx, rbx
0x180007686  jz      short loc_1800076C3
0x180007688  or      r14d, 0FFFFFFFFh
0x18000768c  mov     eax, r14d
0x18000768f  lock xadd [rbx+8], eax
0x180007694  add     eax, r14d
0x180007697  jnz     short loc_1800076C3
0x180007699  mov     rax, [rbx]
0x18000769c  mov     rcx, rbx
0x18000769f  mov     rax, [rax]
0x1800076a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a7  mov     eax, r14d
0x1800076aa  lock xadd [rbx+0Ch], eax
0x1800076af  add     eax, r14d
0x1800076b2  jnz     short loc_1800076C3
0x1800076b4  mov     rax, [rbx]
0x1800076b7  mov     rcx, rbx
0x1800076ba  mov     rax, [rax+8]
0x1800076be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076c3  mov     [rdi+0F0h], r15b
0x1800076ca  mov     [rdi+254h], r15b
0x1800076d1  lea     r14, [rdi+40h]
0x1800076d5  mov     r8, rdi; void *
0x1800076d8  lea     rdx, _lambda_5065b47f869d0d272bc2793c1f862d5c____lambda_invoker_cdecl_; void (__high *)(enum ActionType, void *)
0x1800076df  mov     rcx, r14; pv
0x1800076e2  call    ?Init@WNFNotificationDispatcher@@QEAAXP6AXW4ActionType@@PEAX@Z1@Z; WNFNotificationDispatcher::Init(void (*)(ActionType,void *),void *)
0x1800076e7  lea     rcx, [rdi+90h]; pv
0x1800076ee  mov     r8, rdi; void *
0x1800076f1  lea     rdx, _lambda_f848a3d627fe386eb38ad84789a90242____lambda_invoker_cdecl_; void (__high *)(enum ActionType, void *)
0x1800076f8  call    ?Init@WNFNotificationDispatcher@@QEAAXP6AXW4ActionType@@PEAX@Z1@Z; WNFNotificationDispatcher::Init(void (*)(ActionType,void *),void *)
0x1800076fd  lea     rbx, [rdi+0F8h]
0x180007704  xor     r8d, r8d; pcbe
0x180007707  mov     rdx, rdi; pv
0x18000770a  lea     rcx, _lambda_f4791c5cc29f67cb29f425c93d484277____lambda_invoker_cdecl_; pfnti
0x180007711  call    cs:__imp_CreateThreadpoolTimer
0x180007717  mov     rdx, rax
0x18000771a  mov     rcx, rbx
0x18000771d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180007722  mov     rcx, [rbp+5Fh]; this
0x180007726  cmp     [rbx], r15
0x180007729  jz      loc_180007979
0x18000772f  mov     rbx, [rbp+5Fh]
0x180007733  lea     edx, ds:1000h[rsi*8]
0x18000773a  mov     rcx, r14
0x18000773d  call    ?Enqueue@WNFNotificationDispatcher@@QEAA_NW4ActionType@@@Z; WNFNotificationDispatcher::Enqueue(ActionType)
0x180007742  test    al, al
0x180007744  jz      loc_18000798B
0x18000774a  lea     rbx, [rdi+100h]
0x180007751  lea     rsi, [rbx+0E0h]
0x180007758  jmp     short loc_18000777C
0x18000775a  mov     r8, rdi; void *
0x18000775d  lea     rdx, _lambda_1911fdf903578344d5c92f362d188f99____lambda_invoker_cdecl_; void (__high *)(enum ActionType, void *)
0x180007764  mov     rcx, rbx; this
0x180007767  call    ?Subscribe@WnfSubscription@@QEAAJP6AXW4ActionType@@PEAX@Z1@Z; WnfSubscription::Subscribe(void (*)(ActionType,void *),void *)
0x18000776c  mov     rcx, [rbp+5Fh]; this
0x180007770  test    eax, eax
0x180007772  js      loc_1800079B8
0x180007778  add     rbx, 38h ; '8'
0x18000777c  cmp     rbx, rsi
0x18000777f  jnz     short loc_18000775A
0x180007781  mov     edx, r12d; bAlertable
0x180007784  mov     ecx, r12d; dwMilliseconds
0x180007787  call    cs:__imp_SleepEx
0x18000778d  mov     rcx, r14; this
0x180007790  call    ?Start@WNFNotificationDispatcher@@QEAAXXZ; WNFNotificationDispatcher::Start(void)
0x180007795  lea     rbx, [rdi+280h]
0x18000779c  mov     esi, 4
0x1800077a1  mov     r8d, esi; dwDesiredAccess
0x1800077a4  xor     edx, edx; lpDatabaseName
0x1800077a6  xor     ecx, ecx; lpMachineName
0x1800077a8  call    cs:__imp_OpenSCManagerW
0x1800077ae  mov     rdx, rax
0x1800077b1  mov     rcx, rbx
0x1800077b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800077b9  cmp     [rbx], r15
0x1800077bc  setz    al
0x1800077bf  mov     rcx, [rbp+5Fh]; this
0x1800077c3  test    al, al
0x1800077c5  jnz     loc_1800079A6
0x1800077cb  lea     rbx, [rdi+248h]
0x1800077d2  xor     r9d, r9d; lpName
0x1800077d5  xor     r8d, r8d; bInitialState
0x1800077d8  mov     edx, r12d; bManualReset
0x1800077db  xor     ecx, ecx; lpEventAttributes
0x1800077dd  call    cs:__imp_CreateEventW
0x1800077e3  mov     rdx, rax
0x1800077e6  mov     rcx, rbx
0x1800077e9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800077ee  cmp     [rbx], r15
0x1800077f1  setz    al
0x1800077f4  mov     rcx, [rbp+5Fh]; this
0x1800077f8  test    al, al
0x1800077fa  jnz     loc_1800079CD
0x180007800  lea     rcx, [rbp+57h+var_B0]
0x180007804  call    ??0?$promise@J@std@@QEAA@XZ; std::promise<long>::promise<long>(void)
0x180007809  nop
0x18000780a  lea     rcx, [rbp+57h+var_B0]
0x18000780e  call    ?valid@?$_State_manager@J@std@@QEBA_NXZ; std::_State_manager<long>::valid(void)
0x180007813  test    al, al
0x180007815  jz      loc_1800079DF
0x18000781b  cmp     [rbp+57h+var_A0], r15b
0x18000781f  jnz     loc_1800079E7
0x180007825  mov     [rbp+57h+var_A0], r12b
0x180007829  mov     rbx, [rbp+57h+var_B0]
0x18000782d  mov     [rbp+57h+var_C8], rbx
0x180007831  mov     byte ptr [rbp+57h+var_C0], r12b
0x180007835  test    rbx, rbx
0x180007838  jz      short loc_18000783F
0x18000783a  lock add [rbx+8], r12d
0x18000783f  mov     ecx, 10h; Size
0x180007844  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007849  mov     [rax], rdi
0x18000784c  lea     rcx, [rbp+57h+var_B0]
0x180007850  mov     [rax+8], rcx
0x180007854  mov     [rbp+57h+var_B8], rax
0x180007858  lea     rcx, [rsp+120h+var_E0+8]
0x18000785d  mov     [rsp+120h+var_F8], rcx
0x180007862  mov     [rsp+120h+var_100], r15d; int
0x180007867  mov     r9, rax
0x18000786a  lea     r8, std__thread___Invoke_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____0_
0x180007871  xor     edx, edx
0x180007873  xor     ecx, ecx
0x180007875  call    cs:__imp__o__beginthreadex
0x18000787b  mov     qword ptr [rsp+120h+var_E0], rax
0x180007880  test    rax, rax
0x180007883  jz      loc_180007953
0x180007889  mov     [rbp+57h+var_B8], r15
0x18000788d  lea     rcx, [rbp+57h+var_B8]
0x180007891  call    std__unique_ptr_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std__default_delete_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d__________unique_ptr_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std__default_delete_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______
0x180007896  cmp     [rdi+1E8h], r15d
0x18000789d  jz      short loc_1800078A6
0x18000789f  call    cs:__imp__o_terminate
0x1800078a5  int     3; Trap to Debugger
0x1800078a6  xorps   xmm0, xmm0
0x1800078a9  movaps  xmm1, [rsp+120h+var_E0]
0x1800078ae  movdqa  [rsp+120h+var_E0], xmm0
0x1800078b4  movdqu  xmmword ptr [rdi+1E0h], xmm1
0x1800078bc  lea     rcx, [rsp+120h+var_E0]; this
0x1800078c1  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x1800078c6  mov     [rbp+57h+var_C8], r15
0x1800078ca  mov     qword ptr [rsp+120h+var_E0], rbx
0x1800078cf  mov     byte ptr [rsp+120h+var_E0+8], r12b
0x1800078d4  lea     rcx, [rsp+120h+var_E0]
0x1800078d9  call    ?valid@?$_State_manager@J@std@@QEBA_NXZ; std::_State_manager<long>::valid(void)
0x1800078de  test    al, al
0x1800078e0  jz      loc_1800079F2
0x1800078e6  mov     rax, [rbx]
0x1800078e9  mov     dl, r12b
0x1800078ec  mov     rcx, rbx
0x1800078ef  mov     rax, [rax+10h]
0x1800078f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078f8  mov     ebx, [rax]
0x1800078fa  lea     rcx, [rsp+120h+var_E0]
0x1800078ff  call    ??1?$_State_manager@J@std@@QEAA@XZ; std::_State_manager<long>::~_State_manager<long>(void)
0x180007904  mov     rcx, [rbp+5Fh]
0x180007908  test    ebx, ebx
0x18000790a  js      short loc_180007964
0x18000790c  mov     eax, cs:dword_18001C010
0x180007912  cmp     eax, esi
0x180007914  jbe     short loc_18000793B
0x180007916  mov     rdx, r12
0x180007919  mov     rcx, r13
0x18000791c  call    _tlgKeywordOn
0x180007921  test    al, al
0x180007923  jz      short loc_18000793B
0x180007925  xor     r9d, r9d
0x180007928  xor     r8d, r8d
0x18000792b  lea     rdx, word_1800165BE
0x180007932  mov     rcx, r13
0x180007935  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000793a  nop
0x18000793b  lea     rcx, [rbp+57h+var_C8]
0x18000793f  call    ??1?$_State_manager@J@std@@QEAA@XZ; std::_State_manager<long>::~_State_manager<long>(void)
0x180007944  nop
0x180007945  lea     rcx, [rbp+57h+var_B0]
0x180007949  call    ??1?$promise@J@std@@QEAA@XZ; std::promise<long>::~promise<long>(void)
0x18000794e  jmp     loc_18000763C
0x180007953  mov     dword ptr [rsp+120h+var_E0+8], r15d
0x180007958  mov     ecx, 6
0x18000795d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180007963  nop
0x180007964  mov     r9d, ebx; char *
0x180007967  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x18000796e  mov     edx, 32Fh; void *
0x180007973  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007979  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180007980  mov     edx, 307h; void *
0x180007985  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000798b  mov     r9d, 80004005h; char *
0x180007991  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180007998  mov     edx, 30Eh; void *
0x18000799d  mov     rcx, rbx; this
0x1800079a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800079a6  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x1800079ad  mov     edx, 323h; void *
0x1800079b2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800079b8  mov     r9d, eax; char *
0x1800079bb  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x1800079c2  mov     edx, 317h; void *
0x1800079c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800079cd  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x1800079d4  mov     edx, 326h; void *
0x1800079d9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800079df  mov     ecx, esi
0x1800079e1  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800079e7  mov     ecx, 2
0x1800079ec  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800079f2  mov     ecx, esi
0x1800079f4  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```

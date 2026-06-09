# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180018248`
- end: `0x1800183a1`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180014ff0`

## callees

- `0x180013d6c`
- `0x180014070`
- `0x180018248`
- `0x1800183a8`
- `0x180018434`
- `0x180018454`
- `0x1800186a0`
- `0x1800186c0`
- `0x1800186e4`
- `0x180024b20`
- `0x180024b54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018325`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018325`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018387`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018387`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018352`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018352`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  char v10; // bl
  wil *v11; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
  }
  else
  {
    if ( a3 >= 0xC8 && ((int)a3 < 256 || a3 >= 0x200) )
      return;
    if ( (AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24)), v13 = (RTL_SRWLOCK *)v8, a3 <= 7)
      && (v9 = 204, _bittest(&v9, a3))
      || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    if ( !v10 )
      return;
  }
  if ( !wil::ProcessShutdownInProgress(v11) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
    if ( !*(_BYTE *)(a1 + 65) )
    {
      if ( !*(_QWORD *)(a1 + 48) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            (PVOID)a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)(a1 + 48), (_BYTE *)(a1 + 65), 300000);
    }
    if ( a1 != -32 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
  }
}

```

## disassembly

```asm
0x180018248  mov     [rsp+arg_8], rbx
0x18001824d  mov     [rsp+arg_10], rbp
0x180018252  push    rsi
0x180018253  push    rdi
0x180018254  push    r14
0x180018256  sub     rsp, 20h
0x18001825a  mov     r14, r9
0x18001825d  mov     ebx, r8d
0x180018260  mov     ebp, edx
0x180018262  mov     rdi, rcx
0x180018265  cmp     byte ptr [rcx], 0
0x180018268  jz      loc_18001838E
0x18001826e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180018273  test    al, al
0x180018275  jz      loc_18001838E
0x18001827b  mov     rsi, [rdi+18h]
0x18001827f  cmp     ebx, 0FEh
0x180018285  jz      loc_18001830D
0x18001828b  cmp     ebx, 0C8h
0x180018291  jb      short loc_1800182AB
0x180018293  cmp     ebx, 100h
0x180018299  jl      loc_18001838E
0x18001829f  cmp     ebx, 200h
0x1800182a5  jnb     loc_18001838E
0x1800182ab  mov     rcx, rsi; SRWLock
0x1800182ae  call    cs:__imp_AcquireSRWLockExclusive
0x1800182b4  mov     [rsp+38h+arg_0], rsi
0x1800182b9  cmp     ebx, 7
0x1800182bc  ja      short loc_1800182C8
0x1800182be  mov     eax, 0CCh
0x1800182c3  bt      eax, ebx
0x1800182c6  jb      short loc_1800182E8
0x1800182c8  lea     eax, [rbx-100h]
0x1800182ce  cmp     eax, 7Fh
0x1800182d1  jbe     short loc_1800182E8
0x1800182d3  mov     r9d, r14d
0x1800182d6  lea     rcx, [rsi+48h]
0x1800182da  mov     r8d, ebp
0x1800182dd  mov     edx, ebx
0x1800182df  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800182e4  mov     bl, al
0x1800182e6  jmp     short loc_1800182F9
0x1800182e8  mov     r8d, ebp
0x1800182eb  mov     edx, ebx
0x1800182ed  lea     rcx, [rsi+8]
0x1800182f1  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800182f6  mov     bl, [rsi+40h]
0x1800182f9  lea     rcx, [rsp+38h+arg_0]
0x1800182fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018303  test    bl, bl
0x180018305  jz      loc_18001838E
0x18001830b  jmp     short loc_180018315
0x18001830d  mov     rcx, rsi; SRWLock
0x180018310  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180018315  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001831a  test    al, al
0x18001831c  jnz     short loc_18001838E
0x18001831e  lea     rbx, [rdi+20h]
0x180018322  mov     rcx, rbx; SRWLock
0x180018325  call    cs:__imp_AcquireSRWLockExclusive
0x18001832b  cmp     byte ptr [rdi+41h], 0
0x18001832f  jnz     short loc_18001837F
0x180018331  lea     rsi, [rdi+30h]
0x180018335  cmp     qword ptr [rsi], 0
0x180018339  jnz     short loc_18001836D
0x18001833b  lea     rcx, [rsp+38h+arg_0]; this
0x180018340  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018345  xor     r8d, r8d; pcbe
0x180018348  mov     rdx, rdi; pv
0x18001834b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180018352  call    cs:__imp_CreateThreadpoolTimer
0x180018358  mov     rdx, rax
0x18001835b  mov     rcx, rsi
0x18001835e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180018363  lea     rcx, [rsp+38h+arg_0]; this
0x180018368  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001836d  mov     r8d, 493E0h
0x180018373  lea     rdx, [rdi+41h]
0x180018377  mov     rcx, rsi
0x18001837a  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001837f  test    rbx, rbx
0x180018382  jz      short loc_18001838E
0x180018384  mov     rcx, rbx; SRWLock
0x180018387  call    cs:__imp_ReleaseSRWLockExclusive
0x18001838d  nop
0x18001838e  mov     rbx, [rsp+38h+arg_8]
0x180018393  mov     rbp, [rsp+38h+arg_10]
0x180018398  add     rsp, 20h
0x18001839c  pop     r14
0x18001839e  pop     rdi
0x18001839f  pop     rsi
0x1800183a0  retn
```

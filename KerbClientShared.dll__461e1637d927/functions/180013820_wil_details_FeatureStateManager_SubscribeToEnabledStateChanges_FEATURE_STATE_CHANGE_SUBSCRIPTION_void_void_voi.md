# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180013820`
- end: `0x1800138e7`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180013e80`

## callees

- `0x18000db40`
- `0x180013820`
- `0x1800139e4`
- `0x1800144cc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013855`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013855`

## string_xrefs

- `0x180013880`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v10; // eax
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    v11 = v8;
    if ( this[18].Ptr
      || ((NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification,
           this[18].Ptr = 0,
           NtDllProcedureAddress)
       || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
           (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0)
        ? (v10 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))NtDllProcedureAddress)(
                   _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                   this,
                   0,
                   &this[18]))
        : (v10 = -1073741511),
          !v10) )
    {
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180013820  mov     [rsp+arg_8], rbx
0x180013825  mov     [rsp+arg_10], rbp
0x18001382a  push    rsi
0x18001382b  push    rdi
0x18001382c  push    r14
0x18001382e  sub     rsp, 30h
0x180013832  mov     qword ptr [rdx], 0
0x180013839  mov     rbp, r9
0x18001383c  cmp     byte ptr [rcx], 0
0x18001383f  mov     r14, r8
0x180013842  mov     rsi, rdx
0x180013845  mov     rdi, rcx
0x180013848  jz      loc_1800138D4
0x18001384e  lea     rbx, [rcx+20h]
0x180013852  mov     rcx, rbx; SRWLock
0x180013855  call    cs:__imp_AcquireSRWLockExclusive
0x18001385b  mov     [rsp+48h+arg_0], rbx
0x180013860  lea     rbx, [rdi+90h]
0x180013867  cmp     qword ptr [rbx], 0
0x18001386b  jnz     short loc_1800138B8
0x18001386d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180013874  mov     qword ptr [rbx], 0
0x18001387b  test    rax, rax
0x18001387e  jnz     short loc_18001389F
0x180013880  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180013887  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001388c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180013893  test    rax, rax
0x180013896  jnz     short loc_18001389F
0x180013898  mov     eax, 0C0000139h
0x18001389d  jmp     short loc_1800138B4
0x18001389f  mov     r9, rbx
0x1800138a2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800138a9  xor     r8d, r8d
0x1800138ac  mov     rdx, rdi
0x1800138af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b4  test    eax, eax
0x1800138b6  jnz     short loc_1800138CA
0x1800138b8  lea     rcx, [rdi+48h]; this
0x1800138bc  mov     r9, rbp; void *
0x1800138bf  mov     r8, r14; void (*)(void *)
0x1800138c2  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800138c5  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800138ca  lea     rcx, [rsp+48h+arg_0]
0x1800138cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800138d4  mov     rbx, [rsp+48h+arg_8]
0x1800138d9  mov     rbp, [rsp+48h+arg_10]
0x1800138de  add     rsp, 30h
0x1800138e2  pop     r14
0x1800138e4  pop     rdi
0x1800138e5  pop     rsi
0x1800138e6  retn
```

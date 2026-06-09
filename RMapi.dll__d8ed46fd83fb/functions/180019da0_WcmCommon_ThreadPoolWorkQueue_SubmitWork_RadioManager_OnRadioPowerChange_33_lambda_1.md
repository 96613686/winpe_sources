# WcmCommon::ThreadPoolWorkQueue::SubmitWork__RadioManager::OnRadioPowerChange_::_33_::_lambda_1___

- ea: `0x180019da0`
- end: `0x180019e28`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWork__RadioManager::OnRadioPowerChange_::_33_::_lambda_1___`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f6c0`

## callees

- `0x18000c2a4`
- `0x180019da0`
- `0x180019ff4`
- `0x18001a094`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019dbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019dbc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019e12`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019e12`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWork__RadioManager::OnRadioPowerChange_::_33_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rbx
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v5[0] = v4;
  if ( *(_BYTE *)(a1 + 272) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v5);
  }
  else
  {
    if ( *(_DWORD *)a1 == 1 )
      std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::_Emplace_back_internal__RadioManager::OnRadioPowerChange_::_33_::_lambda_1___(
        a1 + 152,
        a2);
    else
      std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::_Emplace_back_internal__RadioManager::OnRadioPowerChange_::_33_::_lambda_1___(
        a1 + 232,
        a2);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v5);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
  }
}

```

## disassembly

```asm
0x180019da0  mov     [rsp+arg_8], rbx
0x180019da5  mov     [rsp+arg_10], rsi
0x180019daa  push    rdi
0x180019dab  sub     rsp, 30h
0x180019daf  mov     rsi, rdx
0x180019db2  mov     rdi, rcx
0x180019db5  lea     rbx, [rcx+8]
0x180019db9  mov     rcx, rbx; lpCriticalSection
0x180019dbc  call    cs:__imp_EnterCriticalSection
0x180019dc2  mov     [rsp+38h+var_18], rbx
0x180019dc7  lea     rcx, [rdi+98h]
0x180019dce  cmp     byte ptr [rcx+78h], 0
0x180019dd2  jz      short loc_180019DE0
0x180019dd4  lea     rcx, [rsp+38h+var_18]
0x180019dd9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180019dde  jmp     short loc_180019E18
0x180019de0  mov     rdx, rsi
0x180019de3  cmp     dword ptr [rdi], 1
0x180019de6  jnz     short loc_180019DEF
0x180019de8  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void_________Emplace_back_internal__RadioManager__OnRadioPowerChange____33____lambda_1___
0x180019ded  jmp     short loc_180019DF9
0x180019def  add     rcx, 50h ; 'P'
0x180019df3  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult__________Emplace_back_internal__RadioManager__OnRadioPowerChange____33____lambda_1___
0x180019df8  nop
0x180019df9  lea     rcx, [rsp+38h+var_18]
0x180019dfe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180019e03  lock inc qword ptr [rdi+88h]
0x180019e0b  mov     rcx, [rdi+80h]; pwk
0x180019e12  call    cs:__imp_SubmitThreadpoolWork
0x180019e18  mov     rbx, [rsp+38h+arg_8]
0x180019e1d  mov     rsi, [rsp+38h+arg_10]
0x180019e22  add     rsp, 30h
0x180019e26  pop     rdi
0x180019e27  retn
```

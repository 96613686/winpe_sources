# Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18001956c`
- end: `0x1800197e5`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `633`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a770`

## callees

- `0x1800021c0`
- `0x1800021e4`
- `0x180018d30`
- `0x18001956c`
- `0x180019b9c`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001979f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800197de`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001979f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800197de`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800196a8`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800196a8`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800196d1`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800196d1`
- `msvcp_win!_Cnd_broadcast` at `0x1800197bc`
- `msvcp_win!_Cnd_broadcast` at `0x1800197bc`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800196b8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800196b8`
- `msvcp_win!_Mtx_unlock` at `0x18001973b`
- `msvcp_win!_Mtx_unlock` at `0x18001976c`
- `msvcp_win!_Mtx_unlock` at `0x1800197c6`
- `msvcp_win!_Mtx_unlock` at `0x18001973b`
- `msvcp_win!_Mtx_unlock` at `0x18001976c`
- `msvcp_win!_Mtx_unlock` at `0x1800197c6`
- `msvcp_win!_Mtx_lock` at `0x18001970d`
- `msvcp_win!_Mtx_lock` at `0x18001977d`
- `msvcp_win!_Mtx_lock` at `0x18001970d`
- `msvcp_win!_Mtx_lock` at `0x18001977d`

## pseudocode

```c
void __fastcall __Init____InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__QEBAXU_TypeSelectorNoAsync_details_3__Z(
        __int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  _BYTE *v4; // rcx
  _BYTE *v5; // rdx
  _QWORD *v6; // rdx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  char v8; // si
  _BYTE *v9; // rdx
  struct _Mtx_internal_imp_t *v10; // rcx
  _QWORD v11[7]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v12; // [rsp+78h] [rbp-88h]
  _BYTE v13[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v14; // [rsp+B8h] [rbp-48h]
  _BYTE v15[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z; // [rsp+F8h] [rbp-8h]

  v2 = *(_QWORD *)(a1 + 8);
  v11[0] = ___7___Func_impl_no_alloc_V_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__6B_;
  v11[1] = *(_QWORD *)(a1 + 24);
  v12 = v11;
  DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z = 0;
  DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z = (_BYTE *)__Move____Func_impl_no_alloc_V_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z(v11, v15);
  v14 = 0;
  v3 = operator new(0x48u);
  *v3 = ___7___Func_impl_no_alloc_V_lambda_1___1___MakeVoidToUnitFunc_details_Concurrency__YA_AV__function___A6AEXZ_std__AEBV__function___A6AXXZ_6__Z_E__V_std__6B_;
  v3[8] = 0;
  v4 = DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z;
  if ( DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z )
  {
    v3[8] = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z)(
              DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z,
              v3 + 1);
    v4 = DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z;
  }
  v14 = v3;
  if ( v4 )
  {
    v5 = v15;
    LOBYTE(v5) = v4 != v15;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v4 + 32LL))(v4, v5);
    DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_X__V_std__EEAAPEAV___Func_base_X__V_2_PEAX_Z = 0;
  }
  if ( v12 )
  {
    v6 = v11;
    LOBYTE(v6) = v12 != v11;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v12 + 32LL))(v12, v6);
    v12 = 0;
  }
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  if ( !v14 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v8 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v14 + 16LL))(v14);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  if ( v14 )
  {
    v9 = v13;
    LOBYTE(v9) = v14 != v13;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v14 + 32LL))(v14, v9);
    v14 = 0;
  }
  *(_BYTE *)(v2 + 368) = v8;
  if ( _Mtx_lock((_Mtx_t)(v2 + 32)) )
    goto LABEL_23;
  if ( *(_DWORD *)(v2 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 108) = 2147483646;
    goto LABEL_19;
  }
  v10 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v10);
    return;
  }
  *(_DWORD *)(v2 + 8) = 3;
  _Mtx_unlock(v10);
  if ( _Mtx_lock((_Mtx_t)(v2 + 208)) )
  {
LABEL_23:
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x1800197E4LL);
  }
  if ( *(_DWORD *)(v2 + 284) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 284) = 2147483646;
LABEL_19:
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( *(int *)(v2 + 312) < 2 )
    *(_DWORD *)(v2 + 312) = 2;
  _Cnd_broadcast((_Cnd_t)(v2 + 136));
  _Mtx_unlock((_Mtx_t)(v2 + 208));
  Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
}

```

## disassembly

```asm
0x18001956c  mov     [rsp-8+arg_8], rbx
0x180019571  mov     [rsp-8+arg_10], rsi
0x180019576  push    rbp
0x180019577  push    rdi
0x180019578  push    r14
0x18001957a  lea     rbp, [rsp-10h]
0x18001957f  sub     rsp, 110h
0x180019586  mov     rax, cs:__security_cookie
0x18001958d  xor     rax, rsp
0x180019590  mov     [rbp+20h+var_20], rax
0x180019594  mov     r14, rcx
0x180019597  mov     rdi, [rcx+8]
0x18001959b  lea     rax, [rbp+20h+var_A0]
0x18001959f  mov     [rsp+120h+var_100], rax
0x1800195a4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,void,>::`vftable'
0x1800195ab  mov     [rsp+120h+var_E0], rax
0x1800195b0  mov     rax, [rcx+18h]
0x1800195b4  mov     [rsp+120h+var_D8], rax
0x1800195b9  lea     rax, [rsp+120h+var_E0]
0x1800195be  mov     [rsp+120h+var_A8], rax
0x1800195c3  lea     rax, [rsp+120h+var_E0]
0x1800195c8  mov     [rsp+120h+var_F8], rax
0x1800195cd  mov     [rbp+20h+var_28], 0
0x1800195d5  lea     rdx, [rbp+20h+var_60]
0x1800195d9  lea     rcx, [rsp+120h+var_E0]
0x1800195de  call    ?_Move@?$_Func_impl_no_alloc@V_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@X$$V@std@@EEAAPEAV?$_Func_base@X$$V@2@PEAX@Z; std::_Func_impl_no_alloc<`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,void,>::_Move(void *)
0x1800195e3  mov     [rbp+20h+var_28], rax
0x1800195e7  mov     [rbp+20h+var_68], 0
0x1800195ef  mov     ecx, 48h ; 'H'; Size
0x1800195f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800195f9  mov     rbx, rax
0x1800195fc  mov     [rsp+120h+var_F0], rax
0x180019601  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@6@@Z@E$$V@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)'::`2'::_lambda_1_,uchar,>::`vftable'
0x180019608  mov     [rbx], rax
0x18001960b  lea     rsi, [rbx+8]
0x18001960f  mov     [rsp+120h+var_E8], rsi
0x180019614  mov     qword ptr [rsi+38h], 0
0x18001961c  mov     rcx, [rbp+20h+var_28]
0x180019620  test    rcx, rcx
0x180019623  jz      short loc_18001963B
0x180019625  mov     rax, [rcx]
0x180019628  mov     rdx, rsi
0x18001962b  mov     rax, [rax]
0x18001962e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019633  mov     [rsi+38h], rax
0x180019637  mov     rcx, [rbp+20h+var_28]
0x18001963b  mov     [rbp+20h+var_68], rbx
0x18001963f  test    rcx, rcx
0x180019642  jz      short loc_180019662
0x180019644  mov     rax, [rcx]
0x180019647  lea     rdx, [rbp+20h+var_60]
0x18001964b  cmp     rcx, rdx
0x18001964e  setnz   dl
0x180019651  mov     rax, [rax+20h]
0x180019655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001965a  mov     [rbp+20h+var_28], 0
0x180019662  mov     rcx, [rsp+120h+var_A8]
0x180019667  test    rcx, rcx
0x18001966a  jz      short loc_18001968C
0x18001966c  mov     rax, [rcx]
0x18001966f  lea     rdx, [rsp+120h+var_E0]
0x180019674  cmp     rcx, rdx
0x180019677  setnz   dl
0x18001967a  mov     rax, [rax+20h]
0x18001967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019683  mov     [rsp+120h+var_A8], 0
0x18001968c  lea     rax, [rbp+20h+var_A0]
0x180019690  mov     [rsp+120h+var_E8], rax
0x180019695  mov     rbx, [r14+8]
0x180019699  add     rbx, 160h
0x1800196a0  mov     [rsp+120h+var_F0], rbx
0x1800196a5  mov     rcx, rbx
0x1800196a8  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1800196ae  nop
0x1800196af  mov     rcx, [rbp+20h+var_68]
0x1800196b3  test    rcx, rcx
0x1800196b6  jnz     short loc_1800196BF
0x1800196b8  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800196be  int     3; Trap to Debugger
0x1800196bf  mov     rax, [rcx]
0x1800196c2  mov     rax, [rax+10h]
0x1800196c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196cb  mov     sil, al
0x1800196ce  mov     rcx, rbx
0x1800196d1  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800196d7  nop
0x1800196d8  mov     rcx, [rbp+20h+var_68]
0x1800196dc  test    rcx, rcx
0x1800196df  jz      short loc_1800196FF
0x1800196e1  mov     rdx, [rcx]
0x1800196e4  mov     rax, [rdx+20h]
0x1800196e8  lea     rdx, [rbp+20h+var_A0]
0x1800196ec  cmp     rcx, rdx
0x1800196ef  setnz   dl
0x1800196f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f7  mov     [rbp+20h+var_68], 0
0x1800196ff  mov     [rdi+170h], sil
0x180019706  lea     rbx, [rdi+20h]
0x18001970a  mov     rcx, rbx; _Mtx_t
0x18001970d  call    cs:__imp__Mtx_lock
0x180019713  test    eax, eax
0x180019715  jnz     loc_1800197D9
0x18001971b  mov     eax, [rbx+4Ch]
0x18001971e  mov     r14d, 7FFFFFFFh
0x180019724  cmp     eax, r14d
0x180019727  jnz     short loc_180019730
0x180019729  dec     eax
0x18001972b  mov     [rbx+4Ch], eax
0x18001972e  jmp     short loc_18001979A
0x180019730  mov     eax, [rdi+8]
0x180019733  mov     rcx, rbx; _Mtx_t
0x180019736  cmp     eax, 4
0x180019739  jnz     short loc_180019765
0x18001973b  call    cs:__imp__Mtx_unlock
0x180019741  mov     rcx, [rbp+20h+var_20]
0x180019745  xor     rcx, rsp; StackCookie
0x180019748  call    __security_check_cookie
0x18001974d  lea     r11, [rsp+120h+var_10]
0x180019755  mov     rbx, [r11+28h]
0x180019759  mov     rsi, [r11+30h]
0x18001975d  mov     rsp, r11
0x180019760  pop     r14
0x180019762  pop     rdi
0x180019763  pop     rbp
0x180019764  retn
0x180019765  mov     dword ptr [rdi+8], 3
0x18001976c  call    cs:__imp__Mtx_unlock
0x180019772  lea     rsi, [rdi+88h]
0x180019779  lea     rcx, [rsi+48h]; _Mtx_t
0x18001977d  call    cs:__imp__Mtx_lock
0x180019783  test    eax, eax
0x180019785  jnz     short loc_1800197D9
0x180019787  mov     eax, [rsi+94h]
0x18001978d  cmp     eax, r14d
0x180019790  jnz     short loc_1800197A6
0x180019792  dec     eax
0x180019794  mov     [rsi+94h], eax
0x18001979a  mov     ecx, 6
0x18001979f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800197a5  int     3; Trap to Debugger
0x1800197a6  cmp     dword ptr [rsi+0B0h], 2
0x1800197ad  jge     short loc_1800197B9
0x1800197af  mov     dword ptr [rsi+0B0h], 2
0x1800197b9  mov     rcx, rsi; _Cnd_t
0x1800197bc  call    cs:__imp__Cnd_broadcast
0x1800197c2  lea     rcx, [rsi+48h]; _Mtx_t
0x1800197c6  call    cs:__imp__Mtx_unlock
0x1800197cc  mov     rcx, rdi; this
0x1800197cf  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x1800197d4  jmp     loc_180019741
0x1800197d9  mov     ecx, 5
0x1800197de  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

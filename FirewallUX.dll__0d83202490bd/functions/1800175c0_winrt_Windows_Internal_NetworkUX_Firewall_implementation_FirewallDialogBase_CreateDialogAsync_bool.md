# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)

- ea: `0x1800175c0`
- end: `0x1800176dd`
- name: `?CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z`
- size: `285`
- prototype: `void __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase *this, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001815c`
- `0x18001fd60`

## callees

- `0x1800021e4`
- `0x18001510c`
- `0x1800175c0`
- `0x18001a200`
- `0x18002d010`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase *this,
        char a2)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  __int128 v7; // [rsp+20h] [rbp-30h] BYREF
  __int64 v8; // [rsp+30h] [rbp-20h]
  char v9; // [rsp+38h] [rbp-18h]
  char v10; // [rsp+40h] [rbp-10h]
  void *v11; // [rsp+60h] [rbp+10h]
  char v12; // [rsp+68h] [rbp+18h] BYREF

  v12 = a2;
  *(_QWORD *)&v7 = this;
  *((_QWORD *)&v7 + 1) = &v12;
  v11 = operator new(0x120u);
  v2 = ____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__1__Z(
         (__int64)v11,
         &v7);
  v4 = v2;
  v8 = v2;
  v9 = 0;
  v10 = 0;
  if ( !v2 )
    std::_Throw_future_error2(4);
  BYTE8(v7) = 1;
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) == 1 )
  {
    v5 = *(void (__fastcall ****)(_QWORD, __int64))(v2 + 200);
    if ( v5 )
      (**v5)(v5, v2);
    else
      (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
  }
  *(_QWORD *)&v7 = 0;
  v8 = v4;
  v9 = 1;
  if ( *(_BYTE *)(v4 + 184) )
    std::_Throw_future_error2(4);
  LOBYTE(v3) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 16LL))(v4, v3);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 )
  {
    v6 = *(void (__fastcall ****)(_QWORD, __int64))(v4 + 200);
    if ( v6 )
      (**v6)(v6, v4);
    else
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
  }
}

```

## disassembly

```asm
0x1800175c0  mov     [rsp-8+arg_10], rbx
0x1800175c5  mov     [rsp-8+arg_8], dl
0x1800175c9  push    rbp
0x1800175ca  mov     rbp, rsp
0x1800175cd  sub     rsp, 50h
0x1800175d1  mov     [rbp+var_30], rcx
0x1800175d5  lea     rax, [rbp+arg_8]
0x1800175d9  mov     [rbp+var_28], rax
0x1800175dd  mov     ecx, 120h; Size
0x1800175e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800175e7  mov     [rbp+arg_0], rax
0x1800175eb  lea     rdx, [rbp+var_30]
0x1800175ef  mov     rcx, rax
0x1800175f2  call    ??$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@1@@Z; std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)
0x1800175f7  mov     rbx, rax
0x1800175fa  mov     [rbp+var_20], rax
0x1800175fe  mov     [rbp+var_18], 0
0x180017602  mov     [rbp+var_10], 0
0x180017606  test    rax, rax
0x180017609  jz      loc_1800176D2
0x18001760f  mov     byte ptr [rbp+var_28], 1
0x180017613  lock inc dword ptr [rax+8]
0x180017617  or      eax, 0FFFFFFFFh
0x18001761a  lock xadd [rbx+8], eax
0x18001761f  cmp     eax, 1
0x180017622  jnz     short loc_180017654
0x180017624  mov     rcx, [rbx+0C8h]
0x18001762b  test    rcx, rcx
0x18001762e  jz      short loc_180017640
0x180017630  mov     rax, [rcx]
0x180017633  mov     rdx, rbx
0x180017636  mov     rax, [rax]
0x180017639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001763e  jmp     short loc_180017654
0x180017640  mov     rax, [rbx]
0x180017643  mov     edx, 1
0x180017648  mov     rcx, rbx
0x18001764b  mov     rax, [rax]
0x18001764e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017653  nop
0x180017654  mov     [rbp+var_30], 0
0x18001765c  mov     [rbp+var_20], rbx
0x180017660  mov     [rbp+var_18], 1
0x180017664  cmp     byte ptr [rbx+0B8h], 0
0x18001766b  jnz     short loc_1800176C7
0x18001766d  mov     rax, [rbx]
0x180017670  mov     dl, 1
0x180017672  mov     rcx, rbx
0x180017675  mov     rax, [rax+10h]
0x180017679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001767e  nop
0x18001767f  or      eax, 0FFFFFFFFh
0x180017682  lock xadd [rbx+8], eax
0x180017687  cmp     eax, 1
0x18001768a  jnz     short loc_1800176BC
0x18001768c  mov     rcx, [rbx+0C8h]
0x180017693  test    rcx, rcx
0x180017696  jz      short loc_1800176A8
0x180017698  mov     rax, [rcx]
0x18001769b  mov     rdx, rbx
0x18001769e  mov     rax, [rax]
0x1800176a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176a6  jmp     short loc_1800176BC
0x1800176a8  mov     rax, [rbx]
0x1800176ab  mov     edx, 1
0x1800176b0  mov     rcx, rbx
0x1800176b3  mov     rax, [rax]
0x1800176b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176bb  nop
0x1800176bc  mov     rbx, [rsp+50h+arg_10]
0x1800176c1  add     rsp, 50h
0x1800176c5  pop     rbp
0x1800176c6  retn
0x1800176c7  mov     ecx, 4
0x1800176cc  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800176d2  mov     ecx, 4
0x1800176d7  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```

# _Concurrency::details::_Task_impl_base::_Wait_::_1_::catch$4

- ea: `0x18002b4eb`
- end: `0x18002b53a`
- name: `_Concurrency::details::_Task_impl_base::_Wait_::_1_::catch$4`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f3b0`
- `0x1800168a0`
- `0x180018ac4`
- `0x180019544`
- `0x180019b28`
- `0x18001a5dc`
- `0x18002b4eb`

## pseudocode

```c
void __fastcall __noreturn Concurrency::details::_Task_impl_base::_Wait_::_1_::catch_4(__int64 a1, __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx
  const struct std::exception_ptr *v4; // rax
  Concurrency::details::_ExceptionHolder *v5; // rax

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 80);
  if ( !Concurrency::details::_Task_impl_base::_HasUserException(v3) )
  {
    v4 = (const struct std::exception_ptr *)std::current_exception((_QWORD *)(a2 + 32));
    Concurrency::details::_Task_impl_base::_CancelWithException(v3, v4);
    std::exception_ptr::~exception_ptr((std::exception_ptr *)(a2 + 32));
  }
  v5 = (Concurrency::details::_ExceptionHolder *)winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::operator->((__int64)v3 + 16);
  Concurrency::details::_ExceptionHolder::_RethrowUserException(v5);
}

```

## disassembly

```asm
0x18002b4eb  mov     [rsp+arg_8], rdx
0x18002b4f0  push    rbx
0x18002b4f1  push    rbp
0x18002b4f2  sub     rsp, 28h
0x18002b4f6  mov     rbp, rdx
0x18002b4f9  mov     rbx, [rbp+50h]
0x18002b4fd  mov     rcx, rbx; this
0x18002b500  call    ?_HasUserException@_Task_impl_base@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl_base::_HasUserException(void)
0x18002b505  test    al, al
0x18002b507  jnz     short loc_18002B528
0x18002b509  lea     rcx, [rbp+20h]
0x18002b50d  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x18002b512  nop
0x18002b513  mov     rdx, rax; struct std::exception_ptr *
0x18002b516  mov     rcx, rbx; this
0x18002b519  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18002b51e  nop
0x18002b51f  lea     rcx, [rbp+20h]; this
0x18002b523  call    ??1exception_ptr@std@@QEAA@XZ; std::exception_ptr::~exception_ptr(void)
0x18002b528  lea     rcx, [rbx+10h]
0x18002b52c  call    ??C?$com_ptr@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@QEBA@XZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::operator->(void)
0x18002b531  mov     rcx, rax; this
0x18002b534  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
```

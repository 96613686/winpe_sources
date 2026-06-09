# _Concurrency::details::_Task_impl_base::_Wait_::_1_::catch$4

- ea: `0x18001854d`
- end: `0x18001859c`
- name: `_Concurrency::details::_Task_impl_base::_Wait_::_1_::catch$4`
- size: `79`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000ec28`
- `0x180010128`
- `0x180011744`
- `0x180012114`
- `0x180012704`
- `0x180012db0`
- `0x18001854d`

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
  v5 = (Concurrency::details::_ExceptionHolder *)std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator-><Concurrency::details::_ExceptionHolder,0>((char *)v3 + 16);
  Concurrency::details::_ExceptionHolder::_RethrowUserException(v5);
}

```

## disassembly

```asm
0x18001854d  mov     [rsp+arg_8], rdx
0x180018552  push    rbx
0x180018553  push    rbp
0x180018554  sub     rsp, 28h
0x180018558  mov     rbp, rdx
0x18001855b  mov     rbx, [rbp+50h]
0x18001855f  mov     rcx, rbx; this
0x180018562  call    ?_HasUserException@_Task_impl_base@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl_base::_HasUserException(void)
0x180018567  test    al, al
0x180018569  jnz     short loc_18001858A
0x18001856b  lea     rcx, [rbp+20h]
0x18001856f  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x180018574  nop
0x180018575  mov     rdx, rax; struct std::exception_ptr *
0x180018578  mov     rcx, rbx; this
0x18001857b  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180018580  nop
0x180018581  lea     rcx, [rbp+20h]; this
0x180018585  call    ??1exception_ptr@std@@QEAA@XZ; std::exception_ptr::~exception_ptr(void)
0x18001858a  lea     rcx, [rbx+10h]
0x18001858e  call    ??$?CU_ExceptionHolder@details@Concurrency@@$0A@@?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEBAPEAU_ExceptionHolder@details@Concurrency@@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator-><Concurrency::details::_ExceptionHolder,0>(void)
0x180018593  mov     rcx, rax; this
0x180018596  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
```

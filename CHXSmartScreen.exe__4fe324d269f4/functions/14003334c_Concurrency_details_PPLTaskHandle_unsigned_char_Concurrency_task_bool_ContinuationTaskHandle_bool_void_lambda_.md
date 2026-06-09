# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::operator()_::_1_::catch$7

- ea: `0x14003334c`
- end: `0x1400333af`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::operator()_::_1_::catch$7`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14001a96c`

## import_xrefs

- `msvcrt!__ExceptionPtrDestroy` at `0x140033396`
- `msvcrt!__ExceptionPtrDestroy` at `0x140033396`
- `msvcrt!__ExceptionPtrCurrentException` at `0x14003337e`
- `msvcrt!__ExceptionPtrCurrentException` at `0x14003337e`
- `msvcrt!__ExceptionPtrCreate` at `0x14003336d`
- `msvcrt!__ExceptionPtrCreate` at `0x14003336d`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::operator()_::_1_::catch_7(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 48) + 48LL);
  *(_OWORD *)(a2 + 48) = 0;
  __ExceptionPtrCreate((void *)(a2 + 48));
  *(_DWORD *)(a2 + 64) = 2;
  __ExceptionPtrCurrentException((void *)(a2 + 48));
  Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 48));
  __ExceptionPtrDestroy((void *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x14003334c  mov     [rsp+arg_8], rdx
0x140033351  push    rbx
0x140033352  push    rbp
0x140033353  sub     rsp, 38h
0x140033357  mov     rbp, rdx
0x14003335a  mov     rax, [rbp+30h]
0x14003335e  mov     rbx, [rax+30h]
0x140033362  xorps   xmm0, xmm0
0x140033365  movups  xmmword ptr [rbp+30h], xmm0
0x140033369  lea     rcx, [rbp+30h]
0x14003336d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x140033373  mov     dword ptr [rbp+40h], 2
0x14003337a  lea     rcx, [rbp+30h]
0x14003337e  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x140033384  nop
0x140033385  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x140033389  mov     rcx, rbx; this
0x14003338c  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x140033391  nop
0x140033392  lea     rcx, [rbp+30h]
0x140033396  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x14003339c  nop
0x14003339d  mov     rax, 0
0x1400333a7  add     rsp, 38h
0x1400333ab  pop     rbp
0x1400333ac  pop     rbx
0x1400333ad  retn
```

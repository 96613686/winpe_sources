# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency::details::_TypeSelectorNoAsync__pplx::details::_UnrealizedChore_::operator()_::_1_::catch$7

- ea: `0x140033435`
- end: `0x140033498`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency::details::_TypeSelectorNoAsync__pplx::details::_UnrealizedChore_::operator()_::_1_::catch$7`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14001a96c`

## import_xrefs

- `msvcrt!__ExceptionPtrDestroy` at `0x14003347f`
- `msvcrt!__ExceptionPtrDestroy` at `0x14003347f`
- `msvcrt!__ExceptionPtrCurrentException` at `0x140033467`
- `msvcrt!__ExceptionPtrCurrentException` at `0x140033467`
- `msvcrt!__ExceptionPtrCreate` at `0x140033456`
- `msvcrt!__ExceptionPtrCreate` at `0x140033456`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency::details::_TypeSelectorNoAsync__pplx::details::_UnrealizedChore_::operator()_::_1_::catch_7(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 48) + 24LL);
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
0x140033435  mov     [rsp+arg_8], rdx
0x14003343a  push    rbx
0x14003343b  push    rbp
0x14003343c  sub     rsp, 38h
0x140033440  mov     rbp, rdx
0x140033443  mov     rax, [rbp+30h]
0x140033447  mov     rbx, [rax+18h]
0x14003344b  xorps   xmm0, xmm0
0x14003344e  movups  xmmword ptr [rbp+30h], xmm0
0x140033452  lea     rcx, [rbp+30h]
0x140033456  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14003345c  mov     dword ptr [rbp+40h], 2
0x140033463  lea     rcx, [rbp+30h]
0x140033467  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x14003346d  nop
0x14003346e  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x140033472  mov     rcx, rbx; this
0x140033475  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x14003347a  nop
0x14003347b  lea     rcx, [rbp+30h]
0x14003347f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x140033485  nop
0x140033486  mov     rax, 0
0x140033490  add     rsp, 38h
0x140033494  pop     rbp
0x140033495  pop     rbx
0x140033496  retn
```

# __lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch$14

- ea: `0x180018039`
- end: `0x180018092`
- name: `__lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch$14`
- size: `89`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180011744`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180018057`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180018057`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180018061`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180018061`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018079`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018079`

## pseudocode

```c
__int64 __fastcall _lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch_14(__int64 a1, __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 32);
  *(_OWORD *)(a2 + 48) = 0;
  __ExceptionPtrCreate((void *)(a2 + 48));
  __ExceptionPtrCurrentException((void *)(a2 + 48));
  Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 48));
  __ExceptionPtrDestroy((void *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x180018039  mov     [rsp+arg_8], rdx
0x18001803e  push    rbx
0x18001803f  push    rbp
0x180018040  sub     rsp, 28h
0x180018044  mov     rbp, rdx
0x180018047  mov     rbx, [rbp+20h]
0x18001804b  xorps   xmm0, xmm0
0x18001804e  movdqu  xmmword ptr [rbp+30h], xmm0
0x180018053  lea     rcx, [rbp+30h]
0x180018057  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001805d  lea     rcx, [rbp+30h]
0x180018061  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180018067  nop
0x180018068  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x18001806c  mov     rcx, rbx; this
0x18001806f  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180018074  nop
0x180018075  lea     rcx, [rbp+30h]
0x180018079  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001807f  nop
0x180018080  mov     rax, 0
0x18001808a  add     rsp, 28h
0x18001808e  pop     rbp
0x18001808f  pop     rbx
0x180018090  retn
```

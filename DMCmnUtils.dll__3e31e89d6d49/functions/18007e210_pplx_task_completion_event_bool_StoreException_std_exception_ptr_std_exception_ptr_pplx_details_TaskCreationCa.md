# pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)

- ea: `0x18007e210`
- end: `0x18007e2d5`
- name: `??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007cb30`

## callees

- `0x180009200`
- `0x1800092d0`
- `0x18006f824`
- `0x18007e210`
- `0x180085308`
- `0x18008f77c`
- `0x180090f24`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18007e2b9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18007e2b9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18007e266`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18007e266`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(
        __int64 a1,
        void *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  __int64 v7; // rax
  char v8; // bl
  __int128 v10; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v11[40]; // [rsp+30h] [rbp-28h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)a1 + 24LL);
  pplx::details::critical_section_impl::lock(v6);
  if ( (unsigned __int8)pplx::task_completion_event<unsigned __int64>::_IsTriggered(a1)
    || *(_QWORD *)(*(_QWORD *)a1 + 96LL) )
  {
    pplx::details::critical_section_impl::unlock(v6);
    v8 = 0;
  }
  else
  {
    v10 = 0;
    __ExceptionPtrCopy(&v10, a2);
    v7 = pplx::task_completion_event<unsigned __int64>::_ToExceptionHolder(v11, &v10, a3);
    std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(*(_QWORD *)a1 + 96LL, v7);
    std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v11);
    pplx::details::critical_section_impl::unlock(v6);
    v8 = 1;
  }
  __ExceptionPtrDestroy(a2);
  return v8;
}

```

## disassembly

```asm
0x18007e210  mov     [rsp+arg_10], rbx
0x18007e215  mov     [rsp+arg_8], rdx
0x18007e21a  push    rbp
0x18007e21b  push    rsi
0x18007e21c  push    rdi
0x18007e21d  sub     rsp, 40h
0x18007e221  mov     rbp, r8
0x18007e224  mov     rsi, rdx
0x18007e227  mov     rdi, rcx
0x18007e22a  mov     rbx, [rcx]
0x18007e22d  add     rbx, 18h
0x18007e231  mov     [rsp+58h+arg_0], rbx
0x18007e236  mov     rcx, rbx; lpCriticalSection
0x18007e239  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x18007e23e  nop
0x18007e23f  mov     rcx, rdi
0x18007e242  call    ?_IsTriggered@?$task_completion_event@_K@pplx@@QEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_IsTriggered(void)
0x18007e247  test    al, al
0x18007e249  jnz     short loc_18007E2AB
0x18007e24b  mov     rax, [rdi]
0x18007e24e  cmp     qword ptr [rax+60h], 0
0x18007e253  jnz     short loc_18007E2AB
0x18007e255  xorps   xmm0, xmm0
0x18007e258  movdqu  [rsp+58h+var_38], xmm0
0x18007e25e  mov     rdx, rsi
0x18007e261  lea     rcx, [rsp+58h+var_38]
0x18007e266  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18007e26d  nop     dword ptr [rax+rax+00h]
0x18007e272  mov     r8, rbp
0x18007e275  lea     rdx, [rsp+58h+var_38]
0x18007e27a  lea     rcx, [rsp+58h+var_28]
0x18007e27f  call    ?_ToExceptionHolder@?$task_completion_event@_K@pplx@@CA?AV?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@Vexception_ptr@4@AEBV_TaskCreationCallstack@details@2@@Z; pplx::task_completion_event<unsigned __int64>::_ToExceptionHolder(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x18007e284  mov     rcx, [rdi]
0x18007e287  add     rcx, 60h ; '`'
0x18007e28b  mov     rdx, rax
0x18007e28e  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18007e293  lea     rcx, [rsp+58h+var_28]
0x18007e298  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x18007e29d  nop
0x18007e29e  mov     rcx, rbx; lpCriticalSection
0x18007e2a1  call    ?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x18007e2a6  nop
0x18007e2a7  mov     bl, 1
0x18007e2a9  jmp     short loc_18007E2B6
0x18007e2ab  mov     rcx, rbx; lpCriticalSection
0x18007e2ae  call    ?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x18007e2b3  nop
0x18007e2b4  xor     ebx, ebx
0x18007e2b6  mov     rcx, rsi
0x18007e2b9  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18007e2c0  nop     dword ptr [rax+rax+00h]
0x18007e2c5  mov     al, bl
0x18007e2c7  mov     rbx, [rsp+58h+arg_10]
0x18007e2cc  add     rsp, 40h
0x18007e2d0  pop     rdi
0x18007e2d1  pop     rsi
0x18007e2d2  pop     rbp
0x18007e2d3  retn
```

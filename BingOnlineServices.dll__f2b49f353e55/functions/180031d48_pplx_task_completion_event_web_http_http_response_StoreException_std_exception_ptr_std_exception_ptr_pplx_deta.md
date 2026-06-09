# pplx::task_completion_event<web::http::http_response>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)

- ea: `0x180031d48`
- end: `0x180031e0a`
- name: `??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@Vhttp_response@http@web@@@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `194`
- prototype: `char __fastcall(__int64 *, void *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a2bc`

## callees

- `0x180012d44`
- `0x1800148ac`
- `0x180022cdc`
- `0x180031d48`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031dc0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031df7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031dc0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031df7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180031d9d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180031d9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031d71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031ded`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031ded`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall pplx::task_completion_event<web::http::http_response>::_StoreException<std::exception_ptr>(
        __int64 *a1,
        void *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  __int64 v7; // rax
  char v8; // bl
  __int128 v10; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v11[8]; // [rsp+30h] [rbp-10h] BYREF
  std::_Ref_count_base *v12; // [rsp+38h] [rbp-8h]

  v6 = (struct _RTL_CRITICAL_SECTION *)(*a1 + 24);
  EnterCriticalSection(v6);
  v7 = *a1;
  if ( *(_BYTE *)(*a1 + 120) || *(_BYTE *)(v7 + 121) || *(_QWORD *)(v7 + 104) )
  {
    v8 = 0;
  }
  else
  {
    v10 = 0;
    __ExceptionPtrCopy(&v10, a2);
    std::make_shared<pplx::details::_ExceptionHolder,std::exception_ptr &,pplx::details::_TaskCreationCallstack const &>(
      v11,
      &v10,
      a3);
    __ExceptionPtrDestroy(&v10);
    std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(*a1 + 104, v11);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    v8 = 1;
  }
  LeaveCriticalSection(v6);
  __ExceptionPtrDestroy(a2);
  return v8;
}

```

## disassembly

```asm
0x180031d48  mov     [rsp-28h+arg_8], rdx
0x180031d4d  push    rbp
0x180031d4e  push    rbx
0x180031d4f  push    rsi
0x180031d50  push    rdi
0x180031d51  push    r14
0x180031d53  mov     rbp, rsp
0x180031d56  sub     rsp, 40h
0x180031d5a  mov     r14, r8
0x180031d5d  mov     rsi, rdx
0x180031d60  mov     rbx, rcx
0x180031d63  mov     rdi, [rcx]
0x180031d66  add     rdi, 18h
0x180031d6a  mov     [rbp+arg_0], rdi
0x180031d6e  mov     rcx, rdi; lpCriticalSection
0x180031d71  call    cs:__imp_EnterCriticalSection
0x180031d77  nop
0x180031d78  mov     rax, [rbx]
0x180031d7b  cmp     byte ptr [rax+78h], 0
0x180031d7f  jnz     short loc_180031DE8
0x180031d81  cmp     byte ptr [rax+79h], 0
0x180031d85  jnz     short loc_180031DE8
0x180031d87  cmp     qword ptr [rax+68h], 0
0x180031d8c  jnz     short loc_180031DE8
0x180031d8e  xorps   xmm0, xmm0
0x180031d91  movdqu  [rbp+var_20], xmm0
0x180031d96  mov     rdx, rsi
0x180031d99  lea     rcx, [rbp+var_20]
0x180031d9d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180031da3  lea     rax, [rbp+var_20]
0x180031da7  mov     [rbp+arg_18], rax
0x180031dab  mov     r8, r14
0x180031dae  lea     rdx, [rbp+var_20]
0x180031db2  lea     rcx, [rbp+var_10]
0x180031db6  call    ??$make_shared@U_ExceptionHolder@details@pplx@@AEAVexception_ptr@std@@AEBV_TaskCreationCallstack@23@@std@@YA?AV?$shared_ptr@U_ExceptionHolder@details@pplx@@@0@AEAVexception_ptr@0@AEBV_TaskCreationCallstack@details@pplx@@@Z; std::make_shared<pplx::details::_ExceptionHolder,std::exception_ptr &,pplx::details::_TaskCreationCallstack const &>(std::exception_ptr &,pplx::details::_TaskCreationCallstack const &)
0x180031dbb  nop
0x180031dbc  lea     rcx, [rbp+var_20]
0x180031dc0  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180031dc6  mov     rcx, [rbx]
0x180031dc9  add     rcx, 68h ; 'h'
0x180031dcd  lea     rdx, [rbp+var_10]
0x180031dd1  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x180031dd6  mov     rcx, [rbp+var_8]; this
0x180031dda  test    rcx, rcx
0x180031ddd  jz      short loc_180031DE4
0x180031ddf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031de4  mov     bl, 1
0x180031de6  jmp     short loc_180031DEA
0x180031de8  xor     ebx, ebx
0x180031dea  mov     rcx, rdi; lpCriticalSection
0x180031ded  call    cs:__imp_LeaveCriticalSection
0x180031df3  nop
0x180031df4  mov     rcx, rsi
0x180031df7  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180031dfd  mov     al, bl
0x180031dff  add     rsp, 40h
0x180031e03  pop     r14
0x180031e05  pop     rdi
0x180031e06  pop     rsi
0x180031e07  pop     rbx
0x180031e08  pop     rbp
0x180031e09  retn
```

# pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)

- ea: `0x18001f528`
- end: `0x18001f5ea`
- name: `??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `194`
- prototype: `char __fastcall(__int64 *, void *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001eab8`
- `0x1800301d4`

## callees

- `0x180012d44`
- `0x1800148ac`
- `0x18001f528`
- `0x180022cdc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001f5a0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001f5d7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001f5a0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001f5d7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001f57d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001f57d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f551`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f551`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5cd`

## pseudocode

```c
char __fastcall pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(
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
  if ( *(_BYTE *)(*a1 + 112) || *(_BYTE *)(v7 + 113) || *(_QWORD *)(v7 + 96) )
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
    std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(*a1 + 96, v11);
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
0x18001f528  mov     [rsp-28h+arg_8], rdx
0x18001f52d  push    rbp
0x18001f52e  push    rbx
0x18001f52f  push    rsi
0x18001f530  push    rdi
0x18001f531  push    r14
0x18001f533  mov     rbp, rsp
0x18001f536  sub     rsp, 40h
0x18001f53a  mov     r14, r8
0x18001f53d  mov     rsi, rdx
0x18001f540  mov     rbx, rcx
0x18001f543  mov     rdi, [rcx]
0x18001f546  add     rdi, 18h
0x18001f54a  mov     [rbp+arg_0], rdi
0x18001f54e  mov     rcx, rdi; lpCriticalSection
0x18001f551  call    cs:__imp_EnterCriticalSection
0x18001f557  nop
0x18001f558  mov     rax, [rbx]
0x18001f55b  cmp     byte ptr [rax+70h], 0
0x18001f55f  jnz     short loc_18001F5C8
0x18001f561  cmp     byte ptr [rax+71h], 0
0x18001f565  jnz     short loc_18001F5C8
0x18001f567  cmp     qword ptr [rax+60h], 0
0x18001f56c  jnz     short loc_18001F5C8
0x18001f56e  xorps   xmm0, xmm0
0x18001f571  movdqu  [rbp+var_20], xmm0
0x18001f576  mov     rdx, rsi
0x18001f579  lea     rcx, [rbp+var_20]
0x18001f57d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001f583  lea     rax, [rbp+var_20]
0x18001f587  mov     [rbp+arg_18], rax
0x18001f58b  mov     r8, r14
0x18001f58e  lea     rdx, [rbp+var_20]
0x18001f592  lea     rcx, [rbp+var_10]
0x18001f596  call    ??$make_shared@U_ExceptionHolder@details@pplx@@AEAVexception_ptr@std@@AEBV_TaskCreationCallstack@23@@std@@YA?AV?$shared_ptr@U_ExceptionHolder@details@pplx@@@0@AEAVexception_ptr@0@AEBV_TaskCreationCallstack@details@pplx@@@Z; std::make_shared<pplx::details::_ExceptionHolder,std::exception_ptr &,pplx::details::_TaskCreationCallstack const &>(std::exception_ptr &,pplx::details::_TaskCreationCallstack const &)
0x18001f59b  nop
0x18001f59c  lea     rcx, [rbp+var_20]
0x18001f5a0  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001f5a6  mov     rcx, [rbx]
0x18001f5a9  add     rcx, 60h ; '`'
0x18001f5ad  lea     rdx, [rbp+var_10]
0x18001f5b1  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18001f5b6  mov     rcx, [rbp+var_8]; this
0x18001f5ba  test    rcx, rcx
0x18001f5bd  jz      short loc_18001F5C4
0x18001f5bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f5c4  mov     bl, 1
0x18001f5c6  jmp     short loc_18001F5CA
0x18001f5c8  xor     ebx, ebx
0x18001f5ca  mov     rcx, rdi; lpCriticalSection
0x18001f5cd  call    cs:__imp_LeaveCriticalSection
0x18001f5d3  nop
0x18001f5d4  mov     rcx, rsi
0x18001f5d7  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001f5dd  mov     al, bl
0x18001f5df  add     rsp, 40h
0x18001f5e3  pop     r14
0x18001f5e5  pop     rdi
0x18001f5e6  pop     rsi
0x18001f5e7  pop     rbx
0x18001f5e8  pop     rbp
0x18001f5e9  retn
```

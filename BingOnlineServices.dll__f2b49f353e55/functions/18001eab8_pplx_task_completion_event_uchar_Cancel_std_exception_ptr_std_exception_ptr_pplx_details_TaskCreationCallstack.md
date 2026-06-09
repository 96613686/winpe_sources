# pplx::task_completion_event<uchar>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)

- ea: `0x18001eab8`
- end: `0x18001eb24`
- name: `??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@E@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `108`
- prototype: `char __fastcall(__int64, void *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030280`
- `0x18004716c`

## callees

- `0x18001eab8`
- `0x18001f528`
- `0x18002723c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001eb0c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001eb0c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001eae1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001eae1`

## pseudocode

```c
char __fastcall pplx::task_completion_event<unsigned char>::_Cancel<std::exception_ptr>(
        __int64 a1,
        void *a2,
        __int64 a3)
{
  char v6; // bl
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  v8 = 0;
  __ExceptionPtrCopy(&v8, a2);
  if ( (unsigned __int8)pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(a1, &v8, a3) )
    v6 = pplx::task_completion_event<unsigned __int64>::_CancelInternal(a1);
  else
    v6 = 0;
  __ExceptionPtrDestroy(a2);
  return v6;
}

```

## disassembly

```asm
0x18001eab8  mov     rax, rsp
0x18001eabb  mov     [rax+8], rbx
0x18001eabf  mov     [rax+18h], rsi
0x18001eac3  mov     [rax+10h], rdx
0x18001eac7  push    rdi
0x18001eac8  sub     rsp, 30h
0x18001eacc  mov     rbx, r8
0x18001eacf  mov     rdi, rdx
0x18001ead2  mov     rsi, rcx
0x18001ead5  xorps   xmm0, xmm0
0x18001ead8  movdqu  xmmword ptr [rax-18h], xmm0
0x18001eadd  lea     rcx, [rax-18h]
0x18001eae1  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001eae7  mov     r8, rbx
0x18001eaea  lea     rdx, [rsp+38h+var_18]
0x18001eaef  mov     rcx, rsi
0x18001eaf2  call    ??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x18001eaf7  test    al, al
0x18001eaf9  jz      short loc_18001EB07
0x18001eafb  mov     rcx, rsi
0x18001eafe  call    ?_CancelInternal@?$task_completion_event@_K@pplx@@AEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_CancelInternal(void)
0x18001eb03  mov     bl, al
0x18001eb05  jmp     short loc_18001EB09
0x18001eb07  xor     bl, bl
0x18001eb09  mov     rcx, rdi
0x18001eb0c  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001eb12  mov     al, bl
0x18001eb14  mov     rbx, [rsp+38h+arg_0]
0x18001eb19  mov     rsi, [rsp+38h+arg_10]
0x18001eb1e  add     rsp, 30h
0x18001eb22  pop     rdi
0x18001eb23  retn
```

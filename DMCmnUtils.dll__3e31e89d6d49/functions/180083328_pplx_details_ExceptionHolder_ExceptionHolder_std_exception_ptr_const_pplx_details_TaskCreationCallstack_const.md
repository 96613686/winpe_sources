# pplx::details::_ExceptionHolder::_ExceptionHolder(std::exception_ptr const &,pplx::details::_TaskCreationCallstack const &)

- ea: `0x180083328`
- end: `0x180083390`
- name: `??0_ExceptionHolder@details@pplx@@QEAA@AEBVexception_ptr@std@@AEBV_TaskCreationCallstack@12@@Z`
- size: `104`
- prototype: `_QWORD(pplx::details::_ExceptionHolder *__hidden this, const struct std::exception_ptr *, const struct pplx::details::_TaskCreationCallstack *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007d018`

## callees

- `0x180082c34`
- `0x18008348c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180083362`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180083362`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
pplx::details::_ExceptionHolder *__fastcall pplx::details::_ExceptionHolder::_ExceptionHolder(
        pplx::details::_ExceptionHolder *this,
        const struct std::exception_ptr *a2,
        const struct pplx::details::_TaskCreationCallstack *a3)
{
  std::atomic<long>::atomic<long>(this, 0);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  __ExceptionPtrCopy((char *)this + 8, a2);
  pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (pplx::details::_ExceptionHolder *)((char *)this + 24),
    a3);
  return this;
}

```

## disassembly

```asm
0x180083328  mov     [rsp+arg_8], rbx
0x18008332d  mov     [rsp+arg_10], rsi
0x180083332  mov     [rsp+arg_0], rcx
0x180083337  push    rdi
0x180083338  sub     rsp, 20h
0x18008333c  mov     rdi, r8
0x18008333f  mov     rbx, rdx
0x180083342  mov     rsi, rcx
0x180083345  xor     edx, edx
0x180083347  call    ??0?$atomic@J@std@@QEAA@J@Z; std::atomic<long>::atomic<long>(long)
0x18008334c  lea     rcx, [rsi+8]
0x180083350  mov     qword ptr [rcx], 0
0x180083357  mov     qword ptr [rcx+8], 0
0x18008335f  mov     rdx, rbx
0x180083362  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180083369  nop     dword ptr [rax+rax+00h]
0x18008336e  nop
0x18008336f  lea     rcx, [rsi+18h]; this
0x180083373  mov     rdx, rdi; struct pplx::details::_TaskCreationCallstack *
0x180083376  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x18008337b  nop
0x18008337c  mov     rax, rsi
0x18008337f  mov     rbx, [rsp+28h+arg_8]
0x180083384  mov     rsi, [rsp+28h+arg_10]
0x180083389  add     rsp, 20h
0x18008338d  pop     rdi
0x18008338e  retn
```

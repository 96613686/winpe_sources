# pplx::details::_ExceptionHolder::_ExceptionHolder(std::exception_ptr const &,pplx::details::_TaskCreationCallstack const &)

- ea: `0x180011cd0`
- end: `0x180011d27`
- name: `??0_ExceptionHolder@details@pplx@@QEAA@AEBVexception_ptr@std@@AEBV_TaskCreationCallstack@12@@Z`
- size: `87`
- prototype: `_QWORD(pplx::details::_ExceptionHolder *__hidden this, const struct std::exception_ptr *, const struct pplx::details::_TaskCreationCallstack *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010494`

## callees

- `0x180011784`
- `0x180011d84`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180011d05`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180011d05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
pplx::details::_ExceptionHolder *__fastcall pplx::details::_ExceptionHolder::_ExceptionHolder(
        pplx::details::_ExceptionHolder *this,
        const struct std::exception_ptr *a2,
        const struct pplx::details::_TaskCreationCallstack *a3)
{
  _QWORD *v5; // rcx
  const void *v6; // r9

  std::atomic<long>::atomic<long>(this, 0, a3, a2);
  *++v5 = 0;
  v5[1] = 0;
  __ExceptionPtrCopy(v5, v6);
  pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (pplx::details::_ExceptionHolder *)((char *)this + 24),
    a3);
  return this;
}

```

## disassembly

```asm
0x180011cd0  mov     [rsp+arg_8], rbx
0x180011cd5  mov     [rsp+arg_0], rcx
0x180011cda  push    rdi
0x180011cdb  sub     rsp, 20h
0x180011cdf  mov     rbx, r8
0x180011ce2  mov     r9, rdx
0x180011ce5  mov     rdi, rcx
0x180011ce8  xor     edx, edx
0x180011cea  call    ??0?$atomic@J@std@@QEAA@J@Z; std::atomic<long>::atomic<long>(long)
0x180011cef  add     rcx, 8
0x180011cf3  mov     qword ptr [rcx], 0
0x180011cfa  mov     qword ptr [rcx+8], 0
0x180011d02  mov     rdx, r9
0x180011d05  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180011d0b  nop
0x180011d0c  lea     rcx, [rdi+18h]; this
0x180011d10  mov     rdx, rbx; struct pplx::details::_TaskCreationCallstack *
0x180011d13  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x180011d18  nop
0x180011d19  mov     rax, rdi
0x180011d1c  mov     rbx, [rsp+28h+arg_8]
0x180011d21  add     rsp, 20h
0x180011d25  pop     rdi
0x180011d26  retn
```

# std::_Construct_in_place<Concurrency::details::_ExceptionHolder,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack>(Concurrency::details::_ExceptionHolder &,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack &&)

- ea: `0x18001a1f8`
- end: `0x18001a23b`
- name: `??$_Construct_in_place@U_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@std@@V_TaskCreationCallstack@23@@std@@YAXAEAU_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@0@$$QEAV_TaskCreationCallstack@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(_DWORD *, const void *, const struct Concurrency::details::_TaskCreationCallstack *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001d904`

## callees

- `0x18001b004`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001a21c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001a21c`

## pseudocode

```c
__int64 __fastcall std::_Construct_in_place<Concurrency::details::_ExceptionHolder,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack>(
        _DWORD *a1,
        const void *a2,
        const struct Concurrency::details::_TaskCreationCallstack *a3)
{
  _QWORD *v5; // rcx

  *a1 = 0;
  v5 = a1 + 2;
  *v5 = 0;
  v5[1] = 0;
  __ExceptionPtrCopy(v5, a2);
  return Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
           (Concurrency::details::_TaskCreationCallstack *)(a1 + 6),
           a3);
}

```

## disassembly

```asm
0x18001a1f8  mov     [rsp+arg_8], rbx
0x18001a1fd  push    rdi
0x18001a1fe  sub     rsp, 20h
0x18001a202  mov     rdi, r8
0x18001a205  mov     rbx, rcx
0x18001a208  mov     [rsp+28h+arg_0], rcx
0x18001a20d  xor     eax, eax
0x18001a20f  mov     [rcx], eax
0x18001a211  add     rcx, 8
0x18001a215  mov     [rcx], rax
0x18001a218  mov     [rcx+8], rax
0x18001a21c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001a222  nop
0x18001a223  lea     rcx, [rbx+18h]; this
0x18001a227  mov     rdx, rdi; struct Concurrency::details::_TaskCreationCallstack *
0x18001a22a  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18001a22f  nop
0x18001a230  mov     rbx, [rsp+28h+arg_8]
0x18001a235  add     rsp, 20h
0x18001a239  pop     rdi
0x18001a23a  retn
```

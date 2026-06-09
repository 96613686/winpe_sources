# std::_Construct_in_place<Concurrency::details::_ExceptionHolder,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack>(Concurrency::details::_ExceptionHolder &,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack &&)

- ea: `0x18001cc6c`
- end: `0x18001ccaf`
- name: `??$_Construct_in_place@U_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@std@@V_TaskCreationCallstack@23@@std@@YAXAEAU_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@0@$$QEAV_TaskCreationCallstack@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(_DWORD *, const void *, const struct Concurrency::details::_TaskCreationCallstack *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180022b24`

## callees

- `0x18001db34`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001cc90`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001cc90`

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
0x18001cc6c  mov     [rsp+arg_8], rbx
0x18001cc71  push    rdi
0x18001cc72  sub     rsp, 20h
0x18001cc76  mov     rdi, r8
0x18001cc79  mov     rbx, rcx
0x18001cc7c  mov     [rsp+28h+arg_0], rcx
0x18001cc81  xor     eax, eax
0x18001cc83  mov     [rcx], eax
0x18001cc85  add     rcx, 8
0x18001cc89  mov     [rcx], rax
0x18001cc8c  mov     [rcx+8], rax
0x18001cc90  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001cc96  nop
0x18001cc97  lea     rcx, [rbx+18h]; this
0x18001cc9b  mov     rdx, rdi; struct Concurrency::details::_TaskCreationCallstack *
0x18001cc9e  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18001cca3  nop
0x18001cca4  mov     rbx, [rsp+28h+arg_8]
0x18001cca9  add     rsp, 20h
0x18001ccad  pop     rdi
0x18001ccae  retn
```

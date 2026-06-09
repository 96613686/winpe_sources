# std::_Construct_in_place<Concurrency::details::_ExceptionHolder,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack>(Concurrency::details::_ExceptionHolder &,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack &&)

- ea: `0x18000e174`
- end: `0x18000e1b7`
- name: `??$_Construct_in_place@U_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@std@@V_TaskCreationCallstack@23@@std@@YAXAEAU_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@0@$$QEAV_TaskCreationCallstack@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(_DWORD *, const void *, const struct Concurrency::details::_TaskCreationCallstack *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180016d14`

## callees

- `0x180012004`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000e198`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000e198`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000e174  mov     [rsp+arg_8], rbx
0x18000e179  push    rdi
0x18000e17a  sub     rsp, 20h
0x18000e17e  mov     rdi, r8
0x18000e181  mov     rbx, rcx
0x18000e184  mov     [rsp+28h+arg_0], rcx
0x18000e189  xor     eax, eax
0x18000e18b  mov     [rcx], eax
0x18000e18d  add     rcx, 8
0x18000e191  mov     [rcx], rax
0x18000e194  mov     [rcx+8], rax
0x18000e198  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18000e19e  nop
0x18000e19f  lea     rcx, [rbx+18h]; this
0x18000e1a3  mov     rdx, rdi; struct Concurrency::details::_TaskCreationCallstack *
0x18000e1a6  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18000e1ab  nop
0x18000e1ac  mov     rbx, [rsp+28h+arg_8]
0x18000e1b1  add     rsp, 20h
0x18000e1b5  pop     rdi
0x18000e1b6  retn
```

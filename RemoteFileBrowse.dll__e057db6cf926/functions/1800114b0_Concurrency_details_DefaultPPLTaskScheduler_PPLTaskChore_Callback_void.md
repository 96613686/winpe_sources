# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)

- ea: `0x1800114b0`
- end: `0x1800114e8`
- name: `?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z`
- size: `56`
- prototype: `void __fastcall(Concurrency::details *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x1800114cf`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x1800114cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(Concurrency::details *a1)
{
  struct Concurrency::details::_Threadpool_chore *v2; // rdx

  (*((void (__fastcall **)(_QWORD))a1 + 3))(*((_QWORD *)a1 + 4));
  Concurrency::details::_Release_chore(a1, v2);
  operator delete(a1);
}

```

## disassembly

```asm
0x1800114b0  push    rbx
0x1800114b2  sub     rsp, 20h
0x1800114b6  mov     rbx, rcx
0x1800114b9  mov     [rsp+28h+arg_0], rcx
0x1800114be  mov     rcx, [rcx+20h]
0x1800114c2  mov     rax, [rbx+18h]
0x1800114c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114cb  nop
0x1800114cc  mov     rcx, rbx
0x1800114cf  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x1800114d5  nop
0x1800114d6  mov     edx, 28h ; '('; unsigned __int64
0x1800114db  mov     rcx, rbx; void *
0x1800114de  add     rsp, 20h
0x1800114e2  pop     rbx
0x1800114e3  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

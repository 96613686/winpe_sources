# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x1800474e8`
- end: `0x18004750e`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x180046da4`
- `0x180048f40`

## callees

- `0x18000abc4`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x1800474f1`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x1800474f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(
        Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  Concurrency::details::_Release_chore(this, a2);
  operator delete(this, 0x28u);
  return this;
}

```

## disassembly

```asm
0x1800474e8  push    rbx
0x1800474ea  sub     rsp, 20h
0x1800474ee  mov     rbx, rcx
0x1800474f1  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x1800474f7  nop
0x1800474f8  mov     edx, 28h ; '('; unsigned __int64
0x1800474fd  mov     rcx, rbx; void *
0x180047500  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180047505  mov     rax, rbx
0x180047508  add     rsp, 20h
0x18004750c  pop     rbx
0x18004750d  retn
```

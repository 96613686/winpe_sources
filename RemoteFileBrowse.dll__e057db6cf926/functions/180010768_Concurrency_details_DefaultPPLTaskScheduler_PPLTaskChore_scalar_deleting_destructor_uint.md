# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x180010768`
- end: `0x18001078e`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x1800130b8`

## callees

- `0x180002054`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180010771`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180010771`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(
        Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  Concurrency::details::_Release_chore(this, a2);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180010768  push    rbx
0x18001076a  sub     rsp, 20h
0x18001076e  mov     rbx, rcx
0x180010771  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x180010777  nop
0x180010778  mov     edx, 28h ; '('; unsigned __int64
0x18001077d  mov     rcx, rbx; void *
0x180010780  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010785  mov     rax, rbx
0x180010788  add     rsp, 20h
0x18001078c  pop     rbx
0x18001078d  retn
```

# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x180017438`
- end: `0x18001745e`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x18001a9e8`

## callees

- `0x1800025f8`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180017441`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180017441`

## pseudocode

```c
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
0x180017438  push    rbx
0x18001743a  sub     rsp, 20h
0x18001743e  mov     rbx, rcx
0x180017441  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x180017447  nop
0x180017448  mov     edx, 28h ; '('; unsigned __int64
0x18001744d  mov     rcx, rbx; void *
0x180017450  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017455  mov     rax, rbx
0x180017458  add     rsp, 20h
0x18001745c  pop     rbx
0x18001745d  retn
```

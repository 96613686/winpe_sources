# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x18003296c`
- end: `0x180032992`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x1800114f4`
- `0x18001c6e0`
- `0x180023e7c`

## callees

- `0x180026dcc`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180032975`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180032975`

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
0x18003296c  push    rbx
0x18003296e  sub     rsp, 20h
0x180032972  mov     rbx, rcx
0x180032975  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x18003297b  nop
0x18003297c  mov     edx, 28h ; '('; unsigned __int64
0x180032981  mov     rcx, rbx; void *
0x180032984  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180032989  mov     rax, rbx
0x18003298c  add     rsp, 20h
0x180032990  pop     rbx
0x180032991  retn
```

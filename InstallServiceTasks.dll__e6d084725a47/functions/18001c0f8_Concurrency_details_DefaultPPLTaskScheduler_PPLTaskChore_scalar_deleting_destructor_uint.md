# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x18001c0f8`
- end: `0x18001c11e`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x18001b690`
- `0x18001f230`

## callees

- `0x1800038fc`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18001c101`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18001c101`

## pseudocode

```c
Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(
        Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  Concurrency::details::_Release_chore(this, a2);
  operator delete(this, (const struct std::nothrow_t *)0x28);
  return this;
}

```

## disassembly

```asm
0x18001c0f8  push    rbx
0x18001c0fa  sub     rsp, 20h
0x18001c0fe  mov     rbx, rcx
0x18001c101  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x18001c107  nop
0x18001c108  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18001c10d  mov     rcx, rbx; void *
0x18001c110  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c115  mov     rax, rbx
0x18001c118  add     rsp, 20h
0x18001c11c  pop     rbx
0x18001c11d  retn
```

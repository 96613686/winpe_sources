# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x180013bb4`
- end: `0x180013bda`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x180012b34`
- `0x18001bd20`

## callees

- `0x180004194`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180013bbd`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180013bbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013bb4  push    rbx
0x180013bb6  sub     rsp, 20h
0x180013bba  mov     rbx, rcx
0x180013bbd  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x180013bc3  nop
0x180013bc4  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180013bc9  mov     rcx, rbx; void *
0x180013bcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013bd1  mov     rax, rbx
0x180013bd4  add     rsp, 20h
0x180013bd8  pop     rbx
0x180013bd9  retn
```

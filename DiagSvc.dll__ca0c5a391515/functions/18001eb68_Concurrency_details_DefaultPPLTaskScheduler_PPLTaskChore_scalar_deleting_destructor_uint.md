# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x18001eb68`
- end: `0x18001eb8e`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x18001e278`
- `0x180024998`

## callees

- `0x1800040b4`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18001eb71`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18001eb71`

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
0x18001eb68  push    rbx
0x18001eb6a  sub     rsp, 20h
0x18001eb6e  mov     rbx, rcx
0x18001eb71  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x18001eb77  nop
0x18001eb78  mov     edx, 28h ; '('
0x18001eb7d  mov     rcx, rbx; Block
0x18001eb80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001eb85  mov     rax, rbx
0x18001eb88  add     rsp, 20h
0x18001eb8c  pop     rbx
0x18001eb8d  retn
```

# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x180012e4c`
- end: `0x180012e72`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x18001136c`
- `0x18001ec74`

## callees

- `0x180002750`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180012e55`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180012e55`

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
0x180012e4c  push    rbx
0x180012e4e  sub     rsp, 20h
0x180012e52  mov     rbx, rcx
0x180012e55  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x180012e5b  nop
0x180012e5c  mov     edx, 28h ; '('; unsigned __int64
0x180012e61  mov     rcx, rbx; void *
0x180012e64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012e69  mov     rax, rbx
0x180012e6c  add     rsp, 20h
0x180012e70  pop     rbx
0x180012e71  retn
```

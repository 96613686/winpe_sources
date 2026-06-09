# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x18004b5fc`
- end: `0x18004b622`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x1800495d4`
- `0x18004fc34`

## callees

- `0x1800035bc`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18004b605`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18004b605`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18004b5fc  push    rbx
0x18004b5fe  sub     rsp, 20h
0x18004b602  mov     rbx, rcx
0x18004b605  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x18004b60b  nop
0x18004b60c  mov     edx, 28h ; '('
0x18004b611  mov     rcx, rbx; Block
0x18004b614  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004b619  mov     rax, rbx
0x18004b61c  add     rsp, 20h
0x18004b620  pop     rbx
0x18004b621  retn
```

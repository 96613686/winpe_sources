# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)

- ea: `0x180018830`
- end: `0x180018868`
- name: `?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z`
- size: `56`
- prototype: `void __fastcall(Concurrency::details *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x1800025f8`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18001884f`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18001884f`

## pseudocode

```c
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
0x180018830  push    rbx
0x180018832  sub     rsp, 20h
0x180018836  mov     rbx, rcx
0x180018839  mov     [rsp+28h+arg_0], rcx
0x18001883e  mov     rcx, [rcx+20h]
0x180018842  mov     rax, [rbx+18h]
0x180018846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001884b  nop
0x18001884c  mov     rcx, rbx
0x18001884f  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x180018855  nop
0x180018856  mov     edx, 28h ; '('; unsigned __int64
0x18001885b  mov     rcx, rbx; void *
0x18001885e  add     rsp, 20h
0x180018862  pop     rbx
0x180018863  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

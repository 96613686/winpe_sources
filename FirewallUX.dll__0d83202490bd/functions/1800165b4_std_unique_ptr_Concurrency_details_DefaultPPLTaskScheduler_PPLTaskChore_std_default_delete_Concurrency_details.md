# std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>(void)

- ea: `0x1800165b4`
- end: `0x1800165e0`
- name: `??1?$unique_ptr@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@U?$default_delete@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@@std@@@std@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(Concurrency::details **, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18002b1f0`

## callees

- `0x1800025f8`
- `0x1800165b4`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x1800165c5`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x1800165c5`

## pseudocode

```c
void __fastcall std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>(
        Concurrency::details **a1,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  Concurrency::details *v2; // rbx

  v2 = *a1;
  if ( *a1 )
  {
    Concurrency::details::_Release_chore(*a1, a2);
    operator delete(v2, 0x28u);
  }
}

```

## disassembly

```asm
0x1800165b4  push    rbx
0x1800165b6  sub     rsp, 20h
0x1800165ba  mov     rbx, [rcx]
0x1800165bd  test    rbx, rbx
0x1800165c0  jz      short loc_1800165DA
0x1800165c2  mov     rcx, rbx
0x1800165c5  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x1800165cb  nop
0x1800165cc  mov     edx, 28h ; '('; unsigned __int64
0x1800165d1  mov     rcx, rbx; void *
0x1800165d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800165d9  nop
0x1800165da  add     rsp, 20h
0x1800165de  pop     rbx
0x1800165df  retn
```

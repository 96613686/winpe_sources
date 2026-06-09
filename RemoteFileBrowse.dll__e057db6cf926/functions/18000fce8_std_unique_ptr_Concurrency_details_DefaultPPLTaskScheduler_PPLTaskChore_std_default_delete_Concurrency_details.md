# std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>(void)

- ea: `0x18000fce8`
- end: `0x18000fd14`
- name: `??1?$unique_ptr@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@U?$default_delete@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@@std@@@std@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(Concurrency::details **, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800182d8`

## callees

- `0x180002054`
- `0x18000fce8`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18000fcf9`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x18000fcf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000fce8  push    rbx
0x18000fcea  sub     rsp, 20h
0x18000fcee  mov     rbx, [rcx]
0x18000fcf1  test    rbx, rbx
0x18000fcf4  jz      short loc_18000FD0E
0x18000fcf6  mov     rcx, rbx
0x18000fcf9  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x18000fcff  nop
0x18000fd00  mov     edx, 28h ; '('; unsigned __int64
0x18000fd05  mov     rcx, rbx; void *
0x18000fd08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fd0d  nop
0x18000fd0e  add     rsp, 20h
0x18000fd12  pop     rbx
0x18000fd13  retn
```

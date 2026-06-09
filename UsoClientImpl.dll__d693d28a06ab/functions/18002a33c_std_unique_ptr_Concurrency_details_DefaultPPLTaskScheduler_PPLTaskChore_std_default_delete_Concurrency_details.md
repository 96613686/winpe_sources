# std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>(void)

- ea: `0x18002a33c`
- end: `0x18002a372`
- name: `??1?$unique_ptr@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@U?$default_delete@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@@std@@@std@@QEAA@XZ`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18005ed7d`

## callees

- `0x18002a33c`
- `0x180056a08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a352`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a352`

## pseudocode

```c
void __fastcall std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>(
        PTP_WORK **a1)
{
  PTP_WORK *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
    {
      CloseThreadpoolWork(*v1);
      *v1 = 0;
    }
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18002a33c  push    rbx
0x18002a33e  sub     rsp, 20h
0x18002a342  mov     rbx, [rcx]
0x18002a345  test    rbx, rbx
0x18002a348  jz      short loc_18002A36C
0x18002a34a  mov     rcx, [rbx]; pwk
0x18002a34d  test    rcx, rcx
0x18002a350  jz      short loc_18002A35F
0x18002a352  call    cs:__imp_CloseThreadpoolWork
0x18002a358  mov     qword ptr [rbx], 0
0x18002a35f  mov     edx, 28h ; '('
0x18002a364  mov     rcx, rbx; Block
0x18002a367  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a36c  add     rsp, 20h
0x18002a370  pop     rbx
0x18002a371  retn
```

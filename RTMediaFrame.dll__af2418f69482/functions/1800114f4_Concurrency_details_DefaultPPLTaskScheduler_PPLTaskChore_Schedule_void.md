# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Schedule(void)

- ea: `0x1800114f4`
- end: `0x180011549`
- name: `?_Schedule@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001149c`

## callees

- `0x1800114f4`
- `0x18002749c`
- `0x18003200c`
- `0x18003296c`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x1800114fd`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x1800114fd`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Schedule(
        Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  unsigned int v3; // edx
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( Concurrency::details::_Schedule_chore(this, a2) )
  {
    if ( this )
      Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(this, v3);
    std::exception::exception((std::exception *)pExceptionObject, "Fail to schedule the chore!");
    pExceptionObject[0] = &Concurrency::invalid_operation::`vftable';
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800114f4  push    rbx
0x1800114f6  sub     rsp, 40h
0x1800114fa  mov     rbx, rcx
0x1800114fd  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x180011503  test    eax, eax
0x180011505  jz      short loc_180011543
0x180011507  test    rbx, rbx
0x18001150a  jz      short loc_180011514
0x18001150c  mov     rcx, rbx; this
0x18001150f  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x180011514  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x18001151b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011520  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180011525  lea     rax, ??_7invalid_operation@Concurrency@@6B@; const Concurrency::invalid_operation::`vftable'
0x18001152c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180011533  mov     [rsp+48h+pExceptionObject], rax
0x180011538  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001153d  call    _CxxThrowException_0
0x180011543  add     rsp, 40h
0x180011547  pop     rbx
0x180011548  retn
```

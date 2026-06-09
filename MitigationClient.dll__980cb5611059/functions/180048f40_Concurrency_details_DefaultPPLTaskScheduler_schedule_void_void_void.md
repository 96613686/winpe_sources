# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x180048f40`
- end: `0x180048fd9`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `153`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180048908`
- `0x1800489b4`

## callees

- `0x18000a704`
- `0x18000b2c0`
- `0x1800468f4`
- `0x1800474e8`
- `0x180048f40`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x180048f88`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x180048f88`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        Concurrency::details::_DefaultPPLTaskScheduler *this,
        void (*a2)(void *),
        void *a3)
{
  Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *v5; // rsi
  struct Concurrency::details::_Threadpool_chore *v6; // rdx
  unsigned int v7; // edx
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = (Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *)operator new(0x28u);
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback;
  *((_QWORD *)v5 + 2) = v5;
  *((_QWORD *)v5 + 3) = a2;
  *((_QWORD *)v5 + 4) = a3;
  if ( Concurrency::details::_Schedule_chore(v5, v6) )
  {
    Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(v5, v7);
    std::exception::exception((std::exception *)pExceptionObject, "Fail to schedule the chore!");
    pExceptionObject[0] = &std::logic_error::`vftable';
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180048f40  mov     [rsp+arg_0], rbx
0x180048f45  mov     [rsp+arg_8], rsi
0x180048f4a  push    rdi
0x180048f4b  sub     rsp, 40h
0x180048f4f  mov     ecx, 28h ; '('; Size
0x180048f54  mov     rdi, r8
0x180048f57  mov     rbx, rdx
0x180048f5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048f5f  mov     rsi, rax
0x180048f62  mov     [rsp+48h+arg_18], rax
0x180048f67  mov     rcx, rsi
0x180048f6a  mov     qword ptr [rax], 0
0x180048f71  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x180048f78  mov     [rsi+8], rax
0x180048f7c  mov     [rsi+10h], rsi
0x180048f80  mov     [rsi+18h], rbx
0x180048f84  mov     [rsi+20h], rdi
0x180048f88  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x180048f8e  test    eax, eax
0x180048f90  jz      short loc_180048FC9
0x180048f92  mov     rcx, rsi; this
0x180048f95  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x180048f9a  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x180048fa1  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180048fa6  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180048fab  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x180048fb2  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180048fb9  mov     [rsp+48h+pExceptionObject], rax
0x180048fbe  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180048fc3  call    _CxxThrowException_0
0x180048fc9  mov     rbx, [rsp+48h+arg_0]
0x180048fce  mov     rsi, [rsp+48h+arg_8]
0x180048fd3  add     rsp, 40h
0x180048fd7  pop     rdi
0x180048fd8  retn
```

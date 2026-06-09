# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x18001f230`
- end: `0x18001f2c9`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `153`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001e9a0`
- `0x18001ea4c`

## callees

- `0x180003948`
- `0x180003ff0`
- `0x18000ce24`
- `0x18001c0f8`
- `0x18001f230`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18001f278`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18001f278`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        Concurrency::details::_DefaultPPLTaskScheduler *this,
        void (*a2)(void *),
        void *a3)
{
  Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *v5; // rsi
  struct Concurrency::details::_Threadpool_chore *v6; // rdx
  struct Concurrency::details::_Threadpool_chore *v7; // rdx
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
0x18001f230  mov     [rsp+arg_0], rbx
0x18001f235  mov     [rsp+arg_8], rsi
0x18001f23a  push    rdi
0x18001f23b  sub     rsp, 40h
0x18001f23f  mov     ecx, 28h ; '('; Size
0x18001f244  mov     rdi, r8
0x18001f247  mov     rbx, rdx
0x18001f24a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f24f  mov     rsi, rax
0x18001f252  mov     [rsp+48h+arg_18], rax
0x18001f257  mov     rcx, rsi
0x18001f25a  mov     qword ptr [rax], 0
0x18001f261  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x18001f268  mov     [rsi+8], rax
0x18001f26c  mov     [rsi+10h], rsi
0x18001f270  mov     [rsi+18h], rbx
0x18001f274  mov     [rsi+20h], rdi
0x18001f278  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x18001f27e  test    eax, eax
0x18001f280  jz      short loc_18001F2B9
0x18001f282  mov     rcx, rsi; this
0x18001f285  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x18001f28a  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x18001f291  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001f296  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18001f29b  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x18001f2a2  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001f2a9  mov     [rsp+48h+pExceptionObject], rax
0x18001f2ae  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001f2b3  call    _CxxThrowException_0
0x18001f2b9  mov     rbx, [rsp+48h+arg_0]
0x18001f2be  mov     rsi, [rsp+48h+arg_8]
0x18001f2c3  add     rsp, 40h
0x18001f2c7  pop     rdi
0x18001f2c8  retn
```

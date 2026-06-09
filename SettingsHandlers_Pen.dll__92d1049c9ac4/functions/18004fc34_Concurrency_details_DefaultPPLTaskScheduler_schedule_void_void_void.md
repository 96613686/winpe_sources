# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x18004fc34`
- end: `0x18004fcc1`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `141`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18004f0b4`
- `0x18004f160`

## callees

- `0x1800037c0`
- `0x180003c70`
- `0x18003eac0`
- `0x18004b5fc`
- `0x18004fc34`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18004fc7c`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18004fc7c`

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
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v5 = (Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *)operator new(0x28u);
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback;
  *((_QWORD *)v5 + 2) = v5;
  *((_QWORD *)v5 + 3) = a2;
  *((_QWORD *)v5 + 4) = a3;
  if ( Concurrency::details::_Schedule_chore(v5, v6) )
  {
    Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(v5, v7);
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Fail to schedule the chore!");
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18004fc34  mov     [rsp+arg_0], rbx
0x18004fc39  mov     [rsp+arg_8], rsi
0x18004fc3e  push    rdi
0x18004fc3f  sub     rsp, 40h
0x18004fc43  mov     ecx, 28h ; '('; Size
0x18004fc48  mov     rdi, r8
0x18004fc4b  mov     rbx, rdx
0x18004fc4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fc53  mov     rsi, rax
0x18004fc56  mov     [rsp+48h+arg_18], rax
0x18004fc5b  mov     rcx, rsi
0x18004fc5e  mov     qword ptr [rax], 0
0x18004fc65  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x18004fc6c  mov     [rsi+8], rax
0x18004fc70  mov     [rsi+10h], rsi
0x18004fc74  mov     [rsi+18h], rbx
0x18004fc78  mov     [rsi+20h], rdi
0x18004fc7c  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x18004fc82  test    eax, eax
0x18004fc84  jz      short loc_18004FCB1
0x18004fc86  mov     rcx, rsi; this
0x18004fc89  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x18004fc8e  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x18004fc95  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18004fc9a  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18004fc9f  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18004fca6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004fcab  call    _CxxThrowException_0
0x18004fcb1  mov     rbx, [rsp+48h+arg_0]
0x18004fcb6  mov     rsi, [rsp+48h+arg_8]
0x18004fcbb  add     rsp, 40h
0x18004fcbf  pop     rdi
0x18004fcc0  retn
```

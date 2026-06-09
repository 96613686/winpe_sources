# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x18001ec74`
- end: `0x18001ed01`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `141`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001dae4`
- `0x18001db90`

## callees

- `0x18000288c`
- `0x180003318`
- `0x180010880`
- `0x180012e4c`
- `0x18001ec74`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18001ecbc`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18001ecbc`

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
0x18001ec74  mov     [rsp+arg_0], rbx
0x18001ec79  mov     [rsp+arg_8], rsi
0x18001ec7e  push    rdi
0x18001ec7f  sub     rsp, 40h
0x18001ec83  mov     ecx, 28h ; '('; Size
0x18001ec88  mov     rdi, r8
0x18001ec8b  mov     rbx, rdx
0x18001ec8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ec93  mov     rsi, rax
0x18001ec96  mov     [rsp+48h+arg_18], rax
0x18001ec9b  mov     rcx, rsi
0x18001ec9e  mov     qword ptr [rax], 0
0x18001eca5  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x18001ecac  mov     [rsi+8], rax
0x18001ecb0  mov     [rsi+10h], rsi
0x18001ecb4  mov     [rsi+18h], rbx
0x18001ecb8  mov     [rsi+20h], rdi
0x18001ecbc  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x18001ecc2  test    eax, eax
0x18001ecc4  jz      short loc_18001ECF1
0x18001ecc6  mov     rcx, rsi; this
0x18001ecc9  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x18001ecce  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x18001ecd5  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001ecda  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001ecdf  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001ece6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001eceb  call    _CxxThrowException_0
0x18001ecf1  mov     rbx, [rsp+48h+arg_0]
0x18001ecf6  mov     rsi, [rsp+48h+arg_8]
0x18001ecfb  add     rsp, 40h
0x18001ecff  pop     rdi
0x18001ed00  retn
```

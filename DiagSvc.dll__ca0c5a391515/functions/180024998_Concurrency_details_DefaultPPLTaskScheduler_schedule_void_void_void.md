# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x180024998`
- end: `0x180024a3f`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `167`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180024068`
- `0x18002411c`

## callees

- `0x180003b84`
- `0x18001dce0`
- `0x18001eb68`
- `0x180024998`
- `0x180026140`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x1800249e9`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x1800249e9`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        Concurrency::details::_DefaultPPLTaskScheduler *this,
        void (*a2)(void *),
        void *a3)
{
  Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *v5; // rax
  struct Concurrency::details::_Threadpool_chore *v6; // rdx
  Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *v7; // rbx
  struct Concurrency::details::_Threadpool_chore *v8; // rdx
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = (Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *)operator new(0x28u);
  v7 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = 0;
    *((_QWORD *)v5 + 1) = Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback;
    *((_QWORD *)v5 + 2) = v5;
    *((_QWORD *)v5 + 3) = a2;
    *((_QWORD *)v5 + 4) = a3;
  }
  else
  {
    v7 = 0;
  }
  if ( Concurrency::details::_Schedule_chore(v7, v6) )
  {
    if ( v7 )
      Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(v7, v8);
    std::exception::exception((std::exception *)pExceptionObject, "Fail to schedule the chore!");
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180024998  mov     [rsp+arg_0], rbx
0x18002499d  mov     [rsp+arg_8], rsi
0x1800249a2  push    rdi
0x1800249a3  sub     rsp, 40h
0x1800249a7  mov     ecx, 28h ; '('; Size
0x1800249ac  mov     rdi, r8
0x1800249af  mov     rsi, rdx
0x1800249b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800249b7  mov     [rsp+48h+arg_18], rax
0x1800249bc  mov     rbx, rax
0x1800249bf  test    rax, rax
0x1800249c2  jz      short loc_1800249E4
0x1800249c4  mov     qword ptr [rax], 0
0x1800249cb  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x1800249d2  mov     [rbx+8], rax
0x1800249d6  mov     [rbx+10h], rbx
0x1800249da  mov     [rbx+18h], rsi
0x1800249de  mov     [rbx+20h], rdi
0x1800249e2  jmp     short loc_1800249E6
0x1800249e4  xor     ebx, ebx
0x1800249e6  mov     rcx, rbx
0x1800249e9  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x1800249ef  test    eax, eax
0x1800249f1  jz      short loc_180024A2F
0x1800249f3  test    rbx, rbx
0x1800249f6  jz      short loc_180024A00
0x1800249f8  mov     rcx, rbx; this
0x1800249fb  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x180024a00  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x180024a07  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180024a0c  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180024a11  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180024a18  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180024a1f  mov     [rsp+48h+pExceptionObject], rax
0x180024a24  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180024a29  call    _CxxThrowException_0
0x180024a2f  mov     rbx, [rsp+48h+arg_0]
0x180024a34  mov     rsi, [rsp+48h+arg_8]
0x180024a39  add     rsp, 40h
0x180024a3d  pop     rdi
0x180024a3e  retn
```

# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x180093884`
- end: `0x180093951`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `205`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18008eed8`
- `0x18008ef8c`

## callees

- `0x180004a04`
- `0x180005e50`
- `0x18000a70c`
- `0x1800864b8`
- `0x180093884`
- `0x1800d9af4`
- `0x1800d9b24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009391c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009391c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800938de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800938de`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180093906`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180093906`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        Concurrency::details::_DefaultPPLTaskScheduler *this,
        struct _TP_WORK *a2,
        struct _TP_WORK *a3)
{
  PTP_WORK *v5; // rsi
  PTP_WORK ThreadpoolWork; // rax
  unsigned int v7; // edx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v5 = (PTP_WORK *)operator new(0x28u);
  *(_OWORD *)v5 = 0;
  *((_OWORD *)v5 + 1) = 0;
  *v5 = 0;
  v5[1] = (PTP_WORK)Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback;
  v5[2] = (PTP_WORK)v5;
  v5[3] = a2;
  v5[4] = a3;
  ThreadpoolWork = CreateThreadpoolWork(Concurrency::details::_anonymous_namespace_::_Task_scheduler_callback, v5, 0);
  *v5 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    if ( (unsigned int)Concurrency::details::_anonymous_namespace_::_Get_STL_host_status() )
      Concurrency::details::_anonymous_namespace_::_Call_get_module_handle_ex(4, v5[1]);
    SubmitThreadpoolWork(*v5);
  }
  else if ( GetLastError() )
  {
    Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(
      (Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *)v5,
      v7);
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Fail to schedule the chore!");
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180093884  mov     [rsp+arg_0], rbx
0x180093889  mov     [rsp+arg_8], rsi
0x18009388e  push    rdi
0x18009388f  sub     rsp, 40h
0x180093893  mov     ecx, 28h ; '('; Size
0x180093898  mov     rdi, r8
0x18009389b  mov     rbx, rdx
0x18009389e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800938a3  mov     rsi, rax
0x1800938a6  mov     [rsp+48h+arg_18], rax
0x1800938ab  xorps   xmm0, xmm0
0x1800938ae  lea     rcx, Concurrency__details___anonymous_namespace____Task_scheduler_callback; pfnwk
0x1800938b5  xor     eax, eax
0x1800938b7  xor     r8d, r8d; pcbe
0x1800938ba  mov     rdx, rsi; pv
0x1800938bd  movups  xmmword ptr [rsi], xmm0
0x1800938c0  movups  xmmword ptr [rsi+10h], xmm0
0x1800938c4  mov     [rsi], rax
0x1800938c7  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x1800938ce  mov     [rsi+8], rax
0x1800938d2  mov     [rsi+10h], rsi
0x1800938d6  mov     [rsi+18h], rbx
0x1800938da  mov     [rsi+20h], rdi
0x1800938de  call    cs:__imp_CreateThreadpoolWork
0x1800938e4  mov     [rsi], rax
0x1800938e7  test    rax, rax
0x1800938ea  jz      short loc_18009391C
0x1800938ec  call    Concurrency__details___anonymous_namespace____Get_STL_host_status
0x1800938f1  test    eax, eax
0x1800938f3  jz      short loc_180093903
0x1800938f5  mov     rdx, [rsi+8]
0x1800938f9  mov     ecx, 4
0x1800938fe  call    Concurrency__details___anonymous_namespace____Call_get_module_handle_ex
0x180093903  mov     rcx, [rsi]; pwk
0x180093906  call    cs:__imp_SubmitThreadpoolWork
0x18009390c  mov     rbx, [rsp+48h+arg_0]
0x180093911  mov     rsi, [rsp+48h+arg_8]
0x180093916  add     rsp, 40h
0x18009391a  pop     rdi
0x18009391b  retn
0x18009391c  call    cs:__imp_GetLastError
0x180093922  test    eax, eax
0x180093924  jz      short loc_18009390C
0x180093926  mov     rcx, rsi; this
0x180093929  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x18009392e  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x180093935  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18009393a  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18009393f  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180093946  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18009394b  call    _CxxThrowException_0
```

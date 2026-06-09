# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x18002a3cc`
- end: `0x18002a4a8`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `220`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180029d08`
- `0x18002a52c`

## callees

- `0x18002a300`
- `0x18002a3cc`
- `0x1800345b0`
- `0x180037fb0`
- `0x180056524`
- `0x180058abc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a454`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a473`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002a426`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002a426`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a45d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a45d`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        Concurrency::details::_DefaultPPLTaskScheduler *this,
        void (*a2)(void *),
        void *a3)
{
  HMODULE v5; // rsi
  PTP_WORK ThreadpoolWork; // rax
  const WCHAR *v7; // rdx
  unsigned int v8; // edx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+68h] [rbp+20h] BYREF

  v5 = (HMODULE)operator new(0x28u);
  phModule = v5;
  *(_OWORD *)v5 = 0;
  *((_OWORD *)v5 + 1) = 0;
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback;
  *((_QWORD *)v5 + 2) = v5;
  *((_QWORD *)v5 + 3) = a2;
  *((_QWORD *)v5 + 4) = a3;
  ThreadpoolWork = CreateThreadpoolWork(Concurrency::details::_anonymous_namespace_::_Task_scheduler_callback, v5, 0);
  *(_QWORD *)v5 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    if ( (unsigned int)Concurrency::details::_anonymous_namespace_::_Get_STL_host_status() )
    {
      v7 = (const WCHAR *)*((_QWORD *)v5 + 1);
      phModule = 0;
      GetModuleHandleExW(4u, v7, &phModule);
    }
    SubmitThreadpoolWork(*(PTP_WORK *)v5);
  }
  else if ( GetLastError() )
  {
    Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(
      (Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *)v5,
      v8);
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Fail to schedule the chore!");
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002a3cc  mov     [rsp+arg_0], rbx
0x18002a3d1  mov     [rsp+arg_8], rsi
0x18002a3d6  push    rdi
0x18002a3d7  sub     rsp, 40h
0x18002a3db  mov     ecx, 28h ; '('; Size
0x18002a3e0  mov     rdi, r8
0x18002a3e3  mov     rbx, rdx
0x18002a3e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a3eb  mov     rsi, rax
0x18002a3ee  mov     [rsp+48h+phModule], rax
0x18002a3f3  xorps   xmm0, xmm0
0x18002a3f6  lea     rcx, Concurrency__details___anonymous_namespace____Task_scheduler_callback; pfnwk
0x18002a3fd  xor     eax, eax
0x18002a3ff  xor     r8d, r8d; pcbe
0x18002a402  mov     rdx, rsi; pv
0x18002a405  movups  xmmword ptr [rsi], xmm0
0x18002a408  movups  xmmword ptr [rsi+10h], xmm0
0x18002a40c  mov     [rsi], rax
0x18002a40f  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x18002a416  mov     [rsi+8], rax
0x18002a41a  mov     [rsi+10h], rsi
0x18002a41e  mov     [rsi+18h], rbx
0x18002a422  mov     [rsi+20h], rdi
0x18002a426  call    cs:__imp_CreateThreadpoolWork
0x18002a42c  mov     [rsi], rax
0x18002a42f  test    rax, rax
0x18002a432  jz      short loc_18002A473
0x18002a434  call    Concurrency__details___anonymous_namespace____Get_STL_host_status
0x18002a439  test    eax, eax
0x18002a43b  jz      short loc_18002A45A
0x18002a43d  mov     rdx, [rsi+8]; lpModuleName
0x18002a441  lea     r8, [rsp+48h+phModule]; phModule
0x18002a446  mov     ecx, 4; dwFlags
0x18002a44b  mov     [rsp+48h+phModule], 0
0x18002a454  call    cs:__imp_GetModuleHandleExW
0x18002a45a  mov     rcx, [rsi]; pwk
0x18002a45d  call    cs:__imp_SubmitThreadpoolWork
0x18002a463  mov     rbx, [rsp+48h+arg_0]
0x18002a468  mov     rsi, [rsp+48h+arg_8]
0x18002a46d  add     rsp, 40h
0x18002a471  pop     rdi
0x18002a472  retn
0x18002a473  call    cs:__imp_GetLastError
0x18002a479  test    eax, eax
0x18002a47b  jz      short loc_18002A463
0x18002a47d  mov     rcx, rsi; this
0x18002a480  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x18002a485  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x18002a48c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18002a491  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18002a496  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002a49d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18002a4a2  call    _CxxThrowException
```

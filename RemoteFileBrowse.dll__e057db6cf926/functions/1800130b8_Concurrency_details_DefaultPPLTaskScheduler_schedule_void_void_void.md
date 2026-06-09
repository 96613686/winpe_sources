# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x1800130b8`
- end: `0x18001313e`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `134`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012924`
- `0x180012a20`

## callees

- `0x18000208c`
- `0x180002de8`
- `0x18000f874`
- `0x180010768`
- `0x1800130b8`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x180013100`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x180013100`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        Concurrency::details::_DefaultPPLTaskScheduler *this,
        void (*a2)(void *),
        void *a3)
{
  Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *v5; // rsi
  struct Concurrency::details::_Threadpool_chore *v6; // rdx
  struct Concurrency::details::_Threadpool_chore *v7; // rdx
  const char *v8; // rdx
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
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v8);
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800130b8  mov     [rsp+arg_0], rbx
0x1800130bd  mov     [rsp+arg_8], rsi
0x1800130c2  push    rdi
0x1800130c3  sub     rsp, 40h
0x1800130c7  mov     ecx, 28h ; '('; Size
0x1800130cc  mov     rdi, r8
0x1800130cf  mov     rbx, rdx
0x1800130d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800130d7  mov     rsi, rax
0x1800130da  mov     [rsp+48h+arg_18], rax
0x1800130df  mov     rcx, rsi
0x1800130e2  mov     qword ptr [rax], 0
0x1800130e9  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x1800130f0  mov     [rsi+8], rax
0x1800130f4  mov     [rsi+10h], rsi
0x1800130f8  mov     [rsi+18h], rbx
0x1800130fc  mov     [rsi+20h], rdi
0x180013100  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x180013106  test    eax, eax
0x180013108  jnz     short loc_18001311A
0x18001310a  mov     rbx, [rsp+48h+arg_0]
0x18001310f  mov     rsi, [rsp+48h+arg_8]
0x180013114  add     rsp, 40h
0x180013118  pop     rdi
0x180013119  retn
0x18001311a  mov     rcx, rsi; this
0x18001311d  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x180013122  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180013127  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001312c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180013133  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180013138  call    _CxxThrowException_0
```

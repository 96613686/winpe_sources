# Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)

- ea: `0x18001a9e8`
- end: `0x18001aa6e`
- name: `?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z`
- size: `134`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180019d44`
- `0x180019e40`

## callees

- `0x1800021e4`
- `0x180002c10`
- `0x180016090`
- `0x180017438`
- `0x18001a9e8`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18001aa30`
- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x18001aa30`

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
0x18001a9e8  mov     [rsp+arg_0], rbx
0x18001a9ed  mov     [rsp+arg_8], rsi
0x18001a9f2  push    rdi
0x18001a9f3  sub     rsp, 40h
0x18001a9f7  mov     ecx, 28h ; '('; Size
0x18001a9fc  mov     rdi, r8
0x18001a9ff  mov     rbx, rdx
0x18001aa02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aa07  mov     rsi, rax
0x18001aa0a  mov     [rsp+48h+arg_18], rax
0x18001aa0f  mov     rcx, rsi
0x18001aa12  mov     qword ptr [rax], 0
0x18001aa19  lea     rax, ?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)
0x18001aa20  mov     [rsi+8], rax
0x18001aa24  mov     [rsi+10h], rsi
0x18001aa28  mov     [rsi+18h], rbx
0x18001aa2c  mov     [rsi+20h], rdi
0x18001aa30  call    cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)
0x18001aa36  test    eax, eax
0x18001aa38  jnz     short loc_18001AA4A
0x18001aa3a  mov     rbx, [rsp+48h+arg_0]
0x18001aa3f  mov     rsi, [rsp+48h+arg_8]
0x18001aa44  add     rsp, 40h
0x18001aa48  pop     rdi
0x18001aa49  retn
0x18001aa4a  mov     rcx, rsi; this
0x18001aa4d  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x18001aa52  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001aa57  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001aa5c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001aa63  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001aa68  call    _CxxThrowException_0
```

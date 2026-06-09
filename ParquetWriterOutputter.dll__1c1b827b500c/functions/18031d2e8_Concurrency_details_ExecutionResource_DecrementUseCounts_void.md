# Concurrency::details::ExecutionResource::DecrementUseCounts(void)

- ea: `0x18031d2e8`
- end: `0x18031d371`
- name: `?DecrementUseCounts@ExecutionResource@details@Concurrency@@QEAAXXZ`
- size: `137`
- prototype: `void __fastcall(Concurrency::details::ExecutionResource *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1803143a4`
- `0x18031d2e8`

## callees

- `0x180310aa0`
- `0x18031d2e8`
- `0x18031d530`
- `0x18031e64c`
- `0x18031e6a4`
- `0x18031e778`
- `0x18031f12c`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18031d329`
- `KERNEL32!GetCurrentThread` at `0x18031d329`

## pseudocode

```c
void __fastcall Concurrency::details::ExecutionResource::DecrementUseCounts(
        Concurrency::details::ExecutionResource *this)
{
  __int64 v3; // rdi
  Concurrency::details::ExecutionResource *v4; // rcx
  HANDLE CurrentThread; // rax

  if ( (*((_DWORD *)this + 19))-- == 1 )
  {
    v3 = *((_QWORD *)this + 6);
    Concurrency::details::ExecutionResource::ResetCurrent(this);
    v4 = (Concurrency::details::ExecutionResource *)*((_QWORD *)this + 5);
    if ( v4 )
    {
      Concurrency::details::ExecutionResource::DecrementUseCounts(v4);
      Concurrency::details::SchedulerProxy::RemoveThreadSubscription(
        *((Concurrency::details::SchedulerProxy **)this + 4),
        this);
    }
    else
    {
      Concurrency::details::SchedulerProxy::DecrementFixedCoreCount(
        *((Concurrency::details::SchedulerProxy **)this + 4),
        *((_DWORD *)this + 16),
        *((_DWORD *)this + 17),
        v3 == 0);
      if ( !v3 )
      {
        CurrentThread = GetCurrentThread();
        Concurrency::details::HardwareAffinity::ApplyTo(
          (Concurrency::details::ExecutionResource *)((char *)this + 16),
          CurrentThread);
        Concurrency::details::SchedulerProxy::DecrementCoreSubscription(
          *((Concurrency::details::SchedulerProxy **)this + 4),
          this);
        Concurrency::details::SchedulerProxy::DestroyExecutionResource(
          *((Concurrency::details::SchedulerProxy **)this + 4),
          this);
      }
    }
  }
}

```

## disassembly

```asm
0x18031d2e8  mov     [rsp+arg_0], rbx
0x18031d2ed  push    rdi
0x18031d2ee  sub     rsp, 20h
0x18031d2f2  add     dword ptr [rcx+4Ch], 0FFFFFFFFh
0x18031d2f6  mov     rbx, rcx
0x18031d2f9  jnz     short loc_18031D366
0x18031d2fb  mov     rdi, [rcx+30h]
0x18031d2ff  call    ?ResetCurrent@ExecutionResource@details@Concurrency@@QEAAXXZ; Concurrency::details::ExecutionResource::ResetCurrent(void)
0x18031d304  mov     rcx, [rbx+28h]; this
0x18031d308  test    rcx, rcx
0x18031d30b  jnz     short loc_18031D355
0x18031d30d  mov     r8d, [rbx+44h]; unsigned int
0x18031d311  test    rdi, rdi
0x18031d314  mov     edx, [rbx+40h]; unsigned int
0x18031d317  mov     rcx, [rbx+20h]; this
0x18031d31b  setz    r9b; bool
0x18031d31f  call    ?DecrementFixedCoreCount@SchedulerProxy@details@Concurrency@@QEAAXII_N@Z; Concurrency::details::SchedulerProxy::DecrementFixedCoreCount(uint,uint,bool)
0x18031d324  test    rdi, rdi
0x18031d327  jnz     short loc_18031D366
0x18031d329  call    cs:__imp_GetCurrentThread
0x18031d32f  mov     rdx, rax; hThread
0x18031d332  lea     rcx, [rbx+10h]; this
0x18031d336  call    ?ApplyTo@HardwareAffinity@details@Concurrency@@QEAAXPEAX@Z; Concurrency::details::HardwareAffinity::ApplyTo(void *)
0x18031d33b  mov     rcx, [rbx+20h]; this
0x18031d33f  mov     rdx, rbx; struct Concurrency::details::ExecutionResource *
0x18031d342  call    ?DecrementCoreSubscription@SchedulerProxy@details@Concurrency@@QEAAXPEAVExecutionResource@23@@Z; Concurrency::details::SchedulerProxy::DecrementCoreSubscription(Concurrency::details::ExecutionResource *)
0x18031d347  mov     rcx, [rbx+20h]; this
0x18031d34b  mov     rdx, rbx; struct Concurrency::details::ExecutionResource *
0x18031d34e  call    ?DestroyExecutionResource@SchedulerProxy@details@Concurrency@@QEAAXPEAVExecutionResource@23@@Z; Concurrency::details::SchedulerProxy::DestroyExecutionResource(Concurrency::details::ExecutionResource *)
0x18031d353  jmp     short loc_18031D366
0x18031d355  call    ?DecrementUseCounts@ExecutionResource@details@Concurrency@@QEAAXXZ; Concurrency::details::ExecutionResource::DecrementUseCounts(void)
0x18031d35a  mov     rcx, [rbx+20h]; this
0x18031d35e  mov     rdx, rbx; struct Concurrency::details::ExecutionResource *
0x18031d361  call    ?RemoveThreadSubscription@SchedulerProxy@details@Concurrency@@QEAAXPEAVExecutionResource@23@@Z; Concurrency::details::SchedulerProxy::RemoveThreadSubscription(Concurrency::details::ExecutionResource *)
0x18031d366  mov     rbx, [rsp+28h+arg_0]
0x18031d36b  add     rsp, 20h
0x18031d36f  pop     rdi
0x18031d370  retn
```

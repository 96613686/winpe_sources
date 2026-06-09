# Concurrency::details::ExecutionResource::IncrementUseCounts(void)

- ea: `0x18031d394`
- end: `0x18031d489`
- name: `?IncrementUseCounts@ExecutionResource@details@Concurrency@@QEAAXXZ`
- size: `245`
- prototype: `void __fastcall(Concurrency::details::ExecutionResource *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18031e450`
- `0x18031e9f8`
- `0x18031ef5c`

## callees

- `0x18030c3f0`
- `0x180310584`
- `0x180310aa0`
- `0x18031d394`
- `0x18031d55c`
- `0x18031e084`
- `0x18031e124`
- `0x18031ee54`
- `0x18031eeb0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18031d3ec`
- `KERNEL32!GetCurrentThread` at `0x18031d3ec`

## pseudocode

```c
void __fastcall Concurrency::details::ExecutionResource::IncrementUseCounts(
        Concurrency::details::ExecutionResource *this)
{
  int v2; // ecx
  __int64 v3; // rbx
  Concurrency::details::SchedulerProxy *v4; // rcx
  Concurrency::details::platform *CurrentThread; // rbx
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  _QWORD v10[2]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v11[16]; // [rsp+30h] [rbp-28h] BYREF

  v2 = *((_DWORD *)this + 19);
  *((_DWORD *)this + 19) = v2 + 1;
  if ( !v2 )
  {
    v3 = *((_QWORD *)this + 6);
    v4 = (Concurrency::details::SchedulerProxy *)*((_QWORD *)this + 4);
    if ( *((_QWORD *)this + 5) )
    {
      Concurrency::details::SchedulerProxy::AddThreadSubscription(v4, this);
    }
    else
    {
      Concurrency::details::SchedulerProxy::IncrementFixedCoreCount(
        v4,
        *((_DWORD *)this + 16),
        *((_DWORD *)this + 17),
        v3 == 0);
      if ( !v3 )
      {
        CurrentThread = (Concurrency::details::platform *)GetCurrentThread();
        v6 = Concurrency::details::HardwareAffinity::HardwareAffinity(
               (Concurrency::details::HardwareAffinity *)v11,
               CurrentThread);
        *((_WORD *)this + 12) = *(_WORD *)(v6 + 8);
        *((_QWORD *)this + 2) = *(_QWORD *)v6;
        v7 = (unsigned __int64)*((unsigned int *)this + 16) << 6;
        v8 = *(_QWORD *)(*((_QWORD *)this + 4) + 32LL);
        v9 = *(_QWORD *)(v7 + v8);
        v10[1] = *(unsigned __int16 *)(v7 + v8 + 16);
        v10[0] = v9;
        Concurrency::details::HardwareAffinity::ApplyTo((Concurrency::details::HardwareAffinity *)v10, CurrentThread);
        Concurrency::details::SchedulerProxy::IncrementCoreSubscription(
          *((Concurrency::details::SchedulerProxy **)this + 4),
          this);
        Concurrency::details::SchedulerProxy::AddExecutionResource(
          *((Concurrency::details::SchedulerProxy **)this + 4),
          this);
      }
    }
    Concurrency::details::ExecutionResource::SetAsCurrent(this);
  }
}

```

## disassembly

```asm
0x18031d394  mov     [rsp+arg_8], rbx
0x18031d399  push    rdi
0x18031d39a  sub     rsp, 50h
0x18031d39e  mov     rax, cs:__security_cookie
0x18031d3a5  xor     rax, rsp
0x18031d3a8  mov     [rsp+58h+var_18], rax
0x18031d3ad  mov     rdi, rcx
0x18031d3b0  mov     ecx, [rcx+4Ch]
0x18031d3b3  lea     eax, [rcx+1]
0x18031d3b6  mov     [rdi+4Ch], eax
0x18031d3b9  test    ecx, ecx
0x18031d3bb  jnz     loc_18031D471
0x18031d3c1  cmp     qword ptr [rdi+28h], 0
0x18031d3c6  mov     rbx, [rdi+30h]
0x18031d3ca  mov     rcx, [rdi+20h]; this
0x18031d3ce  jnz     loc_18031D461
0x18031d3d4  mov     r8d, [rdi+44h]; unsigned int
0x18031d3d8  test    rbx, rbx
0x18031d3db  mov     edx, [rdi+40h]; unsigned int
0x18031d3de  setz    r9b; bool
0x18031d3e2  call    ?IncrementFixedCoreCount@SchedulerProxy@details@Concurrency@@QEAAXII_N@Z; Concurrency::details::SchedulerProxy::IncrementFixedCoreCount(uint,uint,bool)
0x18031d3e7  test    rbx, rbx
0x18031d3ea  jnz     short loc_18031D469
0x18031d3ec  call    cs:__imp_GetCurrentThread
0x18031d3f2  mov     rdx, rax; Concurrency::details::platform *
0x18031d3f5  lea     rcx, [rsp+58h+var_28]; this
0x18031d3fa  mov     rbx, rax
0x18031d3fd  call    ??0HardwareAffinity@details@Concurrency@@QEAA@PEAX@Z; Concurrency::details::HardwareAffinity::HardwareAffinity(void *)
0x18031d402  movzx   ecx, word ptr [rax+8]
0x18031d406  mov     [rdi+18h], cx
0x18031d40a  mov     rcx, [rax]
0x18031d40d  mov     [rdi+10h], rcx
0x18031d411  mov     rcx, [rdi+20h]
0x18031d415  mov     edx, [rdi+40h]
0x18031d418  shl     rdx, 6
0x18031d41c  mov     rcx, [rcx+20h]
0x18031d420  mov     r8, [rdx+rcx]
0x18031d424  movzx   eax, word ptr [rdx+rcx+10h]
0x18031d429  xor     ecx, ecx
0x18031d42b  mov     [rsp+58h+var_30], rcx
0x18031d430  mov     rdx, rbx; hThread
0x18031d433  lea     rcx, [rsp+58h+var_38]; this
0x18031d438  mov     word ptr [rsp+58h+var_30], ax
0x18031d43d  mov     [rsp+58h+var_38], r8
0x18031d442  call    ?ApplyTo@HardwareAffinity@details@Concurrency@@QEAAXPEAX@Z; Concurrency::details::HardwareAffinity::ApplyTo(void *)
0x18031d447  mov     rcx, [rdi+20h]; this
0x18031d44b  mov     rdx, rdi; struct Concurrency::details::ExecutionResource *
0x18031d44e  call    ?IncrementCoreSubscription@SchedulerProxy@details@Concurrency@@QEAAXPEAVExecutionResource@23@@Z; Concurrency::details::SchedulerProxy::IncrementCoreSubscription(Concurrency::details::ExecutionResource *)
0x18031d453  mov     rcx, [rdi+20h]; this
0x18031d457  mov     rdx, rdi; struct Concurrency::details::ExecutionResource *
0x18031d45a  call    ?AddExecutionResource@SchedulerProxy@details@Concurrency@@QEAAXPEAVExecutionResource@23@@Z; Concurrency::details::SchedulerProxy::AddExecutionResource(Concurrency::details::ExecutionResource *)
0x18031d45f  jmp     short loc_18031D469
0x18031d461  mov     rdx, rdi; struct Concurrency::details::ExecutionResource *
0x18031d464  call    ?AddThreadSubscription@SchedulerProxy@details@Concurrency@@QEAAXPEAVExecutionResource@23@@Z; Concurrency::details::SchedulerProxy::AddThreadSubscription(Concurrency::details::ExecutionResource *)
0x18031d469  mov     rcx, rdi; this
0x18031d46c  call    ?SetAsCurrent@ExecutionResource@details@Concurrency@@QEAAXXZ; Concurrency::details::ExecutionResource::SetAsCurrent(void)
0x18031d471  mov     rcx, [rsp+58h+var_18]
0x18031d476  xor     rcx, rsp; StackCookie
0x18031d479  call    __security_check_cookie
0x18031d47e  mov     rbx, [rsp+58h+arg_8]
0x18031d483  add     rsp, 50h
0x18031d487  pop     rdi
0x18031d488  retn
```

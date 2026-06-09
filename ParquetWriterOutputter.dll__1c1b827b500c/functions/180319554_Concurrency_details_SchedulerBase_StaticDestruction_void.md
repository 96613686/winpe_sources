# Concurrency::details::SchedulerBase::StaticDestruction(void)

- ea: `0x180319554`
- end: `0x180319607`
- name: `?StaticDestruction@SchedulerBase@details@Concurrency@@CAXXZ`
- size: `179`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1803163d8`

## callees

- `0x18030c180`
- `0x18030c200`
- `0x18030dca4`
- `0x180319554`
- `0x18032069c`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1803195e9`
- `KERNEL32!InterlockedPopEntrySList` at `0x1803195e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::SchedulerBase::StaticDestruction(Concurrency::details *a1)
{
  PSLIST_ENTRY v1; // rax
  PSLIST_ENTRY v2; // rbx
  _BYTE v3[8]; // [rsp+28h] [rbp-20h] BYREF
  int v4; // [rsp+30h] [rbp-18h]
  void (__fastcall *v5)(Concurrency::details *__hidden); // [rsp+38h] [rbp-10h]

  if ( _InterlockedExchange((volatile __int32 *)&Concurrency::details::SchedulerBase::s_schedulerLock, 1) )
  {
    v4 = 0;
    v5 = Concurrency::details::_Sleep0;
    do
      Concurrency::details::_SpinWait<1>::_SpinOnce(v3);
    while ( _InterlockedExchange((volatile __int32 *)&Concurrency::details::SchedulerBase::s_schedulerLock, 1) );
  }
  if ( !--Concurrency::details::SchedulerBase::s_initializedCount )
  {
    Concurrency::details::_UnregisterConcRTEventTracing(a1);
    while ( 1 )
    {
      v1 = InterlockedPopEntrySList(&Concurrency::details::SchedulerBase::s_subAllocatorFreePool);
      v2 = v1;
      if ( !v1 )
        break;
      `eh vector destructor iterator'(
        &v1[1],
        0x10u,
        0x60u,
        (void (*)(void *))Concurrency::details::AllocatorBucket::~AllocatorBucket);
      operator delete(v2, 0x620u);
    }
  }
  Concurrency::details::SchedulerBase::s_schedulerLock = 0;
}

```

## disassembly

```asm
0x180319554  push    rbx
0x180319556  sub     rsp, 40h
0x18031955a  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180319563  lea     rax, ?s_schedulerLock@SchedulerBase@details@Concurrency@@0V_NonReentrantLock@23@A
0x18031956a  mov     [rsp+48h+arg_0], rax
0x18031956f  mov     ebx, 1
0x180319574  mov     eax, ebx
0x180319576  xchg    eax, cs:?s_schedulerLock@SchedulerBase@details@Concurrency@@0V_NonReentrantLock@23@A
0x18031957c  test    eax, eax
0x18031957e  jz      short loc_1803195A7
0x180319580  and     [rsp+48h+var_18], 0
0x180319585  lea     rax, ?_Sleep0@details@Concurrency@@YAXXZ
0x18031958c  mov     [rsp+48h+var_10], rax
0x180319591  lea     rcx, [rsp+48h+var_20]
0x180319596  call    ?_SpinOnce@?$_SpinWait@$00@details@Concurrency@@QEAA_NXZ
0x18031959b  mov     eax, ebx
0x18031959d  xchg    eax, cs:?s_schedulerLock@SchedulerBase@details@Concurrency@@0V_NonReentrantLock@23@A
0x1803195a3  test    eax, eax
0x1803195a5  jnz     short loc_180319591
0x1803195a7  sub     cs:?s_initializedCount@SchedulerBase@details@Concurrency@@0JA, ebx
0x1803195ad  jnz     short loc_1803195F7
0x1803195af  call    ?_UnregisterConcRTEventTracing@details@Concurrency@@YAXXZ
0x1803195b4  jmp     short loc_1803195E2
0x1803195b6  test    rbx, rbx
0x1803195b9  jz      short loc_1803195E2
0x1803195bb  lea     rcx, [rbx+10h]; void *
0x1803195bf  lea     r9, ??1AllocatorBucket@details@Concurrency@@QEAA@XZ; void (*)(void *)
0x1803195c6  mov     edx, 10h; unsigned __int64
0x1803195cb  lea     r8d, [rdx+50h]; unsigned __int64
0x1803195cf  call    ??_M@YAXPEAX_K1P6AX0@Z@Z
0x1803195d4  nop
0x1803195d5  mov     edx, 620h; unsigned __int64
0x1803195da  mov     rcx, rbx; void *
0x1803195dd  call    ??3@YAXPEAX_K@Z
0x1803195e2  lea     rcx, ?s_subAllocatorFreePool@SchedulerBase@details@Concurrency@@0V?$LockFreeStack@VSubAllocator@details@Concurrency@@@23@A; ListHead
0x1803195e9  call    cs:__imp_InterlockedPopEntrySList
0x1803195ef  test    rax, rax
0x1803195f2  mov     rbx, rax
0x1803195f5  jnz     short loc_1803195B6
0x1803195f7  mov     cs:?s_schedulerLock@SchedulerBase@details@Concurrency@@0V_NonReentrantLock@23@A, 0
0x180319601  add     rsp, 40h
0x180319605  pop     rbx
0x180319606  retn
```

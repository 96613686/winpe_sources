# Concurrency::details::SchedulerBase::GetSubAllocator(bool)

- ea: `0x180317808`
- end: `0x1803178aa`
- name: `?GetSubAllocator@SchedulerBase@details@Concurrency@@SAPEAVSubAllocator@23@_N@Z`
- size: `162`
- prototype: `struct Concurrency::details::SubAllocator *__fastcall(bool)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180320b74`
- `0x1803265f0`
- `0x180326730`

## callees

- `0x1802f0fb0`
- `0x18030c414`
- `0x180317808`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180317840`
- `KERNEL32!InterlockedPopEntrySList` at `0x180317840`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Concurrency::details::SubAllocator *__fastcall Concurrency::details::SchedulerBase::GetSubAllocator(char a1)
{
  PSLIST_ENTRY v3; // rbx
  struct _SLIST_ENTRY *v4; // rax

  if ( a1 )
  {
    if ( Concurrency::details::SchedulerBase::s_numExternalAllocators >= 32 )
      return 0;
    _InterlockedIncrement(&Concurrency::details::SchedulerBase::s_numExternalAllocators);
  }
  v3 = InterlockedPopEntrySList(&Concurrency::details::SchedulerBase::s_subAllocatorFreePool);
  if ( !v3 )
  {
    v4 = (struct _SLIST_ENTRY *)operator new(0x620u);
    v3 = v4;
    if ( v4 )
    {
      `eh vector constructor iterator'(
        &v4[1],
        0x10u,
        0x60u,
        (void (*)(void *))Concurrency::details::AllocatorBucket::AllocatorBucket,
        (void (*)(void *))Concurrency::details::AllocatorBucket::~AllocatorBucket);
      LOBYTE(v3[97].Next) = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  LOBYTE(v3[97].Next) = a1;
  return (struct Concurrency::details::SubAllocator *)v3;
}

```

## disassembly

```asm
0x180317808  push    rdi
0x18031780a  sub     rsp, 40h
0x18031780e  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180317817  mov     [rsp+48h+arg_0], rbx
0x18031781c  mov     dil, cl
0x18031781f  test    cl, cl
0x180317821  jz      short loc_180317839
0x180317823  mov     eax, cs:?s_numExternalAllocators@SchedulerBase@details@Concurrency@@0JC
0x180317829  cmp     eax, 20h ; ' '
0x18031782c  jl      short loc_180317832
0x18031782e  xor     eax, eax
0x180317830  jmp     short loc_18031789F
0x180317832  lock inc cs:?s_numExternalAllocators@SchedulerBase@details@Concurrency@@0JC
0x180317839  lea     rcx, ?s_subAllocatorFreePool@SchedulerBase@details@Concurrency@@0V?$LockFreeStack@VSubAllocator@details@Concurrency@@@23@A; ListHead
0x180317840  call    cs:__imp_InterlockedPopEntrySList
0x180317846  mov     rbx, rax
0x180317849  test    rax, rax
0x18031784c  jnz     short loc_180317895
0x18031784e  mov     ecx, 620h; Size
0x180317853  call    ??2@YAPEAX_K@Z
0x180317858  mov     rbx, rax
0x18031785b  mov     [rsp+48h+arg_8], rax
0x180317860  test    rax, rax
0x180317863  jz      short loc_180317893
0x180317865  lea     rcx, [rax+10h]; void *
0x180317869  lea     rax, ??1AllocatorBucket@details@Concurrency@@QEAA@XZ
0x180317870  mov     [rsp+48h+var_28], rax; void (*)(void *)
0x180317875  lea     r9, ??0AllocatorBucket@details@Concurrency@@QEAA@XZ; void (*)(void *)
0x18031787c  mov     edx, 10h; unsigned __int64
0x180317881  lea     r8d, [rdx+50h]; unsigned __int64
0x180317885  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z
0x18031788a  mov     byte ptr [rbx+610h], 0
0x180317891  jmp     short loc_180317895
0x180317893  xor     ebx, ebx
0x180317895  mov     [rbx+610h], dil
0x18031789c  mov     rax, rbx
0x18031789f  mov     rbx, [rsp+48h+arg_0]
0x1803178a4  add     rsp, 40h
0x1803178a8  pop     rdi
0x1803178a9  retn
```

# Concurrency::details::ContextBase::CreateWorkQueue(void)

- ea: `0x18031a8ac`
- end: `0x18031a953`
- name: `?CreateWorkQueue@ContextBase@details@Concurrency@@QEAAXXZ`
- size: `167`
- prototype: `void __fastcall(Concurrency::details::ContextBase *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18031b77c`
- `0x18031bfe4`

## callees

- `0x1802f0fb0`
- `0x18031a274`
- `0x18031a8ac`
- `0x1803251f8`
- `0x180326ff4`
- `0x180327094`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18031a8e2`
- `KERNEL32!InterlockedPopEntrySList` at `0x18031a8e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::ContextBase::CreateWorkQueue(
        Concurrency::details::ScheduleGroupSegmentBase **this)
{
  struct Concurrency::details::WorkQueue *DetachedWorkQueue; // rax
  __int64 v3; // rdi
  PSLIST_ENTRY v4; // rax
  Concurrency::details::WorkQueue *v5; // rcx
  Concurrency::details::WorkQueue *v6; // rax

  DetachedWorkQueue = Concurrency::details::ScheduleGroupSegmentBase::GetDetachedWorkQueue(this[6]);
  this[8] = DetachedWorkQueue;
  v3 = 0;
  if ( !DetachedWorkQueue )
  {
    v4 = InterlockedPopEntrySList((PSLIST_HEADER)this[6] + 10);
    v5 = 0;
    if ( v4 )
      v5 = (Concurrency::details::WorkQueue *)&v4[-3];
    this[8] = v5;
    if ( v5 )
    {
      Concurrency::details::WorkQueue::Reinitialize(v5);
      v3 = (__int64)this[8];
    }
    else
    {
      v6 = (Concurrency::details::WorkQueue *)operator new(0xF0u);
      if ( v6 )
        v3 = Concurrency::details::WorkQueue::WorkQueue(v6);
      this[8] = (Concurrency::details::ScheduleGroupSegmentBase *)v3;
    }
    Concurrency::details::ListArray<Concurrency::details::WorkQueue>::Add((char *)this[6] + 160, v3);
  }
  *((_QWORD *)this[8] + 21) = this;
}

```

## disassembly

```asm
0x18031a8ac  push    rdi
0x18031a8ae  sub     rsp, 30h
0x18031a8b2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18031a8bb  mov     [rsp+38h+arg_8], rbx
0x18031a8c0  mov     rbx, rcx
0x18031a8c3  mov     rcx, [rcx+30h]; this
0x18031a8c7  call    ?GetDetachedWorkQueue@ScheduleGroupSegmentBase@details@Concurrency@@IEAAPEAVWorkQueue@23@XZ; Concurrency::details::ScheduleGroupSegmentBase::GetDetachedWorkQueue(void)
0x18031a8cc  mov     [rbx+40h], rax
0x18031a8d0  xor     edi, edi
0x18031a8d2  test    rax, rax
0x18031a8d5  jnz     short loc_18031A93D
0x18031a8d7  mov     rcx, [rbx+30h]
0x18031a8db  add     rcx, 0A0h; ListHead
0x18031a8e2  call    cs:__imp_InterlockedPopEntrySList
0x18031a8e8  test    rax, rax
0x18031a8eb  mov     ecx, edi
0x18031a8ed  jz      short loc_18031A8F3
0x18031a8ef  lea     rcx, [rax-30h]; this
0x18031a8f3  mov     [rbx+40h], rcx
0x18031a8f7  test    rcx, rcx
0x18031a8fa  jnz     short loc_18031A921
0x18031a8fc  mov     ecx, 0F0h; Size
0x18031a901  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18031a906  mov     [rsp+38h+arg_0], rax
0x18031a90b  test    rax, rax
0x18031a90e  jz      short loc_18031A91B
0x18031a910  mov     rcx, rax; this
0x18031a913  call    ??0WorkQueue@details@Concurrency@@QEAA@XZ; Concurrency::details::WorkQueue::WorkQueue(void)
0x18031a918  mov     rdi, rax
0x18031a91b  mov     [rbx+40h], rdi
0x18031a91f  jmp     short loc_18031A92A
0x18031a921  call    ?Reinitialize@WorkQueue@details@Concurrency@@AEAAXXZ; Concurrency::details::WorkQueue::Reinitialize(void)
0x18031a926  mov     rdi, [rbx+40h]
0x18031a92a  mov     rcx, [rbx+30h]
0x18031a92e  add     rcx, 0A0h
0x18031a935  mov     rdx, rdi
0x18031a938  call    ?Add@?$ListArray@VWorkQueue@details@Concurrency@@@details@Concurrency@@QEAAHPEAVWorkQueue@23@@Z; Concurrency::details::ListArray<Concurrency::details::WorkQueue>::Add(Concurrency::details::WorkQueue *)
0x18031a93d  mov     rax, [rbx+40h]
0x18031a941  mov     [rax+0A8h], rbx
0x18031a948  mov     rbx, [rsp+38h+arg_8]
0x18031a94d  add     rsp, 30h
0x18031a951  pop     rdi
0x18031a952  retn
```

# Concurrency::details::ScheduleGroupBase::CreateSegment(Concurrency::location *,Concurrency::details::SchedulingRing *)

- ea: `0x180324e74`
- end: `0x180324f64`
- name: `?CreateSegment@ScheduleGroupBase@details@Concurrency@@IEAAPEAVScheduleGroupSegmentBase@23@PEAVlocation@3@PEAVSchedulingRing@23@@Z`
- size: `240`
- prototype: `struct Concurrency::details::ScheduleGroupSegmentBase *__fastcall(Concurrency::details::ScheduleGroupBase *__hidden this, struct Concurrency::location *, struct Concurrency::details::SchedulingRing *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180323f20`
- `0x180325610`
- `0x180326420`

## callees

- `0x180324130`
- `0x180324b60`
- `0x180324e74`
- `0x18032542c`
- `0x180358070`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180324ebc`
- `KERNEL32!InterlockedPopEntrySList` at `0x180324ebc`

## pseudocode

```c
struct Concurrency::details::ScheduleGroupSegmentBase *__fastcall Concurrency::details::ScheduleGroupBase::CreateSegment(
        Concurrency::details::ScheduleGroupBase *this,
        struct Concurrency::location *a2,
        struct Concurrency::details::SchedulingRing *a3)
{
  union _SLIST_HEADER *v4; // rcx
  unsigned __int64 v7; // rsi
  PSLIST_ENTRY v8; // rax
  __int64 v9; // rbx

  v4 = (union _SLIST_HEADER *)((char *)a3 + 160);
  v7 = -(__int64)((*(_DWORD *)a2 & 0xFFFFFFF) != 0) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( (*(_DWORD *)a2 & 0xFFFFFFF) != 0 )
    v4 = (union _SLIST_HEADER *)((char *)a3 + 32);
  v8 = InterlockedPopEntrySList(v4);
  if ( !v8 || (v9 = (__int64)&v8[-30], v8 == (PSLIST_ENTRY)480) )
    v9 = (*(__int64 (__fastcall **)(Concurrency::details::ScheduleGroupBase *, struct Concurrency::details::SchedulingRing *, struct Concurrency::location *))(*(_QWORD *)this + 64LL))(
           this,
           a3,
           a2);
  else
    Concurrency::details::ScheduleGroupSegmentBase::Initialize(
      (Concurrency::details::ScheduleGroupSegmentBase *)&v8[-30],
      this,
      a3,
      a2);
  *(_QWORD *)(v9 + 432) = *(_QWORD *)((char *)this + v7 + 32);
  *(_QWORD *)((char *)this + v7 + 32) = v9;
  if ( !*((_DWORD *)a3 + 75) )
    Concurrency::details::SchedulingRing::Activate(a3);
  Concurrency::details::ListArray<Concurrency::details::ScheduleGroupSegmentBase>::Add(
    (char *)a3 + (-(__int64)((*(_DWORD *)a2 & 0xFFFFFFF) != 0) & 0xFFFFFFFFFFFFFF80uLL) + 160,
    v9);
  return (struct Concurrency::details::ScheduleGroupSegmentBase *)v9;
}

```

## disassembly

```asm
0x180324e74  mov     rax, rsp
0x180324e77  mov     [rax+8], rbx
0x180324e7b  mov     [rax+10h], rsi
0x180324e7f  mov     [rax+18h], rdi
0x180324e83  mov     [rax+20h], r14
0x180324e87  push    r15
0x180324e89  sub     rsp, 20h
0x180324e8d  mov     r9d, [rdx]
0x180324e90  mov     r15, rcx
0x180324e93  and     r9d, 0FFFFFFFh
0x180324e9a  lea     rcx, [r8+0A0h]
0x180324ea1  mov     eax, r9d
0x180324ea4  mov     rdi, r8
0x180324ea7  neg     eax
0x180324ea9  mov     r14, rdx
0x180324eac  sbb     rsi, rsi
0x180324eaf  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180324eb3  test    r9d, r9d
0x180324eb6  jz      short loc_180324EBC
0x180324eb8  lea     rcx, [r8+20h]; ListHead
0x180324ebc  call    cs:__imp_InterlockedPopEntrySList
0x180324ec2  test    rax, rax
0x180324ec5  jz      short loc_180324EE6
0x180324ec7  lea     rbx, [rax-1E0h]
0x180324ece  test    rbx, rbx
0x180324ed1  jz      short loc_180324EE6
0x180324ed3  mov     r9, r14; struct Concurrency::location *
0x180324ed6  mov     r8, rdi; struct Concurrency::details::SchedulingRing *
0x180324ed9  mov     rdx, r15; struct Concurrency::details::ScheduleGroupBase *
0x180324edc  mov     rcx, rbx; this
0x180324edf  call    ?Initialize@ScheduleGroupSegmentBase@details@Concurrency@@IEAAXPEAVScheduleGroupBase@23@PEAVSchedulingRing@23@PEAVlocation@3@@Z; Concurrency::details::ScheduleGroupSegmentBase::Initialize(Concurrency::details::ScheduleGroupBase *,Concurrency::details::SchedulingRing *,Concurrency::location *)
0x180324ee4  jmp     short loc_180324EFF
0x180324ee6  mov     rax, [r15]
0x180324ee9  mov     r8, r14
0x180324eec  mov     rdx, rdi
0x180324eef  mov     rcx, r15
0x180324ef2  mov     rax, [rax+40h]
0x180324ef6  call    cs:__guard_dispatch_icall_fptr
0x180324efc  mov     rbx, rax
0x180324eff  mov     rcx, [rsi+r15+20h]
0x180324f04  mov     [rbx+1B0h], rcx
0x180324f0b  mov     [rsi+r15+20h], rbx
0x180324f10  mov     ecx, [rdi+12Ch]
0x180324f16  test    ecx, ecx
0x180324f18  jnz     short loc_180324F22
0x180324f1a  mov     rcx, rdi; this
0x180324f1d  call    ?Activate@SchedulingRing@details@Concurrency@@QEAAXXZ; Concurrency::details::SchedulingRing::Activate(void)
0x180324f22  mov     ecx, [r14]
0x180324f25  mov     rdx, rbx
0x180324f28  and     ecx, 0FFFFFFFh
0x180324f2e  neg     ecx
0x180324f30  sbb     rcx, rcx
0x180324f33  add     rdi, 0A0h
0x180324f3a  and     rcx, 0FFFFFFFFFFFFFF80h
0x180324f3e  add     rcx, rdi
0x180324f41  call    ?Add@?$ListArray@VScheduleGroupSegmentBase@details@Concurrency@@@details@Concurrency@@QEAAHPEAVScheduleGroupSegmentBase@23@@Z; Concurrency::details::ListArray<Concurrency::details::ScheduleGroupSegmentBase>::Add(Concurrency::details::ScheduleGroupSegmentBase *)
0x180324f46  mov     rsi, [rsp+28h+arg_8]
0x180324f4b  mov     rax, rbx
0x180324f4e  mov     rbx, [rsp+28h+arg_0]
0x180324f53  mov     rdi, [rsp+28h+arg_10]
0x180324f58  mov     r14, [rsp+28h+arg_18]
0x180324f5d  add     rsp, 20h
0x180324f61  pop     r15
0x180324f63  retn
```

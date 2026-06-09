# Concurrency::details::SchedulerBase::GetRealizedChore(void (*)(void *),void *)

- ea: `0x180317780`
- end: `0x1803177e2`
- name: `?GetRealizedChore@SchedulerBase@details@Concurrency@@QEAAPEAVRealizedChore@23@P6AXPEAX@Z0@Z`
- size: `98`
- prototype: `struct Concurrency::details::RealizedChore *__fastcall(Concurrency::details::SchedulerBase *__hidden this, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180325bdc`

## callees

- `0x1802f0fb0`
- `0x180317780`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180317797`
- `KERNEL32!InterlockedPopEntrySList` at `0x180317797`

## pseudocode

```c
struct Concurrency::details::RealizedChore *__fastcall Concurrency::details::SchedulerBase::GetRealizedChore(
        union _SLIST_HEADER *this,
        void (*a2)(void *),
        void *a3)
{
  PSLIST_ENTRY v5; // rax
  struct Concurrency::details::RealizedChore *result; // rax

  v5 = InterlockedPopEntrySList(this + 49);
  result = (struct Concurrency::details::RealizedChore *)((unsigned __int64)&v5[-2] & -(__int64)(v5 != 0));
  if ( !result )
  {
    result = (struct Concurrency::details::RealizedChore *)operator new(0x30u);
    if ( !result )
      return result;
    *(_QWORD *)result = &Concurrency::details::RealizedChore::`vftable';
  }
  *((_QWORD *)result + 4) = 0;
  *((_QWORD *)result + 2) = a3;
  *((_QWORD *)result + 1) = a2;
  return result;
}

```

## disassembly

```asm
0x180317780  mov     [rsp+arg_8], rbx
0x180317785  push    rdi
0x180317786  sub     rsp, 20h
0x18031778a  add     rcx, 310h; ListHead
0x180317791  mov     rbx, r8
0x180317794  mov     rdi, rdx
0x180317797  call    cs:__imp_InterlockedPopEntrySList
0x18031779d  lea     rcx, [rax-20h]
0x1803177a1  neg     rax
0x1803177a4  sbb     rax, rax
0x1803177a7  and     rax, rcx
0x1803177aa  jnz     short loc_1803177C8
0x1803177ac  lea     ecx, [rax+30h]; Size
0x1803177af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1803177b4  mov     [rsp+28h+arg_0], rax
0x1803177b9  test    rax, rax
0x1803177bc  jz      short loc_1803177D5
0x1803177be  lea     rcx, ??_7RealizedChore@details@Concurrency@@6B@; const Concurrency::details::RealizedChore::`vftable'
0x1803177c5  mov     [rax], rcx
0x1803177c8  and     qword ptr [rax+20h], 0
0x1803177cd  mov     [rax+10h], rbx
0x1803177d1  mov     [rax+8], rdi
0x1803177d5  mov     rbx, [rsp+28h+arg_8]
0x1803177da  add     rsp, 20h
0x1803177de  pop     rdi
0x1803177df  retn
0x1803177e0  jmp     short loc_1803177D5
```

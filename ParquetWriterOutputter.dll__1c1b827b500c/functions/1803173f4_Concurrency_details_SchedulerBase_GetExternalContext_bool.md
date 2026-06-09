# Concurrency::details::SchedulerBase::GetExternalContext(bool)

- ea: `0x1803173f4`
- end: `0x180317474`
- name: `?GetExternalContext@SchedulerBase@details@Concurrency@@AEAAPEAVExternalContextBase@23@_N@Z`
- size: `128`
- prototype: `struct Concurrency::details::ExternalContextBase *__fastcall(Concurrency::details::SchedulerBase *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180316098`

## callees

- `0x1802f0fb0`
- `0x1803173f4`
- `0x1803264c0`
- `0x18032684c`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18031741a`
- `KERNEL32!InterlockedPopEntrySList` at `0x18031741a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Concurrency::details::ExternalContextBase *__fastcall Concurrency::details::SchedulerBase::GetExternalContext(
        union _SLIST_HEADER *this,
        char a2)
{
  PSLIST_ENTRY v4; // rax
  PSLIST_ENTRY v5; // r8
  __int64 v6; // rax
  __int64 v7; // rbx
  Concurrency::details::ExternalContextBase *v8; // rax

  v4 = InterlockedPopEntrySList(this + 48);
  v5 = v4 - 1;
  v6 = -(__int64)v4;
  v7 = (unsigned __int64)v5 & -(__int64)(v6 != 0);
  if ( v7 )
  {
    Concurrency::details::ExternalContextBase::PrepareForUse(
      (Concurrency::details::ExternalContextBase *)((unsigned __int64)v5 & -(__int64)(v6 != 0)),
      a2);
  }
  else
  {
    v8 = (Concurrency::details::ExternalContextBase *)operator new(0x120u);
    if ( v8 )
      return (struct Concurrency::details::ExternalContextBase *)Concurrency::details::ExternalContextBase::ExternalContextBase(
                                                                   v8,
                                                                   (struct Concurrency::details::SchedulerBase *)this,
                                                                   a2);
  }
  return (struct Concurrency::details::ExternalContextBase *)v7;
}

```

## disassembly

```asm
0x1803173f4  push    rdi
0x1803173f6  sub     rsp, 30h
0x1803173fa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180317403  mov     [rsp+38h+arg_8], rbx
0x180317408  mov     [rsp+38h+arg_10], rsi
0x18031740d  mov     dil, dl
0x180317410  mov     rsi, rcx
0x180317413  add     rcx, 300h; ListHead
0x18031741a  call    cs:__imp_InterlockedPopEntrySList
0x180317420  lea     r8, [rax-10h]
0x180317424  neg     rax
0x180317427  sbb     rbx, rbx
0x18031742a  and     rbx, r8
0x18031742d  jnz     short loc_180317456
0x18031742f  mov     ecx, 120h; Size
0x180317434  call    ??2@YAPEAX_K@Z
0x180317439  mov     [rsp+38h+arg_0], rax
0x18031743e  test    rax, rax
0x180317441  jz      short loc_180317454
0x180317443  mov     r8b, dil; bool
0x180317446  mov     rdx, rsi; struct Concurrency::details::SchedulerBase *
0x180317449  mov     rcx, rax; this
0x18031744c  call    ??0ExternalContextBase@details@Concurrency@@QEAA@PEAVSchedulerBase@12@_N@Z
0x180317451  mov     rbx, rax
0x180317454  jmp     short loc_180317461
0x180317456  mov     dl, dil; bool
0x180317459  mov     rcx, rbx; this
0x18031745c  call    ?PrepareForUse@ExternalContextBase@details@Concurrency@@QEAAX_N@Z
0x180317461  mov     rax, rbx
0x180317464  mov     rbx, [rsp+38h+arg_8]
0x180317469  mov     rsi, [rsp+38h+arg_10]
0x18031746e  add     rsp, 30h
0x180317472  pop     rdi
0x180317473  retn
```

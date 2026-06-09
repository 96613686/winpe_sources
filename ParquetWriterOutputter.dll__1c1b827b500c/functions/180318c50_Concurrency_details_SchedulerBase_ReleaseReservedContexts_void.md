# Concurrency::details::SchedulerBase::ReleaseReservedContexts(void)

- ea: `0x180318c50`
- end: `0x180318ce2`
- name: `?ReleaseReservedContexts@SchedulerBase@details@Concurrency@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(Concurrency::details::SchedulerBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180316170`

## callees

- `0x180318c50`
- `0x180358070`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180318c71`
- `KERNEL32!InterlockedPopEntrySList` at `0x180318cb8`
- `KERNEL32!InterlockedPopEntrySList` at `0x180318c71`
- `KERNEL32!InterlockedPopEntrySList` at `0x180318cb8`
- `KERNEL32!InterlockedPushEntrySList` at `0x180318caf`
- `KERNEL32!InterlockedPushEntrySList` at `0x180318caf`

## pseudocode

```c
void __fastcall Concurrency::details::SchedulerBase::ReleaseReservedContexts(Concurrency::details::SchedulerBase *this)
{
  union _SLIST_HEADER *v1; // rsi
  PSLIST_ENTRY v3; // rax
  struct _SLIST_ENTRY *i; // rbx
  PSLIST_ENTRY v5; // rax

  v1 = (union _SLIST_HEADER *)((char *)this + 800);
  v3 = InterlockedPopEntrySList((PSLIST_HEADER)this + 50);
  for ( i = (struct _SLIST_ENTRY *)((unsigned __int64)&v3[-2] & -(__int64)(v3 != 0));
        i;
        i = (struct _SLIST_ENTRY *)((unsigned __int64)&v5[-2] & -(__int64)(v5 != 0)) )
  {
    (*(void (__fastcall **)(_QWORD, struct _SLIST_ENTRY *))(**((_QWORD **)this + 83) + 24LL))(*((_QWORD *)this + 83), i);
    _InterlockedDecrement((volatile signed __int32 *)this + 158);
    InterlockedPushEntrySList((PSLIST_HEADER)this + 47, i + 2);
    v5 = InterlockedPopEntrySList(v1);
  }
}

```

## disassembly

```asm
0x180318c50  mov     [rsp+arg_0], rbx
0x180318c55  mov     [rsp+arg_8], rbp
0x180318c5a  mov     [rsp+arg_10], rsi
0x180318c5f  push    rdi
0x180318c60  sub     rsp, 20h
0x180318c64  lea     rsi, [rcx+320h]
0x180318c6b  mov     rdi, rcx
0x180318c6e  mov     rcx, rsi; ListHead
0x180318c71  call    cs:__imp_InterlockedPopEntrySList
0x180318c77  lea     rdx, [rax-20h]
0x180318c7b  neg     rax
0x180318c7e  sbb     rbx, rbx
0x180318c81  and     rbx, rdx
0x180318c84  jz      short loc_180318CCD
0x180318c86  mov     rcx, [rdi+298h]
0x180318c8d  mov     rdx, rbx
0x180318c90  mov     rax, [rcx]
0x180318c93  mov     rax, [rax+18h]
0x180318c97  call    cs:__guard_dispatch_icall_fptr
0x180318c9d  lock dec dword ptr [rdi+278h]
0x180318ca4  lea     rdx, [rbx+20h]; ListEntry
0x180318ca8  lea     rcx, [rdi+2F0h]; ListHead
0x180318caf  call    cs:__imp_InterlockedPushEntrySList
0x180318cb5  mov     rcx, rsi; ListHead
0x180318cb8  call    cs:__imp_InterlockedPopEntrySList
0x180318cbe  lea     rcx, [rax-20h]
0x180318cc2  neg     rax
0x180318cc5  sbb     rbx, rbx
0x180318cc8  and     rbx, rcx
0x180318ccb  jnz     short loc_180318C86
0x180318ccd  mov     rbx, [rsp+28h+arg_0]
0x180318cd2  mov     rbp, [rsp+28h+arg_8]
0x180318cd7  mov     rsi, [rsp+28h+arg_10]
0x180318cdc  add     rsp, 20h
0x180318ce0  pop     rdi
0x180318ce1  retn
```

# Concurrency::details::SchedulerBase::GetInternalContext(bool)

- ea: `0x180317474`
- end: `0x1803175af`
- name: `?GetInternalContext@SchedulerBase@details@Concurrency@@QEAAPEAVInternalContextBase@23@_N@Z`
- size: `315`
- prototype: `struct Concurrency::details::InternalContextBase *__fastcall(Concurrency::details::SchedulerBase *__hidden this, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18031992c`
- `0x180322ca4`
- `0x180323d30`
- `0x180325304`

## callees

- `0x18030fcd4`
- `0x180315d48`
- `0x180317474`
- `0x180319ad8`
- `0x1803234c8`
- `0x180358070`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1803174b4`
- `KERNEL32!InterlockedPopEntrySList` at `0x180317516`
- `KERNEL32!InterlockedPopEntrySList` at `0x1803174b4`
- `KERNEL32!InterlockedPopEntrySList` at `0x180317516`

## pseudocode

```c
struct Concurrency::details::InternalContextBase *__fastcall Concurrency::details::SchedulerBase::GetInternalContext(
        Concurrency::details::SchedulerBase *this,
        char a2)
{
  char v2; // bl
  PSLIST_ENTRY v4; // rax
  struct Concurrency::details::InternalContextBase *result; // rax
  unsigned int v6; // esi
  PSLIST_ENTRY v7; // rax
  __int64 v8; // rbx
  struct _SLIST_ENTRY *v10; // [rsp+50h] [rbp+18h]

  v2 = a2;
  if ( a2 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(Concurrency::details::SchedulerBase *))(*(_QWORD *)this + 176LL))(this) )
    {
      v4 = InterlockedPopEntrySList((PSLIST_HEADER)this + 50);
      result = (struct Concurrency::details::InternalContextBase *)((unsigned __int64)&v4[-2] & -(__int64)(v4 != 0));
      if ( result )
        return result;
    }
    v6 = Concurrency::details::SchedulerBase::ThrottlingTime(this, 1u);
    if ( v6 )
    {
      if ( (unsigned int)Concurrency::details::platform::__GetTickCount64(this) - *((_DWORD *)this + 176) < v6 )
        return 0;
      v2 = 0;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 158);
  if ( !v2 )
    *((_QWORD *)this + 88) = Concurrency::details::platform::__GetTickCount64(this);
  v7 = InterlockedPopEntrySList((PSLIST_HEADER)this + 47);
  v8 = (unsigned __int64)&v7[-2] & -(__int64)(v7 != 0);
  v10 = (struct _SLIST_ENTRY *)v8;
  if ( !v8 )
  {
    v8 = (*(__int64 (__fastcall **)(Concurrency::details::SchedulerBase *))(*(_QWORD *)this + 128LL))(this);
    v10 = (struct _SLIST_ENTRY *)v8;
    Concurrency::details::SchedulerBase::AddContext(this, (struct Concurrency::details::InternalContextBase *)v8);
    _InterlockedIncrement((volatile signed __int32 *)this + 156);
  }
  Concurrency::details::InternalContextBase::SpinUntilBlocked((Concurrency::details::InternalContextBase *)v8);
  *(_QWORD *)(v8 + 256) = 0;
  try
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 83) + 16LL))(*((_QWORD *)this + 83), v8);
  }
  catch ( Concurrency::scheduler_worker_creation_error )
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 158);
    InterlockedPushEntrySList((PSLIST_HEADER)this + 47, v10 + 2);
    v8 = 0;
  }
  if ( v8 )
  {
    *(_DWORD *)(v8 + 52) = 0;
    *(_DWORD *)(v8 + 56) = 0;
  }
  return (struct Concurrency::details::InternalContextBase *)v8;
}

```

## disassembly

```asm
0x180317474  mov     rax, rsp
0x180317477  mov     [rax+8], rcx
0x18031747b  push    rdi
0x18031747c  sub     rsp, 30h
0x180317480  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180317488  mov     [rax+10h], rbx
0x18031748c  mov     [rax+20h], rsi
0x180317490  mov     bl, dl
0x180317492  mov     rdi, rcx
0x180317495  test    dl, dl
0x180317497  jz      short loc_1803174F8
0x180317499  mov     rax, [rcx]
0x18031749c  mov     rax, [rax+0B0h]
0x1803174a3  call    cs:__guard_dispatch_icall_fptr
0x1803174a9  test    al, al
0x1803174ab  jz      short loc_1803174CD
0x1803174ad  lea     rcx, [rdi+320h]; ListHead
0x1803174b4  call    cs:__imp_InterlockedPopEntrySList
0x1803174ba  lea     rcx, [rax-20h]
0x1803174be  neg     rax
0x1803174c1  sbb     rax, rax
0x1803174c4  and     rax, rcx
0x1803174c7  jnz     loc_18031759F
0x1803174cd  mov     edx, 1; unsigned int
0x1803174d2  mov     rcx, rdi; this
0x1803174d5  call    ?ThrottlingTime@SchedulerBase@details@Concurrency@@QEAAKK@Z; Concurrency::details::SchedulerBase::ThrottlingTime(ulong)
0x1803174da  mov     esi, eax
0x1803174dc  test    eax, eax
0x1803174de  jz      short loc_1803174F8
0x1803174e0  call    ?__GetTickCount64@platform@details@Concurrency@@YA_KXZ; Concurrency::details::platform::__GetTickCount64(void)
0x1803174e5  sub     eax, [rdi+2C0h]
0x1803174eb  cmp     eax, esi
0x1803174ed  jnb     short loc_1803174F6
0x1803174ef  xor     eax, eax
0x1803174f1  jmp     loc_18031759F
0x1803174f6  xor     bl, bl
0x1803174f8  lock inc dword ptr [rdi+278h]
0x1803174ff  test    bl, bl
0x180317501  jnz     short loc_18031750F
0x180317503  call    ?__GetTickCount64@platform@details@Concurrency@@YA_KXZ; Concurrency::details::platform::__GetTickCount64(void)
0x180317508  mov     [rdi+2C0h], rax
0x18031750f  lea     rcx, [rdi+2F0h]; ListHead
0x180317516  call    cs:__imp_InterlockedPopEntrySList
0x18031751c  lea     rcx, [rax-20h]
0x180317520  neg     rax
0x180317523  sbb     rbx, rbx
0x180317526  and     rbx, rcx
0x180317529  mov     [rsp+38h+arg_10], rbx
0x18031752e  jnz     short loc_18031755D
0x180317530  mov     rax, [rdi]
0x180317533  mov     rcx, rdi
0x180317536  mov     rax, [rax+80h]
0x18031753d  call    cs:__guard_dispatch_icall_fptr
0x180317543  mov     rbx, rax
0x180317546  mov     [rsp+38h+arg_10], rax
0x18031754b  mov     rdx, rax; struct Concurrency::details::InternalContextBase *
0x18031754e  mov     rcx, rdi; this
0x180317551  call    ?AddContext@SchedulerBase@details@Concurrency@@QEAAXPEAVInternalContextBase@23@@Z; Concurrency::details::SchedulerBase::AddContext(Concurrency::details::InternalContextBase *)
0x180317556  lock inc dword ptr [rdi+270h]
0x18031755d  mov     rcx, rbx; this
0x180317560  call    ?SpinUntilBlocked@InternalContextBase@details@Concurrency@@IEAAXXZ; Concurrency::details::InternalContextBase::SpinUntilBlocked(void)
0x180317565  mov     qword ptr [rbx+100h], 0
0x180317570  mov     rcx, [rdi+298h]
0x180317577  mov     rax, [rcx]
0x18031757a  mov     rdx, rbx
0x18031757d  mov     rax, [rax+10h]
0x180317581  call    cs:__guard_dispatch_icall_fptr
0x180317587  nop
0x180317588  jmp     short loc_18031758F
0x18031758a  mov     rbx, [rsp+38h+arg_10]
0x18031758f  test    rbx, rbx
0x180317592  jz      short loc_18031759C
0x180317594  and     dword ptr [rbx+34h], 0
0x180317598  and     dword ptr [rbx+38h], 0
0x18031759c  mov     rax, rbx
0x18031759f  mov     rbx, [rsp+38h+arg_8]
0x1803175a4  mov     rsi, [rsp+38h+arg_18]
0x1803175a9  add     rsp, 30h
0x1803175ad  pop     rdi
0x1803175ae  retn
```

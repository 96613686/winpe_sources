# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18004eb98`
- end: `0x18004ec98`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `256`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004eca0`

## callees

- `0x1800037c0`
- `0x18004eb98`
- `0x18004ed78`
- `0x18004fab8`
- `0x18004fac4`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004ec2f`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004ec2f`
- `msvcp_win!_Mtx_unlock` at `0x18004ec24`
- `msvcp_win!_Mtx_unlock` at `0x18004ec77`
- `msvcp_win!_Mtx_unlock` at `0x18004ec24`
- `msvcp_win!_Mtx_unlock` at `0x18004ec77`
- `msvcp_win!_Cnd_broadcast` at `0x18004ec81`
- `msvcp_win!_Cnd_broadcast` at `0x18004ec81`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_RegisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  Concurrency::details::platform *v4; // rcx
  char v5; // bp
  _QWORD *v6; // rax
  signed __int32 CurrentThreadId; // ebx
  signed __int32 v8; // eax

  _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)a2 + 23) = this;
  if ( (unsigned int)std::_Atomic_storage<long,4>::load((char *)this + 16) )
    goto LABEL_9;
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  if ( (unsigned int)std::_Atomic_storage<long,4>::load((char *)this + 16) )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    v6 = operator new(0x10u);
    *v6 = a2;
    v6[1] = 0;
    if ( *((_QWORD *)this + 13) )
      *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = v6;
    else
      *((_QWORD *)this + 13) = v6;
    *((_QWORD *)this + 14) = v6;
  }
  _Mtx_unlock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  if ( v5 )
  {
LABEL_9:
    CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(v4);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 16LL))(a2);
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v8 )
        CurrentThreadId = v8;
      if ( CurrentThreadId == 2 )
      {
        std::_Mutex_base::lock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
        *((_BYTE *)a2 + 176) = 1;
        _Mtx_unlock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
        _Cnd_broadcast((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24));
      }
    }
    Concurrency::details::_RefCounter::_Release(a2);
  }
}

```

## disassembly

```asm
0x18004eb98  push    rbx
0x18004eb9a  push    rbp
0x18004eb9b  push    rsi
0x18004eb9c  push    rdi
0x18004eb9d  sub     rsp, 28h
0x18004eba1  mov     rdi, rdx
0x18004eba4  mov     rbx, rcx
0x18004eba7  xor     eax, eax
0x18004eba9  xchg    eax, [rdx+10h]
0x18004ebac  lock inc dword ptr [rdx+8]
0x18004ebb0  mov     [rdx+0B8h], rcx
0x18004ebb7  add     rcx, 10h
0x18004ebbb  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18004ebc0  test    eax, eax
0x18004ebc2  jnz     short loc_18004EC2F
0x18004ebc4  lea     rsi, [rbx+18h]
0x18004ebc8  mov     [rsp+48h+arg_0], rsi
0x18004ebcd  mov     rcx, rsi; this
0x18004ebd0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004ebd5  nop
0x18004ebd6  lea     rcx, [rbx+10h]
0x18004ebda  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18004ebdf  test    eax, eax
0x18004ebe1  jz      short loc_18004EBE8
0x18004ebe3  mov     bpl, 1
0x18004ebe6  jmp     short loc_18004EC21
0x18004ebe8  xor     bpl, bpl
0x18004ebeb  mov     ecx, 10h; Size
0x18004ebf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ebf5  mov     rcx, rax
0x18004ebf8  mov     [rsp+48h+arg_0], rax
0x18004ebfd  mov     [rax], rdi
0x18004ec00  mov     qword ptr [rax+8], 0
0x18004ec08  cmp     qword ptr [rbx+68h], 0
0x18004ec0d  jnz     short loc_18004EC15
0x18004ec0f  mov     [rbx+68h], rax
0x18004ec13  jmp     short loc_18004EC1D
0x18004ec15  mov     rax, [rbx+70h]
0x18004ec19  mov     [rax+8], rcx
0x18004ec1d  mov     [rbx+70h], rcx
0x18004ec21  mov     rcx, rsi; _Mtx_t
0x18004ec24  call    cs:__imp__Mtx_unlock
0x18004ec2a  test    bpl, bpl
0x18004ec2d  jz      short loc_18004EC8F
0x18004ec2f  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18004ec35  mov     ebx, eax
0x18004ec37  xor     eax, eax
0x18004ec39  lock cmpxchg [rdi+10h], ebx
0x18004ec3e  jnz     short loc_18004EC87
0x18004ec40  mov     rcx, [rdi]
0x18004ec43  mov     rax, [rcx+10h]
0x18004ec47  mov     rcx, rdi
0x18004ec4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec4f  mov     ecx, 3
0x18004ec54  mov     eax, ebx
0x18004ec56  lock cmpxchg [rdi+10h], ecx
0x18004ec5b  cmovnz  ebx, eax
0x18004ec5e  cmp     ebx, 2
0x18004ec61  jnz     short loc_18004EC87
0x18004ec63  lea     rcx, [rdi+60h]; this
0x18004ec67  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004ec6c  mov     byte ptr [rdi+0B0h], 1
0x18004ec73  lea     rcx, [rdi+60h]; _Mtx_t
0x18004ec77  call    cs:__imp__Mtx_unlock
0x18004ec7d  lea     rcx, [rdi+18h]; _Cnd_t
0x18004ec81  call    cs:__imp__Cnd_broadcast
0x18004ec87  mov     rcx, rdi; this
0x18004ec8a  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18004ec8f  add     rsp, 28h
0x18004ec93  pop     rdi
0x18004ec94  pop     rsi
0x18004ec95  pop     rbp
0x18004ec96  pop     rbx
0x18004ec97  retn
```

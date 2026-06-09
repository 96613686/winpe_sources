# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18001d5c0`
- end: `0x18001d6c0`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `256`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d6c8`

## callees

- `0x18000288c`
- `0x18001d5c0`
- `0x18001d7a0`
- `0x18001e880`
- `0x18001e88c`
- `0x180025010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001d64c`
- `msvcp_win!_Mtx_unlock` at `0x18001d69f`
- `msvcp_win!_Mtx_unlock` at `0x18001d64c`
- `msvcp_win!_Mtx_unlock` at `0x18001d69f`
- `msvcp_win!_Cnd_broadcast` at `0x18001d6a9`
- `msvcp_win!_Cnd_broadcast` at `0x18001d6a9`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001d657`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001d657`

## pseudocode

```c
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
0x18001d5c0  push    rbx
0x18001d5c2  push    rbp
0x18001d5c3  push    rsi
0x18001d5c4  push    rdi
0x18001d5c5  sub     rsp, 28h
0x18001d5c9  mov     rdi, rdx
0x18001d5cc  mov     rbx, rcx
0x18001d5cf  xor     eax, eax
0x18001d5d1  xchg    eax, [rdx+10h]
0x18001d5d4  lock inc dword ptr [rdx+8]
0x18001d5d8  mov     [rdx+0B8h], rcx
0x18001d5df  add     rcx, 10h
0x18001d5e3  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18001d5e8  test    eax, eax
0x18001d5ea  jnz     short loc_18001D657
0x18001d5ec  lea     rsi, [rbx+18h]
0x18001d5f0  mov     [rsp+48h+arg_0], rsi
0x18001d5f5  mov     rcx, rsi; this
0x18001d5f8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d5fd  nop
0x18001d5fe  lea     rcx, [rbx+10h]
0x18001d602  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18001d607  test    eax, eax
0x18001d609  jz      short loc_18001D610
0x18001d60b  mov     bpl, 1
0x18001d60e  jmp     short loc_18001D649
0x18001d610  xor     bpl, bpl
0x18001d613  mov     ecx, 10h; Size
0x18001d618  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d61d  mov     rcx, rax
0x18001d620  mov     [rsp+48h+arg_0], rax
0x18001d625  mov     [rax], rdi
0x18001d628  mov     qword ptr [rax+8], 0
0x18001d630  cmp     qword ptr [rbx+68h], 0
0x18001d635  jnz     short loc_18001D63D
0x18001d637  mov     [rbx+68h], rax
0x18001d63b  jmp     short loc_18001D645
0x18001d63d  mov     rax, [rbx+70h]
0x18001d641  mov     [rax+8], rcx
0x18001d645  mov     [rbx+70h], rcx
0x18001d649  mov     rcx, rsi; _Mtx_t
0x18001d64c  call    cs:__imp__Mtx_unlock
0x18001d652  test    bpl, bpl
0x18001d655  jz      short loc_18001D6B7
0x18001d657  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18001d65d  mov     ebx, eax
0x18001d65f  xor     eax, eax
0x18001d661  lock cmpxchg [rdi+10h], ebx
0x18001d666  jnz     short loc_18001D6AF
0x18001d668  mov     rcx, [rdi]
0x18001d66b  mov     rax, [rcx+10h]
0x18001d66f  mov     rcx, rdi
0x18001d672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d677  mov     ecx, 3
0x18001d67c  mov     eax, ebx
0x18001d67e  lock cmpxchg [rdi+10h], ecx
0x18001d683  cmovnz  ebx, eax
0x18001d686  cmp     ebx, 2
0x18001d689  jnz     short loc_18001D6AF
0x18001d68b  lea     rcx, [rdi+60h]; this
0x18001d68f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d694  mov     byte ptr [rdi+0B0h], 1
0x18001d69b  lea     rcx, [rdi+60h]; _Mtx_t
0x18001d69f  call    cs:__imp__Mtx_unlock
0x18001d6a5  lea     rcx, [rdi+18h]; _Cnd_t
0x18001d6a9  call    cs:__imp__Cnd_broadcast
0x18001d6af  mov     rcx, rdi; this
0x18001d6b2  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18001d6b7  add     rsp, 28h
0x18001d6bb  pop     rdi
0x18001d6bc  pop     rsi
0x18001d6bd  pop     rbp
0x18001d6be  pop     rbx
0x18001d6bf  retn
```

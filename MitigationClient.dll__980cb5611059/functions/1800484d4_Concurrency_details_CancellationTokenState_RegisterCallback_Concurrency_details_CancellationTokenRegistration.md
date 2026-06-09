# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x1800484d4`
- end: `0x1800485d4`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `256`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800485dc`

## callees

- `0x18000a704`
- `0x1800484d4`
- `0x1800486b4`
- `0x180048e94`
- `0x180048ea0`
- `0x18005c010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180048560`
- `msvcp_win!_Mtx_unlock` at `0x1800485b3`
- `msvcp_win!_Mtx_unlock` at `0x180048560`
- `msvcp_win!_Mtx_unlock` at `0x1800485b3`
- `msvcp_win!_Cnd_broadcast` at `0x1800485bd`
- `msvcp_win!_Cnd_broadcast` at `0x1800485bd`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004856b`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004856b`

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
0x1800484d4  push    rbx
0x1800484d6  push    rbp
0x1800484d7  push    rsi
0x1800484d8  push    rdi
0x1800484d9  sub     rsp, 28h
0x1800484dd  mov     rdi, rdx
0x1800484e0  mov     rbx, rcx
0x1800484e3  xor     eax, eax
0x1800484e5  xchg    eax, [rdx+10h]
0x1800484e8  lock inc dword ptr [rdx+8]
0x1800484ec  mov     [rdx+0B8h], rcx
0x1800484f3  add     rcx, 10h
0x1800484f7  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x1800484fc  test    eax, eax
0x1800484fe  jnz     short loc_18004856B
0x180048500  lea     rsi, [rbx+18h]
0x180048504  mov     [rsp+48h+arg_0], rsi
0x180048509  mov     rcx, rsi; this
0x18004850c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180048511  nop
0x180048512  lea     rcx, [rbx+10h]
0x180048516  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18004851b  test    eax, eax
0x18004851d  jz      short loc_180048524
0x18004851f  mov     bpl, 1
0x180048522  jmp     short loc_18004855D
0x180048524  xor     bpl, bpl
0x180048527  mov     ecx, 10h; Size
0x18004852c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048531  mov     rcx, rax
0x180048534  mov     [rsp+48h+arg_0], rax
0x180048539  mov     [rax], rdi
0x18004853c  mov     qword ptr [rax+8], 0
0x180048544  cmp     qword ptr [rbx+68h], 0
0x180048549  jnz     short loc_180048551
0x18004854b  mov     [rbx+68h], rax
0x18004854f  jmp     short loc_180048559
0x180048551  mov     rax, [rbx+70h]
0x180048555  mov     [rax+8], rcx
0x180048559  mov     [rbx+70h], rcx
0x18004855d  mov     rcx, rsi; _Mtx_t
0x180048560  call    cs:__imp__Mtx_unlock
0x180048566  test    bpl, bpl
0x180048569  jz      short loc_1800485CB
0x18004856b  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180048571  mov     ebx, eax
0x180048573  xor     eax, eax
0x180048575  lock cmpxchg [rdi+10h], ebx
0x18004857a  jnz     short loc_1800485C3
0x18004857c  mov     rcx, [rdi]
0x18004857f  mov     rax, [rcx+10h]
0x180048583  mov     rcx, rdi
0x180048586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004858b  mov     ecx, 3
0x180048590  mov     eax, ebx
0x180048592  lock cmpxchg [rdi+10h], ecx
0x180048597  cmovnz  ebx, eax
0x18004859a  cmp     ebx, 2
0x18004859d  jnz     short loc_1800485C3
0x18004859f  lea     rcx, [rdi+60h]; this
0x1800485a3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800485a8  mov     byte ptr [rdi+0B0h], 1
0x1800485af  lea     rcx, [rdi+60h]; _Mtx_t
0x1800485b3  call    cs:__imp__Mtx_unlock
0x1800485b9  lea     rcx, [rdi+18h]; _Cnd_t
0x1800485bd  call    cs:__imp__Cnd_broadcast
0x1800485c3  mov     rcx, rdi; this
0x1800485c6  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1800485cb  add     rsp, 28h
0x1800485cf  pop     rdi
0x1800485d0  pop     rsi
0x1800485d1  pop     rbp
0x1800485d2  pop     rbx
0x1800485d3  retn
```

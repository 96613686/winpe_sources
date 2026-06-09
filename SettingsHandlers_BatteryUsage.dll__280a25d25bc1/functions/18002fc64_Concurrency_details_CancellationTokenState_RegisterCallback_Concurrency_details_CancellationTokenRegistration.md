# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18002fc64`
- end: `0x18002fd64`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `256`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002fd6c`

## callees

- `0x180004394`
- `0x18002fc64`
- `0x18002fe44`
- `0x180031468`
- `0x180031474`
- `0x18005a010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18002fcfb`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18002fcfb`
- `msvcp_win!_Cnd_broadcast` at `0x18002fd4d`
- `msvcp_win!_Cnd_broadcast` at `0x18002fd4d`
- `msvcp_win!_Mtx_unlock` at `0x18002fcf0`
- `msvcp_win!_Mtx_unlock` at `0x18002fd43`
- `msvcp_win!_Mtx_unlock` at `0x18002fcf0`
- `msvcp_win!_Mtx_unlock` at `0x18002fd43`

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
0x18002fc64  push    rbx
0x18002fc66  push    rbp
0x18002fc67  push    rsi
0x18002fc68  push    rdi
0x18002fc69  sub     rsp, 28h
0x18002fc6d  mov     rdi, rdx
0x18002fc70  mov     rbx, rcx
0x18002fc73  xor     eax, eax
0x18002fc75  xchg    eax, [rdx+10h]
0x18002fc78  lock inc dword ptr [rdx+8]
0x18002fc7c  mov     [rdx+0B8h], rcx
0x18002fc83  add     rcx, 10h
0x18002fc87  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18002fc8c  test    eax, eax
0x18002fc8e  jnz     short loc_18002FCFB
0x18002fc90  lea     rsi, [rbx+18h]
0x18002fc94  mov     [rsp+48h+arg_0], rsi
0x18002fc99  mov     rcx, rsi; this
0x18002fc9c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002fca1  nop
0x18002fca2  lea     rcx, [rbx+10h]
0x18002fca6  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18002fcab  test    eax, eax
0x18002fcad  jz      short loc_18002FCB4
0x18002fcaf  mov     bpl, 1
0x18002fcb2  jmp     short loc_18002FCED
0x18002fcb4  xor     bpl, bpl
0x18002fcb7  mov     ecx, 10h; Size
0x18002fcbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fcc1  mov     rcx, rax
0x18002fcc4  mov     [rsp+48h+arg_0], rax
0x18002fcc9  mov     [rax], rdi
0x18002fccc  mov     qword ptr [rax+8], 0
0x18002fcd4  cmp     qword ptr [rbx+68h], 0
0x18002fcd9  jnz     short loc_18002FCE1
0x18002fcdb  mov     [rbx+68h], rax
0x18002fcdf  jmp     short loc_18002FCE9
0x18002fce1  mov     rax, [rbx+70h]
0x18002fce5  mov     [rax+8], rcx
0x18002fce9  mov     [rbx+70h], rcx
0x18002fced  mov     rcx, rsi; _Mtx_t
0x18002fcf0  call    cs:__imp__Mtx_unlock
0x18002fcf6  test    bpl, bpl
0x18002fcf9  jz      short loc_18002FD5B
0x18002fcfb  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18002fd01  mov     ebx, eax
0x18002fd03  xor     eax, eax
0x18002fd05  lock cmpxchg [rdi+10h], ebx
0x18002fd0a  jnz     short loc_18002FD53
0x18002fd0c  mov     rcx, [rdi]
0x18002fd0f  mov     rax, [rcx+10h]
0x18002fd13  mov     rcx, rdi
0x18002fd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd1b  mov     ecx, 3
0x18002fd20  mov     eax, ebx
0x18002fd22  lock cmpxchg [rdi+10h], ecx
0x18002fd27  cmovnz  ebx, eax
0x18002fd2a  cmp     ebx, 2
0x18002fd2d  jnz     short loc_18002FD53
0x18002fd2f  lea     rcx, [rdi+60h]; this
0x18002fd33  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002fd38  mov     byte ptr [rdi+0B0h], 1
0x18002fd3f  lea     rcx, [rdi+60h]; _Mtx_t
0x18002fd43  call    cs:__imp__Mtx_unlock
0x18002fd49  lea     rcx, [rdi+18h]; _Cnd_t
0x18002fd4d  call    cs:__imp__Cnd_broadcast
0x18002fd53  mov     rcx, rdi; this
0x18002fd56  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18002fd5b  add     rsp, 28h
0x18002fd5f  pop     rdi
0x18002fd60  pop     rsi
0x18002fd61  pop     rbp
0x18002fd62  pop     rbx
0x18002fd63  retn
```

# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180019e38`
- end: `0x180019f38`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `256`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019f40`

## callees

- `0x18000459c`
- `0x180019e38`
- `0x18001a068`
- `0x18001b74c`
- `0x18001b764`
- `0x180046010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180019f21`
- `msvcp_win!_Cnd_broadcast` at `0x180019f21`
- `msvcp_win!_Mtx_unlock` at `0x180019ec4`
- `msvcp_win!_Mtx_unlock` at `0x180019f17`
- `msvcp_win!_Mtx_unlock` at `0x180019ec4`
- `msvcp_win!_Mtx_unlock` at `0x180019f17`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180019ecf`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180019ecf`

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
  if ( (unsigned int)std::_Atomic_storage<enum NA_RULE_STATE,4>::load((char *)this + 16) )
    goto LABEL_9;
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  if ( (unsigned int)std::_Atomic_storage<enum NA_RULE_STATE,4>::load((char *)this + 16) )
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
0x180019e38  push    rbx
0x180019e3a  push    rbp
0x180019e3b  push    rsi
0x180019e3c  push    rdi
0x180019e3d  sub     rsp, 28h
0x180019e41  mov     rdi, rdx
0x180019e44  mov     rbx, rcx
0x180019e47  xor     eax, eax
0x180019e49  xchg    eax, [rdx+10h]
0x180019e4c  lock inc dword ptr [rdx+8]
0x180019e50  mov     [rdx+0B8h], rcx
0x180019e57  add     rcx, 10h
0x180019e5b  call    ?load@?$_Atomic_storage@W4NA_RULE_STATE@@$03@std@@QEBA?AW4NA_RULE_STATE@@W4memory_order@2@@Z; std::_Atomic_storage<NA_RULE_STATE,4>::load(std::memory_order)
0x180019e60  test    eax, eax
0x180019e62  jnz     short loc_180019ECF
0x180019e64  lea     rsi, [rbx+18h]
0x180019e68  mov     [rsp+48h+arg_0], rsi
0x180019e6d  mov     rcx, rsi; this
0x180019e70  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180019e75  nop
0x180019e76  lea     rcx, [rbx+10h]
0x180019e7a  call    ?load@?$_Atomic_storage@W4NA_RULE_STATE@@$03@std@@QEBA?AW4NA_RULE_STATE@@W4memory_order@2@@Z; std::_Atomic_storage<NA_RULE_STATE,4>::load(std::memory_order)
0x180019e7f  test    eax, eax
0x180019e81  jz      short loc_180019E88
0x180019e83  mov     bpl, 1
0x180019e86  jmp     short loc_180019EC1
0x180019e88  xor     bpl, bpl
0x180019e8b  mov     ecx, 10h; Size
0x180019e90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019e95  mov     rcx, rax
0x180019e98  mov     [rsp+48h+arg_0], rax
0x180019e9d  mov     [rax], rdi
0x180019ea0  mov     qword ptr [rax+8], 0
0x180019ea8  cmp     qword ptr [rbx+68h], 0
0x180019ead  jnz     short loc_180019EB5
0x180019eaf  mov     [rbx+68h], rax
0x180019eb3  jmp     short loc_180019EBD
0x180019eb5  mov     rax, [rbx+70h]
0x180019eb9  mov     [rax+8], rcx
0x180019ebd  mov     [rbx+70h], rcx
0x180019ec1  mov     rcx, rsi; _Mtx_t
0x180019ec4  call    cs:__imp__Mtx_unlock
0x180019eca  test    bpl, bpl
0x180019ecd  jz      short loc_180019F2F
0x180019ecf  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180019ed5  mov     ebx, eax
0x180019ed7  xor     eax, eax
0x180019ed9  lock cmpxchg [rdi+10h], ebx
0x180019ede  jnz     short loc_180019F27
0x180019ee0  mov     rcx, [rdi]
0x180019ee3  mov     rax, [rcx+10h]
0x180019ee7  mov     rcx, rdi
0x180019eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eef  mov     ecx, 3
0x180019ef4  mov     eax, ebx
0x180019ef6  lock cmpxchg [rdi+10h], ecx
0x180019efb  cmovnz  ebx, eax
0x180019efe  cmp     ebx, 2
0x180019f01  jnz     short loc_180019F27
0x180019f03  lea     rcx, [rdi+60h]; this
0x180019f07  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180019f0c  mov     byte ptr [rdi+0B0h], 1
0x180019f13  lea     rcx, [rdi+60h]; _Mtx_t
0x180019f17  call    cs:__imp__Mtx_unlock
0x180019f1d  lea     rcx, [rdi+18h]; _Cnd_t
0x180019f21  call    cs:__imp__Cnd_broadcast
0x180019f27  mov     rcx, rdi; this
0x180019f2a  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180019f2f  add     rsp, 28h
0x180019f33  pop     rdi
0x180019f34  pop     rsi
0x180019f35  pop     rbp
0x180019f36  pop     rbx
0x180019f37  retn
```

# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180023bcc`
- end: `0x180023cd5`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180023cdc`

## callees

- `0x180003b84`
- `0x180023bcc`
- `0x180023dbc`
- `0x180024828`
- `0x180024834`
- `0x180027010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180023c6c`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180023c6c`
- `msvcp_win!_Mtx_unlock` at `0x180023c61`
- `msvcp_win!_Mtx_unlock` at `0x180023cb4`
- `msvcp_win!_Mtx_unlock` at `0x180023c61`
- `msvcp_win!_Mtx_unlock` at `0x180023cb4`
- `msvcp_win!_Cnd_broadcast` at `0x180023cbe`
- `msvcp_win!_Cnd_broadcast` at `0x180023cbe`

## pseudocode

```c
void __fastcall Concurrency::details::_CancellationTokenState::_RegisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  Concurrency::details::platform *v4; // rcx
  char v5; // bp
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  signed __int32 CurrentThreadId; // ebx
  signed __int32 v9; // eax

  _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)a2 + 23) = this;
  if ( (unsigned int)std::_Atomic_storage<long,4>::load((char *)this + 16) )
    goto LABEL_12;
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  if ( (unsigned int)std::_Atomic_storage<long,4>::load((char *)this + 16) )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    v6 = operator new(0x10u);
    v7 = v6;
    if ( v6 )
    {
      *v6 = a2;
      v6[1] = 0;
    }
    else
    {
      v7 = 0;
    }
    if ( *((_QWORD *)this + 13) )
      *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = v7;
    else
      *((_QWORD *)this + 13) = v7;
    *((_QWORD *)this + 14) = v7;
  }
  _Mtx_unlock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  if ( v5 )
  {
LABEL_12:
    CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(v4);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 16LL))(a2);
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v9 )
        CurrentThreadId = v9;
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
0x180023bcc  push    rbx
0x180023bce  push    rbp
0x180023bcf  push    rsi
0x180023bd0  push    rdi
0x180023bd1  sub     rsp, 28h
0x180023bd5  mov     rdi, rdx
0x180023bd8  mov     rbx, rcx
0x180023bdb  xor     eax, eax
0x180023bdd  xchg    eax, [rdx+10h]
0x180023be0  lock inc dword ptr [rdx+8]
0x180023be4  mov     [rdx+0B8h], rcx
0x180023beb  add     rcx, 10h
0x180023bef  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x180023bf4  test    eax, eax
0x180023bf6  jnz     short loc_180023C6C
0x180023bf8  lea     rsi, [rbx+18h]
0x180023bfc  mov     [rsp+48h+arg_0], rsi
0x180023c01  mov     rcx, rsi; this
0x180023c04  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180023c09  nop
0x180023c0a  lea     rcx, [rbx+10h]
0x180023c0e  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x180023c13  test    eax, eax
0x180023c15  jz      short loc_180023C1C
0x180023c17  mov     bpl, 1
0x180023c1a  jmp     short loc_180023C5E
0x180023c1c  xor     bpl, bpl
0x180023c1f  mov     ecx, 10h; Size
0x180023c24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023c29  mov     rcx, rax
0x180023c2c  mov     [rsp+48h+arg_0], rax
0x180023c31  test    rax, rax
0x180023c34  jz      short loc_180023C43
0x180023c36  mov     [rax], rdi
0x180023c39  mov     qword ptr [rax+8], 0
0x180023c41  jmp     short loc_180023C45
0x180023c43  xor     ecx, ecx
0x180023c45  cmp     qword ptr [rbx+68h], 0
0x180023c4a  jnz     short loc_180023C52
0x180023c4c  mov     [rbx+68h], rcx
0x180023c50  jmp     short loc_180023C5A
0x180023c52  mov     rax, [rbx+70h]
0x180023c56  mov     [rax+8], rcx
0x180023c5a  mov     [rbx+70h], rcx
0x180023c5e  mov     rcx, rsi; _Mtx_t
0x180023c61  call    cs:__imp__Mtx_unlock
0x180023c67  test    bpl, bpl
0x180023c6a  jz      short loc_180023CCC
0x180023c6c  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180023c72  mov     ebx, eax
0x180023c74  xor     eax, eax
0x180023c76  lock cmpxchg [rdi+10h], ebx
0x180023c7b  jnz     short loc_180023CC4
0x180023c7d  mov     rcx, [rdi]
0x180023c80  mov     rax, [rcx+10h]
0x180023c84  mov     rcx, rdi
0x180023c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c8c  mov     ecx, 3
0x180023c91  mov     eax, ebx
0x180023c93  lock cmpxchg [rdi+10h], ecx
0x180023c98  cmovnz  ebx, eax
0x180023c9b  cmp     ebx, 2
0x180023c9e  jnz     short loc_180023CC4
0x180023ca0  lea     rcx, [rdi+60h]; this
0x180023ca4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180023ca9  mov     byte ptr [rdi+0B0h], 1
0x180023cb0  lea     rcx, [rdi+60h]; _Mtx_t
0x180023cb4  call    cs:__imp__Mtx_unlock
0x180023cba  lea     rcx, [rdi+18h]; _Cnd_t
0x180023cbe  call    cs:__imp__Cnd_broadcast
0x180023cc4  mov     rcx, rdi; this
0x180023cc7  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180023ccc  add     rsp, 28h
0x180023cd0  pop     rdi
0x180023cd1  pop     rsi
0x180023cd2  pop     rbp
0x180023cd3  pop     rbx
0x180023cd4  retn
```

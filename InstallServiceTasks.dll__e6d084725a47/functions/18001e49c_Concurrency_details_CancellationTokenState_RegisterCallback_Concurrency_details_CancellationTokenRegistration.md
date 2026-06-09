# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18001e49c`
- end: `0x18001e59c`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `256`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e5a4`

## callees

- `0x180003948`
- `0x18001e49c`
- `0x18001e6cc`
- `0x18001f144`
- `0x18001f150`
- `0x180046010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001e533`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001e533`
- `msvcp_win!_Mtx_unlock` at `0x18001e528`
- `msvcp_win!_Mtx_unlock` at `0x18001e57b`
- `msvcp_win!_Mtx_unlock` at `0x18001e528`
- `msvcp_win!_Mtx_unlock` at `0x18001e57b`
- `msvcp_win!_Cnd_broadcast` at `0x18001e585`
- `msvcp_win!_Cnd_broadcast` at `0x18001e585`

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
0x18001e49c  push    rbx
0x18001e49e  push    rbp
0x18001e49f  push    rsi
0x18001e4a0  push    rdi
0x18001e4a1  sub     rsp, 28h
0x18001e4a5  mov     rdi, rdx
0x18001e4a8  mov     rbx, rcx
0x18001e4ab  xor     eax, eax
0x18001e4ad  xchg    eax, [rdx+10h]
0x18001e4b0  lock inc dword ptr [rdx+8]
0x18001e4b4  mov     [rdx+0B8h], rcx
0x18001e4bb  add     rcx, 10h
0x18001e4bf  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18001e4c4  test    eax, eax
0x18001e4c6  jnz     short loc_18001E533
0x18001e4c8  lea     rsi, [rbx+18h]
0x18001e4cc  mov     [rsp+48h+arg_0], rsi
0x18001e4d1  mov     rcx, rsi; this
0x18001e4d4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001e4d9  nop
0x18001e4da  lea     rcx, [rbx+10h]
0x18001e4de  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18001e4e3  test    eax, eax
0x18001e4e5  jz      short loc_18001E4EC
0x18001e4e7  mov     bpl, 1
0x18001e4ea  jmp     short loc_18001E525
0x18001e4ec  xor     bpl, bpl
0x18001e4ef  mov     ecx, 10h; Size
0x18001e4f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e4f9  mov     rcx, rax
0x18001e4fc  mov     [rsp+48h+arg_0], rax
0x18001e501  mov     [rax], rdi
0x18001e504  mov     qword ptr [rax+8], 0
0x18001e50c  cmp     qword ptr [rbx+68h], 0
0x18001e511  jnz     short loc_18001E519
0x18001e513  mov     [rbx+68h], rax
0x18001e517  jmp     short loc_18001E521
0x18001e519  mov     rax, [rbx+70h]
0x18001e51d  mov     [rax+8], rcx
0x18001e521  mov     [rbx+70h], rcx
0x18001e525  mov     rcx, rsi; _Mtx_t
0x18001e528  call    cs:__imp__Mtx_unlock
0x18001e52e  test    bpl, bpl
0x18001e531  jz      short loc_18001E593
0x18001e533  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18001e539  mov     ebx, eax
0x18001e53b  xor     eax, eax
0x18001e53d  lock cmpxchg [rdi+10h], ebx
0x18001e542  jnz     short loc_18001E58B
0x18001e544  mov     rcx, [rdi]
0x18001e547  mov     rax, [rcx+10h]
0x18001e54b  mov     rcx, rdi
0x18001e54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e553  mov     ecx, 3
0x18001e558  mov     eax, ebx
0x18001e55a  lock cmpxchg [rdi+10h], ecx
0x18001e55f  cmovnz  ebx, eax
0x18001e562  cmp     ebx, 2
0x18001e565  jnz     short loc_18001E58B
0x18001e567  lea     rcx, [rdi+60h]; this
0x18001e56b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001e570  mov     byte ptr [rdi+0B0h], 1
0x18001e577  lea     rcx, [rdi+60h]; _Mtx_t
0x18001e57b  call    cs:__imp__Mtx_unlock
0x18001e581  lea     rcx, [rdi+18h]; _Cnd_t
0x18001e585  call    cs:__imp__Cnd_broadcast
0x18001e58b  mov     rcx, rdi; this
0x18001e58e  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18001e593  add     rsp, 28h
0x18001e597  pop     rdi
0x18001e598  pop     rsi
0x18001e599  pop     rbp
0x18001e59a  pop     rbx
0x18001e59b  retn
```

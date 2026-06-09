# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x14001f264`
- end: `0x14001f37d`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `281`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001f384`

## callees

- `0x140004c1c`
- `0x140019d2c`
- `0x14001f264`
- `0x14001f4ac`
- `0x1400200a0`
- `0x1401b9010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001f301`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001f301`
- `msvcp_win!_Cnd_broadcast` at `0x14001f35f`
- `msvcp_win!_Cnd_broadcast` at `0x14001f35f`
- `msvcp_win!_Mtx_unlock` at `0x14001f2f0`
- `msvcp_win!_Mtx_unlock` at `0x14001f34f`
- `msvcp_win!_Mtx_unlock` at `0x14001f2f0`
- `msvcp_win!_Mtx_unlock` at `0x14001f34f`

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
0x14001f264  push    rbx
0x14001f266  push    rbp
0x14001f267  push    rsi
0x14001f268  push    rdi
0x14001f269  sub     rsp, 28h
0x14001f26d  mov     rdi, rdx
0x14001f270  mov     rbx, rcx
0x14001f273  xor     eax, eax
0x14001f275  xchg    eax, [rdx+10h]
0x14001f278  lock inc dword ptr [rdx+8]
0x14001f27c  mov     [rdx+0B8h], rcx
0x14001f283  add     rcx, 10h
0x14001f287  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x14001f28c  test    eax, eax
0x14001f28e  jnz     short loc_14001F301
0x14001f290  lea     rsi, [rbx+18h]
0x14001f294  mov     [rsp+48h+arg_0], rsi
0x14001f299  mov     rcx, rsi; this
0x14001f29c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14001f2a1  nop
0x14001f2a2  lea     rcx, [rbx+10h]
0x14001f2a6  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x14001f2ab  test    eax, eax
0x14001f2ad  jz      short loc_14001F2B4
0x14001f2af  mov     bpl, 1
0x14001f2b2  jmp     short loc_14001F2ED
0x14001f2b4  xor     bpl, bpl
0x14001f2b7  mov     ecx, 10h; Size
0x14001f2bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001f2c1  mov     rcx, rax
0x14001f2c4  mov     [rsp+48h+arg_0], rax
0x14001f2c9  mov     [rax], rdi
0x14001f2cc  mov     qword ptr [rax+8], 0
0x14001f2d4  cmp     qword ptr [rbx+68h], 0
0x14001f2d9  jnz     short loc_14001F2E1
0x14001f2db  mov     [rbx+68h], rax
0x14001f2df  jmp     short loc_14001F2E9
0x14001f2e1  mov     rax, [rbx+70h]
0x14001f2e5  mov     [rax+8], rcx
0x14001f2e9  mov     [rbx+70h], rcx
0x14001f2ed  mov     rcx, rsi; _Mtx_t
0x14001f2f0  call    cs:__imp__Mtx_unlock
0x14001f2f7  nop     dword ptr [rax+rax+00h]
0x14001f2fc  test    bpl, bpl
0x14001f2ff  jz      short loc_14001F373
0x14001f301  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x14001f308  nop     dword ptr [rax+rax+00h]
0x14001f30d  mov     ebx, eax
0x14001f30f  xor     eax, eax
0x14001f311  lock cmpxchg [rdi+10h], ebx
0x14001f316  jnz     short loc_14001F36B
0x14001f318  mov     rcx, [rdi]
0x14001f31b  mov     rax, [rcx+10h]
0x14001f31f  mov     rcx, rdi
0x14001f322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f327  mov     ecx, 3
0x14001f32c  mov     eax, ebx
0x14001f32e  lock cmpxchg [rdi+10h], ecx
0x14001f333  cmovnz  ebx, eax
0x14001f336  cmp     ebx, 2
0x14001f339  jnz     short loc_14001F36B
0x14001f33b  lea     rcx, [rdi+60h]; this
0x14001f33f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14001f344  mov     byte ptr [rdi+0B0h], 1
0x14001f34b  lea     rcx, [rdi+60h]; _Mtx_t
0x14001f34f  call    cs:__imp__Mtx_unlock
0x14001f356  nop     dword ptr [rax+rax+00h]
0x14001f35b  lea     rcx, [rdi+18h]; _Cnd_t
0x14001f35f  call    cs:__imp__Cnd_broadcast
0x14001f366  nop     dword ptr [rax+rax+00h]
0x14001f36b  mov     rcx, rdi; this
0x14001f36e  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x14001f373  add     rsp, 28h
0x14001f377  pop     rdi
0x14001f378  pop     rsi
0x14001f379  pop     rbp
0x14001f37a  pop     rbx
0x14001f37b  retn
```

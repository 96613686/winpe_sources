# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180033d50`
- end: `0x180033e50`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `256`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180033e58`

## callees

- `0x18001df10`
- `0x1800272a0`
- `0x180033d50`
- `0x180033f30`
- `0x180034424`
- `0x180052010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180033e39`
- `msvcp_win!_Cnd_broadcast` at `0x180033e39`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180033de7`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180033de7`
- `msvcp_win!_Mtx_unlock` at `0x180033ddc`
- `msvcp_win!_Mtx_unlock` at `0x180033e2f`
- `msvcp_win!_Mtx_unlock` at `0x180033ddc`
- `msvcp_win!_Mtx_unlock` at `0x180033e2f`

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
0x180033d50  push    rbx
0x180033d52  push    rbp
0x180033d53  push    rsi
0x180033d54  push    rdi
0x180033d55  sub     rsp, 28h
0x180033d59  mov     rdi, rdx
0x180033d5c  mov     rbx, rcx
0x180033d5f  xor     eax, eax
0x180033d61  xchg    eax, [rdx+10h]
0x180033d64  lock inc dword ptr [rdx+8]
0x180033d68  mov     [rdx+0B8h], rcx
0x180033d6f  add     rcx, 10h
0x180033d73  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x180033d78  test    eax, eax
0x180033d7a  jnz     short loc_180033DE7
0x180033d7c  lea     rsi, [rbx+18h]
0x180033d80  mov     [rsp+48h+arg_0], rsi
0x180033d85  mov     rcx, rsi; this
0x180033d88  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180033d8d  nop
0x180033d8e  lea     rcx, [rbx+10h]
0x180033d92  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x180033d97  test    eax, eax
0x180033d99  jz      short loc_180033DA0
0x180033d9b  mov     bpl, 1
0x180033d9e  jmp     short loc_180033DD9
0x180033da0  xor     bpl, bpl
0x180033da3  mov     ecx, 10h; Size
0x180033da8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033dad  mov     rcx, rax
0x180033db0  mov     [rsp+48h+arg_0], rax
0x180033db5  mov     [rax], rdi
0x180033db8  mov     qword ptr [rax+8], 0
0x180033dc0  cmp     qword ptr [rbx+68h], 0
0x180033dc5  jnz     short loc_180033DCD
0x180033dc7  mov     [rbx+68h], rax
0x180033dcb  jmp     short loc_180033DD5
0x180033dcd  mov     rax, [rbx+70h]
0x180033dd1  mov     [rax+8], rcx
0x180033dd5  mov     [rbx+70h], rcx
0x180033dd9  mov     rcx, rsi; _Mtx_t
0x180033ddc  call    cs:__imp__Mtx_unlock
0x180033de2  test    bpl, bpl
0x180033de5  jz      short loc_180033E47
0x180033de7  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180033ded  mov     ebx, eax
0x180033def  xor     eax, eax
0x180033df1  lock cmpxchg [rdi+10h], ebx
0x180033df6  jnz     short loc_180033E3F
0x180033df8  mov     rcx, [rdi]
0x180033dfb  mov     rax, [rcx+10h]
0x180033dff  mov     rcx, rdi
0x180033e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e07  mov     ecx, 3
0x180033e0c  mov     eax, ebx
0x180033e0e  lock cmpxchg [rdi+10h], ecx
0x180033e13  cmovnz  ebx, eax
0x180033e16  cmp     ebx, 2
0x180033e19  jnz     short loc_180033E3F
0x180033e1b  lea     rcx, [rdi+60h]; this
0x180033e1f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180033e24  mov     byte ptr [rdi+0B0h], 1
0x180033e2b  lea     rcx, [rdi+60h]; _Mtx_t
0x180033e2f  call    cs:__imp__Mtx_unlock
0x180033e35  lea     rcx, [rdi+18h]; _Cnd_t
0x180033e39  call    cs:__imp__Cnd_broadcast
0x180033e3f  mov     rcx, rdi; this
0x180033e42  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180033e47  add     rsp, 28h
0x180033e4b  pop     rdi
0x180033e4c  pop     rsi
0x180033e4d  pop     rbp
0x180033e4e  pop     rbx
0x180033e4f  retn
```

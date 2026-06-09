# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x1801ad728`
- end: `0x1801ad838`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `272`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801ad838`

## callees

- `0x1800573f0`
- `0x1800786fc`
- `0x1800795a0`
- `0x1801762d0`
- `0x1801ad728`

## import_xrefs

- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1801ad7c2`
- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1801ad7c2`
- `MSVCP140!_Cnd_broadcast` at `0x1801ad815`
- `MSVCP140!_Cnd_broadcast` at `0x1801ad815`
- `MSVCP140!_Mtx_unlock` at `0x1801ad7b7`
- `MSVCP140!_Mtx_unlock` at `0x1801ad80b`
- `MSVCP140!_Mtx_unlock` at `0x1801ad7b7`
- `MSVCP140!_Mtx_unlock` at `0x1801ad80b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_RegisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char v4; // bp
  struct _Mtx_internal_imp_t *v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned int v7; // r8d
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  signed __int32 CurrentThreadId; // ebx
  signed __int32 v11; // eax

  _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)a2 + 23) = this;
  v4 = 1;
  if ( *((_DWORD *)this + 4) )
    goto LABEL_11;
  v5 = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  if ( !*((_DWORD *)this + 4) )
  {
    v4 = 0;
    v8 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v6, v7);
    v9 = v8;
    if ( v8 )
    {
      *v8 = a2;
      v8[1] = 0;
    }
    else
    {
      v9 = 0;
    }
    if ( *((_QWORD *)this + 13) )
      *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = v9;
    else
      *((_QWORD *)this + 13) = v9;
    *((_QWORD *)this + 14) = v9;
  }
  _Mtx_unlock(v5);
  if ( v4 )
  {
LABEL_11:
    CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(this);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 16LL))(a2);
      v11 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v11 )
        CurrentThreadId = v11;
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
0x1801ad728  mov     [rsp+arg_8], rbx
0x1801ad72d  mov     [rsp+arg_10], rbp
0x1801ad732  mov     [rsp+arg_18], rsi
0x1801ad737  push    rdi
0x1801ad738  sub     rsp, 20h
0x1801ad73c  mov     rdi, rdx
0x1801ad73f  mov     rsi, rcx
0x1801ad742  xor     eax, eax
0x1801ad744  xchg    eax, [rdx+10h]
0x1801ad747  lock inc dword ptr [rdx+8]
0x1801ad74b  mov     [rdx+0B8h], rcx
0x1801ad752  mov     bpl, 1
0x1801ad755  mov     eax, [rcx+10h]
0x1801ad758  test    eax, eax
0x1801ad75a  jnz     short loc_1801AD7C2
0x1801ad75c  lea     rbx, [rcx+18h]
0x1801ad760  mov     [rsp+28h+arg_0], rbx
0x1801ad765  mov     rcx, rbx; this
0x1801ad768  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801ad76d  mov     eax, [rsi+10h]
0x1801ad770  test    eax, eax
0x1801ad772  jnz     short loc_1801AD7B4
0x1801ad774  xor     bpl, bpl
0x1801ad777  lea     ecx, [rax+10h]; this
0x1801ad77a  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801ad77f  mov     rcx, rax
0x1801ad782  mov     [rsp+28h+arg_0], rax
0x1801ad787  test    rax, rax
0x1801ad78a  jz      short loc_1801AD799
0x1801ad78c  mov     [rax], rdi
0x1801ad78f  mov     qword ptr [rax+8], 0
0x1801ad797  jmp     short loc_1801AD79B
0x1801ad799  xor     ecx, ecx
0x1801ad79b  cmp     qword ptr [rsi+68h], 0
0x1801ad7a0  jnz     short loc_1801AD7A8
0x1801ad7a2  mov     [rsi+68h], rcx
0x1801ad7a6  jmp     short loc_1801AD7B0
0x1801ad7a8  mov     rax, [rsi+70h]
0x1801ad7ac  mov     [rax+8], rcx
0x1801ad7b0  mov     [rsi+70h], rcx
0x1801ad7b4  mov     rcx, rbx; _Mtx_t
0x1801ad7b7  call    cs:__imp__Mtx_unlock
0x1801ad7bd  test    bpl, bpl
0x1801ad7c0  jz      short loc_1801AD823
0x1801ad7c2  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1801ad7c8  mov     ebx, eax
0x1801ad7ca  xor     eax, eax
0x1801ad7cc  lock cmpxchg [rdi+10h], ebx
0x1801ad7d1  jnz     short loc_1801AD81B
0x1801ad7d3  mov     rcx, [rdi]
0x1801ad7d6  mov     rax, [rcx+10h]
0x1801ad7da  mov     rcx, rdi
0x1801ad7dd  call    cs:__guard_dispatch_icall_fptr
0x1801ad7e3  mov     ecx, 3
0x1801ad7e8  mov     eax, ebx
0x1801ad7ea  lock cmpxchg [rdi+10h], ecx
0x1801ad7ef  cmovnz  ebx, eax
0x1801ad7f2  cmp     ebx, 2
0x1801ad7f5  jnz     short loc_1801AD81B
0x1801ad7f7  lea     rcx, [rdi+60h]; this
0x1801ad7fb  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801ad800  mov     byte ptr [rdi+0B0h], 1
0x1801ad807  lea     rcx, [rdi+60h]; _Mtx_t
0x1801ad80b  call    cs:__imp__Mtx_unlock
0x1801ad811  lea     rcx, [rdi+18h]; _Cnd_t
0x1801ad815  call    cs:__imp__Cnd_broadcast
0x1801ad81b  mov     rcx, rdi; this
0x1801ad81e  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1801ad823  mov     rbx, [rsp+28h+arg_8]
0x1801ad828  mov     rbp, [rsp+28h+arg_10]
0x1801ad82d  mov     rsi, [rsp+28h+arg_18]
0x1801ad832  add     rsp, 20h
0x1801ad836  pop     rdi
0x1801ad837  retn
```

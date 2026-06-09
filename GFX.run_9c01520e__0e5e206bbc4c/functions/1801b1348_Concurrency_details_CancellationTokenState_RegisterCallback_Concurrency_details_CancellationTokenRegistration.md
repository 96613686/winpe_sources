# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x1801b1348`
- end: `0x1801b1458`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `272`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801b1458`

## callees

- `0x180057e70`
- `0x180076df0`
- `0x180092a58`
- `0x18017a298`
- `0x1801b1348`

## import_xrefs

- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1801b13e2`
- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1801b13e2`
- `MSVCP140!_Cnd_broadcast` at `0x1801b1435`
- `MSVCP140!_Cnd_broadcast` at `0x1801b1435`
- `MSVCP140!_Mtx_unlock` at `0x1801b13d7`
- `MSVCP140!_Mtx_unlock` at `0x1801b142b`
- `MSVCP140!_Mtx_unlock` at `0x1801b13d7`
- `MSVCP140!_Mtx_unlock` at `0x1801b142b`

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
0x1801b1348  mov     [rsp+arg_8], rbx
0x1801b134d  mov     [rsp+arg_10], rbp
0x1801b1352  mov     [rsp+arg_18], rsi
0x1801b1357  push    rdi
0x1801b1358  sub     rsp, 20h
0x1801b135c  mov     rdi, rdx
0x1801b135f  mov     rsi, rcx
0x1801b1362  xor     eax, eax
0x1801b1364  xchg    eax, [rdx+10h]
0x1801b1367  lock inc dword ptr [rdx+8]
0x1801b136b  mov     [rdx+0B8h], rcx
0x1801b1372  mov     bpl, 1
0x1801b1375  mov     eax, [rcx+10h]
0x1801b1378  test    eax, eax
0x1801b137a  jnz     short loc_1801B13E2
0x1801b137c  lea     rbx, [rcx+18h]
0x1801b1380  mov     [rsp+28h+arg_0], rbx
0x1801b1385  mov     rcx, rbx; this
0x1801b1388  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801b138d  mov     eax, [rsi+10h]
0x1801b1390  test    eax, eax
0x1801b1392  jnz     short loc_1801B13D4
0x1801b1394  xor     bpl, bpl
0x1801b1397  lea     ecx, [rax+10h]; this
0x1801b139a  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801b139f  mov     rcx, rax
0x1801b13a2  mov     [rsp+28h+arg_0], rax
0x1801b13a7  test    rax, rax
0x1801b13aa  jz      short loc_1801B13B9
0x1801b13ac  mov     [rax], rdi
0x1801b13af  mov     qword ptr [rax+8], 0
0x1801b13b7  jmp     short loc_1801B13BB
0x1801b13b9  xor     ecx, ecx
0x1801b13bb  cmp     qword ptr [rsi+68h], 0
0x1801b13c0  jnz     short loc_1801B13C8
0x1801b13c2  mov     [rsi+68h], rcx
0x1801b13c6  jmp     short loc_1801B13D0
0x1801b13c8  mov     rax, [rsi+70h]
0x1801b13cc  mov     [rax+8], rcx
0x1801b13d0  mov     [rsi+70h], rcx
0x1801b13d4  mov     rcx, rbx; _Mtx_t
0x1801b13d7  call    cs:__imp__Mtx_unlock
0x1801b13dd  test    bpl, bpl
0x1801b13e0  jz      short loc_1801B1443
0x1801b13e2  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1801b13e8  mov     ebx, eax
0x1801b13ea  xor     eax, eax
0x1801b13ec  lock cmpxchg [rdi+10h], ebx
0x1801b13f1  jnz     short loc_1801B143B
0x1801b13f3  mov     rcx, [rdi]
0x1801b13f6  mov     rax, [rcx+10h]
0x1801b13fa  mov     rcx, rdi
0x1801b13fd  call    cs:__guard_dispatch_icall_fptr
0x1801b1403  mov     ecx, 3
0x1801b1408  mov     eax, ebx
0x1801b140a  lock cmpxchg [rdi+10h], ecx
0x1801b140f  cmovnz  ebx, eax
0x1801b1412  cmp     ebx, 2
0x1801b1415  jnz     short loc_1801B143B
0x1801b1417  lea     rcx, [rdi+60h]; this
0x1801b141b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801b1420  mov     byte ptr [rdi+0B0h], 1
0x1801b1427  lea     rcx, [rdi+60h]; _Mtx_t
0x1801b142b  call    cs:__imp__Mtx_unlock
0x1801b1431  lea     rcx, [rdi+18h]; _Cnd_t
0x1801b1435  call    cs:__imp__Cnd_broadcast
0x1801b143b  mov     rcx, rdi; this
0x1801b143e  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1801b1443  mov     rbx, [rsp+28h+arg_8]
0x1801b1448  mov     rbp, [rsp+28h+arg_10]
0x1801b144d  mov     rsi, [rsp+28h+arg_18]
0x1801b1452  add     rsp, 20h
0x1801b1456  pop     rdi
0x1801b1457  retn
```

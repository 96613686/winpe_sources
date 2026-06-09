# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18017a178`
- end: `0x18017a297`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `287`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180059f74`

## callees

- `0x180020198`
- `0x180076df0`
- `0x18015bed8`
- `0x18015fb2c`
- `0x18017a178`
- `0x18017a298`

## import_xrefs

- `MSVCP140!_Cnd_wait` at `0x18017a265`
- `MSVCP140!_Cnd_wait` at `0x18017a265`
- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18017a23a`
- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18017a23a`
- `MSVCP140!_Mtx_unlock` at `0x18017a20a`
- `MSVCP140!_Mtx_unlock` at `0x18017a20a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char v4; // r14
  struct _Mtx_internal_imp_t *v5; // rbx
  struct Concurrency::details::_CancellationTokenRegistration **v6; // rcx
  struct Concurrency::details::_CancellationTokenRegistration **v7; // rax
  struct Concurrency::details::_CancellationTokenRegistration ***v8; // rdx
  struct Concurrency::details::_CancellationTokenRegistration **v9; // r8
  signed __int32 v10; // eax
  unsigned int v11; // ebx
  Concurrency::details::platform *v12; // rcx
  _Mtx_t v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  v5 = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  v6 = (struct Concurrency::details::_CancellationTokenRegistration **)*((_QWORD *)this + 13);
  if ( v6 )
  {
    v7 = 0;
    while ( v6 )
    {
      v8 = (struct Concurrency::details::_CancellationTokenRegistration ***)(v6 + 1);
      if ( *v6 == a2 )
      {
        v9 = *v8;
        if ( v7 )
          v7[1] = (struct Concurrency::details::_CancellationTokenRegistration *)v9;
        else
          *((_QWORD *)this + 13) = v9;
        if ( !*v8 )
          *((_QWORD *)this + 14) = v7;
        operator delete(v6);
        break;
      }
      v7 = v6;
      v6 = *v8;
    }
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    Concurrency::details::_RefCounter::_Release(a2);
  }
  else
  {
    v4 = 1;
  }
  _Mtx_unlock(v5);
  if ( v4 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    v11 = 0;
    if ( v10 )
      v11 = v10;
    if ( v11 >= 2 )
    {
      v12 = (Concurrency::details::platform *)(v11 - 2);
      if ( (unsigned int)v12 >= 2
        && v11 != Concurrency::details::platform::GetCurrentThreadId(v12)
        && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
      {
        std::unique_lock<std::mutex>::unique_lock<std::mutex>(v13, (char *)a2 + 96);
        while ( !*((_BYTE *)a2 + 176) )
          _Cnd_wait((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24), v13[0]);
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v13);
      }
    }
  }
}

```

## disassembly

```asm
0x18017a178  mov     rax, rsp
0x18017a17b  mov     [rax+10h], rbx
0x18017a17f  mov     [rax+18h], rbp
0x18017a183  mov     [rax+20h], rsi
0x18017a187  push    rdi
0x18017a188  push    r12
0x18017a18a  push    r14
0x18017a18c  sub     rsp, 30h
0x18017a190  mov     rdi, rdx
0x18017a193  mov     rbp, rcx
0x18017a196  xor     r14b, r14b
0x18017a199  lea     rbx, [rcx+18h]
0x18017a19d  mov     [rax+8], rbx
0x18017a1a1  mov     rcx, rbx; this
0x18017a1a4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18017a1a9  mov     rcx, [rbp+68h]; void *
0x18017a1ad  mov     esi, 2
0x18017a1b2  lea     r12d, [rsi-1]
0x18017a1b6  test    rcx, rcx
0x18017a1b9  jnz     short loc_18017A1C0
0x18017a1bb  mov     r14b, r12b
0x18017a1be  jmp     short loc_18017A207
0x18017a1c0  xor     eax, eax
0x18017a1c2  test    rcx, rcx
0x18017a1c5  jz      short loc_18017A1F9
0x18017a1c7  lea     rdx, [rcx+8]
0x18017a1cb  cmp     [rcx], rdi
0x18017a1ce  jz      short loc_18017A1D8
0x18017a1d0  mov     rax, rcx
0x18017a1d3  mov     rcx, [rdx]
0x18017a1d6  jmp     short loc_18017A1C2
0x18017a1d8  mov     r8, [rdx]
0x18017a1db  test    rax, rax
0x18017a1de  jnz     short loc_18017A1E6
0x18017a1e0  mov     [rbp+68h], r8
0x18017a1e4  jmp     short loc_18017A1EA
0x18017a1e6  mov     [rax+8], r8
0x18017a1ea  cmp     qword ptr [rdx], 0
0x18017a1ee  jnz     short loc_18017A1F4
0x18017a1f0  mov     [rbp+70h], rax
0x18017a1f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017a1f9  mov     eax, esi
0x18017a1fb  xchg    eax, [rdi+10h]
0x18017a1fe  mov     rcx, rdi; this
0x18017a201  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18017a206  nop
0x18017a207  mov     rcx, rbx; _Mtx_t
0x18017a20a  call    cs:__imp__Mtx_unlock
0x18017a210  test    r14b, r14b
0x18017a213  jz      short loc_18017A27E
0x18017a215  xor     eax, eax
0x18017a217  lock cmpxchg [rdi+10h], r12d
0x18017a21d  mov     ebx, 0
0x18017a222  cmovnz  ebx, eax
0x18017a225  mov     ecx, ebx
0x18017a227  test    ebx, ebx
0x18017a229  jz      short loc_18017A27E
0x18017a22b  sub     ecx, 1
0x18017a22e  jz      short loc_18017A27E
0x18017a230  sub     ecx, 1
0x18017a233  jz      short loc_18017A27E
0x18017a235  cmp     ecx, 1
0x18017a238  jz      short loc_18017A27E
0x18017a23a  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18017a240  cmp     ebx, eax
0x18017a242  jz      short loc_18017A27E
0x18017a244  xchg    esi, [rdi+10h]
0x18017a247  cmp     esi, 3
0x18017a24a  jz      short loc_18017A27E
0x18017a24c  lea     rdx, [rdi+60h]
0x18017a250  lea     rcx, [rsp+48h+var_28]
0x18017a255  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18017a25a  jmp     short loc_18017A26B
0x18017a25c  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18017a261  lea     rcx, [rdi+18h]; _Cnd_t
0x18017a265  call    cs:__imp__Cnd_wait
0x18017a26b  cmp     byte ptr [rdi+0B0h], 0
0x18017a272  jz      short loc_18017A25C
0x18017a274  lea     rcx, [rsp+48h+var_28]
0x18017a279  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18017a27e  mov     rbx, [rsp+48h+arg_8]
0x18017a283  mov     rbp, [rsp+48h+arg_10]
0x18017a288  mov     rsi, [rsp+48h+arg_18]
0x18017a28d  add     rsp, 30h
0x18017a291  pop     r14
0x18017a293  pop     r12
0x18017a295  pop     rdi
0x18017a296  retn
```

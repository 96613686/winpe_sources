# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180033988`
- end: `0x180033a91`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800213ac`

## callees

- `0x18001df10`
- `0x180026dcc`
- `0x180031e70`
- `0x180032264`
- `0x180033988`
- `0x180033f30`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180033a40`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180033a40`
- `msvcp_win!_Cnd_wait` at `0x180033a6b`
- `msvcp_win!_Cnd_wait` at `0x180033a6b`
- `msvcp_win!_Mtx_unlock` at `0x180033a14`
- `msvcp_win!_Mtx_unlock` at `0x180033a14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  struct _Mtx_internal_imp_t *v4; // rbx
  struct Concurrency::details::_CancellationTokenRegistration **v5; // rcx
  char v6; // r14
  struct Concurrency::details::_CancellationTokenRegistration **v7; // rax
  struct Concurrency::details::_CancellationTokenRegistration *v8; // rdx
  Concurrency::details::platform *v9; // rcx
  unsigned __int32 v10; // eax
  _Mtx_t v11[9]; // [rsp+20h] [rbp-48h] BYREF

  v4 = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  v5 = (struct Concurrency::details::_CancellationTokenRegistration **)*((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( v5 )
    {
      v8 = v5[1];
      if ( *v5 == a2 )
      {
        if ( v7 )
          v7[1] = v8;
        else
          *((_QWORD *)this + 13) = v8;
        if ( !v5[1] )
          *((_QWORD *)this + 14) = v7;
        operator delete(v5, 0x10u);
        break;
      }
      v7 = v5;
      v5 = (struct Concurrency::details::_CancellationTokenRegistration **)v5[1];
    }
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    Concurrency::details::_RefCounter::_Release(a2);
  }
  else
  {
    v6 = 1;
  }
  _Mtx_unlock(v4);
  if ( v6 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v10 >= 2
      && v10 - 2 >= 2
      && v10 != Concurrency::details::platform::GetCurrentThreadId(v9)
      && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
    {
      std::unique_lock<std::mutex>::unique_lock<std::mutex>(v11, (char *)a2 + 96);
      while ( !*((_BYTE *)a2 + 176) )
        _Cnd_wait((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24), v11[0]);
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v11);
    }
  }
}

```

## disassembly

```asm
0x180033988  push    rbx
0x18003398a  push    rbp
0x18003398b  push    rsi
0x18003398c  push    rdi
0x18003398d  push    r12
0x18003398f  push    r14
0x180033991  sub     rsp, 38h
0x180033995  mov     rdi, rdx
0x180033998  mov     rbp, rcx
0x18003399b  lea     rbx, [rcx+18h]
0x18003399f  mov     [rsp+68h+arg_0], rbx
0x1800339a4  mov     rcx, rbx; this
0x1800339a7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800339ac  nop
0x1800339ad  mov     rcx, [rbp+68h]; void *
0x1800339b1  mov     esi, 2
0x1800339b6  lea     r12d, [rsi-1]
0x1800339ba  test    rcx, rcx
0x1800339bd  jnz     short loc_1800339C4
0x1800339bf  mov     r14b, r12b
0x1800339c2  jmp     short loc_180033A11
0x1800339c4  xor     r14b, r14b
0x1800339c7  xor     eax, eax
0x1800339c9  test    rcx, rcx
0x1800339cc  jz      short loc_180033A03
0x1800339ce  mov     rdx, [rcx+8]
0x1800339d2  cmp     [rcx], rdi
0x1800339d5  jz      short loc_1800339DF
0x1800339d7  mov     rax, rcx
0x1800339da  mov     rcx, rdx
0x1800339dd  jmp     short loc_1800339C9
0x1800339df  test    rax, rax
0x1800339e2  jnz     short loc_1800339EA
0x1800339e4  mov     [rbp+68h], rdx
0x1800339e8  jmp     short loc_1800339EE
0x1800339ea  mov     [rax+8], rdx
0x1800339ee  cmp     qword ptr [rcx+8], 0
0x1800339f3  jnz     short loc_1800339F9
0x1800339f5  mov     [rbp+70h], rax
0x1800339f9  mov     edx, 10h; unsigned __int64
0x1800339fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180033a03  mov     eax, esi
0x180033a05  xchg    eax, [rdi+10h]
0x180033a08  mov     rcx, rdi; this
0x180033a0b  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180033a10  nop
0x180033a11  mov     rcx, rbx; _Mtx_t
0x180033a14  call    cs:__imp__Mtx_unlock
0x180033a1a  test    r14b, r14b
0x180033a1d  jz      short loc_180033A84
0x180033a1f  xor     eax, eax
0x180033a21  lock cmpxchg [rdi+10h], r12d
0x180033a27  mov     ebx, eax
0x180033a29  jz      short loc_180033A84
0x180033a2b  mov     edx, eax
0x180033a2d  test    eax, eax
0x180033a2f  jz      short loc_180033A84
0x180033a31  sub     edx, 1
0x180033a34  jz      short loc_180033A84
0x180033a36  sub     edx, 1
0x180033a39  jz      short loc_180033A84
0x180033a3b  cmp     edx, 1
0x180033a3e  jz      short loc_180033A84
0x180033a40  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180033a46  cmp     ebx, eax
0x180033a48  jz      short loc_180033A84
0x180033a4a  xchg    esi, [rdi+10h]
0x180033a4d  cmp     esi, 3
0x180033a50  jz      short loc_180033A84
0x180033a52  lea     rdx, [rdi+60h]
0x180033a56  lea     rcx, [rsp+68h+var_48]
0x180033a5b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180033a60  jmp     short loc_180033A71
0x180033a62  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x180033a67  lea     rcx, [rdi+18h]; _Cnd_t
0x180033a6b  call    cs:__imp__Cnd_wait
0x180033a71  cmp     byte ptr [rdi+0B0h], 0
0x180033a78  jz      short loc_180033A62
0x180033a7a  lea     rcx, [rsp+68h+var_48]
0x180033a7f  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180033a84  add     rsp, 38h
0x180033a88  pop     r14
0x180033a8a  pop     r12
0x180033a8c  pop     rdi
0x180033a8d  pop     rsi
0x180033a8e  pop     rbp
0x180033a8f  pop     rbx
0x180033a90  retn
```

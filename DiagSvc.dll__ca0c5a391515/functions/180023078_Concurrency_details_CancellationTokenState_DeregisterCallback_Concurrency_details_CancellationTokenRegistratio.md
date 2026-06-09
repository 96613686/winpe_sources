# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180023078`
- end: `0x180023181`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e120`

## callees

- `0x1800040b4`
- `0x18001d9e0`
- `0x18001e230`
- `0x180023078`
- `0x180023dbc`
- `0x180024834`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180023130`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180023130`
- `msvcp_win!_Mtx_unlock` at `0x180023104`
- `msvcp_win!_Mtx_unlock` at `0x180023104`
- `msvcp_win!_Cnd_wait` at `0x18002315b`
- `msvcp_win!_Cnd_wait` at `0x18002315b`

## pseudocode

```c
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
        operator delete(v5);
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
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v11);
    }
  }
}

```

## disassembly

```asm
0x180023078  push    rbx
0x18002307a  push    rbp
0x18002307b  push    rsi
0x18002307c  push    rdi
0x18002307d  push    r12
0x18002307f  push    r14
0x180023081  sub     rsp, 38h
0x180023085  mov     rdi, rdx
0x180023088  mov     rbp, rcx
0x18002308b  lea     rbx, [rcx+18h]
0x18002308f  mov     [rsp+68h+arg_0], rbx
0x180023094  mov     rcx, rbx; this
0x180023097  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002309c  nop
0x18002309d  mov     rcx, [rbp+68h]; Block
0x1800230a1  mov     esi, 2
0x1800230a6  lea     r12d, [rsi-1]
0x1800230aa  test    rcx, rcx
0x1800230ad  jnz     short loc_1800230B4
0x1800230af  mov     r14b, r12b
0x1800230b2  jmp     short loc_180023101
0x1800230b4  xor     r14b, r14b
0x1800230b7  xor     eax, eax
0x1800230b9  test    rcx, rcx
0x1800230bc  jz      short loc_1800230F3
0x1800230be  mov     rdx, [rcx+8]
0x1800230c2  cmp     [rcx], rdi
0x1800230c5  jz      short loc_1800230CF
0x1800230c7  mov     rax, rcx
0x1800230ca  mov     rcx, rdx
0x1800230cd  jmp     short loc_1800230B9
0x1800230cf  test    rax, rax
0x1800230d2  jnz     short loc_1800230DA
0x1800230d4  mov     [rbp+68h], rdx
0x1800230d8  jmp     short loc_1800230DE
0x1800230da  mov     [rax+8], rdx
0x1800230de  cmp     qword ptr [rcx+8], 0
0x1800230e3  jnz     short loc_1800230E9
0x1800230e5  mov     [rbp+70h], rax
0x1800230e9  mov     edx, 10h
0x1800230ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800230f3  mov     eax, esi
0x1800230f5  xchg    eax, [rdi+10h]
0x1800230f8  mov     rcx, rdi; this
0x1800230fb  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180023100  nop
0x180023101  mov     rcx, rbx; _Mtx_t
0x180023104  call    cs:__imp__Mtx_unlock
0x18002310a  test    r14b, r14b
0x18002310d  jz      short loc_180023174
0x18002310f  xor     eax, eax
0x180023111  lock cmpxchg [rdi+10h], r12d
0x180023117  mov     ebx, eax
0x180023119  jz      short loc_180023174
0x18002311b  mov     edx, eax
0x18002311d  test    eax, eax
0x18002311f  jz      short loc_180023174
0x180023121  sub     edx, 1
0x180023124  jz      short loc_180023174
0x180023126  sub     edx, 1
0x180023129  jz      short loc_180023174
0x18002312b  cmp     edx, 1
0x18002312e  jz      short loc_180023174
0x180023130  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180023136  cmp     ebx, eax
0x180023138  jz      short loc_180023174
0x18002313a  xchg    esi, [rdi+10h]
0x18002313d  cmp     esi, 3
0x180023140  jz      short loc_180023174
0x180023142  lea     rdx, [rdi+60h]
0x180023146  lea     rcx, [rsp+68h+var_48]
0x18002314b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180023150  jmp     short loc_180023161
0x180023152  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x180023157  lea     rcx, [rdi+18h]; _Cnd_t
0x18002315b  call    cs:__imp__Cnd_wait
0x180023161  cmp     byte ptr [rdi+0B0h], 0
0x180023168  jz      short loc_180023152
0x18002316a  lea     rcx, [rsp+68h+var_48]
0x18002316f  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180023174  add     rsp, 38h
0x180023178  pop     r14
0x18002317a  pop     r12
0x18002317c  pop     rdi
0x18002317d  pop     rsi
0x18002317e  pop     rbp
0x18002317f  pop     rbx
0x180023180  retn
```

# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180017788`
- end: `0x180017891`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001269c`

## callees

- `0x180004194`
- `0x180011e50`
- `0x180012aec`
- `0x180017788`
- `0x18001a068`
- `0x18001b764`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180017814`
- `msvcp_win!_Mtx_unlock` at `0x180017814`
- `msvcp_win!_Cnd_wait` at `0x18001786b`
- `msvcp_win!_Cnd_wait` at `0x18001786b`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180017840`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180017840`

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
        operator delete(v5, (const struct std::nothrow_t *)0x10);
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
0x180017788  push    rbx
0x18001778a  push    rbp
0x18001778b  push    rsi
0x18001778c  push    rdi
0x18001778d  push    r12
0x18001778f  push    r14
0x180017791  sub     rsp, 38h
0x180017795  mov     rdi, rdx
0x180017798  mov     rbp, rcx
0x18001779b  lea     rbx, [rcx+18h]
0x18001779f  mov     [rsp+68h+arg_0], rbx
0x1800177a4  mov     rcx, rbx; this
0x1800177a7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800177ac  nop
0x1800177ad  mov     rcx, [rbp+68h]; void *
0x1800177b1  mov     esi, 2
0x1800177b6  lea     r12d, [rsi-1]
0x1800177ba  test    rcx, rcx
0x1800177bd  jnz     short loc_1800177C4
0x1800177bf  mov     r14b, r12b
0x1800177c2  jmp     short loc_180017811
0x1800177c4  xor     r14b, r14b
0x1800177c7  xor     eax, eax
0x1800177c9  test    rcx, rcx
0x1800177cc  jz      short loc_180017803
0x1800177ce  mov     rdx, [rcx+8]
0x1800177d2  cmp     [rcx], rdi
0x1800177d5  jz      short loc_1800177DF
0x1800177d7  mov     rax, rcx
0x1800177da  mov     rcx, rdx
0x1800177dd  jmp     short loc_1800177C9
0x1800177df  test    rax, rax
0x1800177e2  jnz     short loc_1800177EA
0x1800177e4  mov     [rbp+68h], rdx
0x1800177e8  jmp     short loc_1800177EE
0x1800177ea  mov     [rax+8], rdx
0x1800177ee  cmp     qword ptr [rcx+8], 0
0x1800177f3  jnz     short loc_1800177F9
0x1800177f5  mov     [rbp+70h], rax
0x1800177f9  mov     edx, 10h; struct std::nothrow_t *
0x1800177fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017803  mov     eax, esi
0x180017805  xchg    eax, [rdi+10h]
0x180017808  mov     rcx, rdi; this
0x18001780b  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180017810  nop
0x180017811  mov     rcx, rbx; _Mtx_t
0x180017814  call    cs:__imp__Mtx_unlock
0x18001781a  test    r14b, r14b
0x18001781d  jz      short loc_180017884
0x18001781f  xor     eax, eax
0x180017821  lock cmpxchg [rdi+10h], r12d
0x180017827  mov     ebx, eax
0x180017829  jz      short loc_180017884
0x18001782b  mov     edx, eax
0x18001782d  test    eax, eax
0x18001782f  jz      short loc_180017884
0x180017831  sub     edx, 1
0x180017834  jz      short loc_180017884
0x180017836  sub     edx, 1
0x180017839  jz      short loc_180017884
0x18001783b  cmp     edx, 1
0x18001783e  jz      short loc_180017884
0x180017840  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180017846  cmp     ebx, eax
0x180017848  jz      short loc_180017884
0x18001784a  xchg    esi, [rdi+10h]
0x18001784d  cmp     esi, 3
0x180017850  jz      short loc_180017884
0x180017852  lea     rdx, [rdi+60h]
0x180017856  lea     rcx, [rsp+68h+var_48]
0x18001785b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180017860  jmp     short loc_180017871
0x180017862  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x180017867  lea     rcx, [rdi+18h]; _Cnd_t
0x18001786b  call    cs:__imp__Cnd_wait
0x180017871  cmp     byte ptr [rdi+0B0h], 0
0x180017878  jz      short loc_180017862
0x18001787a  lea     rcx, [rsp+68h+var_48]
0x18001787f  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180017884  add     rsp, 38h
0x180017888  pop     r14
0x18001788a  pop     r12
0x18001788c  pop     rdi
0x18001788d  pop     rsi
0x18001788e  pop     rbp
0x18001788f  pop     rbx
0x180017890  retn
```

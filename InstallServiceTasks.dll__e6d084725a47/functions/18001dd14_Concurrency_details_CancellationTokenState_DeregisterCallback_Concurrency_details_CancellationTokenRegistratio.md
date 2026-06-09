# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18001dd14`
- end: `0x18001de1d`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b548`

## callees

- `0x1800038fc`
- `0x18001ab74`
- `0x18001b630`
- `0x18001dd14`
- `0x18001e6cc`
- `0x18001f150`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001ddcc`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001ddcc`
- `msvcp_win!_Mtx_unlock` at `0x18001dda0`
- `msvcp_win!_Mtx_unlock` at `0x18001dda0`
- `msvcp_win!_Cnd_wait` at `0x18001ddf7`
- `msvcp_win!_Cnd_wait` at `0x18001ddf7`

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
0x18001dd14  push    rbx
0x18001dd16  push    rbp
0x18001dd17  push    rsi
0x18001dd18  push    rdi
0x18001dd19  push    r12
0x18001dd1b  push    r14
0x18001dd1d  sub     rsp, 38h
0x18001dd21  mov     rdi, rdx
0x18001dd24  mov     rbp, rcx
0x18001dd27  lea     rbx, [rcx+18h]
0x18001dd2b  mov     [rsp+68h+arg_0], rbx
0x18001dd30  mov     rcx, rbx; this
0x18001dd33  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001dd38  nop
0x18001dd39  mov     rcx, [rbp+68h]; void *
0x18001dd3d  mov     esi, 2
0x18001dd42  lea     r12d, [rsi-1]
0x18001dd46  test    rcx, rcx
0x18001dd49  jnz     short loc_18001DD50
0x18001dd4b  mov     r14b, r12b
0x18001dd4e  jmp     short loc_18001DD9D
0x18001dd50  xor     r14b, r14b
0x18001dd53  xor     eax, eax
0x18001dd55  test    rcx, rcx
0x18001dd58  jz      short loc_18001DD8F
0x18001dd5a  mov     rdx, [rcx+8]
0x18001dd5e  cmp     [rcx], rdi
0x18001dd61  jz      short loc_18001DD6B
0x18001dd63  mov     rax, rcx
0x18001dd66  mov     rcx, rdx
0x18001dd69  jmp     short loc_18001DD55
0x18001dd6b  test    rax, rax
0x18001dd6e  jnz     short loc_18001DD76
0x18001dd70  mov     [rbp+68h], rdx
0x18001dd74  jmp     short loc_18001DD7A
0x18001dd76  mov     [rax+8], rdx
0x18001dd7a  cmp     qword ptr [rcx+8], 0
0x18001dd7f  jnz     short loc_18001DD85
0x18001dd81  mov     [rbp+70h], rax
0x18001dd85  mov     edx, 10h; struct std::nothrow_t *
0x18001dd8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001dd8f  mov     eax, esi
0x18001dd91  xchg    eax, [rdi+10h]
0x18001dd94  mov     rcx, rdi; this
0x18001dd97  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18001dd9c  nop
0x18001dd9d  mov     rcx, rbx; _Mtx_t
0x18001dda0  call    cs:__imp__Mtx_unlock
0x18001dda6  test    r14b, r14b
0x18001dda9  jz      short loc_18001DE10
0x18001ddab  xor     eax, eax
0x18001ddad  lock cmpxchg [rdi+10h], r12d
0x18001ddb3  mov     ebx, eax
0x18001ddb5  jz      short loc_18001DE10
0x18001ddb7  mov     edx, eax
0x18001ddb9  test    eax, eax
0x18001ddbb  jz      short loc_18001DE10
0x18001ddbd  sub     edx, 1
0x18001ddc0  jz      short loc_18001DE10
0x18001ddc2  sub     edx, 1
0x18001ddc5  jz      short loc_18001DE10
0x18001ddc7  cmp     edx, 1
0x18001ddca  jz      short loc_18001DE10
0x18001ddcc  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18001ddd2  cmp     ebx, eax
0x18001ddd4  jz      short loc_18001DE10
0x18001ddd6  xchg    esi, [rdi+10h]
0x18001ddd9  cmp     esi, 3
0x18001dddc  jz      short loc_18001DE10
0x18001ddde  lea     rdx, [rdi+60h]
0x18001dde2  lea     rcx, [rsp+68h+var_48]
0x18001dde7  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001ddec  jmp     short loc_18001DDFD
0x18001ddee  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x18001ddf3  lea     rcx, [rdi+18h]; _Cnd_t
0x18001ddf7  call    cs:__imp__Cnd_wait
0x18001ddfd  cmp     byte ptr [rdi+0B0h], 0
0x18001de04  jz      short loc_18001DDEE
0x18001de06  lea     rcx, [rsp+68h+var_48]
0x18001de0b  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001de10  add     rsp, 38h
0x18001de14  pop     r14
0x18001de16  pop     r12
0x18001de18  pop     rdi
0x18001de19  pop     rsi
0x18001de1a  pop     rbp
0x18001de1b  pop     rbx
0x18001de1c  retn
```

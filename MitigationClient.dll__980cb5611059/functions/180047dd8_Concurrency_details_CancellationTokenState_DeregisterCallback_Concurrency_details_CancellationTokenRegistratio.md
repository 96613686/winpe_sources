# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180047dd8`
- end: `0x180047ee1`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180046ca8`

## callees

- `0x18000abc4`
- `0x1800466bc`
- `0x180046d5c`
- `0x180047dd8`
- `0x1800486b4`
- `0x180048ea0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180047e64`
- `msvcp_win!_Mtx_unlock` at `0x180047e64`
- `msvcp_win!_Cnd_wait` at `0x180047ebb`
- `msvcp_win!_Cnd_wait` at `0x180047ebb`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180047e90`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180047e90`

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
0x180047dd8  push    rbx
0x180047dda  push    rbp
0x180047ddb  push    rsi
0x180047ddc  push    rdi
0x180047ddd  push    r12
0x180047ddf  push    r14
0x180047de1  sub     rsp, 38h
0x180047de5  mov     rdi, rdx
0x180047de8  mov     rbp, rcx
0x180047deb  lea     rbx, [rcx+18h]
0x180047def  mov     [rsp+68h+arg_0], rbx
0x180047df4  mov     rcx, rbx; this
0x180047df7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180047dfc  nop
0x180047dfd  mov     rcx, [rbp+68h]; void *
0x180047e01  mov     esi, 2
0x180047e06  lea     r12d, [rsi-1]
0x180047e0a  test    rcx, rcx
0x180047e0d  jnz     short loc_180047E14
0x180047e0f  mov     r14b, r12b
0x180047e12  jmp     short loc_180047E61
0x180047e14  xor     r14b, r14b
0x180047e17  xor     eax, eax
0x180047e19  test    rcx, rcx
0x180047e1c  jz      short loc_180047E53
0x180047e1e  mov     rdx, [rcx+8]
0x180047e22  cmp     [rcx], rdi
0x180047e25  jz      short loc_180047E2F
0x180047e27  mov     rax, rcx
0x180047e2a  mov     rcx, rdx
0x180047e2d  jmp     short loc_180047E19
0x180047e2f  test    rax, rax
0x180047e32  jnz     short loc_180047E3A
0x180047e34  mov     [rbp+68h], rdx
0x180047e38  jmp     short loc_180047E3E
0x180047e3a  mov     [rax+8], rdx
0x180047e3e  cmp     qword ptr [rcx+8], 0
0x180047e43  jnz     short loc_180047E49
0x180047e45  mov     [rbp+70h], rax
0x180047e49  mov     edx, 10h; unsigned __int64
0x180047e4e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180047e53  mov     eax, esi
0x180047e55  xchg    eax, [rdi+10h]
0x180047e58  mov     rcx, rdi; this
0x180047e5b  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180047e60  nop
0x180047e61  mov     rcx, rbx; _Mtx_t
0x180047e64  call    cs:__imp__Mtx_unlock
0x180047e6a  test    r14b, r14b
0x180047e6d  jz      short loc_180047ED4
0x180047e6f  xor     eax, eax
0x180047e71  lock cmpxchg [rdi+10h], r12d
0x180047e77  mov     ebx, eax
0x180047e79  jz      short loc_180047ED4
0x180047e7b  mov     edx, eax
0x180047e7d  test    eax, eax
0x180047e7f  jz      short loc_180047ED4
0x180047e81  sub     edx, 1
0x180047e84  jz      short loc_180047ED4
0x180047e86  sub     edx, 1
0x180047e89  jz      short loc_180047ED4
0x180047e8b  cmp     edx, 1
0x180047e8e  jz      short loc_180047ED4
0x180047e90  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180047e96  cmp     ebx, eax
0x180047e98  jz      short loc_180047ED4
0x180047e9a  xchg    esi, [rdi+10h]
0x180047e9d  cmp     esi, 3
0x180047ea0  jz      short loc_180047ED4
0x180047ea2  lea     rdx, [rdi+60h]
0x180047ea6  lea     rcx, [rsp+68h+var_48]
0x180047eab  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180047eb0  jmp     short loc_180047EC1
0x180047eb2  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x180047eb7  lea     rcx, [rdi+18h]; _Cnd_t
0x180047ebb  call    cs:__imp__Cnd_wait
0x180047ec1  cmp     byte ptr [rdi+0B0h], 0
0x180047ec8  jz      short loc_180047EB2
0x180047eca  lea     rcx, [rsp+68h+var_48]
0x180047ecf  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180047ed4  add     rsp, 38h
0x180047ed8  pop     r14
0x180047eda  pop     r12
0x180047edc  pop     rdi
0x180047edd  pop     rsi
0x180047ede  pop     rbp
0x180047edf  pop     rbx
0x180047ee0  retn
```

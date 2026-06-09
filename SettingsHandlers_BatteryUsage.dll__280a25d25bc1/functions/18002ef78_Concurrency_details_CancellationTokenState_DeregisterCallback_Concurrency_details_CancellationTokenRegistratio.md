# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18002ef78`
- end: `0x18002f081`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b2b0`

## callees

- `0x1800029d0`
- `0x18002aa2c`
- `0x18002b518`
- `0x18002ef78`
- `0x18002fe44`
- `0x180031474`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18002f05b`
- `msvcp_win!_Cnd_wait` at `0x18002f05b`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18002f030`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18002f030`
- `msvcp_win!_Mtx_unlock` at `0x18002f004`
- `msvcp_win!_Mtx_unlock` at `0x18002f004`

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
0x18002ef78  push    rbx
0x18002ef7a  push    rbp
0x18002ef7b  push    rsi
0x18002ef7c  push    rdi
0x18002ef7d  push    r12
0x18002ef7f  push    r14
0x18002ef81  sub     rsp, 38h
0x18002ef85  mov     rdi, rdx
0x18002ef88  mov     rbp, rcx
0x18002ef8b  lea     rbx, [rcx+18h]
0x18002ef8f  mov     [rsp+68h+arg_0], rbx
0x18002ef94  mov     rcx, rbx; this
0x18002ef97  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002ef9c  nop
0x18002ef9d  mov     rcx, [rbp+68h]; void *
0x18002efa1  mov     esi, 2
0x18002efa6  lea     r12d, [rsi-1]
0x18002efaa  test    rcx, rcx
0x18002efad  jnz     short loc_18002EFB4
0x18002efaf  mov     r14b, r12b
0x18002efb2  jmp     short loc_18002F001
0x18002efb4  xor     r14b, r14b
0x18002efb7  xor     eax, eax
0x18002efb9  test    rcx, rcx
0x18002efbc  jz      short loc_18002EFF3
0x18002efbe  mov     rdx, [rcx+8]
0x18002efc2  cmp     [rcx], rdi
0x18002efc5  jz      short loc_18002EFCF
0x18002efc7  mov     rax, rcx
0x18002efca  mov     rcx, rdx
0x18002efcd  jmp     short loc_18002EFB9
0x18002efcf  test    rax, rax
0x18002efd2  jnz     short loc_18002EFDA
0x18002efd4  mov     [rbp+68h], rdx
0x18002efd8  jmp     short loc_18002EFDE
0x18002efda  mov     [rax+8], rdx
0x18002efde  cmp     qword ptr [rcx+8], 0
0x18002efe3  jnz     short loc_18002EFE9
0x18002efe5  mov     [rbp+70h], rax
0x18002efe9  mov     edx, 10h; struct std::nothrow_t *
0x18002efee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002eff3  mov     eax, esi
0x18002eff5  xchg    eax, [rdi+10h]
0x18002eff8  mov     rcx, rdi; this
0x18002effb  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18002f000  nop
0x18002f001  mov     rcx, rbx; _Mtx_t
0x18002f004  call    cs:__imp__Mtx_unlock
0x18002f00a  test    r14b, r14b
0x18002f00d  jz      short loc_18002F074
0x18002f00f  xor     eax, eax
0x18002f011  lock cmpxchg [rdi+10h], r12d
0x18002f017  mov     ebx, eax
0x18002f019  jz      short loc_18002F074
0x18002f01b  mov     edx, eax
0x18002f01d  test    eax, eax
0x18002f01f  jz      short loc_18002F074
0x18002f021  sub     edx, 1
0x18002f024  jz      short loc_18002F074
0x18002f026  sub     edx, 1
0x18002f029  jz      short loc_18002F074
0x18002f02b  cmp     edx, 1
0x18002f02e  jz      short loc_18002F074
0x18002f030  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18002f036  cmp     ebx, eax
0x18002f038  jz      short loc_18002F074
0x18002f03a  xchg    esi, [rdi+10h]
0x18002f03d  cmp     esi, 3
0x18002f040  jz      short loc_18002F074
0x18002f042  lea     rdx, [rdi+60h]
0x18002f046  lea     rcx, [rsp+68h+var_48]
0x18002f04b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18002f050  jmp     short loc_18002F061
0x18002f052  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x18002f057  lea     rcx, [rdi+18h]; _Cnd_t
0x18002f05b  call    cs:__imp__Cnd_wait
0x18002f061  cmp     byte ptr [rdi+0B0h], 0
0x18002f068  jz      short loc_18002F052
0x18002f06a  lea     rcx, [rsp+68h+var_48]
0x18002f06f  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18002f074  add     rsp, 38h
0x18002f078  pop     r14
0x18002f07a  pop     r12
0x18002f07c  pop     rdi
0x18002f07d  pop     rsi
0x18002f07e  pop     rbp
0x18002f07f  pop     rbx
0x18002f080  retn
```

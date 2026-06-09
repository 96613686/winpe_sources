# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18001cd98`
- end: `0x18001cea1`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `265`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010e18`

## callees

- `0x180002750`
- `0x18000f98c`
- `0x1800112e0`
- `0x18001cd98`
- `0x18001d7a0`
- `0x18001e88c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001ce24`
- `msvcp_win!_Mtx_unlock` at `0x18001ce24`
- `msvcp_win!_Cnd_wait` at `0x18001ce7b`
- `msvcp_win!_Cnd_wait` at `0x18001ce7b`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001ce50`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001ce50`

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
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v11);
    }
  }
}

```

## disassembly

```asm
0x18001cd98  push    rbx
0x18001cd9a  push    rbp
0x18001cd9b  push    rsi
0x18001cd9c  push    rdi
0x18001cd9d  push    r12
0x18001cd9f  push    r14
0x18001cda1  sub     rsp, 38h
0x18001cda5  mov     rdi, rdx
0x18001cda8  mov     rbp, rcx
0x18001cdab  lea     rbx, [rcx+18h]
0x18001cdaf  mov     [rsp+68h+arg_0], rbx
0x18001cdb4  mov     rcx, rbx; this
0x18001cdb7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001cdbc  nop
0x18001cdbd  mov     rcx, [rbp+68h]; void *
0x18001cdc1  mov     esi, 2
0x18001cdc6  lea     r12d, [rsi-1]
0x18001cdca  test    rcx, rcx
0x18001cdcd  jnz     short loc_18001CDD4
0x18001cdcf  mov     r14b, r12b
0x18001cdd2  jmp     short loc_18001CE21
0x18001cdd4  xor     r14b, r14b
0x18001cdd7  xor     eax, eax
0x18001cdd9  test    rcx, rcx
0x18001cddc  jz      short loc_18001CE13
0x18001cdde  mov     rdx, [rcx+8]
0x18001cde2  cmp     [rcx], rdi
0x18001cde5  jz      short loc_18001CDEF
0x18001cde7  mov     rax, rcx
0x18001cdea  mov     rcx, rdx
0x18001cded  jmp     short loc_18001CDD9
0x18001cdef  test    rax, rax
0x18001cdf2  jnz     short loc_18001CDFA
0x18001cdf4  mov     [rbp+68h], rdx
0x18001cdf8  jmp     short loc_18001CDFE
0x18001cdfa  mov     [rax+8], rdx
0x18001cdfe  cmp     qword ptr [rcx+8], 0
0x18001ce03  jnz     short loc_18001CE09
0x18001ce05  mov     [rbp+70h], rax
0x18001ce09  mov     edx, 10h; unsigned __int64
0x18001ce0e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ce13  mov     eax, esi
0x18001ce15  xchg    eax, [rdi+10h]
0x18001ce18  mov     rcx, rdi; this
0x18001ce1b  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18001ce20  nop
0x18001ce21  mov     rcx, rbx; _Mtx_t
0x18001ce24  call    cs:__imp__Mtx_unlock
0x18001ce2a  test    r14b, r14b
0x18001ce2d  jz      short loc_18001CE94
0x18001ce2f  xor     eax, eax
0x18001ce31  lock cmpxchg [rdi+10h], r12d
0x18001ce37  mov     ebx, eax
0x18001ce39  jz      short loc_18001CE94
0x18001ce3b  mov     edx, eax
0x18001ce3d  test    eax, eax
0x18001ce3f  jz      short loc_18001CE94
0x18001ce41  sub     edx, 1
0x18001ce44  jz      short loc_18001CE94
0x18001ce46  sub     edx, 1
0x18001ce49  jz      short loc_18001CE94
0x18001ce4b  cmp     edx, 1
0x18001ce4e  jz      short loc_18001CE94
0x18001ce50  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18001ce56  cmp     ebx, eax
0x18001ce58  jz      short loc_18001CE94
0x18001ce5a  xchg    esi, [rdi+10h]
0x18001ce5d  cmp     esi, 3
0x18001ce60  jz      short loc_18001CE94
0x18001ce62  lea     rdx, [rdi+60h]
0x18001ce66  lea     rcx, [rsp+68h+var_48]
0x18001ce6b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001ce70  jmp     short loc_18001CE81
0x18001ce72  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x18001ce77  lea     rcx, [rdi+18h]; _Cnd_t
0x18001ce7b  call    cs:__imp__Cnd_wait
0x18001ce81  cmp     byte ptr [rdi+0B0h], 0
0x18001ce88  jz      short loc_18001CE72
0x18001ce8a  lea     rcx, [rsp+68h+var_48]
0x18001ce8f  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001ce94  add     rsp, 38h
0x18001ce98  pop     r14
0x18001ce9a  pop     r12
0x18001ce9c  pop     rdi
0x18001ce9d  pop     rsi
0x18001ce9e  pop     rbp
0x18001ce9f  pop     rbx
0x18001cea0  retn
```

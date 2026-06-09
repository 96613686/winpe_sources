# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x14001ea38`
- end: `0x14001eb54`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `284`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001c060`

## callees

- `0x140004be0`
- `0x140016074`
- `0x140016d88`
- `0x140019d2c`
- `0x14001ea38`
- `0x14001f4ac`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001eaf6`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001eaf6`
- `msvcp_win!_Cnd_wait` at `0x14001eb27`
- `msvcp_win!_Cnd_wait` at `0x14001eb27`
- `msvcp_win!_Mtx_unlock` at `0x14001eac4`
- `msvcp_win!_Mtx_unlock` at `0x14001eac4`

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
0x14001ea38  push    rbx
0x14001ea3a  push    rbp
0x14001ea3b  push    rsi
0x14001ea3c  push    rdi
0x14001ea3d  push    r12
0x14001ea3f  push    r14
0x14001ea41  sub     rsp, 38h
0x14001ea45  mov     rdi, rdx
0x14001ea48  mov     rbp, rcx
0x14001ea4b  lea     rbx, [rcx+18h]
0x14001ea4f  mov     [rsp+68h+arg_0], rbx
0x14001ea54  mov     rcx, rbx; this
0x14001ea57  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14001ea5c  nop
0x14001ea5d  mov     rcx, [rbp+68h]; void *
0x14001ea61  mov     esi, 2
0x14001ea66  lea     r12d, [rsi-1]
0x14001ea6a  test    rcx, rcx
0x14001ea6d  jnz     short loc_14001EA74
0x14001ea6f  mov     r14b, r12b
0x14001ea72  jmp     short loc_14001EAC1
0x14001ea74  xor     r14b, r14b
0x14001ea77  xor     eax, eax
0x14001ea79  test    rcx, rcx
0x14001ea7c  jz      short loc_14001EAB3
0x14001ea7e  mov     rdx, [rcx+8]
0x14001ea82  cmp     [rcx], rdi
0x14001ea85  jz      short loc_14001EA8F
0x14001ea87  mov     rax, rcx
0x14001ea8a  mov     rcx, rdx
0x14001ea8d  jmp     short loc_14001EA79
0x14001ea8f  test    rax, rax
0x14001ea92  jnz     short loc_14001EA9A
0x14001ea94  mov     [rbp+68h], rdx
0x14001ea98  jmp     short loc_14001EA9E
0x14001ea9a  mov     [rax+8], rdx
0x14001ea9e  cmp     qword ptr [rcx+8], 0
0x14001eaa3  jnz     short loc_14001EAA9
0x14001eaa5  mov     [rbp+70h], rax
0x14001eaa9  mov     edx, 10h; struct std::nothrow_t *
0x14001eaae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001eab3  mov     eax, esi
0x14001eab5  xchg    eax, [rdi+10h]
0x14001eab8  mov     rcx, rdi; this
0x14001eabb  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x14001eac0  nop
0x14001eac1  mov     rcx, rbx; _Mtx_t
0x14001eac4  call    cs:__imp__Mtx_unlock
0x14001eacb  nop     dword ptr [rax+rax+00h]
0x14001ead0  test    r14b, r14b
0x14001ead3  jz      short loc_14001EB46
0x14001ead5  xor     eax, eax
0x14001ead7  lock cmpxchg [rdi+10h], r12d
0x14001eadd  mov     ebx, eax
0x14001eadf  jz      short loc_14001EB46
0x14001eae1  mov     edx, eax
0x14001eae3  test    eax, eax
0x14001eae5  jz      short loc_14001EB46
0x14001eae7  sub     edx, 1
0x14001eaea  jz      short loc_14001EB46
0x14001eaec  sub     edx, 1
0x14001eaef  jz      short loc_14001EB46
0x14001eaf1  cmp     edx, 1
0x14001eaf4  jz      short loc_14001EB46
0x14001eaf6  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x14001eafd  nop     dword ptr [rax+rax+00h]
0x14001eb02  cmp     ebx, eax
0x14001eb04  jz      short loc_14001EB46
0x14001eb06  xchg    esi, [rdi+10h]
0x14001eb09  cmp     esi, 3
0x14001eb0c  jz      short loc_14001EB46
0x14001eb0e  lea     rdx, [rdi+60h]
0x14001eb12  lea     rcx, [rsp+68h+var_48]
0x14001eb17  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x14001eb1c  jmp     short loc_14001EB33
0x14001eb1e  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x14001eb23  lea     rcx, [rdi+18h]; _Cnd_t
0x14001eb27  call    cs:__imp__Cnd_wait
0x14001eb2e  nop     dword ptr [rax+rax+00h]
0x14001eb33  cmp     byte ptr [rdi+0B0h], 0
0x14001eb3a  jz      short loc_14001EB1E
0x14001eb3c  lea     rcx, [rsp+68h+var_48]
0x14001eb41  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x14001eb46  add     rsp, 38h
0x14001eb4a  pop     r14
0x14001eb4c  pop     r12
0x14001eb4e  pop     rdi
0x14001eb4f  pop     rsi
0x14001eb50  pop     rbp
0x14001eb51  pop     rbx
0x14001eb52  retn
```

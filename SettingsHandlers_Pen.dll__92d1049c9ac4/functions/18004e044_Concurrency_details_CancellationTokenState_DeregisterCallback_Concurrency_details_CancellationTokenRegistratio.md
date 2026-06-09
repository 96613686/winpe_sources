# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18004e044`
- end: `0x18004e153`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `271`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004e15c`

## callees

- `0x1800035bc`
- `0x18004958c`
- `0x18004e044`
- `0x18004ed78`
- `0x18004fac4`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004e0fc`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004e0fc`
- `msvcp_win!_Cnd_wait` at `0x18004e12d`
- `msvcp_win!_Cnd_wait` at `0x18004e12d`
- `msvcp_win!_Mtx_unlock` at `0x18004e0d0`
- `msvcp_win!_Mtx_unlock` at `0x18004e0d0`

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
  char *v11; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h]

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
      v11 = (char *)a2 + 96;
      std::_Mutex_base::lock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
      v12 = 1;
      while ( !*((_BYTE *)a2 + 176) )
        _Cnd_wait(
          (struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24),
          (struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v11);
    }
  }
}

```

## disassembly

```asm
0x18004e044  push    rbx
0x18004e046  push    rbp
0x18004e047  push    rsi
0x18004e048  push    rdi
0x18004e049  push    r12
0x18004e04b  push    r14
0x18004e04d  sub     rsp, 38h
0x18004e051  mov     rdi, rdx
0x18004e054  mov     rsi, rcx
0x18004e057  lea     rbx, [rcx+18h]
0x18004e05b  mov     [rsp+68h+arg_0], rbx
0x18004e060  mov     rcx, rbx; this
0x18004e063  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004e068  nop
0x18004e069  mov     rcx, [rsi+68h]; Block
0x18004e06d  mov     ebp, 2
0x18004e072  lea     r12d, [rbp-1]
0x18004e076  test    rcx, rcx
0x18004e079  jnz     short loc_18004E080
0x18004e07b  mov     r14b, r12b
0x18004e07e  jmp     short loc_18004E0CD
0x18004e080  xor     r14b, r14b
0x18004e083  xor     eax, eax
0x18004e085  test    rcx, rcx
0x18004e088  jz      short loc_18004E0BF
0x18004e08a  mov     rdx, [rcx+8]
0x18004e08e  cmp     [rcx], rdi
0x18004e091  jz      short loc_18004E09B
0x18004e093  mov     rax, rcx
0x18004e096  mov     rcx, rdx
0x18004e099  jmp     short loc_18004E085
0x18004e09b  test    rax, rax
0x18004e09e  jnz     short loc_18004E0A6
0x18004e0a0  mov     [rsi+68h], rdx
0x18004e0a4  jmp     short loc_18004E0AA
0x18004e0a6  mov     [rax+8], rdx
0x18004e0aa  cmp     qword ptr [rcx+8], 0
0x18004e0af  jnz     short loc_18004E0B5
0x18004e0b1  mov     [rsi+70h], rax
0x18004e0b5  mov     edx, 10h
0x18004e0ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004e0bf  mov     eax, ebp
0x18004e0c1  xchg    eax, [rdi+10h]
0x18004e0c4  mov     rcx, rdi; this
0x18004e0c7  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18004e0cc  nop
0x18004e0cd  mov     rcx, rbx; _Mtx_t
0x18004e0d0  call    cs:__imp__Mtx_unlock
0x18004e0d6  test    r14b, r14b
0x18004e0d9  jz      short loc_18004E146
0x18004e0db  xor     eax, eax
0x18004e0dd  lock cmpxchg [rdi+10h], r12d
0x18004e0e3  mov     ebx, eax
0x18004e0e5  jz      short loc_18004E146
0x18004e0e7  mov     edx, eax
0x18004e0e9  test    eax, eax
0x18004e0eb  jz      short loc_18004E146
0x18004e0ed  sub     edx, 1
0x18004e0f0  jz      short loc_18004E146
0x18004e0f2  sub     edx, 1
0x18004e0f5  jz      short loc_18004E146
0x18004e0f7  cmp     edx, 1
0x18004e0fa  jz      short loc_18004E146
0x18004e0fc  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18004e102  cmp     ebx, eax
0x18004e104  jz      short loc_18004E146
0x18004e106  xchg    ebp, [rdi+10h]
0x18004e109  cmp     ebp, 3
0x18004e10c  jz      short loc_18004E146
0x18004e10e  lea     rbx, [rdi+60h]
0x18004e112  mov     [rsp+68h+var_48], rbx
0x18004e117  mov     rcx, rbx; this
0x18004e11a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004e11f  mov     [rsp+68h+var_40], r12b
0x18004e124  jmp     short loc_18004E133
0x18004e126  mov     rdx, rbx; _Mtx_t
0x18004e129  lea     rcx, [rdi+18h]; _Cnd_t
0x18004e12d  call    cs:__imp__Cnd_wait
0x18004e133  cmp     byte ptr [rdi+0B0h], 0
0x18004e13a  jz      short loc_18004E126
0x18004e13c  lea     rcx, [rsp+68h+var_48]
0x18004e141  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18004e146  add     rsp, 38h
0x18004e14a  pop     r14
0x18004e14c  pop     r12
0x18004e14e  pop     rdi
0x18004e14f  pop     rsi
0x18004e150  pop     rbp
0x18004e151  pop     rbx
0x18004e152  retn
```

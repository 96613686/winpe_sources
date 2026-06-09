# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18001b900`
- end: `0x18001ba5d`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `349`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800171b8`
- `0x18003035c`
- `0x18005d1f8`

## callees

- `0x1800060fc`
- `0x18001b900`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18001ba28`
- `msvcp_win!_Cnd_wait` at `0x18001ba28`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001b9e2`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001b9e2`
- `msvcp_win!_Mtx_unlock` at `0x18001b9b6`
- `msvcp_win!_Mtx_unlock` at `0x18001ba3a`
- `msvcp_win!_Mtx_unlock` at `0x18001b9b6`
- `msvcp_win!_Mtx_unlock` at `0x18001ba3a`
- `msvcp_win!_Mtx_lock` at `0x18001b922`
- `msvcp_win!_Mtx_lock` at `0x18001b9fb`
- `msvcp_win!_Mtx_lock` at `0x18001b922`
- `msvcp_win!_Mtx_lock` at `0x18001b9fb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ba1a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ba56`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ba1a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ba56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char *v4; // rbx
  _QWORD *v5; // rcx
  char v6; // r14
  _QWORD *v7; // rax
  __int64 v8; // rdx
  Concurrency::details::platform *v9; // rcx
  unsigned __int32 v10; // eax

  v4 = (char *)this + 24;
  if ( _Mtx_lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24)) )
    goto LABEL_29;
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
    goto LABEL_24;
  v5 = (_QWORD *)*((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = v5[1];
      if ( (struct Concurrency::details::_CancellationTokenRegistration *)*v5 == a2 )
        break;
      v7 = v5;
      v5 = (_QWORD *)v5[1];
      if ( !v8 )
        goto LABEL_15;
    }
    if ( v7 )
      v7[1] = v8;
    else
      *((_QWORD *)this + 13) = v8;
    if ( !v5[1] )
      *((_QWORD *)this + 14) = v7;
    operator delete(v5, 0x10u);
LABEL_15:
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    v6 = 1;
  }
  _Mtx_unlock((_Mtx_t)v4);
  if ( !v6 )
    return;
  v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
  if ( v10 < 2
    || v10 - 2 < 2
    || v10 == Concurrency::details::platform::GetCurrentThreadId(v9)
    || _InterlockedExchange((volatile __int32 *)a2 + 4, 2) == 3 )
  {
    return;
  }
  v4 = (char *)a2 + 96;
  if ( _Mtx_lock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96)) )
  {
LABEL_29:
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x18001BA5CLL);
  }
  if ( *((_DWORD *)a2 + 43) == 0x7FFFFFFF )
  {
LABEL_24:
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  while ( !*((_BYTE *)a2 + 176) )
    _Cnd_wait(
      (struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24),
      (struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
  _Mtx_unlock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
}

```

## disassembly

```asm
0x18001b900  mov     [rsp+arg_8], rbx
0x18001b905  push    rbp
0x18001b906  push    rsi
0x18001b907  push    rdi
0x18001b908  push    r13
0x18001b90a  push    r14
0x18001b90c  sub     rsp, 20h
0x18001b910  mov     rdi, rdx
0x18001b913  mov     rsi, rcx
0x18001b916  lea     rbx, [rcx+18h]
0x18001b91a  mov     [rsp+48h+arg_10], rbx
0x18001b91f  mov     rcx, rbx; _Mtx_t
0x18001b922  call    cs:__imp__Mtx_lock
0x18001b928  test    eax, eax
0x18001b92a  jnz     loc_18001BA51
0x18001b930  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18001b937  jz      loc_18001BA0E
0x18001b93d  mov     rcx, [rsi+68h]; void *
0x18001b941  lea     ebp, [rax+2]
0x18001b944  lea     r13d, [rax+1]
0x18001b948  test    rcx, rcx
0x18001b94b  jnz     short loc_18001B952
0x18001b94d  mov     r14b, r13b
0x18001b950  jmp     short loc_18001B9B3
0x18001b952  xor     r14b, r14b
0x18001b955  xor     eax, eax
0x18001b957  mov     rdx, [rcx+8]
0x18001b95b  cmp     [rcx], rdi
0x18001b95e  jz      short loc_18001B96D
0x18001b960  mov     rax, rcx
0x18001b963  mov     rcx, rdx
0x18001b966  test    rdx, rdx
0x18001b969  jnz     short loc_18001B957
0x18001b96b  jmp     short loc_18001B991
0x18001b96d  test    rax, rax
0x18001b970  jnz     short loc_18001B978
0x18001b972  mov     [rsi+68h], rdx
0x18001b976  jmp     short loc_18001B97C
0x18001b978  mov     [rax+8], rdx
0x18001b97c  cmp     qword ptr [rcx+8], 0
0x18001b981  jnz     short loc_18001B987
0x18001b983  mov     [rsi+70h], rax
0x18001b987  mov     edx, 10h; unsigned __int64
0x18001b98c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b991  mov     eax, ebp
0x18001b993  xchg    eax, [rdi+10h]
0x18001b996  or      eax, 0FFFFFFFFh
0x18001b999  lock xadd [rdi+8], eax
0x18001b99e  cmp     eax, r13d
0x18001b9a1  jnz     short loc_18001B9B3
0x18001b9a3  mov     rax, [rdi]
0x18001b9a6  mov     rcx, rdi
0x18001b9a9  mov     rax, [rax+8]
0x18001b9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b2  nop
0x18001b9b3  mov     rcx, rbx; _Mtx_t
0x18001b9b6  call    cs:__imp__Mtx_unlock
0x18001b9bc  test    r14b, r14b
0x18001b9bf  jz      short loc_18001BA40
0x18001b9c1  xor     eax, eax
0x18001b9c3  lock cmpxchg [rdi+10h], r13d
0x18001b9c9  mov     ebx, eax
0x18001b9cb  jz      short loc_18001BA40
0x18001b9cd  mov     edx, eax
0x18001b9cf  test    eax, eax
0x18001b9d1  jz      short loc_18001BA40
0x18001b9d3  sub     edx, 1
0x18001b9d6  jz      short loc_18001BA40
0x18001b9d8  sub     edx, 1
0x18001b9db  jz      short loc_18001BA40
0x18001b9dd  cmp     edx, 1
0x18001b9e0  jz      short loc_18001BA40
0x18001b9e2  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18001b9e8  cmp     ebx, eax
0x18001b9ea  jz      short loc_18001BA40
0x18001b9ec  xchg    ebp, [rdi+10h]
0x18001b9ef  cmp     ebp, 3
0x18001b9f2  jz      short loc_18001BA40
0x18001b9f4  lea     rbx, [rdi+60h]
0x18001b9f8  mov     rcx, rbx; _Mtx_t
0x18001b9fb  call    cs:__imp__Mtx_lock
0x18001ba01  test    eax, eax
0x18001ba03  jnz     short loc_18001BA51
0x18001ba05  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18001ba0c  jnz     short loc_18001BA2E
0x18001ba0e  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18001ba15  mov     ecx, 6
0x18001ba1a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001ba20  int     3; Trap to Debugger
0x18001ba21  mov     rdx, rbx; _Mtx_t
0x18001ba24  lea     rcx, [rdi+18h]; _Cnd_t
0x18001ba28  call    cs:__imp__Cnd_wait
0x18001ba2e  cmp     byte ptr [rdi+0B0h], 0
0x18001ba35  jz      short loc_18001BA21
0x18001ba37  mov     rcx, rbx; _Mtx_t
0x18001ba3a  call    cs:__imp__Mtx_unlock
0x18001ba40  mov     rbx, [rsp+48h+arg_8]
0x18001ba45  add     rsp, 20h
0x18001ba49  pop     r14
0x18001ba4b  pop     r13
0x18001ba4d  pop     rdi
0x18001ba4e  pop     rsi
0x18001ba4f  pop     rbp
0x18001ba50  retn
0x18001ba51  mov     ecx, 5
0x18001ba56  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

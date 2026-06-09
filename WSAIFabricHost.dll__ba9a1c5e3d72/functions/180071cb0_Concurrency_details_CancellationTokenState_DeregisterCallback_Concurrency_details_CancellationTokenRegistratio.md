# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180071cb0`
- end: `0x180071e0d`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `349`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006f224`

## callees

- `0x180005140`
- `0x180071cb0`
- `0x180089010`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x180071dd8`
- `msvcp_win!_Cnd_wait` at `0x180071dd8`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180071d92`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180071d92`
- `msvcp_win!_Mtx_unlock` at `0x180071d66`
- `msvcp_win!_Mtx_unlock` at `0x180071dea`
- `msvcp_win!_Mtx_unlock` at `0x180071d66`
- `msvcp_win!_Mtx_unlock` at `0x180071dea`
- `msvcp_win!_Mtx_lock` at `0x180071cd2`
- `msvcp_win!_Mtx_lock` at `0x180071dab`
- `msvcp_win!_Mtx_lock` at `0x180071cd2`
- `msvcp_win!_Mtx_lock` at `0x180071dab`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180071dca`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180071e06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180071dca`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180071e06`

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
    JUMPOUT(0x180071E0CLL);
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
0x180071cb0  mov     [rsp+arg_8], rbx
0x180071cb5  push    rbp
0x180071cb6  push    rsi
0x180071cb7  push    rdi
0x180071cb8  push    r13
0x180071cba  push    r14
0x180071cbc  sub     rsp, 20h
0x180071cc0  mov     rdi, rdx
0x180071cc3  mov     rsi, rcx
0x180071cc6  lea     rbx, [rcx+18h]
0x180071cca  mov     [rsp+48h+arg_10], rbx
0x180071ccf  mov     rcx, rbx; _Mtx_t
0x180071cd2  call    cs:__imp__Mtx_lock
0x180071cd8  test    eax, eax
0x180071cda  jnz     loc_180071E01
0x180071ce0  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180071ce7  jz      loc_180071DBE
0x180071ced  mov     rcx, [rsi+68h]; void *
0x180071cf1  lea     ebp, [rax+2]
0x180071cf4  lea     r13d, [rax+1]
0x180071cf8  test    rcx, rcx
0x180071cfb  jnz     short loc_180071D02
0x180071cfd  mov     r14b, r13b
0x180071d00  jmp     short loc_180071D63
0x180071d02  xor     r14b, r14b
0x180071d05  xor     eax, eax
0x180071d07  mov     rdx, [rcx+8]
0x180071d0b  cmp     [rcx], rdi
0x180071d0e  jz      short loc_180071D1D
0x180071d10  mov     rax, rcx
0x180071d13  mov     rcx, rdx
0x180071d16  test    rdx, rdx
0x180071d19  jnz     short loc_180071D07
0x180071d1b  jmp     short loc_180071D41
0x180071d1d  test    rax, rax
0x180071d20  jnz     short loc_180071D28
0x180071d22  mov     [rsi+68h], rdx
0x180071d26  jmp     short loc_180071D2C
0x180071d28  mov     [rax+8], rdx
0x180071d2c  cmp     qword ptr [rcx+8], 0
0x180071d31  jnz     short loc_180071D37
0x180071d33  mov     [rsi+70h], rax
0x180071d37  mov     edx, 10h; unsigned __int64
0x180071d3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180071d41  mov     eax, ebp
0x180071d43  xchg    eax, [rdi+10h]
0x180071d46  or      eax, 0FFFFFFFFh
0x180071d49  lock xadd [rdi+8], eax
0x180071d4e  cmp     eax, r13d
0x180071d51  jnz     short loc_180071D63
0x180071d53  mov     rax, [rdi]
0x180071d56  mov     rcx, rdi
0x180071d59  mov     rax, [rax+8]
0x180071d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d62  nop
0x180071d63  mov     rcx, rbx; _Mtx_t
0x180071d66  call    cs:__imp__Mtx_unlock
0x180071d6c  test    r14b, r14b
0x180071d6f  jz      short loc_180071DF0
0x180071d71  xor     eax, eax
0x180071d73  lock cmpxchg [rdi+10h], r13d
0x180071d79  mov     ebx, eax
0x180071d7b  jz      short loc_180071DF0
0x180071d7d  mov     edx, eax
0x180071d7f  test    eax, eax
0x180071d81  jz      short loc_180071DF0
0x180071d83  sub     edx, 1
0x180071d86  jz      short loc_180071DF0
0x180071d88  sub     edx, 1
0x180071d8b  jz      short loc_180071DF0
0x180071d8d  cmp     edx, 1
0x180071d90  jz      short loc_180071DF0
0x180071d92  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180071d98  cmp     ebx, eax
0x180071d9a  jz      short loc_180071DF0
0x180071d9c  xchg    ebp, [rdi+10h]
0x180071d9f  cmp     ebp, 3
0x180071da2  jz      short loc_180071DF0
0x180071da4  lea     rbx, [rdi+60h]
0x180071da8  mov     rcx, rbx; _Mtx_t
0x180071dab  call    cs:__imp__Mtx_lock
0x180071db1  test    eax, eax
0x180071db3  jnz     short loc_180071E01
0x180071db5  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180071dbc  jnz     short loc_180071DDE
0x180071dbe  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180071dc5  mov     ecx, 6
0x180071dca  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180071dd0  int     3; Trap to Debugger
0x180071dd1  mov     rdx, rbx; _Mtx_t
0x180071dd4  lea     rcx, [rdi+18h]; _Cnd_t
0x180071dd8  call    cs:__imp__Cnd_wait
0x180071dde  cmp     byte ptr [rdi+0B0h], 0
0x180071de5  jz      short loc_180071DD1
0x180071de7  mov     rcx, rbx; _Mtx_t
0x180071dea  call    cs:__imp__Mtx_unlock
0x180071df0  mov     rbx, [rsp+48h+arg_8]
0x180071df5  add     rsp, 20h
0x180071df9  pop     r14
0x180071dfb  pop     r13
0x180071dfd  pop     rdi
0x180071dfe  pop     rsi
0x180071dff  pop     rbp
0x180071e00  retn
0x180071e01  mov     ecx, 5
0x180071e06  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

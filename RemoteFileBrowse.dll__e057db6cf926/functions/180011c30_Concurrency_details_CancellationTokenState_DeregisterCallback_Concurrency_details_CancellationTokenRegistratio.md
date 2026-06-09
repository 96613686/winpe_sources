# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180011c30`
- end: `0x180011d8d`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `349`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000fb74`

## callees

- `0x180002054`
- `0x180011c30`
- `0x180019010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180011d12`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180011d12`
- `msvcp_win!_Cnd_wait` at `0x180011d58`
- `msvcp_win!_Cnd_wait` at `0x180011d58`
- `msvcp_win!_Mtx_unlock` at `0x180011ce6`
- `msvcp_win!_Mtx_unlock` at `0x180011d6a`
- `msvcp_win!_Mtx_unlock` at `0x180011ce6`
- `msvcp_win!_Mtx_unlock` at `0x180011d6a`
- `msvcp_win!_Mtx_lock` at `0x180011c52`
- `msvcp_win!_Mtx_lock` at `0x180011d2b`
- `msvcp_win!_Mtx_lock` at `0x180011c52`
- `msvcp_win!_Mtx_lock` at `0x180011d2b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d4a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d86`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d4a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d86`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
    operator delete(v5);
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
    JUMPOUT(0x180011D8CLL);
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
0x180011c30  mov     [rsp+arg_8], rbx
0x180011c35  push    rbp
0x180011c36  push    rsi
0x180011c37  push    rdi
0x180011c38  push    r13
0x180011c3a  push    r14
0x180011c3c  sub     rsp, 20h
0x180011c40  mov     rdi, rdx
0x180011c43  mov     rsi, rcx
0x180011c46  lea     rbx, [rcx+18h]
0x180011c4a  mov     [rsp+48h+arg_10], rbx
0x180011c4f  mov     rcx, rbx; _Mtx_t
0x180011c52  call    cs:__imp__Mtx_lock
0x180011c58  test    eax, eax
0x180011c5a  jnz     loc_180011D81
0x180011c60  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180011c67  jz      loc_180011D3E
0x180011c6d  mov     rcx, [rsi+68h]; void *
0x180011c71  lea     ebp, [rax+2]
0x180011c74  lea     r13d, [rax+1]
0x180011c78  test    rcx, rcx
0x180011c7b  jnz     short loc_180011C82
0x180011c7d  mov     r14b, r13b
0x180011c80  jmp     short loc_180011CE3
0x180011c82  xor     r14b, r14b
0x180011c85  xor     eax, eax
0x180011c87  mov     rdx, [rcx+8]
0x180011c8b  cmp     [rcx], rdi
0x180011c8e  jz      short loc_180011C9D
0x180011c90  mov     rax, rcx
0x180011c93  mov     rcx, rdx
0x180011c96  test    rdx, rdx
0x180011c99  jnz     short loc_180011C87
0x180011c9b  jmp     short loc_180011CC1
0x180011c9d  test    rax, rax
0x180011ca0  jnz     short loc_180011CA8
0x180011ca2  mov     [rsi+68h], rdx
0x180011ca6  jmp     short loc_180011CAC
0x180011ca8  mov     [rax+8], rdx
0x180011cac  cmp     qword ptr [rcx+8], 0
0x180011cb1  jnz     short loc_180011CB7
0x180011cb3  mov     [rsi+70h], rax
0x180011cb7  mov     edx, 10h; unsigned __int64
0x180011cbc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011cc1  mov     eax, ebp
0x180011cc3  xchg    eax, [rdi+10h]
0x180011cc6  or      eax, 0FFFFFFFFh
0x180011cc9  lock xadd [rdi+8], eax
0x180011cce  cmp     eax, r13d
0x180011cd1  jnz     short loc_180011CE3
0x180011cd3  mov     rax, [rdi]
0x180011cd6  mov     rcx, rdi
0x180011cd9  mov     rax, [rax+8]
0x180011cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce2  nop
0x180011ce3  mov     rcx, rbx; _Mtx_t
0x180011ce6  call    cs:__imp__Mtx_unlock
0x180011cec  test    r14b, r14b
0x180011cef  jz      short loc_180011D70
0x180011cf1  xor     eax, eax
0x180011cf3  lock cmpxchg [rdi+10h], r13d
0x180011cf9  mov     ebx, eax
0x180011cfb  jz      short loc_180011D70
0x180011cfd  mov     edx, eax
0x180011cff  test    eax, eax
0x180011d01  jz      short loc_180011D70
0x180011d03  sub     edx, 1
0x180011d06  jz      short loc_180011D70
0x180011d08  sub     edx, 1
0x180011d0b  jz      short loc_180011D70
0x180011d0d  cmp     edx, 1
0x180011d10  jz      short loc_180011D70
0x180011d12  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180011d18  cmp     ebx, eax
0x180011d1a  jz      short loc_180011D70
0x180011d1c  xchg    ebp, [rdi+10h]
0x180011d1f  cmp     ebp, 3
0x180011d22  jz      short loc_180011D70
0x180011d24  lea     rbx, [rdi+60h]
0x180011d28  mov     rcx, rbx; _Mtx_t
0x180011d2b  call    cs:__imp__Mtx_lock
0x180011d31  test    eax, eax
0x180011d33  jnz     short loc_180011D81
0x180011d35  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180011d3c  jnz     short loc_180011D5E
0x180011d3e  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180011d45  mov     ecx, 6
0x180011d4a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180011d50  int     3; Trap to Debugger
0x180011d51  mov     rdx, rbx; _Mtx_t
0x180011d54  lea     rcx, [rdi+18h]; _Cnd_t
0x180011d58  call    cs:__imp__Cnd_wait
0x180011d5e  cmp     byte ptr [rdi+0B0h], 0
0x180011d65  jz      short loc_180011D51
0x180011d67  mov     rcx, rbx; _Mtx_t
0x180011d6a  call    cs:__imp__Mtx_unlock
0x180011d70  mov     rbx, [rsp+48h+arg_8]
0x180011d75  add     rsp, 20h
0x180011d79  pop     r14
0x180011d7b  pop     r13
0x180011d7d  pop     rdi
0x180011d7e  pop     rsi
0x180011d7f  pop     rbp
0x180011d80  retn
0x180011d81  mov     ecx, 5
0x180011d86  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

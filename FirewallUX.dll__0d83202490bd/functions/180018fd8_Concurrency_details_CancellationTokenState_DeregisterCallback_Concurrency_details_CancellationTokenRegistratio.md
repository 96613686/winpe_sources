# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180018fd8`
- end: `0x180019135`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `349`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800163ac`

## callees

- `0x1800025f8`
- `0x180018fd8`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800190f2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001912e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800190f2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001912e`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800190ba`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800190ba`
- `msvcp_win!_Cnd_wait` at `0x180019100`
- `msvcp_win!_Cnd_wait` at `0x180019100`
- `msvcp_win!_Mtx_unlock` at `0x18001908e`
- `msvcp_win!_Mtx_unlock` at `0x180019112`
- `msvcp_win!_Mtx_unlock` at `0x18001908e`
- `msvcp_win!_Mtx_unlock` at `0x180019112`
- `msvcp_win!_Mtx_lock` at `0x180018ffa`
- `msvcp_win!_Mtx_lock` at `0x1800190d3`
- `msvcp_win!_Mtx_lock` at `0x180018ffa`
- `msvcp_win!_Mtx_lock` at `0x1800190d3`

## pseudocode

```c
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
    JUMPOUT(0x180019134LL);
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
0x180018fd8  mov     [rsp+arg_8], rbx
0x180018fdd  push    rbp
0x180018fde  push    rsi
0x180018fdf  push    rdi
0x180018fe0  push    r13
0x180018fe2  push    r14
0x180018fe4  sub     rsp, 20h
0x180018fe8  mov     rdi, rdx
0x180018feb  mov     rsi, rcx
0x180018fee  lea     rbx, [rcx+18h]
0x180018ff2  mov     [rsp+48h+arg_10], rbx
0x180018ff7  mov     rcx, rbx; _Mtx_t
0x180018ffa  call    cs:__imp__Mtx_lock
0x180019000  test    eax, eax
0x180019002  jnz     loc_180019129
0x180019008  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18001900f  jz      loc_1800190E6
0x180019015  mov     rcx, [rsi+68h]; void *
0x180019019  lea     ebp, [rax+2]
0x18001901c  lea     r13d, [rax+1]
0x180019020  test    rcx, rcx
0x180019023  jnz     short loc_18001902A
0x180019025  mov     r14b, r13b
0x180019028  jmp     short loc_18001908B
0x18001902a  xor     r14b, r14b
0x18001902d  xor     eax, eax
0x18001902f  mov     rdx, [rcx+8]
0x180019033  cmp     [rcx], rdi
0x180019036  jz      short loc_180019045
0x180019038  mov     rax, rcx
0x18001903b  mov     rcx, rdx
0x18001903e  test    rdx, rdx
0x180019041  jnz     short loc_18001902F
0x180019043  jmp     short loc_180019069
0x180019045  test    rax, rax
0x180019048  jnz     short loc_180019050
0x18001904a  mov     [rsi+68h], rdx
0x18001904e  jmp     short loc_180019054
0x180019050  mov     [rax+8], rdx
0x180019054  cmp     qword ptr [rcx+8], 0
0x180019059  jnz     short loc_18001905F
0x18001905b  mov     [rsi+70h], rax
0x18001905f  mov     edx, 10h; unsigned __int64
0x180019064  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019069  mov     eax, ebp
0x18001906b  xchg    eax, [rdi+10h]
0x18001906e  or      eax, 0FFFFFFFFh
0x180019071  lock xadd [rdi+8], eax
0x180019076  cmp     eax, r13d
0x180019079  jnz     short loc_18001908B
0x18001907b  mov     rax, [rdi]
0x18001907e  mov     rcx, rdi
0x180019081  mov     rax, [rax+8]
0x180019085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001908a  nop
0x18001908b  mov     rcx, rbx; _Mtx_t
0x18001908e  call    cs:__imp__Mtx_unlock
0x180019094  test    r14b, r14b
0x180019097  jz      short loc_180019118
0x180019099  xor     eax, eax
0x18001909b  lock cmpxchg [rdi+10h], r13d
0x1800190a1  mov     ebx, eax
0x1800190a3  jz      short loc_180019118
0x1800190a5  mov     edx, eax
0x1800190a7  test    eax, eax
0x1800190a9  jz      short loc_180019118
0x1800190ab  sub     edx, 1
0x1800190ae  jz      short loc_180019118
0x1800190b0  sub     edx, 1
0x1800190b3  jz      short loc_180019118
0x1800190b5  cmp     edx, 1
0x1800190b8  jz      short loc_180019118
0x1800190ba  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1800190c0  cmp     ebx, eax
0x1800190c2  jz      short loc_180019118
0x1800190c4  xchg    ebp, [rdi+10h]
0x1800190c7  cmp     ebp, 3
0x1800190ca  jz      short loc_180019118
0x1800190cc  lea     rbx, [rdi+60h]
0x1800190d0  mov     rcx, rbx; _Mtx_t
0x1800190d3  call    cs:__imp__Mtx_lock
0x1800190d9  test    eax, eax
0x1800190db  jnz     short loc_180019129
0x1800190dd  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800190e4  jnz     short loc_180019106
0x1800190e6  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x1800190ed  mov     ecx, 6
0x1800190f2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800190f8  int     3; Trap to Debugger
0x1800190f9  mov     rdx, rbx; _Mtx_t
0x1800190fc  lea     rcx, [rdi+18h]; _Cnd_t
0x180019100  call    cs:__imp__Cnd_wait
0x180019106  cmp     byte ptr [rdi+0B0h], 0
0x18001910d  jz      short loc_1800190F9
0x18001910f  mov     rcx, rbx; _Mtx_t
0x180019112  call    cs:__imp__Mtx_unlock
0x180019118  mov     rbx, [rsp+48h+arg_8]
0x18001911d  add     rsp, 20h
0x180019121  pop     r14
0x180019123  pop     r13
0x180019125  pop     rdi
0x180019126  pop     rsi
0x180019127  pop     rbp
0x180019128  retn
0x180019129  mov     ecx, 5
0x18001912e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

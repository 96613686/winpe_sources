# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x18001c400`
- end: `0x18001c6aa`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b0bc`
- `0x1800316e4`
- `0x18005b1a8`

## callees

- `0x180006108`
- `0x18001c400`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001c5ac`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001c5ac`
- `msvcp_win!_Mtx_unlock` at `0x18001c59d`
- `msvcp_win!_Mtx_unlock` at `0x18001c620`
- `msvcp_win!_Mtx_unlock` at `0x18001c59d`
- `msvcp_win!_Mtx_unlock` at `0x18001c620`
- `msvcp_win!_Mtx_lock` at `0x18001c535`
- `msvcp_win!_Mtx_lock` at `0x18001c5e3`
- `msvcp_win!_Mtx_lock` at `0x18001c535`
- `msvcp_win!_Mtx_lock` at `0x18001c5e3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001c5f2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001c60f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001c5f2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001c60f`
- `msvcp_win!_Cnd_broadcast` at `0x18001c62a`
- `msvcp_win!_Cnd_broadcast` at `0x18001c62a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation(__int64 a1, __int64 *a2)
{
  volatile signed __int32 *v4; // rdi
  char v5; // r12
  __int64 v6; // rsi
  Concurrency::details::platform *v7; // rcx
  char *v8; // rbx
  struct _Mtx_internal_imp_t *v9; // r14
  __int64 v10; // rsi
  char **v11; // rax
  int result; // eax
  signed __int32 CurrentThreadId; // esi
  signed __int32 v14; // eax
  volatile signed __int32 *v15; // rcx

  v4 = (volatile signed __int32 *)a2[1];
  v5 = 0;
  if ( v4 )
  {
    v6 = *a2;
    _InterlockedIncrement(v4 + 3);
  }
  else
  {
    v4 = 0;
    v6 = 0;
  }
  v8 = (char *)operator new(0xD0u);
  *(_QWORD *)v8 = &Concurrency::details::_RefCounter::`vftable';
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 4) = 3;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 4) = 0;
  *(_OWORD *)(v8 + 40) = 0;
  *(_OWORD *)(v8 + 56) = 0;
  *(_OWORD *)(v8 + 72) = 0;
  *((_QWORD *)v8 + 11) = 0;
  v9 = (struct _Mtx_internal_imp_t *)(v8 + 96);
  *((_QWORD *)v8 + 12) = 2;
  *(_OWORD *)(v8 + 120) = 0;
  *(_OWORD *)(v8 + 136) = 0;
  *(_OWORD *)(v8 + 152) = 0;
  *((_QWORD *)v8 + 13) = 0;
  *((_QWORD *)v8 + 14) = 0;
  *((_DWORD *)v8 + 42) = -1;
  *((_DWORD *)v8 + 43) = 0;
  v8[176] = 0;
  *((_QWORD *)v8 + 23) = 0;
  *(_QWORD *)v8 = &Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable';
  *((_QWORD *)v8 + 24) = 0;
  *((_QWORD *)v8 + 25) = 0;
  if ( v4 )
  {
    *((_QWORD *)v8 + 24) = v6;
    *((_QWORD *)v8 + 25) = v4;
    _InterlockedIncrement(v4 + 3);
  }
  *(_QWORD *)(a1 + 128) = v8;
  v10 = *(_QWORD *)(a1 + 120);
  _InterlockedExchange((volatile __int32 *)v8 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  *((_QWORD *)v8 + 23) = v10;
  if ( *(_DWORD *)(v10 + 16) )
    goto LABEL_17;
  if ( _Mtx_lock((_Mtx_t)(v10 + 24)) )
    goto LABEL_22;
  if ( *(_DWORD *)(v10 + 100) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v10 + 100) = 2147483646;
    goto LABEL_25;
  }
  if ( *(_DWORD *)(v10 + 16) )
  {
    v5 = 1;
  }
  else
  {
    v11 = (char **)operator new(0x10u);
    *v11 = v8;
    v11[1] = 0;
    if ( *(_QWORD *)(v10 + 104) )
      *(_QWORD *)(*(_QWORD *)(v10 + 112) + 8LL) = v11;
    else
      *(_QWORD *)(v10 + 104) = v11;
    *(_QWORD *)(v10 + 112) = v11;
  }
  result = _Mtx_unlock((_Mtx_t)(v10 + 24));
  if ( v5 )
  {
LABEL_17:
    CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(v7);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
      v14 = _InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v14 )
        CurrentThreadId = v14;
      if ( CurrentThreadId == 2 )
      {
        if ( _Mtx_lock(v9) )
        {
LABEL_22:
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( *((_DWORD *)v8 + 43) == 0x7FFFFFFF )
        {
          *((_DWORD *)v8 + 43) = 2147483646;
LABEL_25:
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        v8[176] = 1;
        _Mtx_unlock(v9);
        _Cnd_broadcast((_Cnd_t)(v8 + 24));
      }
    }
    result = _InterlockedDecrement((volatile signed __int32 *)v8 + 2);
    if ( !result )
      result = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  if ( v4 )
  {
    result = _InterlockedDecrement(v4 + 3);
    if ( !result )
      result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  v15 = (volatile signed __int32 *)a2[1];
  if ( v15 )
  {
    result = _InterlockedDecrement(v15 + 3);
    if ( !result )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
  }
  return result;
}

```

## disassembly

```asm
0x18001c400  mov     rax, rsp
0x18001c403  mov     [rax+18h], rbx
0x18001c407  mov     [rax+10h], rdx
0x18001c40b  push    rbp
0x18001c40c  push    rsi
0x18001c40d  push    rdi
0x18001c40e  push    r12
0x18001c410  push    r13
0x18001c412  push    r14
0x18001c414  push    r15
0x18001c416  sub     rsp, 30h
0x18001c41a  mov     r15, rdx
0x18001c41d  mov     rbp, rcx
0x18001c420  xorps   xmm0, xmm0
0x18001c423  movdqu  xmmword ptr [rax-48h], xmm0
0x18001c428  mov     rdi, [rdx+8]
0x18001c42c  xor     r12d, r12d
0x18001c42f  test    rdi, rdi
0x18001c432  jz      short loc_18001C445
0x18001c434  mov     rsi, [rdx]
0x18001c437  mov     [rax-48h], rsi
0x18001c43b  mov     [rax-40h], rdi
0x18001c43f  lock inc dword ptr [rdi+0Ch]
0x18001c443  jmp     short loc_18001C44F
0x18001c445  mov     rdi, [rsp+68h+var_40]
0x18001c44a  mov     rsi, [rsp+68h+var_48]
0x18001c44f  mov     ecx, 0D0h; Size
0x18001c454  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c459  mov     rbx, rax
0x18001c45c  mov     [rsp+68h+arg_0], rax
0x18001c461  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x18001c468  mov     [rbx], rax
0x18001c46b  mov     dword ptr [rbx+8], 1
0x18001c472  mov     dword ptr [rbx+10h], 3
0x18001c479  mov     [rbx+18h], r12
0x18001c47d  mov     [rbx+20h], r12
0x18001c481  xorps   xmm0, xmm0
0x18001c484  xor     eax, eax
0x18001c486  movups  xmmword ptr [rbx+28h], xmm0
0x18001c48a  movups  xmmword ptr [rbx+38h], xmm0
0x18001c48e  movups  xmmword ptr [rbx+48h], xmm0
0x18001c492  mov     [rbx+58h], rax
0x18001c496  lea     r14, [rbx+60h]
0x18001c49a  mov     qword ptr [r14], 2
0x18001c4a1  movups  xmmword ptr [r14+18h], xmm0
0x18001c4a6  movups  xmmword ptr [r14+28h], xmm0
0x18001c4ab  movups  xmmword ptr [r14+38h], xmm0
0x18001c4b0  mov     [r14+8], r12
0x18001c4b4  mov     [r14+10h], r12
0x18001c4b8  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x18001c4c0  mov     [r14+4Ch], r12d
0x18001c4c4  mov     [rbx+0B0h], r12b
0x18001c4cb  mov     [rbx+0B8h], r12
0x18001c4d2  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable'
0x18001c4d9  mov     [rbx], rax
0x18001c4dc  mov     [rbx+0C0h], r12
0x18001c4e3  mov     [rbx+0C8h], r12
0x18001c4ea  test    rdi, rdi
0x18001c4ed  jz      short loc_18001C501
0x18001c4ef  mov     [rbx+0C0h], rsi
0x18001c4f6  mov     [rbx+0C8h], rdi
0x18001c4fd  lock inc dword ptr [rdi+0Ch]
0x18001c501  mov     [rbp+80h], rbx
0x18001c508  mov     rsi, [rbp+78h]
0x18001c50c  mov     eax, r12d
0x18001c50f  xchg    eax, [rbx+10h]
0x18001c512  lock inc dword ptr [rbx+8]
0x18001c516  mov     [rbx+0B8h], rsi
0x18001c51d  mov     eax, [rsi+10h]
0x18001c520  nop
0x18001c521  test    eax, eax
0x18001c523  jnz     loc_18001C5AC
0x18001c529  lea     rbp, [rsi+18h]
0x18001c52d  mov     [rsp+68h+arg_0], rbp
0x18001c532  mov     rcx, rbp; _Mtx_t
0x18001c535  call    cs:__imp__Mtx_lock
0x18001c53b  test    eax, eax
0x18001c53d  jnz     loc_18001C5ED
0x18001c543  mov     eax, [rbp+4Ch]
0x18001c546  cmp     eax, 7FFFFFFFh
0x18001c54b  jnz     short loc_18001C557
0x18001c54d  dec     eax
0x18001c54f  mov     [rbp+4Ch], eax
0x18001c552  jmp     loc_18001C60A
0x18001c557  mov     eax, [rsi+10h]
0x18001c55a  nop
0x18001c55b  test    eax, eax
0x18001c55d  jz      short loc_18001C564
0x18001c55f  mov     r12b, 1
0x18001c562  jmp     short loc_18001C59A
0x18001c564  mov     ecx, 10h; Size
0x18001c569  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c56e  mov     rcx, rax
0x18001c571  mov     [rsp+68h+arg_0], rax
0x18001c576  mov     [rax], rbx
0x18001c579  mov     qword ptr [rax+8], 0
0x18001c581  cmp     qword ptr [rsi+68h], 0
0x18001c586  jnz     short loc_18001C58E
0x18001c588  mov     [rsi+68h], rax
0x18001c58c  jmp     short loc_18001C596
0x18001c58e  mov     rax, [rsi+70h]
0x18001c592  mov     [rax+8], rcx
0x18001c596  mov     [rsi+70h], rcx
0x18001c59a  mov     rcx, rbp; _Mtx_t
0x18001c59d  call    cs:__imp__Mtx_unlock
0x18001c5a3  test    r12b, r12b
0x18001c5a6  jz      loc_18001C64F
0x18001c5ac  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18001c5b2  mov     esi, eax
0x18001c5b4  xor     eax, eax
0x18001c5b6  lock cmpxchg [rbx+10h], esi
0x18001c5bb  jnz     short loc_18001C630
0x18001c5bd  mov     rcx, [rbx]
0x18001c5c0  mov     rax, [rcx+10h]
0x18001c5c4  mov     rcx, rbx
0x18001c5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5cc  mov     eax, esi
0x18001c5ce  mov     ecx, 3
0x18001c5d3  lock cmpxchg [rbx+10h], ecx
0x18001c5d8  cmovnz  esi, eax
0x18001c5db  cmp     esi, 2
0x18001c5de  jnz     short loc_18001C630
0x18001c5e0  mov     rcx, r14; _Mtx_t
0x18001c5e3  call    cs:__imp__Mtx_lock
0x18001c5e9  test    eax, eax
0x18001c5eb  jz      short loc_18001C5F9
0x18001c5ed  mov     ecx, 5
0x18001c5f2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001c5f8  int     3; Trap to Debugger
0x18001c5f9  mov     eax, [r14+4Ch]
0x18001c5fd  cmp     eax, 7FFFFFFFh
0x18001c602  jnz     short loc_18001C616
0x18001c604  dec     eax
0x18001c606  mov     [r14+4Ch], eax
0x18001c60a  mov     ecx, 6
0x18001c60f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001c615  int     3; Trap to Debugger
0x18001c616  mov     byte ptr [rbx+0B0h], 1
0x18001c61d  mov     rcx, r14; _Mtx_t
0x18001c620  call    cs:__imp__Mtx_unlock
0x18001c626  lea     rcx, [rbx+18h]; _Cnd_t
0x18001c62a  call    cs:__imp__Cnd_broadcast
0x18001c630  or      esi, 0FFFFFFFFh
0x18001c633  mov     eax, esi
0x18001c635  lock xadd [rbx+8], eax
0x18001c63a  add     eax, esi
0x18001c63c  jnz     short loc_18001C652
0x18001c63e  mov     rax, [rbx]
0x18001c641  mov     rcx, rbx
0x18001c644  mov     rax, [rax+8]
0x18001c648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c64d  jmp     short loc_18001C652
0x18001c64f  or      esi, 0FFFFFFFFh
0x18001c652  test    rdi, rdi
0x18001c655  jz      short loc_18001C672
0x18001c657  mov     eax, esi
0x18001c659  lock xadd [rdi+0Ch], eax
0x18001c65e  add     eax, esi
0x18001c660  jnz     short loc_18001C672
0x18001c662  mov     rax, [rdi]
0x18001c665  mov     rcx, rdi
0x18001c668  mov     rax, [rax+8]
0x18001c66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c671  nop
0x18001c672  mov     rcx, [r15+8]
0x18001c676  test    rcx, rcx
0x18001c679  jz      short loc_18001C692
0x18001c67b  mov     eax, esi
0x18001c67d  lock xadd [rcx+0Ch], eax
0x18001c682  add     eax, esi
0x18001c684  jnz     short loc_18001C692
0x18001c686  mov     rax, [rcx]
0x18001c689  mov     rax, [rax+8]
0x18001c68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c692  mov     rbx, [rsp+68h+arg_10]
0x18001c69a  add     rsp, 30h
0x18001c69e  pop     r15
0x18001c6a0  pop     r14
0x18001c6a2  pop     r13
0x18001c6a4  pop     r12
0x18001c6a6  pop     rdi
0x18001c6a7  pop     rsi
0x18001c6a8  pop     rbp
0x18001c6a9  retn
```

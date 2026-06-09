# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x180012454`
- end: `0x1800126fe`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `682`
- prototype: `int __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e664`

## callees

- `0x18000208c`
- `0x180012454`
- `0x180019010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180012600`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180012600`
- `msvcp_win!_Cnd_broadcast` at `0x18001267e`
- `msvcp_win!_Cnd_broadcast` at `0x18001267e`
- `msvcp_win!_Mtx_unlock` at `0x1800125f1`
- `msvcp_win!_Mtx_unlock` at `0x180012674`
- `msvcp_win!_Mtx_unlock` at `0x1800125f1`
- `msvcp_win!_Mtx_unlock` at `0x180012674`
- `msvcp_win!_Mtx_lock` at `0x180012589`
- `msvcp_win!_Mtx_lock` at `0x180012637`
- `msvcp_win!_Mtx_lock` at `0x180012589`
- `msvcp_win!_Mtx_lock` at `0x180012637`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012646`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012663`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012646`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012663`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x180012454  mov     rax, rsp
0x180012457  mov     [rax+18h], rbx
0x18001245b  mov     [rax+10h], rdx
0x18001245f  push    rbp
0x180012460  push    rsi
0x180012461  push    rdi
0x180012462  push    r12
0x180012464  push    r13
0x180012466  push    r14
0x180012468  push    r15
0x18001246a  sub     rsp, 30h
0x18001246e  mov     r15, rdx
0x180012471  mov     rbp, rcx
0x180012474  xorps   xmm0, xmm0
0x180012477  movdqu  xmmword ptr [rax-48h], xmm0
0x18001247c  mov     rdi, [rdx+8]
0x180012480  xor     r12d, r12d
0x180012483  test    rdi, rdi
0x180012486  jz      short loc_180012499
0x180012488  mov     rsi, [rdx]
0x18001248b  mov     [rax-48h], rsi
0x18001248f  mov     [rax-40h], rdi
0x180012493  lock inc dword ptr [rdi+0Ch]
0x180012497  jmp     short loc_1800124A3
0x180012499  mov     rdi, [rsp+68h+var_40]
0x18001249e  mov     rsi, [rsp+68h+var_48]
0x1800124a3  mov     ecx, 0D0h; Size
0x1800124a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800124ad  mov     rbx, rax
0x1800124b0  mov     [rsp+68h+arg_0], rax
0x1800124b5  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x1800124bc  mov     [rbx], rax
0x1800124bf  mov     dword ptr [rbx+8], 1
0x1800124c6  mov     dword ptr [rbx+10h], 3
0x1800124cd  mov     [rbx+18h], r12
0x1800124d1  mov     [rbx+20h], r12
0x1800124d5  xorps   xmm0, xmm0
0x1800124d8  xor     eax, eax
0x1800124da  movups  xmmword ptr [rbx+28h], xmm0
0x1800124de  movups  xmmword ptr [rbx+38h], xmm0
0x1800124e2  movups  xmmword ptr [rbx+48h], xmm0
0x1800124e6  mov     [rbx+58h], rax
0x1800124ea  lea     r14, [rbx+60h]
0x1800124ee  mov     qword ptr [r14], 2
0x1800124f5  movups  xmmword ptr [r14+18h], xmm0
0x1800124fa  movups  xmmword ptr [r14+28h], xmm0
0x1800124ff  movups  xmmword ptr [r14+38h], xmm0
0x180012504  mov     [r14+8], r12
0x180012508  mov     [r14+10h], r12
0x18001250c  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x180012514  mov     [r14+4Ch], r12d
0x180012518  mov     [rbx+0B0h], r12b
0x18001251f  mov     [rbx+0B8h], r12
0x180012526  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable'
0x18001252d  mov     [rbx], rax
0x180012530  mov     [rbx+0C0h], r12
0x180012537  mov     [rbx+0C8h], r12
0x18001253e  test    rdi, rdi
0x180012541  jz      short loc_180012555
0x180012543  mov     [rbx+0C0h], rsi
0x18001254a  mov     [rbx+0C8h], rdi
0x180012551  lock inc dword ptr [rdi+0Ch]
0x180012555  mov     [rbp+80h], rbx
0x18001255c  mov     rsi, [rbp+78h]
0x180012560  mov     eax, r12d
0x180012563  xchg    eax, [rbx+10h]
0x180012566  lock inc dword ptr [rbx+8]
0x18001256a  mov     [rbx+0B8h], rsi
0x180012571  mov     eax, [rsi+10h]
0x180012574  nop
0x180012575  test    eax, eax
0x180012577  jnz     loc_180012600
0x18001257d  lea     rbp, [rsi+18h]
0x180012581  mov     [rsp+68h+arg_0], rbp
0x180012586  mov     rcx, rbp; _Mtx_t
0x180012589  call    cs:__imp__Mtx_lock
0x18001258f  test    eax, eax
0x180012591  jnz     loc_180012641
0x180012597  mov     eax, [rbp+4Ch]
0x18001259a  cmp     eax, 7FFFFFFFh
0x18001259f  jnz     short loc_1800125AB
0x1800125a1  dec     eax
0x1800125a3  mov     [rbp+4Ch], eax
0x1800125a6  jmp     loc_18001265E
0x1800125ab  mov     eax, [rsi+10h]
0x1800125ae  nop
0x1800125af  test    eax, eax
0x1800125b1  jz      short loc_1800125B8
0x1800125b3  mov     r12b, 1
0x1800125b6  jmp     short loc_1800125EE
0x1800125b8  mov     ecx, 10h; Size
0x1800125bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800125c2  mov     rcx, rax
0x1800125c5  mov     [rsp+68h+arg_0], rax
0x1800125ca  mov     [rax], rbx
0x1800125cd  mov     qword ptr [rax+8], 0
0x1800125d5  cmp     qword ptr [rsi+68h], 0
0x1800125da  jnz     short loc_1800125E2
0x1800125dc  mov     [rsi+68h], rax
0x1800125e0  jmp     short loc_1800125EA
0x1800125e2  mov     rax, [rsi+70h]
0x1800125e6  mov     [rax+8], rcx
0x1800125ea  mov     [rsi+70h], rcx
0x1800125ee  mov     rcx, rbp; _Mtx_t
0x1800125f1  call    cs:__imp__Mtx_unlock
0x1800125f7  test    r12b, r12b
0x1800125fa  jz      loc_1800126A3
0x180012600  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180012606  mov     esi, eax
0x180012608  xor     eax, eax
0x18001260a  lock cmpxchg [rbx+10h], esi
0x18001260f  jnz     short loc_180012684
0x180012611  mov     rcx, [rbx]
0x180012614  mov     rax, [rcx+10h]
0x180012618  mov     rcx, rbx
0x18001261b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012620  mov     eax, esi
0x180012622  mov     ecx, 3
0x180012627  lock cmpxchg [rbx+10h], ecx
0x18001262c  cmovnz  esi, eax
0x18001262f  cmp     esi, 2
0x180012632  jnz     short loc_180012684
0x180012634  mov     rcx, r14; _Mtx_t
0x180012637  call    cs:__imp__Mtx_lock
0x18001263d  test    eax, eax
0x18001263f  jz      short loc_18001264D
0x180012641  mov     ecx, 5
0x180012646  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001264c  int     3; Trap to Debugger
0x18001264d  mov     eax, [r14+4Ch]
0x180012651  cmp     eax, 7FFFFFFFh
0x180012656  jnz     short loc_18001266A
0x180012658  dec     eax
0x18001265a  mov     [r14+4Ch], eax
0x18001265e  mov     ecx, 6
0x180012663  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012669  int     3; Trap to Debugger
0x18001266a  mov     byte ptr [rbx+0B0h], 1
0x180012671  mov     rcx, r14; _Mtx_t
0x180012674  call    cs:__imp__Mtx_unlock
0x18001267a  lea     rcx, [rbx+18h]; _Cnd_t
0x18001267e  call    cs:__imp__Cnd_broadcast
0x180012684  or      esi, 0FFFFFFFFh
0x180012687  mov     eax, esi
0x180012689  lock xadd [rbx+8], eax
0x18001268e  add     eax, esi
0x180012690  jnz     short loc_1800126A6
0x180012692  mov     rax, [rbx]
0x180012695  mov     rcx, rbx
0x180012698  mov     rax, [rax+8]
0x18001269c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126a1  jmp     short loc_1800126A6
0x1800126a3  or      esi, 0FFFFFFFFh
0x1800126a6  test    rdi, rdi
0x1800126a9  jz      short loc_1800126C6
0x1800126ab  mov     eax, esi
0x1800126ad  lock xadd [rdi+0Ch], eax
0x1800126b2  add     eax, esi
0x1800126b4  jnz     short loc_1800126C6
0x1800126b6  mov     rax, [rdi]
0x1800126b9  mov     rcx, rdi
0x1800126bc  mov     rax, [rax+8]
0x1800126c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126c5  nop
0x1800126c6  mov     rcx, [r15+8]
0x1800126ca  test    rcx, rcx
0x1800126cd  jz      short loc_1800126E6
0x1800126cf  mov     eax, esi
0x1800126d1  lock xadd [rcx+0Ch], eax
0x1800126d6  add     eax, esi
0x1800126d8  jnz     short loc_1800126E6
0x1800126da  mov     rax, [rcx]
0x1800126dd  mov     rax, [rax+8]
0x1800126e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126e6  mov     rbx, [rsp+68h+arg_10]
0x1800126ee  add     rsp, 30h
0x1800126f2  pop     r15
0x1800126f4  pop     r14
0x1800126f6  pop     r13
0x1800126f8  pop     r12
0x1800126fa  pop     rdi
0x1800126fb  pop     rsi
0x1800126fc  pop     rbp
0x1800126fd  retn
```

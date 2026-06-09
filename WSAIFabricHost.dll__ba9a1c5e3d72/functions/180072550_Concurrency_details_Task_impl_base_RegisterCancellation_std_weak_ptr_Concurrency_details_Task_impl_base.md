# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x180072550`
- end: `0x1800727fa`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c52c`

## callees

- `0x180007ad0`
- `0x180072550`
- `0x180089010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800726fc`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800726fc`
- `msvcp_win!_Cnd_broadcast` at `0x18007277a`
- `msvcp_win!_Cnd_broadcast` at `0x18007277a`
- `msvcp_win!_Mtx_unlock` at `0x1800726ed`
- `msvcp_win!_Mtx_unlock` at `0x180072770`
- `msvcp_win!_Mtx_unlock` at `0x1800726ed`
- `msvcp_win!_Mtx_unlock` at `0x180072770`
- `msvcp_win!_Mtx_lock` at `0x180072685`
- `msvcp_win!_Mtx_lock` at `0x180072733`
- `msvcp_win!_Mtx_lock` at `0x180072685`
- `msvcp_win!_Mtx_lock` at `0x180072733`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180072742`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007275f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180072742`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007275f`

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
0x180072550  mov     rax, rsp
0x180072553  mov     [rax+18h], rbx
0x180072557  mov     [rax+10h], rdx
0x18007255b  push    rbp
0x18007255c  push    rsi
0x18007255d  push    rdi
0x18007255e  push    r12
0x180072560  push    r13
0x180072562  push    r14
0x180072564  push    r15
0x180072566  sub     rsp, 30h
0x18007256a  mov     r15, rdx
0x18007256d  mov     rbp, rcx
0x180072570  xorps   xmm0, xmm0
0x180072573  movdqu  xmmword ptr [rax-48h], xmm0
0x180072578  mov     rdi, [rdx+8]
0x18007257c  xor     r12d, r12d
0x18007257f  test    rdi, rdi
0x180072582  jz      short loc_180072595
0x180072584  mov     rsi, [rdx]
0x180072587  mov     [rax-48h], rsi
0x18007258b  mov     [rax-40h], rdi
0x18007258f  lock inc dword ptr [rdi+0Ch]
0x180072593  jmp     short loc_18007259F
0x180072595  mov     rdi, [rsp+68h+var_40]
0x18007259a  mov     rsi, [rsp+68h+var_48]
0x18007259f  mov     ecx, 0D0h; Size
0x1800725a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800725a9  mov     rbx, rax
0x1800725ac  mov     [rsp+68h+arg_0], rax
0x1800725b1  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x1800725b8  mov     [rbx], rax
0x1800725bb  mov     dword ptr [rbx+8], 1
0x1800725c2  mov     dword ptr [rbx+10h], 3
0x1800725c9  mov     [rbx+18h], r12
0x1800725cd  mov     [rbx+20h], r12
0x1800725d1  xorps   xmm0, xmm0
0x1800725d4  xor     eax, eax
0x1800725d6  movups  xmmword ptr [rbx+28h], xmm0
0x1800725da  movups  xmmword ptr [rbx+38h], xmm0
0x1800725de  movups  xmmword ptr [rbx+48h], xmm0
0x1800725e2  mov     [rbx+58h], rax
0x1800725e6  lea     r14, [rbx+60h]
0x1800725ea  mov     qword ptr [r14], 2
0x1800725f1  movups  xmmword ptr [r14+18h], xmm0
0x1800725f6  movups  xmmword ptr [r14+28h], xmm0
0x1800725fb  movups  xmmword ptr [r14+38h], xmm0
0x180072600  mov     [r14+8], r12
0x180072604  mov     [r14+10h], r12
0x180072608  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x180072610  mov     [r14+4Ch], r12d
0x180072614  mov     [rbx+0B0h], r12b
0x18007261b  mov     [rbx+0B8h], r12
0x180072622  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable'
0x180072629  mov     [rbx], rax
0x18007262c  mov     [rbx+0C0h], r12
0x180072633  mov     [rbx+0C8h], r12
0x18007263a  test    rdi, rdi
0x18007263d  jz      short loc_180072651
0x18007263f  mov     [rbx+0C0h], rsi
0x180072646  mov     [rbx+0C8h], rdi
0x18007264d  lock inc dword ptr [rdi+0Ch]
0x180072651  mov     [rbp+80h], rbx
0x180072658  mov     rsi, [rbp+78h]
0x18007265c  mov     eax, r12d
0x18007265f  xchg    eax, [rbx+10h]
0x180072662  lock inc dword ptr [rbx+8]
0x180072666  mov     [rbx+0B8h], rsi
0x18007266d  mov     eax, [rsi+10h]
0x180072670  nop
0x180072671  test    eax, eax
0x180072673  jnz     loc_1800726FC
0x180072679  lea     rbp, [rsi+18h]
0x18007267d  mov     [rsp+68h+arg_0], rbp
0x180072682  mov     rcx, rbp; _Mtx_t
0x180072685  call    cs:__imp__Mtx_lock
0x18007268b  test    eax, eax
0x18007268d  jnz     loc_18007273D
0x180072693  mov     eax, [rbp+4Ch]
0x180072696  cmp     eax, 7FFFFFFFh
0x18007269b  jnz     short loc_1800726A7
0x18007269d  dec     eax
0x18007269f  mov     [rbp+4Ch], eax
0x1800726a2  jmp     loc_18007275A
0x1800726a7  mov     eax, [rsi+10h]
0x1800726aa  nop
0x1800726ab  test    eax, eax
0x1800726ad  jz      short loc_1800726B4
0x1800726af  mov     r12b, 1
0x1800726b2  jmp     short loc_1800726EA
0x1800726b4  mov     ecx, 10h; Size
0x1800726b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800726be  mov     rcx, rax
0x1800726c1  mov     [rsp+68h+arg_0], rax
0x1800726c6  mov     [rax], rbx
0x1800726c9  mov     qword ptr [rax+8], 0
0x1800726d1  cmp     qword ptr [rsi+68h], 0
0x1800726d6  jnz     short loc_1800726DE
0x1800726d8  mov     [rsi+68h], rax
0x1800726dc  jmp     short loc_1800726E6
0x1800726de  mov     rax, [rsi+70h]
0x1800726e2  mov     [rax+8], rcx
0x1800726e6  mov     [rsi+70h], rcx
0x1800726ea  mov     rcx, rbp; _Mtx_t
0x1800726ed  call    cs:__imp__Mtx_unlock
0x1800726f3  test    r12b, r12b
0x1800726f6  jz      loc_18007279F
0x1800726fc  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180072702  mov     esi, eax
0x180072704  xor     eax, eax
0x180072706  lock cmpxchg [rbx+10h], esi
0x18007270b  jnz     short loc_180072780
0x18007270d  mov     rcx, [rbx]
0x180072710  mov     rax, [rcx+10h]
0x180072714  mov     rcx, rbx
0x180072717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007271c  mov     eax, esi
0x18007271e  mov     ecx, 3
0x180072723  lock cmpxchg [rbx+10h], ecx
0x180072728  cmovnz  esi, eax
0x18007272b  cmp     esi, 2
0x18007272e  jnz     short loc_180072780
0x180072730  mov     rcx, r14; _Mtx_t
0x180072733  call    cs:__imp__Mtx_lock
0x180072739  test    eax, eax
0x18007273b  jz      short loc_180072749
0x18007273d  mov     ecx, 5
0x180072742  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180072748  int     3; Trap to Debugger
0x180072749  mov     eax, [r14+4Ch]
0x18007274d  cmp     eax, 7FFFFFFFh
0x180072752  jnz     short loc_180072766
0x180072754  dec     eax
0x180072756  mov     [r14+4Ch], eax
0x18007275a  mov     ecx, 6
0x18007275f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180072765  int     3; Trap to Debugger
0x180072766  mov     byte ptr [rbx+0B0h], 1
0x18007276d  mov     rcx, r14; _Mtx_t
0x180072770  call    cs:__imp__Mtx_unlock
0x180072776  lea     rcx, [rbx+18h]; _Cnd_t
0x18007277a  call    cs:__imp__Cnd_broadcast
0x180072780  or      esi, 0FFFFFFFFh
0x180072783  mov     eax, esi
0x180072785  lock xadd [rbx+8], eax
0x18007278a  add     eax, esi
0x18007278c  jnz     short loc_1800727A2
0x18007278e  mov     rax, [rbx]
0x180072791  mov     rcx, rbx
0x180072794  mov     rax, [rax+8]
0x180072798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007279d  jmp     short loc_1800727A2
0x18007279f  or      esi, 0FFFFFFFFh
0x1800727a2  test    rdi, rdi
0x1800727a5  jz      short loc_1800727C2
0x1800727a7  mov     eax, esi
0x1800727a9  lock xadd [rdi+0Ch], eax
0x1800727ae  add     eax, esi
0x1800727b0  jnz     short loc_1800727C2
0x1800727b2  mov     rax, [rdi]
0x1800727b5  mov     rcx, rdi
0x1800727b8  mov     rax, [rax+8]
0x1800727bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727c1  nop
0x1800727c2  mov     rcx, [r15+8]
0x1800727c6  test    rcx, rcx
0x1800727c9  jz      short loc_1800727E2
0x1800727cb  mov     eax, esi
0x1800727cd  lock xadd [rcx+0Ch], eax
0x1800727d2  add     eax, esi
0x1800727d4  jnz     short loc_1800727E2
0x1800727d6  mov     rax, [rcx]
0x1800727d9  mov     rax, [rax+8]
0x1800727dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727e2  mov     rbx, [rsp+68h+arg_10]
0x1800727ea  add     rsp, 30h
0x1800727ee  pop     r15
0x1800727f0  pop     r14
0x1800727f2  pop     r13
0x1800727f4  pop     r12
0x1800727f6  pop     rdi
0x1800727f7  pop     rsi
0x1800727f8  pop     rbp
0x1800727f9  retn
```

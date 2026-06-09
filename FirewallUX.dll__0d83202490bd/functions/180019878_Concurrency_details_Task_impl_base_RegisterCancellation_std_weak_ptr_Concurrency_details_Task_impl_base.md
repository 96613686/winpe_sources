# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x180019878`
- end: `0x180019b22`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `682`
- prototype: `int __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014cc0`

## callees

- `0x1800021e4`
- `0x180019878`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019a6a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019a87`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019a6a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019a87`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180019a24`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180019a24`
- `msvcp_win!_Cnd_broadcast` at `0x180019aa2`
- `msvcp_win!_Cnd_broadcast` at `0x180019aa2`
- `msvcp_win!_Mtx_unlock` at `0x180019a15`
- `msvcp_win!_Mtx_unlock` at `0x180019a98`
- `msvcp_win!_Mtx_unlock` at `0x180019a15`
- `msvcp_win!_Mtx_unlock` at `0x180019a98`
- `msvcp_win!_Mtx_lock` at `0x1800199ad`
- `msvcp_win!_Mtx_lock` at `0x180019a5b`
- `msvcp_win!_Mtx_lock` at `0x1800199ad`
- `msvcp_win!_Mtx_lock` at `0x180019a5b`

## pseudocode

```c
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
  *(_QWORD *)v8 = &___7___CancellationTokenCallback_V_lambda_1___1___RegisterCancellation__Task_impl_base_details_Concurrency__QEAAXV__weak_ptr_U_Task_impl_base_details_Concurrency___std___Z__details_Concurrency__6B_;
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
0x180019878  mov     rax, rsp
0x18001987b  mov     [rax+18h], rbx
0x18001987f  mov     [rax+10h], rdx
0x180019883  push    rbp
0x180019884  push    rsi
0x180019885  push    rdi
0x180019886  push    r12
0x180019888  push    r13
0x18001988a  push    r14
0x18001988c  push    r15
0x18001988e  sub     rsp, 30h
0x180019892  mov     r15, rdx
0x180019895  mov     rbp, rcx
0x180019898  xorps   xmm0, xmm0
0x18001989b  movdqu  xmmword ptr [rax-48h], xmm0
0x1800198a0  mov     rdi, [rdx+8]
0x1800198a4  xor     r12d, r12d
0x1800198a7  test    rdi, rdi
0x1800198aa  jz      short loc_1800198BD
0x1800198ac  mov     rsi, [rdx]
0x1800198af  mov     [rax-48h], rsi
0x1800198b3  mov     [rax-40h], rdi
0x1800198b7  lock inc dword ptr [rdi+0Ch]
0x1800198bb  jmp     short loc_1800198C7
0x1800198bd  mov     rdi, [rsp+68h+var_40]
0x1800198c2  mov     rsi, [rsp+68h+var_48]
0x1800198c7  mov     ecx, 0D0h; Size
0x1800198cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800198d1  mov     rbx, rax
0x1800198d4  mov     [rsp+68h+arg_0], rax
0x1800198d9  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x1800198e0  mov     [rbx], rax
0x1800198e3  mov     dword ptr [rbx+8], 1
0x1800198ea  mov     dword ptr [rbx+10h], 3
0x1800198f1  mov     [rbx+18h], r12
0x1800198f5  mov     [rbx+20h], r12
0x1800198f9  xorps   xmm0, xmm0
0x1800198fc  xor     eax, eax
0x1800198fe  movups  xmmword ptr [rbx+28h], xmm0
0x180019902  movups  xmmword ptr [rbx+38h], xmm0
0x180019906  movups  xmmword ptr [rbx+48h], xmm0
0x18001990a  mov     [rbx+58h], rax
0x18001990e  lea     r14, [rbx+60h]
0x180019912  mov     qword ptr [r14], 2
0x180019919  movups  xmmword ptr [r14+18h], xmm0
0x18001991e  movups  xmmword ptr [r14+28h], xmm0
0x180019923  movups  xmmword ptr [r14+38h], xmm0
0x180019928  mov     [r14+8], r12
0x18001992c  mov     [r14+10h], r12
0x180019930  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x180019938  mov     [r14+4Ch], r12d
0x18001993c  mov     [rbx+0B0h], r12b
0x180019943  mov     [rbx+0B8h], r12
0x18001994a  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_1_@?1??_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<`Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)'::`2'::_lambda_1_>::`vftable'
0x180019951  mov     [rbx], rax
0x180019954  mov     [rbx+0C0h], r12
0x18001995b  mov     [rbx+0C8h], r12
0x180019962  test    rdi, rdi
0x180019965  jz      short loc_180019979
0x180019967  mov     [rbx+0C0h], rsi
0x18001996e  mov     [rbx+0C8h], rdi
0x180019975  lock inc dword ptr [rdi+0Ch]
0x180019979  mov     [rbp+80h], rbx
0x180019980  mov     rsi, [rbp+78h]
0x180019984  mov     eax, r12d
0x180019987  xchg    eax, [rbx+10h]
0x18001998a  lock inc dword ptr [rbx+8]
0x18001998e  mov     [rbx+0B8h], rsi
0x180019995  mov     eax, [rsi+10h]
0x180019998  nop
0x180019999  test    eax, eax
0x18001999b  jnz     loc_180019A24
0x1800199a1  lea     rbp, [rsi+18h]
0x1800199a5  mov     [rsp+68h+arg_0], rbp
0x1800199aa  mov     rcx, rbp; _Mtx_t
0x1800199ad  call    cs:__imp__Mtx_lock
0x1800199b3  test    eax, eax
0x1800199b5  jnz     loc_180019A65
0x1800199bb  mov     eax, [rbp+4Ch]
0x1800199be  cmp     eax, 7FFFFFFFh
0x1800199c3  jnz     short loc_1800199CF
0x1800199c5  dec     eax
0x1800199c7  mov     [rbp+4Ch], eax
0x1800199ca  jmp     loc_180019A82
0x1800199cf  mov     eax, [rsi+10h]
0x1800199d2  nop
0x1800199d3  test    eax, eax
0x1800199d5  jz      short loc_1800199DC
0x1800199d7  mov     r12b, 1
0x1800199da  jmp     short loc_180019A12
0x1800199dc  mov     ecx, 10h; Size
0x1800199e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800199e6  mov     rcx, rax
0x1800199e9  mov     [rsp+68h+arg_0], rax
0x1800199ee  mov     [rax], rbx
0x1800199f1  mov     qword ptr [rax+8], 0
0x1800199f9  cmp     qword ptr [rsi+68h], 0
0x1800199fe  jnz     short loc_180019A06
0x180019a00  mov     [rsi+68h], rax
0x180019a04  jmp     short loc_180019A0E
0x180019a06  mov     rax, [rsi+70h]
0x180019a0a  mov     [rax+8], rcx
0x180019a0e  mov     [rsi+70h], rcx
0x180019a12  mov     rcx, rbp; _Mtx_t
0x180019a15  call    cs:__imp__Mtx_unlock
0x180019a1b  test    r12b, r12b
0x180019a1e  jz      loc_180019AC7
0x180019a24  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180019a2a  mov     esi, eax
0x180019a2c  xor     eax, eax
0x180019a2e  lock cmpxchg [rbx+10h], esi
0x180019a33  jnz     short loc_180019AA8
0x180019a35  mov     rcx, [rbx]
0x180019a38  mov     rax, [rcx+10h]
0x180019a3c  mov     rcx, rbx
0x180019a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a44  mov     eax, esi
0x180019a46  mov     ecx, 3
0x180019a4b  lock cmpxchg [rbx+10h], ecx
0x180019a50  cmovnz  esi, eax
0x180019a53  cmp     esi, 2
0x180019a56  jnz     short loc_180019AA8
0x180019a58  mov     rcx, r14; _Mtx_t
0x180019a5b  call    cs:__imp__Mtx_lock
0x180019a61  test    eax, eax
0x180019a63  jz      short loc_180019A71
0x180019a65  mov     ecx, 5
0x180019a6a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019a70  int     3; Trap to Debugger
0x180019a71  mov     eax, [r14+4Ch]
0x180019a75  cmp     eax, 7FFFFFFFh
0x180019a7a  jnz     short loc_180019A8E
0x180019a7c  dec     eax
0x180019a7e  mov     [r14+4Ch], eax
0x180019a82  mov     ecx, 6
0x180019a87  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019a8d  int     3; Trap to Debugger
0x180019a8e  mov     byte ptr [rbx+0B0h], 1
0x180019a95  mov     rcx, r14; _Mtx_t
0x180019a98  call    cs:__imp__Mtx_unlock
0x180019a9e  lea     rcx, [rbx+18h]; _Cnd_t
0x180019aa2  call    cs:__imp__Cnd_broadcast
0x180019aa8  or      esi, 0FFFFFFFFh
0x180019aab  mov     eax, esi
0x180019aad  lock xadd [rbx+8], eax
0x180019ab2  add     eax, esi
0x180019ab4  jnz     short loc_180019ACA
0x180019ab6  mov     rax, [rbx]
0x180019ab9  mov     rcx, rbx
0x180019abc  mov     rax, [rax+8]
0x180019ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ac5  jmp     short loc_180019ACA
0x180019ac7  or      esi, 0FFFFFFFFh
0x180019aca  test    rdi, rdi
0x180019acd  jz      short loc_180019AEA
0x180019acf  mov     eax, esi
0x180019ad1  lock xadd [rdi+0Ch], eax
0x180019ad6  add     eax, esi
0x180019ad8  jnz     short loc_180019AEA
0x180019ada  mov     rax, [rdi]
0x180019add  mov     rcx, rdi
0x180019ae0  mov     rax, [rax+8]
0x180019ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ae9  nop
0x180019aea  mov     rcx, [r15+8]
0x180019aee  test    rcx, rcx
0x180019af1  jz      short loc_180019B0A
0x180019af3  mov     eax, esi
0x180019af5  lock xadd [rcx+0Ch], eax
0x180019afa  add     eax, esi
0x180019afc  jnz     short loc_180019B0A
0x180019afe  mov     rax, [rcx]
0x180019b01  mov     rax, [rax+8]
0x180019b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b0a  mov     rbx, [rsp+68h+arg_10]
0x180019b12  add     rsp, 30h
0x180019b16  pop     r15
0x180019b18  pop     r14
0x180019b1a  pop     r13
0x180019b1c  pop     r12
0x180019b1e  pop     rdi
0x180019b1f  pop     rsi
0x180019b20  pop     rbp
0x180019b21  retn
```

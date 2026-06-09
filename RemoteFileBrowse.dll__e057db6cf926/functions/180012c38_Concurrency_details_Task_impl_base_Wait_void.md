# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x180012c38`
- end: `0x180012da7`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `367`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000fae8`
- `0x1800120d0`
- `0x180012c10`

## callees

- `0x18000ec28`
- `0x180012704`
- `0x180012c38`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x180012c88`
- `msvcp_win!_Cnd_wait` at `0x180012ceb`
- `msvcp_win!_Cnd_wait` at `0x180012d5d`
- `msvcp_win!_Cnd_wait` at `0x180012c88`
- `msvcp_win!_Cnd_wait` at `0x180012ceb`
- `msvcp_win!_Cnd_wait` at `0x180012d5d`
- `msvcp_win!_Mtx_unlock` at `0x180012cfe`
- `msvcp_win!_Mtx_unlock` at `0x180012d70`
- `msvcp_win!_Mtx_unlock` at `0x180012cfe`
- `msvcp_win!_Mtx_unlock` at `0x180012d70`
- `msvcp_win!_Mtx_lock` at `0x180012c62`
- `msvcp_win!_Mtx_lock` at `0x180012cb5`
- `msvcp_win!_Mtx_lock` at `0x180012d1b`
- `msvcp_win!_Mtx_lock` at `0x180012c62`
- `msvcp_win!_Mtx_lock` at `0x180012cb5`
- `msvcp_win!_Mtx_lock` at `0x180012d1b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012cc4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012cdf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012d2a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012d49`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012cc4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012cdf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012d2a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012d49`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_Wait(__int64 a1)
{
  __int64 v1; // rsi
  int v2; // ebx
  __int64 v3; // r14
  __int64 v4; // rdi
  _DWORD *v5; // rcx
  __int64 v6; // r14
  int v7; // eax
  Concurrency::details::_ExceptionHolder *v9; // rax
  const struct std::exception_ptr *v10; // rax
  Concurrency::details::_ExceptionHolder *v11; // rax
  _BYTE v12[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h]
  _Cnd_t v17; // [rsp+60h] [rbp+18h]

  v1 = a1;
  v2 = 0;
  if ( *(_BYTE *)(a1 + 12) )
  {
    v3 = a1 + 136;
    v4 = a1 + 208;
    if ( !_Mtx_lock((_Mtx_t)(a1 + 208)) )
    {
      v5 = (_DWORD *)(v4 + 76);
      if ( *(_DWORD *)(v4 + 76) != 0x7FFFFFFF )
      {
        while ( *(int *)(v3 + 176) < 2 )
          _Cnd_wait((_Cnd_t)v3, (_Mtx_t)v4);
LABEL_24:
        _Mtx_unlock((_Mtx_t)v4);
        goto LABEL_25;
      }
      goto LABEL_21;
    }
    goto LABEL_19;
  }
  v6 = a1 + 136;
  v17 = (_Cnd_t)(a1 + 136);
  v4 = a1 + 208;
  v15 = a1 + 208;
  v7 = _Mtx_lock((_Mtx_t)(a1 + 208));
  try
  {
    if ( v7 )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v4 + 76) != 0x7FFFFFFF )
      goto LABEL_14;
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
    do
    {
      _Cnd_wait((_Cnd_t)v6, (_Mtx_t)v4);
LABEL_14:
      ;
    }
    while ( *(int *)(v6 + 176) < 2 );
    _Mtx_unlock((_Mtx_t)v4);
  }
  catch ( Concurrency::details::_Interruption_exception )
  {
    v4 = v15;
    v1 = a1;
    v2 = 0;
  }
  catch ( Concurrency::task_canceled )
  {
    v4 = v15;
    v1 = a1;
    v2 = 0;
  }
  catch ( ... )
  {
    if ( !Concurrency::details::_Task_impl_base::_HasUserException((Concurrency::details::_Task_impl_base *)a1) )
    {
      v10 = (const struct std::exception_ptr *)std::current_exception(v12);
      Concurrency::details::_Task_impl_base::_CancelWithException((Concurrency::details::_Task_impl_base *)a1, v10);
      std::exception_ptr::~exception_ptr((std::exception_ptr *)v12);
    }
    v11 = (Concurrency::details::_ExceptionHolder *)std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator-><Concurrency::details::_ExceptionHolder,0>(a1 + 16);
    Concurrency::details::_ExceptionHolder::_RethrowUserException(v11);
  }
  if ( *(_BYTE *)(v1 + 13) )
  {
    if ( !_Mtx_lock((_Mtx_t)v4) )
    {
      v5 = (_DWORD *)(v4 + 76);
      if ( *(_DWORD *)(v4 + 76) != 0x7FFFFFFF )
      {
        while ( *((int *)v17 + 44) < 2 )
          _Cnd_wait(v17, (_Mtx_t)v4);
        goto LABEL_24;
      }
LABEL_21:
      *v5 = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
LABEL_19:
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
LABEL_25:
  if ( *(_QWORD *)(v1 + 16) )
  {
    v9 = (Concurrency::details::_ExceptionHolder *)std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator-><Concurrency::details::_ExceptionHolder,0>(v1 + 16);
    Concurrency::details::_ExceptionHolder::_RethrowUserException(v9);
  }
  LOBYTE(v2) = *(_DWORD *)(v1 + 8) == 4;
  return (unsigned int)(v2 + 1);
}

```

## disassembly

```asm
0x180012c38  mov     [rsp+arg_18], rbx
0x180012c3d  mov     [rsp+arg_0], rcx
0x180012c42  push    rsi
0x180012c43  push    rdi
0x180012c44  push    r14
0x180012c46  sub     rsp, 30h
0x180012c4a  mov     rsi, rcx
0x180012c4d  xor     ebx, ebx
0x180012c4f  cmp     [rcx+0Ch], bl
0x180012c52  jz      short loc_180012C9D
0x180012c54  lea     r14, [rcx+88h]
0x180012c5b  lea     rdi, [r14+48h]
0x180012c5f  mov     rcx, rdi; _Mtx_t
0x180012c62  call    cs:__imp__Mtx_lock
0x180012c68  test    eax, eax
0x180012c6a  jnz     loc_180012D25
0x180012c70  lea     rcx, [rdi+4Ch]
0x180012c74  cmp     dword ptr [rcx], 7FFFFFFFh
0x180012c7a  jz      loc_180012D3D
0x180012c80  jmp     short loc_180012C8E
0x180012c82  mov     rdx, rdi; _Mtx_t
0x180012c85  mov     rcx, r14; _Cnd_t
0x180012c88  call    cs:__imp__Cnd_wait
0x180012c8e  cmp     dword ptr [r14+0B0h], 2
0x180012c96  jl      short loc_180012C82
0x180012c98  jmp     loc_180012D6D
0x180012c9d  lea     r14, [rcx+88h]
0x180012ca4  mov     [rsp+48h+arg_10], r14
0x180012ca9  lea     rdi, [r14+48h]
0x180012cad  mov     [rsp+48h+arg_8], rdi
0x180012cb2  mov     rcx, rdi; _Mtx_t
0x180012cb5  call    cs:__imp__Mtx_lock
0x180012cbb  test    eax, eax
0x180012cbd  jz      short loc_180012CCA
0x180012cbf  mov     ecx, 5
0x180012cc4  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012cca  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180012cd1  jnz     short loc_180012CF1
0x180012cd3  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180012cda  mov     ecx, 6
0x180012cdf  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012ce5  mov     rdx, rdi; _Mtx_t
0x180012ce8  mov     rcx, r14; _Cnd_t
0x180012ceb  call    cs:__imp__Cnd_wait
0x180012cf1  cmp     dword ptr [r14+0B0h], 2
0x180012cf9  jl      short loc_180012CE5
0x180012cfb  mov     rcx, rdi; _Mtx_t
0x180012cfe  call    cs:__imp__Mtx_unlock
0x180012d04  nop
0x180012d05  jmp     short loc_180012D13
0x180012d07  mov     rdi, [rsp+48h+arg_8]
0x180012d0c  mov     rsi, [rsp+48h+arg_0]
0x180012d11  xor     ebx, ebx
0x180012d13  cmp     [rsi+0Dh], bl
0x180012d16  jz      short loc_180012D76
0x180012d18  mov     rcx, rdi; _Mtx_t
0x180012d1b  call    cs:__imp__Mtx_lock
0x180012d21  test    eax, eax
0x180012d23  jz      short loc_180012D31
0x180012d25  mov     ecx, 5
0x180012d2a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012d30  int     3; Trap to Debugger
0x180012d31  lea     rcx, [rdi+4Ch]
0x180012d35  cmp     dword ptr [rcx], 7FFFFFFFh
0x180012d3b  jnz     short loc_180012D50
0x180012d3d  mov     eax, 7FFFFFFEh
0x180012d42  mov     [rcx], eax
0x180012d44  mov     ecx, 6
0x180012d49  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012d4f  int     3; Trap to Debugger
0x180012d50  mov     r14, [rsp+48h+arg_10]
0x180012d55  jmp     short loc_180012D63
0x180012d57  mov     rdx, rdi; _Mtx_t
0x180012d5a  mov     rcx, r14; _Cnd_t
0x180012d5d  call    cs:__imp__Cnd_wait
0x180012d63  cmp     dword ptr [r14+0B0h], 2
0x180012d6b  jl      short loc_180012D57
0x180012d6d  mov     rcx, rdi; _Mtx_t
0x180012d70  call    cs:__imp__Mtx_unlock
0x180012d76  lea     rcx, [rsi+10h]
0x180012d7a  cmp     [rcx], rbx
0x180012d7d  jnz     short loc_180012D99
0x180012d7f  mov     ecx, [rsi+8]
0x180012d82  cmp     ecx, 4
0x180012d85  setz    bl
0x180012d88  lea     eax, [rbx+1]
0x180012d8b  mov     rbx, [rsp+48h+arg_18]
0x180012d90  add     rsp, 30h
0x180012d94  pop     r14
0x180012d96  pop     rdi
0x180012d97  pop     rsi
0x180012d98  retn
0x180012d99  call    ??$?CU_ExceptionHolder@details@Concurrency@@$0A@@?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEBAPEAU_ExceptionHolder@details@Concurrency@@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator-><Concurrency::details::_ExceptionHolder,0>(void)
0x180012d9e  mov     rcx, rax; this
0x180012da1  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
```

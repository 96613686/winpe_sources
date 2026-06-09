# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x18001a318`
- end: `0x18001a487`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `367`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016320`
- `0x180019500`
- `0x18001a2f0`

## callees

- `0x18000f3b0`
- `0x180019b28`
- `0x18001a318`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a3a4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a3bf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a40a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a429`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a3a4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a3bf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a40a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a429`
- `msvcp_win!_Cnd_wait` at `0x18001a368`
- `msvcp_win!_Cnd_wait` at `0x18001a3cb`
- `msvcp_win!_Cnd_wait` at `0x18001a43d`
- `msvcp_win!_Cnd_wait` at `0x18001a368`
- `msvcp_win!_Cnd_wait` at `0x18001a3cb`
- `msvcp_win!_Cnd_wait` at `0x18001a43d`
- `msvcp_win!_Mtx_unlock` at `0x18001a3de`
- `msvcp_win!_Mtx_unlock` at `0x18001a450`
- `msvcp_win!_Mtx_unlock` at `0x18001a3de`
- `msvcp_win!_Mtx_unlock` at `0x18001a450`
- `msvcp_win!_Mtx_lock` at `0x18001a342`
- `msvcp_win!_Mtx_lock` at `0x18001a395`
- `msvcp_win!_Mtx_lock` at `0x18001a3fb`
- `msvcp_win!_Mtx_lock` at `0x18001a342`
- `msvcp_win!_Mtx_lock` at `0x18001a395`
- `msvcp_win!_Mtx_lock` at `0x18001a3fb`

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
    v11 = (Concurrency::details::_ExceptionHolder *)winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::operator->(a1 + 16);
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
    v9 = (Concurrency::details::_ExceptionHolder *)winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::operator->(v1 + 16);
    Concurrency::details::_ExceptionHolder::_RethrowUserException(v9);
  }
  LOBYTE(v2) = *(_DWORD *)(v1 + 8) == 4;
  return (unsigned int)(v2 + 1);
}

```

## disassembly

```asm
0x18001a318  mov     [rsp+arg_18], rbx
0x18001a31d  mov     [rsp+arg_0], rcx
0x18001a322  push    rsi
0x18001a323  push    rdi
0x18001a324  push    r14
0x18001a326  sub     rsp, 30h
0x18001a32a  mov     rsi, rcx
0x18001a32d  xor     ebx, ebx
0x18001a32f  cmp     [rcx+0Ch], bl
0x18001a332  jz      short loc_18001A37D
0x18001a334  lea     r14, [rcx+88h]
0x18001a33b  lea     rdi, [r14+48h]
0x18001a33f  mov     rcx, rdi; _Mtx_t
0x18001a342  call    cs:__imp__Mtx_lock
0x18001a348  test    eax, eax
0x18001a34a  jnz     loc_18001A405
0x18001a350  lea     rcx, [rdi+4Ch]
0x18001a354  cmp     dword ptr [rcx], 7FFFFFFFh
0x18001a35a  jz      loc_18001A41D
0x18001a360  jmp     short loc_18001A36E
0x18001a362  mov     rdx, rdi; _Mtx_t
0x18001a365  mov     rcx, r14; _Cnd_t
0x18001a368  call    cs:__imp__Cnd_wait
0x18001a36e  cmp     dword ptr [r14+0B0h], 2
0x18001a376  jl      short loc_18001A362
0x18001a378  jmp     loc_18001A44D
0x18001a37d  lea     r14, [rcx+88h]
0x18001a384  mov     [rsp+48h+arg_10], r14
0x18001a389  lea     rdi, [r14+48h]
0x18001a38d  mov     [rsp+48h+arg_8], rdi
0x18001a392  mov     rcx, rdi; _Mtx_t
0x18001a395  call    cs:__imp__Mtx_lock
0x18001a39b  test    eax, eax
0x18001a39d  jz      short loc_18001A3AA
0x18001a39f  mov     ecx, 5
0x18001a3a4  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a3aa  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x18001a3b1  jnz     short loc_18001A3D1
0x18001a3b3  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x18001a3ba  mov     ecx, 6
0x18001a3bf  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a3c5  mov     rdx, rdi; _Mtx_t
0x18001a3c8  mov     rcx, r14; _Cnd_t
0x18001a3cb  call    cs:__imp__Cnd_wait
0x18001a3d1  cmp     dword ptr [r14+0B0h], 2
0x18001a3d9  jl      short loc_18001A3C5
0x18001a3db  mov     rcx, rdi; _Mtx_t
0x18001a3de  call    cs:__imp__Mtx_unlock
0x18001a3e4  nop
0x18001a3e5  jmp     short loc_18001A3F3
0x18001a3e7  mov     rdi, [rsp+48h+arg_8]
0x18001a3ec  mov     rsi, [rsp+48h+arg_0]
0x18001a3f1  xor     ebx, ebx
0x18001a3f3  cmp     [rsi+0Dh], bl
0x18001a3f6  jz      short loc_18001A456
0x18001a3f8  mov     rcx, rdi; _Mtx_t
0x18001a3fb  call    cs:__imp__Mtx_lock
0x18001a401  test    eax, eax
0x18001a403  jz      short loc_18001A411
0x18001a405  mov     ecx, 5
0x18001a40a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a410  int     3; Trap to Debugger
0x18001a411  lea     rcx, [rdi+4Ch]
0x18001a415  cmp     dword ptr [rcx], 7FFFFFFFh
0x18001a41b  jnz     short loc_18001A430
0x18001a41d  mov     eax, 7FFFFFFEh
0x18001a422  mov     [rcx], eax
0x18001a424  mov     ecx, 6
0x18001a429  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a42f  int     3; Trap to Debugger
0x18001a430  mov     r14, [rsp+48h+arg_10]
0x18001a435  jmp     short loc_18001A443
0x18001a437  mov     rdx, rdi; _Mtx_t
0x18001a43a  mov     rcx, r14; _Cnd_t
0x18001a43d  call    cs:__imp__Cnd_wait
0x18001a443  cmp     dword ptr [r14+0B0h], 2
0x18001a44b  jl      short loc_18001A437
0x18001a44d  mov     rcx, rdi; _Mtx_t
0x18001a450  call    cs:__imp__Mtx_unlock
0x18001a456  lea     rcx, [rsi+10h]
0x18001a45a  cmp     [rcx], rbx
0x18001a45d  jnz     short loc_18001A479
0x18001a45f  mov     ecx, [rsi+8]
0x18001a462  cmp     ecx, 4
0x18001a465  setz    bl
0x18001a468  lea     eax, [rbx+1]
0x18001a46b  mov     rbx, [rsp+48h+arg_18]
0x18001a470  add     rsp, 30h
0x18001a474  pop     r14
0x18001a476  pop     rdi
0x18001a477  pop     rsi
0x18001a478  retn
0x18001a479  call    ??C?$com_ptr@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@QEBA@XZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::operator->(void)
0x18001a47e  mov     rcx, rax; this
0x18001a481  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
```

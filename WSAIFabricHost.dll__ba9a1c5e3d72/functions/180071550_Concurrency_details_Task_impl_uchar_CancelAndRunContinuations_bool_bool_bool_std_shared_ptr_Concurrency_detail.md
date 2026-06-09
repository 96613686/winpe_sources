# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180071550`
- end: `0x18007179b`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180004ca0`
- `0x180071550`
- `0x180072c64`
- `0x180089010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180071700`
- `msvcp_win!_Cnd_broadcast` at `0x180071700`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180071673`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180071673`
- `msvcp_win!_Mtx_unlock` at `0x18007167d`
- `msvcp_win!_Mtx_unlock` at `0x18007170a`
- `msvcp_win!_Mtx_unlock` at `0x180071785`
- `msvcp_win!_Mtx_unlock` at `0x18007167d`
- `msvcp_win!_Mtx_unlock` at `0x18007170a`
- `msvcp_win!_Mtx_unlock` at `0x180071785`
- `msvcp_win!_Mtx_lock` at `0x18007158c`
- `msvcp_win!_Mtx_lock` at `0x1800716bd`
- `msvcp_win!_Mtx_lock` at `0x18007158c`
- `msvcp_win!_Mtx_lock` at `0x1800716bd`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800716e6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180071794`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800716e6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180071794`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v8; // rsi
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  int v13; // edi
  int v14; // edi
  __int64 v15; // rcx
  _QWORD *v16; // rdx
  _QWORD v18[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp-50h]

  v8 = a1 + 32;
  if ( _Mtx_lock((_Mtx_t)(a1 + 32)) )
    goto LABEL_36;
  if ( *(_DWORD *)(v8 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v8 + 76) = 2147483646;
    goto LABEL_28;
  }
  v9 = *(_DWORD *)(a1 + 8);
  if ( a3 )
  {
    if ( v9 != 4 )
    {
      v10 = a5[1];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v11 = a5[1];
      *(_QWORD *)(a1 + 16) = *a5;
      v12 = *(volatile signed __int32 **)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v11;
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      goto LABEL_16;
    }
  }
  else if ( v9 != 3 && *(_DWORD *)(a1 + 8) != 4 && (*(_DWORD *)(a1 + 8) != 2 || a2) )
  {
LABEL_16:
    if ( a2 )
    {
      *(_DWORD *)(a1 + 8) = 4;
      v13 = 1;
    }
    else
    {
      v13 = 0;
      if ( *(_DWORD *)(a1 + 8) == 1 )
        v13 = 2;
      *(_DWORD *)(a1 + 8) = 2;
      Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
    }
    _Mtx_unlock((_Mtx_t)v8);
    v14 = v13 - 1;
    if ( v14 )
    {
      if ( v14 == 1 )
      {
        v15 = *(_QWORD *)(a1 + 432);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return 1;
    }
    if ( !_Mtx_lock((_Mtx_t)(a1 + 208)) )
    {
      if ( *(_DWORD *)(a1 + 284) == 0x7FFFFFFF )
      {
        *(_DWORD *)(a1 + 284) = 2147483646;
LABEL_28:
        std::_Throw_Cpp_error(6);
        __debugbreak();
      }
      if ( *(int *)(a1 + 312) < 2 )
        *(_DWORD *)(a1 + 312) = 2;
      _Cnd_broadcast((_Cnd_t)(a1 + 136));
      _Mtx_unlock((_Mtx_t)(a1 + 208));
      if ( *(_QWORD *)(a1 + 112) )
      {
        v18[0] = &std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable';
        v18[1] = a1;
        v19 = v18;
        Concurrency::details::_ScheduleFuncWithAutoInline(v18, 16);
        if ( v19 )
        {
          v16 = v18;
          LOBYTE(v16) = v19 != v18;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v19 + 32LL))(v19, v16);
        }
      }
      return 1;
    }
LABEL_36:
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x18007179ALL);
  }
  _Mtx_unlock((_Mtx_t)v8);
  return 0;
}

```

## disassembly

```asm
0x180071550  push    rbx
0x180071552  push    rbp
0x180071553  push    rsi
0x180071554  push    rdi
0x180071555  push    r14
0x180071557  push    r15
0x180071559  sub     rsp, 88h
0x180071560  mov     rax, cs:__security_cookie
0x180071567  xor     rax, rsp
0x18007156a  mov     [rsp+0B8h+var_48], rax
0x18007156f  mov     bpl, r8b
0x180071572  mov     r14b, dl
0x180071575  mov     rbx, rcx
0x180071578  mov     rdi, [rsp+0B8h+arg_20]
0x180071580  lea     rsi, [rcx+20h]
0x180071584  mov     [rsp+0B8h+var_98], rsi
0x180071589  mov     rcx, rsi; _Mtx_t
0x18007158c  call    cs:__imp__Mtx_lock
0x180071592  test    eax, eax
0x180071594  jnz     loc_18007178F
0x18007159a  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x1800715a1  jnz     short loc_1800715AF
0x1800715a3  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x1800715aa  jmp     loc_1800716E1
0x1800715af  mov     r15d, 2
0x1800715b5  mov     eax, [rbx+8]
0x1800715b8  test    bpl, bpl
0x1800715bb  jz      short loc_180071623
0x1800715bd  cmp     eax, 4
0x1800715c0  jz      loc_180071782
0x1800715c6  mov     rax, [rdi+8]
0x1800715ca  test    rax, rax
0x1800715cd  jz      short loc_1800715D3
0x1800715cf  lock inc dword ptr [rax+8]
0x1800715d3  mov     rcx, [rdi+8]
0x1800715d7  mov     rax, [rdi]
0x1800715da  mov     [rbx+10h], rax
0x1800715de  mov     rdi, [rbx+18h]
0x1800715e2  mov     [rbx+18h], rcx
0x1800715e6  test    rdi, rdi
0x1800715e9  jz      short loc_180071649
0x1800715eb  or      ebp, 0FFFFFFFFh
0x1800715ee  mov     eax, ebp
0x1800715f0  lock xadd [rdi+8], eax
0x1800715f5  add     eax, ebp
0x1800715f7  jnz     short loc_180071649
0x1800715f9  mov     rax, [rdi]
0x1800715fc  mov     rcx, rdi
0x1800715ff  mov     rax, [rax]
0x180071602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071607  mov     eax, ebp
0x180071609  lock xadd [rdi+0Ch], eax
0x18007160e  add     eax, ebp
0x180071610  jnz     short loc_180071649
0x180071612  mov     rax, [rdi]
0x180071615  mov     rcx, rdi
0x180071618  mov     rax, [rax+8]
0x18007161c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071621  jmp     short loc_180071649
0x180071623  cmp     eax, 3
0x180071626  jz      loc_180071782
0x18007162c  mov     eax, [rbx+8]
0x18007162f  cmp     eax, 4
0x180071632  jz      loc_180071782
0x180071638  mov     eax, [rbx+8]
0x18007163b  cmp     eax, r15d
0x18007163e  jnz     short loc_180071649
0x180071640  test    r14b, r14b
0x180071643  jz      loc_180071782
0x180071649  test    r14b, r14b
0x18007164c  jz      short loc_18007165C
0x18007164e  mov     dword ptr [rbx+8], 4
0x180071655  mov     edi, 1
0x18007165a  jmp     short loc_18007167A
0x18007165c  mov     eax, [rbx+8]
0x18007165f  xor     edi, edi
0x180071661  cmp     eax, 1
0x180071664  cmovz   edi, r15d
0x180071668  mov     [rbx+8], r15d
0x18007166c  lea     rcx, [rbx+160h]
0x180071673  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x180071679  nop
0x18007167a  mov     rcx, rsi; _Mtx_t
0x18007167d  call    cs:__imp__Mtx_unlock
0x180071683  sub     edi, 1
0x180071686  jz      short loc_1800716B2
0x180071688  cmp     edi, 1
0x18007168b  jnz     loc_180071763
0x180071691  mov     rcx, [rbx+1B0h]
0x180071698  test    rcx, rcx
0x18007169b  jz      loc_180071763
0x1800716a1  mov     rax, [rcx]
0x1800716a4  mov     rax, [rax+10h]
0x1800716a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800716ad  jmp     loc_180071763
0x1800716b2  lea     rsi, [rbx+88h]
0x1800716b9  lea     rcx, [rsi+48h]; _Mtx_t
0x1800716bd  call    cs:__imp__Mtx_lock
0x1800716c3  test    eax, eax
0x1800716c5  jnz     loc_18007178F
0x1800716cb  cmp     dword ptr [rsi+94h], 7FFFFFFFh
0x1800716d5  jnz     short loc_1800716ED
0x1800716d7  mov     dword ptr [rsi+94h], 7FFFFFFEh
0x1800716e1  mov     ecx, 6
0x1800716e6  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800716ec  int     3; Trap to Debugger
0x1800716ed  cmp     [rsi+0B0h], r15d
0x1800716f4  jge     short loc_1800716FD
0x1800716f6  mov     [rsi+0B0h], r15d
0x1800716fd  mov     rcx, rsi; _Cnd_t
0x180071700  call    cs:__imp__Cnd_broadcast
0x180071706  lea     rcx, [rsi+48h]; _Mtx_t
0x18007170a  call    cs:__imp__Mtx_unlock
0x180071710  cmp     qword ptr [rbx+70h], 0
0x180071715  jz      short loc_180071763
0x180071717  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18007171e  mov     [rsp+0B8h+var_88], rax
0x180071723  mov     [rsp+0B8h+var_80], rbx
0x180071728  lea     rax, [rsp+0B8h+var_88]
0x18007172d  mov     [rsp+0B8h+var_50], rax
0x180071732  mov     edx, 10h
0x180071737  lea     rcx, [rsp+0B8h+var_88]
0x18007173c  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180071741  nop
0x180071742  mov     rcx, [rsp+0B8h+var_50]
0x180071747  test    rcx, rcx
0x18007174a  jz      short loc_180071763
0x18007174c  mov     rax, [rcx]
0x18007174f  lea     rdx, [rsp+0B8h+var_88]
0x180071754  cmp     rcx, rdx
0x180071757  setnz   dl
0x18007175a  mov     rax, [rax+20h]
0x18007175e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071763  mov     al, 1
0x180071765  mov     rcx, [rsp+0B8h+var_48]
0x18007176a  xor     rcx, rsp; StackCookie
0x18007176d  call    __security_check_cookie
0x180071772  add     rsp, 88h
0x180071779  pop     r15
0x18007177b  pop     r14
0x18007177d  pop     rdi
0x18007177e  pop     rsi
0x18007177f  pop     rbp
0x180071780  pop     rbx
0x180071781  retn
0x180071782  mov     rcx, rsi; _Mtx_t
0x180071785  call    cs:__imp__Mtx_unlock
0x18007178b  xor     al, al
0x18007178d  jmp     short loc_180071765
0x18007178f  mov     ecx, 5
0x180071794  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

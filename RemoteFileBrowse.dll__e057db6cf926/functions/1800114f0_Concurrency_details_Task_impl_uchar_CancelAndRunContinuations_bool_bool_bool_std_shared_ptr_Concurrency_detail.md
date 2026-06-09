# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1800114f0`
- end: `0x18001173b`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `587`
- prototype: `char __fastcall(__int64, char, char, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002030`
- `0x1800114f0`
- `0x180012924`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180011613`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180011613`
- `msvcp_win!_Cnd_broadcast` at `0x1800116a0`
- `msvcp_win!_Cnd_broadcast` at `0x1800116a0`
- `msvcp_win!_Mtx_unlock` at `0x18001161d`
- `msvcp_win!_Mtx_unlock` at `0x1800116aa`
- `msvcp_win!_Mtx_unlock` at `0x180011725`
- `msvcp_win!_Mtx_unlock` at `0x18001161d`
- `msvcp_win!_Mtx_unlock` at `0x1800116aa`
- `msvcp_win!_Mtx_unlock` at `0x180011725`
- `msvcp_win!_Mtx_lock` at `0x18001152c`
- `msvcp_win!_Mtx_lock` at `0x18001165d`
- `msvcp_win!_Mtx_lock` at `0x18001152c`
- `msvcp_win!_Mtx_lock` at `0x18001165d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011686`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011734`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011686`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011734`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
    JUMPOUT(0x18001173ALL);
  }
  _Mtx_unlock((_Mtx_t)v8);
  return 0;
}

```

## disassembly

```asm
0x1800114f0  push    rbx
0x1800114f2  push    rbp
0x1800114f3  push    rsi
0x1800114f4  push    rdi
0x1800114f5  push    r14
0x1800114f7  push    r15
0x1800114f9  sub     rsp, 88h
0x180011500  mov     rax, cs:__security_cookie
0x180011507  xor     rax, rsp
0x18001150a  mov     [rsp+0B8h+var_48], rax
0x18001150f  mov     bpl, r8b
0x180011512  mov     r14b, dl
0x180011515  mov     rbx, rcx
0x180011518  mov     rdi, [rsp+0B8h+arg_20]
0x180011520  lea     rsi, [rcx+20h]
0x180011524  mov     [rsp+0B8h+var_98], rsi
0x180011529  mov     rcx, rsi; _Mtx_t
0x18001152c  call    cs:__imp__Mtx_lock
0x180011532  test    eax, eax
0x180011534  jnz     loc_18001172F
0x18001153a  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180011541  jnz     short loc_18001154F
0x180011543  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x18001154a  jmp     loc_180011681
0x18001154f  mov     r15d, 2
0x180011555  mov     eax, [rbx+8]
0x180011558  test    bpl, bpl
0x18001155b  jz      short loc_1800115C3
0x18001155d  cmp     eax, 4
0x180011560  jz      loc_180011722
0x180011566  mov     rax, [rdi+8]
0x18001156a  test    rax, rax
0x18001156d  jz      short loc_180011573
0x18001156f  lock inc dword ptr [rax+8]
0x180011573  mov     rcx, [rdi+8]
0x180011577  mov     rax, [rdi]
0x18001157a  mov     [rbx+10h], rax
0x18001157e  mov     rdi, [rbx+18h]
0x180011582  mov     [rbx+18h], rcx
0x180011586  test    rdi, rdi
0x180011589  jz      short loc_1800115E9
0x18001158b  or      ebp, 0FFFFFFFFh
0x18001158e  mov     eax, ebp
0x180011590  lock xadd [rdi+8], eax
0x180011595  add     eax, ebp
0x180011597  jnz     short loc_1800115E9
0x180011599  mov     rax, [rdi]
0x18001159c  mov     rcx, rdi
0x18001159f  mov     rax, [rax]
0x1800115a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115a7  mov     eax, ebp
0x1800115a9  lock xadd [rdi+0Ch], eax
0x1800115ae  add     eax, ebp
0x1800115b0  jnz     short loc_1800115E9
0x1800115b2  mov     rax, [rdi]
0x1800115b5  mov     rcx, rdi
0x1800115b8  mov     rax, [rax+8]
0x1800115bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115c1  jmp     short loc_1800115E9
0x1800115c3  cmp     eax, 3
0x1800115c6  jz      loc_180011722
0x1800115cc  mov     eax, [rbx+8]
0x1800115cf  cmp     eax, 4
0x1800115d2  jz      loc_180011722
0x1800115d8  mov     eax, [rbx+8]
0x1800115db  cmp     eax, r15d
0x1800115de  jnz     short loc_1800115E9
0x1800115e0  test    r14b, r14b
0x1800115e3  jz      loc_180011722
0x1800115e9  test    r14b, r14b
0x1800115ec  jz      short loc_1800115FC
0x1800115ee  mov     dword ptr [rbx+8], 4
0x1800115f5  mov     edi, 1
0x1800115fa  jmp     short loc_18001161A
0x1800115fc  mov     eax, [rbx+8]
0x1800115ff  xor     edi, edi
0x180011601  cmp     eax, 1
0x180011604  cmovz   edi, r15d
0x180011608  mov     [rbx+8], r15d
0x18001160c  lea     rcx, [rbx+160h]
0x180011613  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x180011619  nop
0x18001161a  mov     rcx, rsi; _Mtx_t
0x18001161d  call    cs:__imp__Mtx_unlock
0x180011623  sub     edi, 1
0x180011626  jz      short loc_180011652
0x180011628  cmp     edi, 1
0x18001162b  jnz     loc_180011703
0x180011631  mov     rcx, [rbx+1B0h]
0x180011638  test    rcx, rcx
0x18001163b  jz      loc_180011703
0x180011641  mov     rax, [rcx]
0x180011644  mov     rax, [rax+10h]
0x180011648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164d  jmp     loc_180011703
0x180011652  lea     rsi, [rbx+88h]
0x180011659  lea     rcx, [rsi+48h]; _Mtx_t
0x18001165d  call    cs:__imp__Mtx_lock
0x180011663  test    eax, eax
0x180011665  jnz     loc_18001172F
0x18001166b  cmp     dword ptr [rsi+94h], 7FFFFFFFh
0x180011675  jnz     short loc_18001168D
0x180011677  mov     dword ptr [rsi+94h], 7FFFFFFEh
0x180011681  mov     ecx, 6
0x180011686  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001168c  int     3; Trap to Debugger
0x18001168d  cmp     [rsi+0B0h], r15d
0x180011694  jge     short loc_18001169D
0x180011696  mov     [rsi+0B0h], r15d
0x18001169d  mov     rcx, rsi; _Cnd_t
0x1800116a0  call    cs:__imp__Cnd_broadcast
0x1800116a6  lea     rcx, [rsi+48h]; _Mtx_t
0x1800116aa  call    cs:__imp__Mtx_unlock
0x1800116b0  cmp     qword ptr [rbx+70h], 0
0x1800116b5  jz      short loc_180011703
0x1800116b7  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x1800116be  mov     [rsp+0B8h+var_88], rax
0x1800116c3  mov     [rsp+0B8h+var_80], rbx
0x1800116c8  lea     rax, [rsp+0B8h+var_88]
0x1800116cd  mov     [rsp+0B8h+var_50], rax
0x1800116d2  mov     edx, 10h
0x1800116d7  lea     rcx, [rsp+0B8h+var_88]
0x1800116dc  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x1800116e1  nop
0x1800116e2  mov     rcx, [rsp+0B8h+var_50]
0x1800116e7  test    rcx, rcx
0x1800116ea  jz      short loc_180011703
0x1800116ec  mov     rax, [rcx]
0x1800116ef  lea     rdx, [rsp+0B8h+var_88]
0x1800116f4  cmp     rcx, rdx
0x1800116f7  setnz   dl
0x1800116fa  mov     rax, [rax+20h]
0x1800116fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011703  mov     al, 1
0x180011705  mov     rcx, [rsp+0B8h+var_48]
0x18001170a  xor     rcx, rsp; StackCookie
0x18001170d  call    __security_check_cookie
0x180011712  add     rsp, 88h
0x180011719  pop     r15
0x18001171b  pop     r14
0x18001171d  pop     rdi
0x18001171e  pop     rsi
0x18001171f  pop     rbp
0x180011720  pop     rbx
0x180011721  retn
0x180011722  mov     rcx, rsi; _Mtx_t
0x180011725  call    cs:__imp__Mtx_unlock
0x18001172b  xor     al, al
0x18001172d  jmp     short loc_180011705
0x18001172f  mov     ecx, 5
0x180011734  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

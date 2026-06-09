# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180018870`
- end: `0x180018abb`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `587`
- prototype: `char __fastcall(__int64, char, char, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800021c0`
- `0x180018870`
- `0x180019d44`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180018993`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180018993`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018a06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018ab4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018a06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018ab4`
- `msvcp_win!_Cnd_broadcast` at `0x180018a20`
- `msvcp_win!_Cnd_broadcast` at `0x180018a20`
- `msvcp_win!_Mtx_unlock` at `0x18001899d`
- `msvcp_win!_Mtx_unlock` at `0x180018a2a`
- `msvcp_win!_Mtx_unlock` at `0x180018aa5`
- `msvcp_win!_Mtx_unlock` at `0x18001899d`
- `msvcp_win!_Mtx_unlock` at `0x180018a2a`
- `msvcp_win!_Mtx_unlock` at `0x180018aa5`
- `msvcp_win!_Mtx_lock` at `0x1800188ac`
- `msvcp_win!_Mtx_lock` at `0x1800189dd`
- `msvcp_win!_Mtx_lock` at `0x1800188ac`
- `msvcp_win!_Mtx_lock` at `0x1800189dd`

## pseudocode

```c
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
        v18[0] = ___7___Func_impl_no_alloc_V_lambda_1___CC____CancelAndRunContinuations____Task_impl_E_details_Concurrency__UEAA_N_N00AEBV__shared_ptr_U_ExceptionHolder_details_Concurrency___std___Z_X__V_std__6B_;
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
    JUMPOUT(0x180018ABALL);
  }
  _Mtx_unlock((_Mtx_t)v8);
  return 0;
}

```

## disassembly

```asm
0x180018870  push    rbx
0x180018872  push    rbp
0x180018873  push    rsi
0x180018874  push    rdi
0x180018875  push    r14
0x180018877  push    r15
0x180018879  sub     rsp, 88h
0x180018880  mov     rax, cs:__security_cookie
0x180018887  xor     rax, rsp
0x18001888a  mov     [rsp+0B8h+var_48], rax
0x18001888f  mov     bpl, r8b
0x180018892  mov     r14b, dl
0x180018895  mov     rbx, rcx
0x180018898  mov     rdi, [rsp+0B8h+arg_20]
0x1800188a0  lea     rsi, [rcx+20h]
0x1800188a4  mov     [rsp+0B8h+var_98], rsi
0x1800188a9  mov     rcx, rsi; _Mtx_t
0x1800188ac  call    cs:__imp__Mtx_lock
0x1800188b2  test    eax, eax
0x1800188b4  jnz     loc_180018AAF
0x1800188ba  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x1800188c1  jnz     short loc_1800188CF
0x1800188c3  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x1800188ca  jmp     loc_180018A01
0x1800188cf  mov     r15d, 2
0x1800188d5  mov     eax, [rbx+8]
0x1800188d8  test    bpl, bpl
0x1800188db  jz      short loc_180018943
0x1800188dd  cmp     eax, 4
0x1800188e0  jz      loc_180018AA2
0x1800188e6  mov     rax, [rdi+8]
0x1800188ea  test    rax, rax
0x1800188ed  jz      short loc_1800188F3
0x1800188ef  lock inc dword ptr [rax+8]
0x1800188f3  mov     rcx, [rdi+8]
0x1800188f7  mov     rax, [rdi]
0x1800188fa  mov     [rbx+10h], rax
0x1800188fe  mov     rdi, [rbx+18h]
0x180018902  mov     [rbx+18h], rcx
0x180018906  test    rdi, rdi
0x180018909  jz      short loc_180018969
0x18001890b  or      ebp, 0FFFFFFFFh
0x18001890e  mov     eax, ebp
0x180018910  lock xadd [rdi+8], eax
0x180018915  add     eax, ebp
0x180018917  jnz     short loc_180018969
0x180018919  mov     rax, [rdi]
0x18001891c  mov     rcx, rdi
0x18001891f  mov     rax, [rax]
0x180018922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018927  mov     eax, ebp
0x180018929  lock xadd [rdi+0Ch], eax
0x18001892e  add     eax, ebp
0x180018930  jnz     short loc_180018969
0x180018932  mov     rax, [rdi]
0x180018935  mov     rcx, rdi
0x180018938  mov     rax, [rax+8]
0x18001893c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018941  jmp     short loc_180018969
0x180018943  cmp     eax, 3
0x180018946  jz      loc_180018AA2
0x18001894c  mov     eax, [rbx+8]
0x18001894f  cmp     eax, 4
0x180018952  jz      loc_180018AA2
0x180018958  mov     eax, [rbx+8]
0x18001895b  cmp     eax, r15d
0x18001895e  jnz     short loc_180018969
0x180018960  test    r14b, r14b
0x180018963  jz      loc_180018AA2
0x180018969  test    r14b, r14b
0x18001896c  jz      short loc_18001897C
0x18001896e  mov     dword ptr [rbx+8], 4
0x180018975  mov     edi, 1
0x18001897a  jmp     short loc_18001899A
0x18001897c  mov     eax, [rbx+8]
0x18001897f  xor     edi, edi
0x180018981  cmp     eax, 1
0x180018984  cmovz   edi, r15d
0x180018988  mov     [rbx+8], r15d
0x18001898c  lea     rcx, [rbx+160h]
0x180018993  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x180018999  nop
0x18001899a  mov     rcx, rsi; _Mtx_t
0x18001899d  call    cs:__imp__Mtx_unlock
0x1800189a3  sub     edi, 1
0x1800189a6  jz      short loc_1800189D2
0x1800189a8  cmp     edi, 1
0x1800189ab  jnz     loc_180018A83
0x1800189b1  mov     rcx, [rbx+1B0h]
0x1800189b8  test    rcx, rcx
0x1800189bb  jz      loc_180018A83
0x1800189c1  mov     rax, [rcx]
0x1800189c4  mov     rax, [rax+10h]
0x1800189c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189cd  jmp     loc_180018A83
0x1800189d2  lea     rsi, [rbx+88h]
0x1800189d9  lea     rcx, [rsi+48h]; _Mtx_t
0x1800189dd  call    cs:__imp__Mtx_lock
0x1800189e3  test    eax, eax
0x1800189e5  jnz     loc_180018AAF
0x1800189eb  cmp     dword ptr [rsi+94h], 7FFFFFFFh
0x1800189f5  jnz     short loc_180018A0D
0x1800189f7  mov     dword ptr [rsi+94h], 7FFFFFFEh
0x180018a01  mov     ecx, 6
0x180018a06  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180018a0c  int     3; Trap to Debugger
0x180018a0d  cmp     [rsi+0B0h], r15d
0x180018a14  jge     short loc_180018A1D
0x180018a16  mov     [rsi+0B0h], r15d
0x180018a1d  mov     rcx, rsi; _Cnd_t
0x180018a20  call    cs:__imp__Cnd_broadcast
0x180018a26  lea     rcx, [rsi+48h]; _Mtx_t
0x180018a2a  call    cs:__imp__Mtx_unlock
0x180018a30  cmp     qword ptr [rbx+70h], 0
0x180018a35  jz      short loc_180018A83
0x180018a37  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?CC@??_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)'::`34'::_lambda_1_,void,>::`vftable'
0x180018a3e  mov     [rsp+0B8h+var_88], rax
0x180018a43  mov     [rsp+0B8h+var_80], rbx
0x180018a48  lea     rax, [rsp+0B8h+var_88]
0x180018a4d  mov     [rsp+0B8h+var_50], rax
0x180018a52  mov     edx, 10h
0x180018a57  lea     rcx, [rsp+0B8h+var_88]
0x180018a5c  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180018a61  nop
0x180018a62  mov     rcx, [rsp+0B8h+var_50]
0x180018a67  test    rcx, rcx
0x180018a6a  jz      short loc_180018A83
0x180018a6c  mov     rax, [rcx]
0x180018a6f  lea     rdx, [rsp+0B8h+var_88]
0x180018a74  cmp     rcx, rdx
0x180018a77  setnz   dl
0x180018a7a  mov     rax, [rax+20h]
0x180018a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a83  mov     al, 1
0x180018a85  mov     rcx, [rsp+0B8h+var_48]
0x180018a8a  xor     rcx, rsp; StackCookie
0x180018a8d  call    __security_check_cookie
0x180018a92  add     rsp, 88h
0x180018a99  pop     r15
0x180018a9b  pop     r14
0x180018a9d  pop     rdi
0x180018a9e  pop     rsi
0x180018a9f  pop     rbp
0x180018aa0  pop     rbx
0x180018aa1  retn
0x180018aa2  mov     rcx, rsi; _Mtx_t
0x180018aa5  call    cs:__imp__Mtx_unlock
0x180018aab  xor     al, al
0x180018aad  jmp     short loc_180018A85
0x180018aaf  mov     ecx, 5
0x180018ab4  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18001a6f0`
- end: `0x18001a892`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800060a0`
- `0x180017b64`
- `0x18001a6f0`
- `0x18001aba4`
- `0x18001cad4`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001a7dd`
- `msvcp_win!_Mtx_unlock` at `0x18001a86d`
- `msvcp_win!_Mtx_unlock` at `0x18001a7dd`
- `msvcp_win!_Mtx_unlock` at `0x18001a86d`
- `msvcp_win!_Mtx_lock` at `0x18001a72c`
- `msvcp_win!_Mtx_lock` at `0x18001a72c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a73b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a757`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a73b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a757`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001a7d3`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001a7d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rsi
  int v9; // eax
  int v10; // edi
  int v11; // edi
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  _QWORD v15[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-50h]

  v8 = a1 + 32;
  if ( _Mtx_lock((_Mtx_t)(a1 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v8 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v8 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v9 = *(_DWORD *)(a1 + 8);
  if ( !a3 )
  {
    if ( v9 != 3 && *(_DWORD *)(a1 + 8) != 4 && (*(_DWORD *)(a1 + 8) != 2 || a2) )
      goto LABEL_12;
LABEL_25:
    _Mtx_unlock((_Mtx_t)v8);
    return 0;
  }
  if ( v9 == 4 )
    goto LABEL_25;
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(a1 + 16, a5);
LABEL_12:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v10 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock((_Mtx_t)v8);
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      v12 = *(_QWORD *)(a1 + 432);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v15[0] = &std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable';
      v15[1] = a1;
      v16 = v15;
      Concurrency::details::_ScheduleFuncWithAutoInline(v15, 16);
      if ( v16 )
      {
        v13 = v15;
        LOBYTE(v13) = v16 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v13);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001a6f0  push    rbx
0x18001a6f2  push    rbp
0x18001a6f3  push    rsi
0x18001a6f4  push    rdi
0x18001a6f5  push    r14
0x18001a6f7  push    r15
0x18001a6f9  sub     rsp, 88h
0x18001a700  mov     rax, cs:__security_cookie
0x18001a707  xor     rax, rsp
0x18001a70a  mov     [rsp+0B8h+var_48], rax
0x18001a70f  mov     bpl, r8b
0x18001a712  mov     dil, dl
0x18001a715  mov     rbx, rcx
0x18001a718  mov     r14, [rsp+0B8h+arg_20]
0x18001a720  lea     rsi, [rcx+20h]
0x18001a724  mov     [rsp+0B8h+var_98], rsi
0x18001a729  mov     rcx, rsi; _Mtx_t
0x18001a72c  call    cs:__imp__Mtx_lock
0x18001a732  test    eax, eax
0x18001a734  jz      short loc_18001A742
0x18001a736  mov     ecx, 5
0x18001a73b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a741  int     3; Trap to Debugger
0x18001a742  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x18001a749  jnz     short loc_18001A75E
0x18001a74b  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x18001a752  mov     ecx, 6
0x18001a757  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a75d  nop
0x18001a75e  mov     r15d, 2
0x18001a764  mov     eax, [rbx+8]
0x18001a767  test    bpl, bpl
0x18001a76a  jz      short loc_18001A783
0x18001a76c  cmp     eax, 4
0x18001a76f  jz      loc_18001A86A
0x18001a775  lea     rcx, [rbx+10h]
0x18001a779  mov     rdx, r14
0x18001a77c  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x18001a781  jmp     short loc_18001A7A9
0x18001a783  cmp     eax, 3
0x18001a786  jz      loc_18001A86A
0x18001a78c  mov     eax, [rbx+8]
0x18001a78f  cmp     eax, 4
0x18001a792  jz      loc_18001A86A
0x18001a798  mov     eax, [rbx+8]
0x18001a79b  cmp     eax, r15d
0x18001a79e  jnz     short loc_18001A7A9
0x18001a7a0  test    dil, dil
0x18001a7a3  jz      loc_18001A86A
0x18001a7a9  test    dil, dil
0x18001a7ac  jz      short loc_18001A7BC
0x18001a7ae  mov     dword ptr [rbx+8], 4
0x18001a7b5  mov     edi, 1
0x18001a7ba  jmp     short loc_18001A7DA
0x18001a7bc  mov     eax, [rbx+8]
0x18001a7bf  xor     edi, edi
0x18001a7c1  cmp     eax, 1
0x18001a7c4  cmovz   edi, r15d
0x18001a7c8  mov     [rbx+8], r15d
0x18001a7cc  lea     rcx, [rbx+160h]
0x18001a7d3  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18001a7d9  nop
0x18001a7da  mov     rcx, rsi; _Mtx_t
0x18001a7dd  call    cs:__imp__Mtx_unlock
0x18001a7e3  sub     edi, 1
0x18001a7e6  jz      short loc_18001A807
0x18001a7e8  cmp     edi, 1
0x18001a7eb  jnz     short loc_18001A866
0x18001a7ed  mov     rcx, [rbx+1B0h]
0x18001a7f4  test    rcx, rcx
0x18001a7f7  jz      short loc_18001A866
0x18001a7f9  mov     rax, [rcx]
0x18001a7fc  mov     rax, [rax+10h]
0x18001a800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a805  jmp     short loc_18001A866
0x18001a807  lea     rcx, [rbx+88h]; this
0x18001a80e  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x18001a813  cmp     qword ptr [rbx+70h], 0
0x18001a818  jz      short loc_18001A866
0x18001a81a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18001a821  mov     [rsp+0B8h+var_88], rax
0x18001a826  mov     [rsp+0B8h+var_80], rbx
0x18001a82b  lea     rax, [rsp+0B8h+var_88]
0x18001a830  mov     [rsp+0B8h+var_50], rax
0x18001a835  mov     edx, 10h
0x18001a83a  lea     rcx, [rsp+0B8h+var_88]
0x18001a83f  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18001a844  nop
0x18001a845  mov     rcx, [rsp+0B8h+var_50]
0x18001a84a  test    rcx, rcx
0x18001a84d  jz      short loc_18001A866
0x18001a84f  mov     rax, [rcx]
0x18001a852  lea     rdx, [rsp+0B8h+var_88]
0x18001a857  cmp     rcx, rdx
0x18001a85a  setnz   dl
0x18001a85d  mov     rax, [rax+20h]
0x18001a861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a866  mov     al, 1
0x18001a868  jmp     short loc_18001A875
0x18001a86a  mov     rcx, rsi; _Mtx_t
0x18001a86d  call    cs:__imp__Mtx_unlock
0x18001a873  xor     al, al
0x18001a875  mov     rcx, [rsp+0B8h+var_48]
0x18001a87a  xor     rcx, rsp; StackCookie
0x18001a87d  call    __security_check_cookie
0x18001a882  add     rsp, 88h
0x18001a889  pop     r15
0x18001a88b  pop     r14
0x18001a88d  pop     rdi
0x18001a88e  pop     rsi
0x18001a88f  pop     rbp
0x18001a890  pop     rbx
0x18001a891  retn
```

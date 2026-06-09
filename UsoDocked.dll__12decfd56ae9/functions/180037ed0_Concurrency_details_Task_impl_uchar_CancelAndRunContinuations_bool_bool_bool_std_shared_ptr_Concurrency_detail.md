# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180037ed0`
- end: `0x1800380ad`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180037ed0`
- `0x180038654`
- `0x180039e74`
- `0x180071010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180037ff6`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180037ff6`
- `msvcp_win!_Mtx_unlock` at `0x180038000`
- `msvcp_win!_Mtx_unlock` at `0x180038090`
- `msvcp_win!_Mtx_unlock` at `0x180038000`
- `msvcp_win!_Mtx_unlock` at `0x180038090`
- `msvcp_win!_Mtx_lock` at `0x180037ef7`
- `msvcp_win!_Mtx_lock` at `0x180037ef7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180037f06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180037f22`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180037f06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180037f22`

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
  _QWORD v18[7]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v19; // [rsp+58h] [rbp-20h]

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
      goto LABEL_17;
    }
LABEL_30:
    _Mtx_unlock((_Mtx_t)v8);
    return 0;
  }
  if ( v9 == 3 || *(_DWORD *)(a1 + 8) == 4 || *(_DWORD *)(a1 + 8) == 2 && !a2 )
    goto LABEL_30;
LABEL_17:
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
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
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
  }
  return 1;
}

```

## disassembly

```asm
0x180037ed0  mov     rax, rsp
0x180037ed3  mov     [rax+10h], rbx
0x180037ed7  mov     [rax+18h], rbp
0x180037edb  push    rsi
0x180037edc  push    rdi
0x180037edd  push    r15
0x180037edf  sub     rsp, 60h
0x180037ee3  mov     dil, r8b
0x180037ee6  mov     bpl, dl
0x180037ee9  mov     rbx, rcx
0x180037eec  lea     rsi, [rcx+20h]
0x180037ef0  mov     [rax+8], rsi
0x180037ef4  mov     rcx, rsi; _Mtx_t
0x180037ef7  call    cs:__imp__Mtx_lock
0x180037efd  test    eax, eax
0x180037eff  jz      short loc_180037F0D
0x180037f01  mov     ecx, 5
0x180037f06  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180037f0c  int     3; Trap to Debugger
0x180037f0d  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180037f14  jnz     short loc_180037F29
0x180037f16  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x180037f1d  mov     ecx, 6
0x180037f22  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180037f28  nop
0x180037f29  mov     r15d, 2
0x180037f2f  mov     eax, [rbx+8]
0x180037f32  test    dil, dil
0x180037f35  jz      short loc_180037FA6
0x180037f37  cmp     eax, 4
0x180037f3a  jz      loc_18003808D
0x180037f40  mov     rdx, [rsp+78h+arg_20]
0x180037f48  mov     rax, [rdx+8]
0x180037f4c  test    rax, rax
0x180037f4f  jz      short loc_180037F55
0x180037f51  lock inc dword ptr [rax+8]
0x180037f55  mov     rcx, [rdx+8]
0x180037f59  mov     rax, [rdx]
0x180037f5c  mov     [rbx+10h], rax
0x180037f60  mov     rdi, [rbx+18h]
0x180037f64  mov     [rbx+18h], rcx
0x180037f68  test    rdi, rdi
0x180037f6b  jz      short loc_180037FCC
0x180037f6d  or      eax, 0FFFFFFFFh
0x180037f70  lock xadd [rdi+8], eax
0x180037f75  cmp     eax, 1
0x180037f78  jnz     short loc_180037FCC
0x180037f7a  mov     rax, [rdi]
0x180037f7d  mov     rcx, rdi
0x180037f80  mov     rax, [rax]
0x180037f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f88  or      eax, 0FFFFFFFFh
0x180037f8b  lock xadd [rdi+0Ch], eax
0x180037f90  cmp     eax, 1
0x180037f93  jnz     short loc_180037FCC
0x180037f95  mov     rax, [rdi]
0x180037f98  mov     rcx, rdi
0x180037f9b  mov     rax, [rax+8]
0x180037f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fa4  jmp     short loc_180037FCC
0x180037fa6  cmp     eax, 3
0x180037fa9  jz      loc_18003808D
0x180037faf  mov     eax, [rbx+8]
0x180037fb2  cmp     eax, 4
0x180037fb5  jz      loc_18003808D
0x180037fbb  mov     eax, [rbx+8]
0x180037fbe  cmp     eax, r15d
0x180037fc1  jnz     short loc_180037FCC
0x180037fc3  test    bpl, bpl
0x180037fc6  jz      loc_18003808D
0x180037fcc  test    bpl, bpl
0x180037fcf  jz      short loc_180037FDF
0x180037fd1  mov     dword ptr [rbx+8], 4
0x180037fd8  mov     edi, 1
0x180037fdd  jmp     short loc_180037FFD
0x180037fdf  mov     eax, [rbx+8]
0x180037fe2  xor     edi, edi
0x180037fe4  cmp     eax, 1
0x180037fe7  cmovz   edi, r15d
0x180037feb  mov     [rbx+8], r15d
0x180037fef  lea     rcx, [rbx+160h]
0x180037ff6  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x180037ffc  nop
0x180037ffd  mov     rcx, rsi; _Mtx_t
0x180038000  call    cs:__imp__Mtx_unlock
0x180038006  sub     edi, 1
0x180038009  jz      short loc_18003802A
0x18003800b  cmp     edi, 1
0x18003800e  jnz     short loc_180038089
0x180038010  mov     rcx, [rbx+1B0h]
0x180038017  test    rcx, rcx
0x18003801a  jz      short loc_180038089
0x18003801c  mov     rax, [rcx]
0x18003801f  mov     rax, [rax+10h]
0x180038023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038028  jmp     short loc_180038089
0x18003802a  lea     rcx, [rbx+88h]; this
0x180038031  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x180038036  cmp     qword ptr [rbx+70h], 0
0x18003803b  jz      short loc_180038089
0x18003803d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x180038044  mov     [rsp+78h+var_58], rax
0x180038049  mov     [rsp+78h+var_50], rbx
0x18003804e  lea     rax, [rsp+78h+var_58]
0x180038053  mov     [rsp+78h+var_20], rax
0x180038058  mov     edx, 10h
0x18003805d  lea     rcx, [rsp+78h+var_58]
0x180038062  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180038067  nop
0x180038068  mov     rcx, [rsp+78h+var_20]
0x18003806d  test    rcx, rcx
0x180038070  jz      short loc_180038089
0x180038072  mov     rax, [rcx]
0x180038075  lea     rdx, [rsp+78h+var_58]
0x18003807a  cmp     rcx, rdx
0x18003807d  setnz   dl
0x180038080  mov     rax, [rax+20h]
0x180038084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038089  mov     al, 1
0x18003808b  jmp     short loc_180038098
0x18003808d  mov     rcx, rsi; _Mtx_t
0x180038090  call    cs:__imp__Mtx_unlock
0x180038096  xor     al, al
0x180038098  lea     r11, [rsp+78h+var_18]
0x18003809d  mov     rbx, [r11+28h]
0x1800380a1  mov     rbp, [r11+30h]
0x1800380a5  mov     rsp, r11
0x1800380a8  pop     r15
0x1800380aa  pop     rdi
0x1800380ab  pop     rsi
0x1800380ac  retn
```

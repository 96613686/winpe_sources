# Concurrency::details::_Task_impl<DockedClient::AppInstallResult>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1800380c0`
- end: `0x18003829d`
- name: `?_CancelAndRunContinuations@?$_Task_impl@UAppInstallResult@DockedClient@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800380c0`
- `0x180038654`
- `0x180039e74`
- `0x180071010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800381e6`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800381e6`
- `msvcp_win!_Mtx_unlock` at `0x1800381f0`
- `msvcp_win!_Mtx_unlock` at `0x180038280`
- `msvcp_win!_Mtx_unlock` at `0x1800381f0`
- `msvcp_win!_Mtx_unlock` at `0x180038280`
- `msvcp_win!_Mtx_lock` at `0x1800380e7`
- `msvcp_win!_Mtx_lock` at `0x1800380e7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800380f6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180038112`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800380f6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180038112`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<DockedClient::AppInstallResult>::_CancelAndRunContinuations(
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
      v15 = *(_QWORD *)(a1 + 448);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v18[0] = &std::_Func_impl_no_alloc<_lambda_d2af353603cf5f3cc1bcca3cbaa9de62_,void,>::`vftable';
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
0x1800380c0  mov     rax, rsp
0x1800380c3  mov     [rax+10h], rbx
0x1800380c7  mov     [rax+18h], rbp
0x1800380cb  push    rsi
0x1800380cc  push    rdi
0x1800380cd  push    r15
0x1800380cf  sub     rsp, 60h
0x1800380d3  mov     dil, r8b
0x1800380d6  mov     bpl, dl
0x1800380d9  mov     rbx, rcx
0x1800380dc  lea     rsi, [rcx+20h]
0x1800380e0  mov     [rax+8], rsi
0x1800380e4  mov     rcx, rsi; _Mtx_t
0x1800380e7  call    cs:__imp__Mtx_lock
0x1800380ed  test    eax, eax
0x1800380ef  jz      short loc_1800380FD
0x1800380f1  mov     ecx, 5
0x1800380f6  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800380fc  int     3; Trap to Debugger
0x1800380fd  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180038104  jnz     short loc_180038119
0x180038106  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x18003810d  mov     ecx, 6
0x180038112  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180038118  nop
0x180038119  mov     r15d, 2
0x18003811f  mov     eax, [rbx+8]
0x180038122  test    dil, dil
0x180038125  jz      short loc_180038196
0x180038127  cmp     eax, 4
0x18003812a  jz      loc_18003827D
0x180038130  mov     rdx, [rsp+78h+arg_20]
0x180038138  mov     rax, [rdx+8]
0x18003813c  test    rax, rax
0x18003813f  jz      short loc_180038145
0x180038141  lock inc dword ptr [rax+8]
0x180038145  mov     rcx, [rdx+8]
0x180038149  mov     rax, [rdx]
0x18003814c  mov     [rbx+10h], rax
0x180038150  mov     rdi, [rbx+18h]
0x180038154  mov     [rbx+18h], rcx
0x180038158  test    rdi, rdi
0x18003815b  jz      short loc_1800381BC
0x18003815d  or      eax, 0FFFFFFFFh
0x180038160  lock xadd [rdi+8], eax
0x180038165  cmp     eax, 1
0x180038168  jnz     short loc_1800381BC
0x18003816a  mov     rax, [rdi]
0x18003816d  mov     rcx, rdi
0x180038170  mov     rax, [rax]
0x180038173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038178  or      eax, 0FFFFFFFFh
0x18003817b  lock xadd [rdi+0Ch], eax
0x180038180  cmp     eax, 1
0x180038183  jnz     short loc_1800381BC
0x180038185  mov     rax, [rdi]
0x180038188  mov     rcx, rdi
0x18003818b  mov     rax, [rax+8]
0x18003818f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038194  jmp     short loc_1800381BC
0x180038196  cmp     eax, 3
0x180038199  jz      loc_18003827D
0x18003819f  mov     eax, [rbx+8]
0x1800381a2  cmp     eax, 4
0x1800381a5  jz      loc_18003827D
0x1800381ab  mov     eax, [rbx+8]
0x1800381ae  cmp     eax, r15d
0x1800381b1  jnz     short loc_1800381BC
0x1800381b3  test    bpl, bpl
0x1800381b6  jz      loc_18003827D
0x1800381bc  test    bpl, bpl
0x1800381bf  jz      short loc_1800381CF
0x1800381c1  mov     dword ptr [rbx+8], 4
0x1800381c8  mov     edi, 1
0x1800381cd  jmp     short loc_1800381ED
0x1800381cf  mov     eax, [rbx+8]
0x1800381d2  xor     edi, edi
0x1800381d4  cmp     eax, 1
0x1800381d7  cmovz   edi, r15d
0x1800381db  mov     [rbx+8], r15d
0x1800381df  lea     rcx, [rbx+160h]
0x1800381e6  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x1800381ec  nop
0x1800381ed  mov     rcx, rsi; _Mtx_t
0x1800381f0  call    cs:__imp__Mtx_unlock
0x1800381f6  sub     edi, 1
0x1800381f9  jz      short loc_18003821A
0x1800381fb  cmp     edi, 1
0x1800381fe  jnz     short loc_180038279
0x180038200  mov     rcx, [rbx+1C0h]
0x180038207  test    rcx, rcx
0x18003820a  jz      short loc_180038279
0x18003820c  mov     rax, [rcx]
0x18003820f  mov     rax, [rax+10h]
0x180038213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038218  jmp     short loc_180038279
0x18003821a  lea     rcx, [rbx+88h]; this
0x180038221  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x180038226  cmp     qword ptr [rbx+70h], 0
0x18003822b  jz      short loc_180038279
0x18003822d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d2af353603cf5f3cc1bcca3cbaa9de62_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d2af353603cf5f3cc1bcca3cbaa9de62_,void,>::`vftable'
0x180038234  mov     [rsp+78h+var_58], rax
0x180038239  mov     [rsp+78h+var_50], rbx
0x18003823e  lea     rax, [rsp+78h+var_58]
0x180038243  mov     [rsp+78h+var_20], rax
0x180038248  mov     edx, 10h
0x18003824d  lea     rcx, [rsp+78h+var_58]
0x180038252  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180038257  nop
0x180038258  mov     rcx, [rsp+78h+var_20]
0x18003825d  test    rcx, rcx
0x180038260  jz      short loc_180038279
0x180038262  mov     rax, [rcx]
0x180038265  lea     rdx, [rsp+78h+var_58]
0x18003826a  cmp     rcx, rdx
0x18003826d  setnz   dl
0x180038270  mov     rax, [rax+20h]
0x180038274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038279  mov     al, 1
0x18003827b  jmp     short loc_180038288
0x18003827d  mov     rcx, rsi; _Mtx_t
0x180038280  call    cs:__imp__Mtx_unlock
0x180038286  xor     al, al
0x180038288  lea     r11, [rsp+78h+var_18]
0x18003828d  mov     rbx, [r11+28h]
0x180038291  mov     rbp, [r11+30h]
0x180038295  mov     rsp, r11
0x180038298  pop     r15
0x18003829a  pop     rdi
0x18003829b  pop     rsi
0x18003829c  retn
```

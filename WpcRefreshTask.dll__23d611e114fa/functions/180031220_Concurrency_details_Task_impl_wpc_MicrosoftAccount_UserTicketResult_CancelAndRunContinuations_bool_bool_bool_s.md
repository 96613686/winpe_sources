# Concurrency::details::_Task_impl<wpc::MicrosoftAccount::UserTicketResult>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180031220`
- end: `0x1800313c2`
- name: `?_CancelAndRunContinuations@?$_Task_impl@UUserTicketResult@MicrosoftAccount@wpc@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800060a0`
- `0x180017b64`
- `0x18001aba4`
- `0x18001cad4`
- `0x180031220`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003130d`
- `msvcp_win!_Mtx_unlock` at `0x18003139d`
- `msvcp_win!_Mtx_unlock` at `0x18003130d`
- `msvcp_win!_Mtx_unlock` at `0x18003139d`
- `msvcp_win!_Mtx_lock` at `0x18003125c`
- `msvcp_win!_Mtx_lock` at `0x18003125c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003126b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031287`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003126b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031287`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031303`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031303`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<wpc::MicrosoftAccount::UserTicketResult>::_CancelAndRunContinuations(
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
      v12 = *(_QWORD *)(a1 + 496);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v15[0] = &std::_Func_impl_no_alloc<_lambda_52f2dd22679f7dd66c058c0621fea55c_,void,>::`vftable';
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
0x180031220  push    rbx
0x180031222  push    rbp
0x180031223  push    rsi
0x180031224  push    rdi
0x180031225  push    r14
0x180031227  push    r15
0x180031229  sub     rsp, 88h
0x180031230  mov     rax, cs:__security_cookie
0x180031237  xor     rax, rsp
0x18003123a  mov     [rsp+0B8h+var_48], rax
0x18003123f  mov     bpl, r8b
0x180031242  mov     dil, dl
0x180031245  mov     rbx, rcx
0x180031248  mov     r14, [rsp+0B8h+arg_20]
0x180031250  lea     rsi, [rcx+20h]
0x180031254  mov     [rsp+0B8h+var_98], rsi
0x180031259  mov     rcx, rsi; _Mtx_t
0x18003125c  call    cs:__imp__Mtx_lock
0x180031262  test    eax, eax
0x180031264  jz      short loc_180031272
0x180031266  mov     ecx, 5
0x18003126b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180031271  int     3; Trap to Debugger
0x180031272  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180031279  jnz     short loc_18003128E
0x18003127b  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x180031282  mov     ecx, 6
0x180031287  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003128d  nop
0x18003128e  mov     r15d, 2
0x180031294  mov     eax, [rbx+8]
0x180031297  test    bpl, bpl
0x18003129a  jz      short loc_1800312B3
0x18003129c  cmp     eax, 4
0x18003129f  jz      loc_18003139A
0x1800312a5  lea     rcx, [rbx+10h]
0x1800312a9  mov     rdx, r14
0x1800312ac  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x1800312b1  jmp     short loc_1800312D9
0x1800312b3  cmp     eax, 3
0x1800312b6  jz      loc_18003139A
0x1800312bc  mov     eax, [rbx+8]
0x1800312bf  cmp     eax, 4
0x1800312c2  jz      loc_18003139A
0x1800312c8  mov     eax, [rbx+8]
0x1800312cb  cmp     eax, r15d
0x1800312ce  jnz     short loc_1800312D9
0x1800312d0  test    dil, dil
0x1800312d3  jz      loc_18003139A
0x1800312d9  test    dil, dil
0x1800312dc  jz      short loc_1800312EC
0x1800312de  mov     dword ptr [rbx+8], 4
0x1800312e5  mov     edi, 1
0x1800312ea  jmp     short loc_18003130A
0x1800312ec  mov     eax, [rbx+8]
0x1800312ef  xor     edi, edi
0x1800312f1  cmp     eax, 1
0x1800312f4  cmovz   edi, r15d
0x1800312f8  mov     [rbx+8], r15d
0x1800312fc  lea     rcx, [rbx+160h]
0x180031303  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x180031309  nop
0x18003130a  mov     rcx, rsi; _Mtx_t
0x18003130d  call    cs:__imp__Mtx_unlock
0x180031313  sub     edi, 1
0x180031316  jz      short loc_180031337
0x180031318  cmp     edi, 1
0x18003131b  jnz     short loc_180031396
0x18003131d  mov     rcx, [rbx+1F0h]
0x180031324  test    rcx, rcx
0x180031327  jz      short loc_180031396
0x180031329  mov     rax, [rcx]
0x18003132c  mov     rax, [rax+10h]
0x180031330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031335  jmp     short loc_180031396
0x180031337  lea     rcx, [rbx+88h]; this
0x18003133e  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x180031343  cmp     qword ptr [rbx+70h], 0
0x180031348  jz      short loc_180031396
0x18003134a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_52f2dd22679f7dd66c058c0621fea55c_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_52f2dd22679f7dd66c058c0621fea55c_,void,>::`vftable'
0x180031351  mov     [rsp+0B8h+var_88], rax
0x180031356  mov     [rsp+0B8h+var_80], rbx
0x18003135b  lea     rax, [rsp+0B8h+var_88]
0x180031360  mov     [rsp+0B8h+var_50], rax
0x180031365  mov     edx, 10h
0x18003136a  lea     rcx, [rsp+0B8h+var_88]
0x18003136f  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180031374  nop
0x180031375  mov     rcx, [rsp+0B8h+var_50]
0x18003137a  test    rcx, rcx
0x18003137d  jz      short loc_180031396
0x18003137f  mov     rax, [rcx]
0x180031382  lea     rdx, [rsp+0B8h+var_88]
0x180031387  cmp     rcx, rdx
0x18003138a  setnz   dl
0x18003138d  mov     rax, [rax+20h]
0x180031391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031396  mov     al, 1
0x180031398  jmp     short loc_1800313A5
0x18003139a  mov     rcx, rsi; _Mtx_t
0x18003139d  call    cs:__imp__Mtx_unlock
0x1800313a3  xor     al, al
0x1800313a5  mov     rcx, [rsp+0B8h+var_48]
0x1800313aa  xor     rcx, rsp; StackCookie
0x1800313ad  call    __security_check_cookie
0x1800313b2  add     rsp, 88h
0x1800313b9  pop     r15
0x1800313bb  pop     r14
0x1800313bd  pop     rdi
0x1800313be  pop     rsi
0x1800313bf  pop     rbp
0x1800313c0  pop     rbx
0x1800313c1  retn
```

# Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_9d82ec9d7c57bba983cfcd01f0b94018_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x180109440`
- end: `0x180109588`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_9d82ec9d7c57bba983cfcd01f0b94018_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180143c20`

## callees

- `0x18010338c`
- `0x180109440`
- `0x180109590`
- `0x18014363c`
- `0x180143cb4`
- `0x180241010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180109522`
- `msvcp_win!_Mtx_unlock` at `0x180109531`
- `msvcp_win!_Mtx_unlock` at `0x180109567`
- `msvcp_win!_Mtx_unlock` at `0x180109522`
- `msvcp_win!_Mtx_unlock` at `0x180109531`
- `msvcp_win!_Mtx_unlock` at `0x180109567`
- `msvcp_win!_Cnd_broadcast` at `0x18010955d`
- `msvcp_win!_Cnd_broadcast` at `0x18010955d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801094bf`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801094bf`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801094d7`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801094d7`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801094af`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801094af`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_9d82ec9d7c57bba983cfcd01f0b94018_,Concurrency::details::_TypeSelectorNoAsync>::_Init(
        __int64 a1)
{
  __int64 v2; // rdi
  Concurrency::details::_TaskEventLogger *v3; // rsi
  char v4; // bl
  _BYTE *v5; // rdx
  struct _Mtx_internal_imp_t *v6; // rcx
  _QWORD v7[8]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v8[56]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE *v9; // [rsp+98h] [rbp+3Fh]

  v2 = *(_QWORD *)(a1 + 8);
  v7[0] = &std::_Func_impl_no_alloc<_lambda_9d82ec9d7c57bba983cfcd01f0b94018_,void,>::`vftable';
  v7[1] = *(_QWORD *)(a1 + 24);
  v7[7] = v7;
  Concurrency::details::_MakeVoidToUnitFunc(v8, v7);
  std::function<unsigned long (PolicyParameters)>::~function<unsigned long (PolicyParameters)>(v7);
  v3 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v3);
  if ( !v9 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v4 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v9 + 16LL))(v9);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v3);
  if ( v9 )
  {
    v5 = v8;
    LOBYTE(v5) = v9 != v8;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v9 + 32LL))(v9, v5);
    v9 = 0;
  }
  *(_BYTE *)(v2 + 368) = v4;
  std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 32));
  v6 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v6);
  }
  else
  {
    *(_DWORD *)(v2 + 8) = 3;
    _Mtx_unlock(v6);
    std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 208));
    if ( *(int *)(v2 + 312) < 2 )
      *(_DWORD *)(v2 + 312) = 2;
    _Cnd_broadcast((_Cnd_t)(v2 + 136));
    _Mtx_unlock((_Mtx_t)(v2 + 208));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x180109440  mov     [rsp-8+arg_18], rbx
0x180109445  push    rbp
0x180109446  push    rsi
0x180109447  push    rdi
0x180109448  lea     rbp, [rsp-47h]
0x18010944d  sub     rsp, 0A0h
0x180109454  mov     rbx, rcx
0x180109457  mov     rdi, [rcx+8]
0x18010945b  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_9d82ec9d7c57bba983cfcd01f0b94018_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_9d82ec9d7c57bba983cfcd01f0b94018_,void,>::`vftable'
0x180109462  mov     [rbp+57h+var_90], rax
0x180109466  mov     rax, [rcx+18h]
0x18010946a  mov     [rbp+57h+var_88], rax
0x18010946e  lea     rax, [rbp+57h+var_90]
0x180109472  mov     [rbp+57h+var_58], rax
0x180109476  lea     rax, [rbp+57h+var_90]
0x18010947a  mov     [rbp+57h+arg_0], rax
0x18010947e  lea     rdx, [rbp+57h+var_90]
0x180109482  lea     rcx, [rbp+57h+var_50]
0x180109486  call    ?_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@4@@Z; Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)
0x18010948b  nop
0x18010948c  lea     rcx, [rbp+57h+var_90]
0x180109490  call    ??1?$function@$$A6AKUPolicyParameters@@@Z@std@@QEAA@XZ; std::function<ulong (PolicyParameters)>::~function<ulong (PolicyParameters)>(void)
0x180109495  lea     rax, [rbp+57h+var_50]
0x180109499  mov     [rbp+57h+arg_0], rax
0x18010949d  mov     rsi, [rbx+8]
0x1801094a1  add     rsi, 160h
0x1801094a8  mov     [rbp+57h+arg_10], rsi
0x1801094ac  mov     rcx, rsi
0x1801094af  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801094b5  nop
0x1801094b6  mov     rcx, [rbp+57h+var_18]
0x1801094ba  test    rcx, rcx
0x1801094bd  jnz     short loc_1801094C6
0x1801094bf  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801094c5  int     3; Trap to Debugger
0x1801094c6  mov     rax, [rcx]
0x1801094c9  mov     rax, [rax+10h]
0x1801094cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801094d2  mov     bl, al
0x1801094d4  mov     rcx, rsi
0x1801094d7  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801094dd  nop
0x1801094de  mov     rcx, [rbp+57h+var_18]
0x1801094e2  test    rcx, rcx
0x1801094e5  jz      short loc_180109505
0x1801094e7  mov     rax, [rcx]
0x1801094ea  lea     rdx, [rbp+57h+var_50]
0x1801094ee  cmp     rcx, rdx
0x1801094f1  setnz   dl
0x1801094f4  mov     rax, [rax+20h]
0x1801094f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801094fd  mov     [rbp+57h+var_18], 0
0x180109505  mov     [rdi+170h], bl
0x18010950b  lea     rbx, [rdi+20h]
0x18010950f  mov     rcx, rbx; this
0x180109512  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180109517  mov     eax, [rdi+8]
0x18010951a  mov     rcx, rbx; _Mtx_t
0x18010951d  cmp     eax, 4
0x180109520  jnz     short loc_18010952A
0x180109522  call    cs:__imp__Mtx_unlock
0x180109528  jmp     short loc_180109575
0x18010952a  mov     dword ptr [rdi+8], 3
0x180109531  call    cs:__imp__Mtx_unlock
0x180109537  lea     rbx, [rdi+88h]
0x18010953e  lea     rcx, [rbx+48h]; this
0x180109542  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180109547  cmp     dword ptr [rbx+0B0h], 2
0x18010954e  jge     short loc_18010955A
0x180109550  mov     dword ptr [rbx+0B0h], 2
0x18010955a  mov     rcx, rbx; _Cnd_t
0x18010955d  call    cs:__imp__Cnd_broadcast
0x180109563  lea     rcx, [rbx+48h]; _Mtx_t
0x180109567  call    cs:__imp__Mtx_unlock
0x18010956d  mov     rcx, rdi; this
0x180109570  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x180109575  mov     rbx, [rsp+0B0h+arg_18]
0x18010957d  add     rsp, 0A0h
0x180109584  pop     rdi
0x180109585  pop     rsi
0x180109586  pop     rbp
0x180109587  retn
```

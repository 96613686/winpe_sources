# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x18001709c`
- end: `0x18001712e`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `146`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017004`
- `0x180018800`
- `0x1800a3892`

## callees

- `0x18001709c`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180017112`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180017112`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800170be`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800170be`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[5] + 352LL));
  v2 = (volatile signed __int32 *)a1[6];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  *a1 = &Concurrency::details::_ContinuationTaskHandleBase::`vftable';
  Concurrency::details::_ContextCallback::_Reset((Concurrency::details::_ContextCallback *)(a1 + 2));
  result = &Concurrency::details::_TaskProcHandle::`vftable';
  *a1 = &Concurrency::details::_TaskProcHandle::`vftable';
  return result;
}

```

## disassembly

```asm
0x18001709c  mov     [rsp+arg_0], rbx
0x1800170a1  push    rdi
0x1800170a2  sub     rsp, 20h
0x1800170a6  mov     rdi, rcx
0x1800170a9  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x1800170b0  mov     [rcx], rax
0x1800170b3  mov     rcx, [rcx+28h]
0x1800170b7  add     rcx, 160h
0x1800170be  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x1800170c4  mov     rbx, [rdi+30h]
0x1800170c8  test    rbx, rbx
0x1800170cb  jz      short loc_180017104
0x1800170cd  or      eax, 0FFFFFFFFh
0x1800170d0  lock xadd [rbx+8], eax
0x1800170d5  cmp     eax, 1
0x1800170d8  jnz     short loc_180017104
0x1800170da  mov     rax, [rbx]
0x1800170dd  mov     rcx, rbx
0x1800170e0  mov     rax, [rax]
0x1800170e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e8  or      eax, 0FFFFFFFFh
0x1800170eb  lock xadd [rbx+0Ch], eax
0x1800170f0  cmp     eax, 1
0x1800170f3  jnz     short loc_180017104
0x1800170f5  mov     rax, [rbx]
0x1800170f8  mov     rcx, rbx
0x1800170fb  mov     rax, [rax+8]
0x1800170ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017104  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x18001710b  mov     [rdi], rax
0x18001710e  lea     rcx, [rdi+10h]
0x180017112  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x180017118  nop
0x180017119  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x180017120  mov     [rdi], rax
0x180017123  mov     rbx, [rsp+28h+arg_0]
0x180017128  add     rsp, 20h
0x18001712c  pop     rdi
0x18001712d  retn
```

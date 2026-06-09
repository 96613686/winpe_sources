# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x18003017c`
- end: `0x18003020e`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@UUserTicketResult@MicrosoftAccount@wpc@@XV?$function@$$A6AXV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800300e4`
- `0x180030ac0`
- `0x1800a54a5`

## callees

- `0x18003017c`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800301f2`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800301f2`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003019e`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003019e`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
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
0x18003017c  mov     [rsp+arg_0], rbx
0x180030181  push    rdi
0x180030182  sub     rsp, 20h
0x180030186  mov     rdi, rcx
0x180030189  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@UUserTicketResult@MicrosoftAccount@wpc@@XV?$function@$$A6AXV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x180030190  mov     [rcx], rax
0x180030193  mov     rcx, [rcx+28h]
0x180030197  add     rcx, 160h
0x18003019e  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x1800301a4  mov     rbx, [rdi+30h]
0x1800301a8  test    rbx, rbx
0x1800301ab  jz      short loc_1800301E4
0x1800301ad  or      eax, 0FFFFFFFFh
0x1800301b0  lock xadd [rbx+8], eax
0x1800301b5  cmp     eax, 1
0x1800301b8  jnz     short loc_1800301E4
0x1800301ba  mov     rax, [rbx]
0x1800301bd  mov     rcx, rbx
0x1800301c0  mov     rax, [rax]
0x1800301c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301c8  or      eax, 0FFFFFFFFh
0x1800301cb  lock xadd [rbx+0Ch], eax
0x1800301d0  cmp     eax, 1
0x1800301d3  jnz     short loc_1800301E4
0x1800301d5  mov     rax, [rbx]
0x1800301d8  mov     rcx, rbx
0x1800301db  mov     rax, [rax+8]
0x1800301df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301e4  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x1800301eb  mov     [rdi], rax
0x1800301ee  lea     rcx, [rdi+10h]
0x1800301f2  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x1800301f8  nop
0x1800301f9  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x180030200  mov     [rdi], rax
0x180030203  mov     rbx, [rsp+28h+arg_0]
0x180030208  add     rsp, 20h
0x18003020c  pop     rdi
0x18003020d  retn
```

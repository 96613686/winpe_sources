# Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(std::shared_ptr<Concurrency::details::_Task_impl<wpc::MicrosoftAccount::UserTicketResult>> const &,std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)> const &,Concurrency::task_continuation_context const &,Concurrency::details::_TaskInliningMode)

- ea: `0x18002fe74`
- end: `0x18002ffc9`
- name: `??0?$_ContinuationTaskHandle@UUserTicketResult@MicrosoftAccount@wpc@@XV?$function@$$A6AXV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UUserTicketResult@MicrosoftAccount@wpc@@@details@Concurrency@@@std@@AEBV?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@4@AEBV?$function@$$A6AXV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@Z@4@AEBVtask_continuation_context@2@W4_TaskInliningMode@details@2@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fb98`

## callees

- `0x18002fe74`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18002ffa6`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18002ffa6`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18002ff6a`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18002ff6a`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x18002ff99`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x18002ff99`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18002feb0`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18002feb0`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x18002ff76`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x18002ff76`

## pseudocode

```c
__int64 __fastcall Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  Concurrency::details::_ContextCallback *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, __int64); // rcx
  char v14; // dl

  *(_QWORD *)a1 = &Concurrency::details::_ContinuationTaskHandleBase::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  v10 = (Concurrency::details::_ContextCallback *)(a1 + 16);
  Concurrency::task_continuation_context::task_continuation_context((Concurrency::task_continuation_context *)(a1 + 16));
  *(_BYTE *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  v11 = a3[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 40) = *a3;
  *(_QWORD *)(a1 + 48) = a3[1];
  *(_QWORD *)a1 = &Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  v12 = a2[1];
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  *(_QWORD *)(a1 + 56) = *a2;
  *(_QWORD *)(a1 + 64) = a2[1];
  *(_QWORD *)(a1 + 128) = 0;
  v13 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a4 + 56);
  if ( v13 )
    *(_QWORD *)(a1 + 128) = (**v13)(v13, a1 + 72);
  *(_BYTE *)(a1 + 32) = 1;
  if ( v10 != (Concurrency::details::_ContextCallback *)a5 )
  {
    Concurrency::details::_ContextCallback::_Reset(v10);
    Concurrency::details::_ContextCallback::_Assign(v10, *(void **)a5);
  }
  *((_BYTE *)v10 + 8) = *(_BYTE *)(a5 + 8);
  if ( *(_QWORD *)v10 == 1 )
  {
    v14 = *(_BYTE *)(*a2 + 12LL);
    *(_QWORD *)v10 = 0;
    if ( v14 )
    {
      if ( (unsigned __int8)Concurrency::details::_ContextCallback::_IsCurrentOriginSTA() )
        Concurrency::details::_ContextCallback::_Capture(v10);
    }
  }
  *(_DWORD *)(a1 + 36) = a6;
  return a1;
}

```

## disassembly

```asm
0x18002fe74  mov     [rsp+arg_10], rbx
0x18002fe79  mov     [rsp+arg_18], rbp
0x18002fe7e  mov     [rsp+arg_0], rcx
0x18002fe83  push    rsi
0x18002fe84  push    rdi
0x18002fe85  push    r14
0x18002fe87  sub     rsp, 20h
0x18002fe8b  mov     rbp, r9
0x18002fe8e  mov     rsi, r8
0x18002fe91  mov     r14, rdx
0x18002fe94  mov     rbx, rcx
0x18002fe97  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x18002fe9e  mov     [rcx], rax
0x18002fea1  mov     qword ptr [rcx+8], 0
0x18002fea9  lea     rdi, [rcx+10h]
0x18002fead  mov     rcx, rdi
0x18002feb0  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x18002feb6  mov     byte ptr [rbx+20h], 0
0x18002feba  mov     dword ptr [rbx+24h], 0
0x18002fec1  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@UUserTicketResult@MicrosoftAccount@wpc@@XV?$function@$$A6AXV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x18002fec8  mov     [rbx], rax
0x18002fecb  mov     qword ptr [rbx+28h], 0
0x18002fed3  mov     qword ptr [rbx+30h], 0
0x18002fedb  mov     rax, [rsi+8]
0x18002fedf  test    rax, rax
0x18002fee2  jz      short loc_18002FEE8
0x18002fee4  lock inc dword ptr [rax+8]
0x18002fee8  mov     rax, [rsi]
0x18002feeb  mov     [rbx+28h], rax
0x18002feef  mov     rax, [rsi+8]
0x18002fef3  mov     [rbx+30h], rax
0x18002fef7  lea     rax, ??_7?$_ContinuationTaskHandle@UUserTicketResult@MicrosoftAccount@wpc@@XV?$function@$$A6AXV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@6B@; const Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18002fefe  mov     [rbx], rax
0x18002ff01  mov     qword ptr [rbx+38h], 0
0x18002ff09  mov     qword ptr [rbx+40h], 0
0x18002ff11  mov     rax, [r14+8]
0x18002ff15  test    rax, rax
0x18002ff18  jz      short loc_18002FF1E
0x18002ff1a  lock inc dword ptr [rax+8]
0x18002ff1e  mov     rax, [r14]
0x18002ff21  mov     [rbx+38h], rax
0x18002ff25  mov     rax, [r14+8]
0x18002ff29  mov     [rbx+40h], rax
0x18002ff2d  lea     rsi, [rbx+48h]
0x18002ff31  mov     [rsp+38h+arg_8], rsi
0x18002ff36  mov     qword ptr [rsi+38h], 0
0x18002ff3e  mov     rcx, [rbp+38h]
0x18002ff42  test    rcx, rcx
0x18002ff45  jz      short loc_18002FF59
0x18002ff47  mov     rax, [rcx]
0x18002ff4a  mov     rdx, rsi
0x18002ff4d  mov     rax, [rax]
0x18002ff50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff55  mov     [rsi+38h], rax
0x18002ff59  mov     byte ptr [rbx+20h], 1
0x18002ff5d  mov     rsi, [rsp+38h+arg_20]
0x18002ff62  cmp     rdi, rsi
0x18002ff65  jz      short loc_18002FF7C
0x18002ff67  mov     rcx, rdi
0x18002ff6a  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18002ff70  mov     rdx, [rsi]
0x18002ff73  mov     rcx, rdi
0x18002ff76  call    cs:__imp_?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z; Concurrency::details::_ContextCallback::_Assign(void *)
0x18002ff7c  mov     al, [rsi+8]
0x18002ff7f  mov     [rdi+8], al
0x18002ff82  cmp     qword ptr [rdi], 1
0x18002ff86  jnz     short loc_18002FFAC
0x18002ff88  mov     rax, [r14]
0x18002ff8b  mov     dl, [rax+0Ch]
0x18002ff8e  mov     qword ptr [rdi], 0
0x18002ff95  test    dl, dl
0x18002ff97  jz      short loc_18002FFAC
0x18002ff99  call    cs:__imp_?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ; Concurrency::details::_ContextCallback::_IsCurrentOriginSTA(void)
0x18002ff9f  test    al, al
0x18002ffa1  jz      short loc_18002FFAC
0x18002ffa3  mov     rcx, rdi
0x18002ffa6  call    cs:__imp_?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Capture(void)
0x18002ffac  mov     eax, [rsp+38h+arg_28]
0x18002ffb0  mov     [rbx+24h], eax
0x18002ffb3  mov     rax, rbx
0x18002ffb6  mov     rbx, [rsp+38h+arg_10]
0x18002ffbb  mov     rbp, [rsp+38h+arg_18]
0x18002ffc0  add     rsp, 20h
0x18002ffc4  pop     r14
0x18002ffc6  pop     rdi
0x18002ffc7  pop     rsi
0x18002ffc8  retn
```

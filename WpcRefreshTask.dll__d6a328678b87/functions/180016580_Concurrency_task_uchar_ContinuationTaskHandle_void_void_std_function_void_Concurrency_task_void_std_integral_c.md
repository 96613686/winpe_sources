# Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::function<void (Concurrency::task<void>)> const &,Concurrency::task_continuation_context const &,Concurrency::details::_TaskInliningMode)

- ea: `0x180016580`
- end: `0x1800166d5`
- name: `??0?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@0AEBV?$function@$$A6AXV?$task@X@Concurrency@@@Z@4@AEBVtask_continuation_context@2@W4_TaskInliningMode@details@2@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800160b0`

## callees

- `0x180016580`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800166b2`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800166b2`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180016676`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180016676`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x1800166a5`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x1800166a5`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x1800165bc`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x1800165bc`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x180016682`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x180016682`

## pseudocode

```c
__int64 __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(
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
  *(_QWORD *)a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  v11 = a3[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 40) = *a3;
  *(_QWORD *)(a1 + 48) = a3[1];
  *(_QWORD *)a1 = &Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
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
0x180016580  mov     [rsp+arg_10], rbx
0x180016585  mov     [rsp+arg_18], rbp
0x18001658a  mov     [rsp+arg_0], rcx
0x18001658f  push    rsi
0x180016590  push    rdi
0x180016591  push    r14
0x180016593  sub     rsp, 20h
0x180016597  mov     rbp, r9
0x18001659a  mov     rsi, r8
0x18001659d  mov     r14, rdx
0x1800165a0  mov     rbx, rcx
0x1800165a3  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x1800165aa  mov     [rcx], rax
0x1800165ad  mov     qword ptr [rcx+8], 0
0x1800165b5  lea     rdi, [rcx+10h]
0x1800165b9  mov     rcx, rdi
0x1800165bc  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x1800165c2  mov     byte ptr [rbx+20h], 0
0x1800165c6  mov     dword ptr [rbx+24h], 0
0x1800165cd  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x1800165d4  mov     [rbx], rax
0x1800165d7  mov     qword ptr [rbx+28h], 0
0x1800165df  mov     qword ptr [rbx+30h], 0
0x1800165e7  mov     rax, [rsi+8]
0x1800165eb  test    rax, rax
0x1800165ee  jz      short loc_1800165F4
0x1800165f0  lock inc dword ptr [rax+8]
0x1800165f4  mov     rax, [rsi]
0x1800165f7  mov     [rbx+28h], rax
0x1800165fb  mov     rax, [rsi+8]
0x1800165ff  mov     [rbx+30h], rax
0x180016603  lea     rax, ??_7?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18001660a  mov     [rbx], rax
0x18001660d  mov     qword ptr [rbx+38h], 0
0x180016615  mov     qword ptr [rbx+40h], 0
0x18001661d  mov     rax, [r14+8]
0x180016621  test    rax, rax
0x180016624  jz      short loc_18001662A
0x180016626  lock inc dword ptr [rax+8]
0x18001662a  mov     rax, [r14]
0x18001662d  mov     [rbx+38h], rax
0x180016631  mov     rax, [r14+8]
0x180016635  mov     [rbx+40h], rax
0x180016639  lea     rsi, [rbx+48h]
0x18001663d  mov     [rsp+38h+arg_8], rsi
0x180016642  mov     qword ptr [rsi+38h], 0
0x18001664a  mov     rcx, [rbp+38h]
0x18001664e  test    rcx, rcx
0x180016651  jz      short loc_180016665
0x180016653  mov     rax, [rcx]
0x180016656  mov     rdx, rsi
0x180016659  mov     rax, [rax]
0x18001665c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016661  mov     [rsi+38h], rax
0x180016665  mov     byte ptr [rbx+20h], 1
0x180016669  mov     rsi, [rsp+38h+arg_20]
0x18001666e  cmp     rdi, rsi
0x180016671  jz      short loc_180016688
0x180016673  mov     rcx, rdi
0x180016676  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18001667c  mov     rdx, [rsi]
0x18001667f  mov     rcx, rdi
0x180016682  call    cs:__imp_?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z; Concurrency::details::_ContextCallback::_Assign(void *)
0x180016688  mov     al, [rsi+8]
0x18001668b  mov     [rdi+8], al
0x18001668e  cmp     qword ptr [rdi], 1
0x180016692  jnz     short loc_1800166B8
0x180016694  mov     rax, [r14]
0x180016697  mov     dl, [rax+0Ch]
0x18001669a  mov     qword ptr [rdi], 0
0x1800166a1  test    dl, dl
0x1800166a3  jz      short loc_1800166B8
0x1800166a5  call    cs:__imp_?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ; Concurrency::details::_ContextCallback::_IsCurrentOriginSTA(void)
0x1800166ab  test    al, al
0x1800166ad  jz      short loc_1800166B8
0x1800166af  mov     rcx, rdi
0x1800166b2  call    cs:__imp_?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Capture(void)
0x1800166b8  mov     eax, [rsp+38h+arg_28]
0x1800166bc  mov     [rbx+24h], eax
0x1800166bf  mov     rax, rbx
0x1800166c2  mov     rbx, [rsp+38h+arg_10]
0x1800166c7  mov     rbp, [rsp+38h+arg_18]
0x1800166cc  add     rsp, 20h
0x1800166d0  pop     r14
0x1800166d2  pop     rdi
0x1800166d3  pop     rsi
0x1800166d4  retn
```

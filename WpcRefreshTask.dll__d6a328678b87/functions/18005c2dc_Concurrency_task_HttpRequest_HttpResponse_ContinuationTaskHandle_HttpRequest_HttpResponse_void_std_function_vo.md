# Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(std::shared_ptr<Concurrency::details::_Task_impl<HttpRequest::HttpResponse>> const &,std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)> const &,Concurrency::task_continuation_context const &,Concurrency::details::_TaskInliningMode)

- ea: `0x18005c2dc`
- end: `0x18005c431`
- name: `??0?$_ContinuationTaskHandle@VHttpResponse@HttpRequest@@XV?$function@$$A6AXV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@VHttpResponse@HttpRequest@@@Concurrency@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@VHttpResponse@HttpRequest@@@details@Concurrency@@@std@@AEBV?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@4@AEBV?$function@$$A6AXV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@Z@4@AEBVtask_continuation_context@2@W4_TaskInliningMode@details@2@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18005be5c`

## callees

- `0x18005c2dc`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18005c40e`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18005c40e`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18005c3d2`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18005c3d2`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x18005c401`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x18005c401`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18005c318`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18005c318`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x18005c3de`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x18005c3de`

## pseudocode

```c
__int64 __fastcall Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(
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
  *(_QWORD *)a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  v11 = a3[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 40) = *a3;
  *(_QWORD *)(a1 + 48) = a3[1];
  *(_QWORD *)a1 = &Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
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
0x18005c2dc  mov     [rsp+arg_10], rbx
0x18005c2e1  mov     [rsp+arg_18], rbp
0x18005c2e6  mov     [rsp+arg_0], rcx
0x18005c2eb  push    rsi
0x18005c2ec  push    rdi
0x18005c2ed  push    r14
0x18005c2ef  sub     rsp, 20h
0x18005c2f3  mov     rbp, r9
0x18005c2f6  mov     rsi, r8
0x18005c2f9  mov     r14, rdx
0x18005c2fc  mov     rbx, rcx
0x18005c2ff  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x18005c306  mov     [rcx], rax
0x18005c309  mov     qword ptr [rcx+8], 0
0x18005c311  lea     rdi, [rcx+10h]
0x18005c315  mov     rcx, rdi
0x18005c318  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x18005c31e  mov     byte ptr [rbx+20h], 0
0x18005c322  mov     dword ptr [rbx+24h], 0
0x18005c329  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@VHttpResponse@HttpRequest@@XV?$function@$$A6AXV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@VHttpResponse@HttpRequest@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x18005c330  mov     [rbx], rax
0x18005c333  mov     qword ptr [rbx+28h], 0
0x18005c33b  mov     qword ptr [rbx+30h], 0
0x18005c343  mov     rax, [rsi+8]
0x18005c347  test    rax, rax
0x18005c34a  jz      short loc_18005C350
0x18005c34c  lock inc dword ptr [rax+8]
0x18005c350  mov     rax, [rsi]
0x18005c353  mov     [rbx+28h], rax
0x18005c357  mov     rax, [rsi+8]
0x18005c35b  mov     [rbx+30h], rax
0x18005c35f  lea     rax, ??_7?$_ContinuationTaskHandle@VHttpResponse@HttpRequest@@XV?$function@$$A6AXV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@VHttpResponse@HttpRequest@@@Concurrency@@6B@; const Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18005c366  mov     [rbx], rax
0x18005c369  mov     qword ptr [rbx+38h], 0
0x18005c371  mov     qword ptr [rbx+40h], 0
0x18005c379  mov     rax, [r14+8]
0x18005c37d  test    rax, rax
0x18005c380  jz      short loc_18005C386
0x18005c382  lock inc dword ptr [rax+8]
0x18005c386  mov     rax, [r14]
0x18005c389  mov     [rbx+38h], rax
0x18005c38d  mov     rax, [r14+8]
0x18005c391  mov     [rbx+40h], rax
0x18005c395  lea     rsi, [rbx+48h]
0x18005c399  mov     [rsp+38h+arg_8], rsi
0x18005c39e  mov     qword ptr [rsi+38h], 0
0x18005c3a6  mov     rcx, [rbp+38h]
0x18005c3aa  test    rcx, rcx
0x18005c3ad  jz      short loc_18005C3C1
0x18005c3af  mov     rax, [rcx]
0x18005c3b2  mov     rdx, rsi
0x18005c3b5  mov     rax, [rax]
0x18005c3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3bd  mov     [rsi+38h], rax
0x18005c3c1  mov     byte ptr [rbx+20h], 1
0x18005c3c5  mov     rsi, [rsp+38h+arg_20]
0x18005c3ca  cmp     rdi, rsi
0x18005c3cd  jz      short loc_18005C3E4
0x18005c3cf  mov     rcx, rdi
0x18005c3d2  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18005c3d8  mov     rdx, [rsi]
0x18005c3db  mov     rcx, rdi
0x18005c3de  call    cs:__imp_?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z; Concurrency::details::_ContextCallback::_Assign(void *)
0x18005c3e4  mov     al, [rsi+8]
0x18005c3e7  mov     [rdi+8], al
0x18005c3ea  cmp     qword ptr [rdi], 1
0x18005c3ee  jnz     short loc_18005C414
0x18005c3f0  mov     rax, [r14]
0x18005c3f3  mov     dl, [rax+0Ch]
0x18005c3f6  mov     qword ptr [rdi], 0
0x18005c3fd  test    dl, dl
0x18005c3ff  jz      short loc_18005C414
0x18005c401  call    cs:__imp_?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ; Concurrency::details::_ContextCallback::_IsCurrentOriginSTA(void)
0x18005c407  test    al, al
0x18005c409  jz      short loc_18005C414
0x18005c40b  mov     rcx, rdi
0x18005c40e  call    cs:__imp_?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Capture(void)
0x18005c414  mov     eax, [rsp+38h+arg_28]
0x18005c418  mov     [rbx+24h], eax
0x18005c41b  mov     rax, rbx
0x18005c41e  mov     rbx, [rsp+38h+arg_10]
0x18005c423  mov     rbp, [rsp+38h+arg_18]
0x18005c428  add     rsp, 20h
0x18005c42c  pop     r14
0x18005c42e  pop     rdi
0x18005c42f  pop     rsi
0x18005c430  retn
```

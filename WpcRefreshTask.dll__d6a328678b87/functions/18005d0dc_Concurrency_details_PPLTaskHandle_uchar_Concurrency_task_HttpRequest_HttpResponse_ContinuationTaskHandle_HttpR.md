# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x18005d0dc`
- end: `0x18005d16e`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@VHttpResponse@HttpRequest@@XV?$function@$$A6AXV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@VHttpResponse@HttpRequest@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `146`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005cfdc`
- `0x18005db80`
- `0x1800a7dc4`

## callees

- `0x18005d0dc`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18005d152`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18005d152`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005d0fe`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005d0fe`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
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
0x18005d0dc  mov     [rsp+arg_0], rbx
0x18005d0e1  push    rdi
0x18005d0e2  sub     rsp, 20h
0x18005d0e6  mov     rdi, rcx
0x18005d0e9  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@VHttpResponse@HttpRequest@@XV?$function@$$A6AXV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@VHttpResponse@HttpRequest@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x18005d0f0  mov     [rcx], rax
0x18005d0f3  mov     rcx, [rcx+28h]
0x18005d0f7  add     rcx, 160h
0x18005d0fe  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x18005d104  mov     rbx, [rdi+30h]
0x18005d108  test    rbx, rbx
0x18005d10b  jz      short loc_18005D144
0x18005d10d  or      eax, 0FFFFFFFFh
0x18005d110  lock xadd [rbx+8], eax
0x18005d115  cmp     eax, 1
0x18005d118  jnz     short loc_18005D144
0x18005d11a  mov     rax, [rbx]
0x18005d11d  mov     rcx, rbx
0x18005d120  mov     rax, [rax]
0x18005d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d128  or      eax, 0FFFFFFFFh
0x18005d12b  lock xadd [rbx+0Ch], eax
0x18005d130  cmp     eax, 1
0x18005d133  jnz     short loc_18005D144
0x18005d135  mov     rax, [rbx]
0x18005d138  mov     rcx, rbx
0x18005d13b  mov     rax, [rax+8]
0x18005d13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d144  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x18005d14b  mov     [rdi], rax
0x18005d14e  lea     rcx, [rdi+10h]
0x18005d152  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18005d158  nop
0x18005d159  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x18005d160  mov     [rdi], rax
0x18005d163  mov     rbx, [rsp+28h+arg_0]
0x18005d168  add     rsp, 20h
0x18005d16c  pop     rdi
0x18005d16d  retn
```

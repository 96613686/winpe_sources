# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x180010d88`
- end: `0x180010dc7`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(Concurrency::details::_ContinuationTaskHandleBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010cfc`
- `0x180012a10`
- `0x180023876`

## callees

- `0x180010d88`
- `0x180011d30`
- `0x18001cc40`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010da6`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010da6`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        Concurrency::details::_ContinuationTaskHandleBase *this)
{
  std::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(*((_QWORD *)this + 5) + 352LL));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(this);
}

```

## disassembly

```asm
0x180010d88  push    rbx
0x180010d8a  sub     rsp, 20h
0x180010d8e  mov     rbx, rcx
0x180010d91  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x180010d98  mov     [rcx], rax
0x180010d9b  mov     rcx, [rcx+28h]
0x180010d9f  add     rcx, 160h
0x180010da6  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180010dac  mov     rcx, [rbx+30h]; this
0x180010db0  test    rcx, rcx
0x180010db3  jz      short loc_180010DBA
0x180010db5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010dba  mov     rcx, rbx; this
0x180010dbd  add     rsp, 20h
0x180010dc1  pop     rbx
0x180010dc2  jmp     ??1_ContinuationTaskHandleBase@details@Concurrency@@UEAA@XZ; Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(void)
```

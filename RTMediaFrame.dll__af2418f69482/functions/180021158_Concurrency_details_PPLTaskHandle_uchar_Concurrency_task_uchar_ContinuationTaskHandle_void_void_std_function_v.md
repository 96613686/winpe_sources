# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x180021158`
- end: `0x180021197`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(Concurrency::details::_ContinuationTaskHandleBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800210f4`
- `0x180036710`
- `0x180050fcb`

## callees

- `0x18001134c`
- `0x180021158`
- `0x18002124c`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180021176`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180021176`

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
0x180021158  push    rbx
0x18002115a  sub     rsp, 20h
0x18002115e  mov     rbx, rcx
0x180021161  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x180021168  mov     [rcx], rax
0x18002116b  mov     rcx, [rcx+28h]
0x18002116f  add     rcx, 160h
0x180021176  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x18002117c  mov     rcx, [rbx+30h]; this
0x180021180  test    rcx, rcx
0x180021183  jz      short loc_18002118A
0x180021185  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002118a  mov     rcx, rbx; this
0x18002118d  add     rsp, 20h
0x180021191  pop     rbx
0x180021192  jmp     ??1_ContinuationTaskHandleBase@details@Concurrency@@UEAA@XZ; Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(void)
```

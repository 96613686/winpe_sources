# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x18001b40c`
- end: `0x18001b44e`
- name: `??1?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bec0`
- `0x18001bf10`

## callees

- `0x1800109dc`
- `0x18001b40c`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001b42a`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001b42a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (std::_Ref_count_base *)a1[2];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  result = &Concurrency::details::_TaskProcHandle::`vftable';
  *a1 = &Concurrency::details::_TaskProcHandle::`vftable';
  return result;
}

```

## disassembly

```asm
0x18001b40c  push    rbx
0x18001b40e  sub     rsp, 20h
0x18001b412  mov     rbx, rcx
0x18001b415  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x18001b41c  mov     [rcx], rax
0x18001b41f  mov     rcx, [rcx+8]
0x18001b423  add     rcx, 160h
0x18001b42a  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x18001b430  mov     rcx, [rbx+10h]; this
0x18001b434  test    rcx, rcx
0x18001b437  jz      short loc_18001B43E
0x18001b439  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b43e  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x18001b445  mov     [rbx], rax
0x18001b448  add     rsp, 20h
0x18001b44c  pop     rbx
0x18001b44d  retn
```

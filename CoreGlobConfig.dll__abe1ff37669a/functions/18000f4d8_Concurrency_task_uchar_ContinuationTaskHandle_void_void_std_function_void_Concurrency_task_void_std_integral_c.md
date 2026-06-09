# Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::function<void (Concurrency::task<void>)> const &,Concurrency::task_continuation_context const &,Concurrency::details::_TaskInliningMode)

- ea: `0x18000f4d8`
- end: `0x18000f5d5`
- name: `??0?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@0AEBV?$function@$$A6AXV?$task@X@Concurrency@@@Z@4@AEBVtask_continuation_context@2@W4_TaskInliningMode@details@2@@Z`
- size: `253`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000da9c`

## callees

- `0x18000f4d8`
- `0x18000f864`
- `0x18000f958`
- `0x18001ed08`

## import_xrefs

- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18000f5b0`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18000f5b0`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x18000f580`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x18000f580`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x18000f5a3`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x18000f5a3`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18000f574`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18000f574`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  Concurrency::details::_ContextCallback *v9; // rsi
  char v10; // dl

  *(_QWORD *)a1 = &Concurrency::details::_ContinuationTaskHandleBase::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  v9 = (Concurrency::details::_ContextCallback *)(a1 + 16);
  Concurrency::task_continuation_context::use_default(a1 + 16);
  *(_BYTE *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    a1 + 40,
    a3);
  *(_QWORD *)a1 = &Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    a1 + 56,
    a2);
  std::function<void (void)>::function<void (void)>(a1 + 72);
  *(_BYTE *)(a1 + 32) = 1;
  if ( v9 != (Concurrency::details::_ContextCallback *)a5 )
  {
    Concurrency::details::_ContextCallback::_Reset(v9);
    Concurrency::details::_ContextCallback::_Assign(v9, *(void **)a5);
  }
  *((_BYTE *)v9 + 8) = *(_BYTE *)(a5 + 8);
  if ( *(_QWORD *)v9 == 1 )
  {
    v10 = *(_BYTE *)(*(_QWORD *)a2 + 12LL);
    *(_QWORD *)v9 = 0;
    if ( v10 )
    {
      if ( (unsigned __int8)Concurrency::details::_ContextCallback::_IsCurrentOriginSTA() )
        Concurrency::details::_ContextCallback::_Capture(v9);
    }
  }
  *(_DWORD *)(a1 + 36) = a6;
  return a1;
}

```

## disassembly

```asm
0x18000f4d8  mov     [rsp+arg_10], rbx
0x18000f4dd  mov     [rsp+arg_18], rsi
0x18000f4e2  mov     [rsp+arg_0], rcx
0x18000f4e7  push    rdi
0x18000f4e8  push    r14
0x18000f4ea  push    r15
0x18000f4ec  sub     rsp, 20h
0x18000f4f0  mov     rdi, r9
0x18000f4f3  mov     rbx, r8
0x18000f4f6  mov     r15, rdx
0x18000f4f9  mov     r14, rcx
0x18000f4fc  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x18000f503  mov     [rcx], rax
0x18000f506  mov     qword ptr [rcx+8], 0
0x18000f50e  lea     rsi, [rcx+10h]
0x18000f512  mov     rcx, rsi
0x18000f515  call    ?use_default@task_continuation_context@Concurrency@@SA?AV12@XZ; Concurrency::task_continuation_context::use_default(void)
0x18000f51a  mov     byte ptr [r14+20h], 0
0x18000f51f  mov     dword ptr [r14+24h], 0
0x18000f527  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x18000f52e  mov     [r14], rax
0x18000f531  lea     rcx, [r14+28h]
0x18000f535  mov     rdx, rbx
0x18000f538  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18000f53d  nop
0x18000f53e  lea     rax, ??_7?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18000f545  mov     [r14], rax
0x18000f548  lea     rcx, [r14+38h]
0x18000f54c  mov     rdx, r15
0x18000f54f  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18000f554  nop
0x18000f555  lea     rcx, [r14+48h]
0x18000f559  mov     rdx, rdi
0x18000f55c  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18000f561  nop
0x18000f562  mov     byte ptr [r14+20h], 1
0x18000f567  mov     rbx, [rsp+38h+arg_20]
0x18000f56c  cmp     rsi, rbx
0x18000f56f  jz      short loc_18000F586
0x18000f571  mov     rcx, rsi
0x18000f574  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18000f57a  mov     rdx, [rbx]
0x18000f57d  mov     rcx, rsi
0x18000f580  call    cs:__imp_?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z; Concurrency::details::_ContextCallback::_Assign(void *)
0x18000f586  mov     al, [rbx+8]
0x18000f589  mov     [rsi+8], al
0x18000f58c  cmp     qword ptr [rsi], 1
0x18000f590  jnz     short loc_18000F5B6
0x18000f592  mov     rax, [r15]
0x18000f595  mov     dl, [rax+0Ch]
0x18000f598  mov     qword ptr [rsi], 0
0x18000f59f  test    dl, dl
0x18000f5a1  jz      short loc_18000F5B6
0x18000f5a3  call    cs:__imp_?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ; Concurrency::details::_ContextCallback::_IsCurrentOriginSTA(void)
0x18000f5a9  test    al, al
0x18000f5ab  jz      short loc_18000F5B6
0x18000f5ad  mov     rcx, rsi
0x18000f5b0  call    cs:__imp_?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Capture(void)
0x18000f5b6  mov     eax, [rsp+38h+arg_28]
0x18000f5ba  mov     [r14+24h], eax
0x18000f5be  mov     rax, r14
0x18000f5c1  mov     rbx, [rsp+38h+arg_10]
0x18000f5c6  mov     rsi, [rsp+38h+arg_18]
0x18000f5cb  add     rsp, 20h
0x18000f5cf  pop     r15
0x18000f5d1  pop     r14
0x18000f5d3  pop     rdi
0x18000f5d4  retn
```

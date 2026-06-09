# ?set@?Q?$IAsyncOperation@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAV?$AsyncOperationCompletedHandler@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@23@@Z

- ea: `0x1800d621c`
- end: `0x1800d62d0`
- name: `?set@?Q?$IAsyncOperation@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAV?$AsyncOperationCompletedHandler@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@23@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d62e0`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008ade0`
- `0x18008aeb0`
- `0x180092508`
- `0x1800d41dc`
- `0x1800d621c`
- `0x1800d92ec`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d62a6`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d62a6`

## pseudocode

```c
__int64 __fastcall _set__Q__IAsyncOperation_PE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows___Foundation_Windows__Completed____AsyncInfoBase_U___AsyncAttributes_XPE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__U___TaskTypeTraits_V__task_PE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows___Concurrency___0A__details_Concurrency___00_0A__details_Concurrency___00_details_Concurrency__UE_AAAXPE_AAV__AsyncOperationCompletedHandler_PE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows___23__Z(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  int v5; // ecx
  __int64 result; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+40h] [rbp+18h]

  Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForDelegateCall();
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 60)) != 1 )
  {
    Exception = Platform::Exception::CreateException(2147483672LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  v4 = (_QWORD *)Concurrency::details::_ContextCallback::_CaptureCurrent(&pExceptionObject);
  if ( (_QWORD *)(a1 + 32) != v4 )
  {
    *(_QWORD *)(a1 + 32) = *v4;
    *v4 = 0;
  }
  Concurrency::details::_ContextCallback::_Reset((Concurrency::details::_ContextCallback *)&pExceptionObject);
  __abi_winrt_ptr_assign(a1 + 40, a2);
  _InterlockedOr(v7, 0);
  v5 = *(_DWORD *)(a1 + 48);
  result = (unsigned int)(v5 - 1);
  if ( (unsigned int)result <= 2 || v5 == 5 )
    return Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>,0>,1,0>,1>::_FireCompletion(a1);
  return result;
}

```

## disassembly

```asm
0x1800d621c  mov     [rsp+arg_8], rbx
0x1800d6221  push    rdi
0x1800d6222  sub     rsp, 20h
0x1800d6226  mov     rdi, rdx
0x1800d6229  mov     rbx, rcx
0x1800d622c  call    ?_CheckValidStateForDelegateCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForDelegateCall(void)
0x1800d6231  mov     eax, 1
0x1800d6236  lock xadd [rbx+3Ch], eax
0x1800d623b  inc     eax
0x1800d623d  cmp     eax, 1
0x1800d6240  jnz     short loc_1800D62A1
0x1800d6242  lea     rcx, [rsp+28h+pExceptionObject]
0x1800d6247  call    ?_CaptureCurrent@_ContextCallback@details@Concurrency@@SA?AV123@XZ; Concurrency::details::_ContextCallback::_CaptureCurrent(void)
0x1800d624c  lea     rdx, [rbx+20h]
0x1800d6250  cmp     rdx, rax
0x1800d6253  jz      short loc_1800D6262
0x1800d6255  mov     rcx, [rax]
0x1800d6258  mov     [rdx], rcx
0x1800d625b  mov     qword ptr [rax], 0
0x1800d6262  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800d6267  call    ?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x1800d626c  nop
0x1800d626d  lea     rcx, [rbx+28h]
0x1800d6271  mov     rdx, rdi
0x1800d6274  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x1800d6279  lock or [rsp+28h+var_28], 0
0x1800d627e  mov     ecx, [rbx+30h]
0x1800d6281  lea     eax, [rcx-1]
0x1800d6284  cmp     eax, 2
0x1800d6287  jbe     short loc_1800D628E
0x1800d6289  cmp     ecx, 5
0x1800d628c  jnz     short loc_1800D6296
0x1800d628e  mov     rcx, rbx
0x1800d6291  call    ?_FireCompletion@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>,0>,1,0>,1>::_FireCompletion(void)
0x1800d6296  mov     rbx, [rsp+28h+arg_8]
0x1800d629b  add     rsp, 20h
0x1800d629f  pop     rdi
0x1800d62a0  retn
0x1800d62a1  mov     ecx, 80000018h
0x1800d62a6  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800d62ac  mov     [rsp+28h+arg_10], rax
0x1800d62b1  mov     rcx, rax
0x1800d62b4  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d62b9  mov     [rsp+28h+pExceptionObject], rax
0x1800d62be  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800d62c5  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800d62ca  call    _CxxThrowException_0
```

# ?set@?QIAsyncAction@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAVAsyncActionCompletedHandler@23@@Z

- ea: `0x18009a01c`
- end: `0x18009a0d0`
- name: `?set@?QIAsyncAction@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAVAsyncActionCompletedHandler@23@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009a0e0`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008ade0`
- `0x18008aeb0`
- `0x180092508`
- `0x180099820`
- `0x18009a01c`
- `0x1800d92ec`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18009a0a6`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18009a0a6`

## pseudocode

```c
__int64 __fastcall _set__QIAsyncAction_Foundation_Windows__Completed____AsyncInfoBase_U___AsyncAttributes_XXU___TaskTypeTraits_V__task_X_Concurrency___0A__details_Concurrency___0A__0A__details_Concurrency___00_details_Concurrency__UE_AAAXPE_AAVAsyncActionCompletedHandler_23__Z(
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
    return Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_FireCompletion(a1);
  return result;
}

```

## disassembly

```asm
0x18009a01c  mov     [rsp+arg_8], rbx
0x18009a021  push    rdi
0x18009a022  sub     rsp, 20h
0x18009a026  mov     rdi, rdx
0x18009a029  mov     rbx, rcx
0x18009a02c  call    ?_CheckValidStateForDelegateCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForDelegateCall(void)
0x18009a031  mov     eax, 1
0x18009a036  lock xadd [rbx+3Ch], eax
0x18009a03b  inc     eax
0x18009a03d  cmp     eax, 1
0x18009a040  jnz     short loc_18009A0A1
0x18009a042  lea     rcx, [rsp+28h+pExceptionObject]
0x18009a047  call    ?_CaptureCurrent@_ContextCallback@details@Concurrency@@SA?AV123@XZ; Concurrency::details::_ContextCallback::_CaptureCurrent(void)
0x18009a04c  lea     rdx, [rbx+20h]
0x18009a050  cmp     rdx, rax
0x18009a053  jz      short loc_18009A062
0x18009a055  mov     rcx, [rax]
0x18009a058  mov     [rdx], rcx
0x18009a05b  mov     qword ptr [rax], 0
0x18009a062  lea     rcx, [rsp+28h+pExceptionObject]; this
0x18009a067  call    ?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18009a06c  nop
0x18009a06d  lea     rcx, [rbx+28h]
0x18009a071  mov     rdx, rdi
0x18009a074  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x18009a079  lock or [rsp+28h+var_28], 0
0x18009a07e  mov     ecx, [rbx+30h]
0x18009a081  lea     eax, [rcx-1]
0x18009a084  cmp     eax, 2
0x18009a087  jbe     short loc_18009A08E
0x18009a089  cmp     ecx, 5
0x18009a08c  jnz     short loc_18009A096
0x18009a08e  mov     rcx, rbx
0x18009a091  call    ?_FireCompletion@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_FireCompletion(void)
0x18009a096  mov     rbx, [rsp+28h+arg_8]
0x18009a09b  add     rsp, 20h
0x18009a09f  pop     rdi
0x18009a0a0  retn
0x18009a0a1  mov     ecx, 80000018h
0x18009a0a6  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x18009a0ac  mov     [rsp+28h+arg_10], rax
0x18009a0b1  mov     rcx, rax
0x18009a0b4  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009a0b9  mov     [rsp+28h+pExceptionObject], rax
0x18009a0be  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x18009a0c5  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18009a0ca  call    _CxxThrowException_0
```

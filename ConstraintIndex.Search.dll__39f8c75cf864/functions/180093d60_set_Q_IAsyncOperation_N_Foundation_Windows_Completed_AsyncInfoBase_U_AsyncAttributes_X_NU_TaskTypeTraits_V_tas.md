# ?set@?Q?$IAsyncOperation@_N@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAV?$AsyncOperationCompletedHandler@_N@23@@Z

- ea: `0x180093d60`
- end: `0x180093e14`
- name: `?set@?Q?$IAsyncOperation@_N@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAV?$AsyncOperationCompletedHandler@_N@23@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180093e20`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008ade0`
- `0x18008aeb0`
- `0x18008db54`
- `0x180092508`
- `0x180093d60`
- `0x1800d92ec`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180093dea`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180093dea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _set__Q__IAsyncOperation__N_Foundation_Windows__Completed____AsyncInfoBase_U___AsyncAttributes_X_NU___TaskTypeTraits_V__task__N_Concurrency___0A__details_Concurrency___0A__0A__details_Concurrency___00_details_Concurrency__UE_AAAXPE_AAV__AsyncOperationCompletedHandler__N_23__Z(
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
    return Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::_FireCompletion(a1);
  return result;
}

```

## disassembly

```asm
0x180093d60  mov     [rsp+arg_8], rbx
0x180093d65  push    rdi
0x180093d66  sub     rsp, 20h
0x180093d6a  mov     rdi, rdx
0x180093d6d  mov     rbx, rcx
0x180093d70  call    ?_CheckValidStateForDelegateCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForDelegateCall(void)
0x180093d75  mov     eax, 1
0x180093d7a  lock xadd [rbx+3Ch], eax
0x180093d7f  inc     eax
0x180093d81  cmp     eax, 1
0x180093d84  jnz     short loc_180093DE5
0x180093d86  lea     rcx, [rsp+28h+pExceptionObject]
0x180093d8b  call    ?_CaptureCurrent@_ContextCallback@details@Concurrency@@SA?AV123@XZ; Concurrency::details::_ContextCallback::_CaptureCurrent(void)
0x180093d90  lea     rdx, [rbx+20h]
0x180093d94  cmp     rdx, rax
0x180093d97  jz      short loc_180093DA6
0x180093d99  mov     rcx, [rax]
0x180093d9c  mov     [rdx], rcx
0x180093d9f  mov     qword ptr [rax], 0
0x180093da6  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180093dab  call    ?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x180093db0  nop
0x180093db1  lea     rcx, [rbx+28h]
0x180093db5  mov     rdx, rdi
0x180093db8  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x180093dbd  lock or [rsp+28h+var_28], 0
0x180093dc2  mov     ecx, [rbx+30h]
0x180093dc5  lea     eax, [rcx-1]
0x180093dc8  cmp     eax, 2
0x180093dcb  jbe     short loc_180093DD2
0x180093dcd  cmp     ecx, 5
0x180093dd0  jnz     short loc_180093DDA
0x180093dd2  mov     rcx, rbx
0x180093dd5  call    ?_FireCompletion@?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::_FireCompletion(void)
0x180093dda  mov     rbx, [rsp+28h+arg_8]
0x180093ddf  add     rsp, 20h
0x180093de3  pop     rdi
0x180093de4  retn
0x180093de5  mov     ecx, 80000018h
0x180093dea  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x180093df0  mov     [rsp+28h+arg_10], rax
0x180093df5  mov     rcx, rax
0x180093df8  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180093dfd  mov     [rsp+28h+pExceptionObject], rax
0x180093e02  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x180093e09  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180093e0e  call    _CxxThrowException_0
```

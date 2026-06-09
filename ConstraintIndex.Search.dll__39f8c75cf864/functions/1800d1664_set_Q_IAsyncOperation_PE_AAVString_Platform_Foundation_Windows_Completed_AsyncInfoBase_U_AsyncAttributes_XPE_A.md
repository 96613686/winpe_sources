# ?set@?Q?$IAsyncOperation@PE$AAVString@Platform@@@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAV?$AsyncOperationCompletedHandler@PE$AAVString@Platform@@@23@@Z

- ea: `0x1800d1664`
- end: `0x1800d1718`
- name: `?set@?Q?$IAsyncOperation@PE$AAVString@Platform@@@Foundation@Windows@@Completed@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXPE$AAV?$AsyncOperationCompletedHandler@PE$AAVString@Platform@@@23@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d1720`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008ade0`
- `0x18008aeb0`
- `0x180092508`
- `0x1800d0634`
- `0x1800d1664`
- `0x1800d92ec`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d16ee`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d16ee`

## pseudocode

```c
__int64 __fastcall _set__Q__IAsyncOperation_PE_AAVString_Platform___Foundation_Windows__Completed____AsyncInfoBase_U___AsyncAttributes_XPE_AAVString_Platform__U___TaskTypeTraits_V__task_PE_AAVString_Platform___Concurrency___0A__details_Concurrency___0A__0A__details_Concurrency___00_details_Concurrency__UE_AAAXPE_AAV__AsyncOperationCompletedHandler_PE_AAVString_Platform___23__Z(
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
    return Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,1>::_FireCompletion(a1);
  return result;
}

```

## disassembly

```asm
0x1800d1664  mov     [rsp+arg_8], rbx
0x1800d1669  push    rdi
0x1800d166a  sub     rsp, 20h
0x1800d166e  mov     rdi, rdx
0x1800d1671  mov     rbx, rcx
0x1800d1674  call    ?_CheckValidStateForDelegateCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForDelegateCall(void)
0x1800d1679  mov     eax, 1
0x1800d167e  lock xadd [rbx+3Ch], eax
0x1800d1683  inc     eax
0x1800d1685  cmp     eax, 1
0x1800d1688  jnz     short loc_1800D16E9
0x1800d168a  lea     rcx, [rsp+28h+pExceptionObject]
0x1800d168f  call    ?_CaptureCurrent@_ContextCallback@details@Concurrency@@SA?AV123@XZ; Concurrency::details::_ContextCallback::_CaptureCurrent(void)
0x1800d1694  lea     rdx, [rbx+20h]
0x1800d1698  cmp     rdx, rax
0x1800d169b  jz      short loc_1800D16AA
0x1800d169d  mov     rcx, [rax]
0x1800d16a0  mov     [rdx], rcx
0x1800d16a3  mov     qword ptr [rax], 0
0x1800d16aa  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800d16af  call    ?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x1800d16b4  nop
0x1800d16b5  lea     rcx, [rbx+28h]
0x1800d16b9  mov     rdx, rdi
0x1800d16bc  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x1800d16c1  lock or [rsp+28h+var_28], 0
0x1800d16c6  mov     ecx, [rbx+30h]
0x1800d16c9  lea     eax, [rcx-1]
0x1800d16cc  cmp     eax, 2
0x1800d16cf  jbe     short loc_1800D16D6
0x1800d16d1  cmp     ecx, 5
0x1800d16d4  jnz     short loc_1800D16DE
0x1800d16d6  mov     rcx, rbx
0x1800d16d9  call    ?_FireCompletion@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,1>::_FireCompletion(void)
0x1800d16de  mov     rbx, [rsp+28h+arg_8]
0x1800d16e3  add     rsp, 20h
0x1800d16e7  pop     rdi
0x1800d16e8  retn
0x1800d16e9  mov     ecx, 80000018h
0x1800d16ee  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800d16f4  mov     [rsp+28h+arg_10], rax
0x1800d16f9  mov     rcx, rax
0x1800d16fc  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d1701  mov     [rsp+28h+pExceptionObject], rax
0x1800d1706  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800d170d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800d1712  call    _CxxThrowException_0
```

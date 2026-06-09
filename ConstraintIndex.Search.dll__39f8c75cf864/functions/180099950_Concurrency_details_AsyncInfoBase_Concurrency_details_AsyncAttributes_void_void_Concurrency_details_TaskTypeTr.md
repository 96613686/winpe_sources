# Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_Start(void)

- ea: `0x180099950`
- end: `0x18009999e`
- name: `?_Start@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800bf0f0`
- `0x1800cca54`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008f9a4`
- `0x180099950`
- `0x1800fb010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180099974`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180099974`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_Start(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 pExceptionObject; // [rsp+38h] [rbp+10h] BYREF
  __int64 Exception; // [rsp+40h] [rbp+18h]

  if ( !(unsigned __int8)Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(
                           a1,
                           0) )
  {
    Exception = Platform::Exception::CreateException(2147483661LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 88LL))(v1);
}

```

## disassembly

```asm
0x180099950  sub     rsp, 28h
0x180099954  xor     edx, edx
0x180099956  call    ?_TransitionToState@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@AE$AAA_NW4_AsyncStatusInternal@23@@Z; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(Concurrency::details::_AsyncStatusInternal)
0x18009995b  test    al, al
0x18009995d  jz      short loc_18009996F
0x18009995f  mov     rax, [rcx]
0x180099962  mov     rax, [rax+58h]
0x180099966  add     rsp, 28h
0x18009996a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18009996f  mov     ecx, 8000000Dh
0x180099974  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x18009997a  mov     [rsp+28h+arg_10], rax
0x18009997f  mov     rcx, rax
0x180099982  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180099987  mov     [rsp+28h+pExceptionObject], rax
0x18009998c  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x180099993  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180099998  call    _CxxThrowException_0
```

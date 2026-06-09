# Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,1>::_CheckValidStateForAsyncInfoCall(void)

- ea: `0x18008ae34`
- end: `0x18008aea8`
- name: `?_CheckValidStateForAsyncInfoCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@AE$AAAXXZ`
- size: `116`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180092780`
- `0x1800928e0`
- `0x180092a10`
- `0x180093e30`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008ae34`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008ae45`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008ae79`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008ae45`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008ae79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,1>::_CheckValidStateForAsyncInfoCall(
        __int64 a1)
{
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+38h] [rbp+10h]

  result = *(unsigned int *)(a1 + 48);
  if ( (_DWORD)result == 5 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  if ( (_DWORD)result == -1 )
  {
    Exception = Platform::Exception::CreateException(2147483673LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18008ae34  sub     rsp, 28h
0x18008ae38  mov     eax, [rcx+30h]
0x18008ae3b  cmp     eax, 5
0x18008ae3e  jnz     short loc_18008AE6F
0x18008ae40  mov     ecx, 8000000Eh
0x18008ae45  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x18008ae4b  mov     [rsp+28h+arg_8], rax
0x18008ae50  mov     rcx, rax
0x18008ae53  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18008ae58  mov     [rsp+28h+pExceptionObject], rax
0x18008ae5d  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x18008ae64  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18008ae69  call    _CxxThrowException_0
0x18008ae6f  cmp     eax, 0FFFFFFFFh
0x18008ae72  jnz     short loc_18008AEA3
0x18008ae74  mov     ecx, 80000019h
0x18008ae79  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x18008ae7f  mov     [rsp+28h+arg_8], rax
0x18008ae84  mov     rcx, rax
0x18008ae87  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18008ae8c  mov     [rsp+28h+pExceptionObject], rax
0x18008ae91  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x18008ae98  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18008ae9d  call    _CxxThrowException_0
0x18008aea3  add     rsp, 28h
0x18008aea7  retn
```

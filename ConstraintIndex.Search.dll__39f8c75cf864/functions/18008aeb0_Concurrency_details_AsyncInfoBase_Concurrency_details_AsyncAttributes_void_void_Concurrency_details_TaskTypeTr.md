# Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForDelegateCall(void)

- ea: `0x18008aeb0`
- end: `0x18008aef0`
- name: `?_CheckValidStateForDelegateCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ`
- size: `64`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180092740`
- `0x180093d60`
- `0x18009a01c`
- `0x1800d1664`
- `0x1800d621c`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008aeb0`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008aec1`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008aec1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForDelegateCall(
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
  return result;
}

```

## disassembly

```asm
0x18008aeb0  sub     rsp, 28h
0x18008aeb4  mov     eax, [rcx+30h]
0x18008aeb7  cmp     eax, 5
0x18008aeba  jnz     short loc_18008AEEB
0x18008aebc  mov     ecx, 8000000Eh
0x18008aec1  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x18008aec7  mov     [rsp+28h+arg_8], rax
0x18008aecc  mov     rcx, rax
0x18008aecf  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18008aed4  mov     [rsp+28h+pExceptionObject], rax
0x18008aed9  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x18008aee0  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18008aee5  call    _CxxThrowException_0
0x18008aeeb  add     rsp, 28h
0x18008aeef  retn
```

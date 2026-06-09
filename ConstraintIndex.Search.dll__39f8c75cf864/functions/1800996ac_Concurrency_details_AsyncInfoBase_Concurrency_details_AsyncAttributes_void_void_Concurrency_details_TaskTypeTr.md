# Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForResultsCall(void)

- ea: `0x1800996ac`
- end: `0x18009971e`
- name: `?_CheckValidStateForResultsCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@IE$AAAXXZ`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800c3360`
- `0x1800cee30`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x1800996ac`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800996bb`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800996ef`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800996bb`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800996ef`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_CheckValidStateForResultsCall(
        __int64 a1)
{
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+38h] [rbp+10h]

  result = *(unsigned int *)(a1 + 48);
  if ( (_DWORD)result == 3 )
  {
    Exception = Platform::Exception::CreateException(*(unsigned int *)(a1 + 52));
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  if ( (_DWORD)result != 1 )
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
0x1800996ac  sub     rsp, 28h
0x1800996b0  mov     eax, [rcx+30h]
0x1800996b3  cmp     eax, 3
0x1800996b6  jnz     short loc_1800996E5
0x1800996b8  mov     ecx, [rcx+34h]
0x1800996bb  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800996c1  mov     [rsp+28h+arg_8], rax
0x1800996c6  mov     rcx, rax
0x1800996c9  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800996ce  mov     [rsp+28h+pExceptionObject], rax
0x1800996d3  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800996da  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800996df  call    _CxxThrowException_0
0x1800996e5  cmp     eax, 1
0x1800996e8  jz      short loc_180099719
0x1800996ea  mov     ecx, 8000000Eh
0x1800996ef  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800996f5  mov     [rsp+28h+arg_8], rax
0x1800996fa  mov     rcx, rax
0x1800996fd  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180099702  mov     [rsp+28h+pExceptionObject], rax
0x180099707  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x18009970e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180099713  call    _CxxThrowException_0
0x180099719  add     rsp, 28h
0x18009971d  retn
```

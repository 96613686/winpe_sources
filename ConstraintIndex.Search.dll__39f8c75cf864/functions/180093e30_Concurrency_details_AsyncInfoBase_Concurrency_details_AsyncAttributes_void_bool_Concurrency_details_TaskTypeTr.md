# Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::Id::set(uint)

- ea: `0x180093e30`
- end: `0x180093ebc`
- name: `?set@Id@?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXI@Z`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18008ae34`
- `0x180093e30`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180093e4d`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180093e84`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180093e4d`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180093e84`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::Id::set(
        __int64 a1,
        int a2)
{
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  __int64 Exception; // [rsp+48h] [rbp+20h]

  Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,1>::_CheckValidStateForAsyncInfoCall(a1);
  if ( !a2 )
  {
    Exception = Platform::Exception::CreateException(2147942487LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  result = *(unsigned int *)(a1 + 48);
  if ( (_DWORD)result != -1 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  *(_DWORD *)(a1 + 56) = a2;
  return result;
}

```

## disassembly

```asm
0x180093e30  mov     [rsp+arg_0], rbx
0x180093e35  push    rdi
0x180093e36  sub     rsp, 20h
0x180093e3a  mov     edi, edx
0x180093e3c  mov     rbx, rcx
0x180093e3f  call    ?_CheckValidStateForAsyncInfoCall@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@AE$AAAXXZ; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,1>::_CheckValidStateForAsyncInfoCall(void)
0x180093e44  test    edi, edi
0x180093e46  jnz     short loc_180093E77
0x180093e48  mov     ecx, 80070057h
0x180093e4d  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x180093e53  mov     [rsp+28h+arg_18], rax
0x180093e58  mov     rcx, rax
0x180093e5b  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180093e60  mov     [rsp+28h+pExceptionObject], rax
0x180093e65  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x180093e6c  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180093e71  call    _CxxThrowException_0
0x180093e77  mov     eax, [rbx+30h]
0x180093e7a  cmp     eax, 0FFFFFFFFh
0x180093e7d  jz      short loc_180093EAE
0x180093e7f  mov     ecx, 8000000Eh
0x180093e84  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x180093e8a  mov     [rsp+28h+arg_18], rax
0x180093e8f  mov     rcx, rax
0x180093e92  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180093e97  mov     [rsp+28h+pExceptionObject], rax
0x180093e9c  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x180093ea3  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180093ea8  call    _CxxThrowException_0
0x180093eae  mov     [rbx+38h], edi
0x180093eb1  mov     rbx, [rsp+28h+arg_0]
0x180093eb6  add     rsp, 20h
0x180093eba  pop     rdi
0x180093ebb  retn
```

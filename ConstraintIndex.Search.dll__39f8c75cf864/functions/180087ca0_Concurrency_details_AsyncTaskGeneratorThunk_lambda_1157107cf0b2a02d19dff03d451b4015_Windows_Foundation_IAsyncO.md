# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___::[Windows::Foundation::IAsyncOperation_bool_]::GetResults

- ea: `0x180087ca0`
- end: `0x180087d1a`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___::[Windows::Foundation::IAsyncOperation_bool_]::GetResults`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180087d20`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x180087ca0`
- `0x1800926c4`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180087caf`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180087ce3`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180087caf`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180087ce3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___::_Windows::Foundation::IAsyncOperation_bool__::GetResults(
        __int64 a1)
{
  int v1; // eax
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+38h] [rbp+10h]

  v1 = *(_DWORD *)(a1 + 56);
  if ( v1 == 3 )
  {
    Exception = Platform::Exception::CreateException(*(unsigned int *)(a1 + 60));
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  if ( v1 != 1 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  return Concurrency::task<bool>::get(a1 + 104);
}

```

## disassembly

```asm
0x180087ca0  sub     rsp, 28h
0x180087ca4  mov     eax, [rcx+38h]
0x180087ca7  cmp     eax, 3
0x180087caa  jnz     short loc_180087CD9
0x180087cac  mov     ecx, [rcx+3Ch]
0x180087caf  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x180087cb5  mov     [rsp+28h+arg_8], rax
0x180087cba  mov     rcx, rax
0x180087cbd  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180087cc2  mov     [rsp+28h+pExceptionObject], rax
0x180087cc7  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x180087cce  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180087cd3  call    _CxxThrowException_0
0x180087cd9  cmp     eax, 1
0x180087cdc  jz      short loc_180087D0D
0x180087cde  mov     ecx, 8000000Eh
0x180087ce3  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x180087ce9  mov     [rsp+28h+arg_8], rax
0x180087cee  mov     rcx, rax
0x180087cf1  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180087cf6  mov     [rsp+28h+pExceptionObject], rax
0x180087cfb  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x180087d02  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180087d07  call    _CxxThrowException_0
0x180087d0d  add     rcx, 68h ; 'h'
0x180087d11  add     rsp, 28h
0x180087d15  jmp     ?get@?$task@_N@Concurrency@@QEBA_NXZ; Concurrency::task<bool>::get(void)
```

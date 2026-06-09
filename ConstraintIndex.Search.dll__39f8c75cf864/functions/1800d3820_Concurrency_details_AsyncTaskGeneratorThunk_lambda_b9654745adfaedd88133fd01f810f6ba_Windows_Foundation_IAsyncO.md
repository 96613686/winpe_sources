# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___::[Windows::Foundation::IAsyncOperation_Windows::Foundation::Collections::IVectorView_Cortana::ConstraintIndex::Search::ISettingResultItem______]::GetResults

- ea: `0x1800d3820`
- end: `0x1800d38c5`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___::[Windows::Foundation::IAsyncOperation_Windows::Foundation::Collections::IVectorView_Cortana::ConstraintIndex::Search::ISettingResultItem______]::GetResults`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800d38d0`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x18003fee0`
- `0x1800d3820`
- `0x1800d5f40`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d386e`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d389b`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d386e`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d389b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___::_Windows::Foundation::IAsyncOperation_Windows::Foundation::Collections::IVectorView_Cortana::ConstraintIndex::Search::ISettingResultItem_______::GetResults(
        __int64 a1)
{
  int v1; // eax
  __int64 v2; // rdi
  __int64 v3; // rbx
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
  v2 = Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>::get(a1 + 104);
  pExceptionObject = v2;
  v3 = __abi_winrt_ptr_ctor(v2);
  __abi_winrt_ptr_dtor(v2);
  return v3;
}

```

## disassembly

```asm
0x1800d3820  mov     [rsp+arg_10], rbx
0x1800d3825  push    rdi
0x1800d3826  sub     rsp, 20h
0x1800d382a  mov     eax, [rcx+38h]
0x1800d382d  cmp     eax, 3
0x1800d3830  jz      short loc_1800D3898
0x1800d3832  cmp     eax, 1
0x1800d3835  jnz     short loc_1800D3869
0x1800d3837  add     rcx, 68h ; 'h'
0x1800d383b  call    ?get@?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@QEBAPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@XZ; Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>::get(void)
0x1800d3840  mov     rdi, rax
0x1800d3843  mov     [rsp+28h+pExceptionObject], rax
0x1800d3848  mov     rcx, rax
0x1800d384b  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d3850  mov     rbx, rax
0x1800d3853  mov     rcx, rdi
0x1800d3856  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800d385b  mov     rax, rbx
0x1800d385e  mov     rbx, [rsp+28h+arg_10]
0x1800d3863  add     rsp, 20h
0x1800d3867  pop     rdi
0x1800d3868  retn
0x1800d3869  mov     ecx, 8000000Eh
0x1800d386e  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800d3874  mov     [rsp+28h+arg_8], rax
0x1800d3879  mov     rcx, rax
0x1800d387c  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d3881  mov     [rsp+28h+pExceptionObject], rax
0x1800d3886  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800d388d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800d3892  call    _CxxThrowException_0
0x1800d3898  mov     ecx, [rcx+3Ch]
0x1800d389b  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800d38a1  mov     [rsp+28h+arg_8], rax
0x1800d38a6  mov     rcx, rax
0x1800d38a9  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d38ae  mov     [rsp+28h+pExceptionObject], rax
0x1800d38b3  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800d38ba  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800d38bf  call    _CxxThrowException_0
```

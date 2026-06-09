# _lambda_178beb9cc4277a98f7b459699a0e07b7_::operator()(Windows::Foundation::IAsyncOperation<uchar> *,Windows::Foundation::AsyncStatus)

- ea: `0x1800834d4`
- end: `0x1800835a9`
- name: `??R_lambda_178beb9cc4277a98f7b459699a0e07b7_@@QEAA@PE$AAU?$IAsyncOperation@E@Foundation@Windows@@W4AsyncStatus@23@@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180088040`

## callees

- `0x18003fee0`
- `0x18007e7a0`
- `0x1800834d4`
- `0x180087a78`
- `0x18008a114`
- `0x18008acd4`
- `0x18008ca74`
- `0x18008d90c`
- `0x180092490`
- `0x180092dcc`
- `0x180093800`

## import_xrefs

- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008352c`
- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x18008352c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_178beb9cc4277a98f7b459699a0e07b7_::operator()(
        Concurrency::details::_Task_impl_base **a1,
        __int64 a2,
        int a3)
{
  Concurrency::details::_Task_impl_base **v3; // rdi
  Concurrency::details::_Task_impl_base *v4; // rbx
  __int64 v5; // rsi
  unsigned int *v6; // rax
  __int64 Exception; // r14
  const struct std::exception_ptr *v8; // rdx
  Concurrency::details::_Task_impl_base *v9; // rbx
  Concurrency::details::_Task_impl_base *v11; // rbx
  const struct std::exception_ptr *v12; // rax
  _BYTE v13[8]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v14; // [rsp+28h] [rbp-20h]
  char v17; // [rsp+60h] [rbp+18h] BYREF
  __int64 v18; // [rsp+68h] [rbp+20h]

  v3 = a1;
  if ( a3 == 2 )
  {
    Concurrency::details::_Task_impl_base::_Cancel(*a1, 1);
  }
  else if ( a3 == 3 )
  {
    v4 = *a1;
    v5 = __abi_winrt_cast_to(0, a2, &_uuidof__AUIAsyncInfo_Foundation_Windows__);
    v6 = (unsigned int *)Windows::Foundation::IAsyncInfo::ErrorCode::get(v5, &v17);
    Exception = Platform::Exception::ReCreateException(*v6);
    v18 = Exception;
    v8 = (const struct std::exception_ptr *)std::make_exception_ptr<Platform::Exception __gc *>(v13, Exception);
    Concurrency::details::_Task_impl_base::_CancelWithException(v4, v8);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    __abi_winrt_ptr_dtor(Exception);
    __abi_winrt_ptr_dtor(v5);
  }
  else
  {
    v9 = *a1;
    try
    {
      Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<Platform::String __gc *,Windows::Data::Json::IJsonValue __gc *> __gc *>::MoveNext();
      Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v9);
    }
    catch ( ... )
    {
      v11 = *a1;
      v12 = (const struct std::exception_ptr *)std::current_exception(v13);
      Concurrency::details::_Task_impl_base::_CancelWithException(v11, v12);
      if ( v14 )
        std::_Ref_count_base::_Decref(v14);
      v3 = a1;
    }
  }
  return std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::reset(v3);
}

```

## disassembly

```asm
0x1800834d4  mov     [rsp+arg_8], rbx
0x1800834d9  mov     [rsp+arg_0], rcx
0x1800834de  push    rsi
0x1800834df  push    rdi
0x1800834e0  push    r14
0x1800834e2  sub     rsp, 30h
0x1800834e6  mov     rdi, rcx
0x1800834e9  cmp     r8d, 2
0x1800834ed  jnz     short loc_1800834FE
0x1800834ef  mov     dl, 1; bool
0x1800834f1  mov     rcx, [rcx]; this
0x1800834f4  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x1800834f9  jmp     loc_180083594
0x1800834fe  cmp     r8d, 3
0x180083502  jnz     short loc_180083577
0x180083504  mov     rbx, [rcx]
0x180083507  lea     r8, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x18008350e  xor     ecx, ecx
0x180083510  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180083515  mov     rsi, rax
0x180083518  mov     [rsp+48h+arg_0], rax
0x18008351d  lea     rdx, [rsp+48h+arg_10]
0x180083522  mov     rcx, rax
0x180083525  call    ?get@ErrorCode@IAsyncInfo@Foundation@Windows@@UE$AAA?AVHResult@34@XZ; Windows::Foundation::IAsyncInfo::ErrorCode::get(void)
0x18008352a  mov     ecx, [rax]
0x18008352c  call    cs:__imp_?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::ReCreateException(int)
0x180083532  mov     r14, rax
0x180083535  mov     [rsp+48h+arg_18], rax
0x18008353a  mov     rdx, rax
0x18008353d  lea     rcx, [rsp+48h+var_28]
0x180083542  call    ??$make_exception_ptr@PE$AAVException@Platform@@@std@@YA?AVexception_ptr@0@PE$AAVException@Platform@@@Z; std::make_exception_ptr<Platform::Exception *>(Platform::Exception *)
0x180083547  nop
0x180083548  mov     rdx, rax; struct std::exception_ptr *
0x18008354b  mov     rcx, rbx; this
0x18008354e  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180083553  nop
0x180083554  mov     rcx, [rsp+48h+var_20]; this
0x180083559  test    rcx, rcx
0x18008355c  jz      short loc_180083564
0x18008355e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083563  nop
0x180083564  mov     rcx, r14
0x180083567  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18008356c  nop
0x18008356d  mov     rcx, rsi
0x180083570  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180083575  jmp     short loc_180083594
0x180083577  mov     rbx, [rcx]
0x18008357a  mov     rcx, rdx
0x18008357d  call    ?MoveNext@?$IIterator@PE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@UE$AAA_NXZ; Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<Platform::String *,Windows::Data::Json::IJsonValue *> *>::MoveNext(void)
0x180083582  mov     dl, al
0x180083584  mov     rcx, rbx; this
0x180083587  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18008358c  nop
0x18008358d  jmp     short loc_180083594
0x18008358f  mov     rdi, [rsp+48h+arg_0]
0x180083594  mov     rcx, rdi
0x180083597  mov     rbx, [rsp+48h+arg_8]
0x18008359c  add     rsp, 30h
0x1800835a0  pop     r14
0x1800835a2  pop     rdi
0x1800835a3  pop     rsi
0x1800835a4  jmp     ?reset@?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAAXXZ; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::reset(void)
```

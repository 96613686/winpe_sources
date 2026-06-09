# _lambda_2d6874fcbaf6f2ee166cc75a56068fa3_::operator()(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Networking::BackgroundTransfer::DownloadOperation *> *> *,Windows::Foundation::AsyncStatus)

- ea: `0x180083798`
- end: `0x180083895`
- name: `??R_lambda_2d6874fcbaf6f2ee166cc75a56068fa3_@@QEAA@PE$AAU?$IAsyncOperation@PE$AAU?$IVectorView@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4AsyncStatus@23@@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180088050`

## callees

- `0x18003fee0`
- `0x18007e7a0`
- `0x180083798`
- `0x180086f1c`
- `0x18008a114`
- `0x18008acd4`
- `0x18008ca74`
- `0x18008d9a0`
- `0x180092490`
- `0x180092dcc`

## import_xrefs

- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800837f0`
- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800837f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall _lambda_2d6874fcbaf6f2ee166cc75a56068fa3_::operator()(
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
  Concurrency::details::_Task_impl_base *v9; // rsi
  __int64 Results; // rbx
  std::_Ref_count_base *v11; // rcx
  Concurrency::details::_Task_impl_base *v12; // rbx
  const struct std::exception_ptr *v13; // rax
  _BYTE v14[8]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v15; // [rsp+28h] [rbp-20h]
  char v18; // [rsp+60h] [rbp+18h] BYREF
  __int64 v19; // [rsp+68h] [rbp+20h]

  v3 = a1;
  if ( a3 == 2 )
  {
    Concurrency::details::_Task_impl_base::_Cancel(*a1, 1);
  }
  else if ( a3 == 3 )
  {
    v4 = *a1;
    v5 = __abi_winrt_cast_to(0, a2, &_uuidof__AUIAsyncInfo_Foundation_Windows__);
    v6 = (unsigned int *)Windows::Foundation::IAsyncInfo::ErrorCode::get(v5, &v18);
    Exception = Platform::Exception::ReCreateException(*v6);
    v19 = Exception;
    v8 = (const struct std::exception_ptr *)std::make_exception_ptr<Platform::Exception __gc *>(v14, Exception);
    Concurrency::details::_Task_impl_base::_CancelWithException(v4, v8);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    __abi_winrt_ptr_dtor(Exception);
    __abi_winrt_ptr_dtor(v5);
  }
  else
  {
    try
    {
      v9 = *a1;
      Results = Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(a2);
      v19 = Results;
      Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder __gc *> __gc *>::_FinalizeAndRunContinuations(v9);
      __abi_winrt_ptr_dtor(Results);
    }
    catch ( ... )
    {
      v12 = *a1;
      v13 = (const struct std::exception_ptr *)std::current_exception(v14);
      Concurrency::details::_Task_impl_base::_CancelWithException(v12, v13);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      v3 = a1;
    }
  }
  *v3 = 0;
  v11 = v3[1];
  v3[1] = 0;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
}

```

## disassembly

```asm
0x180083798  mov     [rsp+arg_8], rbx
0x18008379d  mov     [rsp+arg_0], rcx
0x1800837a2  push    rsi
0x1800837a3  push    rdi
0x1800837a4  push    r14
0x1800837a6  sub     rsp, 30h
0x1800837aa  mov     rdi, rcx
0x1800837ad  cmp     r8d, 2
0x1800837b1  jnz     short loc_1800837C2
0x1800837b3  mov     dl, 1; bool
0x1800837b5  mov     rcx, [rcx]; this
0x1800837b8  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x1800837bd  jmp     loc_18008386A
0x1800837c2  cmp     r8d, 3
0x1800837c6  jnz     short loc_18008383B
0x1800837c8  mov     rbx, [rcx]
0x1800837cb  lea     r8, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x1800837d2  xor     ecx, ecx
0x1800837d4  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800837d9  mov     rsi, rax
0x1800837dc  mov     [rsp+48h+arg_0], rax
0x1800837e1  lea     rdx, [rsp+48h+arg_10]
0x1800837e6  mov     rcx, rax
0x1800837e9  call    ?get@ErrorCode@IAsyncInfo@Foundation@Windows@@UE$AAA?AVHResult@34@XZ; Windows::Foundation::IAsyncInfo::ErrorCode::get(void)
0x1800837ee  mov     ecx, [rax]
0x1800837f0  call    cs:__imp_?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::ReCreateException(int)
0x1800837f6  mov     r14, rax
0x1800837f9  mov     [rsp+48h+arg_18], rax
0x1800837fe  mov     rdx, rax
0x180083801  lea     rcx, [rsp+48h+var_28]
0x180083806  call    ??$make_exception_ptr@PE$AAVException@Platform@@@std@@YA?AVexception_ptr@0@PE$AAVException@Platform@@@Z; std::make_exception_ptr<Platform::Exception *>(Platform::Exception *)
0x18008380b  nop
0x18008380c  mov     rdx, rax; struct std::exception_ptr *
0x18008380f  mov     rcx, rbx; this
0x180083812  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180083817  nop
0x180083818  mov     rcx, [rsp+48h+var_20]; this
0x18008381d  test    rcx, rcx
0x180083820  jz      short loc_180083828
0x180083822  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083827  nop
0x180083828  mov     rcx, r14
0x18008382b  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180083830  nop
0x180083831  mov     rcx, rsi
0x180083834  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180083839  jmp     short loc_18008386A
0x18008383b  mov     rsi, [rcx]
0x18008383e  mov     rcx, rdx
0x180083841  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x180083846  mov     rbx, rax
0x180083849  mov     [rsp+48h+arg_18], rax
0x18008384e  mov     rdx, rax
0x180083851  mov     rcx, rsi; this
0x180083854  call    ?_FinalizeAndRunContinuations@?$_Task_impl@PE$AAU?$IVectorView@PE$AAVStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@@details@Concurrency@@QEAAXPE$AAU?$IVectorView@PE$AAVStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@@Z; Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder *> *>::_FinalizeAndRunContinuations(Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder *> *)
0x180083859  nop
0x18008385a  mov     rcx, rbx
0x18008385d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180083862  nop
0x180083863  jmp     short loc_18008386A
0x180083865  mov     rdi, [rsp+48h+arg_0]
0x18008386a  mov     qword ptr [rdi], 0
0x180083871  mov     rcx, [rdi+8]; this
0x180083875  mov     qword ptr [rdi+8], 0
0x18008387d  test    rcx, rcx
0x180083880  jz      short loc_180083887
0x180083882  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083887  mov     rbx, [rsp+48h+arg_8]
0x18008388c  add     rsp, 30h
0x180083890  pop     r14
0x180083892  pop     rdi
0x180083893  pop     rsi
0x180083894  retn
```

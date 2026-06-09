# _lambda_a83208676a33b83c51ee2770de201984_::operator()(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *,Windows::Foundation::AsyncStatus)

- ea: `0x180083e10`
- end: `0x180083f0d`
- name: `??R_lambda_a83208676a33b83c51ee2770de201984_@@QEAA@PE$AAU?$IAsyncOperation@PE$AAVStorageFolder@Storage@Windows@@@Foundation@Windows@@W4AsyncStatus@23@@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180088060`

## callees

- `0x18003fee0`
- `0x18007e7a0`
- `0x180083e10`
- `0x180086f1c`
- `0x18008a114`
- `0x18008acd4`
- `0x18008ca74`
- `0x18008da78`
- `0x180092490`
- `0x180092dcc`

## import_xrefs

- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180083e68`
- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180083e68`

## pseudocode

```c
void __fastcall _lambda_a83208676a33b83c51ee2770de201984_::operator()(
        Concurrency::details::_Task_impl_base **a1,
        __int64 a2,
        int a3)
{
  Concurrency::details::_Task_impl_base *v4; // rbx
  __int64 v5; // rsi
  unsigned int *v6; // rax
  __int64 Exception; // r14
  const struct std::exception_ptr *v8; // rax
  Concurrency::details::_Task_impl_base *v9; // rsi
  __int64 Results; // rbx
  std::_Ref_count_base *v11; // rcx
  _BYTE v12[8]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v13; // [rsp+28h] [rbp-20h]
  char v14; // [rsp+60h] [rbp+18h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h]

  if ( a3 == 2 )
  {
    Concurrency::details::_Task_impl_base::_Cancel(*a1, 1);
  }
  else if ( a3 == 3 )
  {
    v4 = *a1;
    v5 = __abi_winrt_cast_to(0, a2, &_uuidof__AUIAsyncInfo_Foundation_Windows__);
    v6 = (unsigned int *)Windows::Foundation::IAsyncInfo::ErrorCode::get(v5, &v14);
    Exception = Platform::Exception::ReCreateException(*v6);
    v15 = Exception;
    v8 = (const struct std::exception_ptr *)std::make_exception_ptr<Platform::Exception __gc *>(v12, Exception);
    Concurrency::details::_Task_impl_base::_CancelWithException(v4, v8);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    __abi_winrt_ptr_dtor(Exception);
    __abi_winrt_ptr_dtor(v5);
  }
  else
  {
    v9 = *a1;
    Results = Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(a2);
    v15 = Results;
    Concurrency::details::_Task_impl<WindowsUdk::Services::Experiences::ExperiencePack __gc *>::_FinalizeAndRunContinuations(v9);
    __abi_winrt_ptr_dtor(Results);
  }
  *a1 = 0;
  v11 = a1[1];
  a1[1] = 0;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
}

```

## disassembly

```asm
0x180083e10  mov     [rsp+arg_8], rbx
0x180083e15  mov     [rsp+arg_0], rcx
0x180083e1a  push    rsi
0x180083e1b  push    rdi
0x180083e1c  push    r14
0x180083e1e  sub     rsp, 30h
0x180083e22  mov     rdi, rcx
0x180083e25  cmp     r8d, 2
0x180083e29  jnz     short loc_180083E3A
0x180083e2b  mov     dl, 1; bool
0x180083e2d  mov     rcx, [rcx]; this
0x180083e30  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x180083e35  jmp     loc_180083EE2
0x180083e3a  cmp     r8d, 3
0x180083e3e  jnz     short loc_180083EB3
0x180083e40  mov     rbx, [rcx]
0x180083e43  lea     r8, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x180083e4a  xor     ecx, ecx
0x180083e4c  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180083e51  mov     rsi, rax
0x180083e54  mov     [rsp+48h+arg_0], rax
0x180083e59  lea     rdx, [rsp+48h+arg_10]
0x180083e5e  mov     rcx, rax
0x180083e61  call    ?get@ErrorCode@IAsyncInfo@Foundation@Windows@@UE$AAA?AVHResult@34@XZ; Windows::Foundation::IAsyncInfo::ErrorCode::get(void)
0x180083e66  mov     ecx, [rax]
0x180083e68  call    cs:__imp_?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::ReCreateException(int)
0x180083e6e  mov     r14, rax
0x180083e71  mov     [rsp+48h+arg_18], rax
0x180083e76  mov     rdx, rax
0x180083e79  lea     rcx, [rsp+48h+var_28]
0x180083e7e  call    ??$make_exception_ptr@PE$AAVException@Platform@@@std@@YA?AVexception_ptr@0@PE$AAVException@Platform@@@Z; std::make_exception_ptr<Platform::Exception *>(Platform::Exception *)
0x180083e83  nop
0x180083e84  mov     rdx, rax; struct std::exception_ptr *
0x180083e87  mov     rcx, rbx; this
0x180083e8a  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180083e8f  nop
0x180083e90  mov     rcx, [rsp+48h+var_20]; this
0x180083e95  test    rcx, rcx
0x180083e98  jz      short loc_180083EA0
0x180083e9a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083e9f  nop
0x180083ea0  mov     rcx, r14
0x180083ea3  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180083ea8  nop
0x180083ea9  mov     rcx, rsi
0x180083eac  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180083eb1  jmp     short loc_180083EE2
0x180083eb3  mov     rsi, [rcx]
0x180083eb6  mov     rcx, rdx
0x180083eb9  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x180083ebe  mov     rbx, rax
0x180083ec1  mov     [rsp+48h+arg_18], rax
0x180083ec6  mov     rdx, rax
0x180083ec9  mov     rcx, rsi; this
0x180083ecc  call    ?_FinalizeAndRunContinuations@?$_Task_impl@PE$AAVExperiencePack@Experiences@Services@WindowsUdk@@@details@Concurrency@@QEAAXPE$AAVExperiencePack@Experiences@Services@WindowsUdk@@@Z; Concurrency::details::_Task_impl<WindowsUdk::Services::Experiences::ExperiencePack *>::_FinalizeAndRunContinuations(WindowsUdk::Services::Experiences::ExperiencePack *)
0x180083ed1  nop
0x180083ed2  mov     rcx, rbx
0x180083ed5  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180083eda  nop
0x180083edb  jmp     short loc_180083EE2
0x180083edd  mov     rdi, [rsp+48h+arg_0]
0x180083ee2  mov     qword ptr [rdi], 0
0x180083ee9  mov     rcx, [rdi+8]; this
0x180083eed  mov     qword ptr [rdi+8], 0
0x180083ef5  test    rcx, rcx
0x180083ef8  jz      short loc_180083EFF
0x180083efa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083eff  mov     rbx, [rsp+48h+arg_8]
0x180083f04  add     rsp, 30h
0x180083f08  pop     r14
0x180083f0a  pop     rdi
0x180083f0b  pop     rsi
0x180083f0c  retn
```

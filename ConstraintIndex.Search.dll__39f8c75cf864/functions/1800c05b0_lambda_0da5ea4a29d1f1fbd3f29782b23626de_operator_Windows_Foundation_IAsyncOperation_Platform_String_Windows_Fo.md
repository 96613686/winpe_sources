# _lambda_0da5ea4a29d1f1fbd3f29782b23626de_::operator()(Windows::Foundation::IAsyncOperation<Platform::String *> *,Windows::Foundation::AsyncStatus)

- ea: `0x1800c05b0`
- end: `0x1800c06ad`
- name: `??R_lambda_0da5ea4a29d1f1fbd3f29782b23626de_@@QEAA@PE$AAU?$IAsyncOperation@PE$AAVString@Platform@@@Foundation@Windows@@W4AsyncStatus@23@@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x1800c37b0`

## callees

- `0x18000617a`
- `0x18003fee0`
- `0x18007e7a0`
- `0x18008a114`
- `0x18008acd4`
- `0x18008ca74`
- `0x180092490`
- `0x180092be4`
- `0x180092dcc`
- `0x1800c05b0`
- `0x1800c74b0`

## import_xrefs

- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800c0608`
- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800c0608`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall _lambda_0da5ea4a29d1f1fbd3f29782b23626de_::operator()(
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
  HSTRING Results; // rbx
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
      Results = (HSTRING)Windows::Foundation::IAsyncOperation<Platform::String __gc *>::GetResults(a2);
      v19 = (__int64)Results;
      Concurrency::details::_Task_impl<Platform::String __gc *>::_FinalizeAndRunContinuations(v9);
      WindowsDeleteString_0(Results);
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
0x1800c05b0  mov     [rsp+arg_8], rbx
0x1800c05b5  mov     [rsp+arg_0], rcx
0x1800c05ba  push    rsi
0x1800c05bb  push    rdi
0x1800c05bc  push    r14
0x1800c05be  sub     rsp, 30h
0x1800c05c2  mov     rdi, rcx
0x1800c05c5  cmp     r8d, 2
0x1800c05c9  jnz     short loc_1800C05DA
0x1800c05cb  mov     dl, 1; bool
0x1800c05cd  mov     rcx, [rcx]; this
0x1800c05d0  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x1800c05d5  jmp     loc_1800C0682
0x1800c05da  cmp     r8d, 3
0x1800c05de  jnz     short loc_1800C0653
0x1800c05e0  mov     rbx, [rcx]
0x1800c05e3  lea     r8, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x1800c05ea  xor     ecx, ecx
0x1800c05ec  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800c05f1  mov     rsi, rax
0x1800c05f4  mov     [rsp+48h+arg_0], rax
0x1800c05f9  lea     rdx, [rsp+48h+arg_10]
0x1800c05fe  mov     rcx, rax
0x1800c0601  call    ?get@ErrorCode@IAsyncInfo@Foundation@Windows@@UE$AAA?AVHResult@34@XZ; Windows::Foundation::IAsyncInfo::ErrorCode::get(void)
0x1800c0606  mov     ecx, [rax]
0x1800c0608  call    cs:__imp_?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::ReCreateException(int)
0x1800c060e  mov     r14, rax
0x1800c0611  mov     [rsp+48h+arg_18], rax
0x1800c0616  mov     rdx, rax
0x1800c0619  lea     rcx, [rsp+48h+var_28]
0x1800c061e  call    ??$make_exception_ptr@PE$AAVException@Platform@@@std@@YA?AVexception_ptr@0@PE$AAVException@Platform@@@Z; std::make_exception_ptr<Platform::Exception *>(Platform::Exception *)
0x1800c0623  nop
0x1800c0624  mov     rdx, rax; struct std::exception_ptr *
0x1800c0627  mov     rcx, rbx; this
0x1800c062a  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1800c062f  nop
0x1800c0630  mov     rcx, [rsp+48h+var_20]; this
0x1800c0635  test    rcx, rcx
0x1800c0638  jz      short loc_1800C0640
0x1800c063a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c063f  nop
0x1800c0640  mov     rcx, r14
0x1800c0643  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c0648  nop
0x1800c0649  mov     rcx, rsi
0x1800c064c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c0651  jmp     short loc_1800C0682
0x1800c0653  mov     rsi, [rcx]
0x1800c0656  mov     rcx, rdx
0x1800c0659  call    ?GetResults@?$IAsyncOperation@PE$AAVString@Platform@@@Foundation@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::Foundation::IAsyncOperation<Platform::String *>::GetResults(void)
0x1800c065e  mov     rbx, rax
0x1800c0661  mov     [rsp+48h+arg_18], rax
0x1800c0666  mov     rdx, rax
0x1800c0669  mov     rcx, rsi; this
0x1800c066c  call    ?_FinalizeAndRunContinuations@?$_Task_impl@PE$AAVString@Platform@@@details@Concurrency@@QEAAXPE$AAVString@Platform@@@Z; Concurrency::details::_Task_impl<Platform::String *>::_FinalizeAndRunContinuations(Platform::String *)
0x1800c0671  nop
0x1800c0672  mov     rcx, rbx; string
0x1800c0675  call    WindowsDeleteString_0
0x1800c067a  nop
0x1800c067b  jmp     short loc_1800C0682
0x1800c067d  mov     rdi, [rsp+48h+arg_0]
0x1800c0682  mov     qword ptr [rdi], 0
0x1800c0689  mov     rcx, [rdi+8]; this
0x1800c068d  mov     qword ptr [rdi+8], 0
0x1800c0695  test    rcx, rcx
0x1800c0698  jz      short loc_1800C069F
0x1800c069a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c069f  mov     rbx, [rsp+48h+arg_8]
0x1800c06a4  add     rsp, 30h
0x1800c06a8  pop     r14
0x1800c06aa  pop     rdi
0x1800c06ab  pop     rsi
0x1800c06ac  retn
```

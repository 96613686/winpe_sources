# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::Cancel(void)

- ea: `0x1800205dc`
- end: `0x1800206c3`
- name: `?Cancel@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800205b0`

## callees

- `0x180003aac`
- `0x180003ab8`
- `0x180005a1c`
- `0x180005e78`
- `0x18001e1f8`
- `0x18001f264`
- `0x1800205dc`
- `0x18002b010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180020644`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180020644`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002064f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002064f`

## pseudocode

```c
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::Cancel(
        __int64 a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  void (__fastcall *v4)(_QWORD); // rax
  _QWORD v5[2]; // [rsp+20h] [rbp-48h] BYREF
  int v6; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+38h] [rbp-30h]
  _BYTE v8[24]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v9; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  v9 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( !*(_DWORD *)(a1 + 96) )
  {
    *(_DWORD *)(a1 + 96) = 2;
    v6 = 0;
    v7 = 0;
    winrt::hresult_error::hresult_error(v8, winrt::impl::error_canceled, &v6);
    v3 = std::make_exception_ptr<winrt::hresult_canceled>(v5, v8);
    __ExceptionPtrAssign((void *)(a1 + 56), v3);
    __ExceptionPtrDestroy(v5);
    winrt::Windows::Foundation::IUnknown::operator=(&v9, a1 + 88);
    v2 = v9;
  }
  ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 72));
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  v4 = (void (__fastcall *)(_QWORD))_InterlockedExchange64((volatile __int64 *)(a1 + 32), 1);
  if ( (unsigned __int64)v4 >= 2 )
    v4(*(_QWORD *)(a1 + 40));
  *(_QWORD *)(a1 + 32) = 0;
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v9);
}

```

## disassembly

```asm
0x1800205dc  mov     [rsp+arg_8], rbx
0x1800205e1  mov     [rsp+arg_10], rsi
0x1800205e6  push    rdi
0x1800205e7  sub     rsp, 60h
0x1800205eb  mov     rdi, rcx
0x1800205ee  xor     ebx, ebx
0x1800205f0  mov     [rsp+68h+arg_0], rbx
0x1800205f5  add     rcx, 48h ; 'H'; SRWLock
0x1800205f9  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800205fe  mov     eax, [rdi+60h]
0x180020601  test    eax, eax
0x180020603  jnz     short loc_180020668
0x180020605  mov     dword ptr [rdi+60h], 2
0x18002060c  mov     [rsp+68h+var_38], ebx
0x180020610  xorps   xmm0, xmm0
0x180020613  movdqu  [rsp+68h+var_30], xmm0
0x180020619  lea     r8, [rsp+68h+var_38]
0x18002061e  mov     edx, cs:?error_canceled@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_canceled
0x180020624  lea     rcx, [rsp+68h+var_20]
0x180020629  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002062e  lea     rdx, [rsp+68h+var_20]
0x180020633  lea     rcx, [rsp+68h+var_48]
0x180020638  call    ??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z; std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)
0x18002063d  lea     rcx, [rdi+38h]
0x180020641  mov     rdx, rax
0x180020644  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002064a  lea     rcx, [rsp+68h+var_48]
0x18002064f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180020655  lea     rdx, [rdi+58h]
0x180020659  lea     rcx, [rsp+68h+arg_0]
0x18002065e  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180020663  mov     rbx, [rsp+68h+arg_0]
0x180020668  lea     rcx, [rdi+48h]; SRWLock
0x18002066c  call    ReleaseSRWLockExclusive_0
0x180020671  test    rbx, rbx
0x180020674  jz      short loc_180020685
0x180020676  mov     rax, [rbx]
0x180020679  mov     rcx, rbx
0x18002067c  mov     rax, [rax+18h]
0x180020680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020685  mov     eax, 1
0x18002068a  xchg    rax, [rdi+20h]
0x18002068e  cmp     rax, 2
0x180020692  jb      short loc_18002069D
0x180020694  mov     rcx, [rdi+28h]
0x180020698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002069d  nop
0x18002069e  mov     qword ptr [rdi+20h], 0
0x1800206a6  lea     rcx, [rsp+68h+arg_0]; this
0x1800206ab  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800206b0  nop
0x1800206b1  lea     r11, [rsp+68h+var_8]
0x1800206b6  mov     rbx, [r11+18h]
0x1800206ba  mov     rsi, [r11+20h]
0x1800206be  mov     rsp, r11
0x1800206c1  pop     rdi
0x1800206c2  retn
```

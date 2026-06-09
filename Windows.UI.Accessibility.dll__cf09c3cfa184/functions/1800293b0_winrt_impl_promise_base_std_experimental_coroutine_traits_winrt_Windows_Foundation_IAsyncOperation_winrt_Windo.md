# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::Completed(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController> const &)

- ea: `0x1800293b0`
- end: `0x180029479`
- name: `?Completed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXAEBU?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@3@@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a470`

## callees

- `0x180004601`
- `0x18000460d`
- `0x1800050da`
- `0x1800072d8`
- `0x180007924`
- `0x180007e64`
- `0x180028a38`
- `0x180028ad4`
- `0x180028e60`
- `0x1800293b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::Completed(
        __int64 a1,
        _QWORD *a2)
{
  RTL_SRWLOCK *v4; // rdi
  __int64 v5; // rax
  const struct winrt::impl::slim_source_location *v6; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  v4 = (RTL_SRWLOCK *)(a1 + 72);
  v9 = a1 + 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( *(_BYTE *)(a1 + 100) )
  {
    v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v8);
    winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(
      (winrt::hresult_illegal_delegate_assignment *)pExceptionObject,
      v6);
    throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
  }
  *(_BYTE *)(a1 + 100) = 1;
  LODWORD(v9) = *(_DWORD *)(a1 + 96);
  if ( (_DWORD)v9 )
  {
    ReleaseSRWLockExclusive_0(v4);
    if ( *a2 )
      winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>,enum winrt::Windows::Foundation::AsyncStatus>(
        a2,
        a1,
        &v9);
  }
  else
  {
    v5 = winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>((winrt::Windows::Foundation::IUnknown *)&v9);
    winrt::Windows::Foundation::IUnknown::operator=(a1 + 80, v5);
    if ( v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    ReleaseSRWLockExclusive_0(v4);
  }
}

```

## disassembly

```asm
0x1800293b0  mov     [rsp+arg_8], rbx
0x1800293b5  mov     [rsp+arg_10], rsi
0x1800293ba  push    rdi
0x1800293bb  sub     rsp, 50h
0x1800293bf  mov     rsi, rdx
0x1800293c2  mov     rbx, rcx
0x1800293c5  lea     rdi, [rcx+48h]
0x1800293c9  mov     [rsp+58h+arg_0], rdi
0x1800293ce  mov     rcx, rdi; SRWLock
0x1800293d1  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800293d6  nop
0x1800293d7  cmp     byte ptr [rbx+64h], 0
0x1800293db  jnz     short loc_180029450
0x1800293dd  mov     byte ptr [rbx+64h], 1
0x1800293e1  mov     eax, [rbx+60h]
0x1800293e4  mov     dword ptr [rsp+58h+arg_0], eax
0x1800293e8  test    eax, eax
0x1800293ea  jnz     short loc_180029422
0x1800293ec  mov     rdx, rsi
0x1800293ef  lea     rcx, [rsp+58h+arg_0]; this
0x1800293f4  call    ??$make_agile_delegate@U?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController> const &)
0x1800293f9  lea     rcx, [rbx+50h]
0x1800293fd  mov     rdx, rax
0x180029400  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180029405  cmp     [rsp+58h+arg_0], 0
0x18002940b  jz      short loc_180029418
0x18002940d  lea     rcx, [rsp+58h+arg_0]
0x180029412  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180029417  nop
0x180029418  mov     rcx, rdi; SRWLock
0x18002941b  call    ReleaseSRWLockExclusive_0
0x180029420  jmp     short loc_180029440
0x180029422  mov     rcx, rdi; SRWLock
0x180029425  call    ReleaseSRWLockExclusive_0
0x18002942a  cmp     qword ptr [rsi], 0
0x18002942e  jz      short loc_180029440
0x180029430  lea     r8, [rsp+58h+arg_0]
0x180029435  mov     rdx, rbx
0x180029438  mov     rcx, rsi
0x18002943b  call    ??$invoke@U?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBU?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController> const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180029440  mov     rbx, [rsp+58h+arg_8]
0x180029445  mov     rsi, [rsp+58h+arg_10]
0x18002944a  add     rsp, 50h
0x18002944e  pop     rdi
0x18002944f  retn
0x180029450  lea     rcx, [rsp+58h+var_20]
0x180029455  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002945a  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002945d  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180029462  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::impl::slim_source_location const &)
0x180029467  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18002946e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180029473  call    _CxxThrowException_0
```

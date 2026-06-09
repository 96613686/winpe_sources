# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::put_Completed(void *)

- ea: `0x180008c70`
- end: `0x180008d7e`
- name: `?put_Completed@?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@UEAAHPEAX@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003840`
- `0x180008c70`
- `0x18000a420`
- `0x18000a470`
- `0x18000e0a0`
- `0x1800162aa`
- `0x1800162b0`
- `0x1800181b0`
- `0x180019c0c`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::put_Completed(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdi
  RTL_SRWLOCK *v4; // rbx
  __int64 *v5; // rsi
  __int64 *v6; // rdi
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h] BYREF

  v11 = a2;
  v3 = a1 - 16;
  if ( !a1 )
    v3 = 0;
  v4 = (RTL_SRWLOCK *)(v3 + 72);
  v9 = v3 + 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(v3 + 72));
  if ( *(_BYTE *)(v3 + 100) )
  {
    winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment((winrt::hresult_illegal_delegate_assignment *)pExceptionObject);
    throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
  }
  *(_BYTE *)(v3 + 100) = 1;
  LODWORD(v9) = *(_DWORD *)(v3 + 96);
  if ( (_DWORD)v9 )
  {
    ReleaseSRWLockExclusive_0((PSRWLOCK)(v3 + 72));
    if ( a2 )
      winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,enum winrt::Windows::Foundation::AsyncStatus>(
        &v11,
        v3,
        (unsigned int *)&v9);
  }
  else
  {
    v5 = winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>(&v9, &v11);
    v6 = (__int64 *)(v3 + 80);
    if ( v6 != v5 )
    {
      if ( *v6 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
      v7 = *v5;
      *v5 = 0;
      *v6 = v7;
    }
    if ( v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    ReleaseSRWLockExclusive_0(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180008c70  mov     [rsp+arg_10], rbx
0x180008c75  push    rsi
0x180008c76  push    rdi
0x180008c77  push    r14
0x180008c79  sub     rsp, 50h
0x180008c7d  mov     rax, cs:__security_cookie
0x180008c84  xor     rax, rsp
0x180008c87  mov     [rsp+68h+var_20], rax
0x180008c8c  mov     rsi, rdx
0x180008c8f  mov     [rsp+68h+var_28], rdx
0x180008c94  lea     rdi, [rcx-10h]
0x180008c98  xor     r14d, r14d
0x180008c9b  test    rcx, rcx
0x180008c9e  cmovz   rdi, r14
0x180008ca2  lea     rbx, [rdi+48h]
0x180008ca6  mov     [rsp+68h+var_48], rbx
0x180008cab  mov     rcx, rbx; SRWLock
0x180008cae  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180008cb3  nop
0x180008cb4  cmp     [rdi+64h], r14b
0x180008cb8  jnz     loc_180008D61
0x180008cbe  mov     byte ptr [rdi+64h], 1
0x180008cc2  mov     eax, [rdi+60h]
0x180008cc5  mov     dword ptr [rsp+68h+var_48], eax
0x180008cc9  test    eax, eax
0x180008ccb  jnz     short loc_180008D1C
0x180008ccd  lea     rdx, [rsp+68h+var_28]
0x180008cd2  lea     rcx, [rsp+68h+var_48]
0x180008cd7  call    ??$make_agile_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@YA?AUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &)
0x180008cdc  mov     rsi, rax
0x180008cdf  add     rdi, 50h ; 'P'
0x180008ce3  cmp     rdi, rax
0x180008ce6  jz      short loc_180008CFF
0x180008ce8  cmp     qword ptr [rdi], 0
0x180008cec  jz      short loc_180008CF6
0x180008cee  mov     rcx, rdi
0x180008cf1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008cf6  mov     rcx, [rsi]
0x180008cf9  mov     [rsi], r14
0x180008cfc  mov     [rdi], rcx
0x180008cff  cmp     [rsp+68h+var_48], 0
0x180008d05  jz      short loc_180008D12
0x180008d07  lea     rcx, [rsp+68h+var_48]
0x180008d0c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008d11  nop
0x180008d12  mov     rcx, rbx; SRWLock
0x180008d15  call    ReleaseSRWLockExclusive_0
0x180008d1a  jmp     short loc_180008D3B
0x180008d1c  mov     rcx, rbx; SRWLock
0x180008d1f  call    ReleaseSRWLockExclusive_0
0x180008d24  test    rsi, rsi
0x180008d27  jz      short loc_180008D3B
0x180008d29  lea     r8, [rsp+68h+var_48]
0x180008d2e  mov     rdx, rdi
0x180008d31  lea     rcx, [rsp+68h+var_28]
0x180008d36  call    ??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180008d3b  xor     eax, eax
0x180008d3d  jmp     short loc_180008D43
0x180008d3f  mov     eax, dword ptr [rsp+68h+var_48]
0x180008d43  mov     rcx, [rsp+68h+var_20]
0x180008d48  xor     rcx, rsp; StackCookie
0x180008d4b  call    __security_check_cookie
0x180008d50  mov     rbx, [rsp+68h+arg_10]
0x180008d58  add     rsp, 50h
0x180008d5c  pop     r14
0x180008d5e  pop     rdi
0x180008d5f  pop     rsi
0x180008d60  retn
0x180008d61  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180008d66  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@XZ; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(void)
0x180008d6b  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180008d72  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180008d77  call    _CxxThrowException
```

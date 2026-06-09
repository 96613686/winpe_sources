# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::Cancel(void)

- ea: `0x180008850`
- end: `0x1800089a2`
- name: `?Cancel@?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@UEAAHXZ`
- size: `338`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003840`
- `0x180003b50`
- `0x180008850`
- `0x1800162aa`
- `0x1800162b0`
- `0x180017c9c`
- `0x180017cd0`
- `0x180017cfc`
- `0x180017d94`
- `0x18001c759`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::Cancel(
        __int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
  __int64 *v3; // rax
  void (__fastcall *v4)(_QWORD); // rax
  __int64 v6; // [rsp+20h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-40h] BYREF
  int v8; // [rsp+30h] [rbp-38h]
  int v9; // [rsp+34h] [rbp-34h]
  __int64 v10; // [rsp+38h] [rbp-30h] BYREF
  _OWORD v11[2]; // [rsp+40h] [rbp-28h] BYREF

  v1 = a1 - 24;
  if ( !a1 )
    v1 = 0;
  v2 = 0;
  v6 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(v1 + 72));
  if ( !*(_DWORD *)(v1 + 96) )
  {
    *(_DWORD *)(v1 + 96) = 2;
    bstrString = 0;
    v8 = -1430532899;
    v9 = -2147023673;
    v10 = 0;
    winrt::hresult_error::originate(&bstrString, 2147943623LL, 0);
    v11[0] = 0;
    __ExceptionPtrCreate(v11);
    __ExceptionPtrCopyException(v11, &bstrString, &TI2_AUhresult_canceled_winrt__);
    if ( v10 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    if ( bstrString )
    {
      WINRT_IMPL_SysFreeString(bstrString);
      bstrString = 0;
    }
    __ExceptionPtrAssign((void *)(v1 + 56), v11);
    __ExceptionPtrDestroy(v11);
    v3 = (__int64 *)(v1 + 88);
    if ( &v6 != (__int64 *)(v1 + 88) )
    {
      v2 = *v3;
      *v3 = 0;
      v6 = v2;
    }
  }
  ReleaseSRWLockExclusive_0((PSRWLOCK)(v1 + 72));
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  v4 = (void (__fastcall *)(_QWORD))_InterlockedExchange64((volatile __int64 *)(v1 + 32), 1);
  if ( (unsigned __int64)v4 >= 2 )
    v4(*(_QWORD *)(v1 + 40));
  *(_QWORD *)(v1 + 32) = 0;
  if ( v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v6);
  return 0;
}

```

## disassembly

```asm
0x180008850  mov     [rsp+arg_8], rbx
0x180008855  mov     [rsp+arg_10], rbp
0x18000885a  mov     [rsp+arg_18], rsi
0x18000885f  push    rdi
0x180008860  sub     rsp, 60h
0x180008864  xor     ebp, ebp
0x180008866  lea     rsi, [rcx-18h]
0x18000886a  test    rcx, rcx
0x18000886d  cmovz   rsi, rbp
0x180008871  mov     ebx, ebp
0x180008873  mov     [rsp+68h+var_48], rbx
0x180008878  lea     rcx, [rsi+48h]; SRWLock
0x18000887c  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180008881  mov     eax, [rsi+60h]
0x180008884  test    eax, eax
0x180008886  jnz     loc_18000893E
0x18000888c  mov     dword ptr [rsi+60h], 2
0x180008893  mov     [rsp+68h+bstrString], rbp
0x180008898  mov     [rsp+68h+var_38], 0AABBCCDDh
0x1800088a0  mov     [rsp+68h+var_34], 800704C7h
0x1800088a8  mov     [rsp+68h+var_30], rbp
0x1800088ad  xor     r8d, r8d
0x1800088b0  mov     edx, 800704C7h
0x1800088b5  lea     rcx, [rsp+68h+bstrString]
0x1800088ba  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAX@Z; winrt::hresult_error::originate(winrt::hresult,void *)
0x1800088bf  xorps   xmm0, xmm0
0x1800088c2  movdqu  [rsp+68h+var_28], xmm0
0x1800088c8  lea     rcx, [rsp+68h+var_28]; void *
0x1800088cd  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800088d2  lea     r8, _TI2?AUhresult_canceled@winrt@@; void *
0x1800088d9  lea     rdx, [rsp+68h+bstrString]; void *
0x1800088de  lea     rcx, [rsp+68h+var_28]; void *
0x1800088e3  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800088e8  cmp     [rsp+68h+var_30], rbx
0x1800088ed  jz      short loc_1800088F9
0x1800088ef  lea     rcx, [rsp+68h+var_30]
0x1800088f4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800088f9  mov     rcx, [rsp+68h+bstrString]; bstrString
0x1800088fe  test    rcx, rcx
0x180008901  jz      short loc_18000890D
0x180008903  call    WINRT_IMPL_SysFreeString
0x180008908  mov     [rsp+68h+bstrString], rbp
0x18000890d  lea     rcx, [rsi+38h]; void *
0x180008911  lea     rdx, [rsp+68h+var_28]; void *
0x180008916  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18000891b  lea     rcx, [rsp+68h+var_28]; void *
0x180008920  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180008925  lea     rax, [rsi+58h]
0x180008929  lea     rcx, [rsp+68h+var_48]
0x18000892e  cmp     rcx, rax
0x180008931  jz      short loc_18000893E
0x180008933  mov     rbx, [rax]
0x180008936  mov     [rax], rbp
0x180008939  mov     [rsp+68h+var_48], rbx
0x18000893e  lea     rcx, [rsi+48h]; SRWLock
0x180008942  call    ReleaseSRWLockExclusive_0
0x180008947  test    rbx, rbx
0x18000894a  jz      short loc_18000895C
0x18000894c  mov     rax, [rbx]
0x18000894f  mov     rcx, rbx
0x180008952  mov     rax, [rax+18h]
0x180008956  call    cs:__guard_dispatch_icall_fptr
0x18000895c  mov     eax, 1
0x180008961  xchg    rax, [rsi+20h]
0x180008965  cmp     rax, 2
0x180008969  jb      short loc_180008975
0x18000896b  mov     rcx, [rsi+28h]
0x18000896f  call    cs:__guard_dispatch_icall_fptr
0x180008975  mov     [rsi+20h], rbp
0x180008979  test    rbx, rbx
0x18000897c  jz      short loc_180008989
0x18000897e  lea     rcx, [rsp+68h+var_48]
0x180008983  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008988  nop
0x180008989  xor     eax, eax
0x18000898b  lea     r11, [rsp+68h+var_8]
0x180008990  mov     rbx, [r11+18h]
0x180008994  mov     rbp, [r11+20h]
0x180008998  mov     rsi, [r11+28h]
0x18000899c  mov     rsp, r11
0x18000899f  pop     rdi
0x1800089a0  retn
```

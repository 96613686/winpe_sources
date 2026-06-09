# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::Cancel(void)

- ea: `0x180006e30`
- end: `0x180006fc3`
- name: `?Cancel@?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@UEAAHXZ`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002088`
- `0x180002094`
- `0x1800020a9`
- `0x180006e30`
- `0x18000964c`
- `0x18000a014`
- `0x18000d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180006ed9`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180006ed9`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180006f19`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180006f19`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180006f24`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180006f24`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180006ec2`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180006ec2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::Cancel(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // r14
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  void (__fastcall *v9)(_QWORD); // rax
  __int64 result; // rax
  __int64 v11; // [rsp+20h] [rbp-78h] BYREF
  __int128 v12; // [rsp+28h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-60h] BYREF
  int v14; // [rsp+40h] [rbp-58h]
  int v15; // [rsp+44h] [rbp-54h]
  __int64 v16; // [rsp+48h] [rbp-50h] BYREF
  int v17; // [rsp+50h] [rbp-48h] BYREF
  __int128 v18; // [rsp+58h] [rbp-40h]
  int v19; // [rsp+A0h] [rbp+8h] BYREF

  v2 = 0;
  v11 = 0;
  v3 = a1 + 48;
  if ( !a1 )
    v3 = 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)v3);
  v4 = a1 + 72;
  if ( !a1 )
    v4 = 96;
  v5 = 0;
  if ( !*(_DWORD *)v4 )
  {
    *(_DWORD *)v4 = 2;
    v17 = 0;
    v18 = 0;
    bstrString = 0;
    v14 = -1430532899;
    v15 = -2147023673;
    v16 = 0;
    winrt::hresult_error::originate(&bstrString, 2147943623LL, 0, &v17, v11);
    v12 = 0;
    __ExceptionPtrCreate(&v12);
    __ExceptionPtrCopyException(&v12, &bstrString, &TI2_AUhresult_canceled_winrt__);
    if ( v16 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
    if ( bstrString )
    {
      WINRT_IMPL_SysFreeString(bstrString);
      bstrString = 0;
    }
    v6 = a1 + 32;
    if ( !a1 )
      v6 = 56;
    __ExceptionPtrAssign((void *)v6, &v12);
    __ExceptionPtrDestroy(&v12);
    v7 = a1 + 64;
    if ( !a1 )
      v7 = 88;
    if ( &v11 != (__int64 *)v7 )
    {
      v2 = *(_QWORD *)v7;
      *(_QWORD *)v7 = 0;
      v11 = v2;
      v5 = v2;
    }
  }
  ReleaseSRWLockExclusive_0((PSRWLOCK)v3);
  try
  {
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
    v8 = a1 + 8;
    if ( !a1 )
      v8 = 32;
    v9 = (void (__fastcall *)(_QWORD))_InterlockedExchange64((volatile __int64 *)v8, 1);
    if ( (unsigned __int64)v9 >= 2 )
      v9(*(_QWORD *)(v8 + 8));
    *(_QWORD *)v8 = 0;
    if ( v5 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v19);
  }
  return result;
}

```

## disassembly

```asm
0x180006e30  push    rbx
0x180006e32  push    rsi
0x180006e33  push    rdi
0x180006e34  push    r14
0x180006e36  sub     rsp, 78h
0x180006e3a  mov     rdi, rcx
0x180006e3d  xor     ebx, ebx
0x180006e3f  mov     [rsp+98h+var_78], rbx
0x180006e44  lea     r14, [rcx+30h]
0x180006e48  lea     eax, [rbx+48h]
0x180006e4b  test    rcx, rcx
0x180006e4e  cmovz   r14, rax
0x180006e52  mov     rcx, r14; SRWLock
0x180006e55  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180006e5a  lea     rcx, [rdi+48h]
0x180006e5e  lea     eax, [rbx+60h]
0x180006e61  test    rdi, rdi
0x180006e64  cmovz   rcx, rax
0x180006e68  mov     eax, [rcx]
0x180006e6a  xor     esi, esi
0x180006e6c  test    eax, eax
0x180006e6e  jnz     loc_180006F52
0x180006e74  mov     dword ptr [rcx], 2
0x180006e7a  mov     [rsp+98h+var_48], ebx
0x180006e7e  xorps   xmm0, xmm0
0x180006e81  movdqu  [rsp+98h+var_40], xmm0
0x180006e87  mov     edx, 800704C7h
0x180006e8c  mov     [rsp+98h+bstrString], rbx
0x180006e91  mov     [rsp+98h+var_58], 0AABBCCDDh
0x180006e99  mov     [rsp+98h+var_54], edx
0x180006e9d  mov     [rsp+98h+var_50], rbx
0x180006ea2  lea     r9, [rsp+98h+var_48]
0x180006ea7  xor     r8d, r8d
0x180006eaa  lea     rcx, [rsp+98h+bstrString]
0x180006eaf  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x180006eb4  xorps   xmm0, xmm0
0x180006eb7  movdqu  [rsp+98h+var_70], xmm0
0x180006ebd  lea     rcx, [rsp+98h+var_70]
0x180006ec2  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180006ec8  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x180006ecf  lea     rdx, [rsp+98h+bstrString]
0x180006ed4  lea     rcx, [rsp+98h+var_70]
0x180006ed9  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x180006edf  cmp     [rsp+98h+var_50], rbx
0x180006ee4  jz      short loc_180006EF0
0x180006ee6  lea     rcx, [rsp+98h+var_50]
0x180006eeb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006ef0  mov     rcx, [rsp+98h+bstrString]; bstrString
0x180006ef5  test    rcx, rcx
0x180006ef8  jz      short loc_180006F04
0x180006efa  call    WINRT_IMPL_SysFreeString
0x180006eff  mov     [rsp+98h+bstrString], rbx
0x180006f04  lea     rcx, [rdi+20h]
0x180006f08  mov     eax, 38h ; '8'
0x180006f0d  test    rdi, rdi
0x180006f10  cmovz   rcx, rax
0x180006f14  lea     rdx, [rsp+98h+var_70]
0x180006f19  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180006f1f  lea     rcx, [rsp+98h+var_70]
0x180006f24  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180006f2a  lea     rax, [rdi+40h]
0x180006f2e  mov     ecx, 58h ; 'X'
0x180006f33  test    rdi, rdi
0x180006f36  cmovz   rax, rcx
0x180006f3a  lea     rcx, [rsp+98h+var_78]
0x180006f3f  cmp     rcx, rax
0x180006f42  jz      short loc_180006F52
0x180006f44  mov     rbx, [rax]
0x180006f47  mov     [rax], rsi
0x180006f4a  mov     [rsp+98h+var_78], rbx
0x180006f4f  mov     rsi, rbx
0x180006f52  mov     rcx, r14; SRWLock
0x180006f55  call    ReleaseSRWLockExclusive_0
0x180006f5a  test    rsi, rsi
0x180006f5d  jz      short loc_180006F6E
0x180006f5f  mov     rax, [rbx]
0x180006f62  mov     rcx, rbx
0x180006f65  mov     rax, [rax+18h]
0x180006f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f6e  lea     rbx, [rdi+8]
0x180006f72  mov     eax, 20h ; ' '
0x180006f77  test    rdi, rdi
0x180006f7a  cmovz   rbx, rax
0x180006f7e  mov     eax, 1
0x180006f83  xchg    rax, [rbx]
0x180006f86  cmp     rax, 2
0x180006f8a  jb      short loc_180006F95
0x180006f8c  mov     rcx, [rbx+8]
0x180006f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f95  nop
0x180006f96  mov     qword ptr [rbx], 0
0x180006f9d  test    rsi, rsi
0x180006fa0  jz      short loc_180006FAD
0x180006fa2  lea     rcx, [rsp+98h+var_78]
0x180006fa7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006fac  nop
0x180006fad  xor     eax, eax
0x180006faf  jmp     short loc_180006FB8
0x180006fb1  mov     eax, [rsp+98h+arg_0]
0x180006fb8  add     rsp, 78h
0x180006fbc  pop     r14
0x180006fbe  pop     rdi
0x180006fbf  pop     rsi
0x180006fc0  pop     rbx
0x180006fc1  retn
```

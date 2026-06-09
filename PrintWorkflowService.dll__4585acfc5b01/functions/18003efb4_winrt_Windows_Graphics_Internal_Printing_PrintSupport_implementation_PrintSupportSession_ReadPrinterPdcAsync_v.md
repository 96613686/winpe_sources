# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync(void)

- ea: `0x18003efb4`
- end: `0x18003f0d3`
- name: `?ReadPrinterPdcAsync@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUIAsyncAction@Foundation@78@XZ`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800388a4`

## callees

- `0x180003ca0`
- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x18003ed20`
- `0x18004106c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003f071`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003f071`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rsi
  _QWORD *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9

  v4 = operator new(0xF0u);
  v5 = (__int64)(v4 + 14);
  v4[29] = a1;
  v4[14] = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync__ResumeCoro_1;
  *((_DWORD *)v4 + 30) = 65538;
  v6 = v4;
  memset_0(v4, 0, 0x68u);
  v6[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  v6[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v6 + 1));
  v6[1] = 1;
  v6[4] = 0;
  v6[5] = 0;
  *((_BYTE *)v6 + 48) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  v6[7] = 0;
  v6[8] = 0;
  __ExceptionPtrCreate(v6 + 7);
  v6[9] = 0;
  v6[10] = 0;
  v6[11] = 0;
  *((_DWORD *)v6 + 24) = 0;
  *((_BYTE *)v6 + 100) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::get_return_object(
    v5 - 112,
    a2);
  *(_BYTE *)(v5 + 112) = 0;
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync__ResumeCoro_1(
    v5,
    v7,
    v8,
    v9);
  return a2;
}

```

## disassembly

```asm
0x18003efb4  mov     [rsp+arg_0], rbx
0x18003efb9  mov     [rsp+arg_10], rbp
0x18003efbe  mov     [rsp+arg_8], rdx
0x18003efc3  push    rsi
0x18003efc4  push    rdi
0x18003efc5  push    r14
0x18003efc7  sub     rsp, 40h
0x18003efcb  mov     rax, cs:__security_cookie
0x18003efd2  xor     rax, rsp
0x18003efd5  mov     [rsp+58h+var_20], rax
0x18003efda  mov     rbp, rdx
0x18003efdd  mov     rbx, rcx
0x18003efe0  mov     r14d, 70h ; 'p'
0x18003efe6  lea     rcx, [r14+80h]; Size
0x18003efed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003eff2  mov     [rsp+58h+var_38], rax
0x18003eff7  lea     rsi, [r14+rax]
0x18003effb  mov     [rsp+58h+var_38], rsi
0x18003f000  mov     [rsi+r14+8], rbx
0x18003f005  lea     rax, winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__ReadPrinterPdcAsync$_ResumeCoro$1
0x18003f00c  mov     [rsi], rax
0x18003f00f  mov     dword ptr [rsi+8], 10002h
0x18003f016  lea     rdi, [rsi-70h]
0x18003f01a  xor     edx, edx; Val
0x18003f01c  lea     r8d, [r14-8]; Size
0x18003f020  mov     rcx, rdi; void *
0x18003f023  call    memset_0
0x18003f028  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x18003f02f  mov     [rdi+10h], rax
0x18003f033  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18003f03a  mov     [rdi+18h], rax
0x18003f03e  lea     rcx, [rdi+8]
0x18003f042  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x18003f047  mov     qword ptr [rdi+8], 1
0x18003f04f  xor     ebx, ebx
0x18003f051  mov     [rdi+20h], rbx
0x18003f055  mov     [rdi+28h], rbx
0x18003f059  mov     [rdi+30h], bl
0x18003f05c  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x18003f063  mov     [rdi], rax
0x18003f066  lea     rcx, [rdi+38h]
0x18003f06a  mov     [rcx], rbx
0x18003f06d  mov     [rcx+8], rbx
0x18003f071  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003f077  mov     [rdi+48h], rbx
0x18003f07b  mov     [rdi+50h], rbx
0x18003f07f  mov     [rdi+58h], rbx
0x18003f083  xor     eax, eax
0x18003f085  mov     [rdi+60h], eax
0x18003f088  mov     [rdi+64h], bl
0x18003f08b  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x18003f092  mov     [rdi], rax
0x18003f095  mov     rdx, rbp
0x18003f098  mov     rcx, rdi
0x18003f09b  call    ?get_return_object@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA?AUIAsyncAction@Foundation@Windows@3@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::get_return_object(void)
0x18003f0a0  nop
0x18003f0a1  xor     eax, eax
0x18003f0a3  mov     [rsi+r14], al
0x18003f0a7  mov     rcx, rsi
0x18003f0aa  call    winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__ReadPrinterPdcAsync$_ResumeCoro$1
0x18003f0af  nop
0x18003f0b0  mov     rax, rbp
0x18003f0b3  mov     rcx, [rsp+58h+var_20]
0x18003f0b8  xor     rcx, rsp; StackCookie
0x18003f0bb  call    __security_check_cookie
0x18003f0c0  mov     rbx, [rsp+58h+arg_0]
0x18003f0c5  mov     rbp, [rsp+58h+arg_10]
0x18003f0ca  add     rsp, 40h
0x18003f0ce  pop     r14
0x18003f0d0  pop     rdi
0x18003f0d1  pop     rsi
0x18003f0d2  retn
```

# winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint> const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>,void> const &,winrt::Windows::Foundation::AsyncStatus const &)

- ea: `0x180005b18`
- end: `0x180005b67`
- name: `??$invoke@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBU?$AsyncOperationCompletedHandler@I@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000917c`
- `0x1800097e0`

## callees

- `0x180005b18`
- `0x180009c90`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>,void>,enum winrt::Windows::Foundation::AsyncStatus>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3)
{
  winrt::impl *v4; // rcx
  _DWORD *v5; // rdx
  _DWORD v6[10]; // [rsp+0h] [rbp-48h] BYREF
  __int128 v7; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+50h] [rbp+8h]

  v6[8] = 0;
  v7 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*a1 + 24LL))(*a1, a2 + 16, *a3) < 0 )
  {
    try
    {
      winrt::throw_hresult();
    }
    catch ( ... )
    {
      v5 = v6;
      *((_BYTE *)v5 + 80) = winrt::impl::report_failed_invoke(v4);
      return v8;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180005b18  sub     rsp, 48h
0x180005b1c  add     rdx, 10h
0x180005b20  mov     [rsp+48h+arg_0], rdx
0x180005b25  mov     [rsp+48h+var_28], 0
0x180005b2d  xorps   xmm0, xmm0
0x180005b30  movdqu  [rsp+48h+var_20], xmm0
0x180005b36  mov     rcx, [rcx]
0x180005b39  mov     rax, [rcx]
0x180005b3c  mov     r8d, [r8]
0x180005b3f  mov     rax, [rax+18h]
0x180005b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b48  test    eax, eax
0x180005b4a  js      short loc_180005B59
0x180005b4c  mov     al, 1
0x180005b4e  jmp     short loc_180005B54
0x180005b50  mov     al, byte ptr [rsp+48h+arg_0]
0x180005b54  add     rsp, 48h
0x180005b58  retn
0x180005b59  lea     rdx, [rsp+48h+var_28]
0x180005b5e  mov     ecx, eax
0x180005b60  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

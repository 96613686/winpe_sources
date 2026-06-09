# winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x1800086c0`
- end: `0x18000870c`
- name: `?GetIids@?$produce_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `76`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800086c0`
- `0x1800162c8`
- `0x18001cf40`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo,void>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  void *v4; // rax

  _mm_lfence();
  *a2 = 2;
  v4 = WINRT_IMPL_CoTaskMemAlloc(0x20u);
  *a3 = v4;
  if ( !v4 )
    return 2147942414LL;
  memmove(
    v4,
    winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>>::value,
    0x20u);
  return 0;
}

```

## disassembly

```asm
0x1800086c0  push    rbx
0x1800086c2  sub     rsp, 20h
0x1800086c6  mov     rbx, r8
0x1800086c9  lfence
0x1800086cc  mov     ecx, 20h ; ' '; cb
0x1800086d1  mov     dword ptr [rdx], 2
0x1800086d7  call    WINRT_IMPL_CoTaskMemAlloc
0x1800086dc  mov     [rbx], rax
0x1800086df  test    rax, rax
0x1800086e2  jnz     short loc_1800086EF
0x1800086e4  mov     eax, 8007000Eh
0x1800086e9  add     rsp, 20h
0x1800086ed  pop     rbx
0x1800086ee  retn
0x1800086ef  mov     r8d, 20h ; ' '; Size
0x1800086f5  lea     rdx, ?value@?$uncloaked_iids@U?$interface_list@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@234@@impl@winrt@@@impl@winrt@@2V?$array@Uguid@winrt@@$01@std@@B; Src
0x1800086fc  mov     rcx, rax; void *
0x1800086ff  call    memmove
0x180008704  xor     eax, eax
0x180008706  add     rsp, 20h
0x18000870a  pop     rbx
0x18000870b  retn
```

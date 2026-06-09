# winrt::implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::GetIids(ulong *,_GUID * *)

- ea: `0x18000c5b0`
- end: `0x18000c64a`
- name: `?GetIids@?$implements@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@U?$IMapView@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@5673@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@5673@@winrt@@QEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a420`
- `0x18000a6c0`
- `0x18000a870`
- `0x18000aaa0`
- `0x180025b10`
- `0x180025f60`

## callees

- `0x18000c5b0`
- `0x180034ef0`
- `0x1800398a5`
- `0x18003bed0`
- `0x18003c020`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  void *v6; // rax
  unsigned int v8; // [rsp+20h] [rbp-28h] BYREF
  void *Src; // [rsp+28h] [rbp-20h]

  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 32LL))(a1, &v8);
  if ( v8 )
  {
    _mm_lfence();
    v5 = v8;
    *a2 = v8;
    v6 = WINRT_IMPL_CoTaskMemAlloc(16 * v5);
    *a3 = v6;
    if ( !v6 )
      return 2147942414LL;
    memmove(v6, Src, 16LL * v8);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c5b0  mov     [rsp+arg_18], rbx
0x18000c5b5  push    rdi
0x18000c5b6  sub     rsp, 40h
0x18000c5ba  mov     rax, cs:__security_cookie
0x18000c5c1  xor     rax, rsp
0x18000c5c4  mov     [rsp+48h+var_18], rax
0x18000c5c9  mov     rax, [rcx]
0x18000c5cc  mov     rbx, rdx
0x18000c5cf  lea     rdx, [rsp+48h+var_28]
0x18000c5d4  mov     rdi, r8
0x18000c5d7  mov     rax, [rax+20h]
0x18000c5db  call    cs:__guard_dispatch_icall_fptr
0x18000c5e1  cmp     [rsp+48h+var_28], 0
0x18000c5e6  jbe     short loc_18000C623
0x18000c5e8  lfence
0x18000c5eb  mov     eax, [rsp+48h+var_28]
0x18000c5ef  mov     ecx, eax
0x18000c5f1  mov     [rbx], eax
0x18000c5f3  shl     rcx, 4; cb
0x18000c5f7  call    WINRT_IMPL_CoTaskMemAlloc
0x18000c5fc  mov     [rdi], rax
0x18000c5ff  test    rax, rax
0x18000c602  jnz     short loc_18000C60B
0x18000c604  mov     eax, 8007000Eh
0x18000c609  jmp     short loc_18000C632
0x18000c60b  mov     r8d, [rsp+48h+var_28]
0x18000c610  mov     rcx, rax; void *
0x18000c613  mov     rdx, [rsp+48h+Src]; Src
0x18000c618  shl     r8, 4; Size
0x18000c61c  call    memmove
0x18000c621  jmp     short loc_18000C630
0x18000c623  mov     dword ptr [rbx], 0
0x18000c629  mov     qword ptr [rdi], 0
0x18000c630  xor     eax, eax
0x18000c632  mov     rcx, [rsp+48h+var_18]
0x18000c637  xor     rcx, rsp; StackCookie
0x18000c63a  call    __security_check_cookie
0x18000c63f  mov     rbx, [rsp+48h+arg_18]
0x18000c644  add     rsp, 40h
0x18000c648  pop     rdi
0x18000c649  retn
```

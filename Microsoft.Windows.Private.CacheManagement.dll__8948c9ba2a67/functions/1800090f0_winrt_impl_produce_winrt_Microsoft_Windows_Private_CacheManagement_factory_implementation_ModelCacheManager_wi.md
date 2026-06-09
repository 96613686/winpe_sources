# winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory>::ActivateInstance(void * *)

- ea: `0x1800090f0`
- end: `0x18000911c`
- name: `?ActivateInstance@?$produce@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `44`
- prototype: `void __fastcall __noreturn(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009ca0`
- `0x180009cb0`
- `0x180009df0`

## pseudocode

```c
void __fastcall __noreturn winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory>::ActivateInstance(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // rax
  __int64 *v3; // rdx
  __int64 v4; // [rsp+0h] [rbp-28h] BYREF
  int v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v2 = winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::shim();
  _tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(&v5, v2);
  try
  {
    winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManagerT<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::ActivateInstance();
  }
  catch ( ... )
  {
    v3 = &v4;
    *((_DWORD *)v3 + 14) = *(_DWORD *)winrt::to_hresult(v3 + 7);
  }
}

```

## disassembly

```asm
0x1800090f0  sub     rsp, 28h
0x1800090f4  mov     qword ptr [rdx], 0
0x1800090fb  call    ?shim@?$produce_base@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@X@impl@winrt@@QEAAAEAUModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@3@XZ; winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::shim(void)
0x180009100  mov     rdx, rax
0x180009103  lea     rcx, [rsp+28h+arg_8]
0x180009108  call    ??0?$_tlgWrapSz@_W@@QEAA@PEB_W@Z; _tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(wchar_t const *)
0x18000910d  call    ?ActivateInstance@?$ModelCacheManagerT@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U1implementation@34567@$$V@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEBA?AUIInspectable@Foundation@57@XZ; winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManagerT<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::ActivateInstance(void)
0x180009113  mov     eax, [rsp+28h+arg_8]
0x180009117  add     rsp, 28h
0x18000911b  retn
```

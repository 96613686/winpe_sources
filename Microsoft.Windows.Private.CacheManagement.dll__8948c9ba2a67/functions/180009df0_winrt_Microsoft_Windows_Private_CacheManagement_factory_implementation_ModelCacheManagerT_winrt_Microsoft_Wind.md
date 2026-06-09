# winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManagerT<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::ActivateInstance(void)

- ea: `0x180009df0`
- end: `0x180009e10`
- name: `?ActivateInstance@?$ModelCacheManagerT@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U1implementation@34567@$$V@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEBA?AUIInspectable@Foundation@57@XZ`
- size: `32`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800090f0`

## callees

- `0x18000e060`
- `0x180019c0c`

## pseudocode

```c
void __noreturn winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManagerT<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::ActivateInstance()
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject);
  throw (winrt::hresult_not_implemented *)pExceptionObject;
}

```

## disassembly

```asm
0x180009df0  sub     rsp, 48h
0x180009df4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180009df9  call    ??0hresult_not_implemented@winrt@@QEAA@XZ
0x180009dfe  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180009e05  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180009e0a  call    _CxxThrowException
```

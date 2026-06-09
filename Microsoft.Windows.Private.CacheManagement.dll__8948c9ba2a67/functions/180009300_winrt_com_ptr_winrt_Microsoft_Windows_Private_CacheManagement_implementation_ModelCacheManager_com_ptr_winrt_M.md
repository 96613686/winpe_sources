# winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::~com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>(void)

- ea: `0x180009300`
- end: `0x18000930b`
- name: `??1?$com_ptr@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@winrt@@QEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001da89`
- `0x18001fb50`

## callees

- `0x18000ac20`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::~com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref();
  return result;
}

```

## disassembly

```asm
0x180009300  cmp     qword ptr [rcx], 0
0x180009304  jnz     ?unconditional_release_ref@?$com_ptr@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref(void)
0x18000930a  retn
```

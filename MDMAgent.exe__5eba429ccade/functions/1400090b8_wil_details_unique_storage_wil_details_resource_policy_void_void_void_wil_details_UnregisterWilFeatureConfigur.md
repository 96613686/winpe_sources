# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1400090b8`
- end: `0x1400090ce`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009160`

## callees

- `0x1400090b8`
- `0x140011e70`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return wil_details_RtlUnregisterFeatureConfigurationChangeNotification();
  return result;
}

```

## disassembly

```asm
0x1400090b8  sub     rsp, 28h
0x1400090bc  mov     rcx, [rcx]
0x1400090bf  test    rcx, rcx
0x1400090c2  jz      short loc_1400090C9
0x1400090c4  call    wil_details_RtlUnregisterFeatureConfigurationChangeNotification
0x1400090c9  add     rsp, 28h
0x1400090cd  retn
```

# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000949c`
- end: `0x1400094b3`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009548`

## callees

- `0x14000949c`
- `0x140012690`

## pseudocode

```c
__int64 (*__fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1))(void)
{
  __int64 v1; // rcx
  __int64 (*result)(void); // rax

  v1 = *a1;
  if ( v1 )
    return wil_details_RtlUnregisterFeatureConfigurationChangeNotification(v1);
  return result;
}

```

## disassembly

```asm
0x14000949c  sub     rsp, 28h
0x1400094a0  mov     rcx, [rcx]
0x1400094a3  test    rcx, rcx
0x1400094a6  jz      short loc_1400094AD
0x1400094a8  call    wil_details_RtlUnregisterFeatureConfigurationChangeNotification
0x1400094ad  add     rsp, 28h
0x1400094b1  retn
```

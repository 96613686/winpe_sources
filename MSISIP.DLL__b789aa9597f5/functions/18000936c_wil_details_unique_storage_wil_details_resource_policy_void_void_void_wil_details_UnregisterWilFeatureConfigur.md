# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000936c`
- end: `0x180009382`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006370`

## callees

- `0x18000936c`
- `0x18000d168`

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
0x18000936c  sub     rsp, 28h
0x180009370  mov     rcx, [rcx]
0x180009373  test    rcx, rcx
0x180009376  jz      short loc_18000937D
0x180009378  call    wil_details_RtlUnregisterFeatureConfigurationChangeNotification
0x18000937d  add     rsp, 28h
0x180009381  retn
```

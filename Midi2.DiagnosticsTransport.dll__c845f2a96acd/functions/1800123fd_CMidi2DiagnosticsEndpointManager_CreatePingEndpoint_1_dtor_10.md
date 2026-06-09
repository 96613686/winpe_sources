# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$10

- ea: `0x1800123fd`
- end: `0x180012409`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c924`

## pseudocode

```c
void __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)(a2 + 96));
}

```

## disassembly

```asm
0x1800123fd  lea     rcx, [rdx+60h]
0x180012404  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
```

# _WOSCOneSettings::ParseJsonBlob_::_1_::dtor$12

- ea: `0x180019e82`
- end: `0x180019ea8`
- name: `_WOSCOneSettings::ParseJsonBlob_::_1_::dtor$12`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180006df8`
- `0x180019e82`

## pseudocode

```c
void __fastcall WOSCOneSettings::ParseJsonBlob_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 72) & 2) != 0 )
  {
    *(_DWORD *)(a2 + 72) &= ~2u;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)(a2 + 96));
  }
}

```

## disassembly

```asm
0x180019e82  push    rbp
0x180019e84  sub     rsp, 20h
0x180019e88  mov     rbp, rdx
0x180019e8b  mov     eax, [rbp+48h]
0x180019e8e  and     eax, 2
0x180019e91  test    eax, eax
0x180019e93  jz      short loc_180019EA2
0x180019e95  and     dword ptr [rbp+48h], 0FFFFFFFDh
0x180019e99  lea     rcx, [rbp+60h]
0x180019e9d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180019ea2  add     rsp, 20h
0x180019ea6  pop     rbp
0x180019ea7  retn
```

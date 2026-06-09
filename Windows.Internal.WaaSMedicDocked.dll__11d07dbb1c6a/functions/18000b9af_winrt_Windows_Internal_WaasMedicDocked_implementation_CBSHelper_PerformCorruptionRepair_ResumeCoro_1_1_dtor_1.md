# _winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::dtor$1

- ea: `0x18000b9af`
- end: `0x18000b9dd`
- name: `_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::dtor$1`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180006958`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair__ResumeCoro_1_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  *(_QWORD *)(a2 + 152) = *(_QWORD *)(a2 + 240) + 32LL;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(*(void ***)(a2 + 152));
}

```

## disassembly

```asm
0x18000b9af  push    rbp
0x18000b9b1  sub     rsp, 20h
0x18000b9b5  mov     rbp, rdx
0x18000b9b8  mov     eax, 20h ; ' '
0x18000b9bd  add     rax, [rbp+0F0h]
0x18000b9c4  mov     [rbp+98h], rax
0x18000b9cb  mov     rcx, [rbp+98h]
0x18000b9d2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000b9d7  add     rsp, 20h
0x18000b9db  pop     rbp
0x18000b9dc  retn
```

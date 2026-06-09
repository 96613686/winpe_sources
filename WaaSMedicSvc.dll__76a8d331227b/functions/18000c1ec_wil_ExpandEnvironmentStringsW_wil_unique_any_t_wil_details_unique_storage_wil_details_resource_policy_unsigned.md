# _wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t______256__::_1_::dtor$0

- ea: `0x18000c1ec`
- end: `0x18000c212`
- name: `_wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t______256__::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180008fa8`
- `0x18000c1ec`

## pseudocode

```c
void __fastcall wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t______256__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(*(void ***)(a2 + 64));
  }
}

```

## disassembly

```asm
0x18000c1ec  push    rbp
0x18000c1ee  sub     rsp, 20h
0x18000c1f2  mov     rbp, rdx
0x18000c1f5  mov     eax, [rbp+20h]
0x18000c1f8  and     eax, 1
0x18000c1fb  test    eax, eax
0x18000c1fd  jz      short loc_18000C20C
0x18000c1ff  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000c203  mov     rcx, [rbp+40h]
0x18000c207  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18000c20c  add     rsp, 20h
0x18000c210  pop     rbp
0x18000c211  retn
```

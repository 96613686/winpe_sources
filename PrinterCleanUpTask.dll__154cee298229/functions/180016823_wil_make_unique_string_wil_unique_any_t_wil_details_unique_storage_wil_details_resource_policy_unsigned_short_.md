# _wil::make_unique_string_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t________::_1_::dtor$0

- ea: `0x180016823`
- end: `0x180016849`
- name: `_wil::make_unique_string_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t________::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x18000a694`
- `0x180016823`

## pseudocode

```c
__int64 __fastcall wil::make_unique_string_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t________::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(*(_QWORD *)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x180016823  push    rbp
0x180016825  sub     rsp, 20h
0x180016829  mov     rbp, rdx
0x18001682c  mov     eax, [rbp+20h]
0x18001682f  and     eax, 1
0x180016832  test    eax, eax
0x180016834  jz      short loc_180016843
0x180016836  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18001683a  mov     rcx, [rbp+40h]
0x18001683e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x180016843  add     rsp, 20h
0x180016847  pop     rbp
0x180016848  retn
```

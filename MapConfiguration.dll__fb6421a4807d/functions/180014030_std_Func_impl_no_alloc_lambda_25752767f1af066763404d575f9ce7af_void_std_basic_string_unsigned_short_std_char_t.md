# std::_Func_impl_no_alloc__lambda_25752767f1af066763404d575f9ce7af__void_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const_&_::_Do_call

- ea: `0x180014030`
- end: `0x18001406a`
- name: `std::_Func_impl_no_alloc__lambda_25752767f1af066763404d575f9ce7af__void_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const_&_::_Do_call`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000c2f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001405f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001405f`

## pseudocode

```c
LSTATUS __fastcall std::_Func_impl_no_alloc__lambda_25752767f1af066763404d575f9ce7af__void_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___::_Do_call(
        __int64 a1,
        __int64 a2)
{
  const WCHAR *v2; // rax
  __int64 v3; // r8

  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 1u, (PHKEY)(*(_QWORD *)(v3 + 8) + 8LL));
}

```

## disassembly

```asm
0x180014030  sub     rsp, 38h
0x180014034  mov     r8, rcx
0x180014037  mov     rcx, rdx
0x18001403a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001403f  mov     rcx, [r8+8]
0x180014043  mov     r9d, 1; samDesired
0x180014049  add     rcx, 8
0x18001404d  xor     r8d, r8d; ulOptions
0x180014050  mov     [rsp+38h+phkResult], rcx; phkResult
0x180014055  mov     rdx, rax; lpSubKey
0x180014058  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001405f  call    cs:__imp_RegOpenKeyExW
0x180014065  add     rsp, 38h
0x180014069  retn
```

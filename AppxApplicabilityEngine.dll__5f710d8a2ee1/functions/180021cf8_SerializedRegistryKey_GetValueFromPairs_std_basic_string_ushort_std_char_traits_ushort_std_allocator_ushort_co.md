# SerializedRegistryKey::GetValueFromPairs(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &)

- ea: `0x180021cf8`
- end: `0x180021d5f`
- name: `?GetValueFromPairs@SerializedRegistryKey@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@AEBV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010c40`
- `0x1800218a0`

## callees

- `0x18000d8f8`
- `0x18000f768`
- `0x18002158c`
- `0x180021cf8`

## pseudocode

```c
__int64 __fastcall SerializedRegistryKey::GetValueFromPairs(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = a1;
  std::find_if_std::_Vector_const_iterator_std::_Vector_val_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____________lambda_b212412e5cb9c0b88399e750b54ee717___(
    &v7,
    *a4,
    a4[1],
    a3);
  if ( v7 == a4[1] )
    std::wstring::wstring(a2, &qword_18002C640);
  else
    std::wstring::substr(v7 + 40, a2, 1, -1);
  return a2;
}

```

## disassembly

```asm
0x180021cf8  mov     [rsp+arg_8], rbx
0x180021cfd  mov     [rsp+arg_0], rcx
0x180021d02  push    rdi
0x180021d03  sub     rsp, 30h
0x180021d07  mov     rbx, r9
0x180021d0a  lea     rcx, [rsp+38h+arg_0]
0x180021d0f  mov     rdi, rdx
0x180021d12  mov     r9, r8
0x180021d15  mov     r8, [rbx+8]
0x180021d19  mov     rdx, [rbx]
0x180021d1c  call    std__find_if_std___Vector_const_iterator_std___Vector_val_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__allocator_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____________lambda_b212412e5cb9c0b88399e750b54ee717___
0x180021d21  mov     rcx, [rsp+38h+arg_0]
0x180021d26  cmp     rcx, [rbx+8]
0x180021d2a  jnz     short loc_180021D3D
0x180021d2c  lea     rdx, qword_18002C640
0x180021d33  mov     rcx, rdi
0x180021d36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180021d3b  jmp     short loc_180021D51
0x180021d3d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021d41  add     rcx, 28h ; '('
0x180021d45  mov     rdx, rdi
0x180021d48  lea     r8d, [r9+2]
0x180021d4c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180021d51  mov     rbx, [rsp+38h+arg_8]
0x180021d56  mov     rax, rdi
0x180021d59  add     rsp, 30h
0x180021d5d  pop     rdi
0x180021d5e  retn
```

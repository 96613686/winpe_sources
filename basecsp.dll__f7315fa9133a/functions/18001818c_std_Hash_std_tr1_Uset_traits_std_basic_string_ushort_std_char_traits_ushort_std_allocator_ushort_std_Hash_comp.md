# std::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Init(unsigned __int64)

- ea: `0x18001818c`
- end: `0x1800181e9`
- name: `?_Init@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAX_K@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b3d8`
- `0x180017dfc`

## callees

- `0x18001818c`
- `0x180018344`
- `0x180018d98`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v2; // rbp
  __int64 *v4; // rbx
  __int64 v6; // rdx
  __int64 result; // rax
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v2 = 2 * a2;
  v4 = a1 + 4;
  std::vector<std::_List_const_iterator<std::_List_val<std::wstring>>>::reserve(a1 + 4, 2 * a2);
  v6 = *v4;
  v8 = a1[1];
  if ( v6 != v4[1] )
    v4[1] = v6;
  std::vector<std::_List_const_iterator<std::_List_val<std::wstring>>>::_Insert_n(v4, v6, v2, &v8);
  result = a2 - 1;
  a1[9] = a2;
  a1[8] = a2 - 1;
  return result;
}

```

## disassembly

```asm
0x18001818c  push    rbx
0x18001818e  push    rbp
0x18001818f  push    rsi
0x180018190  push    rdi
0x180018191  sub     rsp, 28h
0x180018195  lea     rbp, [rdx+rdx]
0x180018199  mov     rsi, rdx
0x18001819c  lea     rbx, [rcx+20h]
0x1800181a0  mov     rdi, rcx
0x1800181a3  mov     rdx, rbp
0x1800181a6  mov     rcx, rbx
0x1800181a9  call    ?reserve@?$vector@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@V?$allocator@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::_List_const_iterator<std::_List_val<std::wstring>>>::reserve(unsigned __int64)
0x1800181ae  mov     rdx, [rbx]
0x1800181b1  mov     rax, [rdi+8]
0x1800181b5  mov     [rsp+48h+arg_0], rax
0x1800181ba  cmp     rdx, [rbx+8]
0x1800181be  jz      short loc_1800181C4
0x1800181c0  mov     [rbx+8], rdx
0x1800181c4  lea     r9, [rsp+48h+arg_0]
0x1800181c9  mov     r8, rbp
0x1800181cc  mov     rcx, rbx
0x1800181cf  call    ?_Insert_n@?$vector@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@V?$allocator@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@@std@@IEAAXV?$_Vector_const_iterator@V?$_Vector_val@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@V?$allocator@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@@std@@@2@_KAEBV?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@Z; std::vector<std::_List_const_iterator<std::_List_val<std::wstring>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_List_const_iterator<std::_List_val<std::wstring>>>>,unsigned __int64,std::_List_const_iterator<std::_List_val<std::wstring>> const &)
0x1800181d4  lea     rax, [rsi-1]
0x1800181d8  mov     [rdi+48h], rsi
0x1800181dc  mov     [rdi+40h], rax
0x1800181e0  add     rsp, 28h
0x1800181e4  pop     rdi
0x1800181e5  pop     rsi
0x1800181e6  pop     rbp
0x1800181e7  pop     rbx
0x1800181e8  retn
```

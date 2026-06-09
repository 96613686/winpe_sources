# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Init(unsigned __int64)

- ea: `0x18000c794`
- end: `0x18000c822`
- name: `?_Init@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `8`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800093d0`
- `0x18000bab0`
- `0x18000c458`
- `0x18000e0a8`
- `0x18000f9f4`
- `0x1800104e4`
- `0x180011f40`
- `0x180012560`

## callees

- `0x18000c794`
- `0x18000c828`
- `0x18000cb18`
- `0x18000cd9c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(
        __int64 *a1,
        __int64 a2)
{
  __int64 *v2; // rbx
  unsigned __int64 v4; // rdi
  __int64 v6; // r8
  __int64 result; // rax
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  char v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = a1 + 2;
  v4 = 2 * a2;
  if ( (a1[4] - a1[2]) >> 3 < (unsigned __int64)(2 * a2) )
  {
    if ( v4 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
    std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>>::_Reallocate(
      a1 + 2,
      v4);
  }
  v6 = *v2;
  v8 = *a1;
  v2[1] = v6;
  std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>>::_Insert_n(
    (_DWORD)v2,
    (unsigned int)&v9,
    v6,
    v4,
    (__int64)&v8);
  result = a2 - 1;
  a1[5] = a2 - 1;
  a1[6] = a2;
  return result;
}

```

## disassembly

```asm
0x18000c794  mov     [rsp+arg_10], rbx
0x18000c799  push    rsi
0x18000c79a  push    rdi
0x18000c79b  push    r14
0x18000c79d  sub     rsp, 30h
0x18000c7a1  lea     rbx, [rcx+10h]
0x18000c7a5  mov     r14, rdx
0x18000c7a8  mov     rax, [rbx+10h]
0x18000c7ac  lea     rdi, [rdx+rdx]
0x18000c7b0  sub     rax, [rbx]
0x18000c7b3  mov     rsi, rcx
0x18000c7b6  sar     rax, 3
0x18000c7ba  cmp     rax, rdi
0x18000c7bd  jnb     short loc_18000C7D9
0x18000c7bf  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000c7c9  cmp     rdi, rax
0x18000c7cc  ja      short loc_18000C81C
0x18000c7ce  mov     rdx, rdi
0x18000c7d1  mov     rcx, rbx
0x18000c7d4  call    ?_Reallocate@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>>::_Reallocate(unsigned __int64)
0x18000c7d9  mov     rax, [rsi]
0x18000c7dc  lea     rdx, [rsp+48h+arg_8]
0x18000c7e1  mov     r8, [rbx]
0x18000c7e4  mov     r9, rdi
0x18000c7e7  mov     [rsp+48h+arg_0], rax
0x18000c7ec  mov     rcx, rbx
0x18000c7ef  lea     rax, [rsp+48h+arg_0]
0x18000c7f4  mov     [rbx+8], r8
0x18000c7f8  mov     [rsp+48h+var_28], rax
0x18000c7fd  call    ?_Insert_n@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>>,unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> const &)
0x18000c802  mov     rbx, [rsp+48h+arg_10]
0x18000c807  lea     rax, [r14-1]
0x18000c80b  mov     [rsi+28h], rax
0x18000c80f  mov     [rsi+30h], r14
0x18000c813  add     rsp, 30h
0x18000c817  pop     r14
0x18000c819  pop     rdi
0x18000c81a  pop     rsi
0x18000c81b  retn
0x18000c81c  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
```

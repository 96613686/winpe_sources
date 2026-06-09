# std::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>)

- ea: `0x180018b6c`
- end: `0x180018bfd`
- name: `?erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@V32@@Z`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002d865`

## callees

- `0x1800180d4`
- `0x180018b6c`
- `0x180018c94`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::erase(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // rcx
  _QWORD *result; // rax
  char v10; // [rsp+30h] [rbp+8h] BYREF

  v6 = std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Hashval(
         a1,
         a3 + 2);
  v7 = *(_QWORD *)(a1 + 32);
  if ( *(_QWORD **)(v7 + 16 * v6 + 8) == a3 )
  {
    if ( *(_QWORD **)(v7 + 16 * v6) == a3 )
    {
      *(_QWORD *)(v7 + 16 * v6) = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 16 * v6 + 8) = *(_QWORD *)(a1 + 8);
    }
    else
    {
      *(_QWORD *)(v7 + 16 * v6 + 8) = a3[1];
    }
  }
  else if ( *(_QWORD **)(v7 + 16 * v6) == a3 )
  {
    *(_QWORD *)(v7 + 16 * v6) = *a3;
  }
  v8 = *(_QWORD *)std::list<std::wstring>::erase(a1 + 8, &v10, a3);
  result = a2;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x180018b6c  mov     [rsp+arg_8], rbx
0x180018b71  mov     [rsp+arg_10], rsi
0x180018b76  push    rdi
0x180018b77  sub     rsp, 20h
0x180018b7b  mov     rsi, rdx
0x180018b7e  mov     rbx, r8
0x180018b81  lea     rdx, [r8+10h]
0x180018b85  mov     rdi, rcx
0x180018b88  call    ?_Hashval@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Hashval(std::wstring const &)
0x180018b8d  mov     r9, [rdi+20h]
0x180018b91  mov     r8, rax
0x180018b94  add     r8, r8
0x180018b97  cmp     [r9+r8*8+8], rbx
0x180018b9c  jnz     short loc_180018BC6
0x180018b9e  cmp     [r9+r8*8], rbx
0x180018ba2  jnz     short loc_180018BBB
0x180018ba4  mov     rcx, [rdi+8]
0x180018ba8  mov     [r9+r8*8], rcx
0x180018bac  mov     rcx, [rdi+20h]
0x180018bb0  mov     rax, [rdi+8]
0x180018bb4  mov     [rcx+r8*8+8], rax
0x180018bb9  jmp     short loc_180018BD3
0x180018bbb  mov     rax, [rbx+8]
0x180018bbf  mov     [r9+r8*8+8], rax
0x180018bc4  jmp     short loc_180018BD3
0x180018bc6  cmp     [r9+r8*8], rbx
0x180018bca  jnz     short loc_180018BD3
0x180018bcc  mov     rax, [rbx]
0x180018bcf  mov     [r9+r8*8], rax
0x180018bd3  lea     rcx, [rdi+8]
0x180018bd7  mov     r8, rbx
0x180018bda  lea     rdx, [rsp+28h+arg_0]
0x180018bdf  call    ?erase@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@Z; std::list<std::wstring>::erase(std::_List_const_iterator<std::_List_val<std::wstring>>)
0x180018be4  mov     rbx, [rsp+28h+arg_8]
0x180018be9  mov     rcx, [rax]
0x180018bec  mov     rax, rsi
0x180018bef  mov     [rsi], rcx
0x180018bf2  mov     rsi, [rsp+28h+arg_10]
0x180018bf7  add     rsp, 20h
0x180018bfb  pop     rdi
0x180018bfc  retn
```

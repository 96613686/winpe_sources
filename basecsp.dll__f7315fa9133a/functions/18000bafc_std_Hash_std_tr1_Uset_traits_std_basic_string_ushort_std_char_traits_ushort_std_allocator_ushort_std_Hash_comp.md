# std::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::~_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>(void)

- ea: `0x18000bafc`
- end: `0x18000bb1c`
- name: `??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002dbc0`

## callees

- `0x18000bb78`
- `0x18000bd5c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(
        __int64 a1)
{
  std::vector<std::_List_const_iterator<std::_List_val<std::wstring>>>::~vector<std::_List_const_iterator<std::_List_val<std::wstring>>>(a1 + 32);
  return std::list<std::wstring>::~list<std::wstring>(a1 + 8);
}

```

## disassembly

```asm
0x18000bafc  push    rbx
0x18000bafe  sub     rsp, 20h
0x18000bb02  mov     rbx, rcx
0x18000bb05  add     rcx, 20h ; ' '
0x18000bb09  call    ??1?$vector@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@V?$allocator@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_const_iterator<std::_List_val<std::wstring>>>::~vector<std::_List_const_iterator<std::_List_val<std::wstring>>>(void)
0x18000bb0e  lea     rcx, [rbx+8]
0x18000bb12  add     rsp, 20h
0x18000bb16  pop     rbx
0x18000bb17  jmp     ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
```
